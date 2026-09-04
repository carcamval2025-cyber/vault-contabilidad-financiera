---
icon: "🗂️"
banner_icon: "🗂️"
tags: [curso/contabilidad-financiera, bitácora, entrada]
fecha: 2026-09-04
unidad: "Unidad 2 - Transacciones de Capital"
entregables: "HTML (pase de enriquecimiento sobre el ya entregado el mismo día — no se regeneró el Excel)"
funciono: "El estudiante comparó directamente el HTML de Unidad 2 contra el de Unidad 1 ('mira el anterior material y compara cómo está de lleno de información') y eso permitió medir objetivamente la brecha: Unidad 1 tenía 52 SVG / 19 h2 / 16 cards en 4,649 líneas; Unidad 2 solo 23 SVG / 9 h2 / 4 cards en 887 líneas — el Panel 1 de Unidad 1 tenía 9 secciones contra 3 de Unidad 2, y el Panel 2 casi 5 ejercicios contra 2. Se expandió el Panel 1 a 6 secciones (Formación de la S.A. con línea de tiempo, Los cuatro valores de una acción, Panorama de tres momentos, más una caja de Profundización teórica conectando con Unidad 1), se agregó el Ejercicio 3 (dividendo preferente DEF, S.A. de C.V. — diapositiva 31, ya usado en el Excel pero ausente del HTML) al Panel 2, un diagrama de fórmulas encadenadas al Panel 3, 4 preguntas nuevas al quiz (10→14), y una parte e) de dividendo al Panel 5. Todo verificado con Playwright (0 errores de consola, div/section/svg balanceados, 0 emoji) antes de entregar."
fallo: "Dos cosas se pasaron por alto y el estudiante tuvo que corregir en el momento: (1) el HTML se entregó originalmente mucho más pobre en contenido que el estándar ya establecido por Unidad 1, sin que Claude comparara contra la unidad anterior antes de dar por completo el entregable. (2) Al construir los diagramas nuevos, Claude generó TODOS los SVG directo en el HTML sin usar el protocolo de delegación a Antigravity/Codex para las escenas editoriales/metáforas conceptuales (documentado en 'Sistema de Diseño HTML.md', sección 'Protocolo — pedir ilustraciones a otro agente', establecido desde Unidad 1) — el estudiante tuvo que recordarlo explícitamente ('Los pedidos de SVGs deben de ser a Antigravity, recuerda eso'). Se corrigió agregando 4 tarjetas `.img-request` + el archivo `Pedidos de Imagen - Unidad 2.md`, pero debió aplicarse desde el primer pase, no como corrección posterior. Un error menor adicional: dos diagramas SVG nuevos (Textiles Izalco y prelación) reutilizaban un `marker` (`arrow2`) definido en un `<svg>` distinto del documento — el arrowhead no se renderizaba de forma consistente entre navegadores/casos por la distancia en el DOM y el color heredado equivocado; se corrigió definiendo un `<marker>` local con el color correcto en cada SVG que lo necesitaba, verificado con capturas de Playwright antes y después."
accion: "(1) Antes de dar por completo cualquier entregable HTML nuevo, comparar su conteo de secciones/SVG/cards contra el de la unidad anterior más reciente — si la diferencia es grande y no se explica por menos material fuente en el PDF, enriquecer antes de entregar, no esperar a que el estudiante lo señale. (2) Al planear cualquier SVG nuevo, clasificarlo primero: ¿es un diagrama de datos (flujo, comparación, línea de tiempo con cifras) → construir directo en el HTML; o es una escena editorial/metáfora conceptual (anclar en un lugar y personas concretas, o ilustrar una idea abstracta de forma memorable) → SIEMPRE dejar una tarjeta `.img-request` + entrada en 'Pedidos de Imagen - Unidad [N].md', nunca construirla directo aunque sea rápido hacerlo. (3) Si un SVG reutiliza un `<marker>` definido en otro bloque `<svg>` del mismo documento, mejor definir el marker localmente dentro de cada `<svg>` que lo usa (con el color correcto para ese diagrama) — la referencia cruzada entre `<svg>` distintos puede fallar de forma inconsistente."
---

# Unidad 2 — Pase de enriquecimiento (2026-09-04, tarde)

