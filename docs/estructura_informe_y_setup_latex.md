# Informe EVI. 6 — Estructura del documento y setup del proyecto LaTeX

**Caso:** Auditoría socioambiental de la Mina Marlin (Montana Exploradora / Goldcorp), San Marcos, Guatemala.
**Documento ancla:** *Human Rights Assessment of Goldcorp's Marlin Mine* — On Common Ground Consultants (2010).
**Repositorio:** https://github.com/BrandonQuispeTapia/trabajo_auditoria.git
**Flujo de trabajo:** GitHub ↔ Overleaf, compilación pdfLaTeX + Biber.

---

## PARTE 1 — Estructura del informe

Extensión objetivo sugerida: **35–45 páginas** sin contar anexos. Si el docente dio un límite, ajusta las secciones 6 y 8 (son las que más se pueden expandir o comprimir).

### Preliminares

| # | Sección | Contenido | Extensión |
|---|---|---|---|
| — | Carátula | Universidad, facultad, escuela profesional, curso, título del informe, docente, integrantes (apellidos y nombres, código), ciudad y fecha | 1 p. |
| — | Índice | Automático (`\tableofcontents`) | 1 p. |
| — | Índice de tablas y figuras | Automático (`\listoftables`, `\listoffigures`) | 1 p. |
| — | Resumen ejecutivo | 250–300 palabras: caso, auditoría analizada, hallazgos centrales y propuesta de mejora. Se escribe **al final**. | 1 p. |

### Cuerpo del informe

**1. Introducción** *(2 p.)*
Contexto de la minería como actividad de alto impacto socioambiental; por qué la auditoría es una herramienta de control; por qué se eligió el caso Marlin (auditoría independiente, pública, con eje ambiental **y** social, y con ciclo completo hasta el cierre de 2017). Cierra anunciando la estructura del documento.
> *Fuentes:* marco teórico general + justificación de la sección A de la bitácora.

**2. Objetivos** *(0.5 p.)*
- **General:** Analizar el proceso y los resultados de la auditoría socioambiental aplicada a la Mina Marlin, para formular una propuesta de plan de mejora continua.
- **Específicos (4–5):** describir la unidad minera y su entorno; identificar el alcance, criterios y metodología de la auditoría; clasificar los hallazgos ambientales y sociales; evaluar críticamente la independencia y las limitaciones del proceso; proponer un plan de mejora bajo el ciclo PHVA.

**3. Marco teórico y normativo** *(6–8 p.)*
- 3.1 Auditoría ambiental: definición, tipos (primera/segunda/tercera parte), y diferencias con **fiscalización**, **supervisión** y **EIA**.
- 3.2 ISO 14001:2015 — el SGA y la Estructura de Alto Nivel.
- 3.3 ISO 19011:2018 — fases de la auditoría, evidencia objetiva, hallazgo, no conformidad, competencia del auditor.
- 3.4 Estándares de desempeño social: IFC Performance Standards (PS1, PS4, PS5, PS7, PS8), Convenio 169 OIT, Voluntary Principles on Security and Human Rights, ICMM, GISTM, IRMA.
- 3.5 Marco normativo peruano de referencia: Ley 28611, Ley 27446 (SEIA), Ley 29325 (SINEFA/OEFA), D.S. 040-2014-EM, Ley 29785 (Consulta Previa). *Sirve para contrastar el caso guatemalteco con el régimen que aplicaría en Perú — es un plus argumentativo fuerte.*
- 3.6 Ciclo de mejora continua PHVA aplicado a la gestión ambiental minera.
> *Fuentes:* Sección D de la bitácora (ICMM/GISTM, IRMA, IFC, normativa peruana).

