# Informe EVI. 6 — Auditoría socioambiental de la Mina Marlin

Informe académico en LaTeX sobre la auditoría socioambiental de la **Mina Marlin**
(Montana Exploradora de Guatemala, S.A. / Goldcorp), departamento de San Marcos, Guatemala.

**Formato:** académico basado en IEEE (`IEEEtran`), a dos columnas.
**Compilador:** pdfLaTeX · **Motor bibliográfico:** Biber · **Estilo de citas:** IEEE numérico.

## Integrantes

| # | Apellidos y nombres | Secciones a cargo | Archivo `.tex` |
|---|---|---|---|
| 1 | Brandon Gabriel Quispe Tapia | Marco teórico y normativo | `secciones/03_marco_teorico.tex` |
| 2 | Cristian Ivan Huanca Constancia | Unidad minera, mapas y figuras | `secciones/04_unidad_minera.tex` |
| 3 | Rudy Javier Mollocondo Mollocondo | Descripción de la auditoría | `secciones/05_auditoria.tex` |
| 4 | Britt Lizardo Gemio Mamani | Hallazgos y análisis crítico | `secciones/06_hallazgos.tex`, `secciones/07_analisis_critico.tex` |
| — | _(por asignar)_ | Plan PHVA, conclusiones y bibliografía | `secciones/08_plan_mejora.tex`, `secciones/09_conclusiones.tex`, `referencias.bib` |

> **Verificar:** la lista de integrantes se tomó del trabajo de Perforación y Voladura,
> asumiendo que el grupo es el mismo. El reparto de secciones es una propuesta. Ambas
> cosas se corrigen en `config/portada.tex` y en esta tabla.

**Curso y docente:** pendientes de rellenar en `config/portada.tex`.

## El caso

La Mina Marlin operó entre 2005 y 2017 produciendo 2,3 millones de onzas de oro y
63 millones de onzas de plata. Se implantó en territorio de los pueblos maya-mam y
maya-sipakapense, lo que generó un conflicto socioambiental de escala internacional.

El documento que se analiza es la ***Human Rights Assessment of Goldcorp's Marlin Mine***
(On Common Ground Consultants, 2010): una evaluación independiente de más de 200 páginas
que examinó siete ejes —consulta, ambiente, trabajo, adquisición de tierras, inversión
económica y social, seguridad y acceso a remediación— y que constituye el eje del informe.

Toda la investigación, las fuentes verificadas y las advertencias sobre datos están en
[`docs/bitacora_decisiones.md`](docs/bitacora_decisiones.md). La estructura de contenidos
está en [`docs/estructura_informe_y_setup_latex.md`](docs/estructura_informe_y_setup_latex.md).

> **Léelas antes de escribir.** La bitácora contiene advertencias sobre datos que circulan
> mezclados en fuentes secundarias; en particular, **no atribuir a Marlin cifras que
> corresponden a la mina Constancia, en Perú**.

## Estado de la redacción

Se redacta **capítulo por capítulo**, no de una vez.

| Capítulo | Estado |
|---|---|
| 3. Marco teórico y normativo | ✅ Redactado (~3.100 palabras) |
| 1, 2, 4–11 | ⬜ Esqueleto con `% TODO` y objetivos de extensión |

## Cómo escribir en este formato

**La jerarquía de títulos va un nivel por encima de lo habitual.** En los archivos de
`secciones/` se escribe:

| Escribes | Resultado | Aspecto |
|---|---|---|
| `\chapter{}` | Capítulo (nivel 1) | negrita, grande, centrado |
| `\section{}` | Sección (nivel 2) | negrita, tamaño intermedio |
| `\subsection{}` | Subsección (nivel 3) | cursiva, sin negrita |
| `\subsubsection{}` | Sub-subsección (nivel 4) | cursiva, en línea |

Lo hace el adaptador de jerarquía de `config/preambulo.tex`. No lo cambies.

**Tablas y figuras.** El preámbulo convierte automáticamente `table` en `table*` y
`figure` en `figure*`, de modo que abarcan las dos columnas. Por eso `[H]` y `\centering`
no hacen falta. Para el ancho hay `\anchotabla` (0,85 del texto).

**`longtable` no funciona a dos columnas.** Las tablas que se parten en varias páginas
—la matriz completa de no conformidades y la cronología— van en los **anexos**, donde
`main.tex` vuelve a una columna con `\onecolumn`. En el cuerpo del informe van extractos
de una página.

## Compilación local

Requiere una distribución de LaTeX (MiKTeX o TeX Live) con pdfLaTeX y Biber.

```bash
latexmk -pdf main.tex
```

Para limpiar los temporales:

```bash
latexmk -c
```

Secuencia manual equivalente:

```bash
pdflatex main.tex && biber main && pdflatex main.tex && pdflatex main.tex
```

## Trabajo en Overleaf

1. **New Project → Upload Project** y sube el `.zip` del proyecto (o
   **Import from GitHub** si tienes plan de pago; la integración con GitHub **no está
   disponible en la cuenta gratuita**).
2. *Menu → Settings → Compiler:* **pdfLaTeX**.
3. *Menu → Settings → TeX Live version:* la más reciente.
4. El motor bibliográfico es **Biber**; Overleaf lo detecta al ver `biblatex`.

> ⚠️ **Overleaf y GitHub no se sincronizan solos**, ni siquiera con plan de pago: hay que
> pulsar *Menu → GitHub → Push/Pull* manualmente en ambos sentidos.
>
> **Regla para el grupo:** decidan una única fuente de verdad. O todos en Overleaf y una
> sola persona hace commit al cerrar la sesión, o todos en local con Git. Lo que rompe
> cosas es que unos editen en Overleaf y otros en local a la vez.

## Reglas de trabajo en grupo

- **Cada quien toca solo su archivo `.tex`.** Es lo que evita los conflictos de merge.
- `main.tex`, `config/preambulo.tex` y `config/portada.tex` los modifica **una sola persona**.
- El resumen, la introducción y los objetivos se cierran **al final**, entre todos.
- Las referencias se añaden a `referencias.bib`, nunca escritas a mano en el texto.
- No borres las etiquetas `\label{sec:...}`: hay capítulos que se remiten entre sí.

## Antes de entregar

1. Busca `\pendiente` y `% TODO` en todo el proyecto; no debe quedar ninguno.
   En `config/comandos.tex` hay una línea comentada que hace desaparecer del PDF los
   marcadores `\pendiente`.
2. Comenta el `\nocite{*}` de `main.tex`: fuerza que aparezcan **todas** las entradas de
   la bibliografía aunque no estén citadas. Es cómodo mientras se redacta, pero la lista
   final debe contener solo lo efectivamente citado.
3. Revisa los **21 avisos `VERIFICAR`** de `referencias.bib`. Los tres críticos son
   **COPAE**, **Rights Action** y la **tesis de la UNSA** (citada por su universidad en
   vez de por su autor).

## Nota sobre el estilo de citas

El formato usa **citas numéricas IEEE** (`[1]`, `[2]`), no APA 7 autor-año. Si el docente
exige APA 7, se cambia en un solo lugar —el bloque de `biblatex` de
`config/preambulo.tex`, que lleva las dos líneas alternativas comentadas—. El archivo
`referencias.bib` sirve para ambos estilos sin tocar nada.
