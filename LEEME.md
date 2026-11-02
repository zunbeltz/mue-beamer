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

`\mufootercenter{..}` cambia el texto central del pie (por defecto «Mondragon Unibertsitatea», o «MIK S. Coop.» con `brand=mik`) y `\muthankstext{..}` el agradecimiento (por defecto solo la frase del idioma `lang`: «Eskerrik asko», «Muchas gracias» o «Thank you»; para las tres, `\muthankstext{Eskerrik asko\\Muchas gracias\\Thank you}`).

## Formas de la marca

`\muforma[opciones]{forma}` dibuja una forma en la diapositiva, `\muformabg[opciones]{forma}` la pone en el fondo (siempre detrás del texto, se llame donde se llame). Con `\muforma` llámala antes del texto si quieres que quede detrás.

Formas: `circulo`, `arco`, `cuenco`, `barra`, `gancho`, `corte`. Posición y tamaño en % de la página, con el origen arriba a la izquierda.

| Opción | Valores | Por defecto |
|---|---|---|
| `x`, `y` | posición del punto de anclaje | `50`, `50` |
| `w` | ancho | `20` |
| `anchor` | ancla del dibujo (`center`, `north west`, `south east`...) | `center` |
| `color` | `accent`, `dark`, `deep`, `tint` (siguen la `palette`), `cta`, `white` | `accent` |
| `rot` | giro en grados, antihorario | `0` |
| `flip` | espeja horizontalmente | `false` |
| `opacity` | `0`..`1` | `1` |

```latex
\muformabg[color=tint,x=100,y=100,w=30,anchor=south east]{gancho}
\muforma[color=cta,x=88,y=30,w=5]{circulo}
```

Los PNG salen de `MU-sistema-diseno/formas` (círculo, arco, cuenco y barra corporativos, gancho 7467 y corte45 7467), recoloreados con los colores de cada paleta: `assets/formas/f-<forma>-<color>-<paleta>.png`.

Los recursos de `assets/` salen de `MU-sistema-diseno`. Duplicate tiene licencia de la universidad: no distribuyas la carpeta `fonts` fuera de MU sin confirmarlo con Comunicación.
