# Phase 0: Fundación Estratégica - Research

**Researched:** 2026-04-13
**Domain:** Strategic documentation — PRD writing and strategic narrative for B2B SaaS compliance platform
**Confidence:** HIGH (domain well-established, legal context verified from official sources)

---

<user_constraints>
## User Constraints (from CONTEXT.md)

### Locked Decisions

- **D-01:** Audiencia objetivo: primer cliente o socio estratégico potencial (no inversores ni equipo interno).
- **D-02:** Uso principal: reunión presencial donde el equipo fundador presenta la narrativa. Documento funciona como respaldo proyectado, no como lectura autónoma.
- **D-03:** Perfil del cliente/socio objetivo aún no está definido. La narrativa debe ser flexible y no asumir un perfil específico (PyME, firma legal, u otro).
- **D-04:** Tono: valor real para el cliente, cómo resuelve su problema concreto. No es un pitch de inversión.
- **D-05:** La narrativa NO menciona modelo de negocio, pricing ni tiers.
- **D-06:** El modelo de negocio se define por separado, fuera del alcance de esta fase.

### Claude's Discretion

- Stack tecnológico: no se decide en esta fase — queda para Phase 1
- Personas de usuario concretas: el planner puede definirlas basándose en el contexto del proyecto (PROJECT.md, REQUIREMENTS.md)
- Formato final de la narrativa: el planner decide si usar Markdown o estructura de slides, orientado al uso en reunión presencial

### Deferred Ideas (OUT OF SCOPE)

- Stack tecnológico — se define en Phase 1
- Pricing / modelo de negocio — se define por separado, fuera del roadmap actual
- Personas de usuario concretas (Jefa de RRHH vs. dueño de empresa vs. asistente) — el planner las define en el PRD basándose en el contexto del proyecto
</user_constraints>

---

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| DOC-01 | Narrativa estratégica estructurada según framework de presentación estratégica (problema → solución → mercado → diferenciación → roadmap) | Section "Architecture Patterns > Narrative Framework" details the optimal structure for this audience |
| DOC-02 | PRD.md con personas de usuario, flujos principales, requisitos funcionales y no funcionales | Section "Standard Stack > PRD Structure" maps the mandatory sections; "Personas" subsection addresses the unvalidated-profile challenge |
| DOC-03 | PRD incluye arquitectura de integraciones (manual-first → API) | Section "Architecture Patterns > Integration Architecture" provides the manual-first concierge model and migration path |
| DOC-04 | Narrativa comprensible por co-founders, socios estratégicos e interesados externos sin contexto previo | Section "Architecture Patterns > Self-Contained Narrative Principles" addresses this requirement |
</phase_requirements>

---

## Summary

Phase 0 produces two strategic documents — a narrative presentation and a PRD — before any code is written. The research domain is documentation methodology, not software architecture. The primary technical challenge is not tooling but structure: what sections belong in each document, how to handle unvalidated personas, and how to describe an integration architecture that starts manual and evolves to automated.

The compliance context (Ley 21.719, derechos ARCO+) is now well-understood from official sources. The law enters into force December 1, 2026, establishing a hard market window. ARCO+ covers six rights (acceso, rectificación, cancelación, oposición, portabilidad, bloqueo) with 30-day response deadlines and penalties ranging from 5,000 to 20,000 UTM. This legal context is the central problem anchor for both documents.

For the strategic narrative, the optimal framework for a first-client presential meeting is a problem-first arc (situation → complication → resolution), not an investor pitch arc. The audience is a decision-maker who needs to understand the problem better before evaluating the solution. For the PRD, the standard B2B SaaS pre-development structure requires 10–12 sections with user personas, functional/non-functional requirements, and an integration architecture section that explicitly describes the manual-first → API evolution path.

**Primary recommendation:** Write the narrative as a projected Markdown document structured in 5–6 sections following problem → solution → market → differentiation → roadmap. Write the PRD as a standalone Markdown file with all standard sections filled, treating personas as "proto-personas" based on the known market context (PyMEs without DPO, firms with RRHH systems) with explicit "to be validated" flags.

---

## Standard Stack

### Core

This phase produces documents, not software. The "stack" is structural templates and frameworks.

