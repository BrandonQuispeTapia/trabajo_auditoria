# Informe EVI. 6 — Auditoría socioambiental de la Mina Marlin

Informe académico en LaTeX sobre la auditoría socioambiental de la **Mina Marlin**
(Montana Exploradora de Guatemala, S.A. / Goldcorp), departamento de San Marcos, Guatemala.

## Integrantes

- Cesar Diego Flores Callata
- Gianluis Fabricio Canqui Dueñas
- Jhean Kennedy Zarate Quispe
- Juan Diego Enriquez Ticona
- John Emerson Asqui Cartagena
- José Ignacio Cueva Condori

**Docente:** Ing. Carlos Paul Hancco Ramos · **Curso:** Gestión Ambiental en Minería
**Universidad:** Nacional del Altiplano, Facultad de Ingeniería de Minas · **Puno, 2026**

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
- No quedan marcadores `\pendiente` ni `% TODO` en el proyecto. Si alguien añade uno
  mientras edita, `config/comandos.tex` tiene una línea comentada que los hace
  desaparecer del PDF final.
- El `\nocite{*}` de `main.tex` ya está **desactivado**: la lista de referencias
  contiene solo las obras efectivamente citadas, como exige APA.

## Estado

**El informe está terminado.** 66 páginas, ~19.500 palabras, 5 figuras y 10 tablas.
Todas las URL de la bibliografía fueron comprobadas el 2 de agosto de 2026.

| Capítulo | Palabras | Contenido |
|---|---:|---|
| Resumen ejecutivo | 282 | |
| 1. Introducción | 816 | |
| 2. Objetivos | 186 | General + 5 específicos |
| 3. Marco teórico y normativo | 3.102 | Tabla 3.1 |
| 4. Descripción de la unidad minera | 3.078 | Figuras 4.1 y 4.2 · Tablas 4.1 y 4.2 |
| 5. Descripción de la auditoría | 2.271 | Figura 5.1 · Tablas 5.1 y 5.2 |
| 6. Análisis de hallazgos | 2.900 | Matriz completa de 10 hallazgos (Tabla 6.1) |
| 7. Análisis crítico | 2.184 | |
| 8. Plan de mejora continua (PHVA) | 2.303 | Figura 8.1 · Plan de 12 acciones (Tabla 8.1) |
| 9. Conclusiones | 820 | Una por objetivo específico + una general |
| 10. Recomendaciones | 569 | Por destinatario |
| Anexos A–E | 1.007 | Cartografía, distribución de hallazgos, cronología, fichas y glosario |

> Las figuras y tablas se numeran **por capítulo** (p. ej. Tabla 6.1, Figura 4.2),
> convención estándar de la clase `report`. Si citas una en el texto, usa siempre
> `\ref{...}` o `\Cref{...}`, nunca el número a mano: al insertar o quitar una
> figura/tabla, todos los demás números se recalculan solos.

### Estado de la entrega

**No queda nada pendiente.** Carátula completa con logo e integrantes, las cinco
figuras insertadas, cero marcadores `TODO` o `\pendiente`, `\nocite{*}`
desactivado y las 30 referencias con enlace comprobado.

> Si el docente exige el formato «APELLIDOS, Nombres» o los códigos de matrícula
> en la carátula, se cambian en `config/portada.tex`. Al hacerlo hay que volver a
> comprobar que la carátula sigue cabiendo en una sola página: con el logo va
> justa.

### Figuras

| Figura | Dónde | Fuente | Qué es |
|---|---|---|---|
| 4.1 | §4.2 | TikZ (código, en el propio `.tex`) | Esquema de ubicación y entorno hidrográfico (croquis sin escala) |
| 4.2 | §4.6 | `imagenes/diagramas/flujo_proceso.jpg` | Diagrama de flujo del proceso metalúrgico |
| 5.1 | §5.6 | `imagenes/diagramas/linea_tiempo_auditoria.jpg` | Cronología del proceso de auditoría (2004–2011) |
| 8.1 | §8.6 | `imagenes/diagramas/ciclo_phva.jpg` | Ciclo PHVA aplicado al caso |
| A.1 | Anexo A | `imagenes/mapas/mapa_ubicacion_marlin.jpg` | Mapa de ubicación (cartografía real) |

