# Mehr zum Hintergrund des Projekts

## Das Passwortproblem

🔑 Passwortdiebstahl gehört zu den meist verbreiteten Gefahren online. [80% an Datenleaks sind auf gestohlene oder schlechte Passwörter zurückzuführen](https://www.cyclonis.com/report-reveals-data-breach-due-bad-password-habits/).

Die meisten Accounts werden aber immernoch mit Passwörtern gesichert. Passwörter haben ein Sicherheitsproblem: Sehr einfache Passwörter wie ‘Berlin2020’, ‘passwort’, ‘qwerty’ oder ‘12345678’ können sehr schnell dazu führen, dass die eigene digitale Identität gestohlen und missbraucht wird. Gute Passwörter haben ein Usability Problem: Es ist sehr unkomfortabel, für jeden Account ein anderes sicheres Passwort einzusetzen und Passwortmanager sind in Deutschland nur wenig akzeptiert.

## Zu viele Methoden, zu viele Passwörter

🤯 Wir haben immer mehr Accounts und Methoden, uns online zu verifizieren. Mit SMS-TAN Verfahren, Authentifizierung- und AusweisApps, Videoidentifikation und vielen Passwörtern über mehrere Geräten verteilt verlieren wir den Überblick. Nutzer:innen haben Probleme all ihre Passwörter zu verwalten und wünschen sich praktische, sichere Lösungen.

## Privatisierung der digitalen Identität

💳 Der online Ausweis (eID) wurde [von 94% der Deutschen noch nie genutzt](https://initiatived21.de/app/uploads/2019/10/egovernment-monitor-2019.pdf). Eine weit verbreite Lösung, die es ermöglicht, Login und online ausweisen zu kombinieren, gibt es bisher nicht. Im digitalen Raum nehmen vor allem private Unternehmen diese Aufgabe durch ihre Login-Services wahr. So weisen häufig Dritte die Identität der Nutzenden als sogenannte “Identity-Provider” nach, wie man es zum Beispiel vom “Login mit Google” kennt. Die Privatisierung der Identität birgt aber gesellschaftliche Risiken: Datenschutz und Sicherheit treten bei profitorientierten Modellen häufig in den Hintergrund. Gerade wegen der bevorstehenden Digitalisierung von 575 öffentlichen Leistungen bis 2022 ist es wichtig, die digitale Identität von Bürger:innen wahren zu können und nachhaltige, nutzerfreundliche und faire öffentliche Alternativen zu bieten. Eine einheitliche Lösung, die für den öffentlichen und den privaten Bereich in Deutschland für die Identifikation verbreitet eingesetzt wird, existiert bislang nicht.

## Der passwortlose Login
![Diagramm, das den Ablauf vom passwortlosen Login verdeutlich](/ressourcen/fido_process_klein.png)
Wenn Nutzer:innen einen Sicherheitsschlüssel zum Beispiel bei ihrem Mail-Account verwenden möchten, müssen sie diesen zunächst dort registrieren. Dabei werden zwei neue Schlüssel auf dem Sicherheitsschlüssel erzeugt: ein privater und ein öffentlicher Schlüssel. Der öffentliche Schlüssel wird für den Mail-Account beim Mail-Anbieter gespeichert, während der private Schlüssel den Sicherheitsschlüssel nie verlässt. Für jeden Dienst und jede Nutzer:in werden auf dem Sicherheitsschlüssel unterschiedliche Schlüsselpaare erzeugt.
Man kann sich das wie ein schwarzes Brett hinter einer Vitrine vorstellen, das jeder einsehen kann, der den öffentlichen Schlüssel hat. Die Vitrine kann jedoch nur mit dem privaten Schlüssel geöffnet werden. Um zu überprüfen, ob jemand den privaten Schlüssel besitzt kann man dieser Person also eine Information mitteilen (z. B. die Zahl “12”) und sie auffordern diese auf das schwarze Brett zu schreiben. Wenn dann “12” auf dem schwarzen Brett auftaucht, können wir bestätigen, dass die Person Zugang zum privaten Schlüssel hat.

## Was ist FIDO2?

Der offene Standard FIDO2 (Fast Identity Online) ermöglicht den passwortlosen Login. Mit einem Tippen auf einen Button am USB-Stick, einem Fingerabdruck oder Blick in die Kamera ist man eingeloggt. 

Er wird von der nicht-kommerziellen [FIDO Allianz](https://fidoalliance.org/members/) entwickelt, der bisher ca. 250 große Unternehmen (u.a. Google, Facebook, Amazon und viele mehr) und öffentliche Partner wie das deutsche Bundesamt für Sicherheit in der Informationstechnik (BSI) angehören. Da sich inzwischen auch Apple der Allianz angeschlossen hat, unterstützen alle wichtigen Browser (Chrome, Firefox, Edge, Opera, Safari) den Standard.

Durch diese breite Unterstützung und Verbreitung hat der FIDO2 Standard großen Potenzial, in Zukunft eine große Akzeptanz und breite Nutzer:innenbasis für den passwortlosen Login zu bekommen.

## **Was ist ein Sicherheitsschlüssel?**

Der FIDO Standard kann  **auf Laptops und Smartphones (interne Sicherheitsschlüssel)** und auf anderer Hardware wie **USB Sticks implementiert werden (externer Sicherheitsschlüssel).** 

Verwendet man interne Sicherheitsschlüssel, wird auch nur dieses Gerät registriert. Das kann den Login über unterschiedliche Geräte hinweg erschweren, wenn zum Beispiel das eigene Smartphone für das Mail-Konto registriert wurde, Nutzer:innen ihre Mails aber kurz auf dem Laptop eines Freundes checken möchten. Externe Sicherheitsschlüssel können dafür die Sicherheit erhöhen. Neben dem Laptop müsste ein Angreifer dann auch noch den USB-Stick stehlen.

![Roter schwarzer und blauer USB-Stick vor weißem Hintergrund](/ressourcen/drei_sticks.png)

USB-Sicherheitsschlüssel können außerdem Bluetooth oder NFC-Übertragungswege nutzen, um einen Stick auch über verschiedene Geräte hinweg einzusetzen. Dafür hält man den Stick entweder an die Rückseite des Smartphones oder drückt nur auf den Knopf, um die Übertragung zu starten.