| Artifact | Format | Purpose | Why Standard |
|----------|--------|---------|--------------|
| Narrativa estratégica | Markdown (rendered as slides or projected) | Alignment document for first client meeting | Format decided as Claude's Discretion; Markdown gives portability and version control |
| PRD.md | Markdown | Single source of truth for product definition | Markdown is the standard for engineering-facing PRDs; readable without tooling |

### Narrative Framework (DOC-01)

The recommended framework for a first-client presential meeting is the **McKinsey Situation-Complication-Resolution (SCR)** arc adapted to B2B product narratives. This maps directly to the problem → solution → market → differentiation → roadmap sequence specified in the requirements. [CITED: McKinsey problem-solving frameworks, widely documented in B2B presentation methodology]

| Section | Content | Purpose |
|---------|---------|---------|
| 1. Situación | El contexto del mercado: Ley 21.719 entra en vigencia. Empresas deben cumplir o enfrentan multas. | Establishes shared understanding — audience already lives in this reality |
| 2. Complicación | El problema operativo real: solicitudes ARCO+ llegan por canales dispersos, no hay trazabilidad, el plazo corre igual. | Creates urgency and emotional resonance |
| 3. Solución | ARCO Legal: plataforma centralizada que recibe, gestiona y responde solicitudes dentro del plazo legal. | Positions product as the direct answer to the complication |
| 4. Mercado | PyMEs chilenas sin DPO ni equipos legales — mayoría del tejido empresarial, primera vez que enfrentan esta obligación. | Validates market reality without investor framing |
| 5. Diferenciación | Flujo completo (intake → tracking → respuesta → comprobante), integración con plataformas de RRHH existentes, desde manual hasta automatizado. | Specific capabilities that competitors don't offer together |
| 6. Roadmap | Tres fases: plataforma core, flujos de cumplimiento, integraciones automatizadas. | Shows trajectory without committing to dates |

**Key constraint for this audience (D-02, D-04):** The narrative is projected in a meeting, not read alone. Each section should be max 3–4 bullet points, designed to be spoken to, not read. No pricing, no model. [ASSUMED: Optimal slide density for projected B2B presentations is 3-4 points per section — based on presentation design principles, not empirically tested for this specific audience.]

### PRD Structure (DOC-02, DOC-03)

The standard sections for a B2B SaaS PRD in pre-development stage, based on industry research: [CITED: Codelevate B2B SaaS PRD guide, Infrasity PRD guide 2025]

| Section | Required | Notes |
|---------|----------|-------|
| 1. Overview / Problem Statement | Yes | 1–2 paragraphs — why this product exists |
| 2. Goals & Success Metrics | Yes | What does success look like at v1 launch |
| 3. User Personas | Yes | Proto-personas with explicit validation flags |
| 4. User Stories / Main Flows | Yes | Key paths through the product |
| 5. Functional Requirements | Yes | Feature list organized by module |
| 6. Non-Functional Requirements | Yes | Performance, security, compliance constraints |
| 7. Integration Architecture | Yes | The manual-first → API evolution (DOC-03) |
| 8. Out of Scope | Yes | Explicit exclusions to prevent scope creep |
| 9. Open Questions | Yes | Unresolved decisions to flag for Phase 1 |
| 10. Assumptions | Yes | What we're assuming before validation |

---

## Architecture Patterns

### Recommended Document Structure

```
docs/
├── STRATEGIC-NARRATIVE.md    # DOC-01, DOC-04 — presential narrative
└── PRD.md                    # DOC-02, DOC-03 — full product requirements
```

Both documents are written from scratch in this phase. The planning directory (`.planning/`) already holds structural files; the deliverable documents should live in the project root's `docs/` folder or at the root level for maximum visibility.

### Pattern 1: Problem-First Narrative for First Client

**What:** Open with the problem the client already recognizes (Ley 21.719 compliance deadline), not with your product. Make them say "yes, that's my problem" before you introduce the solution.

**When to use:** Any first-meeting presentation where the audience is an operator (not an investor). [CITED: B2B storytelling frameworks — problem-protagonist arc, aspid.marketing, euncet.com]

