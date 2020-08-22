# Konzeption
Wie sind wir zum Identity Stick gekommen? Welche Konzeptideen sind aufgekommen und was haben wir herausgefunden? Hier tragen wir kurz ein paar der Erkenntnisse zusammen, die wir über die Projektlaufzeit gewonnen haben.

## Wo sind wir gestartet?

Zum einloggen und ausweisen im Internet werden unterschiedlichste Methoden genutzt. Von Passwörtern, SMS-TAN Codes, Ausweis- und Authentifikationsapps über Videodentifikationsverfahren wird es unübersichtlich.

Wir sind damit gestartet, das digitale Einloggen und Ausweisen zu verbinden.

## Was hat das jetzt mit FIDO zu tun?

Der offene Standard FIDO2 (Fast Identity Online) ermöglicht den passwortlosen Login. Mit einem Tippen auf einen Button am USB-Stick, einem Fingerabdruck oder Blick in die Kamera ist man eingeloggt. 

Damit erhöht er Sicherheit und Usability für den Login von Nutzer:innen und könnte durch eine weitere Verbreitung bald eine einheitliche Lösung für den Login werden. Nutzer:innen müssen sich online viel seltener ausweisen als einloggen. Daher wäre es sinnvoll, wenn ausweisen gleich funktioniert wie einloggen.

## Drei Konzeptideen

Wie lässt sich der Login mittels FIDO und das online Ausweisen verknüpfen? Wir haben drei Konzeptrichtungen erstellt. 

