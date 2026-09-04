---
icon: "🗂️"
banner_icon: "🗂️"
tags: [curso/contabilidad-financiera, bitácora, entrada]
fecha: 2026-09-04
unidad: "Unidad 2 - Transacciones de Capital"
entregables: "Entregable 1 (HTML, 5 paneles) + Entregable 2 (Excel, 8 hojas). No aplica Entregable 3 (sin Control esta semana)."
funciono: "Se leyeron completos los 4 PDFs de la semana (Unidad 2 Transacciones de capital.pdf, 39 diapositivas; Acciones de Tesorería.pdf, 4 diapositivas; Ejercicios clase acciones.pdf; Caso I Sección 2.pdf) y los dos Excel de solución de la profesora (Unidad 2 ejercicios.xlsx, Ejercicios Acc Tesoreria.xlsx) antes de generar nada, siguiendo el protocolo del vault. El HTML sigue el sistema de diseño Fintech Oscuro vigente, con SVG en absolutamente todo (cero emoji, incluida la retroalimentación del quiz) — el estudiante confirmó explícitamente que esto es la regla fija desde ahora, no una excepción de la Unidad 1 (ver cambio en 00 Curso/Sistema de Diseño HTML.md). El Excel (8 hojas) recalculó sin errores de fórmula en LibreOffice headless al primer intento tras corregir 4 celdas con texto que empezaba por '=' (ver 'falló' abajo). Los montos del Ejercicio 1 (patrimonio final $2,660,000) coinciden exactamente entre el HTML y el Excel — se verificó cruzando ambos archivos, no solo cada uno por separado."
fallo: "1) El archivo 'Caso I Sección 2.pdf' — el caso graduado que se entrega el sábado 6 de septiembre — resultó ser en realidad un caso completo de Planillas (aguinaldos, bonificación, recálculo de ISR, liquidación, renuncia voluntaria), no de Transacciones de Capital, a pesar de aparecer en la semana 2 del calendario. No se detectó hasta leer el PDF completo. 2) Se encontraron 3 discrepancias en los Excel de solución de la profesora (hoja 'Ejercicios1' con cifras obsoletas distintas al PDF vigente; anotación de texto '$0.44 por acción común' que no coincide con el resultado real de la fórmula, que da $0.38; cifras de capital contable en la parte D) del ejercicio de tesorería que no aparecen en el enunciado del PDF, solo en la hoja de solución) — se documentaron todas en la nota de la unidad en vez de copiarlas sin verificar. 3) Bug propio: al escribir la leyenda de colores de la Hoja 1 del Excel ('Texto azul = valor de entrada...'), el signo '=' al inicio del texto hizo que Excel lo interpretara como fórmula, generando #VALUE!/#N/A en 4 celdas — se detectó con recalc.py y se corrigió quitando el '=' inicial. Registrar este patrón en Aprendizajes Acumulados porque es un error mecánico fácil de repetir en futuras unidades."
accion: "Para toda unidad futura: (a) nunca escribir un texto de celda de Excel que empiece literalmente con '=' sin verificar que no se quiera como fórmula — revisar con recalc.py antes de dar por terminado; (b) cuando el PDF del 'Caso' semanal no coincida temáticamente con la unidad de la semana (como pasó aquí), leerlo completo de todas formas y documentar la discrepancia en la nota de la unidad en vez de asumir que aplica; nunca resolver el caso graduado completo por el estudiante, ya que es trabajo individual con código de honor propio — ofrecer solo repaso de conceptos; (c) cuando un Excel de solución de la profesora tenga una anotación de texto y una fórmula que no coinciden entre sí, confiar en el resultado de la fórmula (verificable) y no en el texto (puede quedar desactualizado de una versión anterior del archivo)."
---

# Entregables de la Unidad 2 — Transacciones de Capital (2026-09-04)

## Qué se generó

