---
icon: "📊"
banner_icon: "📊"
tags: [curso/contabilidad-financiera, entregables, diseño]
---

# Sistema de Diseño — Entregable 2 (Excel, 8 hojas)

Resumen de referencia rápida. La especificación completa vive en las instrucciones maestras del proyecto.

## Estructura general (fija en número, adaptable en contenido)

| Hoja | Contenido |
|---|---|
| 1. 📋 Inicio | Portada, código de honor, datos del estudiante, guía visual, leyenda de colores |
| 2. ⚖️ Marco Normativo | Artículos y tablas oficiales del tema, **copiadas tal cual del PDF de la clase** |
| 3. 🧮 Cálculo [Tema] | Cálculo principal resuelto (ejemplo) |
| 4. 🧮 Cálculo Práctica | Plantilla en blanco |
| 5. 📒 Asientos Resueltos | Libro diario, enlazado por fórmulas a la Hoja 3 |
| 6. 📒 Asientos Práctica | Plantilla en blanco |
| 7. 📊 Producto Final | El entregable que pide la profesora para esa unidad, resuelto |
| 8. 📊 Producto Final Práctica | Plantilla en blanco del mismo producto |

## 🧮 Qué va en las Hojas 3-4, 5-6 y 7-8 según la unidad

| Unidad | Hoja 3-4 (Cálculo) | Hoja 7-8 (Producto Final) |
|---|---|---|
| 1. Planillas | Cédula de planilla: sueldo, horas extra, ISSS 3%, AFP 7.25%, ISR, salario neto + aportes patronales | Cédula de prestaciones laborales (vacaciones, aguinaldo, indemnización, renuncia voluntaria) |
| 2. Transacciones de capital | Emisión de acciones comunes/preferentes (nominal, prima/descuento, mercado) | Sección de Patrimonio del Balance General |
| 3. Impuesto sobre la Renta | Retención mensual con recálculo junio/diciembre | Formulario resumen de declaración (persona natural asalariada / rentas diversas / jurídica) |
| 4. Conciliación bancaria | Conciliación por saldos y por saldos ajustados | Cédula final de partidas con saldo conciliado |
| 5. Flujo de efectivo | Clasificación operación/inversión/financiamiento | Estado de Flujo directo **y** indirecto, enlazado a ER y BG |
| 6. Bonos | Valor actual del bono | Tabla de amortización completa |
| 7. Análisis de EF | Análisis vertical y horizontal de ER y BG | Cédula de razones financieras con interpretación escrita |

**No** se usa la misma estructura de Estado de Resultados / Balance General / ECP para todas las unidades — depende de la matriz de arriba.

## Reglas técnicas que no se rompen

- Fórmulas `=SUM()`, `=SUMIF()`, `=VLOOKUP()` — **nunca valores hardcodeados** en cálculos.
- Cero errores de fórmula (`#REF!`, `#DIV/0!`, `#VALUE!`, `#N/A`).
- `freeze_panes` en la fila de encabezados.
- Celdas de práctica en rosa `#FFF0F5`; texto guía en gris.
- Convención de color de texto: azul `#0000FF` = valores de entrada editables, negro = fórmulas/cálculos, gris `#5A6480` = notas.
- Nombre del archivo: `U[X]_[NombreTema]_ContFinanciera.xlsx`.

## Ver también

[[Sistema de Diseño HTML]] · [[Reglas de Precisión Legal y Pedagógica]] · [[Aprendizajes Acumulados]]
