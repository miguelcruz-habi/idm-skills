# Blueprint Template — Secciones 5-8 (Plan de Ejecución Técnica)

Este es el formato exacto de output que debe generar el skill. El DRI copia esto
al Google Doc del blueprint. Mantén este formato al pie de la letra.

## Template

```markdown
## **II. Plan de ejecución técnica**

### **5. Hipótesis de Solución (Alto Nivel)**

[Párrafo de 3-5 oraciones describiendo el approach conceptual elegido.
Debe ser entendible por un stakeholder no técnico.
Ejemplo: "Implementaremos un motor de coincidencia automático que sugiera
conciliaciones con un 90% de confianza, requiriendo aprobación manual solo
en excepciones."]

### **6. Estrategia Técnica**

#### **6.1 Diagrama y Flujo**

* **Diagrama:** [Link a Miro / Excalidraw / Lucid]
* **Descripción del Flujo:** [Descripción narrativa paso a paso del flujo
  de datos y componentes. Incluir: origen de datos → transformaciones →
  destino. Marcar qué componentes son existentes vs nuevos.]

#### **6.2 Decisiones Clave y Stack**

1. **Stack:** [Lenguajes, Frameworks, Infraestructura]
2. **Decisión Crítica 1:** [Qué se decidió]
   - *Alternativas evaluadas:* [Qué más se consideró]
   - *Justificación:* [Por qué esta opción]
3. **Decisión Crítica 2:** [Repetir estructura si hay más decisiones]

### **7. Plan de Ejecución (Entrega de Valor)**

#### **7.1 Milestones del proyecto**

| Milestone | Fecha de entrega | OUTPUT (entregable técnico) | OUTCOME (Impacto de Negocio) | Dependencias identificadas |
| ----- | ----- | ----- | ----- | ----- |
| **Milestone A:** [Síntesis] | Fecha | [¿Qué pieza de software funciona?] | [¿Qué métrica impactamos y en qué medida?] | [Deps internas/externas] |
| **Milestone B:** [Síntesis] | Fecha | | | |
| **Milestone C:** [Síntesis] | Fecha | | | |
| **Milestone D:** [Síntesis] | Fecha | | | |
| **Milestone E:** [Síntesis] | Fecha | | | |
| **Milestone F:** [Síntesis] | Fecha | | | |

### **8. Riesgos Conocidos**

*Identificados por el project lead y resultados de la sesión de validación
técnica (Roast). Si no hay riesgos, no se pensó lo suficiente.*

| Riesgos/dependencias Identificados | Impacto (Alto/Medio/Bajo) | Estrategia de Mitigación (Plan B) |
| :---- | :---- | :---- |
| **Riesgo 1:** [Descripción del Riesgo] | [Nivel] | [Acción preventiva o reactiva] |
| **Riesgo 2:** [Descripción del Riesgo] | [Nivel] | [Acción preventiva o reactiva] |
| **Riesgo 3:** [Descripción del Riesgo] | [Nivel] | [Acción preventiva o reactiva] |
```

## Notas sobre formato

- Las tablas deben ser compatibles con Google Docs (Markdown estándar).
- Los milestones se numeran con letras (A, B, C...) no números, para diferenciarlos de las secciones.
- OUTPUT siempre responde "¿Qué pieza de software funciona?" — no "¿Qué hicimos?".
- OUTCOME siempre conecta con la métrica de la sección 3 o dice explícitamente "Habilitador para milestone X".
- Riesgos mínimos: 3. Si hay menos, el skill debe insistir.

## Compatibilidad con CCPM

Para que CCPM pueda parsear los milestones para ejecución:

- Cada milestone debe tener un OUTPUT suficientemente detallado para ser descompuesto en tasks.
- Las dependencias deben ser explícitas para que CCPM ordene la ejecución.
- El DRI puede usar `/pm:prd-parse` en CCPM pasando el blueprint completo como input.
- CCPM transformará cada milestone en un epic con tasks descompuestos.
