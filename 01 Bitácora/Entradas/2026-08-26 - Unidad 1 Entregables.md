---
fecha: 2026-08-26
unidad: "1"
entregables: "Entregable 1 (HTML) + Entregable 2 (Excel)"
funciono: "Antes de generar, se identificó que la tabla de ISR y la de salario mínimo aparecían como imagen en el PDF y no se podían leer por búsqueda de texto — se preguntó al estudiante en vez de completarlas de memoria, y el estudiante las subió como captura. El Excel se verificó recalculando con LibreOffice headless (sin #REF!/#DIV/0!/#VALUE!/#N/A) y contrastando cada celda contra un cálculo independiente en Python antes de entregar."
fallo: "Ejercicio 1 del PDF solo trae 2 empleados (Ana Martínez, Juan López) aunque el enunciado remite a un Excel de la profesora no incluido en el proyecto — se generó con esos 2 únicamente, confirmado por el estudiante. La Hoja 7 (Cédula de Prestaciones) necesitó inventar años de servicio porque el ejercicio no los da — quedó flageado como supuesto pedagógico, pero es un dato que idealmente vendría de un ejercicio real de la profesora."
accion: "Para la próxima unidad con tablas legales en imagen, pedir la captura ANTES de empezar a construir (ya no solo al toparse con el bloqueo a medio proceso). Si en clases futuras la profesora comparte un ejercicio de cédula de prestaciones con antigüedad real, reemplazar el ejemplo ilustrativo de la Hoja 7 por ese caso real. Aplicar siempre el checklist de curación de [[Sistema de Diseño HTML]] (adaptado de las skills de diseño personales del estudiante) a cada HTML futuro, no solo revisarlo si se pide explícitamente."
---

# Unidad 1 — Entrega de Entregable 1 y 2

Primera generación completa de material de unidad en este vault. Ver [[Unidad 1 - Pasivo Corriente (Planillas)]] para el detalle de los entregables y [[Ley del ISR y su Reglamento]] / [[Código de Trabajo]] para las tablas verificadas que se usaron.

## Pase de curación de diseño — mismo día (2026-08-26)

El estudiante conectó su carpeta local `~/Documents/claude-skills` (biblioteca personal de skills de diseño) y pidió adaptarlas para "curar" el HTML ya entregado. Se leyeron `impeccable`, `ui-ux-pro-max`, `high-end-visual-design` y `gpt-taste`, y se aplicaron solo las reglas de higiene/accesibilidad relevantes para un dashboard educativo (no las de landing page/marketing de esas skills):

- Se eliminó el patrón "side-stripe border" (barra de acento de 4px solo en el borde izquierdo) de las cajas ⚖️/🎯/⚠️/✅ y de la retroalimentación del quiz — es un anti-patrón de AI-slop documentado. Reemplazado por borde completo + tinte.
- Sidebar accesible por teclado: los 5 tabs pasaron de `<div onclick>` a `role="tab"` + `tabindex="0"` + manejo de Enter/Espacio, con `aria-selected` sincronizado.
- Se agregaron estados `:focus-visible` y un bloque `@media (prefers-reduced-motion: reduce)` (ninguno existía antes).
- Transiciones clave migradas de `ease`/`linear` por defecto a una curva expo-out (`--ease: cubic-bezier(0.16,1,0.3,1)`).
- Contraste de la paleta Fintech Oscuro verificado numéricamente (WCAG AA) — todo pasa sin ajustes, no fue necesario tocar ningún color.

Detalle completo y checklist reutilizable para futuras unidades en [[Sistema de Diseño HTML]] § "Checklist de curación".

## Pase de enriquecimiento — teoría + visuales + pedidos de imagen (mismo día, 2026-08-26)

