# vernetztthesis
The LATEX files for the thesis paper discussing the sound art installation "Vernetzt". 

Copy following command into terminal to build PDF.

```bash
pandoc -F pandoc-citeproc --csl chicago-author-date-footnotes.csl -s 0_Header.md 1_Einleitung.md 2_RechercheZurKunsthistorischenEinordnung.md  3_Konzeption.md  4_Umsetzung.md  5_Evaluierung.md  6_Ausblick.md  -N -o testexport.pdf
```

Dependencies:

- Pandoc
- Latex
- PDF-Latex
- Pandoc-Citeproc