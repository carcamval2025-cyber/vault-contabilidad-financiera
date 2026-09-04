---
icon: "🎨"
banner_icon: "🎨"
tags: [curso/contabilidad-financiera, entregables, diseño]
---

# Sistema de Diseño — Entregable 1 (HTML, 5 paneles)

> [!warning] Paleta y estética reemplazadas — 2026-08-26
> El estudiante pidió explícitamente abandonar la paleta navy/rosa/verde de las instrucciones maestras del proyecto (que se sentía genérica / "AI slop") y adoptar una nueva dirección: **Fintech oscuro moderno**, con acento eléctrico único. Se decidió que este es el **nuevo estándar para todas las unidades futuras**, no solo para la Unidad 1. Esta nota (no las instrucciones maestras del proyecto, que no se pueden editar desde aquí) es la fuente de verdad vigente del sistema de diseño HTML — cualquier sesión futura debe seguir la paleta y tipografía de más abajo, no la del texto de las instrucciones del proyecto.

> [!info] Pase de curación con skills de diseño personales — 2026-08-26
> El mismo día, el estudiante pidió usar su biblioteca de skills de diseño (carpeta local `claude-skills`, sincronizada vía device bridge) para "curar" el resultado y evitar patrones de AI-slop más finos que la paleta por sí sola no resuelve. Se leyeron y adaptaron principios de `impeccable`, `ui-ux-pro-max`, `high-end-visual-design` y `gpt-taste`. La sección **"Checklist de curación"** más abajo es el resultado — es un filtro adicional que corre DESPUÉS de aplicar la paleta Fintech Oscuro, en todas las unidades futuras, no una paleta nueva.

Resumen de referencia rápida. La estructura de paneles y las reglas de contenido siguen viniendo de las instrucciones maestras del proyecto; lo que cambió es exclusivamente la piel visual (paleta, tipografía, tratamiento de componentes) — ver también [[Aprendizajes Acumulados]] para el porqué del cambio.

## Estructura fija

Un solo HTML, barra lateral izquierda + 5 paneles:

1. **Resumen Visual** — SVG del concepto central, 3 cards de conceptos clave, tabla con badges y ejemplos salvadoreños, caja ⚖️ Marco Legal, caja 🎯 cobertura en Parcial/Control, glosario.
2. **Ejercicio Resuelto** — el ejercicio exacto de la guía de la profesora, steps numerados con razonamiento y referencia legal, caja ⚠️ errores comunes, glosario.
3. **Guía Excel** — SVG preview del Excel, instrucciones paso a paso, caja ✅ código de honor, glosario de funciones.
4. **Quiz de Práctica** — mínimo 10 preguntas (3 fáciles + 4 medias + 3 difíciles), retroalimentación inmediata, glosario.
5. **Ejercicio Variante** — empresa salvadoreña/centroamericana nueva, misma estructura, solución oculta con botón, glosario.

## Paleta — "Fintech Oscuro" (vigente desde 2026-08-26)

Modo oscuro con un único acento eléctrico dominante (ámbar — asociación directa con dinero/efectivo) y dos acentos secundarios de uso *restringido y semántico* (cian solo para Marco Legal, magenta solo para el badge de Patrimonio). Nunca usar el acento ámbar y el cian con el mismo peso visual en una misma composición — el ámbar manda.

```
--bg:        #0B0D10   --bg-elev:  #14171C   --bg-elev2: #1C2027
--border:    #262B33
--text:      #EDEEF0   --text-dim: #9098A6
--accent:    #FFB020   --accent-2: #FFD873   --accent-dim: rgba(255,176,32,.12)
--success:   #3ECF8E   --danger:   #FF5C5C   --info(legal): #5AC8FA
--patrimonio:#FF6EC7
--ease:      cubic-bezier(0.16,1,0.3,1)   /* expo-out, ver checklist de curación */
```

Contraste verificado (WCAG AA, texto normal ≥4.5:1): `--text-dim` sobre `--bg`/`--bg-elev`/`--bg-elev2` da 6.70 / 6.18 / 5.62 — todos aprueban sin ajuste. No usar un gris más apagado que `--text-dim` para texto de cuerpo.

