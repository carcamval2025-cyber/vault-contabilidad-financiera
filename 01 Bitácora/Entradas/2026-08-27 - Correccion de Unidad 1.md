---
tags: [meta, bitacora, entrada]
fecha: 2026-08-27
unidad: "1"
entregables: "Entregable 1 (HTML) + Entregable 2 (Excel) — corrección de contenido faltante en Panel 1 y de una fórmula legalmente incorrecta en la Hoja 7/8"
funciono: "El estudiante señaló que el material 'no tiene bastantes cosas que sí deberían estar' y que no era suficientemente visual respecto al PDF. Se releyó el PDF completo (47 diapositivas) y se contrastó por conteo de términos contra el HTML ya entregado: Aguinaldo, Indemnización, Renuncia Voluntaria, Comisiones y Bonificaciones aparecían mencionadas como máximo una vez (solo como referencia a la Hoja 7 del Excel), aunque el propio HTML ya tenía una caja de Marco Legal citando Art. 177/179/169 sin que el cuerpo del texto explicara esos temas. Se agregaron 4 bloques teóricos nuevos al Panel 1 (Jornadas y horas extra; Prestaciones laborales — vacaciones, aguinaldo con tabla de antigüedad y gráfico de barras SVG, indemnizaciones con las 4 formas de terminación de contrato, renuncia voluntaria, comisiones y bonificaciones; Salario mínimo vigente por sector; tabla de síntesis ISSS/AFP/ISR por concepto), todos con cifras y artículos verificados contra el PDF, una caja ⚠️ de errores comunes, la caja de Marco Legal ampliada y 7 términos nuevos en el glosario. Se agregaron 3 preguntas nuevas al quiz (13 en total) cubriendo estos temas, corrigiendo además el conteo hardcodeado '/10' del JavaScript por `QUESTIONS.length` para que no vuelva a quedar desincronizado si se agregan preguntas en el futuro."
fallo: "Al revisar la Hoja 7 del Excel para confirmar que ya cubría bien las prestaciones, se encontró que la fórmula de Indemnización (columna L) nunca aplicaba el tope legal del Art. 58 del Código de Trabajo (ningún salario diario puede considerarse superior a 4 salarios mínimos diarios para este cálculo) — calculaba simplemente sueldo mensual × años de servicio. Para Juan López (sueldo $2,500, salario diario $83.33, muy por encima del tope de $54.51), esto sobrestimaba su indemnización en cerca de $10,376 ($30,000 calculado vs. $19,623.60 correcto). El mismo error existía en la Hoja 8 (Práctica). La columna de Renuncia Voluntaria sí aplicaba correctamente su propio tope (2 salarios mínimos diarios), lo que hizo más fácil notar la inconsistencia."
accion: "Cuando se revise contenido ya entregado por queja de que 'falta algo', no basta con comparar el texto contra el PDF — también hay que revisar que las fórmulas del Excel apliquen TODOS los topes legales mencionados en el propio Marco Legal del HTML, no solo los que se ven a simple vista (el de renuncia voluntaria sí estaba bien, lo cual pudo dar una falsa sensación de que todo estaba correcto). Se recalculó todo el libro con LibreOffice headless tras el cambio y se confirmó cero errores de fórmula (#REF!/#DIV/0!/#VALUE!/#N/A) antes de entregar."
---

# Corrección de contenido faltante — Unidad 1 (2026-08-27)

## Qué se agregó al HTML (Panel 1 — Resumen Visual)

- **Bloque 6 — Jornadas de trabajo y horas extra:** tabla diurna/nocturna (Art. 161 CT) y caja de Marco Legal sobre el recargo del 100% por hora extra (Art. 169 CT), incluyendo las excepciones de hora extra permanente.
- **Bloque 7 — Prestaciones laborales:** resumen visual de las 6 prestaciones (grid de tarjetas) y desarrollo teórico completo de cada una — vacaciones (con el +30% y el +25% por alojamiento/alimentación interrumpidos), aguinaldo (tabla de antigüedad + gráfico de barras SVG nuevo), indemnizaciones (despido de hecho, indirecto, incausado y *ante tempus*, con sus topes), renuncia voluntaria (tabla de requisitos), comisiones y bonificaciones — cerrando con una caja ⚠️ de errores comunes.
- **Bloque 8 — Salario mínimo vigente:** tabla por sector económico (Industria, Comercio y servicios, Maquila, Agrícola), con la fuente y fecha de vigencia explícitas, tal como exige el sistema de diseño para tablas legales/normativas.
- **Bloque 9 — Síntesis:** tabla final que conecta cada concepto salarial (ISSS, AFP, ISR, vacaciones, aguinaldo, indemnización, maternidad) con su tratamiento fiscal — tomada directamente de la diapositiva de cierre del PDF de la profesora.
- Caja de Marco Legal del panel ampliada con los artículos 161, 49/50/53, 58 y 59 del Código de Trabajo, la Ley Reguladora de la Prestación Económica por Renuncia Voluntaria y el Art. 4 de la Ley del ISR.
- 7 términos nuevos en el glosario del Panel 1 y 3 preguntas nuevas en el quiz del Panel 4 (13 preguntas en total: 4 fáciles, 5 medias, 4 difíciles).

