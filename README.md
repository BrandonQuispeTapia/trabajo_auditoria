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

**El informe está terminado.** 72 páginas, ~19.500 palabras, 4 figuras y 10 tablas.
Todas las URL de la bibliografía fueron comprobadas el 2 de agosto de 2026.

| Capítulo | Palabras | Contenido |
|---|---:|---|
| Resumen ejecutivo | 282 | |
| 1. Introducción | 816 | |
| 2. Objetivos | 186 | General + 5 específicos |
| 3. Marco teórico y normativo | 3.102 | Tabla 1 |
| 4. Descripción de la unidad minera | 3.078 | Figuras 1 y 2 · Tablas 2 y 3 |
| 5. Descripción de la auditoría | 2.271 | Figura 3 · Tablas 4 y 5 |
| 6. Análisis de hallazgos | 2.900 | Matriz completa de 10 hallazgos (Tabla 6) |
| 7. Análisis crítico | 2.184 | |
| 8. Plan de mejora continua (PHVA) | 2.303 | Figura 4 · Plan de 12 acciones (Tabla 7) |
| 9. Conclusiones | 820 | Una por objetivo específico + una general |
| 10. Recomendaciones | 569 | Por destinatario |
| Anexos A–E | 1.007 | Cartografía, distribución de hallazgos, cronología, fichas y glosario |

### Estado de la entrega

**No queda nada pendiente.** Carátula completa con logo e integrantes, las cinco
figuras insertadas, cero marcadores `TODO` o `\pendiente`, `\nocite{*}`
desactivado y las 30 referencias con enlace comprobado.

> Si el docente exige el formato «APELLIDOS, Nombres» o los códigos de matrícula
> en la carátula, se cambian en `config/portada.tex`. Al hacerlo hay que volver a
> comprobar que la carátula sigue cabiendo en una sola página: con el logo va
> justa.

### Figuras

Las cuatro figuras están **dibujadas en TikZ**, es decir, en código LaTeX dentro
de los propios archivos `.tex`. No hay que subir ninguna imagen ni preocuparse de
que se pixelen al imprimir:

| Figura | Dónde | Qué es |
|---|---|---|
| 1 | §4.2 | Esquema de ubicación y entorno hidrográfico (croquis sin escala) |
| 2 | §4.6 | Diagrama de flujo del proceso metalúrgico |
| 3 | §5.6 | Cronología del proceso de auditoría (2004–2017) |
| 4 | §8.6 | Ciclo PHVA aplicado al caso |

> La Figura 1 es un **croquis esquemático, no un mapa cartográfico**, y así se
> declara en su nota. Si el docente exige cartografía real, el Anexo A explica
> cómo añadirla (OpenStreetMap centrado en 15.234852, −91.689418; la atribución
> «© OpenStreetMap contributors» es obligatoria por licencia ODbL).

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

## Tipografía

El preámbulo usa `mathptmx` (Times New Roman) y `\onehalfspacing` (interlineado 1,5).
Ambos se cambian en un solo lugar: `config/preambulo.tex`. Si la universidad exigiera Arial,
hay que pasar el compilador a **XeLaTeX** y usar `fontspec` con `\setmainfont{Arial}`.