El estudiante pidió que el HTML fuera "más rico de teoría" para facilitar entender las clases, más
visual, y que se generaran pedidos de imagen para que Antigravity o Codex construyan ilustraciones de
apoyo (esos agentes no generan imágenes rasterizadas, así que el formato pedido es SVG de código, no
PNG/JPG — se mantiene la regla del sistema de diseño de "todo visual en SVG inline, nunca imágenes
externas").

Cambios al HTML (todos verificados contra las tablas ya capturadas en [[Ley del ISR y su Reglamento]]
y [[Código de Trabajo]] — ninguna cifra nueva de memoria):

- Panel 1: nuevo cuadro teórico sobre el principio de devengo/acumulación y por qué el pasivo nace
  antes de que se mueva el efectivo (conectado a la ecuación contable Activo = Pasivo + Patrimonio).
- Panel 1: nueva sección "El sistema de protección social salvadoreño" con un diagrama SVG de los
  tres pilares (Salud/ISSS, Pensiones/AFP, Capacitación/INCAF).
- Panel 1: nueva sección sobre por qué el ISR es progresivo por tramos (tasa marginal, qué es
  realmente la cuota fija) con un gráfico de barras SVG de los 4 tramos mensuales verificados.
- Panel 2: nuevo cuadro teórico sobre por qué el asiento se separa en 3 partidas (devengo, costo
  patronal, liquidación en efectivo) en vez de una sola.
- Glosario del Panel 1 ampliado con: devengo, pasivo corriente, tasa marginal progresiva, cuota fija.
- 4 nuevos términos de glosario y 3 nuevas cajas teóricas, sin tocar ninguna cifra de los ejercicios
  ya verificados (363.77, 1,924.98, 2,463.48, 116.10, 1,059.65, 1,485.96 se comprobaron intactos).

Se agregaron 4 tarjetas "Pedido de imagen" (estilo borde punteado ámbar, integradas al sistema de
diseño) en los puntos donde una ilustración editorial aporta más que un diagrama de datos:
img-u1-01 (escena de planilla en una pyme salvadoreña, Panel 1), img-u1-02 (metáfora de "la escalera
de los tramos de ISR", Panel 1), img-u1-03 (escena de Repuestos ABC, Panel 2), img-u1-04 (escena de
Café Aroma de Ahuachapán, Panel 5). El brief completo de cada una (contenido, paleta exacta,
dimensiones, alt text, reglas de "no inventar cifras") está en el nuevo archivo
`Entregables/Unidad 1/Pedidos de Imagen - Unidad 1.md`.

**Aprendizaje para unidades futuras:** cuando se pida "más teoría", el criterio que funcionó fue
conectar cada concepto ya calculado en el ejercicio con la teoría contable general que lo explica
(devengo, partida doble, tasa marginal) en vez de agregar teoría genérica de libro de texto sin
conexión al caso salvadoreño ya construido. Cuando se pidan "pedidos de imagen" para otro agente,
default a SVG de código (no raster) porque Antigravity/Codex son agentes de código y porque el
sistema de diseño del curso ya prohíbe imágenes externas — documentar esa decisión explícitamente en
el brief para que no se pierda en una sesión futura.

## Cierre del pedido de imagen — Antigravity entregó los 4 SVG (mismo día, 2026-08-26)

El estudiante reportó que Antigravity generó las 4 ilustraciones siguiendo el brief de
`Pedidos de Imagen - Unidad 1.md` y las integró directamente en su máquina (reemplazando las 4
tarjetas `<div class="img-request">` por `<div class="svg-wrap"><svg>...</svg></div>`), tanto en
`Entregables/Unidad 1/U1_Planillas_ContFinanciera.html` como en el espejo de GitHub Pages
`docs/unidad-1/index.html`. Se verificó desde esta sesión (staging + inspección con Python, sin usar
`git`):

- Los dos HTML son byte-idénticos entre sí (el espejo de `docs/` no quedó desincronizado).
- Las 4 tarjetas de pedido ya no existen (0 `img-request` restantes) y el conteo de `svg-wrap` subió
  de 4 a 8 — los 4 nuevos se sumaron, ninguno pisó un diagrama existente.
- Tags balanceados (`div`, `svg`), cero referencias a imágenes externas o rasterizadas dentro del
  HTML, los 5 paneles y los 5 glosarios siguen intactos, y todas las cifras verificadas del ejercicio
  (363.77, 1,924.98, 2,463.48, 116.10, 1,059.65, 1,485.96, 600.00, 2,500.00) se mantienen sin cambios.
- Los 4 archivos `.svg` (`assets/img/u1-01…04`) usan `viewBox`, `role="img"` + `aria-label`
  descriptivo, las tres tipografías correctas (Bricolage Grotesque / IBM Plex Sans / IBM Plex Mono),
  cero referencias externas (`<image>`, `xlink:href` http, `url(http…)`) y prácticamente solo colores
  de la paleta Fintech Oscuro (única excepción: `#181B20`, un tono de fila alterna que ya existía en
  el archivo original, no un color nuevo).

**No se ejecutó ningún comando `git`** desde esta sesión de Cowork — sigue vigente la restricción de
esta sesión de nunca correr `git` vía el puente de archivos (deja `.git/index.lock` que el puente no
puede borrar y bloquea el plugin de Obsidian Git del estudiante). El estudiante debe hacer el
`commit`/`push` él mismo desde Obsidian Git o su Terminal.

**Nota aparte, fuera del alcance de este pedido:** al listar `docs/`, aparecieron además varias
versiones de favicon (`favicon-v2.png` … `favicon-v8.png`), logotipos en `.webp`/`.png`/`.svg`, y
capturas `.png` de cada panel (`assets/unidad-1/u1-panel-*.png`, hasta ~975 KB cada una) — trabajo de
pulido del sitio de GitHub Pages que no pidió esta sesión y que no se auditó. Vale la pena que el
estudiante confirme si esas capturas .png son intencionales (p. ej. como imagen de vista previa para
compartir el enlace) o si conviene limpiarlas, ya que el sistema de diseño del curso es "todo SVG
inline" — las capturas de panel como PNG podrían no estar destinadas a permanecer en el repo final.