Tipografía: **Bricolage Grotesque** (titulares/hero, variable, mucho carácter) + **IBM Plex Sans** (cuerpo/UI) + **IBM Plex Mono** (TODA cifra monetaria y tabla numérica — tabular-nums, sensación de terminal financiera real). Nunca Inter, Roboto, Arial, ni Space Grotesk (sobreusado en generaciones de IA).

## Cajas especiales (obligatorias donde aplique) — versión oscura

| Caja | Fondo / borde / texto |
|---|---|
| 🎯 Evaluación | rgba(255,176,32,.05) / borde completo rgba(255,176,32,.35) / #EDEEF0 |
| ⚠️ Error | rgba(255,92,92,.05) / borde completo rgba(255,92,92,.35) / #EDEEF0 |
| ✅ OK | rgba(62,207,142,.05) / borde completo rgba(62,207,142,.35) / #EDEEF0 |
| ⚖️ Marco Legal | rgba(90,200,250,.05) / borde completo rgba(90,200,250,.35) / #EDEEF0 |

> [!warning] Tratamiento corregido — 2026-08-26 (pase de curación)
> La primera versión usaba una **barra de acento de 4px solo en el borde izquierdo** ("side-stripe"). Se corrigió: es un patrón de AI-slop documentado (skill `impeccable`, sección "Absolute bans" → *Side-stripe borders*) — se ve en el 80%+ de interfaces generadas por IA y no aporta nada que el fondo con tinte y el ícono/emoji del encabezado no den ya. **Tratamiento vigente: borde completo de 1px en el color semántico (a ~35% de opacidad) + fondo con tinte + el emoji ya existente en el `<h4>` hace de "leading icon".** Nunca volver a la barra lateral sola.

La caja **⚖️ Marco Legal** es obligatoria en Paneles 1 y 2 — cita el artículo o ley exacta (ej. "Art. 177, Código de Trabajo") y es la única caja que usa el acento cian. La misma corrección (borde completo, no side-stripe) aplica a la retroalimentación del quiz (`.q-feedback`).

## Badges contables (versión oscura)

| Badge | Color |
|---|---|
| Activo | cian `#5AC8FA` |
| Pasivo | ámbar `#FFB020` |
| Patrimonio | magenta `#FF6EC7` (único uso de este color) |
| Ingreso | verde `#3ECF8E` |
| Gasto | rojo `#FF5C5C` |

## Toques distintivos de esta dirección (para no repetir el layout genérico de siempre)

- Fondo con textura sutil de puntos (dot-grid) en toda la app, no un fondo plano.
- Sidebar con números fantasma grandes (outline, semitransparentes) detrás de cada label de navegación.
- Hero tipo "encabezado de estado de cuenta": eyebrow en monoespaciada estilo terminal (ej. `UNIDAD—01 / PLANILLAS.SV`), regla horizontal ámbar arriba y abajo, elemento decorativo tipo arco/gauge parcial en vez de blobs de gradiente genéricos.
- Chips de alerta como contornos (outline), no rellenos sólidos.
- Todas las cifras en IBM Plex Mono con alineación tabular — refuerza la sensación de app financiera real.

## Checklist de curación (adaptado de skills de diseño personales — correr en TODA unidad futura)

Fuente: biblioteca personal del estudiante en `~/Documents/claude-skills` (skills `impeccable`, `ui-ux-pro-max`, `high-end-visual-design`, `gpt-taste`, sincronizada vía device bridge). Este curso usa un dashboard educativo con paneles y tablas, no una landing page — por eso se adoptaron solo las reglas de *higiene/anti-slop* y accesibilidad de esas skills, no sus patrones de marketing (bento grids, GSAP pesado, glassmorphism, hero-metric) que no aplican aquí y sobrecargarían el diseño en vez de curarlo.

