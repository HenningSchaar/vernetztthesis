

# Konzeption

Wie in der [Einleitung](#einleitung)  (\ref{einleitung}) erwähnt, stand am Anfang der Arbeit an der Installation, der Wunsch das Schienennetz als akustischen Raum darzustellen. Hieraus entstand die Idee, diese Vertonung anhand der Gefühle von Zugreisenden zu orientieren. Es wurde für die Entwicklung ein experimenteller Ansatz gewählt, da sich die Komposition an bereits gegebene Inputs, den Zugverkehr an dem gewählten Ort, anpassen muss.

## Experimente und deren Ergebnisse

### Ansätze mit Kontaktmikrofonen

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroAnSchiene}
\break file:///Users/henningschaar/Dropbox/Schule/NwT/Micro%20Controller/Eierwirbraucheneier.bs1 
\caption{Kontaktmikrofon an stillgelegtem Gleis}
\end{figure}

Zunächst bestand der Wunsch die Installation ähnlich wie [Bill Fontanas](#bill-fontana) (\ref{bill-fontana}, S. \pageref{bill-fontana}) Klangskulpturen zu gestalten. Es sollten portable Stationen entwickelt werden welc file:///Users/henningschaar/Dropbox/Schule/NwT/Micro%20Controller/Eierwirbraucheneier.bs1 he mit einem Kontaktmikrofon das Akustische Signal der Schiene über LTE das Audiosignal an einen Ausstellungsraum per Livestream übertragen sollten. Dafür wurde folgende Hardware geplant:

| Kategorie       | Produkt                           | Preis (ca.) |
| --------------- | --------------------------------- | ----------- |
| Internet        | Aircard Sierra 320U 4G            | 23€         |
| Computer        | Rasberry Pi Zero                  | 15€         |
| Audio I2S       | MikroElektronika MIKROE-506       | 18€         |
| Mikrofon        | Schaller Oyster                   | 36€         |
| Stromversorgung | Hiluckey Solar Powerbank 25000mAh | 36€         |
|                 |                                   |             |
| Gesamt          |                                   | 142€        |

Der ausgewählte Ausstellungsraum oder *Zuhörpunkt* war das Straßenbahnmuseum Stuttgart im Straßenbahndepot in Bad-Canstatt. [@schumacher_museum_2018] Je nach Budget würden Stationen angefertigt und pro Station ein Lautsprecher in der großen Halle des Museums angebracht. 

Die Stationen würden an Punkten im Baden-Württembergischen Schienennetz angebracht um den Lokalbezug zur Landeshauptstadt herzustellen. Im Ausstellungsraum wäre das stetige Vibrieren der Gleise zu hören, welches mutmaßlich durch Wind und Erschütterungen im Boden entsteht, bis ein Zug an einem der Punkte vorbeiführe. Züge auf anderen Gleisen würden die Schiene an der das Kontaktmikrofon befestigt ist dennoch in Schwingung versetzen und am *Zuhörpunkt* zu hören sein. Fährt ein Zug über das Gleis, an dem das Kontaktmikrofon befestigt ist, entsteht ein sehr direktes klangliches Bild des Zuges. Zunächst ein Anschwellen eines Resonanztones der Schiene, bis schließlich das Schleifen der Räder und das Rumpeln verursacht durch das Gewicht des Zuges zu hören sind.

Diese Geräuschkulisse, würde sich mit den Reflexionen im Straßenbahndepot und den Geräuschen welche dort stattfinden mischen und so einerseits den Raum des Schienennetzes von Baden-Württemberg in einen für Menschen erfassbaren Raum bringen. Dies kann als räumliche Verdichtung angesehen werden, da der Ausstellungsraum deutlich kleiner als der Raum der abgenommenen *Abhörpunkte* ist. Andererseits würde das Innere der Schiene vergrößert, indem dem akustischen Signal welches in dieser entsteht erlaubt wird, einen Raum zu füllen.

Diese Verzerrung von Räumlichkeit, sowohl vom Großen ins kleine, als auch von dem inneren ins äußere, stellte die Essenz der Idee welche hinter diesem ersten Konzept steckte dar.

Inspiriert von Bill Fontanas Arbeit, insbesondere *Harmonic Bridge*, bei der die Geräusche einer Fußgängerbrücke in die *Tate Gallery of Modern Art* übertragen wurden, wurde die Möglichkeit der Nutzung von Beschleunigungssensoren in Erwägung gezogen. Für die Wahl des Kontaktmikrofons wurden dann Experimente mit Metallischen Körpern durchgeführt. 

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroVergleich}
\break
\caption{Piezoelektrisches Mikrofon (links) und Beschleunigungssensor an Teensy (rechts)}
\end{figure}

Sogenannte *MEMS* (microelectromechanical systems) Beschleunigungssensoren können als Kontaktmikrofon verwendet werden. Klassische Mikrofone messen den Schalldruck. Der Schalldruck der von einem vibrierenden Körper verursacht wird ist proportional zu der Beschleunigung weswegen sich ein Beschleunigungssensor zur Abnahme einer akustischen Quelle eignet. [@oreilly_sonic_2009 S. 1f] 