**Structure principle:**
```
[Section 1 — Situación]
  - Ley 21.719 entra en vigencia diciembre 2026
  - Toda empresa que trata datos personales debe responder solicitudes ARCO+
  - Plazo: 30 días corridos. Multas: hasta 20.000 UTM

[Section 2 — Complicación]
  - Solicitudes llegan por email, formulario, WhatsApp, carta
  - No hay sistema central — se pierden
  - El plazo corre igual aunque no se haya visto la solicitud

[Section 3 — Solución]
  - ARCO Legal recibe, centraliza y alerta
  - El operador nunca pierde un plazo
  - Trazabilidad completa para demostrar cumplimiento ante la Agencia
```

**Why this works for D-03 (flexible audience):** The problem is universal across all company types. The specific pain (losing track of requests, missing deadlines) is the same whether the audience is a PyME, a firma legal managing multiple clients, or an HR department. The product addresses the problem structurally, not by targeting a specific industry.

### Pattern 2: Proto-Personas for Unvalidated Markets

**What:** Define personas based on the known problem context and market research, not primary user interviews. Label them explicitly as proto-personas with a "to be validated" flag.

**When to use:** Pre-product, pre-customer-interview stage where writing "TBD" would leave the PRD incomplete. [CITED: Synthetic personas methodology for SaaS pre-development, quickcreator.io 2025; T2D3 B2B persona guide]

**The three proto-personas for ARCO Legal based on context:**

**Persona A — El Operador de Compliance (Primary User)**
- Role: Encargado de RRHH, Asistente Legal, o Jefa de Administración en PyME chilena
- Has no DPO, handles compliance as part of a broader administrative role
- Pain: Receives requests via email, has no tracking system, dreads the audit
- Behavior: Works in spreadsheets, familiar with email, not a developer
- *To be validated: title varies significantly by company size and sector*

**Persona B — El Administrador de la Empresa (Buyer + Admin)**
- Role: Dueño de empresa, Gerente General, o Director de RRHH en empresa de 50–500 empleados
- Needs compliance as a liability shield, not primarily as a workflow tool
- Pain: Fear of fines, fear of reputational damage, no visibility into current state
- Behavior: Will purchase but not operate daily; cares about auditability
- *To be validated: decision-making unit in Chilean SMB; may be same person as Persona A in small companies*

**Persona C — El Titular (Data Subject — External Actor)**
- Not a "user" of the platform, but an actor in every flow
- Sends ARCO+ requests; expects confirmation and status updates
- No technical sophistication required
- *This persona does not need validation — the law defines them*

**Note on Persona C:** The platform serves both operators (internal) and titulares (external). The UX for each is fundamentally different. The PRD must be explicit that titulares interact only through the public intake form and status-check URL, never through the operator dashboard. [ASSUMED: No third persona type (e.g., firma legal managing multiple companies) needs to appear in v1 PRD — multi-tenant use case is deferred to v2 per REQUIREMENTS.md MULT-01.]

### Pattern 3: Integration Architecture (Manual-First → API)

**What:** Document the integration strategy as a two-phase evolution model. Phase 1 is manual (operador-guided checklist). Phase 2 is automated (API or OAuth connector).

**Why this pattern exists:** For compliance SaaS targeting PyMEs, the integration value is real but the setup friction of API connections is too high for v1 adoption. Starting manual validates the workflow before automating it. [CITED: Concierge MVP pattern, SaaS MVP development guides 2025]

**The PRD integration architecture section must answer:**

1. **What data needs to be collected** — personal data dispersed across HR systems (buk.cl), CRMs, email
2. **Phase 1 — Manual collection flow** (INTG-01 in REQUIREMENTS.md): Operator gets a guided checklist of platforms to check, manually searches each, and records what was found. The platform provides structure, not automation.
3. **Phase 2 — Automated collection** (INTG-02/03/04): OAuth connection to buk.cl; API call returns relevant records by RUT; operator reviews and selects what to include.
4. **Migration trigger** — When a customer manually runs 10+ ARCO+ searches in buk.cl, the automated connector pays for itself. This is the natural upsell/upgrade trigger.

**Section structure for PRD:**
```
## Integration Architecture

### Philosophy: Manual-First → Automated

The platform is designed around the reality that operators must complete ARCO+ 
responses with or without API integrations. Integrations accelerate an existing 
workflow — they don't define it.

### Phase 1: Manual-Guided Collection (v1)
[describe INTG-01 flow]

### Phase 2: Automated Collection — buk.cl (v2/Phase 3)
[describe INTG-02/03/04]

### Future Integrations (v2+)
[INTG-05/06/07 from REQUIREMENTS.md]

### Integration Decision Criteria
A new integration is justified when:
- The platform is a common source of personal data for the target customer
- Manual lookup takes > 5 minutes per request
- The platform has a documented API or OAuth standard
```

