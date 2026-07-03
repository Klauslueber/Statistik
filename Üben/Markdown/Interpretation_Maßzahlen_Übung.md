# Übung: Interpretation von Streu-, Konzentrations- und Zusammenhangsmaßen

> Fünf Aufgaben zur Interpretation gegebener Kennzahlen. Kein Rechnen — es geht darum, Werte im sachlichen Kontext sinnvoll zu deuten und typische Klausurfallen zu vermeiden.

---

## Aufgabe 1 — Standardabweichung

In zwei Bundesländern wird die Schulzufriedenheit auf einer Skala von 0–100 gemessen.

- Land A: $\bar{x} = 65$, $s = 4$
- Land B: $\bar{x} = 65$, $s = 18$

**a)** Was sagen die Standardabweichungen über die Verteilung in jedem Land aus?

**b)** Was lässt sich über die gesellschaftliche Homogenität schließen? Warum reicht allein der Mittelwert nicht aus?

**c)** Welche inhaltliche Aussage wäre falsch: „Land B ist unzufriedener als Land A"?

---

## Aufgabe 2 — Herfindahl-Streuungsmaß

Zwei Parteiensysteme werden verglichen:

- System X: $HF = 0{,}82$
- System Y: $HF = 0{,}38$

**a)** Interpretiere beide Werte. Welches System ist fragmentierter, welches konzentrierter?

**b)** Was bedeutet das für den politischen Wettbewerb in jedem System?

**c)** Welchen Wert hätte $HF$ bei einer vollkommen gleichmäßigen Verteilung auf vier Parteien? Und welchen bei einer Partei mit 100 %?

---

## Aufgabe 3 — Gini-Koeffizient

Drei Länder im Vergleich (Einkommensverteilung):

- Land 1: $G = 0{,}05$
- Land 2: $G = 0{,}31$
- Land 3: $G = 0{,}62$

**a)** Interpretiere alle drei Werte auf der Skala von 0 bis 1.

**b)** Zwischen welchen zwei Ländern ist der Unterschied inhaltlich am bedeutsamsten — und warum?

**c)** Was würde $G = 0$ und $G = 1$ jeweils bedeuten?

---

## Aufgabe 4 — $\varphi$, Cramér's V und Odds Ratio

Aus einer Studie zu Bildung $\times$ Demokratiezufriedenheit ($n = 1{.}200$, 2×2-Tabelle) liegen vor:

- $\chi^2 = 54{,}0$
- $\varphi = 0{,}21$
- $OR = 3{,}4$ (Gruppe 1: Kein Abitur, Gruppe 2: Abitur; Ereignis: „zufrieden mit der Demokratie")

**a)** Interpretiere $\chi^2 = 54{,}0$. Warum ist dieser Wert allein schwer zu interpretieren?

**b)** Interpretiere $\varphi = 0{,}21$. Wie stark ist der Zusammenhang?

**c)** Interpretiere $OR = 3{,}4$ konkret im Sachzusammenhang.

**d)** Welche Schlussfolgerung ist aus diesen Maßen **nicht** erlaubt?

---

## Aufgabe 5 — Pearson $r$ und Spearman $\rho$

Für den Zusammenhang zwischen BIP pro Kopf ($x$) und Demokratieindex ($y$) in 40 Ländern:

- Pearson $r = 0{,}71$
- Spearman $\varrho = 0{,}83$

**a)** Interpretiere $r = 0{,}71$ inhaltlich. Was bedeutet $r^2$ in diesem Zusammenhang?

**b)** Interpretiere $\varrho = 0{,}83$. Worin unterscheidet sich die Aussage von $r$?

**c)** Warum könnte $\varrho > r$ sein? Was deutet das über die Art des Zusammenhangs an?

---

# Lösungen

## Lösung Aufgabe 1

**a) Standardabweichungen im Vergleich:**

Beide Länder haben denselben Mittelwert $\bar{x} = 65$.

- **Land A ($s = 4$):** Die Werte streuen sehr wenig um den Mittelwert. Die meisten Befragten liegen nahe bei 65 — die Bevölkerung ist in ihrer Schulzufriedenheit **homogen**.
- **Land B ($s = 18$):** Sehr hohe Streuung — es gibt viele sehr zufriedene und viele sehr unzufriedene Befragte. Der Mittelwert verdeckt tiefe **gesellschaftliche Spaltung**.

