

# Konzeption

Wie in der [Einleitung](#einleitung)  (\ref{einleitung} S. \pageref{einleitung}) erwähnt, stand am Anfang der Arbeit an der Installation, der Wunsch das Schienennetz als akustischen Raum darzustellen. Hieraus entstand die Idee, diese Vertonung anhand der Gefühle von Zugreisenden zu orientieren. Da sich die Installation an bereits existierende Inputs, den Zugverkehr des gewählten Ortes, anpassen muss, wurde ein experimenteller Ansatz zur Entwicklung der Arbeit gewählt.

## Experimente und deren Ergebnisse

### Ansätze mit Kontaktmikrofonen

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroAnSchiene}
\break
\caption{Kontaktmikrofon an stillgelegtem Gleis}
\end{figure}

Zunächst bestand der Wunsch die Installation ähnlich wie [Bill Fontanas](#bill-fontana) (\ref{bill-fontana}, S. \pageref{bill-fontana}) Klangskulpturen zu gestalten. Es sollten portable Stationen entwickelt werden welche mit einem Kontaktmikrofon das Akustische Signal der Schiene über LTE an einen Ausstellungsraum per Livestream übertragen sollten. Dafür wurde folgende Hardware geplant:

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

Die Stationen würden an Punkten im Baden-Württembergischen Schienennetz angebracht um den Lokalbezug zur Landeshauptstadt herzustellen. Im Ausstellungsraum wäre das stetige Vibrieren der Gleise zu hören, welches mutmaßlich durch Wind und Erschütterungen im Boden entsteht, bis ein Zug an einem der Punkte vorbeiführe. Züge auf anderen Gleisen würden die Schiene an der das Kontaktmikrofon befestigt ist dennoch in Schwingung versetzen und am *Zuhörpunkt* zu hören sein. Fährt ein Zug über das Gleis, an dem das Kontaktmikrofon befestigt ist, entsteht ein sehr direktes klangliches Bild des Zuges. Zunächst ein Anschwellen eines Resonanztones in der Schiene, bis schließlich das Schleifen der Räder und das Rumpeln verursacht durch das Gewicht des Zuges zu hören sind.

Diese Geräuschkulisse, würde sich mit den Reflexionen der Lautsprechersignale im Straßenbahndepot und den Geräuschen welche dort stattfinden mischen und so den Raum des Schienennetzes von Baden-Württemberg in einen für Menschen erfassbaren Raum bringen. Dies kann als räumliche Verdichtung angesehen werden, da der Ausstellungsraum deutlich kleiner als der Raum der abgenommenen *Abhörpunkte* ist. Andererseits würde das Innere der Schiene vergrößert, indem dem akustischen Signal welches in dieser entsteht erlaubt wird, einen Raum zu füllen.

Diese Verzerrung von Räumlichkeit, sowohl vom Großen ins kleine, als auch vom Inneren ins Äußere, stellte die Essenz der Idee dar, welche hinter diesem ersten Konzept steckte.

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

Zugfinder.de ist eine deutsche Zug-Positionsanzeige, welche Statistiken über die meisten Züge in Deutschland bereithält. Für den Fernverkehr gibt es eine Deutschlandkarte, welche alle Fernverkehrszüge in einer animierten Netzkarte zeigt. Für alle weiteren Züge gibt es animierte Ansichten der einzelnen Streckenabschnitte. [@schubert_zugfinder_nodate] Die Daten dieser Seite sollten nachdem das erste Konzept gescheitert war die neue Grundlage für die Installation bilden. Hierfür müssen die Daten aus der Website in einem Benutzbaren Format vorliegen. 

Nachdem Johannes Schubert, der Entwickler von Zugfinder.de mitteilte, dass keine API Schnittstellen vorhanden sind, fiel die Entscheidung die Daten mittels Webscraping zu extrahieren. Webscraping oder Screenscraping emuliert die Benutzung einer Website durch ein automatisiertes Programm, mit dem Ziel Daten aus dieser Website zu extrahieren. [@ball_screen-scraping_2003] 

Zunächst wurde ein Prototyp entwickelt, der die Daten einer einzelnen Strecke als Input nutzte. Hierfür wurde eine *Node.js* Anwendung zum Webscraping entwickelt. *Node.js* ist eine Javascript Runtime, welche die V8 Javascript engine von Google Chrome nutzt.  [@openjs_foundation_about_nodate] Es ist also eine Umgebung um Javascript auszuführen, ähnlich wie ein Webbrowser Javascript ausführen würde. *Node.js* hat jedoch den Vorteil nicht den overhead eines Browsers zu haben und mit vielen zusätzlichen Funktionen ausgestattet zu sein, welche in klassischen Browserumgebungen nicht verfügbar sind.

Dieser Prototyp sollte das ursprüngliche Konzept mit fixen punkten im Schienennetz welche als Abhörpunkte fungieren auf andere Weise erreichen. So sollte ein bestimmter Punkt auf einer Strecke abgefragt werden, und wenn sich dort ein Zug aufhält sollten Informationen über diesen per UDP (\ref{webscraping-kommunikation} [*Kommunikation*](#webscraping-kommunikation) S. \pageref{webscraping-kommunikation}) an das Klangsyntheseprogramm in Max (siehe \ref{max} [*Max*](#max) S. \pageref{max}) übertragen werden. Es werden außer der Information, dass sich an dem Punkt ein Zug aufhält allerdings noch weitere Informationen über den Zug mitgesendet, da bei einer Synthetischen Klangerzeugung der direkte Klangliche Bezug zu dem spezifischen Zug fehlt. 

Bei einer Umsetzung mit Kontaktmikrofonen, würden Zugtyp, Umgebungsgeräusche, Gleisbett und Zustand der Schiene sowie Besonderheiten des Streckenabschnitts (Kurven, Weichen) Faktoren sein, welche den Klang verändern. Um einen Bezug zu dem Zug und dem Abgehörten Punkt herzustellen, werden zur Klangerzeugung Daten genutzt welche vom Kontext abhängig sind. 

 Als Proof-of-concept wurde eine Node.js anwendung entwickelt, welche ein Http-request an die ausgewählte Strecke auf *Zugfinder.de* schickte und die Antwort in von Javascript benutzbares JSON (*Javascript Object Notation*) und schließlich in ein Array der aktuell auf der Strecke fahrenden Züge umwandelt. Aus diesem Array werden API-Requests für die Google Distance Matrix API, eine API welche aus mehreren Start und Endpunkten eine Matrix von Distanzen herstellt [@google_get_nodate], generiert, um die Distanzen zwischen Abhörpunkt, Start- und Endbahnhof zu ermitteln. Daraus wird dann eine Angabe in Prozent erstellt, wie viel der Gesamtstrecke der Zug bereits zurückgelegt hat. In diesem Prototypen wurde diese Angabe dann genutzt um einen Bestimmten Abschnitt eines Audiofiles abzuspielen.

Dieses Konzept offenbarte nach dem testen des Prototyps einige Schwächen. Zunächst wurde klar, dass viele Abhörpunkte von Nöten wären, da es anders als bei dem ersten Konzept, zwischen den Zugevents keinerlei Klang gibt und die Ereignisdichte somit sehr gering wäre. Zudem wäre dieser Aufbau in der Wahrnehmung der Besucher nicht leicht mit Zügen in Verbindung zu bringen, und eine Installation, welche sich zumindest Teilweise selbst erklären kann war gewünscht.

### Ansätze zur Visualisierung

Um die Installation selbsterklärender zu gestalten, wurden Visuelle Elemente entwickelt. Zunächst sollten die Lautsprecher mit Plaketten ausgestattet werden, welche angeben zwischen welchen beiden Haltestellen der zugehörige Abhörpunkt liegt. Zudem sollten Lichter an den Lautsprechern angebracht werden welche je nach Zugtyp, bei einem vorbeifahrenden Zug in verschiedenen Farben leuchten. So sollte der Blick des Besuchers auf die Lautsprecher gerichtet werden, sodass dieser die Plakette liest. Zudem sollte es die Events noch eindeutiger machen. Beim Testen dieses Ansatzes wurde jedoch klar, dass auch diese Visuellen Hilfen nicht die grundlegenden Probleme mit diesem Prototypen lösen würde. 

Es wurde deswegen entschieden eine Karte der Züge anzufertigen, welche sich in Echtzeit aktualisiert. Auf dieser sollten die Abhörpunkte dann eindeutig markiert werden. Im laufe der Entwicklung dieser Karte wurden Debugging features entwickelt, um mithilfe des Cursors Information über einzelne Züge auszulesen. Während des Debuggings, entstand die Idee, die Cursorinteraktion als Interaktionsmöglichkeit für den Besucher bereitzustellen. Schließlich wurden die Abhörpunkte als Konzept aus der Installation vollständig entfernt, und die Installation wurde Interaktiv. Es ist jetzt nur noch einen Abhörpunkt vorhanden, und dieser wird von einem Besucher selbst gesteuert. 

Genaueres zur finalen Implementierung dieses Interaktionsprinzips findes sich in Kaptiel \ref{umsetzung} [*Umsetzung*](#umsetzung) S. \pageref{umsetzung}.

## Finales Konzept

Im folgenden wird das Konzept vorgestellt, welches das Ergebnis der Experimente und Entwicklungen seit der ursprünglichen Idee bis zum Zeitpunkt dieser Arbeit ist.

### Motivation

#### Persönliche Beweggründe

Henning Schaar lebte in seiner Schulzeit 4 Jahre lang in einer Fernbeziehung nach Mannheim, von Karlsruhe eine Entfernung von ca. einer Zugstunde. Diese wurde dann schließlich durch eine gemeinsame Wohnung in Mannheim aufgelöst. Nicht viel später Jedoch begann das Studium in Dieburg, welches wieder über eine Zugstunde entfernt war. Nach Ende der Beziehung gab es einen Wohnortwechsel nach Darmstadt, so dass das Studium nun näher war, doch gibt es weiterhin Freundschaften in Hamburg, einen Arbeitgeber in Stuttgart und eine Band und Familie in Karlsruhe, weswegen Zugfahrten weiterhin zum Alltag gehören.

Diese räumlich verteilte Lebensweise verändert nicht nur das Reiseverhalten, auch die Selbstwahrnehmung wird durch sie beeinflusst. In jedem dieser Orte gibt es andere soziale Kreise, welche sich nicht oder kaum überschneiden und das Selbstbild einer Person wird durch sozial geteilte Merkmale und Gruppenmitgliedschaften maßgeblich beeinflusst. [@rempe_zur_2012 S. 31f] So wird die Zugfahrt zu einem Prozess welcher in diesem Fall nicht nur den Aufenthaltsort einer Person ändert, sondern schließlich auch die Wahrnehmung der eigenen Person.

Aus diesen komplexen Gefühlen welche durch das Reisen hervorgebracht wurden entstand ein generelles Interesse an den Gefühlen die Personen beim Nutzen von öffentlichen Verkehrsmitteln haben und der Wunsch diese Künstlerisch festzuhalten.

#### Befragungen {#befragungen}

Um über den eigenen Erfahrungshorizont hinauszugehen, wurden formlose Befragungen von Kommilitonen, Freunden und Familie durchgeführt. Es wurde nach Gründen und Häufigkeit der Nutzung gefragt, sowie welcher emotionaler Bezug zu Abfahrts- und Ankunftsort besteht, und wie sich diese im Laufe der Reise wandeln. [@schaar_gedachtnisprotokoll_2019]

Anhand der Antworten wurden die Befragten in drei Kategorien unterteilt:

- **20-45 Minuten, mehrmals die Woche:** Die Person nimmt das Fahrzeug größtenteils in seiner Funktion die Hürde der Distanz zu verringern wahr. Der Innenraum des Zuges wird als Teil des öffentlichen Raumes empfunden. Es ist kein Ort an dem man sich tatsächlich aufhält, sondern vielmehr eine Art Wartezimmer. Die Reise wird als Zeitlich homogen wahrgenommen.
- **1-2 Stunden, ca. einmal die Woche:** Das Fahrzeug wird ähnlich wie ein Gebäude wahrgenommen in welchem man sich temporär einrichtet. Arbeit oder Unterhaltung der man auch zu Hause nachgehen würde wird mitgebracht. Personen die unter diese Kategorie fallen berichteten von *FOMO* (fear of missing out), also ein Gefühl ein wichtiges oder erfüllendes Ereignis zu verpassen welches an dem Ort, an dem sie sich gerade nicht aufhalten erlebt werden könnte. [@bosker_fear_2012] Insbesondere wurde berichtet, dass die Reise sich grob in 5 Teile einteilen lässt: Zuerst das Gefühl des Abschieds und das verarbeiten dessen. Wenn dieses Gefühl schwindet, wird, oft in Vorfreude, darüber nachgedacht, was am Ankunftsort wartet. Als drittes kommt ein Gefühl des Zwischenzustandes auf, an dem manchmal ein Gefühl von Langeweile oder des nicht-Empfindens beschrieben wird. Vor Ende der Reise denken viele der Befragten nochmal zurück an den Abfahrtsort und was dort während ihrer Abwesenheit geschieht bevor sie sich schließlich auf die Ankunft vorbereiten und ein Gefühl des Erwartens oder des Aufbrechens über sie kommt.
- **3-5 Stunden einmal alle 6-8 Wochen:** Anders als bei den beiden anderen Kategorien, antizipieren Reisende dieser Art die Reise schon weit im Voraus und das Reisegefühl stellt sich schon oft ein bis zwei Tage vor der tatsächlichen Reise ein. Das Fahrzeug wird ähnlich wie in der vorangehenden Kategorie als eine Art Gebäude wahrgenommen. Reisende dieser Kategorie, berichten nur selten von FOMO, da der Ankunftsort oft noch gar nicht oder lange nicht mehr besucht wurde und viele ungewöhnliche Erlebnisse bereithält. Oft wird die Zeit der Reise für Dinge genutzt für die im Alltag selten Zeit ist, wie zum Beispiel viel Zeit mit einem Buch zu verbringen. Die Reise verläuft meist ähnlich wie bei der vorangehenden  Kategorie jedoch wird der mittlere Teil, des Zwischenzustandes meist als positiv beschrieben. Statt Langeweile oder Leere empfinden Zugreisende oft Entspannung und friedliche Gefühle oder schlafen sogar ein. Insgesamt wird die Reise, wenn keine Probleme auftreten, als angenehmer beschrieben.

#### Inspiration aus kunsthistorischer Recherche

Wie sich die Geräuschkulisse die wir Menschen durch die Industrielle Revolution veränderte und wie dies unser aurikulare Wahrnehmung veränderte wurde durch die Studie der Italienischen Futuristen offensichtlich. Da der Schienenverkehr eine treibende Kraft der Industriellen Revolution war, konnte diese Assoziation bei der klanglichen Gestaltung nicht außer Acht gelassen werden. Beim erstellen der Klangobjekte, welcher zur Herstellung der interaktiven Sounds genutzt werden, wurde aus diesem Grund darauf geachtet, dass ein Bezug zu den Geräuschen des Zugverkehrs zu erkennen ist. 

Das Publikum hat bei der Installation eine aktive Rolle bei der Entstehung der Klänge. So ist die Installation meist still, wenn es keine Interaktion durch den Besucher gibt. Hierdurch entsteht eine Verantwortung über die Klangerzeugung die zu einem großen Teil in den Händen des Publikums liegt. Ähnlich wie in Cages Werken, wird durch die Installation nur ein Rahmen geschaffen, in welchem das Publikum an der Entstehung eines Klangs teilhaben kann. Auch wird durch die Interaktion die Form des Zuhörens modifiziert. Denn wenn der Besucher die Verantwortung über die Erzeugung des Klangs annimmt, ist der Bezug zu den entstehenden Klängen eher vergleichbar mit jenem, welcher auch beim Ausüben eines Musikinstrumentes besteht als mit dem der beim anhören eines Konzertes herrscht. Anders als bei Cages populären stillen Werken allerdings, ist der Rahmen ein sehr fester, welcher zum Großteil von äußeren Faktoren, nur teilweise durch den Künstler und kaum durch das Publikum kontrolliert wird.

Die Klangobjekte sind größtenteils durch das modifizieren von Aufnahmen von Zügen entstanden. Das modifizieren fand jedoch nicht nach einem geordneten Prinzip statt, sondern es wurde viel mehr mit einen Feedback-Loop aus zuhören, bewerten und verändern gearbeitet. Diese Arbeitsweise war zwar bereits vor Recherchieren der experimentellen Ansätze von *Musique Concrète* und Steina Vasulka bekannt, jedoch wurde eine höhere Sicherheit im Arbeiten nach diesem Prinzip durch die Kenntnis über die Bewährtheit dieser Methoden erreicht.

Auch die Idee des *Objet Trouvé* fand Verwendung in der Herstellung der Arbeit. So handelt es sich nicht um einen fertigen Gegenstand welcher ausgestellt wird, jedoch ist die Grundsätzliche Idee, etwas Alltägliches durch den Prozess des Ausstellens zu einem Kunstwerk zu machen, grundlegend für die Installation. Die Benutzung öffentlicher Verkehrsmittel ist etwas mit dem die meisten Menschen in ihrem Alltag konfrontiert sind. Dem Schienenverkehr jedoch einen Klang zu geben und Ästhetisch darzustellen ist nicht der gewohnte Kontext und gibt dem Besucher dadurch die Möglichkeit seinen Bezug zu diesem neu zu definieren.

Der Musikbegriff von Bill Fontana, der darauf beruht, dass Musik kein Akustisches Ereignis ist, sondern ein Modus des Zuhörens, geht Hand in Hand mit dem Gedanken von John Cage, den Zuhörer auf eben diesen Modus aufmerksam zu machen. Bei der Umsetzung der Installation werden diese Prinzipien genutzt um die Geräusche von Zügen durch Soundprocessing im allgemeinen Verständnis musikalischer zu gestalten, jedoch nur genug, um dem Zuhörer welcher eben dieses allgemeine Verständnis von Musik mitbringt darauf hinzuweisen, dass die Möglichkeit besteht diese Geräusche, die uns Umgeben und häufig als störend empfunden werden, als musikalisch zu verstehen.

Als eine Art *Sound Map* des Zugverkehrs reiht sich *Vernetzt* in den aktuellen Trend der *Aural Architecture* ein, in dem es räumliche Wahrnehmung  und urbane Infrastruktur durch interaktiv gesteuerte Sonification musikalisch versteht und darstellt.

### Inhaltliche Beschreibung

#### Reisegeschichten und Dramaturgie

#### Personae

Aus den Befragungen entstanden zur Herstellung der Klangobjekte Personae. Der Begriff der Personae wird in diesem Fall als Darstellung einer Sammlung derer Eigenschaften einer fiktiven Person genutzt welche von außen ersichtlich sind. Sie sind stellvertretend für Eigenschaften die in fast jedem Menschen gefunden werden können und stellen als ganzes nur eine Facette der Erlebniswelt einer tatsächlichen Person dar. 

Es gibt drei Personae, und jede hat ihr korrespondierendes Klangobjekt welches das Material ist, dass die Sonification in *Max* nutzt um die Klänge der Installation zu produzieren. Welches Klangobjekt benutzt wird ist Abhängig vom Zugtypen, wobei die Zugtypen so gewählt wurden, dass sie zur Art der Reise der jeweiligen Persona passen. In der Ausstellung hängen außerdem Steckbriefe zu den Personae mit den korrespondierenden Farben der Züge in der Visualisierung um den Bezug zwischen Persona und gehörtem Klang herzustellen. Im folgenden soll kurz beschrieben werden, welche Eigenschaften die Personae haben und welche Funktionen diese Eigenschaften in ihrem Verhältnis zu einem Besucher erfüllen:

- **Gabriel** ist das äquivalent zu dem mehrmals in der Woche Kurzstrecken zurücklegenden Zugreisenden. Er ist 35 Jahre alt und hat eine Festanstellung in einem mittelgroßen IT Betrieb ohne den Wunsch diese Position in absehbarer Zeit zu verlassen. Er beginnt und beendet seine Arbeit pünktlich, da ihm sein Familienleben mit seiner Frau und seinen zwei Töchtern, genau wie seine Mitgliedschaft im Lokalen Motorcrossverein sehr wichtig sind. Die Zeit im Zug zu und von seinem Arbeitsplatz nutzt er gerne um in Ruhe nachzudenken. Sein alter, ist ein Alter in dem die meisten Menschen einen mehr oder weniger gefestigtes Leben haben. Dieses Gefühl der Sicherheit wird weiterhin durch seine Vereinsmitgliedschaft, die Festanstellung und das Intakte Familienleben gestärkt. Ihn ihm kann der eigene Wunsch nach Sicherheit gespiegelt werden, jedoch nicht in einem Maße, dass sich einschränkend anfühlen soll. 
  Er steht bei seinem Arbeitgeber für seine Interessen ein, auch wenn das bedeutet, dass er bei der nächsten Unternehmensverkleinerung eine höhere Gefahr läuft seine Anstellung zu verlieren. Außerdem geht er dem nicht ungefährlichen Hobby des Motorcross' nach. Das Motorcross fahren und seine Position als Informatiker machen seine Liebe zur Technik klar. Dies soll auf ein Ästhetikverständnis hinweisen welches sich zum Großteil auf geordnete Schönheit bezieht, jedoch nicht ausschließlich, da Motorcross als Freiluftsport auch auf eine Naturverbundenheit hinweist.
- **Julia** entspricht der Zugreisenden, welche ca. einmal in der Woche 1-2 Stunden unterwegs ist. Sie ist 23 Jahre alt und strebt aktuell ihren Bachelor in Literaturwissenschaften an. Ihr Partner ist aktuell im Praxissemester etwas über eine Stunde entfernt von ihrem Wohnort weswegen sie am Wochenende häufig den Zug nimmt. Sie wohnt auch nur 2 Zugstunden von ihren Eltern entfernt welche sie meist in der Vorlesungsfreien Zeit aber auch an manchen Wochenenden besucht. Sie weiß noch nicht wo sie nach ihrem Bachelor hingehen wird. Ein Master in der gleichen Fachrichtung wäre eine Option aber sie interessiert sich neben Literaturwissenschaften für eine Ausbildung in Layout und Graphikdesign, da sie in ihrer Freizeit gerne zeichnet. Die Wahl des weiterführenden Ausbildungsortes wird erschwert dadurch, dass sie sowohl in der Nähe ihrer Famillie als auch ihres Partners bleiben möchte. 
  Der Besucher kann in ihr die Unsicherheit von Wandel und einer ungewissen Zukunft nachempfinden. Jedoch steht sie gleichzeitig für den Wunsch nach Selbstverwirklichung, welcher in dieser Unsicherheit ermöglicht ist und durch ihre künstlerischen Anlagen in Literatur und Bildender Kunst verkörpert wird. Die Angst etwas zu verpassen und alle Bereiche des Lebens miteinander zu vereinen, ohne dabei viele Kompromisse eingehen zu müssen, findet sich in ihrem Abwägen über den neuen Wohnort in Abhängigkeit von Ausbildung, Familie und Liebe wieder. (*FOMO* vgl. \ref{befragungen} [*Befragungen*](#befragungen) S. \pageref{befragungen}) 
- **Leonie** fährt nur ca. alle 6-8 Wochen mit dem Zug, aber dafür 6-8 Stunden lang. Mit 28 Jahren ist Sie seit ca. 2 Jahren im Berufsalltag als Messtechnikerin. Sie genießt nach dem Ende einer langen Beziehung die neu gefundene Unabhängigkeit und ist für ihren Job in eine neue Stadt, weit weg von ihrer Heimat gezogen. Sie übernimmt in ihrem Job viel Verantwortung und eine Beförderung ist aktuell in Sicht. Obwohl sie viel Zeit im Büro verbringt hilft sie am Wochenende auf einem Gnadenhof, da sie schon von klein auf eine besondere Bindung zu Tieren empfindand. In einer Männerdomäne arbeitend ist sie mit unkooperativen männlichen vorgesetzten konfrontiert weswegen sie sehr widerstandsfähig ist. Dadurch verkörpert sie die Stärke auch unter schweren Umständen entschlossen voranzuschreiten. In dieser Entschlossenheit und Unabhängigkeit spiegelt sie jedoch auch die Gefühle der Einsamkeit der Besucher wider. In Leonies Arbeit auf dem Gnadenhof können Besucher sich in ihrem Selbstverständnis als vielseitig und manchmal missverstanden wiederfinden.

#### Zwischenzustände

#### Bedeutung von Raum

### Raumkonzept/Aufbau

#### Nutzung von Lautsprechern

Für den Aufbau wurde ein quadrophonischer Aufbau mit Subwoofer gewählt. Ein klassisches 5.1 Setup wurde in Erwägung gezogen, der Lautsprecheraufbau hat aber keinen Grund unsymmetrisch zu sein, da die Richtung der Leinwand nur optisch im Vordergrund steht, und keine besonderen Akustischen Impulse als von der Leinwand kommend verstanden werden sollen. 

Der Subwoofer ist möglichst nah am Interaktionsinterface, damit dieser auch möglichst nah am Interagierenden Besucher ist. Diese Position wurde gewählt, weil der Tieftonanteil nicht ortbar sein soll, sondern nur eine unterstützende Funktion hat

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{visualisierungp5}
\break
\caption{Screenshot eines Ausschnittes der Visualisierung in p5: Züge in Farben nach Typ, Haltestellen grau und Cursor weiß umrandet.}
\end{figure}

Die Klänge die von den Zügen erzeugt werden, sollen so um den interagierenden Besucher verteilt sein wie sie um den Cursor verteilt sind. Die visuelle Darstellung ist jedoch zweidimensional, weswegen die Räumliche Verteilung von der ZY Ebene auf der Projektionsfläche um 90° vom Besucher weggekippt wird, um auf der XY Ebene zu Liegen. 

So wird der Quadrophonische Aufbau genutzt um die XY Ebene akustisch zu füllen. Es werden basierend auf der Distanz der Züge zum Cursor außerdem Halleffekte genutzt um die Illusion eines akustischen Raumes zu verbessern. 

#### Raum als Medium für Schall

Außerhalb des virtuellen akustischen Raumes gibt es allerdings noch den echten akustischen Raum in dem die Installation aufgebaut wird. 

#### Nutzung von Graphik

#### 

