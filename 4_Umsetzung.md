# Umsetzung {#umsetzung}

## Entwicklung der Klangobjekte

### Aufgabe der Klangobjekte

Zunächst sollte ein Bezug zu den Geräuschen des Zugverkehrs zu erkennen sein, um einen Bezug zu dem akustischen Gedächtnis der Besucher herzustellen. Das charakteristische Schleifen der Räder auf den Gleisen ist ein Klang der sowohl durch aufnahmen von eben diesem Geräusch als auch durch die Auswahl von Synthetische klängen in die resultierenden Klangobjekte eingebaut wurde. Auch der typische immer wieder ansteigende Sinus-ähnliche Ton welcher von Elektromotoren von modernen Zügen produziert wird wurde durch Sägezahn LFOs welche eine die Frequenz eines Trägertons modulieren emuliert. Schnellere LFOs welche die Frequenz von breitbandigen Trägersignalen modulierten wurden genutzt um das Vorbeischnellen von Zugwagons und den dabei entstehenden Dopplereffekt zu emulieren. 

Der Dopplereffekt beschreibt ein Phänomen, bei welchem sich die Frequenz einer Welle erhöht, wenn der emittierende Körper sich auf den Beobachter zubewegt, da die Welle gestaucht wird. Das Gegenteil ist der Fall bei Körpern die sich von einem Beobachter wegbewegen. [@schmuser_theoretische_2013 S. 147] Im Falle von Zugwagons, ist dies insbesondere bei Güterzügen bemerkbar, da genug Abstand zwischen den einzelnen Wagons ist, dass sie als einzelne akustische Körper wahrgenommen werden können.

### Bezug auf Personae

### Dramaturgie

### Algorithmen & Klangästhetik

## Webscraping & P5js {#p5}

### Verwendete Datenquellen & APIs

Das Webscraping besteht aus zwei Node.js (vgl. \ref{ansaetze-mit-webscraping} [*Ansätze mit Webscraping*](#ansaetze-mit-webscraping) S. \pageref{ansaetze-mit-webscraping}) Programmen: *getStrecken.js* und *extractStations.js*.

*getStrecken.js* bekommt eine Liste mit URLs der Strecken auf *Zugfinder.de* welche in der Installation angezeigt werden sollen. Für jeden dieser URLs macht das Programm ein HTTP Request aus welchem es mit Hilfe des *dom-parsers* die Namen der Haltestellen sowie deren Position auf der Darstellung entnimmt und die um diese Parameter ergänzte Liste unter *strecken.json* speichert. Die Position der Haltestellen ist wichtig für die spätere Darstellung in *p5js*, da dadurch die relative Position der Züge zu den Haltestellen berechnet wird. *dom-parser* ist eine Erweiterung für Node.js um HTML, die Markup Sprache mit der *Zugfinder.de* arbeitet, effektiv zu parsen. [@ershov-konst_pseudonym_dom-parser_nodate]

*extractStation.js* hat die Funktion aus dem durch *getStrecken.js* angefertigten Datensatz eine Karte herzustellen. Es sammelt alle darin enthaltenen Haltestellen in einer Liste, entfernt die Duplikate und formatiert aus dieser neuen Liste einen API Request an die Google Distance Matrix API, welche die geographischen Koordinaten dieser Haltestellen zurückgibt. Diese Koordinaten werden in der Liste der in *strecken.json* vorkommenden Haltestellen ergänzt und als *map.json* abgespeichert.

### P5 Programmbeschreibung  {#p5-programmbeschreibung}

### Kommunikation {#webscraping-kommunikation}

UDP ist ein Netzwerk Nachrichtenprotokoll, welches auf Handshakes verzichtet und deswegen einfach zu nutzen ist [@fairhurst_unicast_2008]

## Max {#max}

### Kommunikation

### Steuerung

### Signal Processing

## Hardware

### Komponenten

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

Der Mac Mini ist das Herz der Installation. Auf ihm Laufen die beiden Software Komponenten, die jeweils für Webscraping+Visualisierung und Sonification zuständig sind. An ihn angeschlossen sind über HDMI der Beamer welcher die Darstellung auf die Leinwand projiziert. Über USB sind drei weitere Geräte angeschlossen.

Einerseits das Audiointerface, dass die digitalen Audiosignale des Rechners in Analoge Signale umwandelt und diese an die Lautsprecher weitergibt. Zweitens der Trackball welcher dem Nutzer erlaubt die Cursorposition zu verändern.

Als drittes ist ein Teensy angeschlossen. Teensy ist eine Art Microcontroller welcher in der Lage ist über USB als MIDI gerät angeschlossen zu werden. Für ihn kann Software in einer modifizierten Version der Programmiersprache C entwickelt werden. [@pjrc_teensy_nodate] In diesem Fall läuft lediglich eine Software auf dem Controller, welche empfangene MIDI Control Change Nachrichten in Spannungen für den Roten, Grünen und Blauen Anteil einer RGB-LED umwandeln. 

Das MIDI (*Musical Instrument Digital Interface*) Protokoll ist ein Standard zur Übertragung von musikalischen Informationen. [@midi_manufacturers_association_complete_1996 S. 1] MIDI Control Messages sind eine besondere Art von MIDI Nachricht welche bei der Kontrolle von Synthesizern für alle nicht im MIDI Protokoll spezifizierten Funktionen genutzt werden kann, sie hat eine Auflösung von 7 Bit. [@midi_manufacturers_association_complete_1996 S. 4ff]

### Aufbau

\begin{figure}[h]
\centering
\includegraphics[width=12cm]{raumlayout}
\break
\caption{Raumlayout mit Lautsprecherpositionen}
\end{figure}