**4. Descripción de la unidad minera** *(6–7 p.)*
- 4.1 Identificación: titular (Montana Exploradora de Guatemala S.A.), grupo corporativo (Goldcorp → Newmont), historia y cambios de propiedad (1998–2017).
- 4.2 **Ubicación** — país, departamento de San Marcos, municipios de San Miguel Ixtahuacán y Sipacapa; coordenadas 15°14′05″N, 91°41′22″O; altitud 1.800–2.300 m s. n. m.; ríos Tzalá, Quivichil y Cuilco. → **Figura 1: Mapa de ubicación** (OpenStreetMap, licencia ODbL, con atribución).
- 4.3 Entorno social: población maya-mam y sipakapense, ~70.000 habitantes entre ambos municipios, economía agrícola de subsistencia.
- 4.4 Geología y mineral explotado: depósito epitermal de baja sulfuración Au-Ag, falla Virginia, vetas Marlin, West Vero, La Hamaca, Cochis. → **Tabla 1: Reservas y leyes (NI 43-101, 2010)**.
- 4.5 Método de explotación: tajo abierto + subterráneo (rampa en espiral; ~147 km de túneles al cierre).
- 4.6 Procesamiento: molienda SAG/bolas → lixiviación CIL con cianuro → Merrill-Crowe → doré; destrucción de cianuro proceso INCO; certificación International Cyanide Management Code. → **Figura 2: Diagrama de flujo del proceso** (lo dibujas tú en TikZ o lo insertas como imagen).
- 4.7 Producción y ciclo de vida: 2,3 M oz Au y 63 M oz Ag en 12 años; ~3.000 trabajadores en el pico; cierre 31/05/2017.
- 4.8 Infraestructura crítica: depósito de relaves, transición a relaves filtrados (dry-stack, 2013), planta de tratamiento de agua, aliviadero de emergencia.
> *Fuentes:* NI 43-101 (SEC), IFC disclosure, Goldcorp/Newmont, El Observador. **Ojo con los caveats:** capacidad de planta varía según la métrica; no atribuir a Marlin datos de Constancia.

**5. Descripción de la auditoría** *(6–7 p.)* ← **núcleo del trabajo**
- 5.1 Antecedentes: presión de accionistas socialmente responsables, MOU de marzo 2008, Comité Directivo independiente.
- 5.2 **¿Quién auditó?** On Common Ground Consultants Inc. (Vancouver). Independencia, mandato, quién financió.
- 5.3 **Equipo auditor:** Susan Joyce (líder), Myriam Cabrera, Giselle Huamani, Lloyd Lipsett, Monica Leonardo Segura, Sandro Macassi. → **Tabla 2: Composición del equipo, perfil y rol**.
- 5.4 Alcance temporal y espacial; exclusiones declaradas.
- 5.5 **Criterios de auditoría:** DUDH, PIDCP, PIDESC, Convenio 169 OIT, marco Ruggie, herramienta HRCA del Danish Institute for Human Rights, IFC PS, VPSHR.
- 5.6 **Metodología:** revisión documental, análisis de datos secundarios, entrevistas individuales y grupales, adaptación del HRCA, revisión técnica ambiental independiente. Cronograma oct. 2008 – may. 2010. → **Figura 3: Esquema metodológico / línea de tiempo**.
> *Fuente:* HRIA de On Common Ground (PDF completo espejado en q4cdn.com).

**6. Análisis de hallazgos** *(8–10 p.)* ← **la sección que más califica**
Organizada por los **siete ejes** de la auditoría: consulta, ambiente, trabajo, adquisición de tierras, inversión económica y social, seguridad, y acceso a remediación.
Formato obligatorio → **Tabla 3: Matriz de no conformidades** con columnas:
`Eje | Hallazgo | Evidencia objetiva | Criterio/estándar incumplido | Clasificación (NC mayor / NC menor / observación) | Recomendación | Estado de cierre`
Después de la tabla, desarrolla en prosa los 3–4 hallazgos más relevantes.
> *Fuentes:* HRIA + CAO/IFC + estudio de salud PHR/Michigan (Basu & Hu) + monitoreo COPAE.

