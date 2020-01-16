---
documentclass: article
classoption: 
- twoside
fontsize: 11pt
geometry:
- a4paper
- left=3cm
- right=3cm
- top=2cm
- bottom=2cm
- bindingoffset=0.5cm
bibliography: Meine Bibliothek.bib
csl: din-1505-2.csl
date: \today
header-includes: |
 \usepackage[T1]{fontenc}
 \usepackage{baskervillef}
 \usepackage[varqu,varl,var0]{inconsolata}
 \usepackage[scale=.95,type1]{cabin}
 \usepackage[baskerville,vvarbb]{newtxmath}
 \usepackage[cal=boondoxo]{mathalfa}
 \usepackage{blindtext}
 \usepackage[ngerman]{babel}
 \usepackage{ragged2e}
 \usepackage{tocloft}
 \usepackage[utf8]{inputenc}
 \usepackage[export]{adjustbox}
 \usepackage{graphicx}
 \graphicspath{ {Graphics/} }
 \usepackage[font=small,labelfont=bf]{caption}
 \usepackage[rightcaption]{sidecap}
 \usepackage[right]{eurosym}
 \usepackage{lmodern}
 \usepackage{fancyhdr}
 \usepackage{color}
 \usepackage{amssymb}
 \usepackage{mathtools}
 \usepackage{capt-of}
 \usepackage[german]{nomencl}
 \let\abbrev\nomenclature
 \newcommand{\changefont}{%
    \fontsize{9}{11}\selectfont}
 \usepackage{chngcntr}
 \counterwithin{figure}{section}
 \counterwithin{table}{section}
 \setcounter{tocdepth}{4}
 \usepackage[onehalfspacing]{setspace}
...

\pagenumbering{gobble}

\begin{center}
\includegraphics[height=0.95\textheight, keepaspectratio]{Graphics/Titelblatt.pdf}
\end{center}
\newpage
\cleardoublepage

\section*{Zusammenfassung}

Reisen mit dem Zug ist für viele Menschen Alltag. Ob das Pendeln zur Arbeit, der Besuch von Familie oder das Leben in einer Fernbeziehung. So erweitert sich der Raum, in dem das Leben erfahren wird, sowohl um die Infrastruktur des Netzes, also Bahnhöfe, Zugstrecken und Fahrzeuge, als auch um die Orte, welche besucht werden.

*Vernetzt* ist eine Raumklanginstallation hergestellt aus Klängen von Zügen, algorithmisch komponiert aus Echtzeitdaten des Schienenverkehrs. Es handelt sich dabei um eine interaktive Installation welche mit Webcrawling Daten sammelt, diese dann in *p5js* visuell aufbereitet und in der nodebasierten Entwicklungsumgebung *Max* sonifiziert.

Die vorliegende Arbeit beschreibt den Entstehungsprozess der Arbeit und wie das Arbeiten mit Klängen und Echtzeitdaten in der Installation Kunsthistorisch einzuordnen ist.

Schließlich wird durch eine Befragung ermittelt inwiefern die Klanginstallation erfolgreich darin ist, die Gefühle, welche mit Zugreisen verbunden sind, zu kommunizieren und die Erfahrung des Schienennetzes als akustischen Raum zu vermitteln. 

\section*{Abstract}

\blindtext

\newpage



\tableofcontents
\newpage

\listoftables
\newpage

\listoffigures
\newpage

\justifying 

\pagenumbering{arabic}

\pagestyle{fancy}
\fancyhf{}
\renewcommand{\footrulewidth}{0.2pt}
\renewcommand{\headrulewidth}{0pt}
\fancyfoot[LO]{\changefont Henning Schaar | Hochschule Darmstadt | 2020}
\fancyfoot[RO,LE]{\thepage}

\onecolumn 