Nachdem jedoch klar wurde, dass das Anbringen von technischen Geräten an das Gleis unter §315 StGB: "Gefährliche Eingriffe in den Bahn-, Schiffs- und Luftverkehr" strafbar sein könnte, wurden alternativen gesucht.

### Ansätze mit Webscraping

Zugfinder.de ist eine deutsche Zug-Positionsanzeige, welche Statistiken über die meisten Züge in Deutschland bereithält. Für den Fernverkehr gibt es eine Deutschlandkarte, welche alle Fernverkehrszüge in einer animierten Netzkarte zeigt. Für alle weiteren Züge gibt es animierte Ansichten der einzelnen Streckenabschnitte. Die Daten dieser Seite sollten nach dem das erste Konzept gescheitert war die neue Grundlage für die Installation bilden. Hierfür müssen die Daten aus der Website in einem Benutzbaren Format vorliegen. [@schubert_zugfinder_nodate]

Nachdem Johannes Schubert, der Entwickler von Zugfinder.de mitteilte, dass keine API Schnittstellen vorhanden sind, fiel die Entscheidung die Daten mittels Webscraping zu extrahieren. Webscraping oder Screenscraping emuliert die Benutzung einer Website durch ein automatisiertes Programm, mit dem Ziel Daten aus dieser Website zu extrahieren. [@ball_screen-scraping_2003] 

Zunächst wurde ein Prototyp entwickelt, der die Daten einer einzelnen Strecke als Input nutzte. Hierfür wurde eine *Node.js* Anwendung entwickelt. *Node.js* ist eine Javascript Runtime, welche die V8 Javascript engine von Google Chrome nutzt.  [@openjs_foundation_about_nodate] Es ist also eine Umgebung um Javascript auszuführen, ähnlich wie ein Webbrowser Javascript ausführen würde. *Node.js* hat jedoch den Vorteil nicht den overhead eines Browsers zu haben und mit vielen zusätzlichen Funktionen ausgestattet zu sein, welche in klassischen Browserumgebungen nicht verfügbar sind.