## Qué se corrigió en el Excel

`7. Producto Final` y `8. Producto Final Práct.`, columna Indemnización: se agregó el tope de 4 salarios mínimos diarios (Art. 58, Código de Trabajo) a la fórmula, siguiendo el mismo patrón que ya usaba la columna de Renuncia Voluntaria con su tope de 2 salarios mínimos. Se agregó una nota en `2. Marco Normativo` documentando este tope. Verificado con LibreOffice headless: cero errores de fórmula en todo el libro.

## Archivos actualizados (en ambas copias — Entregables/ y docs/unidad-1/, mantenidas idénticas)

- `Entregables/Unidad 1/U1_Planillas_ContFinanciera.html` y `docs/unidad-1/index.html`
- `Entregables/Unidad 1/U1_Planillas_ContFinanciera.xlsx` y `docs/unidad-1/U1_Planillas_ContFinanciera.xlsx`

## Cambio adicional — emojis reemplazados por íconos SVG (mismo día)

El estudiante pidió explícitamente ("sí o sí") quitar todos los emojis del HTML y sustituirlos por íconos. Se reemplazaron las 22 apariciones (chips del hero, cajas ⚖️ Marco Legal / 🎯 Evaluación / ⚠️ Error / ✅ OK / 📚 Profundización teórica, las 6 tarjetas de prestaciones del Panel 1, el ícono dentro del mock de Excel del Panel 3, y los 3 emojis generados por JavaScript en la retroalimentación del quiz y el badge de nivel) por SVG outline en línea, coherentes con el estilo ya usado en las pestañas de la barra lateral y en las tarjetas "Tres conceptos clave" (ícono en un `div.ic` de 36×36 sobre el `<h4>` para tarjetas, o `<svg>` en línea de 13-15px antes del texto para chips y encabezados de caja). Las 6 tarjetas de prestaciones (Vacaciones, Aguinaldo, Indemnización, Renuncia voluntaria, Comisiones, Bonificaciones) se reestructuraron para seguir ese mismo patrón de ícono, en vez de dejar el emoji suelto dentro del `<h4>` como se había hecho al agregarlas horas antes.

**Nota para el estudiante:** las instrucciones maestras del proyecto (sección "🎨 SISTEMA DE DISEÑO HTML") piden explícitamente emojis en las cajas especiales (🎯/⚠️/✅/⚖️). Este cambio es una excepción para la Unidad 1 por instrucción directa tuya; si quieres que aplique a todas las unidades futuras, conviene actualizar esas instrucciones del proyecto en Claude para que no haya que repetir el pedido cada vez.

Verificado con el mismo método de siempre: conteo de etiquetas balanceado (div/section/table/ul/svg/h2/h3/h4), render en Playwright sin errores de consola nuevos, y capturas de pantalla del hero, el bloque de prestaciones, el marco legal, el mock de Excel y la retroalimentación del quiz.

## Tercer cambio — 3 diagramas SVG nuevos (mismo día)

El estudiante notó que, tras quitar los emojis, varios de los bloques agregados en la primera corrección (Bloque 6, 7 y 8) seguían siendo solo texto y tabla, sin apoyo visual — la queja original era justamente que el material fuera "más visual que el PDF". Se agregaron 3 diagramas SVG nuevos, en el mismo estilo que el gráfico de barras del aguinaldo ya existente:

- **Línea de tiempo de 24 horas** (jornada diurna 6am–7pm vs. nocturna 7pm–6am), con los límites legales de cada una y un marcador de "+1h = hora extra, +100% de recargo" — insertada antes de la caja de Marco Legal de horas extra.
- **Comparativo visual de los 4 tipos de despido** (de hecho, indirecto, incausado Art. 58, ante tempus Art. 59) con el monto/tope de cada uno, colocado antes de las tarjetas de texto que ya explicaban cada tipo en detalle.
- **Gráfico de barras del salario mínimo por sector** (Industria/Comercio $408.80, Maquila $402.32, Agrícola caña/beneficio de café $305.23, Agrícola recolección de café/agropecuario $272.53), debajo de la tabla ya existente.

