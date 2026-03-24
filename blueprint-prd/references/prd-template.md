# Blueprint Template — Secciones 1-4 (PRD) + Ficha Técnica

Este es el formato exacto de output. El PM copia esto al Google Doc del blueprint.

## Template

```markdown
# **Blueprint Doc de [nombre del proyecto]**

## **Ficha Técnica**

| Rol | Persona Asignada |
| :---- | :---- |
| **Project Owner (DRI)** | [Nombre] |
| **Backup** | [Nombre] |
| **Devs** | [Nombres] |
| **Stakeholders** | [Nombres] |
| **Link a Github Projects:** | [URL] |
| **Link de Repos que se usan en el proyecto:** | [URLs] |

## **I. PRD (Product Requirement)**

### **1. El Problema (The Why)**

*¿Qué dolor específico estamos resolviendo? Evita saltar a la solución.*

[Narrativa de 3-5 oraciones describiendo el problema actual y su impacto
negativo en el usuario o la operación.]

### **2. Impacto en el Negocio (Business Value)**

*¿Qué gana la compañía al resolver esto? (Money, Strategy, Risk)*

* **Beneficio Directo:** [Tangible y cuantificable]
* **Alineación Estratégica:** [Qué desbloquea o habilita]

### **3. Outcome Esperado (Éxito)**

*¿Cómo mediremos si obtuvimos ese impacto?*

* **KPI:** [Métrica principal]
* **Fórmula de Cálculo:** [Numerador / denominador]
* **Temporalidad de Medición:** [Últimas dos semanas del Q]
* **Línea Base (Actual):** [Valor numérico actual]
* **Meta (Target):** [Valor numérico objetivo]

### **4. Alcance (Scope)**

*Mata la ambigüedad. Qué entra y qué NO entra.*

| ✅ Dentro de alcance | ❌ Fuera del alcance (Fase 2+) |
| :---- | :---- |
| [Feature Crítico 1] | [Feature Futuro A] |
| [Feature Crítico 2] | [Feature Futuro B] |
```

## Notas sobre formato

- La Ficha Técnica va ANTES del PRD — es lo primero que se ve al abrir el doc.
- El DRI debe estar confirmado antes de enviar el blueprint al equipo técnico.
- Los links a repos son críticos para que el skill blueprint-tech-plan pueda explorar el codebase.
- El nombre del proyecto debe ser descriptivo y corto (3-5 palabras max).

## Handoff al DRI

Cuando el PRD está completo:

1. PM copia el output al Google Doc del blueprint.
2. PM agenda sesión de alineación con el DRI para:
   - Explicar el problema y el KPI (5-10 min)
   - Resolver dudas sobre scope y boundaries
   - Confirmar que el DRI tiene contexto suficiente para arrancar el plan técnico
3. DRI usa el skill `blueprint-tech-plan` en Claude Code para completar secciones 5-8.
4. DRI comparte el plan técnico de vuelta al PM para review.
5. Se agenda el Roast con el equipo para validar riesgos.
