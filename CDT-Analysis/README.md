# CDT-Templates/Templates/Analisis

Plantilla para documentar el Análisis de Requerimeintos de proyectos pequeños.

Diseñada para los estudiantes de [ESCOM](http://www.escom.ipn.mx/), pero puede ser aprovechada por cualquier interesado en documentar sus requerimientos utilizando LaTeX como herramienta.

Todos los archivos .tex conforman el ejemplo a seguir para ver el uso de los comandos.

Para compilar el documento se debe usar TeX Live 2026, que proporciona el estilo
bibliográfico `IEEEtran.bst`:

```bash
export PATH="$HOME/texlive/2026/bin/x86_64-linux:$PATH"
cd CDT-Analysis
pdflatex -interaction=nonstopmode -halt-on-error proyecto.tex
bibtex proyecto
pdflatex -interaction=nonstopmode -halt-on-error proyecto.tex
pdflatex -interaction=nonstopmode -halt-on-error proyecto.tex
```

Las referencias se ordenan según su primera aparición porque
`6Referencias.tex` utiliza `IEEEtran` y no emplea `\nocite{*}`. Las referencias
que aún no estén citadas no se muestran en la bibliografía hasta asociarlas con
una cita en el contenido.