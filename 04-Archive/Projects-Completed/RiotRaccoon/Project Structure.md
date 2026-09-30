```mermaid
graph TD
    src["src/"]
    src --> src_assets["assets/"]
    src --> src_components["components/"]
    src --> src_config["config/"]
    src --> src_hooks["hooks/"]
    src --> src_pages["pages/"]
    src --> src_services["services/"]
    src --> src_store["store/"]
    src --> src_types["types/"]
    src --> src_utils["utils/"]
    src --> src_app["App.tsx"]
    src --> src_index["index.tsx"]

    %% Assets
    src_assets --> src_assets_icons["icons/"]
    src_assets --> src_assets_images["images/"]
    src_assets --> src_assets_styles["styles/"]
    src_assets_styles --> src_assets_styles_variables["variables.scss"]
    src_assets_styles --> src_assets_styles_global["global.scss"]

    %% Components
    src_components --> src_components_common["common/"]
    src_components --> src_components_layout["layout/"]
    src_components --> src_components_products["products/"]

    %% Common Components
    src_components_common --> src_components_common_Button["Button/"]
    src_components_common --> src_components_common_Input["Input/"]
    src_components_common --> src_components_common_Modal["Modal/"]
    src_components_common --> src_components_common_LoadingSpinner["LoadingSpinner/"]

    %% Layout Components
    src_components_layout --> src_components_layout_Header["Header/"]
    src_components_layout --> src_components_layout_Footer["Footer/"]
    src_components_layout --> src_components_layout_Navigation["Navigation/"]

    %% Product Components
    src_components_products --> src_components_products_ProductCard["ProductCard/"]
    src_components_products --> src_components_products_ProductList["ProductList/"]
    src_components_products --> src_components_products_ProductDetails["ProductDetails/"]

    %% Config
    src_config --> src_config_endpoints["endpoints.ts"]
    src_config --> src_config_constants["constants.ts"]

    %% Hooks
    src_hooks --> src_hooks_useAuth["useAuth.ts"]
    src_hooks --> src_hooks_useCart["useCart.ts"]
    src_hooks --> src_hooks_useProducts["useProducts.ts"]
    src_hooks --> src_hooks_useForm["useForm.ts"]

    %% Pages
    src_pages --> src_pages_auth["auth/"]
    src_pages --> src_pages_shop["shop/"]
    src_pages --> src_pages_user["user/"]

    %% Auth Pages
    src_pages_auth --> src_pages_auth_Login["Login.tsx"]
    src_pages_auth --> src_pages_auth_Register["Register.tsx"]

    %% Shop Pages
    src_pages_shop --> src_pages_shop_ProductList["ProductList.tsx"]
    src_pages_shop --> src_pages_shop_ProductDetail["ProductDetail.tsx"]
    src_pages_shop --> src_pages_shop_Cart["Cart.tsx"]

    %% User Pages
    src_pages_user --> src_pages_user_Profile["Profile.tsx"]
    src_pages_user --> src_pages_user_Orders["Orders.tsx"]

    %% Services
    src_services --> src_services_api["api.ts"]
    src_services --> src_services_auth["auth.service.ts"]
    src_services --> src_services_product["product.service.ts"]
    src_services --> src_services_order["order.service.ts"]

    %% Store
    src_store --> src_store_slices["slices/"]
    src_store --> src_store_store["store.ts"]

    %% Slices
    src_store_slices --> src_store_slices_auth["authSlice.ts"]
    src_store_slices --> src_store_slices_cart["cartSlice.ts"]
    src_store_slices --> src_store_slices_product["productSlice.ts"]

    %% Types
    src_types --> src_types_auth["auth.types.ts"]
    src_types --> src_types_product["product.types.ts"]
    src_types --> src_types_order["order.types.ts"]

    %% Utils
    src_utils --> src_utils_formatters["formatters.ts"]
    src_utils --> src_utils_validators["validators.ts"]
    src_utils --> src_utils_helpers["helpers.ts"]

```



