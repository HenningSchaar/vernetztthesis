# Ausblick

## Mögliche Verbesserungen

Wie in \ref{gewonnene-erkenntnisse}  [*Gewonnene Erkentnnisse*](#gewonnene-erkenntnisse) (S. \pageref{gewonnene-erkenntnisse}) erwähnt ist der Prozess, mit welchem die Züge durch sound processing räumlich werden noch verbesserungswürdig. Eine Option wäre die Nutzung eines Surround-Halls, welcher einen Raum simuliert. In der aktuellen Implementierung hat jeder Zug seinen eigenen Mono-Hall, welcher auf das Ausgangssignal der Tonwiedergabe gemischt wird. Würde ein Surround-Hall verwendet, würden die Klänge auch aus anderen Richtungen reflektiert werden, was eher einem echten akustischen Raum entspräche.

Die Struktur der Softwarekomponenten könnte in Zukunft noch vereinfacht werden. *extractStation.js* und *getStrecken.js* könnten zu einem Prozess zusammengefasst werden, um die Vorbereitung neuer Streckengebiete zu vereinfachen. Außerdem könnte der *p5js-osc* Prozess in *scraper.js* eingebaut werden, so dass es nur einen *Node.js* Prozess, einen *Max* Prozess und eine *p5js* Instanz gäbe. Außerdem könnten Dinge die aktuell in *p5js*  und in *Max* parallel stattfinden, wie die Zuordnung des Zugtyps zu den Personae, zentralisiert in dem *Node.js* Prozess stattfinden. Dies würde die Flexibilität für zukünftige Änderungen erhöhen und den Betrieb und die Fehlersuche vereinfachen.

Zusätzlich wäre für weitere Ausstellungen der Installation wünschenswert, die Personabeschreibungen auf Hartschaumplatten drucken zu lassen. Dies würde der Installation ein professionelleres Erscheinungsbild geben. Auf eine vierte Hartschaumplatte könnte eine kurze Beschreibung der Funktionsweise und der inhaltlichen Hintergründe gegeben werden, um Besuchern, welche an dem genaueren Kontext des Kunstwerkes interessiert sind, die Möglichkeit zu geben, diesen zu erfahren.

## Mögliche Erweiterungen

Wie in \ref{nutzung-von-lautsprechern} [*Nutzung von Lautsprechern*](#nutzung-von-lautsprechern) (S. \pageref{nutzung-von-lautsprechern}) beschrieben, müssen Benutzer die Visualisierung von der ZY um 90° in die XY Ebene kippen um die akustische Ortung zu verstehen. Ein direkterer Bezug zwischen Spatialisierung der Klänge und Visualisierung könnte jedoch hergestellt werden, indem die Visualisierung auf den Boden projiziert würde. In diesem Fall würde sich jedoch anbieten von einer Cursorsteuerung zu einer Steuerung durch die Position des Besuchers auf der Projektionsfläche überzugehen. Dies könnte durch Druckempfindliche Bodenplatten erreicht werden. [@voisen_designing_2013] 

Wenn das Kunstwerk dann aber weiterhin mit Lautsprechern funktionieren sollte, würde die Spatialisierung leiden, sobald sich mehrere Benutzer auf der Installationsfläche bewegen. Dies könnte zum Beispiel durch die Nutzung von Kopfhörern mit Drahtlosen Empfängern gelöst werden. So würde jeder Benutzer eine auf seine Position in der Installation angepasste Spatialisierung erhalten. 

Andererseits könnte die Benutzung von Lautsprechern auch die Chance für Besucher bieten, aus der Herstellung von Klängen durch das Berühren von Zügen einen kollaborativen Prozess zu machen, was unter Umständen wertvoller sein könnte, als eine korrekte Spatialisierung.

# Danksagungen

Im Folgenden möchte ich mich bei allen Personen Bedanken, ohne die das Schreiben dieser Arbeit und die Entwicklung der Klanginstallation in dieser Form nicht möglich gewesen wäre. 

Großer Dank gilt meinem Betreuer Prof. Dr. Thorsten Greiner für seine hilfreichen Anregungen und seine weitreichende Unterstützung während des gesamten Vorbereitungs- und Betreuungszeitraums. Das Engagement welches mir entgegengebracht wurde war alles andere als selbstverständlich.

Ich bedanke mich außerdem herzlich bei meinem Kommilitonen Jonas Ohland, welcher meinen Code prüfte, die Arbeit Korrektur las und mich beim Bau der Hardware unterstützte.

Ebenso danke ich Christian Losert für Anregungen zum Inhalt der Installation und für die Unterstützung beim kreativen Schreiben. 

Besonderer Dank gilt auch Johannes Schubert, dem Entwickler von *Zugfinder.de*, ohne dessen Zugdaten die Umsetzung der Installation so nicht funktioniert hätte.

Auch die Teilnehmer*innen meiner Evaluierung und alle die an der Gestaltung der Veranstaltung, welche den Rahmen für diese bot, beteiligt waren, haben durch ihre Hilfsbereitschaft einen Wertvollen Beitrag zu meiner Bachelorarbeit geleistet.

Außerdem möchte ich mich bei Gabriel Arlauskas, Julia Stoll und Leonie Adam für das Bereitstellen privater Fotografien bedanken.

Letztlich richte ich auch ein Dankeschön an Felicitas Weber und Gundula Schaar für das Korrekturlesen der Arbeit sowie an Vincent Wikstroem für seine Anregungen über die Nutzung von druckempfindlichen Bodenplatten.

\newpage

\pagebreak



# Literaturverzeichnis 

<div id="refs"></div>
\newpage

# Anhang

## Fragebogen {#fragebogen}

![](Graphics/Evaluation.pdf){ width=\pagewidth }

\newpage

## Personabeschreibungen {#personabeschreibungen}

![](Graphics/gabriel.pdf){ width=\pagewidth }

\newpage

![](Graphics/julia.pdf){ width=\pagewidth }

\newpage

![](Graphics/leonie.pdf){ width=\pagewidth }

## Code

Der gesamte code für das Projekt sowie dieses Dokument selbst ist verfügbar unter [https://github.com/HenningSchaar/vernetzt.git](https://github.com/HenningSchaar/vernetzt.git). Dort werden auch alle zukünftigen aktualisierungen der Software zu finden sein. Um den Zustand eines der verlinkten Repositories zum Zeitpunkt der Abgabe zu sehen nutzen sie den jeweiligen Branch *published*.