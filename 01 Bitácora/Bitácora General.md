---
icon: "📒"
banner_icon: "📒"
tags: [curso/contabilidad-financiera, bitácora]
---

# Bitácora General

Registro vivo, **aditivo**, de cada entrega generada para el curso. Esta es la nota que le da sentido al vault: aquí queda constancia de qué funcionó y qué falló, para que la siguiente sesión de Claude no repita el mismo error y para que tú puedas ver tu propio progreso en lo que necesitas reforzar.

Cada entrega es **una nota independiente** dentro de `01 Bitácora/Entradas/` (no una fila más en una tabla gigante) — así cada entrada puede tener su propio detalle, y la tabla de abajo se arma sola gracias a Dataview.

## Cómo agregar una entrada nueva

Después de revisar un entregable (HTML, Excel o Simulacro de Control), pídele a Claude: *"Agrega una entrada a la Bitácora con lo que revisamos de la Unidad X"*. Claude debe crear una nota nueva en `01 Bitácora/Entradas/` siguiendo [[Plantilla - Entrada de Bitácora]] — no editar esta nota directamente, esta tabla se actualiza sola.

## Registro (generado automáticamente)

```dataview
TABLE
  fecha as "Fecha",
  unidad as "Unidad",
  entregables as "Entregables",
  funciono as "✅ Qué funcionó",
  fallo as "⚠️ Qué falló",
  accion as "🎯 Acción siguiente"
FROM "01 Bitácora/Entradas"
SORT fecha DESC
```

> [!tip] Si esta tabla aparece vacía o como texto plano
> Significa que el plugin **Dataview** no está activo en Obsidian. Actívalo en Configuración → Complementos de la comunidad → Dataview. Si prefieres no usarlo, puedes abrir directamente las notas dentro de `01 Bitácora/Entradas/`.

## Ver también

[[Aprendizajes Acumulados]] · [[Reglas de Precisión Legal y Pedagógica]] · [[Inicio]]