**7. Análisis crítico del proceso de auditoría** *(4–5 p.)*
- 7.1 El problema de la independencia: auditoría **encargada y pagada por la empresa auditada**. Postura de Rights Action vs. diseño del Comité Directivo.
- 7.2 Limitaciones metodológicas reconocidas por los propios auditores: no participación de Sipacapa ni de los opositores; peer review de International Alert no ejecutado.
- 7.3 Conflicto de evidencia sobre contaminación: PHR/Michigan y COPAE reportan metales por encima de estándares; empresa y monitoreos oficiales sostienen conformidad. **Presenta ambas posiciones sin resolverlas artificialmente.**
- 7.4 Consecuencias institucionales: CAO/IFC (2005–2006), medidas cautelares CIDH MC 260-07 (2010) y su modificación (dic. 2011), pronunciamiento CEACR/OIT (2010).
- 7.5 Contraste: ¿qué habría pasado bajo el régimen del OEFA en Perú? (auditoría voluntaria vs. fiscalización con potestad sancionadora).

**8. Propuesta de plan de mejora continua (PHVA)** *(6–8 p.)* ← **la evidencia EVI. 6 propiamente dicha**
- 8.1 Política y compromiso.
- 8.2 **PLANIFICAR:** identificación de aspectos e impactos ambientales y sociales; objetivos y metas medibles.
- 8.3 **HACER:** controles operacionales, programa de relacionamiento comunitario, mecanismo de quejas, adopción de VPSHR.
- 8.4 **VERIFICAR:** monitoreo participativo (modelo AMAC / mesa de Espinar), indicadores, auditorías internas.
- 8.5 **ACTUAR:** acciones correctivas, revisión por la dirección, cierre de no conformidades.
- 8.6 → **Tabla 4: Plan de acción** con `Objetivo | Acción | Responsable | Plazo | Indicador | Meta | Recursos`.
- 8.7 → **Figura 4: Diagrama del ciclo PHVA aplicado al caso**.
> Mapea **cada recomendación de la HRIA a un requisito concreto** de IFC PS, GISTM o IRMA. Eso es lo que distingue un trabajo de nota alta.

**9. Conclusiones** *(1.5 p.)* — Una conclusión por objetivo específico. Sin información nueva.

**10. Recomendaciones** *(1 p.)* — Dirigidas a la empresa, al Estado y a la comunidad académica.

**11. Referencias** — Automático con `\printbibliography`, APA 7.

**12. Anexos** — A: Mapa ampliado. B: Matriz de no conformidades completa. C: Cronología del caso 1998–2017. D: Fichas de los estándares aplicados. E: Glosario de siglas.

### Reparto sugerido del trabajo

| Integrante | Secciones | Archivo `.tex` |
|---|---|---|
| 1 | Marco teórico y normativo | `03_marco_teorico.tex` |
| 2 | Unidad minera + mapa + figuras | `04_unidad_minera.tex` |
| 3 | Descripción de la auditoría | `05_auditoria.tex` |
| 4 | Hallazgos + análisis crítico | `06_hallazgos.tex`, `07_analisis_critico.tex` |
| 5 | Plan PHVA + conclusiones + bibliografía | `08_plan_mejora.tex`, `09_conclusiones.tex`, `referencias.bib` |
| Todos | Introducción, objetivos y resumen (al final, en conjunto) | `01_`, `02_`, `00_` |

---

## PARTE 2 — Prompt para Claude Code

Abre una terminal en `C:\Users\Brandon.DESKTOP-FF0NNOM\Downloads\TRABAJO AUDITORIA`, lanza `claude` y pega esto tal cual:

````text
Vamos a montar el andamiaje de un informe académico en LaTeX que se editará en Overleaf
sincronizado con GitHub. Trabaja en el directorio actual.

CONTEXTO
- Repositorio remoto: https://github.com/BrandonQuispeTapia/trabajo_auditoria.git
- En este directorio existe el archivo `bitacora_decisiones.md`, que contiene toda la
  investigación del caso y la bibliografía en APA 7 con URLs. LÉELO COMPLETO antes de
  generar nada: de ahí sacarás los datos del caso y las referencias.
- El informe analiza la auditoría socioambiental de la Mina Marlin (Goldcorp, Guatemala).