### Anti-Patterns to Avoid

- **Investor pitch framing in client narrative:** Includes TAM/SAM/SOM slides, growth projections, monetization strategy. This audience needs operational confidence, not financial upside. (D-04, D-05)
- **Generic personas:** "Maria, 35, uses technology daily" — useless. Personas must be specific to compliance workflow roles.
- **Deferred integration architecture:** Writing "TBD" in the PRD integration section leaves Phase 3 unanchored. Even though automation is Phase 3, the architecture must be described in Phase 0.
- **Over-specifying technical stack in PRD:** The PRD should describe behavior and constraints, not implementation. Stack is Phase 1's domain. (D-06 from CONTEXT.md)
- **Missing non-functional requirements:** Compliance platforms have specific NFRs — audit log immutability, 30-day data retention minimums, Spanish-language interface. These must be explicit in the PRD even if the platform isn't built yet.

### Self-Contained Narrative Principles (DOC-04)

A document is self-contained (readable without prior context) when it:
1. Opens by establishing the regulatory context — not assuming the reader knows about Ley 21.719
2. Defines acronyms on first use — "ARCO (Acceso, Rectificación, Cancelación, Oposición)"
3. States the problem in operational terms, not abstract ones — "una solicitud puede llegar por email y perderse en la bandeja" not "gestión deficiente de compliance"
4. Uses concrete numbers — "30 días corridos," "multas hasta 20.000 UTM (~$1.4M)"
5. Ends with a clear next step — what does this audience do differently after reading this?

[ASSUMED: No prior context should be assumed beyond: the audience operates a Chilean company and has heard of "Ley 21.719" but may not know its specific obligations.]

---

## Don't Hand-Roll

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| PRD structure | Custom section ordering per author preference | Standard 10-section B2B SaaS PRD template | Planner and downstream agents need predictable section locations |
| Narrative framework | Inventing a new presentation arc | SCR (Situation-Complication-Resolution) adapted for B2B client meetings | Proven framework; keeps narrative from drifting into investor pitch territory |
| Legal research | Re-researching Ley 21.719 from scratch | Use the verified facts in this document | Already sourced from official/legal documentation |
| Persona definition | Waiting for user interviews | Proto-personas from market context, clearly flagged as unvalidated | Unblocks PRD writing; flags what needs validation |

**Key insight:** Both deliverables are Markdown documents. The planning complexity is structural (what sections, what depth) not technical. The planner should allocate task effort around getting the content right, not the format.

---

## Common Pitfalls

### Pitfall 1: Mixing Narrative and PRD Content

**What goes wrong:** The strategic narrative starts including functional requirements ("el formulario tendrá X campos"). The PRD starts including pitch language ("el mercado potencial es X millones").
**Why it happens:** Both documents cover the same product, so content bleeds between them.
**How to avoid:** The narrative answers "why does this exist and why now." The PRD answers "what exactly will be built and how it will behave." Keep a strict boundary.
**Warning signs:** Any section of the narrative that specifies UI behavior; any section of the PRD that mentions market size or business opportunity.

### Pitfall 2: Personas Too Vague to Drive Design Decisions

**What goes wrong:** Personas are written as demographic sketches without job-specific behaviors. They don't inform which features matter most.
**Why it happens:** Easy to write, hard to make useful.
**How to avoid:** Each persona must answer: what is their workflow today (without the platform)? What specific step breaks down? How do they currently handle ARCO+ requests?
**Warning signs:** A persona description that could describe a user of any B2B SaaS product.

### Pitfall 3: Integration Architecture Left Vague

**What goes wrong:** PRD says "se integra con plataformas de RRHH" without describing what "integration" means in v1 vs. v2.
**Why it happens:** Integrations feel like a later concern.
**How to avoid:** Explicitly separate manual collection flow (v1) from API-based collection (v2/Phase 3). The PRD must describe both.
**Warning signs:** Integration section has no distinction between manual and automated approaches.

### Pitfall 4: Non-Functional Requirements Omitted

