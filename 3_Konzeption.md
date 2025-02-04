

# Konzeption

Wie in \ref{einleitung} [*Einleitung*](#einleitung)  (S. \pageref{einleitung}) erwähnt, stand am Anfang der Arbeit an der Installation, der Wunsch, das Schienennetz als akustischen Raum darzustellen. Hieraus entstand die Idee, diese Vertonung anhand der Gefühle von Zugreisenden zu orientieren. Da sich die Installation an bereits existierende Inputs, den Zugverkehr des gewählten Ortes, anpassen muss, wurde ein experimenteller Ansatz zur Entwicklung der Arbeit gewählt.

## Experimente und deren Ergebnisse

### Ansätze mit Kontaktmikrofonen

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroAnSchiene}
\break
\caption{Kontaktmikrofon an stillgelegtem Gleis}
\end{figure}

Zunächst bestand der Wunsch die Installation ähnlich wie [Bill Fontanas](#bill-fontana) (vgl \ref{bill-fontana} [*Bill Fontana*](#bill-fontana), S. \pageref{bill-fontana}) Klangskulpturen zu gestalten. Es sollten portable Stationen entwickelt werden welche mit einem Kontaktmikrofon das akustische Signal der Schiene über LTE an einen Ausstellungsraum per Livestream übertragen sollten. Dafür wurde folgende Hardware geplant:

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

Die Stationen würden an Punkten im Baden-Württembergischen Schienennetz angebracht um den Lokalbezug zur Landeshauptstadt herzustellen. Im Ausstellungsraum wäre das stetige Vibrieren der Gleise zu hören, welches mutmaßlich durch Wind und Erschütterungen im Boden entsteht, bis ein Zug an einem der Punkte vorbeiführe. Züge auf anderen Gleisen würden die Schiene an der das Kontaktmikrofon befestigt ist dennoch in Schwingung versetzen und am *Zuhörpunkt* zu hören sein. Fährt ein Zug über das Gleis, an dem das Kontaktmikrofon befestigt ist, entsteht ein sehr direktes klangliches Bild des Zuges. Zunächst ein Anschwellen eines Resonanztones in der Schiene, bis schließlich das Schleifen der Räder und das Rumpeln, verursacht durch das Gewicht des Zuges, zu hören sind.

Diese Geräuschkulisse, würde sich mit den Reflexionen der Lautsprechersignale im Straßenbahndepot und den Geräuschen, welche dort stattfinden, mischen und so den Raum des Schienennetzes von Baden-Württemberg in einen für Menschen erfassbaren Raum bringen. Dies kann als räumliche Verdichtung angesehen werden, da der Ausstellungsraum deutlich kleiner als der Raum der abgenommenen *Abhörpunkte* ist. Andererseits würde das Innere der Schiene vergrößert, indem dem akustischen Signal welches in dieser entsteht erlaubt wird, einen Raum zu füllen.

Diese Verzerrung von Räumlichkeit, sowohl vom Großen ins Kleine, als auch vom Inneren ins Äußere, stellte die Essenz der Idee dar, welche hinter diesem ersten Konzept steckte.

Inspiriert von Bill Fontanas Arbeit, insbesondere *Harmonic Bridge*, bei der die Geräusche einer Fußgängerbrücke in die *Tate Gallery of Modern Art* übertragen wurden, wurde die Möglichkeit der Nutzung von Beschleunigungssensoren in Erwägung gezogen. Für die Wahl des Kontaktmikrofons wurden dann Experimente mit Metallischen Körpern durchgeführt. 

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroVergleich}
\break
\caption{Piezoelektrisches Mikrofon (links) und Beschleunigungssensor an Teensy (rechts)}
\end{figure}

Sogenannte *MEMS* (microelectromechanical systems) Beschleunigungssensoren können als Kontaktmikrofon verwendet werden. Viele Mikrofontypen funktionieren, indem sie den Schalldruck messen. Der Schalldruck, der von einem vibrierenden Körper verursacht wird, ist proportional zu der Beschleunigung, weswegen sich ein Beschleunigungssensor zur Abnahme einer akustischen Quelle eignet. [@oreilly_sonic_2009 S. 1f] 

Nachdem jedoch klar wurde, dass das Anbringen von technischen Geräten an das Gleis unter §315 StGB: "Gefährliche Eingriffe in den Bahn-, Schiffs- und Luftverkehr" strafbar sein könnte, wurden Alternativen gesucht.