Todas las cifras se tomaron de las tablas ya verificadas contra el PDF en la primera corrección de este mismo día — no se agregó ningún dato nuevo, solo la representación visual. Verificado igual que los cambios anteriores (balance de etiquetas, render en Playwright, capturas de pantalla de los tres diagramas).

## Cuarto cambio — botón de descarga del Excel + Ejercicios 3, 4 y 5 de la guía (mismo día)

El estudiante señaló dos cosas: (1) el HTML describe las 8 hojas del Excel pero nunca ofrece un enlace para descargarlo, y (2) en la carpeta de la materia hay más ejercicios de la guía de la profesora (un PDF y su solución en Excel) que no se habían revisado.

**Botón de descarga:** se agregó un botón estilizado (`.dl-btn`, mismo patrón visual que `.reveal-btn`) al inicio del Panel 3 — Guía Excel, con enlace directo a `U1_Planillas_ContFinanciera.xlsx` y un ícono SVG de descarga.

**Ejercicios adicionales encontrados:** al revisar "Ejercicios clase planillas.pdf" y su solución en Excel, se confirmó que el Panel 2 solo cubría el Ejercicio 1 (Repuestos ABC) de la guía, dejando sin resolver el Ejercicio 3 (liquidación por despido incausado), el Ejercicio 4 (aguinaldo con menos de 1 año de servicio) y el Ejercicio 5 completo (planilla con horas extra, planilla de aguinaldos, y un adelanto del recálculo de ISR). El estudiante pidió agregar los tres al Panel 2, con el mismo nivel de detalle paso a paso que ya tenía el Ejercicio 1. Se agregaron como bloques nuevos, después de la caja de Marco Legal y Errores del Ejercicio 1, y antes del glosario del panel (que se amplió con 5 términos nuevos: Liquidación, Indemnización, Recargo por hora extra, Ingreso base de cotización y Recálculo de ISR).

**Tres hallazgos en la hoja de solución de la profesora — para confirmar con ella:**

1. **Fórmula de INCAF en el Ejercicio 3:** la hoja de la profesora calcula el INCAF patronal de ABC, S.A. de C.V. como si tuviera el mismo tope de $1,000 que el ISSS (resultado: $10.00), pero el material teórico de la Unidad 1 indica que el INCAF se calcula sobre el monto total de planillas, sin tope, para empresas con 10 o más empleados. Con 14 empleados y sin tope, el valor correcto es $27.30. Todo indica que fue un error de copiar la fórmula del ISSS. El HTML presenta el valor correcto ($27.30) con una nota transparente explicando la diferencia.
2. **Tabla de ISR desactualizada en la pestaña "Ejercicio 5":** esa pestaña específica usa una tabla de ISR mensual con el Tramo I hasta $472.00, mientras que la tabla vigente (ya confirmada en el Marco Normativo propio y en la propia pestaña "CALCULO" de la profesora, en el mismo archivo) tiene el Tramo I hasta $550.00. Esto afecta el ISR de María Leonor y de Lucía en la planilla de horas extra (Ejercicio 5.1) y el de José Rigoberto en la planilla de aguinaldos (Ejercicio 5.2). El HTML usa la tabla vigente y marca la diferencia en una caja de advertencia.
3. **Recálculo de ISR (Ejercicio 5.3):** las cifras mes a mes de esta pestaña no coinciden ni con la tabla de $472 ni con la de $550 — parecen venir de una tercera versión de la tabla. Por eso este ejercicio no se resolvió con números en el HTML; se dejó solo el enunciado y una explicación conceptual del recálculo, indicando que se resolverá a fondo en la Unidad 3, que es donde el programa del curso trata este tema en detalle.

Verificado igual que los cambios anteriores: balance de etiquetas HTML, render en Playwright sin errores de consola nuevos, y capturas de pantalla de los 5 bloques nuevos, incluyendo las dos cajas de discrepancia y el glosario ampliado. Además, se reordenó el contenido para que la caja "Marco Legal aplicado en este ejercicio" y "Errores más comunes" del Ejercicio 1 queden inmediatamente después de ese ejercicio (y no después de los 4 ejercicios nuevos, donde habían quedado tras la primera inserción).

## Ver también

[[Unidad 1 - Pasivo Corriente (Planillas)]] · [[2026-08-26 - Unidad 1 Entregables]] · `02 Curso/Sistema de Diseño HTML.md` (si el estudiante quiere revisar el mismo tipo de auditoría de completitud para futuras unidades)
