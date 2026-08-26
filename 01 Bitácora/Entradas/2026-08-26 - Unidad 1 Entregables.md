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
