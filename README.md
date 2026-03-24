# idm-skills
# IDM Claude Skills

Skills de Claude Code para el equipo de Inteligencia de Mercados (IDM). Estandarizan la creación de Blueprint Docs — desde la definición del problema hasta el plan de ejecución técnica — con coaching agéntico que eleva la calidad de cada sección.

## ¿Qué problema resuelven?

Los Blueprint Docs son el artefacto central de planning de IDM. Definen qué se va a construir, por qué, cómo se mide el éxito y cómo se ejecuta. En la práctica, la calidad varía: problemas vagos, KPIs no medibles, milestones sin entregables claros y riesgos genéricos son problemas recurrentes.

Estos skills actúan como coaches especializados que guían al autor sección por sección con preguntas de challenge, validaciones de consistencia y formatos estandarizados. No generan el documento por ti — te ayudan a pensarlo mejor.

## Skills

### `blueprint-prd`
**Para:** Product Managers  
**Cubre:** Secciones 1-4 del Blueprint (PRD)

Guía la definición del problema, valor de negocio, KPI de éxito y scope. Frena al PM si salta a la solución antes de articular el dolor, valida que el KPI sea medible con fórmula y línea base, y fuerza boundaries explícitos de scope.

### `blueprint-tech-plan`
**Para:** Dev Lead / DRI del proyecto  
**Cubre:** Secciones 5-8 del Blueprint (Plan de Ejecución Técnica)

Toma el PRD como input, explora el codebase existente (brownfield), y guía al DRI a completar hipótesis de solución, estrategia técnica con decisiones justificadas, milestones con entregables incrementales, y riesgos con planes de mitigación. Valida el plan completo contra un checklist de calidad antes de entregarlo.

## Instalación

### Opción 1 — Symlink (recomendada para equipos)

Clona una vez, linkea en cada proyecto. Las actualizaciones se propagan con `git pull`.

```bash
git clone git@github.com:habi/idm-claude-skills.git ~/repos/idm-claude-skills

# En el repo de tu proyecto:
mkdir -p .claude/skills
ln -s ~/repos/idm-claude-skills/blueprint-prd .claude/skills/blueprint-prd
ln -s ~/repos/idm-claude-skills/blueprint-tech-plan .claude/skills/blueprint-tech-plan
```

### Opción 2 — Copiar al proyecto

```bash
cp -r blueprint-prd/ /ruta/al/proyecto/.claude/skills/blueprint-prd/
cp -r blueprint-tech-plan/ /ruta/al/proyecto/.claude/skills/blueprint-tech-plan/
```

### Opción 3 — Instalación personal

```bash
cp -r blueprint-prd/ ~/.claude/skills/blueprint-prd/
cp -r blueprint-tech-plan/ ~/.claude/skills/blueprint-tech-plan/
```

> **Nota:** Requiere Claude Code con acceso a Claude. Los skills se activan automáticamente cuando Claude detecta intención relevante (ej: "quiero crear un PRD", "completar el blueprint").

## Flujo de trabajo

```
PM                          DRI                         Equipo
 │                           │                           │
 │  1. "Crear PRD para X"   │                           │
 │  ──► blueprint-prd       │                           │
 │  ──► Google Doc (§1-4)   │                           │
 │                           │                           │
 │  2. Alineación con DRI   │                           │
 │  ─────────────────────►  │                           │
 │                           │                           │
 │                           │  3. Pega PRD en Claude    │
 │                           │  ──► blueprint-tech-plan  │
 │                           │  ──► Google Doc (§5-8)    │
 │                           │                           │
 │                           │  4. Roast ───────────────►│
 │                           │                           │
 │                           │  5. CCPM ejecuta          │
 │                           │     milestone x milestone │
 │                           │                           │
```

**Paso 1 — PM crea el PRD.** Abre Claude Code y describe la iniciativa. El skill `blueprint-prd` lo guía por problema, valor, KPI y scope con preguntas de challenge. El output se copia al Google Doc del blueprint.

**Paso 2 — Alineación.** PM y DRI revisan el PRD juntos. El DRI resuelve dudas sobre scope y confirma que tiene contexto suficiente.

**Paso 3 — DRI completa el plan técnico.** Abre Claude Code en el repo del proyecto, pega el PRD. El skill `blueprint-tech-plan` explora el codebase, luego guía hipótesis de solución, estrategia técnica, milestones y riesgos. El output se copia al Google Doc.

**Paso 4 — Roast.** El equipo valida el blueprint completo. Foco en riesgos, dependencias y viabilidad de milestones.

**Paso 5 — Ejecución.** Con el blueprint aprobado, el DRI puede usar [CCPM](https://github.com/automazeio/ccpm) para descomponer milestones en epics y tasks ejecutables con revisión incremental.

## Contexto de negocio

Si el repo del proyecto contiene un archivo `business-context-idm.md`, el skill `blueprint-prd` lo lee automáticamente para usar glosario, procesos y métricas del área. Recomendamos mantener este archivo actualizado en el repo principal de IDM.

## Estructura del repo

```
idm-claude-skills/
├── README.md
├── blueprint-prd/
│   ├── SKILL.md                        # Coach de PRD para PMs
│   └── references/
│       └── prd-template.md             # Formato de output + handoff al DRI
└── blueprint-tech-plan/
    ├── SKILL.md                        # Coach de plan técnico para DRIs
    └── references/
        ├── blueprint-template.md       # Formato de output secciones 5-8
        └── quality-checklist.md        # Validación de calidad pre-entrega
```

## Cómo contribuir

Si identificas patrones recurrentes que los skills no cubren (ej: un tipo de riesgo que siempre se omite, un challenge que siempre falta), abre un PR con el ajuste. Los skills son markdown — editarlos es tan simple como editar un doc.

## FAQ

**¿Funciona con Cursor?**  
Los skills están diseñados para Claude Code. Si tus devs usan Cursor, pueden copiar el contenido de SKILL.md a un `.cursorrules` como contexto para el agente, aunque la experiencia no es idéntica.

**¿Necesito CCPM para usar los skills?**  
No. Los skills generan el blueprint completo como markdown. CCPM es opcional para la fase de ejecución — puedes ejecutar milestones con el workflow que tu equipo prefiera.

**¿Los skills generan el documento por mí?**  
No. Los skills actúan como coaches: preguntan, cuestionan y validan. Tú (o el DRI) aportan el conocimiento de dominio y las decisiones. El output es tuyo, no de la IA.
