# Tema Beamer MU

Tema `MU` para la clase `beamer`, basado en la plantilla PPT 16:9 y el libro de marca de Mondragon Unibertsitatea.

## Uso

Compila con **LuaLaTeX** o **XeLaTeX** (Duplicate Sans/Slab, incluidas en `assets/fonts`). Con pdfLaTeX usa Helvetica como sustituto de Arial.

```latex
\documentclass[aspectratio=169]{beamer}
\usetheme[brand=enpresagintza,lang=eu]{MU}
\title{...} \subtitle{Facultad de Empresariales} \author{...} \date{...}
\begin{document}
\begin{frame}[plain]\titlepage\end{frame}
\sectionsubtitle{Subtítulo}   % opcional
\section{Introducción}        % genera la diapositiva de sección
\subsectionsubtitle{Subtítulo} % opcional
\subsection{Contexto}          % diapositiva de subsección (con subsectionpages=true)
\begin{frame}{Título}...\end{frame}
\mudestacado[Título]{«Cita»}{Texto de apoyo}
\muclosing{\textbf{Nombre}\\correo\\...}
\end{document}
```

Mira `ejemplo.tex`. Coloca `beamerthemeMU.sty` y `assets/` junto al documento (o define `\muassets` antes de `\usetheme`).

## Opciones

| Opción | Valores | Por defecto |
|---|---|---|
| `brand` | `mu`, `enpresagintza`, `profesionales`, `mik` | `mu` |
| `lang` | `eu`, `es` (logo de facultad); `en` solo con `brand=mik` | `eu` |
| `palette` | `mu`, `eps`, `huhezi`, `enpresagintza`, `prof` | `mu` |
| `font` | `sans` (institucional), `slab` (actividad) | `sans` |
| `weight` | `medium` (académico), `bold` (no académico) | `medium` |
| `sectionpages` | `true`, `false` | `true` |
| `subsectionpages` | `true`, `false` (diapositiva de subsección automática) | `false` |

`font` y `weight` aplican la matriz académico/institucional del libro de marca a los titulares.
**`brand=mik`** (endoso fuerte MU + facultad + MIK): el logotipo conjunto va a color arriba a la derecha en las transparencias, también arriba a la derecha en secciones y subsecciones, y en blanco (sin cápsula) arriba a la derecha sobre fondos oscuros (portada, destacado, contraportada). Úsalo en investigación, transferencia y proyectos de formación in company; no en formación reglada ni Formación Continua abierta. Ejemplo: `ejemplo-mik.tex`. Los logos transparentes (`-transparente`, a color) y en blanco (`-negativo`) de todas las variantes están en `assets/logos/mik/`.

`\mufootercenter{..}` cambia el texto central del pie y `\muthankstext{..}` el agradecimiento.

Los recursos de `assets/` salen de `MU-sistema-diseno`. Duplicate tiene licencia de la universidad: no distribuyas la carpeta `fonts` fuera de MU sin confirmarlo con Comunicación.
