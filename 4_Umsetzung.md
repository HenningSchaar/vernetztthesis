# Umsetzung {#umsetzung}

## Entwicklung der Klangobjekte

### Aufgabe der Klangästhetik {#aufgabe-der-klangaesthetik}

Zunächst sollte ein Bezug zu den Geräuschen des Zugverkehrs zu erkennen sein, um auf das akustische Gedächtnis der Besucher zuzugreifen. Das charakteristische Schleifen der Räder auf den Gleisen ist ein Klang der sowohl durch aufnahmen von eben diesem Geräusch als auch durch die Auswahl von Synthetische klängen in die resultierenden Klangobjekte eingebaut wurde. Auch der typische immer wieder ansteigende Sinus-ähnliche Ton welcher von Elektromotoren von modernen Zügen produziert wird wurde emuliert, indem die Frequenz eines Trägertons mit Sägezahn-LFOs moduliert wurde.

Als LFOs (*Low Frequency Oscillators*) werden niederfrequente Signale bezeichnet, die meist genutzt werden um Frequenz, Filter oder andere Parameter eines Synthesizers zu steuern. [@raffaseder_audiodesign_2010 S. 219] 

Schnellere LFOs welche die Frequenz von breitbandigen Trägersignalen modulieren wurden genutzt, um das Vorbeischnellen von Zugwagons und den dabei entstehenden Dopplereffekt zu emulieren. 

Der Dopplereffekt beschreibt ein Phänomen, bei welchem sich die Frequenz einer Welle erhöht, wenn der emittierende Körper sich auf den Beobachter zubewegt, da die Welle gestaucht wird. Das Gegenteil ist der Fall bei Körpern die sich von einem Beobachter wegbewegen. [@schmuser_theoretische_2013 S. 147] Im Falle von Zugwagons, ist dies insbesondere bei Güterzügen bemerkbar, da genug Abstand zwischen den einzelnen Wagons besteht, sodass sie als einzelne akustische Körper wahrgenommen werden können.

Außer dem Bezug auf die Geräusche des öffentlichen Personenverkehrs sollte noch Bezug zu den persönlichen Reiseerfahrungen des Künstlers hergestellt werden. Hierfür wurden die meistgefahrenen Zugstrecken aus allen bisherigen Wohnort gesammelt und die Distanzen dieser Zugstrecken wurden ermittelt.

Zum einen wurden die Distanzen in Kilometern als Frequenzen für Oszillatoren verwendet um je Wohnort eine Art Akkord zu bauen, welche als Toncluster zu beschreiben wären, bei welchem jeder Ton einer Zugstrecke entsprach. Da diese Klänge an sich sehr Dissonant und unangenehm sind, und das nicht der zu erzielende Effekt war, wurde entschieden einen Granularsynthesizer zu verwenden, um auf der Grundlage dieser Toncluster verschiedenste Klangmaterialen herzustellen, welche in der Erstellung der fertigen Klangobjekte verwendet wurden.

Bei Granularsynthese handelt es sich um eine Arbeitsweise mit Klang, bei der kurze Segmente von Klang, sogenannte *Grains*, generiert und manipuliert werden. [@lazzarini_computer_2017 S. 201] Für Granularsynthese kann eine vorhandene Tondatei genutzt werden um daraus eben diese *Grains* zu gewinnen und diese dann auf unterschiedliche weise wieder zusammenzusetzen. Die hierfür verwendete Software war das Open Source Projekt *Dronebox* welches in *Max* zu verwenden ist. [@ohland_jonasohlanddronebox-max_2019]

Weiterhin wurden die Distanzen genutzt um FM Synthese zu betreiben. Es wurden Netzwerke von sich gegenseitig in der Frequenz modulierende Oszillatoren angelegt, welche dann mit den Distanzen in Kilometern als Frequenzen betrieben wurden. Der letzte Stand des hierfür verwendeten Maxpatches findet sich im digitalen Anhang.

### Bezug auf Personae