**b) Homogenität:**

Der Mittelwert allein reicht nicht aus: Zwei Gesellschaften mit $\bar{x} = 65$ können fundamental verschieden sein. Land A hat kaum Meinungsverschiedenheiten; in Land B prallen gegensätzliche Gruppen aufeinander. Für sozialpolitische Diagnosen ist $s$ mindestens so wichtig wie $\bar{x}$.

**c) Falsche Aussage:**

„Land B ist unzufriedener als Land A" ist **falsch** — beide Länder haben denselben Mittelwert. Richtig wäre: „In Land B ist die Zufriedenheit ungleich verteilt."

> **Klausurfalle:** $s$ sagt nichts über das Niveau, nur über die Streuung. Niemals höheres $s$ mit niedrigerer Zufriedenheit gleichsetzen.

---

## Lösung Aufgabe 2

**a) Herfindahl-Streuungsmaß:**

$HF = 1 - \sum f_j^2$ liegt zwischen $0$ (alle Beobachtungen in einer Kategorie — keine Streuung) und $1 - 1/k$ (Gleichverteilung — maximale Streuung).

- **System X ($HF = 0{,}82$):** Hoher Wert — die Stimmen verteilen sich gleichmäßig auf viele Parteien. Stark **fragmentiertes Vielparteiensystem**, typisch für Verhältniswahlrecht mit niedrigen Hürden.
- **System Y ($HF = 0{,}38$):** Niedriger Wert — wenige Parteien dominieren, die Verteilung ist wenig gestreut. **Konzentriertes System**, Richtung Zweiparteiensystem.

**b) Politischer Wettbewerb:**

In System X verteilt sich Macht auf viele Akteure — Koalitionen sind nötig, Mehrheitsbildung schwierig. In System Y sind klare Mehrheiten leichter erreichbar, aber die politische Auswahl für Wählerinnen und Wähler ist geringer.

**c) Grenzwerte:**

Gleichmäßige Verteilung auf vier Parteien (je 25 %):
$$HF_{\max} = 1 - 4 \cdot \left(\frac{1}{4}\right)^2 = 1 - 4 \cdot 0{,}0625 = 1 - 0{,}25 = 0{,}75$$

Eine Partei mit 100 % (alle anderen 0 %):
$$HF_{\min} = 1 - 1{,}0^2 = 1 - 1 = 0$$

> **Klausurfalle:** Die Richtung ist bei $HF$ umgekehrt zu dem, was man intuitiv erwartet: **hohes $HF$ = hohe Streuung** (viele Parteien), **niedriges $HF$ = hohe Konzentration** (eine Partei dominiert). $HF = 0$ bedeutet vollständige Konzentration — nicht Gleichverteilung. Das ist der häufigste Interpretationsfehler.

---

## Lösung Aufgabe 3

**a) Drei Länder auf der Gini-Skala:**

- **Land 1 ($G = 0{,}05$):** Nahezu perfekte Gleichverteilung — alle Haushalte haben fast gleich viel. In der Realität extrem selten; nur in sehr egalitären Gesellschaften denkbar.
- **Land 2 ($G = 0{,}31$):** Moderate Ungleichheit — typisch für westeuropäische Wohlfahrtsstaaten. Deutschland liegt bei $G \approx 0{,}29$–$0{,}32$.
- **Land 3 ($G = 0{,}62$):** Sehr hohe Ungleichheit — ein kleiner Teil der Bevölkerung hält den Großteil des Einkommens. Typisch für Länder wie Südafrika oder Brasilien.

**b) Bedeutsamster Unterschied:**

Der Sprung von Land 2 zu Land 3 ($+0{,}31$) ist inhaltlich gravierender als von Land 1 zu Land 2 ($+0{,}26$). Ab $G > 0{,}5$ sind gesellschaftliche Konsequenzen — Armut, soziale Mobilität, politische Instabilität — deutlich spürbar.

**c) Grenzwerte:**

- $G = 0$: Alle Haushalte haben dasselbe Einkommen (perfekte Gleichheit). Die Lorenzkurve fällt mit der Winkelhalbierenden zusammen.
- $G = 1$: Ein einziger Haushalt besitzt alles (maximale Ungleichheit). Nur theoretisch möglich.

