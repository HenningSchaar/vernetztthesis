

# Konzeption

Wie in der [Einleitung](#einleitung)  (\ref{#einleitung}) erwähnt, stand am Anfang der Arbeit an der Installation, der Wunsch das Schienennetz als akustischen Raum darzustellen. Hieraus entstand die Idee, diese Vertonung anhand der Gefühle von Zugreisenden zu orientieren. Es wurde für die Entwicklung ein experimenteller Ansatz gewählt, da sich die Komposition an bereits gegebene Inputs, den Zugverkehr an dem gewählten Ort, anpassen muss.

## Experimente und deren Ergebnisse

### Ansätze mit Kontaktmikrofonen

\begin{figure}[h]
\centering
\includegraphics[width=7cm]{mikroAnSchiene}
\break
\caption{Kontaktmikrofon an stillgelegtem Gleis}
\end{figure}

Zunächst bestand der Wunsch die Installation ähnlich wie [Bill Fontanas](#bill-fontana) (\ref{#bill-fontana}) Klangskulpturen zu gestalten. Es sollten portable Stationen entwickelt werden welche mit einem Kontaktmikrofon das Akustische Signal der Schiene über LTE das Audiosignal an einen Ausstellungsraum per Livestream übertragen sollten. Dafür wurde folgende Hardware geplant:

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

### Ansätze mit Webcrawling

### Ansätze zur Visualisierung

## Finales Konzept

### Motivation

#### Befragungen

#### Persönliche Beweggründe

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

