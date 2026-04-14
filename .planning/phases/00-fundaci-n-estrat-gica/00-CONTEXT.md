# Phase 0: Fundación Estratégica - Context

**Gathered:** 2026-04-14
**Status:** Ready for planning

<domain>
## Phase Boundary

Producir la narrativa estratégica del producto ARCO Legal usando el skill `/draft-strategic-narrative`, que guía la creación paso a paso a través de 6 fases y luego ensambla el documento final.

**Output único**: `docs/STRATEGIC-NARRATIVE.md` — reescrito desde cero con la estructura del skill.

Esta fase cubre **solo DOC-01 y DOC-04**. El PRD (DOC-02, DOC-03) está fuera del roadmap por ahora (movido a backlog).

</domain>

<decisions>
## Implementation Decisions

## Scope y output

- **D-01:** Phase 0 produce un único artefacto: `docs/STRATEGIC-NARRATIVE.md`.
- **D-02:** El documento existente (SCR framework) se reemplaza completamente. No se adapta ni reutiliza — se reescribe desde cero.
- **D-03:** El PRD (DOC-02, DOC-03) queda fuera del roadmap activo, movido a backlog (999.x). `docs/PRD.md` existe pero no es parte de esta fase.

## Estructura del documento

- **D-04:** La narrativa sigue **exactamente la estructura de `/draft-strategic-narrative`**:
    - Phase 0: Foundation — Mensaje clave, audiencia, insights de decisión
    - Phase 1: El Contexto — Realidad actual con datos verificados
    - Phase 2: El Desafío — Problema real, urgencia, costo de la inacción
    - Phase 3: La Gran Idea — Solución con impacto medible
    - Phase 4: Estrategia — 3-5 elecciones estratégicas
    - Phase 5: Ejecución — Blueprint de ejecución y métricas
- **D-05:** El plan ejecuta el skill `/draft-strategic-narrative` completo (no una escritura manual), siguiendo su flujo fase por fase hasta el ensamblado final.

## Audiencia y tono

- **D-06:** Audiencia objetivo: primer cliente o socio estratégico potencial (no inversores, no equipo interno).
- **D-07:** Uso principal: reunión presencial donde el equipo fundador presenta la narrativa. El documento funciona como respaldo proyectado.
- **D-08:** Perfil del cliente/socio aún no definido — puede ser PyME chilena, firma legal u otro. La narrativa debe ser flexible, sin asumir un perfil específico.
- **D-09:** Tono: valor real para el cliente (cómo resuelve su problema concreto). No es un pitch de inversión.

## Contenido prohibido

- **D-10:** La narrativa NO menciona modelo de negocio, pricing ni tiers. 100% enfocada en el producto y el problema que resuelve.
- **D-11:** Modelo de negocio se define fuera del alcance de esta fase.

## Claude's Discretion

- Profundidad de cada sección del documento — el skill guía el nivel de detalle apropiado
- Longitud total del documento — lo que el skill produce naturalmente
- Formato exacto de secciones internas

</decisions>

<canonical_refs>

## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Contexto del proyecto

- `.planning/PROJECT.md` — Visión, core value, contexto legal (Ley 21.719), constraints
- `.planning/REQUIREMENTS.md` — DOC-01 y DOC-04 con criterios de aceptación (DOC-02/03 en backlog)
- `.planning/ROADMAP.md` — Goal y success criteria de Phase 0

### Skill de ejecución

- `/draft-strategic-narrative` (skill instalado en Claude Code) — Estructura de 6 fases, preguntas por fase, criterios de validación, proceso de ensamblado final. El plan debe invocar este skill, no replicar su lógica manualmente.

### No hay specs externas adicionales

Esta es la fase fundacional del proyecto. Todos los requisitos están en los archivos de arriba y en las decisiones de este contexto.

</canonical_refs>

<code_context>

## Existing Code Insights

### Reusable Assets

- Ninguno — proyecto greenfield. Phase 0 produce solo documentos.

### Established Patterns

- Ninguno aún.

### Integration Points

- `docs/STRATEGIC-NARRATIVE.md` — el plan sobreescribe este archivo con el nuevo documento generado por el skill.

</code_context>

<specifics>
## Specific Ideas

- El skill `/draft-strategic-narrative` es la herramienta de ejecución, no una tarea de escritura libre. El plan debe invocar el skill y dejar que guíe el proceso.
- La narrativa para reunión presencial debe ser concisa y orientada a provocar conversación, no a cubrir todos los detalles.
- El documento resultante debe ser proyectable — cada sección pensada para ser hablada, no leída en silencio.
- La Ley 21.719 con números concretos (30 días, 5K/10K/20K UTM, diciembre 2026) debe estar presente desde el principio.

</specifics>

<deferred>
## Deferred Ideas

- **PRD.md → backlog (999.x)**: personas de usuario, flujos principales, requisitos funcionales/no funcionales, arquitectura de integraciones (DOC-02, DOC-03). `docs/PRD.md` ya existe como referencia pero no es parte del roadmap activo.
- Stack tecnológico — se define en Phase 1.
- Pricing / modelo de negocio — fuera del roadmap actual.
- Personas de usuario concretas — en backlog junto con el PRD.

</deferred>

---

*Phase: 00-fundaci-n-estrat-gica*
*Context gathered: 2026-04-14*