Für Gabriel wurde ein Klangobjekt entwickelt, welches im vergleich zu den anderen beiden viel tonalen Inhalt hat. Diese Entscheidung wurde getroffen, da Tonalität ein wichtiger Grundbestandteil der musikalischen Hörgewohnheiten der Besucher ist, und Gabriel für Sicherheit stehen soll. Der Inspiration für den harmonischen und melodischen Inhalt lag eine Aussage einer Befragten zu Grunde. Sie meinte, der öffentliche Personennahverkehr sei für sie ähnlich wie ein Wartezimmer, dies bezog sie darauf, dass es sich dabei um einen geteilten Raum handelt, in welchem man sich kurz genug aufhält um nicht dem Bedürfnis nachzugehen sich einzurichten, sondern eventuelle Unannehmlichkeiten aushält. 

Auf die Unannehmlichkeiten des Reisens bezog sich auch Brian Eno in seiner Reihe von Stücken *Music for Airports* von 1978. Es sollte an Flughäfen gespielt werden um die Irritation der Reisenden zu verringern, die Musik sollte dabei nicht aufdringlich, aber dennoch interessant sein.[@peter_h_lisius_music_2010 S. 633] Dies wird durch ein geringes Tempo und minimale harmonische Bewegung bei jedoch vielseitiger akustischer Textur erreicht. 

Von dem melodischen Material von *Music for Airports* inspirierte Melodien wurden geschrieben und durch Verlangsamung und Oktavverschiebungen variiert um den Tonalen Inhalt des Klangobjektes für Gabriel herzustellen. Das Klangobjekt für Gabriel beinhaltet wenig texturelle Variation, um die Einförmigkeit seiner Nutzung von Zügen widerzuspiegeln.

