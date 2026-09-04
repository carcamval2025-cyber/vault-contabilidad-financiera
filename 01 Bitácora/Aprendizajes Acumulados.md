---
icon: "🧠"
banner_icon: "🧠"
tags: [curso/contabilidad-financiera, bitácora]
---

# Aprendizajes Acumulados

Esta nota es distinta de [[Bitácora General]]: la Bitácora registra el detalle de cada entrega; esta nota destila **patrones que se repiten** en un checklist corto que se revisa antes de cada entrega nueva. Solo se agrega una regla aquí cuando el mismo tipo de error aparece más de una vez en la Bitácora, o cuando tú marcas explícitamente algo como "esto siempre se te olvida" o "esto siempre te sale bien, sigue así".

## Reglas base (heredadas de las instrucciones del proyecto — punto de partida, no aprendizajes propios)

Estas ya están detalladas en [[Reglas de Precisión Legal y Pedagógica]]; se resumen aquí como el punto de partida contra el que se medirá el aprendizaje real:

- Nunca completar cifras legales de memoria.
- Siempre citar el artículo/ley exacto que respalda un cálculo, o generalizar si el PDF no da el número.
- Siempre los 5 paneles HTML + las 8 hojas de Excel + Simulacro de Control cuando aplique según el calendario.
- Siempre contexto salvadoreño/centroamericano, nunca genérico.

## 🟢 Lo que se hace bien (patrones a mantener)

*Aún no hay suficientes entregas para identificar un patrón. Esta sección se llena a medida que [[Bitácora General]] acumule entradas con "✅ Qué funcionó" repetido.*

## 🔴 Lo que falla con frecuencia (patrones a corregir)

- **Comparar contra la unidad anterior antes de dar por completo un HTML.** En Unidad 2 (2026-09-04) el
  HTML se entregó con menos de la mitad de secciones/SVG/cards que Unidad 1, sin que se detectara antes
  de entregar — el estudiante tuvo que señalarlo. Antes de cerrar cualquier entregable HTML nuevo,
  contar sus secciones (`<h2>`), SVG y cards contra los de la unidad más reciente ya entregada; si la
  diferencia es grande y no se explica por menos material fuente en el PDF de esa unidad, enriquecer
  antes de entregar.
- **No olvidar el protocolo de delegación de ilustraciones (Antigravity/Codex).** Establecido desde
  Unidad 1 en `00 Curso/Sistema de Diseño HTML.md`. En Unidad 2 (2026-09-04) Claude construyó todos los
  SVG nuevos directo en el HTML sin clasificarlos primero — el estudiante tuvo que recordarlo
  explícitamente ("Los pedidos de SVGs deben de ser a Antigravity, recuerda eso"). Regla: todo SVG que
  sea un diagrama de datos (flujo, comparación, línea de tiempo con cifras) se construye directo; todo
  SVG que sea una escena editorial o metáfora conceptual (anclar en un lugar/personas concretas, o
  ilustrar una idea abstracta de forma memorable) se deja como tarjeta `.img-request` + brief en
  `Pedidos de Imagen - Unidad [N].md`, nunca se construye directo aunque sea rápido hacerlo.

## 📌 Preferencias del estudiante sobre el material

*Espacio para preferencias explícitas que no son errores sino gustos — por ejemplo, nivel de dificultad preferido en el Panel 4, tipo de empresas de ejemplo, ritmo de explicación. Se llena solo cuando el estudiante lo indica directamente.*

## Ver también

[[Bitácora General]] · [[Reglas de Precisión Legal y Pedagógica]]
