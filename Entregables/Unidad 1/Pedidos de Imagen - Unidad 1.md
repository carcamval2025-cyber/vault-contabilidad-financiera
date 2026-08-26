---
tags: [curso/contabilidad-financiera, unidad-1, pedidos-de-imagen]
sources: "Generado por Claude a partir de U1_Planillas_ContFinanciera.html (pase de enriquecimiento, 2026-08-26)"
---

# Pedidos de Imagen — Unidad 1 (Planillas)

Este documento es para **Antigravity o Codex** (u otro agente de código con capacidad de generar
gráficos/ilustraciones), no para Claude. Contiene el brief completo de las 4 imágenes que el HTML
de la Unidad 1 ya deja reservadas con una tarjeta de "Pedido de imagen" (borde punteado ámbar) en el
lugar exacto donde deben insertarse.

## Antes de empezar — reglas que no se negocian

1. **Formato: SVG de código, no imágenes rasterizadas (PNG/JPG).** El sistema de diseño de este curso
   ("Fintech Oscuro", ver `00 Curso/Sistema de Diseño HTML.md` en el vault) prohíbe explícitamente
   imágenes externas — todo visual debe ser SVG inline con `viewBox` responsive. Como Antigravity y
   Codex son agentes de código (no modelos de difusión de imágenes), lo natural y lo que cumple la
   regla es que entreguen **el código SVG completo**, no un archivo de imagen binario.
2. **Nunca usar emoji como ícono estructural** dentro del SVG — construir los íconos con `<path>`,
   `<circle>`, `<rect>`, etc., estilo *outline*, igual que los íconos ya existentes en el HTML.
3. **Contexto salvadoreño o centroamericano siempre**, nunca genérico ni de otro país.
4. **No inventar cifras.** Si una ilustración necesita un número (un monto, un porcentaje), debe ser
   uno de los que ya aparecen verificados en el HTML o en el vault — nunca un valor nuevo o
   redondeado "para que se vea bien".
5. Cada entregable final debe ser un bloque `<svg>` completo y autocontenido, listo para pegar dentro
   de un `<div class="svg-wrap">` en el HTML, sin dependencias externas (sin `<image>` con URL, sin
   fuentes que no sean Bricolage Grotesque / IBM Plex Sans / IBM Plex Mono).

## Paleta de colores — usar exactamente estos valores hexadecimales

```
--bg:        #0B0D10   (fondo general, casi negro)
--bg-elev:   #14171C   (fondo de tarjetas/paneles)
--bg-elev2:  #1C2027   (fondo de tarjetas elevadas / filas de tabla)
--border:    #262B33   (líneas y bordes neutros)
--text:      #EDEEF0   (texto principal, casi blanco)
--text-dim:  #9098A6   (texto secundario/gris)
--accent:    #FFB020   (ámbar — color de marca, usar como color dominante)
--accent-2:  #FFD873   (ámbar claro — resaltados, texto sobre fondo oscuro)
--success:   #3ECF8E   (verde — resultados positivos, salario neto, ISSS/salud)
--danger:    #FF5C5C   (rojo suave — alertas, tramo más alto de ISR)
--legal:     #5AC8FA   (azul — todo lo relacionado a marco legal / ISSS)
--patrimonio:#FF6EC7   (rosa — reservado para patrimonio, usar solo si aplica)
```

Tipografía dentro del SVG (usar `font-family` exactamente así):
- Títulos / números grandes: `Bricolage Grotesque` (peso 700–800)
- Texto de apoyo: `IBM Plex Sans` (peso 400–600)
- Cifras, códigos, etiquetas técnicas: `IBM Plex Mono` (peso 400–600), con `font-variant-numeric: tabular-nums` si son números alineados

Fondo siempre oscuro (`#0B0D10` o `#14171C`) — nunca blanco. Sin gradientes decorativos fuera de los
ya usados en el archivo (los `linear-gradient` de fondo del tab activo son la única excepción ya
aprobada). Sin sombras difusas tipo glassmorphism.

## Cómo entregar cada imagen

