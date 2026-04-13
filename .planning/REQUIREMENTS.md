# Requirements: ARCO Legal

**Defined:** 2026-04-13
**Core Value:** Una empresa puede recibir, gestionar y responder a toda solicitud ARCO+ dentro del plazo legal, sin perder ninguna ni arriesgar multas.

---

## Fase 0: Documentos Estratégicos

Requisitos del entregable inmediato (previo al desarrollo de software).

- [ ] **DOC-01**: Narrativa estratégica estructurada según framework de presentación estratégica (problema → solución → mercado → diferenciación → roadmap)
- [ ] **DOC-02**: PRD.md con personas de usuario, flujos principales, requisitos funcionales y no funcionales
- [ ] **DOC-03**: PRD incluye arquitectura de integraciones (manual-first → API)
- [ ] **DOC-04**: Narrativa es comprensible por co-founders, socios estratégicos e interesados externos sin contexto previo

---

## v1 Requirements (Web App)

### Intake — Recepción de solicitudes

- [ ] **INTAK-01**: Titular puede acceder a un formulario público sin registro para enviar solicitud ARCO+
- [ ] **INTAK-02**: Formulario solicita: tipo de derecho (lista), identificación del titular, descripción, datos de contacto
- [ ] **INTAK-03**: Titular recibe confirmación por email con número de seguimiento
- [ ] **INTAK-04**: Sistema verifica identidad mínima del titular (datos coinciden con RUT/nombre) antes de procesar
- [ ] **INTAK-05**: Operador recibe notificación inmediata de nueva solicitud

### Tracking — Gestión de plazos

- [ ] **TRACK-01**: Operador ve dashboard con todas las solicitudes activas, su tipo, estado y días restantes
- [ ] **TRACK-02**: Sistema calcula y muestra el plazo de vencimiento desde la fecha de recepción (30 días corridos)
- [ ] **TRACK-03**: Sistema envía alertas al operador a los 20, 25 y 29 días de recibida una solicitud sin respuesta
- [ ] **TRACK-04**: Operador puede solicitar prórroga (30 días adicionales) con registro de justificación
- [ ] **TRACK-05**: Sistema notifica al titular cuando se ejerce prórroga

### Workflow — Cumplimiento de solicitudes

- [ ] **WORK-01**: Operador puede asignar una solicitud a un responsable interno
- [ ] **WORK-02**: Operador puede cambiar el estado de una solicitud (Recibida → En Revisión → Resuelta → Cerrada)
- [ ] **WORK-03**: Operador puede registrar la respuesta entregada al titular y adjuntar documentos
- [ ] **WORK-04**: Sistema genera plantillas de respuesta por tipo de derecho ARCO+ como punto de partida
- [ ] **WORK-05**: Titular puede consultar el estado de su solicitud con su número de seguimiento

### Integrations — Recolección de datos

- [ ] **INTG-01**: Operador puede iniciar un flujo de recolección manual: lista de plataformas donde buscar datos del titular
- [ ] **INTG-02**: Sistema se integra con buk.cl para recuperar datos personales de un titular (CV, contratos, historial) de forma automatizada
- [ ] **INTG-03**: Operador puede revisar y seleccionar qué datos recolectados incluir en la respuesta al titular
- [ ] **INTG-04**: Sistema muestra qué datos fueron recolectados, de qué plataforma y en qué fecha

### Audit — Trazabilidad

- [ ] **AUDIT-01**: Cada acción sobre una solicitud queda registrada con timestamp, usuario y descripción (log inmutable)
- [ ] **AUDIT-02**: Sistema genera un comprobante de cumplimiento por solicitud (PDF exportable) con timeline completo
- [ ] **AUDIT-03**: Operador puede exportar el historial de solicitudes en CSV para reportes externos
- [ ] **AUDIT-04**: Log de auditoría no puede ser modificado ni eliminado por usuarios (solo lectura)

### Auth — Acceso y roles

- [ ] **AUTH-01**: Administrador de empresa puede registrar su organización en la plataforma
- [ ] **AUTH-02**: Administrador puede invitar operadores con email corporativo
- [ ] **AUTH-03**: Operador se autentica con email y contraseña
- [ ] **AUTH-04**: Roles: Administrador (configuración + todo) y Operador (solo gestión de solicitudes)

---

## v2 Requirements

### Notificaciones avanzadas

- **NOTF-01**: Integración con Agencia de Protección de Datos (notificaciones formales directas)
- **NOTF-02**: Notificaciones por WhatsApp al titular (canal alternativo)
- **NOTF-03**: Resumen semanal de estado de compliance para el administrador

### Integraciones adicionales

- **INTG-05**: Integración con plataformas CRM (Salesforce, HubSpot)
- **INTG-06**: Integración con plataformas de email marketing (Mailchimp, etc.)
- **INTG-07**: API pública para que empresas conecten sus propios sistemas

### Multi-empresa

- **MULT-01**: Una firma legal o consultora puede gestionar múltiples empresas desde una cuenta
- **MULT-02**: Reportes consolidados cross-empresa para gestores externos

### IA y automatización

- **AI-01**: Asistente IA para redactar respuestas basadas en tipo de solicitud y datos recolectados
- **AI-02**: Clasificación automática de solicitudes entrantes por tipo de derecho

---

## Out of Scope

| Feature | Reason |
|---------|--------|
| App móvil nativa | Web-first; mobile en v2+ cuando haya base de usuarios validada |
| Almacenamiento de datos personales del titular | La plataforma gestiona el proceso, no almacena los datos personales en sí mismos |
| Asesoría legal automatizada | Riesgo regulatorio; la plataforma facilita el proceso, no reemplaza al abogado |
| Integración con Registro Civil (verificación RUT) | Complejidad de acceso a API gubernamental; se hace validación básica en v1 |
| Multilenguaje | Mercado chileno en español; i18n es complejidad innecesaria para v1 |

---

## Traceability

| Requirement | Phase | Status |
|-------------|-------|--------|
| DOC-01 | Phase 0 | Pending |
| DOC-02 | Phase 0 | Pending |
| DOC-03 | Phase 0 | Pending |
| DOC-04 | Phase 0 | Pending |
| INTAK-01–05 | Phase 1 | Pending |
| TRACK-01–05 | Phase 1 | Pending |
| AUTH-01–04 | Phase 1 | Pending |
| WORK-01–05 | Phase 2 | Pending |
| AUDIT-01–04 | Phase 2 | Pending |
| INTG-01 | Phase 2 | Pending |
| INTG-02–04 | Phase 3 | Pending |

**Coverage:**
- Fase 0 requirements: 4 total — mapped ✓
- v1 requirements: 24 total — mapped ✓
- Unmapped: 0 ✓

---
*Requirements defined: 2026-04-13*
*Last updated: 2026-04-13 after initial definition*
