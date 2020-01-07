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
bibliography: ZoteroLibrary.bib
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
 \usepackage{graphicx}
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
...

\pagenumbering{gobble}

\begin{center}
\includegraphics[height=0.95\textheight, keepaspectratio]{Graphics/Titelblatt.pdf}
\end{center}
\newpage
\cleardoublepage

\section*{Abstract}

Hier Abstract Text
\newpage

\cleardoublepage

\tableofcontents
\newpage

\listoftables
\newpage

\listoffigures
\newpage

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