Para cada ID de abajo: devolver un bloque de código `<svg>...</svg>` completo, lo bastante ligero
para pegarse inline (evitar más de ~150 líneas por SVG). Nombrar el archivo `.svg` con el nombre
sugerido y guardarlo en `assets/img/` dentro de `Entregables/Unidad 1/` del vault. Cuando Navas reciba
el SVG, la integración es: reemplazar el `<div class="img-request">...</div>` completo (buscar por su
`ID` en el comentario `Pedido de imagen · ID img-u1-0X`) por `<div class="svg-wrap">` + el SVG nuevo.

---

## img-u1-01 — Escena editorial: la planilla en una pyme salvadoreña

**Ubicación en el HTML:** Panel 1 (Resumen Visual), justo después del cuadro "📚 Profundización
teórica — ¿por qué la planilla ya es un pasivo...?", antes de la sección "Tres conceptos clave".

**Propósito pedagógico:** dar un ancla visual concreta y humana al concepto abstracto de devengo —
que el estudiante vea "el momento" en que nace el pasivo, no solo la ecuación.

**Contenido sugerido:** una escena de mostrador/oficina pequeña — un local tipo "Repuestos ABC"
(autopartería/ferretería salvadoreña) al cierre del día 31 de mayo. Elementos posibles: una persona
en un escritorio con una calculadora o laptop, un calendario marcando fin de mes, un ícono de
"reloj/check" indicando que el servicio ya se prestó pero el pago aún no sale. Puede incluir texto
mínimo dentro del SVG (ej. "31 MAY" en el calendario) pero sin inventar cifras nuevas.

**Estilo:** ilustración plana (*flat*), líneas outline en `--accent` (#FFB020) y `--legal` (#5AC8FA)
sobre fondo `--bg-elev` (#14171C), consistente con el resto de íconos del archivo (stroke-width
~1.6–1.8, sin relleno sólido salvo acentos puntuales).

**Dimensiones:** `viewBox="0 0 760 260"` aprox. (ancho completo del panel, proporción ~3:1).

**Alt text sugerido:** "Escena de una pequeña empresa salvadoreña al cierre de la planilla de fin de mes."

**Archivo:** `assets/img/u1-01-planilla-pyme.svg`

---

## img-u1-02 — Metáfora ilustrada: "la escalera de los tramos de ISR"

**Ubicación en el HTML:** Panel 1, dentro de la sección "¿Por qué el ISR se calcula por tramos y no
con una sola tasa?", justo después del gráfico de barras técnico que ya existe (el de los 4 tramos
con % y cuota fija) — esta imagen es el complemento *amigable/metafórico* de ese gráfico técnico, no
un reemplazo.

**Propósito pedagógico:** reforzar con una metáfora visual — no solo con números — que el ISR es
progresivo *sobre el exceso*, no sobre el total. Es el error conceptual más frecuente en esta unidad
según la Profesora Caballero (confundir "cae en el tramo IV" con "todo se grava al 30%").

**Contenido sugerido:** una escalera de 4 escalones ascendentes. Cada escalón representa un tramo
(0%, 10%, 20%, 30%) y solo la porción de la altura de ese escalón que sobrepasa el escalón anterior
se pinta con su color — para transmitir visualmente "solo lo que excede se grava al nuevo porcentaje".
Puede incluir una figura humana simple subiendo la escalera como referencia de escala, y etiquetas de
los 4 porcentajes (0%, 10%, 20%, 30%) ya verificados en el HTML — no agregar montos nuevos.

**Estilo:** colores progresivos usando `--border` (tramo 0%), `--accent` en opacidades crecientes
(tramos 10% y 20%) y `--danger` (tramo 30%) — igual que el gráfico técnico ya existente, para que
ambos "hablen el mismo idioma" visual.

**Dimensiones:** `viewBox="0 0 500 320"` aprox. (más vertical que horizontal, por la escalera).

**Alt text sugerido:** "Escalera de cuatro escalones representando los tramos progresivos de retención de ISR, donde solo la porción que excede cada escalón se grava al porcentaje superior."

**Archivo:** `assets/img/u1-02-escalera-isr.svg`

