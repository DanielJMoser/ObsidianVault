Daniel — taking "which shell?" first, since the rest depends on it.

**The shell is the main myMCI Capacitor WebView** — the one running the React app at `my.mci4me.at`, with the menu, tab bar and router. It's the app you see before chat opens. `MciChatPlugin` is registered on *that* WebView's bridge (`MainActivity.java`, `registerPlugin(MciChatPlugin.class)` before `super.onCreate`, so `window.Capacitor.Plugins.MciChat` exists on the first page load). The chat WebView has no Capacitor runtime at all — `window.Capacitor` is undefined there.

## You're right that the capabilities overlap. That isn't what isolation is about.

Same camera, same filesystem, same FCM token. Absolutely. The isolation isn't preventing the chat from *using* those — it demonstrably does. It constrains **what the page is allowed to ask for**.

Compare what each channel lets JavaScript request:

| Need          | Capacitor plugin API                                                        | `mciChatBridge` equivalent                                                                                       |
| ------------- | --------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Camera        | `Camera.getPhoto()` — programmatic, returns image data to JS                | OS chooser only, via `<input type="file">` → `onShowFileChooser`. User gesture required, **user** picks the file |
| Read a file   | `Filesystem.readFile({path})` — arbitrary path in the app sandbox           | **No message type exists.** There is no read primitive                                                           |
| Write a file  | `Filesystem.writeFile({path, data})` — page chooses the path                | `save-file{fileName, mimeType, dataBase64}` — page supplies content it already has; native decides placement     |
| Stored values | `Preferences.get({key})` — reads the shell's store, including session state | `secure-storage-get` against `MciChatSecureStorage`, a separate store                                            |
| Push          | full messaging plugin surface                                               | `push-token-get` — returns a token, nothing else                                                                 |

The chat can send a photo. It cannot enumerate your photos. It can save a download. It cannot read your documents folder. Same hardware, same OS APIs underneath — a fraction of the authority.

## Why that fraction matters here specifically

The two WebViews render content at **different trust levels**. The shell renders MCI's own backend. The chat renders Matrix events: message bodies, `formatted_body` HTML, media uploaded by any user on the homeserver. That's attacker-influenced content by design.

So the question isn't "do both need a camera," it's "what happens when the sanitizer has a bug." With `mciChatBridge`, script execution in the chat WebView gets you six message types, each re-validated natively. With Capacitor attached, it gets you every registered plugin — Filesystem with the permissions declared in `capacitor.config.ts`, FirebaseMessaging, and everything else the shell has accumulated for grades, documents and evaluations. A rendering bug becomes filesystem access.

That's also why `addWebMessageListener` was chosen over `addJavascriptInterface` (`MciChatWebViewHost.java:243-251`) — the former is origin-scoped to `https://chat.mci-local`, the latter isn't.

## The structural reason one bridge can't work

Even setting security aside: **`MciChat` is the plugin that creates and destroys the chat WebView.** `open()` constructs `MciChatWebViewHost` / `MciChatWebViewController` and presents it; `close()` tears it down. Before `open()` runs, there is no chat WebView for a bridge to live in. A plugin cannot be hosted inside the thing whose existence it controls. Its callers are all shell-side for exactly this reason — `MessagesMenuItem.tsx`, `usePushService.ts`, `Playground.tsx`.

## Where your instinct is correct

There is real duplication, and it isn't free. `MciChatSecureStorage` duplicates what Preferences does. `save-file` duplicates part of Filesystem. The file-chooser plumbing in `MciChatPlugin` exists only because the chat WebView can't reach Capacitor's. Sygnal will likely add more — though note `push-token-get` is already in the protocol, so the design anticipated it, and it's a good illustration of the actual pattern: the chat doesn't register for push independently, it asks native for the token native already holds.

That duplication is the price of the trust boundary, not an accident. It's a legitimate thing to weigh — but the thing being bought is a narrow, auditable surface between untrusted content and the device, not separate hardware.