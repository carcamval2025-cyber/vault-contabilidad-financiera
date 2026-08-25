---
icon: "🎨"
banner_icon: "🎨"
tags: [curso/contabilidad-financiera, entregables, diseño]
---

# Sistema de Diseño — Entregable 1 (HTML, 5 paneles)

Resumen de referencia rápida. La especificación completa y obligatoria vive en las instrucciones maestras del proyecto — esta nota es para consulta rápida y para anotar cuando algo del diseño falló en la práctica (ver [[Aprendizajes Acumulados]]).

## Estructura fija

Un solo HTML, barra lateral izquierda + 5 paneles:

1. **Resumen Visual** — SVG del concepto central, 3 cards de conceptos clave, tabla con badges y ejemplos salvadoreños, caja ⚖️ Marco Legal, caja 🎯 cobertura en Parcial/Control, glosario.
2. **Ejercicio Resuelto** — el ejercicio exacto de la guía de la profesora, steps numerados con razonamiento y referencia legal, caja ⚠️ errores comunes, glosario.
3. **Guía Excel** — SVG preview del Excel, instrucciones paso a paso, caja ✅ código de honor, glosario de funciones.
4. **Quiz de Práctica** — mínimo 10 preguntas (3 fáciles + 4 medias + 3 difíciles), retroalimentación inmediata, glosario.
5. **Ejercicio Variante** — empresa salvadoreña/centroamericana nueva, misma estructura, solución oculta con botón, glosario.

## Paleta

```
--navy: #1e2d5a   --navy2: #2C3E6B   --navy3: #3d5491
--rose: #E8A0B4   --rose2: #d4718e   --rose3: #f5c8d6
--green: #7CB342  --green2: #5a8a2e
--bg: #F0F4FA     --white: #ffffff
--text: #1A1A2E   --muted: #5a6480
```

Tipografía: **Playfair Display** (títulos, itálica para énfasis) + **DM Sans** (cuerpo, 300/400/500/600). Nunca Inter, Roboto o Arial.

## Cajas especiales (obligatorias donde aplique)

| Caja | Fondo / borde / texto |
|---|---|
| 🎯 Evaluación | #FFF8E1 / #F9A825 / #5d4037 |
| ⚠️ Error | #FDECEA / #E53935 / #7b1b1b |
| ✅ OK | #E8F5E9 / #7CB342 / #1b5e20 |
| ⚖️ Marco Legal | #EAF0FA / #2C3E6B / #1e2d5a |

La caja **⚖️ Marco Legal** es obligatoria en Paneles 1 y 2 — cita el artículo o ley exacta (ej. "Art. 177, Código de Trabajo").

## Reglas que no se rompen

- Todo visual en SVG inline, nunca imágenes externas.
- Nunca omitir ninguno de los 5 paneles ni el glosario de cada uno.
- Nunca usar ejemplos genéricos — siempre contexto salvadoreño o centroamericano.
- Quiz siempre con retroalimentación inmediata pregunta por pregunta (a diferencia del Simulacro de Control, que es modo examen).

## Ver también

[[Sistema de Diseño Excel]] · [[Reglas de Precisión Legal y Pedagógica]] · [[Aprendizajes Acumulados]]