TAREA 1 — Inicializar el repositorio
1. Si no existe `.git`, ejecuta `git init` y `git branch -M main`.
2. Añade el remoto `origin` con la URL de arriba (si ya existe, no lo dupliques).
3. Si el remoto ya tiene commits, haz `git pull origin main --allow-unrelated-histories`
   antes de continuar. NO hagas push todavía: solo déjame el comando listo al final.

TAREA 2 — Crear esta estructura de carpetas y archivos
trabajo_auditoria/
├── main.tex                  <- documento principal, OBLIGATORIAMENTE en la raíz
├── referencias.bib
├── .gitignore
├── README.md
├── config/
│   ├── preambulo.tex
│   ├── portada.tex
│   └── comandos.tex
├── secciones/
│   ├── 00_resumen.tex
│   ├── 01_introduccion.tex
│   ├── 02_objetivos.tex
│   ├── 03_marco_teorico.tex
│   ├── 04_unidad_minera.tex
│   ├── 05_auditoria.tex
│   ├── 06_hallazgos.tex
│   ├── 07_analisis_critico.tex
│   ├── 08_plan_mejora.tex
│   ├── 09_conclusiones.tex
│   ├── 10_recomendaciones.tex
│   └── 11_anexos.tex
├── imagenes/
│   ├── mapas/
│   ├── diagramas/
│   ├── fotos/
│   └── logos/
├── tablas/
└── docs/
    └── bitacora_decisiones.md   <- mueve aquí el archivo que ya existe en la raíz

Las carpetas vacías deben llevar un `.gitkeep` para que Git las registre.

TAREA 3 — main.tex
Debe ser mínimo: documentclass, \input de config, y los \input de cada sección en orden,
con \tableofcontents, \listoffigures, \listoftables y \printbibliography. Nada de
contenido sustantivo aquí. Deja comentado con qué integrante corresponde cada \input.

TAREA 4 — config/preambulo.tex
Usa exactamente este stack (probado en Overleaf, compilador pdfLaTeX + Biber):
- \documentclass[12pt,a4paper]{article}  (va en main.tex, no aquí)
- geometry: márgenes 3cm izq, 2.5cm los demás
- \usepackage[T1]{fontenc}, \usepackage{mathptmx}  (Times New Roman, requisito típico)
- \usepackage[spanish,es-tabla,es-nodecimaldot]{babel}
- \usepackage{setspace} con \onehalfspacing
- graphicx con \graphicspath{{imagenes/}{imagenes/mapas/}{imagenes/diagramas/}}
- booktabs, longtable, tabularx, multirow, array
- caption con formato de tabla arriba y figura abajo
- enumitem, float, pdflscape
- hyperref al final, con colorlinks, enlaces en azul oscuro y bookmarks activados
- Bibliografía:
    \usepackage{csquotes}
    \usepackage[backend=biber,style=apa,sortlocale=es_ES,natbib=true]{biblatex}
    \DeclareLanguageMapping{spanish}{spanish-apa}
    \addbibresource{referencias.bib}
Comenta cada bloque en español explicando para qué sirve.

TAREA 5 — config/portada.tex
Portada con placeholders claros entre llaves para que yo rellene:
universidad, facultad, escuela profesional, logo (imagenes/logos/), curso, título del
informe, docente, lista de integrantes, ciudad (Puno) y año (2026).

TAREA 6 — Esqueletos de las secciones
Cada archivo de `secciones/` debe llevar su \section (y las \subsection que correspondan
según la estructura que te detallo abajo), y bajo cada encabezado un comentario LaTeX
`% TODO:` describiendo qué contenido va ahí y qué fuente lo sustenta. NO inventes ni
redactes el contenido académico: solo el andamiaje. Deja también los entornos `figure` y
`table` vacíos comentados donde la estructura los pide (Figuras 1-4, Tablas 1-4).

Estructura de secciones y subsecciones: replícala desde la sección "Cuerpo del informe"
del archivo `docs/estructura_informe_y_setup_latex.md`, que voy a colocar en esa carpeta.
Si aún no está, pídemelo antes de generar los esqueletos.

