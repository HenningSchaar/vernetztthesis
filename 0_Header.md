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
csl: hennings-bachelorarbeit-samac-et-al.csl
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
\includegraphics[height=\paperheight, keepaspectratio]{Graphics/Titelblatt.pdf}
\end{center}
\newpage

\cleardoublepage

\begin{center}
\includegraphics[height=\paperheight, keepaspectratio]{Graphics/Erklaerung.pdf}
\end{center} 
\newpage

\cleardoublepage

\section*{Zusammenfassung}

Reisen mit dem Zug ist für viele Menschen Alltag. Ob das Pendeln zur Arbeit, der Besuch von Familie oder das Leben in einer Fernbeziehung. So erweitert sich der Raum, in dem das Leben erfahren wird, sowohl um die Infrastruktur des Netzes, also Bahnhöfe, Zugstrecken und Fahrzeuge, als auch um die Orte, welche besucht werden.

*Vernetzt* ist eine Raumklanginstallation hergestellt aus Klängen von Zügen, algorithmisch komponiert aus Echtzeitdaten des Schienenverkehrs. Es handelt sich dabei um eine interaktive Installation, welche mit Webscraping Daten sammelt, diese dann in *p5js* visuell aufbereitet und in der nodebasierten Entwicklungsumgebung *Max* sonifiziert.

Die vorliegende Arbeit beschreibt den Entstehungsprozess der Arbeit und ihre Umsetzung und wie das Arbeiten mit Klängen und Echtzeitdaten in ihr kunsthistorisch einzuordnen ist.

Schließlich wurde durch eine Befragung ermittelt inwiefern die Klanginstallation erfolgreich darin ist, die Gefühle, welche mit Zugreisen verbunden sind, zu kommunizieren und akustische Qualitäten zu vermitteln.

\section*{Abstract}

Travelling by train is a part of everyday life for a lot of people, whether they are commuting, visiting family or are living in a long distance relationship. Thus, the space in which life is experienced is expanded by the railway system, encompassing stations, railway lines and vehicles, as well as the places visited.

*Vernetzt* is an interactive sound art installation using train sounds manipulated by real time data of rail traffic. It uses webscraping to collect data, *p5.js* to produce visuals and *Max*, a node based development environment, for its sonification.

The present work describes the development process of the installation, its implementation and how the methods used fit into the art historical context. 

Finally an evaluation of how the installation is perceived in terms of emotion and sound quality is presented. 

\newpage



\tableofcontents
\newpage
\cleardoublepage 
\listoffigures

\cleardoublepage

\justifying 

\pagenumbering{arabic}

\pagestyle{fancy}
\fancyhf{}
\renewcommand{\footrulewidth}{0.2pt}
\renewcommand{\headrulewidth}{0pt}
\fancyfoot[LO]{\changefont Henning Schaar | Hochschule Darmstadt | 2020}
\fancyfoot[RO,LE]{\thepage}

\onecolumn 