**What goes wrong:** PRD lists features but skips performance, security, and compliance NFRs. Phase 1 developers have no constraints to design against.
**Why it happens:** Pre-development PRDs focus on "what" not "how well."
**How to avoid:** Include an explicit NFR section. For a compliance platform, minimum NFRs are: audit log immutability, data retention policy, Spanish-only interface, availability target, maximum response time for dashboard.
**Warning signs:** No "Non-Functional Requirements" section in PRD draft.

### Pitfall 5: Narrative Assumes a Known Audience Profile

**What goes wrong:** Narrative uses examples specific to one vertical (e.g., "your HR director") when the audience profile is unvalidated (D-03).
**Why it happens:** Concrete examples are more compelling, so authors default to specificity.
**How to avoid:** Use universal operator language — "el responsable de compliance en tu empresa" — rather than role-specific titles. Avoid industry-specific jargon.
**Warning signs:** Narrative draft that assumes a specific job title, company size, or industry sector.

---

## Code Examples

This phase produces documents, not code. The patterns below are structural templates, not code samples.

### Strategic Narrative — Opening Section Structure

```markdown
# ARCO Legal — Por qué ahora importa la protección de datos

## La situación: una nueva obligación legal que empieza en diciembre 2026

La Ley 21.719 entra en vigencia el 1 de diciembre de 2026.
Toda empresa que trata datos personales debe estar preparada para recibir
y responder solicitudes ARCO+ de sus clientes y empleados.

**Plazo legal de respuesta:** 30 días corridos.
**Multas por incumplimiento:** hasta 20.000 UTM (~USD 1.4 millones).
```

```markdown
## El problema: las solicitudes se pierden antes de empezar

Hoy, las solicitudes llegan por email, formulario web, carta, o en persona.
No hay un lugar central donde registrarlas.
El plazo corre desde el día que llegan — aunque nadie las haya visto.

Cuando alguien las encuentra, ya pueden quedar 15 días para responder.
```

### PRD — User Personas Section Structure

```markdown
## User Personas

> Note: These are proto-personas based on market context. To be validated 
> with first customers in Phase 1.

### Persona A: El Operador de Compliance

**Role:** Encargado de RRHH / Asistente Legal / Jefa de Administración
**Company size:** 50–500 empleados
**Context:** Maneja cumplimiento como parte de un rol más amplio. No tiene DPO dedicado.
**Current workflow:** Recibe solicitudes ARCO+ por email. Las anota en una planilla 
  o carpeta. No tiene alertas de plazo.
**Key pain:** "Si me llega una solicitud un viernes y no la veo hasta el lunes, 
  ya perdí dos días del plazo."
**Success metric:** Cero solicitudes vencidas. Comprobante exportable para mostrar 
  a la Agencia.

---

### Persona B: El Administrador / Responsable de Empresa

**Role:** Dueño, Gerente General, o Director de RRHH
**Context:** Toma la decisión de compra. No opera la herramienta diariamente.
**Pain:** Exposición legal. No sabe si su empresa está cumpliendo.
**Success metric:** Dashboard que muestre estado de compliance en tiempo real. 
  Trazabilidad ante auditoría.
```

### PRD — Integration Architecture Section Structure

```markdown
## Integration Architecture

### Philosophy: Manual-First → Automated

The platform enables compliance with or without API integrations. 
Integrations accelerate an existing manual workflow.

### v1: Manual-Guided Collection (Phase 2 of platform)

When an operator receives a data access request, they must locate the 
requestor's data across internal systems. In v1:

1. Operator opens the "Collect Data" flow for a request
2. Platform presents a configurable checklist of platforms to check 
   (configured by admin: buk.cl, CRM, email archives, etc.)
3. Operator manually searches each platform and records what was found
4. Platform stores the record with source, date, and operator attribution

**Why manual first:** Validates the workflow before automating. Identifies 
which integrations deliver the most time savings.

### v2/Phase 3: Automated Collection — buk.cl

After validating the manual workflow, the platform adds API-based collection 
starting with buk.cl (most common HR platform in Chilean SMB market):

1. Admin connects company's buk.cl account via OAuth
2. For each ARCO+ request, operator triggers a search by RUT
3. Platform retrieves relevant records (CV, contracts, payroll history)
4. Operator reviews and selects which records to include in the response

### Future Integrations (v2+)
- CRM platforms (INTG-05)
- Email marketing platforms (INTG-06)  
- Public API for custom systems (INTG-07)
```