### Ansätze mit Webscraping {#ansaetze-mit-webscraping}

*Zugfinder.de* ist eine deutsche Zug-Positionsanzeige, welche Statistiken über die meisten Züge in Deutschland bereithält. Für den Fernverkehr gibt es eine Deutschlandkarte, welche alle Fernverkehrszüge in einer animierten Netzkarte zeigt. Für alle weiteren Züge gibt es animierte Ansichten der einzelnen Streckenabschnitte. [@schubert_zugfinder_nodate] Die Daten dieser Seite sollten, nachdem das erste Konzept gescheitert war, die neue Grundlage für die Installation bilden. Hierfür müssen die Daten aus der Website in einem geeigneten Format vorliegen. 

Nachdem Johannes Schubert, der Entwickler von *Zugfinder.de* mitteilte, dass keine API Schnittstellen vorhanden sind, fiel die Entscheidung die Daten mittels Webscraping zu extrahieren. Webscraping oder Screenscraping emuliert die Benutzung einer Website durch ein automatisiertes Programm, mit dem Ziel Daten aus dieser Website zu extrahieren. [@ball_screen-scraping_2003] 

Zunächst wurde ein Prototyp entwickelt, der die Daten einer einzelnen Strecke als Input nutzte. Hierfür wurde eine *Node.js* Anwendung zum Webscraping entwickelt. (*Node.js* vgl.\ref{nodejs} [*Webscraping & Node.js*](#nodejs) S. \pageref{nodejs} )

Dieser Prototyp sollte das ursprüngliche Konzept mit fixen Punkten im Schienennetz, welche als Abhörpunkte fungieren, auf andere Weise erreichen. So sollte ein bestimmter Punkt auf einer Strecke abgefragt werden, und wenn sich dort ein Zug aufhält sollten Informationen über diesen per UDP (vgl. \ref{webscraping-kommunikation} [*Kommunikation*](#webscraping-kommunikation) S. \pageref{webscraping-kommunikation}) an das Klangsyntheseprogramm in Max (vgl. \ref{max} [*Max*](#max) S. \pageref{max}) übertragen werden. Es werden außer der Information, dass sich an dem Punkt ein Zug aufhält allerdings noch weitere Informationen über den Zug mitgesendet, da bei einer synthetischen Klangerzeugung der direkte klangliche Bezug zu dem spezifischen Zug fehlt. 

Bei einer Umsetzung mit Kontaktmikrofonen, würden Zugtyp, Umgebungsgeräusche, Gleisbett und Zustand der Schiene sowie Besonderheiten des Streckenabschnitts (Kurven, Weichen) Faktoren sein, welche den Klang verändern. Um einen Bezug zu dem Zug und dem abgehörten Punkt herzustellen, werden zur Klangerzeugung Daten genutzt welche vom Kontext abhängig sind. 

 Als Proof-of-concept wurde eine Node.js Anwendung entwickelt, welche ein Http-request an die ausgewählte Strecke auf *Zugfinder.de* stellt und die Antwort in von Javascript benutzbares JSON (*Javascript Object Notation*) und schließlich in ein Array der aktuell auf der Strecke fahrenden Züge umwandelt. Aus diesem Array werden API-requests für die Google Distance Matrix API, eine API welche aus mehreren Start und Endpunkten eine Matrix von Distanzen herstellt [@google_get_nodate], generiert, um die Distanzen zwischen Abhörpunkt, Start- und Endbahnhof zu ermitteln. Hieraus wird dann eine Angabe in Prozent berechnet, welchen Anteil der Gesamtstrecke der Zug bereits zurückgelegt hat. In diesem Prototypen wurde diese Angabe dann genutzt, um einen bestimmten Abschnitt einer Tondatei abzuspielen.

Dieses Konzept offenbarte nach dem Testen des Prototyps einige Schwächen. Zunächst wurde klar, dass viele Abhörpunkte benötigt würden, da es anders als bei dem ersten Konzept, zwischen den Zugevents keinerlei Klang gibt und die Ereignisdichte somit sehr gering wäre. Zudem wäre dieser Aufbau in der Wahrnehmung der Besucher nicht leicht mit Zügen in Verbindung zu bringen, und eine Installation, welche sich zumindest teilweise selbst erklären kann, war gewünscht.

### Ansätze zur Visualisierung

Um die Installation selbsterklärender zu gestalten, wurden visuelle Elemente entwickelt. Zunächst sollten die Lautsprecher mit Plaketten ausgestattet werden, welche angeben zwischen welchen beiden Haltestellen der zugehörige Abhörpunkt liegt. Zudem sollten Lichter an den Lautsprechern angebracht werden die, je nach Zugtyp, bei einem vorbeifahrenden Zug in verschiedenen Farben leuchten. So sollte der Blick des Besuchers auf die Lautsprecher gerichtet werden, sodass dieser die Plakette liest. Zudem sollte es die Events noch eindeutiger machen. Beim Testen dieses Ansatzes wurde jedoch klar, dass auch diese visuellen Hilfen nicht die grundlegenden Probleme mit diesem Prototypen lösen würden. 

Es wurde deswegen entschieden eine Karte der Züge anzufertigen, welche sich in Echtzeit aktualisiert. Auf dieser sollten die Abhörpunkte dann eindeutig markiert werden. Im Laufe der Entwicklung dieser Karte wurden Debugging features entwickelt, um mithilfe des Cursors Information über einzelne Züge auszulesen. Während des Debuggings, entstand die Idee, den Cursor als Interaktionsmöglichkeit für den Besucher bereitzustellen. Schließlich wurden die Abhörpunkte als Konzept aus der Installation vollständig entfernt, und die Installation wurde interaktiv. Es ist jetzt nur noch ein Abhörpunkt vorhanden, und dieser wird von einem Besucher selbst gesteuert. 

Genaueres zur finalen Implementierung dieses Interaktionsprinzips findet sich in Kaptiel \ref{umsetzung} [*Umsetzung*](#umsetzung) S. \pageref{umsetzung}.

## Finales Konzept

Im Folgenden wird das Konzept vorgestellt, welches das Ergebnis der Experimente und Entwicklungen seit der ursprünglichen Idee bis zum Zeitpunkt dieser Arbeit ist.

### Motivation

#### Persönliche Beweggründe

Der Autor lebte in seiner Schulzeit 4 Jahre lang in einer Fernbeziehung nach Mannheim, von Karlsruhe eine Entfernung von ca. einer Zugstunde. Diese wurde dann schließlich durch eine gemeinsame Wohnung in Mannheim aufgelöst. Nicht viel später jedoch begann das Studium in Dieburg, welches wieder über eine Zugstunde entfernt war. Nach Ende der Beziehung gab es einen Wohnortwechsel nach Darmstadt, so dass das Studium nun näher war, doch gibt es weiterhin Freundschaften in Hamburg, einen Arbeitgeber in Stuttgart und eine Band und Familie in Karlsruhe, weswegen Zugfahrten weiterhin zum Alltag gehören.

Diese räumlich verteilte Lebensweise verändert nicht nur das Reiseverhalten, auch die Selbstwahrnehmung wird durch sie beeinflusst. In jedem dieser Orte gibt es andere soziale Kreise, welche sich nicht oder kaum überschneiden und das Selbstbild einer Person wird durch sozial geteilte Merkmale und Gruppenmitgliedschaften maßgeblich beeinflusst. [@rempe_zur_2012 S. 31f] So wird die Zugfahrt zu einem Prozess welcher in diesem Fall nicht nur den Aufenthaltsort einer Person ändert, sondern schließlich auch die Wahrnehmung der eigenen Person.

Aus diesen komplexen Gefühlen, welche durch das Reisen hervorgebracht wurden, entstand ein generelles Interesse an den Gefühlen die Personen beim Nutzen von öffentlichen Verkehrsmitteln haben und der Wunsch diese künstlerisch festzuhalten.

#### Befragungen {#befragungen}

Um über den eigenen Erfahrungshorizont hinauszugehen, wurden formlose Befragungen von Kommiliton\*innen, Freund\*innen und Familie durchgeführt. Es wurde nach Gründen und Häufigkeit der Nutzung gefragt, sowie welcher emotionaler Bezug zu Abfahrts- und Ankunftsort besteht, und wie sich diese im Laufe der Reise wandeln. [@schaar_gedachtnisprotokoll_2019]

Anhand der Antworten wurden die befragten Personen in drei Kategorien unterteilt:

- **20-45 Minuten, mehrmals die Woche:** Die Person nimmt das Fahrzeug größtenteils in seiner Funktion, die Hürde der Distanz zu verringern, wahr. Der Innenraum des Zuges wird als Teil des öffentlichen Raumes empfunden. Es ist kein Ort an dem man sich tatsächlich aufhält, sondern vielmehr eine Art Wartezimmer. Die Reise wird als zeitlich homogen wahrgenommen.
- **1-2 Stunden, ca. einmal die Woche:** Das Fahrzeug wird ähnlich wie ein Gebäude wahrgenommen, in welchem man sich temporär einrichtet. Arbeit oder Unterhaltung, der man auch zu Hause nachgehen würde, wird mitgebracht. Personen die unter diese Kategorie fallen berichteten von *FOMO* (fear of missing out), also ein Gefühl ein wichtiges oder erfüllendes Ereignis zu verpassen welches an dem Ort, an dem sie sich gerade nicht aufhalten erlebt werden könnte. [@bosker_fear_2012] Insbesondere wurde berichtet, dass die Reise sich grob in fünf Teile einteilen lässt: Zuerst das Gefühl des Abschieds und das Verarbeiten dessen. Wenn dieses Gefühl schwindet, wird, oft in Vorfreude, darüber nachgedacht, was am Ankunftsort wartet. Als drittes kommt ein Gefühl des Zwischenzustandes auf, an dem manchmal ein Gefühl von Langeweile oder des nicht-Empfindens beschrieben wird. Vor Ende der Reise denken viele der Befragten nochmal zurück an den Abfahrtsort und was dort während ihrer Abwesenheit geschieht, bevor sie sich schließlich auf die Ankunft vorbereiten und ein Gefühl des Erwartens oder des Aufbrechens über sie kommt.
- **3-5 Stunden einmal alle 6-8 Wochen:** Anders als bei den beiden anderen Kategorien, antizipieren Reisende dieser Art die Reise schon weit im Voraus und das Reisegefühl stellt sich schon oft ein bis zwei Tage vor der tatsächlichen Reise ein. Das Fahrzeug wird ähnlich wie in der zweiten Kategorie als eine Art Gebäude wahrgenommen. Reisende dieser Kategorie, berichten nur selten von FOMO, da der Ankunftsort oft noch gar nicht oder lange nicht mehr besucht wurde und viele ungewöhnliche Erlebnisse bereithält. Oft wird die Zeit der Reise für Dinge genutzt für die im Alltag selten Zeit ist, wie zum Beispiel viel Zeit mit einem Buch zu verbringen. Die Reise verläuft meist ähnlich wie bei der vorangehenden  Kategorie jedoch wird der mittlere Teil des Zwischenzustandes meist als positiv beschrieben. Statt Langeweile oder Leere empfinden Zugreisende oft Entspannung und friedliche Gefühle oder schlafen sogar ein. Insgesamt wird die Reise, wenn keine Probleme auftreten, als angenehm beschrieben.

#### Inspiration aus kunsthistorischer Recherche

Wie sich die Geräuschkulissen, die wir wahrnehmen durch die Industrielle Revolution veränderten und wie dies unsere aurikulare Wahrnehmung veränderte, wurde durch die Studie der Italienischen Futuristen offensichtlich. Da der Schienenverkehr eine treibende Kraft der Industriellen Revolution war, konnte diese Assoziation bei der klanglichen Gestaltung nicht außer Acht gelassen werden. Beim Erstellen der Klangobjekte, welche zur Herstellung der interaktiven Sounds genutzt werden, wurde aus diesem Grund darauf geachtet, dass ein Bezug zu den Geräuschen des Zugverkehrs zu erkennen ist. 

Das Publikum hat bei der Installation eine aktive Rolle in der Entstehung der Klänge. So ist die Installation meist still, wenn es keine Interaktion durch den Besucher gibt. Hierdurch entsteht eine Verantwortung über die Klangerzeugung, die zu einem großen Teil in den Händen des Publikums liegt. Ähnlich wie in Cages Werken, wird durch die Installation nur ein Rahmen geschaffen, in welchem das Publikum an der Entstehung eines Klangs teilhaben kann. Auch wird durch die Interaktion die Form des Zuhörens modifiziert, denn wenn der Besucher die Verantwortung über die Erzeugung des Klangs annimmt, ist der Bezug zu den entstehenden Klängen eher vergleichbar mit jenem, welcher auch beim Ausüben eines Musikinstrumentes besteht, als mit dem der beim Anhören eines Konzertes herrscht. Anders als bei Cages populären stillen Werken allerdings, ist der Rahmen ein sehr fester, welcher zum Großteil von äußeren Faktoren, nur teilweise durch den Künstler und kaum durch das Publikum kontrolliert wird.

Die Klangobjekte sind größtenteils durch das Modifizieren von Aufnahmen von Zügen entstanden. Das Modifizieren fand jedoch nicht nach einem geordneten Prinzip statt, sondern es wurde viel mehr mit einen Feedback-Loop aus Zuhören, Bewerten und Verändern gearbeitet. Diese Arbeitsweise war zwar bereits vor Recherchieren der experimentellen Ansätze von *Musique Concrète* und Steina Vasulka bekannt, jedoch wurde eine höhere Sicherheit im Arbeiten nach diesem Prinzip durch die Kenntnis über die Bewährtheit dieser Methoden erreicht.

Auch die Idee des *Objet Trouvé* fand Verwendung in der Herstellung der Arbeit. So handelt es sich nicht um einen fertigen Gegenstand welcher ausgestellt wird, jedoch ist die grundsätzliche Idee, etwas Alltägliches durch den Prozess des Ausstellens zu einem Kunstwerk zu machen, grundlegend für die Installation. Die Benutzung öffentlicher Verkehrsmittel ist etwas mit dem die meisten Menschen in ihrem Alltag konfrontiert sind. Dem Schienenverkehr jedoch einen Klang zu geben und ihn ästhetisch darzustellen ist nicht der gewohnte Kontext und gibt dem Besucher dadurch die Möglichkeit seinen Bezug zu diesem neu zu definieren.

Der Musikbegriff von Bill Fontana, der darauf beruht, dass Musik kein akustisches Ereignis ist, sondern ein Modus des Zuhörens, geht Hand in Hand mit dem Gedanken von John Cage, den Zuhörer auf eben diesen Modus aufmerksam zu machen. Bei der Umsetzung der Installation werden diese Prinzipien genutzt um die Geräusche von Zügen durch Soundprocessing im allgemeinen Verständnis musikalischer zu gestalten. Es wurde darauf geachtet, dies nur in einem Maße zu tun, das genügt, um dem Zuhörer, welcher ein allgemeine Verständnis von Musik mitbringt, darauf hinzuweisen, dass die Möglichkeit besteht diese Geräusche, die uns umgeben und häufig als störend empfunden werden, als musikalisch zu verstehen.

Als eine Art *Sound Map* des Zugverkehrs reiht sich *Vernetzt* in den aktuellen Trend der *Aural Architecture* ein, in dem es räumliche Wahrnehmung  und urbane Infrastruktur durch interaktiv gesteuerte Sonification musikalisch versteht und darstellt.

### Inhaltliche Beschreibung

#### Personae

Aus den Befragungen entstanden zur Herstellung der Klangobjekte Personae. Der Begriff der Personae wird in diesem Fall als Darstellung einer Sammlung derer Eigenschaften einer fiktiven Person genutzt, welche von Außen ersichtlich sind. Sie sind stellvertretend für Eigenschaften die in fast jedem Menschen gefunden werden können und stellen als Ganzes nur eine Facette der Erlebniswelt einer tatsächlichen Person dar. 

Es gibt drei Personae und jede hat ihr korrespondierendes Klangobjekt, welches das Material ist, dass die Sonification in *Max* nutzt um die Klänge der Installation zu produzieren. Welches Klangobjekt benutzt wird ist abhängig vom Zugtyp, wobei die Zugtypen so gewählt wurden, dass sie zur Art der Reise der jeweiligen Persona passen. In der Ausstellung hängen außerdem Beschreibungen zu den Personae mit den entsprechenden Farben der Züge in der Visualisierung, um den Bezug zwischen Persona und gehörtem Klang herzustellen. Im Folgenden soll beschrieben werden, welche Eigenschaften die Personae haben und welche Funktionen diese Eigenschaften in ihrem Verhältnis zu einem Besucher erfüllen:

- **Gabriel** ist das äquivalent zu dem mehrmals in der Woche Kurzstrecken zurücklegenden Zugreisenden. Er ist 35 Jahre alt und hat eine Festanstellung in einem mittelgroßen IT Betrieb ohne den Wunsch diese Position in absehbarer Zeit zu verlassen. Er beginnt und beendet seine Arbeit pünktlich, da ihm sein Familienleben mit seiner Frau und seinen zwei Töchtern, genau wie seine Mitgliedschaft im lokalen Motorcrossverein sehr wichtig sind. Die Zeit im Zug, zu und von seinem Arbeitsplatz, nutzt er gerne um in Ruhe nachzudenken. 
  
  Sein Alter, ist ein Alter in dem die meisten Menschen ein mehr oder weniger gefestigtes Leben haben. Dieses Gefühl der Sicherheit wird weiterhin durch seine Vereinsmitgliedschaft, die Festanstellung und das intakte Familienleben gestärkt. In ihm kann der eigene Wunsch nach Sicherheit gespiegelt werden, jedoch nicht in einem Maße, dass sich einschränkend anfühlen soll. 
  
  Er steht bei seinem Arbeitgeber für seine Interessen ein, auch wenn das bedeutet, dass er bei der nächsten Unternehmensverkleinerung eine höhere Gefahr läuft seine Anstellung zu verlieren. Außerdem geht er dem nicht ungefährlichen Hobby des Motorcross' nach. Das Motorcross fahren und seine Position als Informatiker machen seine Liebe zur Technik klar. Dies soll auf ein Ästhetikverständnis hinweisen welches sich zum Großteil auf geordnete Schönheit bezieht, jedoch nicht ausschließlich, da Motorcross als Freiluftsport auch auf eine Naturverbundenheit hinweist.
- **Julia** entspricht der Zugreisenden, welche ca. einmal in der Woche 1-2 Stunden unterwegs ist. Sie ist 23 Jahre alt und strebt aktuell ihren Bachelor in Literaturwissenschaften an. Ihr Partner ist aktuell im Praxissemester, etwas über eine Stunde entfernt von ihrem Wohnort, weswegen sie am Wochenende häufig den Zug nimmt. Sie wohnt auch nur 2 Zugstunden von ihren Eltern entfernt, welche sie meist in der vorlesungsfreien Zeit, aber auch an manchen Wochenenden, besucht. 
  
  Sie weiß noch nicht wohin sie nach ihrem Bachelor gehen wird. Ein Master in der gleichen Fachrichtung wäre eine Option aber sie interessiert sich neben Literaturwissenschaften für eine Ausbildung in Layout und Graphikdesign, da sie in ihrer Freizeit gerne zeichnet. Die Wahl des weiterführenden Ausbildungsortes wird erschwert dadurch, dass sie sowohl in der Nähe ihrer Famillie als auch ihres Partners bleiben möchte. 
  
  Der Besucher kann in ihr die Unsicherheit von Wandel und einer ungewissen Zukunft nachempfinden. Jedoch steht sie gleichzeitig für den Wunsch nach Selbstverwirklichung, welche in dieser Unsicherheit ermöglicht ist und durch ihre künstlerischen Anlagen in Literatur und Bildender Kunst verkörpert wird. Die Angst etwas zu verpassen und alle Bereiche des Lebens miteinander zu vereinen, ohne dabei viele Kompromisse eingehen zu müssen, findet sich in ihrem Abwägen über den neuen Wohnort in Abhängigkeit von Ausbildung, Familie und Liebe wieder. (*FOMO*: vgl. \ref{befragungen} [*Befragungen*](#befragungen) S. \pageref{befragungen}) 
- **Leonie** fährt nur ca. alle 6-8 Wochen mit dem Zug, aber dafür 3-5 Stunden lang. Mit 28 Jahren ist sie seit ca. 2 Jahren im Berufsalltag als Messtechnikerin. Sie genießt nach dem Ende einer langen Beziehung die neu gefundene Unabhängigkeit und ist für ihren Job in eine neue Stadt, weit weg von ihrer Heimat gezogen. Sie übernimmt in ihrem Job viel Verantwortung und eine Beförderung ist aktuell in Sicht. Obwohl sie viel Zeit im Büro verbringt, hilft sie am Wochenende auf einem Gnadenhof, da sie schon von klein auf eine besondere Bindung zu Tieren empfindet. 

  In einer Männerdomäne arbeitend ist sie mit unkooperativen männlichen Vorgesetzten konfrontiert weswegen sie sehr widerstandsfähig ist. Dadurch verkörpert sie die Stärke, auch unter schweren Umständen entschlossen voranzuschreiten. In dieser Entschlossenheit und Unabhängigkeit spiegelt sie jedoch auch die Gefühle der Einsamkeit der Besucher wider. In Leonies Arbeit auf dem Gnadenhof können Besucher sich in ihrem Selbstverständnis als vielseitig und manchmal missverstanden wiederfinden.

### Raumkonzept/Aufbau

#### Nutzung von Graphik {#nutzung-von-graphik}

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{visualisierungp5}
\break
\caption{Screenshot eines Ausschnittes der Visualisierung in p5: Züge in Farben nach Typ, Haltestellen grau und Cursor weiß umrandet.}
\end{figure}

Die Graphische Darstellung hat die Aufgabe das Interaktionsprinzip deutlich zu machen und Hinweise auf den Inhalt zu geben. Grundsätzlich gibt es 4 verschiedene visuelle Elemente. 

Haltestellen werden als graue Kreisflächen dargestellt die so auf der Visualisierung verteilt sind, wie sie auf einer Landkarte zu finden wären. Sie sind grau gehalten und liegen auf der hintersten Ebene um darzustellen, dass sie Teil des Hintergrundes sind.

Züge sind je nachdem welcher Persona bzw. welchem Zugtypen sie zugeordnet sind farbige Kreisflächen in grün für Gabriel/regional, rot für Julia/überregional und pink für Leonie/Fernverkehr. Sie bewegen sich in Echtzeit über die Karte.

Dann gibt es den Cursor, welcher als weiße Kreisfläche dargestellt wird. Die Kreisfläche ist durchsichtig und liegt auf der obersten Ebene um zu kommunizieren, dass sie nicht Teil der Karte selbst ist sondern nur der Beobachter dieser Karte. Der Rand ist blickdicht, um eine Lupe anzumuten. Er ist außerdem größer als die anderen Elemente, um seine Wichtigkeit darzustellen. Er wird vom Nutzer durch einen Trackball gesteuert.

Berührt der Cursor einen der Züge erscheint das vierte Element: ein wachsender und immer durchsichtiger werdender Kreis der von dem berührten Zug ausgeht. Die Animation dauert so lange wie die Sonification die von diesem Zug ausgeht, damit der Nutzer sehen kann, von welchen Zügen aktuell Klänge produziert werden. Zusätzlich ist auf diesem Kreis ein Textelement, welches den Start- und Endbahnhof des Zuges anzeigt. Dies wurde hinzugefügt um einen Hinweis darauf zu geben, dass es sich bei den Kreisflächen um Züge handelt. Da die Installation die Haltestellen des Bundeslandes nutzt in dem sie ausgestellt wird, können Nutzer evtl. Zugverbindungen entdecken die sie schon genutzt haben, wodurch sie einen persönlichen Bezug zu dem Kunstwerk herstellen können.

Zusätzlich zu der graphischen Darstellung leuchtet der Trackball in der Farbe des zuletzt berührten Zuges, um den Bezug zwischen Trackball und Graphik zu verdeutlichen.

#### Nutzung von Druck

Abgesehen von der Graphischen Darstellung auf der Projektionsfläche gibt es noch die drei Kurzbeschreibungen der Personae, welche mit einem Bild und einer Kreisfläche der korrespondieren Zugfarbe versehen sind und im Ausstellungsraum ausgehangen werden. (vgl. \ref{personabeschreibungen} [*Personabeschreibungen*](#personabeschreibungen) S. \pageref{personabeschreibungen}ff)

Die Bilder wurden von Befragten zur Verfügung gestellt, welche ursprünglich als Vorlage für die Personae dienten. In der Entwicklung der Personae bewegten sich die Personae jedoch sehr weit weg von der ursprünglichen Inspiration. 

Um auf die Ursprünge der Personae anzuspielen und einen Persönlichen Bezug zu den Personae zu behalten wurden Namen und Bilder der anfänglichen Vorlagen übernommen.

![Bild für Gabriel [@arlauskas_selfie_2015]](Graphics/gabriel.jpg){ height=256px }

Bei der Auswahl der Bilder wurde beachtet, dass diese zu der später entwickelten Persona passten. Für Gabriel wurde ein Selfie verwendet, welches bei einer Zugfahrt aufgenommen wurde. Die Umgebung des Zuges und die unprofessionelle Aufnahmetechnik, mit dem Kamerawinkel unter der Augenhöhe deutet auf ein nicht inszeniertes im Alltag aufgenommenes Bild hin. Dies Spiegelt die von ihm empfundene Einförmigkeit des Reisens wider. 



![Bild für Julia [@stoll_portraitfoto_2020]](Graphics/julia.jpeg){ height=256px }



Für Julia wurde ein inszenierteres Bild verwendet, da sie in der Unsicherheit, die durch ihre ungewisse Zukunft verursacht ist, darauf Bedacht ist, ihre Außenwirkung zu kontrollieren. Außerdem trägt sie eine Brille um die Assoziation zu Lesen und in der Konsequenz auch zu Literaturwissenschaften herzustellen. Auch dieses Bild wurde mit einer Handykamera aufgenommen, um einem Social Media Post anzumuten, was ihren Status als Studierende glaubhaft macht.

Bei dem Bild welches Leonie darstellt, wurde ein Bild gewählt welches von einer Professionellen Fotografin aufgenommen wurde. Es könnte auch als Bewerbungsfoto fungieren, und weckt somit beim Besucher die Assoziation der Professionalität und der damit verbundenen Entschlossenheit der Persona.

![Bild für Leonie [@dollak_portraitfoto_2020]](Graphics/leonie.jpg){ height=256px }

#### Nutzung von Lautsprechern {#nutzung-von-lautsprechern}

Für die Lautsprecherkonfiguration wurde ein quadrophonischer Aufbau mit Subwoofer gewählt. Ein klassisches 5.1 Setup wurde in Erwägung gezogen. Da aber die Richtung der Graphischen Darstellung nur optisch im Vordergrund steht und keine besonderen akustischen Impulse als von der Darstellung kommend verstanden werden sollen, ist eine gleichwertige Behandlung aller Raumrichtungen sinnvoll Center Lautsprecher hätte keine Funktion. Aus diesem Grund wird ein symmetrischer Lautsprecheraufbau genutzt.

Der Subwoofer wird hinter der Leinwand versteckt um das Aussehen der Installation minimalistisch zu halten. Die Positionierung des Subwoofers ist akustisch nicht so kritisch wie die anderen Lautsprecher der Installation da dieser nur Frequenzen unter 80 Hz wiedergeben soll und diese kaum zu orten sind. [@hall_musikalische_2008 S. 305]

Die Klänge die von den Zügen erzeugt werden, sollen so um den interagierenden Besucher verteilt sein wie sie in der Visualisierung um den Cursor verteilt sind. Die visuelle Darstellung befindet sich jedoch in der YZ Ebene, welche von einem Surround Aufbau nicht dargestellt werden kann, da dafür Höheninformationen benötigt würden. Aus diesem Grund wird die räumliche Verteilung von der YZ Ebene auf der Darstellung um 90° vom Besucher weg gekippt um in der YX Ebene zu liegen.

So wird der Quadrophonische Aufbau genutzt um die YX Ebene akustisch zu füllen. Es werden basierend auf der Distanz der Züge zum Cursor außerdem Halleffekte genutzt um die Illusion eines akustischen Raumes zu verbessern. 

#### Raum als Medium für Schall

Außerhalb des virtuellen akustischen Raumes gibt es allerdings noch den echten akustischen Raum in dem die Installation aufgebaut wird. Es wurde bei der Gestaltung der Klänge darauf geachtet keine starken Impulse zu verwenden sondern eher langsam anschwellende Klänge um die Aufmerksamkeit des Besuchers nicht auf die Raumakustik zu lenken. Trotzdem spielt der Ausstellungsraum eine Rolle da es keine Lautsprecher außerhalb der Ebene gibt, womit alle Höheninformationen von den Reflexionen des Ausstellungsraumes kommen. Aus diesem Grund gibt es im Soundprocessing die Möglichkeit den virtuellen Hallraum anzupassen. Die Einstellung soll so vorgenommen werden, dass sich der virtuelle Hall und der Raumhall bestmöglich ähneln, damit die Installation sich nahtlos in den Ausstellungsraum einfügt. 

Dieses unauffällige Einfügen in den Raum ist gewünscht, da die Installation in ihrer Funktion als Sound Map einen Bezug zu ihrer Umgebung herstellen soll. So wie die dargestellte Karte sich an das Bundesland des Ausstellungsortes anpasst, soll sich der akustische Raum, der durch sie erzeugt wird, an den Ausstellungsraum anpassen.


