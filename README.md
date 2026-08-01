# Informe EVI. 6 — Auditoría socioambiental de la Mina Marlin

Informe académico en LaTeX sobre la auditoría socioambiental de la **Mina Marlin**
(Montana Exploradora de Guatemala, S.A. / Goldcorp), departamento de San Marcos, Guatemala.

## Integrantes

| # | Apellidos y nombres | Código | Secciones a cargo | Archivo `.tex` |
|---|---|---|---|---|
| 1 | _(completar)_ | | Marco teórico y normativo | `secciones/03_marco_teorico.tex` |
| 2 | _(completar)_ | | Unidad minera, mapas y figuras | `secciones/04_unidad_minera.tex` |
| 3 | _(completar)_ | | Descripción de la auditoría | `secciones/05_auditoria.tex` |
| 4 | _(completar)_ | | Hallazgos y análisis crítico | `secciones/06_hallazgos.tex`, `secciones/07_analisis_critico.tex` |
| 5 | _(completar)_ | | Plan PHVA, conclusiones y bibliografía | `secciones/08_plan_mejora.tex`, `secciones/09_conclusiones.tex`, `referencias.bib` |

**Docente:** _(completar)_ · **Curso:** _(completar)_ · **Ciudad y año:** Puno, 2026

## El caso

La Mina Marlin operó entre 2005 y 2017 produciendo 2,3 millones de onzas de oro y
63 millones de onzas de plata. Se implantó en territorio de los pueblos maya-mam y
maya-sipakapense, lo que generó un conflicto socioambiental de escala internacional.

El documento que se analiza es la ***Human Rights Assessment of Goldcorp's Marlin Mine***
(On Common Ground Consultants, 2010): una auditoría independiente de más de 200 páginas
que evaluó siete ejes —consulta, ambiente, trabajo, adquisición de tierras, inversión
económica y social, seguridad y acceso a remediación— y que constituye el eje del informe.

Toda la investigación, las fuentes verificadas y las advertencias sobre datos están en
[`docs/bitacora_decisiones.md`](docs/bitacora_decisiones.md). La estructura detallada del
informe está en [`docs/estructura_informe_y_setup_latex.md`](docs/estructura_informe_y_setup_latex.md).

> **Léelas antes de escribir.** La bitácora contiene advertencias específicas sobre datos
> que circulan mezclados en fuentes secundarias (en particular: no atribuir a Marlin cifras
> que corresponden a la mina Constancia, en Perú).

## Compilación local

Requiere una distribución de LaTeX (MiKTeX o TeX Live) con **pdfLaTeX** y **Biber**.

```bash
latexmk -pdf main.tex
```

Para limpiar los archivos temporales:

```bash
latexmk -c
```

Si `latexmk` no está disponible, la secuencia manual es:

```bash
pdflatex main.tex && biber main && pdflatex main.tex && pdflatex main.tex
```

## Trabajo en Overleaf

1. **New Project → Import from GitHub → `trabajo_auditoria`**.
2. En *Menu → Settings*, fija el compilador en **pdfLaTeX**.
3. En *Menu → Bibliography*, verifica que el motor sea **Biber** (Overleaf lo detecta solo
   al ver `biblatex`, pero conviene comprobarlo).
4. Comparte el proyecto con el resto del grupo para editar en paralelo.

> ⚠️ **Overleaf y GitHub no se sincronizan solos.** Hay que pulsar *Menu → GitHub → Push/Pull*
> manualmente. Si el grupo edita durante días sin sincronizar, el repositorio se queda atrás.
>
> ⚠️ La sincronización con GitHub es una **función de pago** de Overleaf. Sin plan premium,
> las alternativas son trabajar solo en Overleaf y subir el `.zip` periódicamente, o editar
> en local con VS Code + LaTeX Workshop y usar Git normalmente.

## Reglas de trabajo en grupo

- **Cada quien toca solo su archivo `.tex`.** Es la única forma de evitar conflictos de merge.
- `main.tex` y `config/preambulo.tex` los modifica **una sola persona**.
- El resumen ejecutivo, la introducción y los objetivos se cierran **al final**, entre todos.
- Las referencias se añaden a `referencias.bib`, nunca escritas a mano en el texto.
- Antes de entregar: busca `\pendiente` y `% TODO` en todo el proyecto; no debe quedar ninguno.
  En `config/comandos.tex` hay una línea comentada que hace desaparecer los marcadores
  `\pendiente` del PDF final.

## Estado de la bibliografía

`referencias.bib` está organizado en seis bloques. Los bloques 1 a 5 corresponden a la
bibliografía verificada de la bitácora. **El bloque 6 contiene entradas incompletas a
propósito**: fuentes que el informe necesita pero cuyos datos (año, autor o URL) no constan
en la bitácora. Busca `VERIFICAR` en el archivo y complétalas o elimínalas antes de entregar.

Mientras se redacta, `main.tex` incluye un `\nocite{*}` que fuerza la aparición de todas las
referencias en el PDF. **Hay que comentarlo antes de la entrega final**, porque APA exige que
la lista contenga únicamente las obras efectivamente citadas.

## Tipografía

El preámbulo usa `mathptmx` (Times New Roman) y `\onehalfspacing` (interlineado 1,5).
Ambos se cambian en un solo lugar: `config/preambulo.tex`. Si la universidad exigiera Arial,
hay que pasar el compilador a **XeLaTeX** y usar `fontspec` con `\setmainfont{Arial}`.