## Contexto

El mismo día que se entregó el material inicial de Unidad 2, el estudiante pidió compararlo contra
Unidad 1 y notó que el HTML estaba "bien pobre de información" en comparación. Pidió mejorar el
contenido y agregar más SVG para comprensión visual y aprendizaje.

## Qué se hizo

- Panel 1: de 3 a 6 secciones numeradas. Nuevas: "Formación de la Sociedad Anónima" (línea de tiempo
  legal), "Los cuatro valores de una acción" (comparación visual nominal/libros/mercado/liquidación),
  "Panorama: tres momentos en la vida del capital" (emisión/operación/reporte). Se agregó una caja
  "Profundización teórica" conectando el tema con Unidad 1 (por qué el capital nunca pasa por el
  Estado de Resultados), y un diagrama de prelación de pago dentro de la sección de comunes vs.
  preferentes.
- Panel 2: se agregó el Ejercicio 3 completo (declaración y pago de dividendo preferente, DEF, S.A.
  de C.V., diapositiva 31 — cifras que ya estaban en el Excel pero nunca se habían mostrado resueltas
  en el HTML), con su propia línea de tiempo de declaración/pago y caja de errores comunes.
- Panel 3: diagrama de la cadena de fórmulas entre hojas (Hoja 3 → Hoja 5 → Hoja 7).
- Panel 4: quiz de 10 a 14 preguntas (se agregaron 2 media + 1 fácil + 1 difícil, cubriendo el
  Ejercicio 3 nuevo y la formación de la S.A.).
- Panel 5: se agregó la parte e) del ejercicio variante (dividendo preferente de Textiles Izalco) con
  su propio diagrama resumen de la emisión.
- Entrega de ilustraciones vectoriales y vinculación: se generaron los 4 diagramas SVG en archivos
  independientes dentro de `assets/img/` (`u2-01-constitucion-sa.svg`, `u2-02-fila-prelacion.svg`,
  `u2-03-oficina-xyz.svg` y `u2-04-textiles-izalco.svg`), siguiendo con rigor la estética limpia,
  esquemática y pedagógica de `u1-02-escalera-isr.svg` (tarjetas con bordes sutiles, porcentajes en
  grande, siluetas humanas outline sencillas y cajas de regla de oro/marco legal en la esquina superior
  derecha).
- Se vincularon en ambos HTML (`Entregables/Unidad 2/` y `docs/unidad-2/`) mediante etiquetas `<img>`
  autónomas dentro de contenedores `.svg-wrap`, evitando incrustar miles de líneas de código SVG en el
  cuerpo del HTML y manteniendo el archivo ligero y mantenible.

## Verificación

1. Playwright: 0 errores de consola/JS en los 5 paneles, quiz completo de 14 preguntas respondido sin
   fallos, botón de revelar solución probado.
2. Verificación técnica de ilustraciones:
   - 0 tarjetas `.img-request` restantes en ambos HTML.
   - Exactamente 4 bloques `.svg-wrap` con `<img src="assets/img/...">` en cada archivo.
   - 100% de paridad byte por byte entre `Entregables/Unidad 2/U2_TransaccionesCapital_ContFinanciera.html`
     y `docs/unidad-2/index.html`.
   - Cero emojis y cero dependencias externas en los 4 SVGs.
   - Tipografías estrictamente limitadas a `Bricolage Grotesque`, `IBM Plex Sans` e `IBM Plex Mono`.
   - Paleta 100% conforme al sistema Fintech Oscuro.
   - Se integraron botones de navegación bidireccional (`.nav-back-btn` en el sidebar y `.hero-back-link` en el hero) para permitir el retorno inmediato a la página principal (`../index.html`), se añadió el `favicon-v8.png` oficial y se conectó la Unidad 2 en los portales raíz (`docs/index.html` y `Entregables/index.html`) con estado 'Disponible'.
   - Balance estructural verificado: `<div>` 186/186, `<svg>` 36/36, `<section>` 19/19.

## Ver también

[[Unidad 2 - Transacciones de Capital]] · [[Aprendizajes Acumulados]] · `Entregables/Unidad 2/Pedidos de Imagen - Unidad 2.md` · `docs/index.html`