- 🏢 1. FIDO-Provider

    Identitätsprovider stellen eine Schnittstelle zwischen Nutzer:innen und Diensten dar. Wenn der Dienst den Identitätsprovidern traut, können diese etwas über die Identität von Nutzer:innen aussagen (z. B. deren Alter). Ganz genau wie bspw. eine Freundin und jemand Fremden vorstellt. 
    Dazu müssen sich Nutzer:innen aber bei Identitätsprovidern einloggen. Dies geschieht bisher über Passwörter und teilweise zusätzliche zweite Faktoren wie mobile TANs. Dies könnte aber durch den passwortlosen Login mittels FIDO ersetzt werden. Nutzer:innen würden sich somit über Identitätsprovider ausweisen, nutzen dafür aber genau das gleiche Mittel wie bei einem Login, nämlich ihren FIDO-Sicherheitsschlüssel.
    Der Vorschlag wird auch vom Bundesamt für Sicherheit in der Informationstechnik [erwähnt](https://www.bsi.bund.de/DE/Publikationen/TechnischeRichtlinien/tr03159/tr03159_node.html). 

- 💳 2. FIDO mit Ausweis

    Mit dem deutschen Personalausweis können sich Nutzer:innen auch elektronisch ausweisen. Die Idee hinter diesem Konzept war es den Ausweis als Sicherheitsschlüssel für einen passwortlosen Login mittels FIDO2 zu nutzen.
    Den Ausweis mittels dem FIDO1 Standard (U2F-Protokoll) als 2. Faktor bei Webseiten zu hinterlegen ermöglicht bereits [Fidelio](https://play.google.com/store/apps/details?id=de.persoapp.android.FIDELIO&hl=de). Mehr dazu wird in [diesem Video](https://youtu.be/Oc32AwPL2Nw) genauer erläutert.

    Die Überlegung wäre gewesen darauf aufbauend eine Art 2.0 Variante zu entwickeln, bei der der Ausweis direkt über die AusweisApp2 genutzt und der neue FIDO2 Standard eingesetzt werden könnte. 

- 🔑 3. FIDO-Ident

    Entgegengesetzt zur Nutzung eines Personalausweises zum Login ist die Idee von FIDO-Ident, einen FIDO2-Sicherheitsschlüssel ebenfalls zum Ausweisen einzusetzen. 
    Dazu soll FIDO2 als Protokoll zur Übermittlung von Identitätsattributen genutzt werden, die sich auf dem Sicherheitsschlüssel befinden.

## Erste Nutzertests

In ersten Nutzertests mit Papierprototypen wurden vor allen Dingen die Konzepte Fido mit Ausweis und FidoIdent getestet. 

**Folgende Fragen waren zentral:**

- **Login-Mittel**: Verwenden Nutzer:innen den Ausweis oder ein anderes Mittel (z.B. USB-Stick) lieber?
- **Abgrenzung von Services**: Unterscheiden sich die Wahrnehmung des Login-Mittels je nach Service?
- **Prozess und Verständnis**: Was sind grundsätzliche Fragen, die sich Nutzer:innen während der Prozesse stellen?

**Testszenarien**

Diese Szenarien wurden mit einer Gruppe aus fünf Personen in persönlichen Interviews an einem Smartphone getestet:

- Anmelden bei einem öffentlichen Nutzerkonto mit der eID Funktion über (1) die AusweisApp oder (2) mit einem USB-Sicherheitsschlüssel mit NFC-Funktion
- Anmelden bei einem privaten Dienst (in unserem Beispiel ein YouTube Konto) über (1) die AusweisApp (ähnlich der FIDELIO Funktion) oder über (2) einen USB-Sicherheitsschlüssel mit NFC Funktion

**Ergebnisse** 

- Die Nutzung der NFC Funktion mit einem Stick oder einer Ausweiskarte am Smartphone war Tester:innen vorher nicht bekannt und führte vorerst zu Verwirrung. Nachzubilden, wie Nutzende die Hardware ans Telefon halten sollten, half, die Funktion zu verstehen.
- ‘Sicherheitsschlüssel’ als Begriff und was damit gemeint ist, war Tester:innen unklar
- Dass die Ausweiskarte selbst ein ‘Sicherheitsschlüssel’ sein kann, war für die Tester:innen neu und unklar; ein Tester sagte: “Das ist kein Sicherheitsschlüssel, das ist ein Personalausweis”.
- Tester:innen hatten Hemmungen, die Ausweiskarte in der Simulation als Login Mittel für private Services (in diesem Beispiel YouTube) zu nutzen. Es entstand der Eindruck, dass die Daten des Personalausweises ausgelesen werden könnten, wenn man diesen zum Login benutzt. Eine Testerin sagte zum Beispiel: “Das würde ich nicht machen. Ich will nicht mehr Daten preisgeben, als ich muss”.
- Tester:innen fragten sich, welche Daten auf dem USB-Schlüssel liegen, wie diese Daten dorthin gelangen und was sie im Fall des Verlustes des Sticks machen sollen
- Nach den unterschiedlichen Durchgängen der verschiedenen Varianten wurde ein Mehrwert der Identifikation mit dem USB-Stick empfunden, da im Papierprototyp keine Installation von weiteren Anwendungen nötig war (keine Apps wie für den Fall der AusweisApp)
- Testerin empfand es als Mehrwert, wenn Stick für unterschiedliche Szenarien einsetzbar wäre

### Schlussfolgerungen

- **Informationsbedürfnis**: Nutzer:innen müssen darüber informiert werden, was ein ‘Sicherheitsschlüssel’ ist und wie dieser eingesetzt werden kann. Im Interface könnte das Wort ‘Sicherheitsschlüssel’ durch Alternativen ersetzt werden (z.B. ‘Passwortlos anmelden’, ‘Mit USB-Stick anmelden’, ‘Sicherheitsstick verwenden’)
- Vielseitige **Einsatzmöglichkeiten** könnten für die Nutzung eines Identity Sticks von Vorteil sein (—> Ausblick)
- **Ausweiskarte** ist nur bedingt als Login-Mittel geeignet. Hier müsste die Wahrnehmung noch stärker je nach Service getestet werden.
- Dass die eID auch **pseudonym** genutzt werden kann, war Tester:innen unbekannt.
- Das Wort **'Sicherheitsschlüssel'** in Bezug auf den Ausweis führt zu Verwirrung.

## Auswahl von FIDOIdent

Unsere Umsetzung orientiert sich am FIDOIdent Konzept. Hier listen wir einige Gründe, warum wir so vorgegangen sind:

- 'FIDO mit Ausweis' wurde unabhängig von uns während der Projektlaufzeit teilweise umgesetzt (hier sind [Browser-Erweiterungen](https://addons.mozilla.org/de/firefox/addon/webauthn-eid-for-firefox/) dazu). Die Nutzertests haben gezeigt, dass User:innen bedenken hatten, den Ausweis als Login Mittel einzusetzen. Es gibt außerdem ein paar Usability Probleme (unklar, wann Nutzende Daten pseudonym übertragen; unklar, dass der 'Ausweis' als "Sicherheitsschlüssel" verwendet werden kann; Download von Plugin und AusweisApps notwendig).
- Da bei 'FIDOProvider' nur die Art des Logins beim Identitätsprovider angepasst wird, ist das Potenzial durch eine Entwicklung einer solchen Lösung geringer. Weiterhin muss dem Identitätsprovider vertraut werden. Wenn dies eine private Organisation ist, so wird die Verantwortung für digitale Identitäten weiter auf den privaten Markt verschoben. Außerdem bietet eine einzelne Stelle wie sie der Identitätsprovider darstellt, Gefahren für den Datenschutz.