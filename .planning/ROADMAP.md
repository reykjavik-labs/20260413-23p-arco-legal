# Roadmap: ARCO Legal

## Overview

El proyecto parte con una fase estratégica (narrativa) antes de tocar código. Una vez alineada la visión, se construye la plataforma en capas: primero la recepción y tracking de solicitudes (el core del compliance), luego los flujos de cumplimiento con auditoría, luego las integraciones con plataformas externas que automatizan la recolección de datos. Cada fase entrega valor independiente; cada una prepara el terreno para la siguiente.

## Phases

- [ ] **Phase 0: Fundación Estratégica** - Narrativa estratégica (via /draft-strategic-presentation)
- [ ] **Phase 1: Plataforma Core** - Recepción de solicitudes ARCO+ + dashboard + tracking de plazos
- [ ] **Phase 2: Flujos de Cumplimiento** - Gestión de respuestas + auditoría + recolección manual
- [ ] **Phase 3: Integración buk.cl** - Primera integración automatizada para recolección de datos personales
- [ ] **Phase 4: Escala y Pulido** - Multi-usuario, reportería avanzada, optimizaciones

---

## Phase Details

### Phase 0: Fundación Estratégica

**Goal**: Producir la narrativa estratégica del producto usando `/draft-strategic-presentation` para reunión presencial con primer cliente o socio estratégico.
**Depends on**: Nothing
**Requirements**: DOC-01, DOC-04
**Success Criteria** (what must be TRUE):

  1. Existe una presentación/narrativa estratégica estructurada (problema → solución → mercado → diferenciación → roadmap) comprensible sin contexto previo
  2. Cualquier co-founder o socio estratégico puede leer el documento y entender exactamente qué se va a construir y para quién
**Plans:** 1 plan

Plans:

- [x] 00-01: Narrativa estratégica (via /draft-strategic-presentation)

---

### Phase 1: Plataforma Core

**Goal**: Empresa puede recibir solicitudes ARCO+ de titulares a través de un formulario público, verlas en un dashboard interno, y saber exactamente cuánto tiempo queda para responder a cada una.
**Depends on**: Phase 0
**Requirements**: INTAK-01, INTAK-02, INTAK-03, INTAK-04, INTAK-05, TRACK-01, TRACK-02, TRACK-03, TRACK-04, TRACK-05, AUTH-01, AUTH-02, AUTH-03, AUTH-04
**Success Criteria** (what must be TRUE):

  1. Un titular puede ingresar a la URL pública de la empresa, llenar el formulario y recibir un email de confirmación con número de seguimiento
  2. El operador ve la solicitud en su dashboard en menos de 1 minuto desde el envío, con el plazo de 30 días ya calculado
  3. El sistema envía alerta automática al operador cuando una solicitud lleva 20, 25 y 29 días sin respuesta
  4. El operador puede solicitar prórroga de 30 días adicionales y el titular recibe notificación automática
  5. Un administrador puede crear la cuenta de empresa, invitar operadores, y los operadores pueden autenticarse
**Plans:** 2 plans

Plans:

- [ ] 01-01: Setup del proyecto web (stack, base de datos, autenticación)
- [ ] 01-02: Formulario público de intake para titulares
- [ ] 01-03: Dashboard interno + sistema de plazos y alertas

---

### Phase 2: Flujos de Cumplimiento

**Goal**: El operador puede gestionar el ciclo de vida completo de una solicitud: asignarla, trabajarla con plantillas, registrar la respuesta, y generar el comprobante de cumplimiento. Toda acción queda en un log inmutable.
**Depends on**: Phase 1
**Requirements**: WORK-01, WORK-02, WORK-03, WORK-04, WORK-05, AUDIT-01, AUDIT-02, AUDIT-03, AUDIT-04, INTG-01
**Success Criteria** (what must be TRUE):

  1. El operador puede cambiar el estado de una solicitud a través de todos los estados (Recibida → En Revisión → Resuelta → Cerrada) y registrar la respuesta entregada
  2. El sistema ofrece plantillas de respuesta por tipo de derecho (acceso, rectificación, supresión, etc.) como punto de partida editable
  3. El titular puede consultar el estado de su solicitud ingresando su número de seguimiento
  4. Existe un log de auditoría por solicitud que registra cada acción con timestamp y usuario, que no puede ser modificado
  5. El operador puede exportar el comprobante de cumplimiento en PDF con el timeline completo de la solicitud
**Plans:** 2 plans

Plans:

- [ ] 02-01: Gestión de estados y asignación de solicitudes
- [ ] 02-02: Plantillas de respuesta por tipo de derecho ARCO+
- [ ] 02-03: Log de auditoría inmutable + exportación PDF y CSV

---

### Phase 3: Integración buk.cl

**Goal**: El operador puede iniciar una búsqueda automatizada en buk.cl para recolectar los datos personales de un titular (ej: CV, historial de contrato) y adjuntarlos a la respuesta de la solicitud sin salir de la plataforma.
**Depends on**: Phase 2
**Requirements**: INTG-02, INTG-03, INTG-04
**Success Criteria** (what must be TRUE):

  1. El operador puede conectar su cuenta de buk.cl desde la configuración de la empresa
  2. Frente a una solicitud activa, el operador puede ejecutar la búsqueda en buk.cl con el RUT del titular y obtener resultados dentro de la plataforma
  3. El operador puede seleccionar qué datos recolectados incluir en la respuesta y el sistema registra la fuente y fecha de cada dato
  4. El flujo completo (solicitud → búsqueda en buk → respuesta) puede completarse sin salir de ARCO Legal
**Plans:** 2 plans

Plans:

- [ ] 03-01: OAuth / conexión de cuenta buk.cl por empresa
- [ ] 03-02: Búsqueda y recolección de datos desde buk.cl por RUT
- [ ] 03-03: Selector de datos recolectados + vinculación a respuesta de solicitud

---

### Phase 4: Escala y Pulido

**Goal**: La plataforma está lista para crecer: múltiples usuarios por empresa con roles diferenciados, reportería exportable para mostrar compliance ante auditores, y mejoras de UX basadas en uso real.
**Depends on**: Phase 3
**Requirements**: (v1 completo — polish + observabilidad)
**Success Criteria** (what must be TRUE):

  1. Un administrador puede ver un resumen de compliance (total solicitudes, % respondidas a tiempo, tiempo promedio de respuesta) para los últimos 12 meses
  2. El reporte de compliance es exportable en CSV y PDF
  3. El sistema soporta al menos 5 operadores simultáneos por empresa sin degradación de rendimiento
  4. El tiempo de carga del dashboard es inferior a 2 segundos con 100 solicitudes activas
**Plans:** 2 plans

Plans:

- [ ] 04-01: Dashboard de métricas de compliance + exportación de reportes
- [ ] 04-02: Optimizaciones de rendimiento y pruebas de carga

---

## Progress

| Phase | Plans Complete | Status | Completed |
|-------|----------------|--------|-----------|
| 0. Fundación Estratégica | 0/2 | Not started | - |
| 1. Plataforma Core | 0/3 | Not started | - |
| 2. Flujos de Cumplimiento | 0/3 | Not started | - |
| 3. Integración buk.cl | 0/3 | Not started | - |
| 4. Escala y Pulido | 0/2 | Not started | - |