**Anti-patrones a rechazar siempre (`impeccable`, sección "Absolute bans"):**
- ❌ Side-stripe borders (`border-left`/`border-right` de color como único acento de una caja/card/alerta) → usar borde completo + tinte, o nada.
- ❌ Gradient text (`background-clip:text` con gradiente).
- ❌ Glassmorphism decorativo sin propósito.
- ❌ "Ghost-card": `border:1px solid` + `box-shadow` difuso de ≥16px en el mismo elemento, como decoración.
- ❌ `border-radius` ≥ 24-32px en cards/inputs (tope real: 10-16px; pill/circular solo en badges, chips o step-circles).
- ❌ Eyebrow tag idéntico repetido arriba de cada sección (aceptable UNA vez en el hero, no como plantilla por sección).
- ❌ Emoji en cualquier parte del HTML, incluidas las cajas ⚖️/🎯/⚠️/✅. **Regla fija desde Unidad 2 (confirmada explícitamente por el estudiante, 2026-09-04): cero emoji en todo el documento, sin excepción.** Las cajas especiales llevan en su lugar un ícono SVG outline de línea (mismo tratamiento que los íconos de sidebar) como "leading icon" del `<h4>`; el color y fondo de la caja (ámbar/rojo/verde/azul según el tipo) siguen distinguiéndola visualmente. Esto reemplaza la excepción documentada como "corrección puntual de Unidad 1": ya no es puntual, es la regla para Unidad 2 en adelante.

**Accesibilidad y motion (`ui-ux-pro-max` + `impeccable`) — no negociable:**
- Contraste texto normal ≥ 4.5:1, texto grande ≥ 3:1 — verificar con la paleta de arriba, no asumir.
- Todo elemento interactivo (tabs de sidebar incluidos, aunque sean `<div>`) necesita `role`, `tabindex="0"`, manejo de teclado (Enter/Espacio) y un estado `:focus-visible` visible — no solo `onclick`.
- Toda animación con transición/`@keyframes` necesita una alternativa bajo `@media (prefers-reduced-motion: reduce)`.
- Transiciones con curva expo-out (`--ease: cubic-bezier(0.16,1,0.3,1)`), nunca `linear` ni el `ease` por defecto del navegador — se siente más premium sin añadir peso visual.
- Animar solo `transform`/`opacity` (GPU-safe); nunca animar `width`/`height`/`top`/`left`.
- Botones y opciones clickeables ≥ 44×44px de área táctil.

**Antes de entregar cualquier HTML de unidad, verificar:**
1. Ningún `.box`/caja de alerta usa borde lateral solo — borde completo + tinte.
2. Los 5 tabs del sidebar tienen `role="tab"`, `tabindex="0"` y responden a teclado.
3. Existe un bloque `@media (prefers-reduced-motion: reduce)`.
4. Las transiciones clave usan `var(--ease)`, no `ease`/`linear` por defecto.
5. Contraste de `--text-dim` y de cada color semántico sobre su fondo sigue ≥ 4.5:1 (no cambiar los tokens sin volver a verificar).

## Protocolo — pedir ilustraciones a otro agente (Antigravity/Codex)

Establecido y verificado por primera vez en la Unidad 1 (2026-08-26, 4 imágenes: `img-u1-01`…`04`).
Funcionó bien — este es el procedimiento a repetir y mejorar en toda unidad futura, no un caso único.

**Cuándo pedir una ilustración en vez de construir el SVG directamente en la sesión de Claude:**
un diagrama de datos (gráfico de tramos, flujo de un cálculo, comparación de tasas) lo sigue
construyendo la sesión de Claude, directo en el HTML. Se delega a otro agente cuando el panel se
beneficia de una **escena editorial o una metáfora conceptual** — anclar un ejercicio en un lugar y
personas concretas (ej. el mostrador de una empresa salvadoreña con los empleados del enunciado), o
ilustrar una idea abstracta con una imagen memorable (ej. una escalera para tramos progresivos de
impuesto) — algo que se beneficia de más tiempo/detalle artístico del que vale la pena invertir
dentro del flujo principal de generación del HTML.

**Cómo estructurar el pedido:**
1. En el HTML, dejar una tarjeta placeholder con la clase `.img-request` (borde punteado ámbar,
   integrada visualmente al sistema de diseño — no un hueco roto) en el lugar exacto donde irá la
   imagen, con un `ID` único con el patrón `img-u[N]-0[X]` (N = número de unidad).