Bei dem Klangobjekt für Julia handelt es sich ausschließlich um Klänge die durch die im Kapitel \ref{aufgabe-der-klangaesthetik} [*Aufgabe der Klangästhetik*](#aufgabe-der-klangaesthetik) beschriebene FM-Synthese entwickelt wurden. Der persönliche Bezug, der durch die Nutzung der Reisedistanzen hergestellt wird, ist in diesem Fall angebracht, da der Künstler in seiner persönlichen Erfahrung meist zu weiten Teilen mit dieser Persona übereinstimmte. Es wurden schnelle Wechsel in Klangfarbe und Intensität genutzt um die Umstellung zwischen den verschieden gelebten sozialen Umfeldern der von ihr besuchten Orte darzustellen.

Das Klangobjekt welches für Leonie steht, wurde durch die in \ref{aufgabe-der-klangaesthetik} [*Aufgabe der Klangästhetik*](#aufgabe-der-klangaesthetik) beschriebene Granularsynthese der Toncluster aus Zugdistanzen sowie der Tonaufnahmen von Zügen hergestellt. Der persönliche Bezug durch die Zugdistanzen ist hier abgeschwächt durch die weitere Verarbeitung durch die Granularsynthese und das Vermischen mit akustischen Quellen, da der Künstler nur teilweise Übereinstimmungen mit dieser Persona erlebt hat. Auch in diesem Klangobjekt wurden abrupte Wechsel verwendet, jedoch mit längeren Spannungsaufbauten vor diesen. Die Spannungsaufbauten wurden durch immer stärker werdende Überlagerung verschiedener Texturen und ansteigender Lautstärke erreicht. Dieses Vorgehen wurde gewählt um die durch Leonie erlebte Ereignishaftigkeit ihrer Reisen abzubilden. 

### Dramaturgie

Dem dramaturgischen Verlauf der Klangobjekte liegen die jeweiligen Wahrnehmungen der den Personae zugeordneten Befragten des Reiseverlaufs zugrunde.

Für Gabriel wurde eine im zeitlichen Verlauf nur minimal variierende Entwicklung gewählt um die Zeitlich als homogen empfundene Reise abzubilden.

Für Julia wurde das Klangobjekt in fünf Teile eingeteilt. (vgl. \ref{befragungen} [*Befragungen*](#befragungen) S. \pageref{befragungen}) Die einzelnen Etappen wurden nach dem Empfinden des Künstlers durch Klänge widergespiegelt, wobei für als unangenehm empfundene Emotionen eher Obertonreiche, also kratzende, und für als angenehme Empfundene Emotionen eher tonale Klänge verwendet wurden. Töne mit Stark variierendem Grundton im Bassbereich wurden verwendet um Bedrohliche Gefühle darzustellen.

Für das Klangobjekt, welches Leonies Reise darstellt, wurde eine ähnliche Einteilung vorgenommen, wobei der Mittlere teil, eher Ruhig gehalten wurde um den in den Befragungen als angenehm empfundenen Mittelteil wiederzugeben. Die Übergänge zwischen den Teilen wurden weniger Abrupt gestaltet um die Verteilung der Gefühle über die längere Dauer der Reise einzufangen.

## Webscraping & Node.js {#nodejs}

*Node.js* ist eine Javascript Runtime, welche die V8 Javascript engine von Google Chrome nutzt. [@openjs_foundation_about_nodate] Es ist also eine Umgebung um Javascript auszuführen, ähnlich wie ein Webbrowser Javascript ausführen würde. *Node.js* hat jedoch den Vorteil nicht den overhead eines Browsers zu haben und mit vielen zusätzlichen Funktionen ausgestattet zu sein, welche in klassischen Browserumgebungen nicht verfügbar sind. Zudem haben *Node.js* Anwendungen im Gegensatz zu im Browser ausgeführtem Javascript sehr viel weniger Einschränkungen, zum Beispiel um auf Netzwerkhardware und Festplatte des Host-Rechners zuzugreifen.

Das Webscraping besteht aus drei Node.js Programmen: *getStrecken.js*, *extractStations.js*. und *scraper.js* wobei die ersten beiden zur Erstellung der für den Betrieb erforderlichen Daten zuständig sind und letzteres im Betrieb der Installation genutzt wird.

*getStrecken.js* wird manuell mit einer Liste von URLs der Strecken auf *Zugfinder.de* welche in der Installation angezeigt werden sollen bespielt. Für jeden dieser URLs macht das Programm ein HTTP Request aus welchem es mit Hilfe des *dom-parsers* die Namen der Haltestellen sowie deren Position auf der Darstellung entnimmt und die um diese Parameter ergänzte Liste unter *strecken.json* speichert. Die Position der Haltestellen ist wichtig für die spätere Darstellung in *p5js*, da dadurch die relative Position der Züge zu den Haltestellen berechnet wird. *dom-parser* ist eine Erweiterung für Node.js um HTML, die Markup Sprache mit der *Zugfinder.de* arbeitet, effektiv zu parsen. [@ershov-konst_pseudonym_dom-parser_nodate]

*extractStation.js* hat die Funktion aus dem durch *getStrecken.js* angefertigten Datensatz eine Karte herzustellen. Es sammelt alle darin enthaltenen Haltestellen in einer Liste, entfernt die Duplikate und formatiert aus dieser neuen Liste einen API Request an die Google Distance Matrix API, welche die geographischen Koordinaten dieser Haltestellen zurückgibt. Diese Koordinaten werden in der Liste der in *strecken.json* vorkommenden Haltestellen ergänzt und als *map.json* abgespeichert.

*scraper.js* hat die Aufgabe die Positionen der Züge zu ermitteln welche sich auf den in der URL-Liste enthaltenen Strecken befinden. Dieses Programm musste kurze Zeit vor Fertigstellen der Arbeit implementiert werden, da sich die Infrastruktur der Seite *Zugfinder.de* am 24. Januar auf entscheidende Weise änderte. Die Streckenansicht auf *Zugfinder.de* funktioniert durch ein JSON-File welches dynamisch, also nach Laden des eigentlichen Inhaltes der Seite, geladen wird. Vor dem 24. Januar war es möglich auf diese JSON Datei mit einem einfachen HTTP-request, also dem aufrufen eines Links, zuzugreifen. Mutmaßlich aus Sicherheitsgründen implementierte der Entwickler jedoch dann eine Einschränkung, die zur Folge hat, dass nur von der besuchten Streckenansicht ein *XMLHttpRequest* (kurz *XHR*) genutzt werden kann um das erforderliche JSON zu laden. *XHRs*  sind von Microsoft entwickelte Javascript Objekte, die den Zugriff auf Daten über eine URL erlauben und vereinfachen. [@mozilla_xmlhttprequest_nodate] In diesem Fall wird jedoch nur eine vollständige Datei zurückgegeben wenn dieses *XHR* einen Cookie enthält welcher beim Besuchen der Seite generiert wird.

Cookies sind Textdateien welche entweder vom Server an den Browser gesendet, oder von einem im Browser ausgeführten Javascript generiert werden. Sie werden unter anderem genutzt um Nutzer zu identifizieren und Statusinformationen über den Besuch der Website zu speichern. [@barth_abartheecsberkeleyedu_http_nodate] Auf der Seite *Zugfinder.de* werden die Cookies vom Server generiert, weswegen der einfachste Weg weiterhin auf das zugrundeliegende JSON zuzugreifen die Nutzung eines headless Browsers, in diesem Fall *Puppeteer*, ist. 

*Puppeteer* ist eine *Node.js* Library, welche die Automatisierung der Nutzung eines Browsers über Javascript Befehle erlaubt. Sie führt dafür eine oder mehrere Instanzen des Browsers *Chromium* ohne die Darstellung eines Graphischen User Interfaces (kurz *GUI*) aus. Das ausführen ohne GUI bezeichnet man als *headless operation*. [@noauthor_puppeteerpuppeteer_2020]

Das Programm öffnet eine Instanz von *Chromium*, besucht die Streckenansicht und wartet dann darauf, dass das *XHR* für die benötigten Zugpositionen gesendet wird. Wenn die Datei heruntergeladen ist, wird sie dem *Node.js* Prozess zugeführt und von dort an den p5js Prozess gesendet (vgl. \ref{webscraping-kommunikation} [*Kommunikation*](#webscraping-kommunikation) S. \pageref{webscraping-kommunikation}) . Dieser Prozess wird für alle in der Liste enthaltenen Zugstrecken durchgeführt, um dann wieder am Anfang der zu beginnen.

## p5js {#p5}

p5.js ist eine Javascript Library mit dem Ziel, Programmieren für Künstler, Designer und andere zugänglicher zu machen. Es nutzt einen sogenannten *Sketch* in dem alle in der *draw* Funktion enthaltenen Operationen einmal pro angezeigtem Bild ausgeführt werden. [@mccarthy_home_nodate] Dies kann genutzt werden um Animationen in einem *HTML* Dokument darzustellen.

### Kommunikation {#webscraping-kommunikation}

Für die Kommunikation zu den anderen Prozessen wird *Open Sound Control* (kurz *OSC*) verwendet. *OSC* ist ein offenes Nachrichten Protokoll, welches ursprünglich im UC Berkeley Center for New Music and Audio Technology (CNMAT) entwickelt wurde. Es wurde speziell für die Kommunikation zwischen Computern, Synthesizern und anderen Multimediageräten entwickelt. [@wright_open_2002]

Die Wahl viel auf OSC, da es sowohl für *p5js*, als auch für *Node.js* und *Max* einfach zu nutzende implementierungen dieses Standards gibt. Für das versenden der *OSC* Nachrichten wird meist UDP verwendet.

*UDP* (*User Datagram Protocol*) ist ein Netzwerk-Nachrichtenprotokoll, welches auf Handshakes verzichtet und deswegen einfach zu nutzen ist. [@fairhurst_unicast_2008] Allerdings bedeutet dieser Verzicht auf Bestätigungen auch, dass *UDP* kein besonders sicheres Netzwerkprotokoll ist, weswegen Browser das Senden und Empfangen von *UDP* nicht erlauben. *p5js* läuft allerdings innerhalb eines Browsers, weswegen eine sogenannte Bridge zum Einsatz kam. Diese gibt die Empfangenen *UDP* Pakete über *Socket.io*, einer beliebten *Node.js* zu Browser Kommunikationsschnittstelle[@socketio_socketio_2020], an den Browser weiter.

Die hierfür genutzte Bridge, *p5js-osc*[@kogan_genekoganp5js-osc_2020] wurde speziell für *p5js* entwickelt und war deshalb leicht in das Programm einzubinden. 

### Visualisierung  {#programmbeschreibung}

Die Visualisierung besteht wie in \ref{nutzung-von-graphik} [*Nutzung von Graphik*](#nutzung-von-graphik) (S. \pageref{nutzung-von-graphik}) beschrieben aus vier Elementen. 

Die Haltestellen werden dargestellt, indem die geographischen Koordinaten aus der Datei *map.json* auf die Größe des anzeigenden Bildschirms skaliert werden. Es wird dann pro berechnetem Punkt auf dem Sketch eine graue Kreisfläche gezeichnet.

Die Züge werden dargestellt, indem die Relative Distanz zu der letzten und der nächsten Haltestelle auf der Darstellung der Strecke auf *Zugfinder.de* berechnet wird. Diese beiden Haltestellen werden dann auf der Darstellung der Karte gesucht und es wird eine Kreisfläche zwischen diesen, relativ zu der berechneten Position, gezeichnet. Die Kreisfläche wird je nach Zugtyp gefärbt, um den Bezug zu den Personae herzustellen.

Der Cursor ist eine Kreisfläche welche an der Stelle gezeichnet wird, an der sich die Maus gerade befindet. Befindet sich der Cursor an der gleichen Stelle wie einer der Züge, so werden die Informationen über diesen Zug per *OSC* an das Soundprocessing in *Max* gesendet und eine Animation eines größer werdenden Kreises um den dargestellten Zug wird ausgelöst. Zudem werden der letzte und der nächste Halt des Zuges weiß eingefärbt.

## Max {#max}

*Max* (ehemals *Max/MSP*) ist eine graphische Entwicklungsumgebung für Signalverarbeitung und Multimedia welche genutzt werden kann um flexible Echtzeitsignalverarbeitung zu implementieren. Außer der Signalverarbeitung hat *Max* viele weitere Funktionen, welche in der graphischen Umgebung als *Objects* bezeichnet werden, die unter anderem Logikoperationen, Textverarbeitung und vieles mehr erlauben. [@cycling_74_max_nodate]

### Kommunikation

Max erhält von dem *p5js* Prozess über *OSC* Daten über Züge welche vom Benutzer berührt werden. Diese Daten umfassen eine einmalige ID zur eindeutigen Identifikation des Zugs, Zugnamen, Zugtyp und den aktuellen Fortschritt in der Gesamtreise des Zuges.

Zudem erhält Max zum verteilen der Züge im Surroundfeld einmal pro Frame die zum Cursor relative Position aller relevanten Züge als Liste.

Aus *Max*, werden außerdem Farbinformationen per MIDI an einen Microcontroller gesendet um die Farbe einer LED zu steuern. (vgl. \ref{komponenten} [*Komponenten*](#komponenten) S. \pageref{komponenten}).

### Steuerung

Der Zugtyp bzw. die Zuordnung zu den Personae entscheidet, welche Tondatei abgespielt wird. Für das Abspielen der Tondatei gibt es Wiedergabeinstanzen welche jeweils aus Tonwiedergabe, Panning, also Verteilung im Surroundfeld, Halleffekt und tonaler Effekteinheit bestehen (vgl. \ref{signal-processing} [*Signal Processing*](#signal-processing) S. \pageref{signal-processing}).

Die Tonwiedergabe wird durch die Berührung des Zuges ausgelöst und durch den Fortschritt des Zuges gesteuert. Je nachdem wie weit der Zug in seiner Reise fortgeschritten ist, wird ein Ausschnitt der Tondatei abgespielt, welcher sich relativ zur Länge der Tondatei an der selben Stelle befindet.

Das positionieren der virtuellen Schallquelle im Surroundfeld geschieht anhand der durch die von *p5js* übergebenen relativen Positionen der Züge zum Cursor. Die einmaligen Zug IDs in der Positionsliste werden mit dem aktuell in der Wiedergabeinstanz gespielten Zug verglichen, und Falls es eine Übereinstimmung gibt, wird der Winkel zur Positionierung und der Abstand zur Lautstärkeregulierung genutzt, um die Platzierung in einem virtuellen akustischen Raum zu simulieren.

Der Abstand des Zugs wird weiterhin genutzt um den Anteil des Halleffektes zu bestimmen. Ist der Zug weiter weg, so wird der Hallanteil größer. Auch dies soll das Verhalten von realen Schallquellen in einem Raum simulieren.

### Weiteres Signal Processing {#signal-processing}

Die Tonale Effekteinheit wird unabhängig von den Speziellen Zugdaten gesteuert. Sie besteht aus 8 Bandpassfiltern, dessen Frequenzen über *MIDI* gesteuert werden.

Bandpassfilter erlauben den Durchlass eines Teils des Spektrums eines Signals, zentriert um eine Frequenz, während der Rest des Spektrums gedämpft wird. [@lazzarini_computer_2017 S. 88] Bei einem breitbandigen Signal wird diese Zentrale Frequenz als tonaler Ankerpunkt empfunden. So kann wenn Frequenzen, welche Noten entsprechen, genutzt werden durch das Filtern eines breitbandigen Signals die Illusion von gespielten Melodien erzeugt werden.

Dieser Effekt wird hier genutzt um Akkordfolgen zu spielen. Die Akkordfolgen beziehen sich auf die Personae, und wurden passend zu deren assoziierten Emotionen ausgewählt. 

Bei Gabriel ist der Anteil des Tonalen Effekt am Stärksten, bei Julia und Leonie wird er nur als Verzierung verwendet.

Zusätzlich werden Global alle Laustsprechersignale Monosummiert um an den Subwoofer gesendet zu werden.

## Hardware

### Komponenten {#komponenten}

Der Aufbau der Installation Besteht aus folgenden Elementen:

| Stk. | Bezeichnung                                    | Kabeltyp         |
| ---- | ---------------------------------------------- | ---------------- |
| 4    | Full range Monitore auf Stativen               | XLR zu TRS       |
| 1    | Subwoofer                                      | XLR zu TRS       |
| 1    | Full HD Beamer                                 | HDMI             |
| 1    | Leinwand 168*200cm                             | -                |
| 1    | Trackball                                      | USB-A            |
| 1    | Teensy mit RGB-LED                             | mikro USB-B zu A |
| 1    | MDF Möbel, 100cm höhe                          | -                |
| 1    | Focusrite Scarlett 18i20 Audiointerface        | USB-C zu A       |
| 1    | Mac Mini mit *Max*, *p5js* und Internetzugriff | -                |

### Aufbau

\begin{figure}[h]
\centering
\includegraphics[width=12cm]{raumlayout}
\break
\caption{Raumlayout mit Lautsprecherpositionen}
\end{figure}

Der Mac Mini ist das Herz der Installation. Auf ihm Laufen die Software Komponenten, die für Webscraping, Visualisierung und Sonification zuständig sind. An ihn angeschlossen sind über HDMI der Beamer welcher die Darstellung auf die Leinwand projiziert. Über USB sind drei weitere Geräte angeschlossen.

Einerseits das Audiointerface, dass die digitalen Audiosignale des Rechners in Analoge Signale umwandelt und diese an die Lautsprecher weitergibt. Zweitens der Trackball welcher dem Nutzer erlaubt die Cursorposition zu verändern.

Als drittes ist ein Teensy angeschlossen. Teensy ist eine Art Microcontroller welcher in der Lage ist über USB als MIDI gerät angeschlossen zu werden. Für ihn kann Software in einer modifizierten Version der Programmiersprache C entwickelt werden. [@pjrc_teensy_nodate] In diesem Fall läuft lediglich eine Software auf dem Controller, welche empfangene MIDI Control Change Nachrichten in Spannungen für den Roten, Grünen und Blauen Anteil einer RGB-LED umwandeln. 

Das MIDI (*Musical Instrument Digital Interface*) Protokoll ist ein Standard zur Übertragung von musikalischen Informationen. [@midi_manufacturers_association_complete_1996 S. 1] MIDI Control Messages sind eine besondere Art von MIDI Nachricht welche bei der Kontrolle von Synthesizern für alle nicht im MIDI Protokoll spezifizierten Funktionen genutzt werden kann. [@midi_manufacturers_association_complete_1996 S. 4ff]

