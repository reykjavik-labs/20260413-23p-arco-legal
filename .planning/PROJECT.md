# ARCO Legal — Plataforma de Compliance Ley 21.719

## What This Is

SaaS B2B para empresas chilenas que necesitan cumplir con la Ley 21.719 de Protección de Datos Personales (vigente desde diciembre 2026). La plataforma recibe solicitudes ARCO+ de personas naturales (titulares), gestiona los plazos de respuesta obligatorios de 30 días, y facilita la recolección de datos personales desde plataformas integradas. Apunta a PyMEs chilenas que no cuentan con equipos legales o DPO dedicados.

## Core Value

Una empresa puede recibir, gestionar y responder a toda solicitud ARCO+ dentro del plazo legal, sin perder ninguna ni arriesgar multas.

## Requirements

### Validated

<!-- Nada aún — se valida al hacer ship -->

(None yet — ship to validate)

### Active

<!-- Scope actual. Construyendo hacia aquí. -->

- [ ] Titular puede enviar solicitudes ARCO+ a través de un formulario público
- [ ] Operador puede ver todas las solicitudes activas con sus plazos en un dashboard
- [ ] Sistema alerta antes de que venza el plazo de 30 días
- [ ] Operador puede marcar solicitudes como respondidas y registrar la respuesta
- [ ] Sistema mantiene un log de auditoría inmutable por solicitud
- [ ] Operador puede recolectar datos personales desde plataformas integradas (buk.cl)
- [ ] Sistema genera comprobante de cumplimiento exportable

### Out of Scope

- App móvil nativa — web-first, mobile en v2+
- Integración con Agencia de Protección de Datos (notificaciones directas) — v2
- IA generativa para redactar respuestas — v2
- Multi-empresa (multi-tenant real) — arquitectura preparada, funcionalidad en v2

## Context

**Marco legal:**
- Ley 21.719 entra en vigencia el 1 de diciembre de 2026
- Derechos ARCO+: Acceso, Rectificación, Cancelación/Supresión, Oposición, Portabilidad, Bloqueo
- Plazo: 30 días corridos para responder (ampliable una vez por otros 30 días, con justificación)
- Sanciones: Leve ≤5.000 UTM, Grave ≤10.000 UTM, Gravísima ≤20.000 UTM
- Empresas grandes con infracciones reiteradas: 2–4% de ingresos anuales
- Ente regulador: Agencia de Protección de Datos Personales (autónoma)

**Contexto de mercado:**
- La mayoría de las PyMEs chilenas no tienen DPO ni herramientas de compliance de datos
- Las solicitudes llegan por múltiples canales (email, formulario web, presencial)
- La data personal está dispersa en múltiples plataformas: RRHH (buk.cl), CRMs, ERPs, email
- El proceso manual es propenso a errores y pérdida de solicitudes

**Entregable inmediato (Fase 0):**
- Narrativa estratégica (usando framework /draft-strategic-presentation)
- PRD.md inicial desde el cual partir con el desarrollo

## Constraints

- **Legal**: Cumplir con la Ley 21.719 en el diseño de la plataforma misma (mínimo de datos, base legal, etc.)
- **Timeline**: Ley vigente desde diciembre 2026 — ventana de mercado estrecha para capturar early adopters
- **Stack**: Por definir en PRD (debe ser cloud, escalable, con base de datos auditada)
- **Idioma**: Interfaz en español — mercado chileno primero

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| SaaS B2B sobre consultoría + tool | Escalabilidad, ingresos recurrentes, mayor impacto con menos recursos humanos | — Pending |
| Foco en PyMEs primero | No tienen equipos legales, mayor dolor, menor competencia que en enterprise | — Pending |
| Fase 0 = narrativa + PRD antes de código | Alinear visión y validar antes de invertir en desarrollo | — Pending |

---
*Last updated: 2026-04-13 after project initialization*