2. Crear un archivo `Pedidos de Imagen - Unidad [N].md` dentro de `Entregables/Unidad [N]/`, con: las
   reglas no negociables (ver abajo) una sola vez al inicio, y un brief por imagen — ubicación exacta
   en el HTML, propósito pedagógico, contenido sugerido, estilo, `viewBox` recomendado, alt text, y
   nombre de archivo destino (`assets/img/u[N]-0[X]-descripcion.svg`).

**Reglas no negociables del brief (repetirlas siempre, un agente nuevo no las hereda por defecto):**
- Formato: **SVG de código completo, nunca PNG/JPG** — es la única forma de que la ilustración
  cumpla "todo visual en SVG inline, nunca imágenes externas" y a la vez tenga sentido pedírsela a un
  agente de código (Antigravity/Codex no son generadores de imágenes rasterizadas).
- Paleta: únicamente los valores hexadecimales de la sección "Paleta — Fintech Oscuro" de arriba.
- Tipografía: únicamente Bricolage Grotesque / IBM Plex Sans / IBM Plex Mono si el SVG lleva texto.
- Sin emoji como ícono estructural — construir íconos con `<path>`/`<circle>`/`<rect>`, estilo outline.
- Contexto salvadoreño o centroamericano siempre; nunca inventar una cifra que no esté ya verificada
  en el HTML o el vault.
- Cada SVG debe llevar `viewBox` responsive y `role="img"` + `aria-label` descriptivo.

**Cómo verificar el resultado sin usar `git`** (el estudiante integra los cambios en su propia
máquina; esta sesión de Cowork nunca ejecuta `git` vía el puente de archivos — deja `.git/index.lock`
que el puente no puede borrar y bloquea el plugin de Obsidian Git del estudiante):
1. `device_stage_files` de los HTML modificados (el entregable y su espejo en `docs/`, si existe) y
   de los `.svg` nuevos.
2. Un script Python de verificación (no visual, estructural) que confirme: cero tarjetas
   `img-request` restantes, el conteo de `svg-wrap` subió exactamente en el número de imágenes
   pedidas, tags balanceados (`div`, `svg`), los HTML del entregable y de `docs/` siguen idénticos
   entre sí, las cifras clave del ejercicio no cambiaron, y cada `.svg` nuevo usa `viewBox`,
   `role="img"`+`aria-label`, las tipografías correctas, cero `<image>`/`xlink:href http`/`url(http…)`,
   y solo colores de la paleta (una excepción legítima: tonos de elevación ya usados en el archivo
   original, como `#181B20`, que no son "nuevos" aunque no estén en la tabla de tokens).
3. Registrar el resultado de la verificación en la entrada de bitácora del día — qué se pidió, qué se
   entregó, qué pasó y qué no en la verificación.

**Ideas de mejora para la próxima vez** (pendientes de probar, no reglas todavía): pedir que cada SVG
entregado incluya un comentario `<!-- generado por Antigravity/Codex · brief img-uN-0X -->` para
trazabilidad; si una unidad futura pide más de 4-5 imágenes, considerar agrupar el brief por panel en
vez de un archivo plano; si el agente introduce texto sobre un fondo o color nuevo dentro del SVG,
añadir a la verificación un chequeo de contraste WCAG igual al que ya se hace para la paleta del HTML.

## Reglas que no se rompen

- Todo visual en SVG inline, nunca imágenes externas — incluidas las ilustraciones que construya
  otro agente (Antigravity/Codex): se piden y se verifican como SVG de código, nunca como PNG/JPG
  (ver protocolo arriba).
- Nunca omitir ninguno de los 5 paneles ni el glosario de cada uno.
- Nunca usar ejemplos genéricos — siempre contexto salvadoreño o centroamericano.
- Quiz siempre con retroalimentación inmediata pregunta por pregunta (a diferencia del Simulacro de Control, que es modo examen).

## Ver también

[[Sistema de Diseño Excel]] · [[Reglas de Precisión Legal y Pedagógica]] · [[Aprendizajes Acumulados]]