- **HTML** (`U2_TransaccionesCapital_ContFinanciera.html`): 5 paneles completos siguiendo el sistema Fintech Oscuro — Resumen Visual (diagrama de flujo del ciclo de capital, tabla comparativa comunes/preferentes, Marco Legal, cobertura de evaluaciones, glosario de 13 términos), Ejercicio Resuelto (Ejercicio 1 completo de la guía — emisión XYZ, S.A. de C.V. — más el ejemplo de valor en libros de la diapositiva 24 y el Ejercicio 2 completo de tesorería ABC, S.A. de C.V., con sus 4 partes A-D), Guía Excel (vista previa SVG de la Hoja 7, instrucciones paso a paso, código de honor), Quiz de Práctica (10 preguntas: 3 fáciles + 4 medias + 3 difíciles, retroalimentación inmediata con íconos SVG en vez de ✓/✗ de texto), Ejercicio Variante (Textiles Izalco, S.A. de C.V. — empresa textil de Sonsonate — con solución oculta tras botón).
- **Excel** (8 hojas): Inicio, Marco Normativo (capital mínimo $2,000, 5% pagado a inscripción, dividendo preferente mín. 6%, ISR 5% sobre dividendos — todo del PDF, sin inventar artículos numerados porque el PDF no los da), Cálculo Emisión (resuelta, Ejercicio 1), Cálculo Práctica (empresa nueva, Ceiba Andina S.A. de C.V.), Asientos Resueltos (emisión + declaración/pago de dividendo preferente con retención de ISR, enlazado por fórmulas a la Hoja 3), Asientos Práctica, Producto Final (sección de Patrimonio del Balance General, enlazada a la Hoja 3 — Patrimonio total $2,660,000) y Producto Final Práctica.

## Discrepancia importante — Caso 1 no es de esta unidad

El PDF `Casos/Caso I Sección 2.pdf` es un caso de Planillas (Unidad 1), no de Transacciones de Capital, aunque se entrega en la semana 2. Se documentó en `02 Unidades/Unidad 2 - Transacciones de Capital.md` y se le avisó al estudiante en el chat y en un chip de advertencia dentro del propio HTML. No se resolvió el caso (es individual, graduado, con código de honor propio) — se ofreció repasar Planillas si lo necesita.

## Verificación realizada

- Lectura completa de los 4 PDFs de la semana antes de generar cualquier cosa.
- Playwright: render de los 5 paneles sin errores de consola (salvo un `ERR_CONNECTION_RESET` de la fuente de Google Fonts, propio del sandbox de esta sesión, no del archivo), captura de pantalla de cada panel, prueba del quiz (respuesta correcta) y del botón de revelar solución del Panel 5.
- Balance de etiquetas HTML (`div`, `section`, `table`, `svg`, `h2`, `h4`, `ul`, `li`) — todos coinciden.
- Cero emoji en todo el archivo (se verificó con una búsqueda de rango Unicode de emoji) — solo quedaban dos símbolos ✓/✗ en el JavaScript del quiz, que se reemplazaron por SVG inline.
- `recalc.py` (LibreOffice headless) sobre el Excel: `errors_found` con 4 errores en el primer intento (ver "falló" arriba) → corregidos → segunda pasada: `status: success`, 0 errores en 26 fórmulas.
- Cifras cruzadas entre HTML y Excel: patrimonio total de $2,660,000 coincide en ambos archivos.

## Archivos actualizados (en ambas copias — Entregables/ y docs/unidad-2/, mantenidas idénticas)

- `Entregables/Unidad 2/U2_TransaccionesCapital_ContFinanciera.html` y `docs/unidad-2/index.html`
- `Entregables/Unidad 2/U2_TransaccionesCapital_ContFinanciera.xlsx` y `docs/unidad-2/U2_TransaccionesCapital_ContFinanciera.xlsx`
- `docs/index.html` — tarjeta de Unidad 2 cambiada de "Próximamente" a "Disponible", enlazando a `unidad-2/`.

## Ver también

[[Unidad 2 - Transacciones de Capital]] · [[Sistema de Diseño HTML]] (actualizado: SVG en todo es ahora regla fija, no excepción de Unidad 1)
