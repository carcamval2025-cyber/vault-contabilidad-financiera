---
icon: "🧩"
banner_icon: "🧩"
tags: [curso/contabilidad-financiera, bitácora, plantilla]
---

# Plantilla — Entrada de Bitácora

Cada entrega genera **una nota nueva** dentro de `01 Bitácora/Entradas/`, nombrada `AAAA-MM-DD - [Unidad o tema].md`. La tabla de [[Bitácora General]] se arma sola con Dataview a partir de estas notas — no hace falta tocar esa nota directamente.

## Frontmatter a copiar en la nota nueva

```yaml
---
icon: "🗂️"
banner_icon: "🗂️"
tags: [curso/contabilidad-financiera, bitácora, entrada]
fecha: AAAA-MM-DD
unidad: "[Unidad X - Nombre]"
entregables: "[HTML / Excel / Simulacro de Control — cuáles se generaron]"
funciono: "[Qué salió bien, con detalle: qué panel/hoja, por qué funcionó]"
fallo: "[Qué falló, con detalle: qué panel/hoja/celda, cuál fue el error exacto]"
accion: "[Qué debe hacer Claude distinto la próxima vez en esta unidad o en general]"
---
```

Debajo del frontmatter, desarrolla los mismos puntos en prosa (el frontmatter alimenta la tabla resumen; el cuerpo de la nota es donde va el detalle completo, capturas, o ejemplos concretos).

## Guía para que la entrada sea útil de verdad

- **Sé específico, no genérico.** "El Excel tenía un error" no ayuda. "La fórmula de la Hoja 3, columna F, no aplicó el tope de $1,000 en la base ISSS" sí ayuda — y permite que la próxima sesión lo evite.
- **Distingue error de diseño vs. error de contenido/legal.** Un error de paleta de colores no es lo mismo que una cifra de ISR mal aplicada — esto último es mucho más grave según [[Reglas de Precisión Legal y Pedagógica]].
- **Si el mismo tipo de error aparece 2 o más veces**, pídele a Claude que lo agregue como regla en [[Aprendizajes Acumulados]], no solo en esta nota.
- **También registra lo que funcionó bien**, no solo los errores — así se sabe qué mantener.
- **Enlaza la nota de la unidad correspondiente** (ej. `[[Unidad 1 - Pasivo Corriente (Planillas)]]`) para poder navegar de la unidad a su historial de entregas y viceversa.