> **Klausurfalle:** $G$ misst Ungleichheit, nicht das Wohlstandsniveau. Ein armes Land kann $G = 0{,}20$ haben (alle arm), ein reiches Land $G = 0{,}60$ (Einkommen extrem ungleich verteilt).

---

## Lösung Aufgabe 4

**a) $\chi^2 = 54{,}0$:**

Der Wert zeigt, dass die beobachteten Häufigkeiten stark von den erwarteten (bei Unabhängigkeit) abweichen. Er ist **nicht direkt interpretierbar**, weil er von $n$ und der Tabellenstruktur abhängt: Dieselbe inhaltliche Beziehung erzeugt bei $n = 5{.}000$ einen viel größeren $\chi^2$-Wert als bei $n = 100$. $\chi^2$ dient primär dem Signifikanztest, nicht der Stärkemessung.

**b) $\varphi = 0{,}21$:**

$\varphi$ liegt zwischen 0 (Unabhängigkeit) und 1 (perfekter Zusammenhang). Hier: **schwacher bis moderater Zusammenhang** zwischen Bildung und Demokratiezufriedenheit — statistisch klar vorhanden, aber nicht stark. Bildung erklärt nur einen Teil der Variation in der Zufriedenheit.

**c) $OR = 3{,}4$:**

Personen **ohne Abitur** haben eine **3,4-mal so hohe Chance**, mit der Demokratie unzufrieden zu sein, verglichen mit Abiturientinnen und Abiturienten. Konkret: Wenn auf je 10 Zufriedene unter Abi-Trägern 3 Unzufriedene kommen, kommen auf 10 Zufriedene ohne Abitur etwa 10,2 Unzufriedene.

**d) Nicht erlaubte Schlussfolgerung:**

„Geringere Bildung **verursacht** Demokratieunzufriedenheit." Das ist eine **Kausalaussage** — aus Kreuztabellen-Maßen nicht ableitbar. Bildung korreliert mit Einkommen, sozialem Status, Mediennutzung und weiteren Faktoren. Der beobachtete Zusammenhang könnte vollständig durch eine Drittvariable erklärt werden.

> **Klausurfalle:** $\chi^2$, $\varphi$, $V$ und $OR$ sind **Zusammenhangsmaße**, keine Kausalmaße. Nie von Zusammenhang auf Ursache schließen.

---

## Lösung Aufgabe 5

**a) Pearson $r = 0{,}71$:**

Starker **positiver linearer** Zusammenhang: Länder mit höherem BIP pro Kopf tendieren zu höheren Werten im Demokratieindex. Das Bestimmtheitsmaß $r^2 = 0{,}71^2 = 0{,}50$ bedeutet: **50 % der Varianz** im Demokratieindex werden durch das BIP pro Kopf statistisch erklärt. 50 % gehen auf andere Faktoren zurück (Geschichte, Institutionen, Bildung etc.).

**b) Spearman $\varrho = 0{,}83$:**

Ebenfalls sehr starker Zusammenhang — auf Rangbasis sogar noch klarer. $\varrho$ misst, ob Länder mit **höherem BIP-Rang** auch einen **höheren Demokratie-Rang** haben. Die Aussage ist etwas schwächer: kein Linearitätsanspruch, nur **Monotonie** (je mehr BIP, desto mehr Demokratie — aber nicht unbedingt proportional).

**c) Warum $\varrho > r$?**

Zwei mögliche Erklärungen:

1. **Ausreißer:** Einzelne Länder mit extrem hohem BIP (z.B. Erdöl-Monarchien) aber niedrigem Demokratieindex verzerren $r$ nach unten. Spearman weist solchen Ländern einfach einen Rang zu — der extreme Abstandswert schadet nicht.
2. **Nicht-linearer Zusammenhang:** Der Zusammenhang ist **monoton aber nicht linear** — z.B. logarithmisch. Bei geringen BIP-Niveaus steigt der Demokratieindex steil, bei hohem BIP flacht der Zuwachs ab. Spearman erfasst das besser als Pearson.

Fazit: Wenn $\varrho > r$, lohnt sich ein Blick auf Streudiagramm und Ausreißer — Pearson unterschätzt den Zusammenhang möglicherweise.

> **Klausurfalle:** $r = 0{,}71$ ist kein Prozentsatz! „71 % der Länder folgen dem Muster" ist falsch. Erst $r^2 = 0{,}50$ gibt den Varianzanteil an.