---

## Legal Context (Verified)

This section documents verified facts about Ley 21.719 that must inform both documents.

[CITED: infoproteccion.com/ley-21719, preyproject.com/ley-proteccion-datos-chile, bcn.cl/leychile Ley 21.719]

| Element | Detail | Confidence |
|---------|--------|------------|
| Nombre completo | Ley 21.719 sobre Protección de Datos Personales | HIGH [CITED: BCN Chile] |
| Fecha de vigencia | 1 de diciembre de 2026 | HIGH [CITED: multiple sources] |
| Derechos ARCO+ | Acceso, Rectificación, Cancelación/Supresión, Oposición, Portabilidad, Bloqueo | HIGH [CITED: infoproteccion.com] |
| Plazo de respuesta | 30 días corridos (ampliable una vez por 30 días adicionales con justificación) | HIGH [CITED: PROJECT.md — sourced by project founders] |
| Multa Leve | Hasta 5.000 UTM | HIGH [CITED: infoproteccion.com] |
| Multa Grave | Hasta 10.000 UTM | HIGH [CITED: infoproteccion.com] |
| Multa Gravísima | Hasta 20.000 UTM (~USD 1.4M) | HIGH [CITED: infoproteccion.com] |
| Multas empresas grandes | 2–4% de ingresos anuales para infracciones reiteradas | HIGH [CITED: preyproject.com] |
| Ente regulador | Agencia de Protección de Datos Personales (autónoma) | HIGH [CITED: PROJECT.md] |
| Período de gracia PyMEs | Primer año (dic 2026 – dic 2027): solo advertencias, no multas | MEDIUM [CITED: preyproject.com — pending official regulation confirmation] |

---

## State of the Art

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| Exhaustive PRD before coding | Lean PRD: essential sections, explicit assumptions, rapid iteration | ~2018–present | PRD should be a living document, not a complete spec — but for pre-development alignment, a solid draft is still needed |
| Monolithic personas (20-page documents) | Proto-personas: role + pain + success metric, flagged as unvalidated | ~2020–present | Enables PRD writing without waiting for user research |
| Integration = full API at launch | Manual-first concierge MVP → API when validated | ~2015–present (popularized by Stripe/Zapier) | Reduces Phase 1 complexity; validates workflow before automating |

**Deprecated/outdated:**
- **Waterfall PRD:** Complete specification before any development. Replaced by iterative PRDs that evolve with the product.
- **Investor-framing for client decks:** Mixing TAM/SAM/SOM into first-client narratives. Modern B2B sales decks center on the buyer's problem, not the seller's market opportunity.

---

## Assumptions Log

| # | Claim | Section | Risk if Wrong |
|---|-------|---------|---------------|
| A1 | Optimal slide density for projected B2B presentations is 3–4 bullet points per section | Architecture Patterns > Pattern 1 | Narrative may be too dense or too sparse for the actual meeting context; adjust after first review |
| A2 | buk.cl is the most common HR platform in Chilean SMB market | Integration Architecture | If target customers use a different HR platform (e.g., Talana, Buk competitor), the v2 integration priority should change; no material impact on PRD structure |
| A3 | No third persona type (firma legal managing multiple companies) needs to appear in v1 PRD | Architecture Patterns > Pattern 2 | If first customer is a firma legal (not a PyME), the PRD needs a third persona and the multi-tenant requirement becomes v1 scope |
| A4 | The 30-day response deadline is confirmed in the actual law text | Legal Context | Already cross-referenced in PROJECT.md by project founders — LOW risk |
| A5 | The narrative should be written as a Markdown document formatted for projection, not as a slide deck in a presentation tool | Standard Stack | If the actual meeting requires PowerPoint/Keynote, the Markdown output will need post-conversion; low effort |

---

## Open Questions

1. **¿Hay un skill `/draft-strategic-presentation` disponible en este proyecto?**
   - What we know: CONTEXT.md mentions the skill is available
   - What's unclear: The skill is not in the project's `.claude/` directory; it appears to be in `/Volumes/Workspace/sandbox/skills/` but there is no `draft-strategic-presentation` skill found there
   - Recommendation: The planner should use the `/draft-strategic-presentation` call as described in CONTEXT.md, or fall back to producing the narrative directly using the framework documented in this research. The structural template in "Code Examples" above is sufficient to proceed without the skill.

