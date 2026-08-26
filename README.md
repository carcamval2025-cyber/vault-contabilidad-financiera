---
icon: "📘"
banner_icon: "📘"
tags: [meta]
---

# README — Cómo usar y mantener este Vault

## Qué es esto

Un Vault de Obsidian pensado para vivir junto a los materiales del curso de Contabilidad Financiera (Sección 2, ESEN, Trimestre 3/2026). No reemplaza las instrucciones maestras del proyecto de Claude — las complementa con dos cosas que las instrucciones del proyecto no pueden hacer por sí solas:

1. **Memoria de contenido navegable**: en vez de tener todo en un solo bloque de instrucciones, cada unidad, cada ley y cada regla de diseño vive en su propia nota, enlazada. Esto te sirve para repasar rápido antes de un Control o Parcial, y le sirve a Claude para no tener que releer los PDFs completos cada vez que solo necesita, por ejemplo, la tasa de AFP.
2. **Bitácora de mejora continua**: un lugar donde queda registrado, entrega tras entrega, qué salió bien y qué hubo que corregir — para que el patrón de errores no se repita y el material vaya mejorando semana a semana.

## Cómo abrirlo en Obsidian

1. Abre Obsidian → "Open folder as vault" → selecciona la carpeta `Vault Contabilidad Financiera` (queda dentro de tu carpeta `Contabilidad Financiera`, junto a los PDFs y Excel del curso).
2. Obsidian creará automáticamente su carpeta de configuración `.obsidian` la primera vez que abras el vault — no necesitas hacer nada más.
3. Los enlaces `[[Así]]` ya están listos para el grafo de Obsidian; explóralo desde el ícono de grafo para ver cómo se conectan las unidades con las leyes que las rigen.

## Flujo de trabajo recomendado, sesión a sesión

1. **Antes de pedirle a Claude el material de una unidad nueva**, abre la nota de esa unidad en `02 Unidades/` y revisa si ya tiene contenido de sesiones previas (ejercicios, dudas, correcciones).
2. **Pide el material como siempre** en el proyecto de Claude ("Nuevo tema: [unidad]" + PDFs).
3. **Después de revisar lo que Claude entregó**, dile qué funcionó y qué no — con la misma conversación o citando la nota de la unidad. Ejemplos:
   - "El quiz del Panel 4 estuvo bien, pero el Excel tenía la fórmula del ISSS mal — se pasó del tope de $1,000."
   - "La Unidad 2 quedó excelente, guárdalo como algo que se hizo bien."
4. **Pídele a Claude que actualice el Vault**: que agregue una fila en [[Bitácora General]], que actualice la nota de la unidad correspondiente, y que — si el error es un patrón que se repite — lo agregue a [[Aprendizajes Acumulados]].
5. Cuando Claude actualice archivos del vault, debe escribirlos directamente en tu carpeta conectada (no solo mostrarlos en el chat), para que ya queden guardados en Obsidian.

## Reglas para mantener el Vault confiable

- **Nunca se completan cifras legales de memoria.** Toda tasa, tramo de ISR, tope o tabla que aparezca en [[Reglas de Precisión Legal y Pedagógica]] y en las notas de `03 Marco Legal/` debe venir del PDF de la profesora o de lo que tú indiques explícitamente. Si una nota tiene un campo marcado como `[Pendiente: verificar con el PDF de la clase]`, significa que aún no hay una fuente confiable — no se debe rellenar por deducción.
- **Cada nota de unidad enlaza a las leyes que la rigen** y viceversa, para poder navegar en ambos sentidos.
- **La Bitácora es aditiva, no se reescribe.** Cada entrega agrega una fila nueva; no se borran entradas anteriores (así el patrón de mejora queda visible en el tiempo).
- Si el calendario de un PDF de clase no coincide con [[Programa y Calendario]], gana el PDF más reciente — se actualiza la nota y se anota la fecha del cambio.

## Estructura de carpetas

```
Vault Contabilidad Financiera/
├── Inicio.md                      → panel principal / mapa de contenido
├── Organigrama.md                 → mapa visual (diagramas) de la estructura y el flujo de trabajo
├── 00 Curso/                      → programa, calendario, sistema de diseño, reglas de precisión
├── 01 Bitácora/                   → registro de aprendizaje sesión a sesión
├── 02 Unidades/                   → una nota por unidad temática (1 a 7)
├── 03 Marco Legal/                → una nota por ley/normativa citada en el curso
├── 04 Glosario.md                 → términos técnicos y legales
├── Plantillas/                    → plantillas para nuevas unidades y entradas de bitácora
└── README.md                      → este archivo
```
