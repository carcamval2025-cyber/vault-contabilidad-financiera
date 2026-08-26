# AGENTS.md — Vault Contabilidad Financiera

Este archivo es el punto de entrada agnóstico de herramienta: cualquier agente de IA
(Claude, Antigravity, Codex, Cursor, Aider, etc.) que abra esta carpeta debe leerlo
primero. A diferencia de `Inicio.md` (pensado para Obsidian: usa `[[wikilinks]]`,
banners y bloques Dataview que solo se renderizan con esos plugins), este documento
usa únicamente markdown plano y rutas de archivo relativas, para que funcione igual
sin Obsidian.

## Qué es esto

Base de conocimiento persistente para el curso **Contabilidad Financiera, Sección 2**
(ESEN, Trimestre 3/2026, profesora Antonia Caballero de Siman — antonia.caballero@esen.edu.sv).
Estudiante: Carlos Alberto Navas Flores (carnet 20255766).

**Las instrucciones maestras completas del curso viven en un Claude Project separado,
no en este repositorio** (formato exacto de los 5 paneles HTML, las 8 hojas de Excel,
paleta de diseño original, etc.). Un agente sin acceso a ese Project no puede leerlas
directamente — las reglas que sí importan para no romper nada están resumidas más
abajo y en `00 Curso/`. Ante cualquier duda sobre formato de entregable, es mejor
preguntar al usuario que inventar una estructura nueva.

## Reglas que nunca se rompen (independientes del Project)

1. **Nunca completar de memoria** tramos de ISR, salario mínimo, tasas ISSS/AFP/INCAF,
   días de aguinaldo/vacaciones u otra cifra normativa. Usar solo las que aparecen en
   `03 Marco Legal/` (ya verificadas contra el PDF de clase) o las que el usuario
   indique explícitamente. Si falta un dato, preguntar — no rellenar con un valor
   plausible.
2. Si se cita un artículo de ley, debe corresponder al material de la clase. Si el PDF
   no especifica el número exacto, usar "según el Código de Trabajo / Ley del ISR" en
   términos generales, nunca inventar un número de artículo.
3. Español formal universitario. Ejemplos siempre con empresas reales o verosímiles de
   El Salvador / Centroamérica — nunca genéricos. Montos siempre en dólares ($).
4. Cualquier HTML de un entregable de unidad debe seguir la paleta y las reglas de
   `00 Curso/Sistema de Diseño HTML.md` ("Fintech Oscuro", vigente desde 2026-08-26,
   con su checklist de curación anti-AI-slop) — no inventar una paleta nueva por
   sesión.
5. Antes de generar cualquier entregable, preguntar si hay ambigüedad — es una
   instrucción explícita y repetida del usuario, no solo una buena práctica genérica.

## Estructura de carpetas

- `00 Curso/` — calendario y ponderación oficial, sistema de diseño HTML vigente
  (`Sistema de Diseño HTML.md`), sistema de diseño Excel.
- `01 Bitácora/Entradas/` — una nota por sesión de trabajo: qué se generó, qué
  funcionó, qué falló, qué ajustar la próxima vez. Revisar la entrada más reciente
  antes de generar material nuevo.
- `02 Unidades/` — una nota por unidad temática (Unidad 1 - Pasivo Corriente
  (Planillas), Unidad 2 - Transacciones de Capital, ... Unidad 7), con el marco legal
  aplicable, ejercicios del material y qué entregables ya se generaron.
- `03 Marco Legal/` — Código de Trabajo, Ley del ISR y su Reglamento, Ley del Seguro
  Social, Ley del INCAF, Ley Integral del Sistema de Pensiones, Ley de Renuncia
  Voluntaria. Las tablas numéricas aquí ya fueron verificadas contra el PDF de clase —
  son la fuente de verdad, no reconstruirlas de memoria.
- `04 Glosario/` — términos técnicos y legales acumulados.
- `Entregables/Unidad N/` — copia de cada archivo `.html`/`.xlsx` ya entregado al
  estudiante.
- `docs/` — sitio estático publicado en GitHub Pages (índice + una carpeta por unidad
  disponible). Repo: `github.com/carcamval2025-cyber/vault-contabilidad-financiera`
  (público), rama `main`, Pages sirve desde `/docs`.
- `Plantillas/` — plantilla de unidad nueva y de entrada de bitácora.
- `Organigrama.md` / `Organigrama.canvas` — mapa visual de cómo fluye el vault.

## Formato de los entregables (resumen — la fuente completa es el Claude Project)

- **Entregable 1**: un HTML con barra lateral y 5 paneles (Resumen Visual, Ejercicio
  Resuelto, Guía Excel, Quiz de Práctica, Ejercicio Variante), diseño Fintech Oscuro,
  caja "⚖️ Marco Legal" obligatoria en Paneles 1 y 2, glosario en cada panel.
- **Entregable 2**: un Excel de 8 hojas (Inicio, Marco Normativo, Cálculo resuelto,
  Cálculo práctica, Asientos resueltos, Asientos práctica, Producto Final, Producto
  Final práctica) — la estructura de las hojas 3-8 varía según la unidad, ver la nota
  de cada unidad en `02 Unidades/`. Fórmulas siempre, nunca valores calculados
  hardcodeados; cero errores `#REF!`/`#DIV/0!`/`#VALUE!`/`#N/A`.
- **Entregable 3** (Simulacro de Control): solo en semanas con Control según el
  calendario oficial en `00 Curso/`.

## Cómo trabajar aquí

1. Antes de generar material de una unidad: leer la nota de esa unidad en
   `02 Unidades/`, la entrada más reciente de `01 Bitácora/Entradas/` y las tablas
   correspondientes en `03 Marco Legal/`.
2. Si falta una tabla legal o un dato del ejercicio, preguntar al usuario — nunca
   asumir.
3. Después de generar: registrar el resultado en una nueva nota de
   `01 Bitácora/Entradas/` (misma plantilla que las existentes) y actualizar el
   estado de la unidad en `02 Unidades/` e `Inicio.md`.
4. Si el material incluye HTML, verificar contra el checklist de curación en
   `00 Curso/Sistema de Diseño HTML.md` antes de darlo por terminado.

## Ver también (rutas de archivo, no wikilinks)

- `Inicio.md` — mapa del vault pensado para Obsidian (con Dataview).
- `00 Curso/Sistema de Diseño HTML.md`
- `00 Curso/Programa y Calendario.md`
- `01 Bitácora/Entradas/`