> La Figura 4.1 es un **croquis esquemático, no un mapa cartográfico**, y así se
> declara en su nota; complementa al mapa real del Anexo A, no lo sustituye.
> Si el mapa base de una figura procede de OpenStreetMap, la atribución
> «© OpenStreetMap contributors» es obligatoria por licencia ODbL (ya incluida
> en el pie de la Figura A.1).

## Bibliografía

**Las 30 entradas de `referencias.bib` tienen URL comprobada** mediante petición HTTP
el 2 de agosto de 2026. Las fuentes que no se pudieron localizar o verificar fueron
eliminadas, y el texto del informe se reescribió para no depender de ellas. La
cabecera del `.bib` lleva la lista de qué se eliminó y por qué.

Dos advertencias sobre fuentes que **sí funcionan pero devuelven error a los robots**:

- **SEC EDGAR** (informe técnico NI 43-101) devuelve 403 a cualquier petición que no
  venga de un navegador. En Chrome o Firefox abre sin problema.
- **iso.org** (ISO 14001 e ISO 19011) hace lo mismo, y además las normas ISO son de
  pago, como todas las normas ISO. Se mantienen porque son el eje normativo del
  informe y APA admite citarlas sin enlace libre.

Fuente destacada que **no estaba en la bitácora original** y se incorporó tras la
verificación: Maest y Kamp (2010), *Evaluation of predicted and actual water quality
conditions at the Marlin Mine*, de E-Tech International y financiado por Oxfam America.
Compara lo predicho en el estudio de impacto ambiental con lo realmente medido, y
aporta los datos duros que sostienen el hallazgo central del capítulo 6: línea base de
solo 8–9 meses, dos manantiales muestreados y potencial «moderado a alto» de generar
acidez.

## Formato: clase `report`, estilo libro

Desde el 2 de agosto de 2026 el informe usa la clase `report` (antes: `article` con
una carátula simulando capítulos). El cambio es puramente de presentación — el
contenido de los diez capítulos no se tocó — pero afecta a cómo se escribe cualquier
archivo nuevo de `secciones/`:

- **Los archivos de `secciones/` siguen escribiéndose exactamente igual**: `\section{}`
  para el título del capítulo, `\subsection{}` para sección y `\subsubsection{}` para
  subsección. `config/preambulo.tex` redirige cada uno al nivel real de la clase
  (`\chapter`, `\section`, `\subsection`). **No escribas `\chapter` directamente** en un
  archivo de sección: rompería la numeración.
- **No hace falta ningún `\newpage` manual entre capítulos.** Cada `\chapter` (real, vía
  el adaptador) inicia página nueva por sí solo; lo mismo `\tableofcontents`,
  `\listoffigures`, `\listoftables` y los anexos. Si ves un `\newpage` seguido
  inmediatamente de un `\section{}` en algún archivo, sóbra: produce una página en
  blanco.
- Los capítulos sin numerar (Resumen ejecutivo, Referencias) se escriben con
  `\section*{}` → `\chapter*{}` real. Si alguno de estos llega a ocupar más de una
  página, hay que fijar el encabezado a mano con `\markboth{Título}{Título}` justo
  después (ver `secciones/00_resumen.tex` o el bloque de la bibliografía en `main.tex`):
  `\chapter*` no actualiza el encabezado de página automáticamente, a diferencia de
  `\chapter` numerado.
- Tipografía: `newtxtext`/`newtxmath` (variante de Times New Roman) e interlineado
  `\setstretch{1.2}` vía `setspace`. Ambos se cambian en `config/preambulo.tex`. Si la
  universidad exigiera Arial, hay que pasar el compilador a **XeLaTeX** y usar
  `fontspec` con `\setmainfont{Arial}`.
- Los anexos usan `\appendix`, que numera los capítulos con letras (A, B, C…) y cambia
  automáticamente la palabra «Capítulo» por «Anexo» en el título y en el índice.