2. **¿Cuál es la ruta de salida definitiva para los documentos entregables?**
   - What we know: The project root is `/Volumes/Workspace/cowork/20260413-arco-legal/`
   - What's unclear: Should `STRATEGIC-NARRATIVE.md` and `PRD.md` live at the root, in `docs/`, or in `.planning/`?
   - Recommendation: Root-level or `docs/` — both documents are primary artifacts, not planning artifacts. They should be visible without navigating into `.planning/`.

3. **¿Debe la narrativa estratégica incluir una sección explícita de "roadmap del producto"?**
   - What we know: DOC-01 requires "problema → solución → mercado → diferenciación → roadmap"
   - What's unclear: For a first client meeting (not an investor), the roadmap detail level that's appropriate is unclear — high-level phases vs. specific feature timelines
   - Recommendation: Include a roadmap section at phase-level granularity (3 phases: core, compliance workflows, integrations) without dates. Dates introduce commitment; phase names show trajectory.

---

## Environment Availability

Step 2.6: SKIPPED — Phase 0 produces only documents. No external tools, services, CLI utilities, databases, or runtimes are required to produce Markdown files.

---

## Validation Architecture

Step 4: SKIPPED — `workflow.nyquist_validation` is set to `false` in `.planning/config.json`.

---

## Security Domain

Phase 0 produces documents (narrative + PRD). There is no code, no data processing, no authentication, and no external services involved in this phase.

The PRD itself MUST document security and compliance constraints for the product being designed (even though implementation is Phase 1+):

**NFRs the PRD must include:**
- Audit log must be immutable (AUDIT-04)
- The platform must comply with Ley 21.719 in its own data processing (meta-compliance)
- Authentication: email + password for operators (AUTH-03)
- Data minimization: platform manages the process, does not store personal data of titulares beyond what's operationally necessary
- Spanish-language interface required (market constraint)

Security domain research for Phase 0 itself: NOT APPLICABLE.

---

## Sources

### Primary (HIGH confidence)
- [BCN Chile — Ley 21.719 text](https://www.bcn.cl/leychile/navegar?idNorma=1209272) — official law text
- [InfoProtección — Ley 21.719](https://www.infoproteccion.com/leyes-ciberseguridad/chile/todo-lo-que-debe-saber-sobre-la-ley-21719-en-chile-proteccion-de-datos-personales/) — ARCO+ rights, penalty tiers verified
- [Prey Project — Guía Ley 21.719](https://preyproject.com/es/blog/ley-de-proteccion-de-datos-en-chile) — penalty percentages, SME grace period
- `.planning/PROJECT.md` — project vision, market context, 30-day deadline, verified by project founders

### Secondary (MEDIUM confidence)
- [Codelevate — Ultimate PRD Guide B2B SaaS 2025](https://www.codelevate.com/blog/the-ultimate-prd-guide-for-your-b2b-saas-success-in-2025) — PRD section structure
- [Infrasity — B2B SaaS PRD 2025](https://www.infrasity.com/blog/b2b-saas-prd) — mandatory PRD sections
- [T2D3 — Defining Personas in B2B SaaS](https://www.t2d3.pro/learn/defining-personas-in-b2b-saas-go-to-market-strategies) — proto-persona methodology
- [Aspid Marketing — Storytelling B2B](https://aspid.marketing/historia-storytelling-b2b/) — narrative arc for B2B client meetings
- [QuickCreator — Synthetic Personas 2025](https://quickcreator.io/blog/synthetic-personas-saas-content-marketing-2025/) — proto-persona methodology before user research

### Tertiary (LOW confidence)
- WebSearch results on B2B strategic narrative frameworks — general patterns confirmed by multiple sources but not tied to a single authoritative source

---

## Metadata

**Confidence breakdown:**
- Legal context (Ley 21.719 facts): HIGH — verified from official Chilean law sources
- PRD structure: HIGH — standard B2B SaaS practice, multiple sources agree
- Narrative framework: HIGH — established SCR framework with B2B adaptation
- Persona definitions: MEDIUM — proto-personas based on market context, not user interviews
- Integration architecture pattern: HIGH — concierge/manual-first is well-established SaaS MVP practice

**Research date:** 2026-04-13
**Valid until:** 2026-10-01 (stable domain; legal context stable until regulations change)
