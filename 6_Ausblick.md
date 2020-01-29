# Ausblick

## Mögliche Verbesserungen

Wie in [*Gewonnene Erkentnnisse*](#gewonnene-erkenntnisse)  (\ref{gewonnene-erkenntnisse} erwähnt ist der Prozess, mit welchem die Züge durch sound processing räumlich werden noch verbesserungswürdig. Eine Option wäre die Nutzung eines Surround-Halls, welcher einen Raum simuliert. In der aktuellen Implementierung hat jeder Zug seinen eigenen Mono-Hall, welcher auf das Ausgangssignal der Tonwiedergabe gemischt wird. Würde ein Surround-Hall verwendet würden die Klänge auch aus anderen Richtungen reflektiert werde, was eher einem echten akustischen Raum entspräche.

Außerdem könnte die Strukturierung der Software vereinfacht werden. *extractStation.js* und *getStrecken.js* könnten zu einem Prozess zusammengefasst werden, um die Vorbereitung neuer Streckengebiete zu vereinfachen.

Außerdem könnte der *p5js-osc* Prozess in *scraper.js* eingebaut werden, so dass es nur einen *Node.js* Prozess, einen *Max* Prozess und eine *p5js* Instanz gäbe. Außerdem könnten Dinge die aktuell in *p5js*  und in *Max* parallel stattfinden, wie die Zuordnung des Zugtyps zu den Personae, Zentralisiert in dem *Node.js* Prozess stattfinden. Dies würde die Flexibilität für zukünftige Änderungen erhöhen und den Betrieb und die Fehlersuche vereinfachen.

## Mögliche Erweiterungen

Wie in \ref{nutzung-von-lautsprechern} [*Nutzung von Lautsprechern*](#nutzung-von-lautsprechern) S. \pageref{nutzung-von-lautsprechern} beschrieben, müssen Benutzer die Visualisierung von der ZY um 90° in die XY Ebene kippen um die akustische Ortung zu verstehen. Ein direkterer Bezug zwischen Spatialisierung der Klänge und Visualisierung könnte hergestellt werden, indem die Visualisierung auf den Boden projiziert würde. In diesem Fall würde sich jedoch anbieten von einer Cursorsteuerung zu einer Steuerung durch die Position des Besuchers auf der Projektionsfläche überzugehen. Dies könnte durch Druckempfindliche Bodenplatten erreicht werden. [@voisen_designing_2013] 

Wenn das Kunstwerk dann aber weiterhin mit Lautsprechern funktionieren sollte, würde die Spatialisierung leiden, sobald sich mehrere Benutzer auf der Installationsfläche bewegen. Dies könnte zum Beispiel durch die Nutzung von Kopfhörern, mit Drahtlosen Empfängern gelöst werden. So würde jeder Benutzer eine auf seine Position in der Installation angepasste Spatialisierung erhalten. 

Andererseits könnte die Benutzung von Lautsprechern die Chance für Besucher bieten, aus der Herstellung von Klängen durch das Berühren von Zügen einen kollaborativen Prozess zu machen, was unter Umständen wichtiger sein könnte, als eine korrekte Spatialisierung.

## Mögliche Ausstellungsorte



# Danksagungen

\pagebreak

# Literaturverzeichnis 