# Quality Checklist — Blueprint Tech Plan

Lee este archivo en la Fase 6 para validar el blueprint antes de entregarlo.

## Checklist por sección

### Sección 5 — Hipótesis de Solución
- [ ] Es entendible por un stakeholder no técnico
- [ ] Describe el approach conceptual, no la implementación detallada
- [ ] Se conecta directamente con el problema descrito en sección 1
- [ ] No introduce scope fuera de lo definido en sección 4

### Sección 6 — Estrategia Técnica

#### 6.1 Diagrama y Flujo
- [ ] Tiene link a diagrama visual (o placeholder explícito "PENDIENTE")
- [ ] La descripción narrativa cubre el flujo completo de datos
- [ ] Cada componente mencionado se identifica como existente o nuevo
- [ ] Se describen los puntos de integración con sistemas existentes
- [ ] Se cubren los flujos de error, no solo el happy path

#### 6.2 Decisiones Clave
- [ ] Cada decisión tiene alternativas consideradas y justificación
- [ ] El stack elegido es consistente con el stack existente, o se justifica la divergencia
- [ ] Si hay tecnología nueva, hay plan de ramp-up para el equipo
- [ ] No hay decisiones implícitas — todo lo que se eligió está documentado

### Sección 7 — Plan de Ejecución

#### Milestones generales
- [ ] Hay entre 4-6 milestones para un proyecto de un quarter
- [ ] La secuencia es lógica — cada milestone desbloquea el siguiente
- [ ] Si el proyecto se cancela en el milestone N, ya se entregó algún valor
- [ ] Las fechas son realistas considerando el equipo disponible

#### Por cada milestone
- [ ] OUTPUT es concreto: describe qué pieza de software funciona, no solo qué se hizo
- [ ] OUTCOME conecta con el KPI de la sección 3 o es explícitamente habilitador
- [ ] Dependencias están identificadas (internas y externas)
- [ ] No hay milestones de más de 3 semanas sin entrega intermedia

### Sección 8 — Riesgos
- [ ] Hay mínimo 3 riesgos identificados
- [ ] Al menos 1 riesgo es técnico (deuda, performance, integración)
- [ ] Al menos 1 riesgo es de dependencia (otro equipo, sistema externo, datos)
- [ ] Cada riesgo tiene impacto asignado (Alto/Medio/Bajo)
- [ ] Cada riesgo tiene plan de mitigación concreto y accionable
- [ ] Los riesgos del codebase descubiertos en la exploración están reflejados

## Señales de alerta (Red Flags)

Marca como alerta si encuentras alguno de estos patrones:

- **Milestone vacío:** OUTPUT dice "investigación", "análisis", "setup" sin entregable tangible
- **Riesgo genérico:** "Puede haber problemas de performance" sin especificar dónde ni por qué
- **Decisión sin justificación:** "Usaremos Redis" sin explicar por qué no otra alternativa
- **Scope creep:** La solución técnica cubre cosas fuera del scope definido en sección 4
- **Optimismo no fundamentado:** Fechas agresivas sin considerar dependencias o complejidad
- **Milestones no incrementales:** El valor solo se entrega al final, no incrementalmente
- **Sin considerar el codebase:** La estrategia técnica ignora patrones o restricciones existentes

## Formato de reporte de validación

Al terminar el checklist, presenta al DRI:

```
## Resultado de validación

**Estado:** [LISTO / NECESITA AJUSTES]

### Items aprobados: X/Y

### Ajustes necesarios:
1. [Sección] — [Problema específico] — [Sugerencia]
2. ...

### Red flags encontrados:
- [Descripción del red flag]
```
