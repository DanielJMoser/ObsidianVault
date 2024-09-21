Der Diffie-Hellman Key Exchange ist ein kryptografisches Protokoll, das es zwei Parteien ermöglicht, über einen unsicheren Kommunikationskanal einen gemeinsamen geheimen Schlüssel zu vereinbaren. Dieser Schlüssel kann dann zur symmetrischen Verschlüsselung von Nachrichten verwendet werden.

## Grundprinzip

Das Protokoll basiert auf der Schwierigkeit des diskreten Logarithmusproblems in endlichen Körpern. Die beiden Parteien, oft als Alice und Bob bezeichnet, einigen sich auf zwei öffentliche Werte:

- Eine große Primzahl $p$
- Eine Ganzzahl $g$, die als Generator bezeichnet wird und eine primitive Wurzel modulo $p$ ist.

Diese Werte sind **öffentlich** und können von jedem gesehen werden, ohne die Sicherheit des Verfahrens zu beeinträchtigen.

## Schritte des Algorithmus

1. **Wahl der privaten Schlüssel:**
   - Alice wählt eine zufällige geheime Zahl $a$, die als ihr privater Schlüssel dient.
   - Bob wählt eine zufällige geheime Zahl $b$, die als sein privater Schlüssel dient.

2. **Berechnung der öffentlichen Schlüssel:**
   - Alice berechnet ihren öffentlichen Schlüssel $A$ als:
     $$ A = g^a \mod p $$
   - Bob berechnet seinen öffentlichen Schlüssel $B$ als:
     $$ B = g^b \mod p $$

   Diese beiden öffentlichen Schlüssel $A$ und $B$ werden über den unsicheren Kanal ausgetauscht.

3. **Berechnung des gemeinsamen Schlüssels:**
   - Alice berechnet den gemeinsamen geheimen Schlüssel $S$, indem sie Bobs öffentlichen Schlüssel $B$ verwendet:
     $$ S = B^a \mod p = (g^b \mod p)^a \mod p = g^{ab} \mod p $$
   - Bob berechnet den gemeinsamen geheimen Schlüssel $S$, indem er Alices öffentlichen Schlüssel $A$ verwendet:
     $$ S = A^b \mod p = (g^a \mod p)^b \mod p = g^{ab} \mod p $$

   Beide berechneten Werte sind gleich, sodass Alice und Bob denselben geheimen Schlüssel $S$ erhalten.

## Sicherheit des Verfahrens

Die Sicherheit des Diffie-Hellman-Verfahrens basiert auf dem diskreten Logarithmusproblem, das wie folgt lautet: Angenommen, ein Angreifer kennt $g$, $p$ und die öffentlichen Schlüssel $A$ und $B$, es ist dennoch extrem schwierig, $a$ oder $b$ zu berechnen. Somit kann der gemeinsame Schlüssel $g^{ab} \mod p$ nicht leicht ermittelt werden.

## Beispiel

Angenommen, Alice und Bob wählen $p = 23$ und $g = 5$.
- Alice wählt ihren geheimen Schlüssel $a = 6$ und berechnet ihren öffentlichen Schlüssel:
  $$ A = 5^6 \mod 23 = 15625 \mod 23 = 8 $$
- Bob wählt seinen geheimen Schlüssel $b = 15$ und berechnet seinen öffentlichen Schlüssel:
  $$ B = 5^{15} \mod 23 = 30517578125 \mod 23 = 19 $$

- Alice berechnet den gemeinsamen Schlüssel:
  $$ S = 19^6 \mod 23 = 47045881 \mod 23 = 2 $$
- Bob berechnet den gemeinsamen Schlüssel:
  $$ S = 8^{15} \mod 23 = 35184372088832 \mod 23 = 2 $$

Beide haben denselben gemeinsamen Schlüssel $S = 2$.

## Man-in-the-Middle-Angriff

Ein Schwachpunkt des Diffie-Hellman-Verfahrens besteht darin, dass es anfällig für einen Man-in-the-Middle-Angriff ist, bei dem ein Angreifer in der Mitte die Kommunikation abfängt und zwei separate Schlüssel mit Alice und Bob aushandelt. Um dies zu verhindern, wird Diffie-Hellman häufig in Kombination mit digitalen Signaturen oder einem Public-Key-Infrastruktursystem (PKI) verwendet, um die Identität der Kommunikationspartner sicherzustellen.