TAREA 7 — referencias.bib
Convierte TODA la bibliografía APA de `docs/bitacora_decisiones.md` a entradas BibTeX
válidas para biblatex. Reglas:
- Claves nemotécnicas: apellidoAñoPalabra (ej. `oncommonground2010hria`, `sec2011ni43101`).
- Usa el tipo correcto: @report, @online, @article, @book, @legislation/@misc según toque.
- Incluye SIEMPRE el campo `url` y `urldate = {2026-08-01}`.
- Protege mayúsculas de siglas y nombres propios con llaves: {IFC}, {OEFA}, {ISO}, {CIDH}.
- Añade `langid = {spanish}` o `{english}` según el idioma de la fuente.
- NO inventes datos: si un año o autor no consta en la bitácora, deja el campo con
  `% VERIFICAR` al lado. No fabriques DOIs.
Agrupa las entradas con comentarios por tipo: primarias/auditoría, normativa y estándares,
académicas, institucionales, prensa.

TAREA 8 — .gitignore
Ignora artefactos de LaTeX: *.aux *.log *.out *.toc *.lof *.lot *.bbl *.bcf *.blg
*.run.xml *.synctex.gz *.fls *.fdb_latexmk *.xdv, y además .DS_Store, Thumbs.db,
_minted*/ y la carpeta build/. NO ignores el PDF de salida (lo queremos versionado para
entregarlo).

TAREA 9 — README.md
Con: título del trabajo, integrantes (placeholder), descripción del caso, instrucciones
de compilación local (`latexmk -pdf main.tex`), cómo importar el repo en Overleaf
(New Project → Import from GitHub) y un recordatorio de que el compilador debe ser
pdfLaTeX y el motor bibliográfico Biber.

TAREA 10 — Verificación
1. Si hay LaTeX instalado, compila con `latexmk -pdf main.tex` y arregla los errores hasta
   que el PDF salga limpio. Si no hay LaTeX, dilo y no falles.
2. Haz un commit inicial con mensaje "chore: andamiaje del informe de auditoría en LaTeX".
3. NO hagas push. Muéstrame el comando de push y un árbol final del proyecto.

REGLAS GENERALES
- Todo comentario y texto en español.
- No redactes contenido académico del informe: solo estructura, comentarios TODO y la
  bibliografía (esa sí completa y real, extraída de la bitácora).
- Si algún dato de la bitácora es ambiguo, pregúntame antes de asumir.
````

### Después de que Claude Code termine

1. Copia este mismo archivo a `docs/estructura_informe_y_setup_latex.md` dentro del proyecto (la Tarea 6 lo necesita como referencia).
2. `git push -u origin main`.
3. En Overleaf: **New Project → Import from GitHub → trabajo_auditoria**.
4. En Overleaf, menú *Settings*: compilador **pdfLaTeX**, y en *Menu → Bibliography* verifica que use **Biber** (es el default cuando detecta `biblatex`).
5. Comparte el proyecto de Overleaf con tus compañeros por correo para que editen en paralelo.
6. Regla de oro con el grupo: **cada quien toca solo su archivo `.tex`**. Los cambios en `main.tex` y `preambulo.tex` los hace una sola persona.

### Advertencias

- **Overleaf ↔ GitHub no sincroniza solo.** Hay que pulsar *Menu → GitHub → Push/Pull* manualmente. Si el grupo edita en Overleaf durante días sin sincronizar, el repo se queda atrás.
- La sincronización con GitHub es una **función de pago** en Overleaf. Si no tienes plan premium, la alternativa es trabajar solo en Overleaf y subir el `.zip` al repo periódicamente, o editar en local con VS Code + LaTeX Workshop y usar Git normalmente.
- `mathptmx` da Times New Roman. Si tu universidad exige **Arial**, hay que cambiar a compilador **XeLaTeX** y usar `fontspec` con `\setmainfont{Arial}` — dímelo y ajusto el preámbulo.