---

## img-u1-03 — Escena editorial: Repuestos ABC calculando la planilla de mayo

**Ubicación en el HTML:** Panel 2 (Ejercicio Resuelto), justo después de la tabla con los datos de
Ana Martínez y Juan López, antes del cuadro teórico "por qué son tres partidas y no una sola".

**Propósito pedagógico:** anclar el ejercicio resuelto (el más largo e importante del material) en un
lugar y unas personas concretas, para que los 7 pasos que siguen se sientan como "resolver el caso de
Ana y Juan", no como álgebra abstracta.

**Contenido sugerido:** interior de una autopartería salvadoreña sencilla — mostrador con repuestos
visibles de forma esquemática (llantas, filtros, cajas), una vendedora (Ana) atendiendo y un gerente
(Juan) revisando papeles/una laptop con la planilla del mes. Nada de rostros detallados — estilo
icónico/geométrico, coherente con el resto del archivo.

**Estilo:** misma paleta ámbar/azul sobre fondo oscuro; puede incluir el logotipo esquemático de
"Repuestos ABC" como texto en `IBM Plex Mono`.

**Dimensiones:** `viewBox="0 0 760 280"` aprox.

**Alt text sugerido:** "Interior de la autopartería Repuestos ABC, con la vendedora Ana y el gerente Juan revisando la planilla de mayo."

**Archivo:** `assets/img/u1-03-repuestos-abc.svg`

---

## img-u1-04 — Escena editorial: Café Aroma de Ahuachapán

**Ubicación en el HTML:** Panel 5 (Ejercicio Variante), justo después del párrafo "Se pide: (1)...(2)...(3)...", antes del botón "Ver solución →".

**Propósito pedagógico:** dar al ejercicio variante (con una empresa nueva) el mismo tratamiento
visual que el Ejercicio 1, para que el estudiante practique el mismo razonamiento en un contexto
distinto sin sentir que es "menos importante" por venir al final.

**Contenido sugerido:** una caficultora/tienda de café artesanal en Ahuachapán — sacos de café,
una prensa o molino esquemático, una cajera (Marta) en el mostrador y un supervisor de planta
(Ricardo) de fondo. Paisaje de fondo puede sugerir montaña/volcán de forma muy esquemática (silueta
simple), ya que Ahuachapán es zona cafetalera de montaña — sin inventar datos geográficos específicos
más allá de esa referencia general.

**Estilo:** igual paleta; para diferenciar de la escena de Repuestos ABC (img-u1-03), usar más
proporción de `--success` (#3ECF8E, tono café/verde) en vez de azul, ya que esta es una empresa
distinta.

**Dimensiones:** `viewBox="0 0 760 280"` aprox.

**Alt text sugerido:** "Interior de una caficultora artesanal en Ahuachapán, con la cajera Marta y el supervisor Ricardo."

**Archivo:** `assets/img/u1-04-cafe-aroma.svg`

---

## Checklist antes de entregar cada imagen a Navas

- [ ] Es un bloque `<svg>` de código, no un PNG/JPG adjunto.
- [ ] Usa únicamente los colores hexadecimales de la paleta de arriba.
- [ ] Usa únicamente `Bricolage Grotesque` / `IBM Plex Sans` / `IBM Plex Mono` si lleva texto.
- [ ] No inventa ninguna cifra que no esté ya verificada en `U1_Planillas_ContFinanciera.html` o en el vault.
- [ ] Tiene `role="img"` y `aria-label` con el alt text sugerido (o uno equivalente).
- [ ] El `viewBox` es responsive (sin ancho/alto fijo en píxeles que rompa el layout).
- [ ] Contexto salvadoreño/centroamericano explícito, sin elementos genéricos de stock.

## Ver también

`U1_Planillas_ContFinanciera.html` (los 4 pedidos están marcados ahí con tarjetas de borde punteado
ámbar) · `00 Curso/Sistema de Diseño HTML.md` (sistema de diseño Fintech Oscuro completo) ·
`AGENTS.md` (punto de entrada para Antigravity/Codex en este vault)