Dieser Prototyp sollte das ursprüngliche Konzept mit fixen punkten im Schienennetz welche als Abhörpunkte fungieren auf andere Weise erreichen. So sollte ein bestimmter Punkt auf einer Strecke abgefragt werden, und wenn sich dort ein Zug aufhält sollten Informationen über diesen per UDP (\ref{webscraping-kommunikation} [*Kommunikation*](#webscraping-kommunikation) S. \pageref{webscraping-kommunikation}) an das Klangsynthese Programm in Max (siehe \ref{max} [*Max*](#max) S. \pageref{max}) übertragen werden. Es werden außer der Information, dass sich an dem Punkt ein Zug aufhält allerdings noch weitere Informationen über den Zug mitgesendet, da bei einer Synthetischen Klangerzeugung der direkte Klangliche Bezug zu dem spezifischen Zug fehlt. Bei einer Umsetzung mit Kontaktmikrofonen, würden Zugtyp, Umgebungsgeräusche, Gleisbett und Zustand der Schiene sowie Besonderheiten des Streckenabschnitts (Kurven, Weichen) Faktoren sein, welche den Klang verändern. Um einen Bezug zu dem Zug und dem Abgehörten Punkt herzustellen, werden Daten genutzt und generiert welche vom Kontext abhängig sind. 

 Als Proof-of-concept wurde eine Node.js anwendung entwickelt, welche ein Http-request an die ausgewählte Strecke auf *Zugfinder.de* schickte und die Antwort in von Javascript benutzbares JSON (*Javascript Object Notation*) und schließlich in ein Array der aktuell auf der Strecke fahrenden Züge umwandelt. Aus diesem Array werden API-Requests für die Google Distance Matrix API, eine API welche aus mehreren Start und Endpunkten eine Matrix von Distanzen herstellt [@google_get_nodate], generiert, um die Distanzen zwischen Abhörpunkt, Start- und Endbahnhof zu ermitteln. Daraus wird dann eine Angabe in Prozent erstellt, wie viel der Gesamtstrecke der Zug bereits zurückgelegt hat. In diesem Prototypen wurde diese Angabe dann genutzt um einen Bestimmten Abschnitt eines Audiofiles abzuspielen.

Dieses Konzept offenbarte nach dem testen des Prototyps einige Schwächen. Zunächst wurde klar, dass viele Abhörpunkte von Nöten wären, da es anders als bei dem ersten Konzept, zwischen den Zugevents keinerlei Klang gibt und die Ereignisdichte somit sehr gering wäre. Zudem wäre dieser Aufbau nicht leicht mit Zügen in Verbindung zu bringen, und eine Installation, welche sich zumindest Teilweise selbst erklären kann war gewünscht.

### Ansätze zur Visualisierung

Um die Installation selbsterklärender zu gestalten, wurden Visualisierungen entwickelt. Zunächst sollten die Lautsprecher mit Plaketten ausgestattet werden, welche angibt zwischen welchen beiden Haltestellen der zugehörige Abhörpunkt liegt. Zudem sollten Lichter an den Lautsprechern angebracht werden welche je nach Zugtyp, bei einem vorbeifahrenden Zug leuchten. So sollte der Blick des Besuchers auf die Lautsprecher gerichtet werden, sodass dieser die Plakette liest. Außerdem sollte es die Events noch eindeutiger machen. Doch beim Testen dieses Ansatzes wurde klar, dass auch diese Visuellen Hilfen nicht die grundlegenden Probleme mit diesem Prototypen lösen würde. 

Es wurde deswegen entschieden eine Karte der Züge anzufertigen, welche sich in Echtzeit aktualisiert. Auf dieser sollten die Abhörpunkte dann eindeutig markiert werden. Im laufe der Entwicklung dieser Karte wurden Debugging features entwickelt, um mithilfe des Cursors Information über einzelne Züge auszulesen. Während des Debuggings, entstand die Idee, die Cursor Interaktion als Interaktionsmöglichkeit für den Besucher bereitzustellen. Schließlich wurden die Abhörpunkte als Konzept aus der Installation vollständig entfernt, und die Installation wurde Interaktiv. Es gibt jetzt nur noch einen Abhörpunkt, und dieser wird von einem Besucher selbst gesteuert. 

Genaueres zur finalen Implementierung dieses Interaktionsprinzips findes sich in Kaptiel \ref{umsetzung} [*Umsetzung*](#umsetzung) S. \pageref{umsetzung}.

## Finales Konzept

Im folgenden wird das Konzept vorgestellt, welches das Ergebnis der Experimente und Entwicklungen seit der ursprünglichen Idee bis zum Zeitpunkt dieser Arbeit ist.

### Motivation

#### Persönliche Beweggründe

Henning Schaar lebte in seiner Schulzeit 4 Jahre lang in einer Fernbeziehung nach Mannheim, von Karlsruhe eine Entfernung von ca. einer Zugstunde. Diese wurde dann schließlich durch eine gemeinsame Wohnung in Mannheim aufgelöst. Nicht viel später Jedoch begann das Studium in Dieburg, welches wieder über eine Zugstunde entfernt war. Nach Ende der Beziehung gab es einen Wohnortwechsel nach Darmstadt, so dass das Studium nun näher war, doch gibt es weiterhin Freundschaften in Hamburg, einen Arbeitgeber in Stuttgart und eine Band und Familie in Karlsruhe, weswegen Zugfahren weiterhin zum Alltag gehören.

Diese räumlich verteilte Lebensweise verändert nicht nur das Reiseverhalten, auch die Selbstwahrnehmung wird durch sie beeinflusst. In jedem dieser Orte gibt es andere soziale Kreise, welche sich nicht oder kaum überschneiden und das Selbstbild einer Person wird durch sozial geteilte Merkmale und Gruppenmitgliedschaften maßgeblich beeinflusst. [@rempe_zur_2012 S. 31f] So wird die Zugfahrt zu einem Prozess welcher in diesem Fall nicht nur den Aufenthaltsort einer Person ändert, sondern schließlich auch die Wahrnehmung der eigenen Person.

Aus diesem Gefühl des Reisens entstand ein Interesse an den Gefühlen die Personen beim Nutzen von öffentlichen Verkehrsmitteln haben um diese in einer Installation darzustellen.

#### Befragungen

Um über den eigenen Erfahrungshorizont hinauszugehen, wurden formlose Befragungen von Kommilitonen, Freunden und Familie durchgeführt. Es wurde nach Gründen und Häufigkeit gefragt, sowie welcher emotionaler Bezug zu Abfahrts- und Ankunftsort besteht, und wie sich diese im Laufe der Reise wandeln. [@schaar_gedachtnisprotokoll_2019]

Die befragten in drei Kategorien unterteilt:

- **20-45 Minuten, mehrmals die Woche:** Die Person nimmt das Fahrzeug größtenteils in seiner Funktion die Hürde der Distanz zu verringern wahr. Der Innenraum des Zuges wird als Teil des öffentlichen Raumes empfunden. Es ist kein Ort an dem man sich tatsächlich aufhält, sondern vielmehr eine Art Wartezimmer. Die Reise wird als Zeitlich homogen wahrgenommen.
- **1-2 Stunden, einmal die Woche:** Das Fahrzeug wird ähnlich wie ein Gebäude wahrgenommen in welchem man sich temporär einrichtet. Arbeit oder Unterhaltung der man auch zu Hause nachgehen würde wird mitgebracht. Personen die in diese Kategorie fallen berichteten von *FOMO* (fear of missing out), also ein Gefühl ein wichtiges oder erfüllendes Ereignis zu verpassen welches an dem Ort, an dem sie sich gerade nicht aufhalten erlebt werden könnte. [@bosker_fear_2012]

#### Inspiration aus kunsthistorischer Recherche

### Inhaltliche Beschreibung

#### Reisegeschichten und Dramaturgie

#### Personae und deren Geschichte

#### Zwischenzustände

#### Bedeutung von Raum

### Raumkonzept/Aufbau

#### Nutzung von Lautsprechern

#### Nutzung von Graphik

#### Raum als Medium für Schall

