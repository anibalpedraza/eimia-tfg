# Plantilla de TFG de la EIMIA-UCLM

Plantilla en LaTeX para preparar el Trabajo Fin de Grado de la
[Escuela de Ingeniería Minera e Industrial de Almadén](https://www.uclm.es/es/ciudad-real/Eimia)
(EIMIA), Universidad de Castilla-La Mancha.

Puede utilizarse localmente con una distribución como
[TeX Live](https://www.tug.org/texlive/) o [MiKTeX](https://miktex.org/), y
también en línea mediante [Overleaf](https://www.overleaf.com/). `main.tex`
funciona como ejemplo mínimo y guía de uso.

## Inicio rápido

Completa este único bloque al principio de `main.tex`:

```tex
\titulo{TÍTULO DEL TRABAJO FIN DE GRADO}
\tituloIngles{FINAL DEGREE PROJECT TITLE}
\autor{NOMBRE Y APELLIDOS}
\titulacion{GRADO EN INGENIERÍA MINERA Y ENERGÉTICA}
\director{NOMBRE Y APELLIDOS DEL DIRECTOR O DIRECTORA}
\codirector{NOMBRE Y APELLIDOS DEL CODIRECTOR O CODIRECTORA} % Déjalo vacío si no existe codirección.
\fechaEntrega{9}{2026} % Mes (1-12) y año.
```

El título se reutiliza automáticamente en portada, resumen y metadatos. La
universidad, el centro, la ciudad y el tipo de documento ya están configurados
para la EIMIA. El nombre del mes se genera en español e inglés.

Después:

1. Sustituye el resumen, el abstract y las palabras clave en
   `preambulo/Resumen.tex`.
2. Reemplaza el contenido de ejemplo de los capítulos de `caps/`.
3. Añade tus referencias a `bibliography.bib`.
4. Comenta en `main.tex` la dedicatoria, los agradecimientos o el bloque de
   anexos si no los necesitas.

No es necesario modificar `packagesTFG.tex` salvo que quieras cambiar el
formato interno de la plantilla.

## Estructura

- `README.md`: inicio rápido, estructura y opciones de compilación.
- [`FAQ.md`](FAQ.md): respuestas a las dudas habituales.
- `main.tex`: datos y orden del documento.
- `preambulo/`: portada, créditos, dedicatoria, índices, agradecimientos,
  resumen y abstract.
- `caps/`: capítulos y anexo de ejemplo.
- `figs/`: imágenes y logotipos.
- `bibliography.bib`: bibliografía BibTeX.
- `packagesTFG.tex`: configuración tipográfica.

## Compilación

La plantilla está preparada para compilarse con pdfLaTeX y BibTeX. Puedes
elegir cualquiera de estas opciones.

### Desde la terminal

La forma recomendada es dejar que `latexmk` ejecute automáticamente las
pasadas necesarias:

```powershell
latexmk -pdf -interaction=nonstopmode main.tex
```

Si no tienes `latexmk`, ejecuta la secuencia manual:

```powershell
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### En Overleaf

Sube todos los archivos y carpetas del proyecto a
[Overleaf](https://www.overleaf.com/), selecciona `main.tex` como documento
principal y usa pdfLaTeX como compilador. No necesitas instalar LaTeX en tu
equipo.

### Con Texmaker u otro editor local

Abre `main.tex` y establécelo como documento maestro o raíz del proyecto. En
[Texmaker](https://www.xm1math.net/texmaker/),
[TeXstudio](https://www.texstudio.org/) o
[Visual Studio Code con LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
puedes usar una receta basada en `latexmk` o configurar la compilación rápida
como pdfLaTeX, BibTeX y dos pasadas finales de pdfLaTeX.

Si aparecen referencias `??`, vuelve a compilar. Si persiste un error, revisa
primero el mensaje correspondiente en `main.log`.

## Licencia y citas

La plantilla se distribuye bajo
[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).
La licencia no se extiende automáticamente al contenido académico añadido por
cada estudiante ni a marcas, logotipos o materiales de terceros.

Referencia de esta adaptación —URL y DOI pendientes hasta su publicación—:

```bibtex
@misc{pedraza2026plantillaEIMIA,
  author = {Pedraza Dorado, Aníbal},
  title  = {Plantilla de TFG de la EIMIA-UCLM},
  year   = {2026},
  url    = {https://github.com/ORGANIZACION/REPOSITORIO},
  doi    = {10.XXXX/XXXX}
}
```

Plantilla original:

```bibtex
@misc{salido2019plantillaTFG,
  author = {Salido Tercero, Jesús},
  title  = {Plantilla guía de TFG de la ESI-UCLM},
  year   = {2019},
  url    = {https://github.com/JesusSalido/TFG_ESI_UCLM},
  doi    = {10.5281/zenodo.4561708}
}
```

Enlaces pendientes de completar cuando se publique esta adaptación:

- Repositorio: `https://github.com/ORGANIZACION/REPOSITORIO`
- Overleaf: `https://www.overleaf.com/latex/templates/NOMBRE/IDENTIFICADOR`
- DOI: `https://doi.org/10.XXXX/XXXX`
