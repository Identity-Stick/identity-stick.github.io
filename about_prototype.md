Mit dem Identity-Stick soll der passwortlose Login um eine Möglichkeit erweitert werden, sich auszuweisen. FIDO2 ermöglicht es momentan nur, sich bei Accounts einzuloggen (mehr über den Standard hier). Wenn Nutzer:innen sich bei einem Dienst ausweisen sollen, zum Beispiel bei der Eröffnung eines Bankkontos oder für eine öffentliche Verwaltungsleistung, ist das bisher nicht möglich.

Die FIDO Allianz strebt an, die Accounterstellung mit verifizierten Identitätsattributen Wirklichkeit werden zu lassen und Probleme wie die Wiederherstellung von Accounts oder den FIDO-Standard im Internet der Dinge stärker einzusetzen. Bisher wurde der Standard aber nicht dementsprechend erweitert.

## Wie funktioniert das Ausweisen mit dem Identity Stick?

Der FIDO-Standard kann für bestimmte Anwendungszwecke angepasst werden. Diese Möglichkeit wurde genutzt um ein eigenes Protokoll zu entwickeln, dass es ermöglicht Nachrichten mit Identitätsattributen von Nutzenden auszutauschen.

Die Idee für die Bestätigung der Informationen lässt sich mit einem versiegelten Empfehlungsschreiben vergleichen. In den Brief werden die Informationen geschrieben, die ein Bote mündlich übertragen soll. Anschließend wird der Brief versiegelt und vom Boten zum Empfänger gebracht. Der Empfänger, der das Siegel kennt, öffnet den Brief und vergleicht die Informationen mit denen des Boten.

So werden in unserem Protokoll die Attribute werden gemeinsam mit einem signierten Hash auf dem Sicherheitsschlüssel abgespeichert. Der für die Signatur benutzte öffentliche Schlüssel sollte von einer vertrauenswürdigen Instanz stammen und auf vertrauenswürdigem Weg veröffentlicht werden. Das ist wie das Siegel für den Brief. Ein Diensteanbieter kann nun die Erweiterung wie folgt benutzen:

Zuerst wird der Sicherheitsschlüssel angefragt, ob die Identity Stick Erweiterung unterstützt wird. Daraufhin übermittelt der Sicherheitsschlüssel welche Attribute hinterlegt sind (bspw. Name, Geburtsdatum und Adresse). Der Dienst kann die gewünschten Attribute einzeln abfragen.

Diensteanbieter berechnen nun erneute den Hash der Attribute. Mittels des öffentlichen Schlüssels wird der signierte Hash entschlüsselt und mit dem berechneten verglichen. Dadurch können Diensteanbietende die Bestätigung der Attribute überprüfen. Dazu wird der Hash der Daten erneut berechnet. Dies ist vergleichbar mit der Überprüfung der Aussage des Boten mit dem Inhalt im versiegelten Brief.

![Ein Prozessdiagramm, das vier Punkte zeigt: 1. Siginierung von Attributen; 2. Abfrage von Daten; 3. Abfrage von Sicherheitsschlüssel; 4. Berechnung Hash](/ressourcen/identity_stick_process_klein.png)

Für den Prototyp wurde auf dem Solo FIDO2 Stick "[Solo for Hackers](https://github.com/solokeys/solo)" aufgebaut, dessen Firm- und Hardware offen zur Verfügung stehen. Für die Umsetzung wurde eine Anpassung des Solo Codes vorgenommen, die das oben beschriebene Protokoll implementiert. Da der Solo nur begrenzten Speicher zur Verfügung hat, müssen zum Senden der Attribute mehrere Nachrichten ausgetauscht werden. 

Weitere Infos:

👩🏾‍💻 [Prototyp des Identity Sticks](https://github.com/identity-Stick/identity-stick)<br>
📜 [Definition der Erweiterung identity-stick](https://github.com/Identity-Stick/identity-stick-extension)<br>
🖥️ [Demo des User Interface](/demo)<br>

## <span id="next-steps"> Was könnte noch weiterentwickelt werden?</span>

Für ein vollumfängliches Produkt könnten weitere Entwicklungsschritte unternommen werden:

- **Personalisierung des Sticks und Signatur von Daten**
<br>Die Personalisierung des Sticks bzw. Signatur der Daten müsste in einem Produktionsumfeld von einer **vertrauenswürdigen Instanz** gesichert werden. Dafür käme eine staatliche Stelle wie bspw. die Bundesdruckerei in frage, die auch die technische Infrastruktur der eID betreut. Für eine einsatzfähige und sichere Version des Sticks müsste die Hardware von dieser Instanz hergestellt, die Maintenance gesichert und die entsprechenden individuellen Daten bei Erstausstellung für jede Bürger:in signiert werden. Es wäre nützlich, Bürger:innen mit entsprechenden Informationen und Materialien über die Funktionsweise aufzuklären.

- **Weiterentwicklung des Protokolls**
<br>In der momentanen Version des Identity Stick Prototyps werden die Daten signiert auf dem Stick abgelegt und dann an Diensteanbieter:innen weiter gesendet. Dies verhindert zum Einen keine Replay-Attacken. Zum Anderen könnten die bestätigten Daten von Diensteanbieter:innen an Dritte weitergegeben werden. Daher müssten weitere Verbesserungen des Protokolls erfolgen. So sollte ein authentifizierter sichererer Kanal zwischen Stick und Diensteanbieter:in aufgebaut werden über den Daten ausgetauscht werden könnten.

- **Erweiterter Hardwarespeicher und Features**
<br>Der Speicherplatz des Solo-Sticks ist limitiert, weshalb nur eine begrenzte Menge an Informationen darauf abgelegt werden kann. Mit der Produktion eigener Hardware könnte dieser Speicherplatz und damit die Funktionalität des Sticks erweitert werden. So könnte der Stick neben der sicheren (multi- und passwortlosen) Authentifizierung und Identifizierung auch einen sicheren Datenspeicher beinhalten, auf dem wichtige Dateien und Zertifikate abgelegt werden können, einen Passwortmanager beinhalten und vieles mehr.

- **Bekanntheitsgrad und Verbreitung von FIDO2**
<br>Der noch recht junge Standard wurde bisher von relativ wenigen Webseiten komplett implementiert. In Zukunft ist damit zu rechnen, dass mehr Diensteanbieter:innen die Standards umsetzen und sich somit auch das Potenzial für Anwender:innen erhöht. Nur 7% der deutschen Bürger:innen geben außerdem bei einer Befragung an, den Standard zu kennen (gefragt nach: “Token/Stick (FIDO2)”), obwohl sie Potenzial für dessen Nutzung sehen. Eine größere Adaption könnte also auch erreicht werden, wenn dessen Vorteile stärker an Bürger:innen herangetragen werden. Durch die breite Beteiligung an der FIDO-Allianz ist jedoch mit einer zukünftig stärkeren Verbreitung zu rechnen..

- **Verlust eines Identity Sticks**
<br>Die Problematik des Verlustes eines Sticks ist noch nicht vollständig gelöst. In bestehenden Ansätzen wird empfohlen, einen zweiten Sicherheitsschlüssel zu hinterlegen oder eine Liste an Backup Codes zu generieren, die für die Zurücksetzung des Accounts verwendet werden können. Es könnte in solch einem Fall aber auch auf die Identifizierung mittels eines Ausweisdokuments (z.B. der eID) zurückgegriffen werden. Einen ähnlichen Fall beschreibt das BSI in einer Technischen Richtlinie.

🚀 [Wie könnte es weitergehen?](/ausblick)