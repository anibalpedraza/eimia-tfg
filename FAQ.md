# Preguntas frecuentes

## ¿Qué archivos debo editar?

Normalmente solo `main.tex`, `preambulo/Resumen.tex`, los capítulos de `caps/`
y `bibliography.bib`. La dedicatoria y los agradecimientos tienen sus propios
archivos en `preambulo/`.

`packagesTFG.tex` contiene el formato interno y no necesita cambios para
redactar un TFG.

## ¿Dónde cambio los datos de portada?

En el bloque `DATOS DEL TFG` de `main.tex`. Solo contiene:
`\titulo`, `\tituloIngles`, `\autor`, `\titulacion`, `\director`,
`\codirector` y `\fechaEntrega`.

## ¿Cómo indico que no hay codirección?

Deja el campo vacío:

```tex
\codirector{}
```

La segunda persona no aparecerá en la portada.

## ¿Cómo introduzco la fecha?

Usa el número de mes y el año:

```tex
\fechaEntrega{9}{2026}
```

En este caso, por ejemplo, la plantilla mostrará `septiembre` en español y `September` en inglés.

## ¿Cómo cambio el idioma principal?

Al principio de `main.tex`, sustituye `\spanishtrue` por `\spanishfalse`. El
resumen en español y el abstract en inglés se mantienen en ambos casos.

## ¿Cómo elimino partes opcionales?

Comenta en `main.tex` la línea de la dedicatoria o de los agradecimientos. Si no
necesitas anexos, comenta el bloque indicado desde `\appendix` hasta el último
`\include`.

## ¿Cómo añado un capítulo o un anexo?

Crea un archivo en `caps/` y añádelo en la posición deseada:

```tex
\include{./caps/06_Discusion}
```

Los capítulos situados después de `\appendix` se numeran con letras.

## ¿Cómo compilo la memoria?

Aunque la forma de uso más sencilla es [**Abrir la plantilla de TFG de la EIMIA en Overleaf**](https://www.overleaf.com/latex/templates/plantilla-tfg-eimia-uclm/dbsmjdfbdjkg), también puedes crear una copia de este repositorio y compilarlo con una distribución como [TeX Live](https://www.tug.org/texlive/) o
[MiKTeX](https://miktex.org/).

Desde la terminal, la forma recomendada es:

```powershell
latexmk -pdf -interaction=nonstopmode main.tex
```

Si no dispones de `latexmk`, ejecuta:

```powershell
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

También puedes compilar sin utilizar la terminal, en [Texmaker](https://www.xm1math.net/texmaker/), [TeXstudio](https://www.texstudio.org/) o [Visual Studio Code con LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop).

## ¿Por qué aparecen signos `??`?

Suele faltar alguna pasada de compilación o hay una clave/referencia mal escrita. Comprueba
que los `\label{...}` y sus `\ref{...}` coincidan, así como los `\cite{...}` con su entrada en el fichero `.bib`, y vuelve
a compilar.

## ¿Cómo añado figuras y tablas?

Guarda las imágenes en `figs/`. Toda figura o tabla debe estar citada en el
texto y, si no es propia, debe indicar su fuente y respetar su licencia.

## ¿Cómo acorto un título en un índice?

Usa el argumento opcional de capítulos o pies:

```tex
\chapter[Título corto]{Título largo que aparece en el documento}
\caption[Título corto]{Título largo de la figura o tabla}
```

## ¿Cómo se gestionan las referencias?

Añade las entradas a `bibliography.bib` y cítalas con `\cite{clave}`. La
plantilla utiliza `apacite` para generar las referencias bibliográficas con el formato correcto automáticamente.

## ¿Qué reviso antes del depósito?

Consulta siempre la
[página oficial de TFG de la EIMIA](https://www.uclm.es/es/ciudad-real/Eimia/Docencia/TFG).
La plantilla genera la memoria, pero los formularios, plazos y demás
entregables externos pueden cambiar.
