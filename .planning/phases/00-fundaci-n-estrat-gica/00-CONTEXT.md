# Phase 0: Fundación Estratégica - Context

**Gathered:** 2026-04-13
**Status:** Ready for planning

<domain>
## Phase Boundary

Producir dos documentos estratégicos previos al desarrollo:
1. **Narrativa estratégica** estructurada (problema → solución → mercado → diferenciación → roadmap) — para uso en reunión presencial con primer cliente o socio estratégico
2. **PRD.md** con personas de usuario, flujos principales, requisitos funcionales y no funcionales, y arquitectura de integraciones (manual-first → API)

Esta fase NO incluye decisiones de stack tecnológico ni definición de modelo de negocio o pricing.

</domain>

<decisions>
## Implementation Decisions

### Narrativa estratégica — Audiencia

- **D-01:** La audiencia objetivo es un primer cliente o socio estratégico potencial (no inversores ni equipo interno).
- **D-02:** El uso principal es una reunión presencial donde el equipo fundador presenta la narrativa. El documento funciona como respaldo proyectado, no como lectura autónoma.
- **D-03:** El perfil del cliente/socio objetivo aún no está definido — puede ser PyME chilena, firma legal u otro. La narrativa debe ser flexible y no asumir un perfil específico.
- **D-04:** El tono debe enfocarse en el valor real para el cliente: cómo resuelve su problema concreto. No es un pitch de inversión.

### Narrativa estratégica — Modelo de negocio

- **D-05:** La narrativa NO menciona modelo de negocio, pricing ni tiers. Se centra 100% en el producto y el problema que resuelve.
- **D-06:** El modelo de negocio se define por separado, fuera del alcance de esta fase.

### Claude's Discretion

- Stack tecnológico: no se decide en esta fase — queda para Phase 1
- Personas de usuario concretas: el planner puede definirlas basándose en el contexto del proyecto (PROJECT.md, REQUIREMENTS.md)
- Formato final de la narrativa: el planner decide si usar Markdown o estructura de slides, orientado al uso en reunión presencial

</decisions>

<canonical_refs>
## Canonical References

**Downstream agents MUST read these before planning or implementing.**

### Project context
- `.planning/PROJECT.md` — Visión, principios, contexto de mercado, decisiones clave
- `.planning/REQUIREMENTS.md` — Requisitos DOC-01 a DOC-04 con criterios de aceptación
- `.planning/ROADMAP.md` — Goal y success criteria de Phase 0

### No external specs
No hay ADRs ni specs externas aún — esta es la fase fundacional. Los requisitos están completamente capturados en los archivos de arriba y en las decisiones de este contexto.

</canonical_refs>

<code_context>
## Existing Code Insights

### Reusable Assets
- Ninguno — proyecto greenfield, sin codebase

### Established Patterns
- Ninguno aún

### Integration Points
- Ninguno aún — Phase 0 produce solo documentos

</code_context>

<specifics>
## Specific Ideas

- La narrativa para reunión presencial debe ser concisa y orientada a provocar conversación, no a cubrir todos los detalles
- El skill `/draft-strategic-presentation` está disponible para generar la narrativa siguiendo el framework (problema → solución → mercado → diferenciación → roadmap)

</specifics>

<deferred>
## Deferred Ideas

- Stack tecnológico — se define en Phase 1
- Pricing / modelo de negocio — se define por separado, fuera del roadmap actual
- Personas de usuario concretas (Jefa de RRHH vs. dueño de empresa vs. asistente) — el planner las define en el PRD basándose en el contexto del proyecto

</deferred>

---

*Phase: 00-fundaci-n-estrat-gica*
*Context gathered: 2026-04-13*
