# PRD — ARCO Legal: Plataforma de Compliance Ley 21.719

---

## Overview / Problem Statement

La Ley 21.719 sobre Protección de Datos Personales entra en vigencia el 1 de diciembre de 2026. Desde esa fecha, toda empresa que trata datos personales en Chile tiene la obligación legal de responder a solicitudes de derechos ARCO+ — Acceso, Rectificación, Cancelación/Supresión, Oposición, Portabilidad y Bloqueo — dentro de un plazo de 30 días corridos contados desde la recepción de la solicitud. El incumplimiento es sancionado por la Agencia de Protección de Datos Personales con multas de hasta 5.000 UTM para infracciones leves, hasta 10.000 UTM para infracciones graves, y hasta 20.000 UTM para infracciones gravísimas. Para empresas grandes con infracciones reiteradas, la multa puede alcanzar el 2–4% de los ingresos anuales. Los seis derechos ARCO+ establecidos por la ley son explícitos: el titular puede solicitar saber qué datos se tienen sobre él (Acceso), corregir información incorrecta (Rectificación), eliminar sus datos (Cancelación/Supresión), impedir ciertos usos (Oposición), recibir sus datos en formato portátil (Portabilidad), o impedir temporalmente su tratamiento (Bloqueo).

El problema operativo que enfrenta la mayoría de las PyMEs chilenas es estructural: las solicitudes llegan por canales dispersos (email, formulario web, carta, teléfono, de manera presencial), no existe un registro central, y el plazo legal comienza a correr desde el momento de recepción — no desde que alguien la descubre. Una solicitud que llega un viernes y no se revisa hasta el lunes ya ha consumido dos días del plazo. Los datos personales del titular están distribuidos en múltiples plataformas — sistemas de RRHH como buk.cl, CRMs, ERPs, correo corporativo, carpetas compartidas — y recopilarlos manualmente para construir una respuesta completa consume horas de trabajo sin ninguna estructura de seguimiento. La mayoría de las PyMEs no tiene DPO (Delegado de Protección de Datos) dedicado; la responsabilidad recae en alguien con otras funciones que no tiene visibilidad del estado de cumplimiento en tiempo real.

ARCO Legal existe para resolver este problema: una empresa puede recibir, gestionar y responder a toda solicitud ARCO+ dentro del plazo legal, sin perder ninguna ni arriesgar multas. La plataforma centraliza la recepción, calcula los plazos automáticamente, alerta antes del vencimiento, y genera el comprobante de cumplimiento que la empresa necesita si la Agencia de Protección de Datos Personales realiza una fiscalización.

**Base legal para recolección de datos desde plataformas de terceros:** El derecho de acceso establecido por la Ley 21.719 obliga al responsable de datos (la empresa) a entregar al titular toda la información personal que posea sobre él, incluyendo los datos tratados por encargados de tratamiento — terceros que procesan datos en nombre del responsable (plataformas de RRHH, CRMs, servicios de email, etc.). Esto crea la necesidad operativa de buscar en múltiples sistemas para compilar una respuesta completa. La arquitectura de integraciones de la plataforma facilita el cumplimiento de esta obligación legal.

---

## Goals and Success Metrics

**Objetivo primario:** Que una empresa pueda cumplir con las obligaciones ARCO+ de la Ley 21.719 sin perder solicitudes ni vencer plazos.

### Métricas de Éxito — v1

| # | Métrica | Base legal que atiende |
|---|---------|------------------------|
| 1 | 100% de solicitudes recibidas quedan registradas con número de seguimiento | Ley 21.719 — el responsable debe confirmar recepción al titular |
| 2 | 0 solicitudes vencidas por falta de visibilidad (alertas a los 20, 25 y 29 días) | Ley 21.719 — plazo de 30 días corridos improrrogable salvo excepción justificada |
| 3 | Tiempo promedio de primera acción sobre una solicitud inferior a 24 horas desde la recepción | Práctica de cumplimiento — permite margen operativo dentro del plazo legal |
| 4 | Comprobante de cumplimiento exportable para el 100% de las solicitudes resueltas | Ley 21.719 — principio de responsabilidad (accountability): el responsable debe demostrar cumplimiento |
| 5 | Operador puede completar el flujo completo (recepción a cierre) sin salir de la plataforma | Requisito de adopción — si el flujo requiere herramientas externas, se fragmenta la trazabilidad |

---

## User Personas

> Proto-personas basadas en contexto de mercado. A validar con primeros clientes en Phase 1.

---

### Persona A: El Operador de Compliance (Primary User)

**Rol:** Encargado de RRHH / Asistente Legal / Jefa de Administración en PyME chilena (50–500 empleados)

**Contexto:** No tiene DPO dedicado. Maneja cumplimiento como parte de un rol más amplio. Su responsabilidad sobre la Ley 21.719 puede ser explícita o implícita según la empresa.

**Current workflow (sin la plataforma):** Recibe solicitudes ARCO+ por email o en persona. Las anota en planilla Excel o carpeta compartida en Google Drive o SharePoint. No tiene alertas de plazo. Cuando debe responder, busca manualmente en buk.cl, CRM y email los datos del titular. Redacta la respuesta en un documento Word. No genera comprobante ni mantiene log.

**Key pain:** "Si me llega una solicitud un viernes y no la veo hasta el lunes, ya perdí dos días del plazo de 30 días corridos."

**Success metric:** Cero solicitudes vencidas. Comprobante exportable para demostrar cumplimiento ante la Agencia de Protección de Datos Personales.

**A validar:** El título del cargo varía significativamente según tamaño y sector de la empresa.

---

### Persona B: El Administrador / Responsable de la Empresa (Buyer + Admin)

**Rol:** Dueño de empresa, Gerente General, o Director de RRHH en empresa de 50–500 empleados

**Contexto:** Toma la decisión de compra. No opera la herramienta diariamente. Su motivación es reducir la exposición legal y tener visibilidad del estado de cumplimiento.

**Current workflow (sin la plataforma):** Recibe reportes esporádicos del operador. No tiene visibilidad en tiempo real del estado de compliance. En caso de fiscalización, no podría demostrar que las solicitudes fueron respondidas a tiempo.

**Key pain:** "No sé si estamos cumpliendo. Si llega una fiscalización de la Agencia, no tengo cómo demostrar que respondimos a tiempo."

**Success metric:** Dashboard con estado de compliance en tiempo real. Trazabilidad completa ante auditoría.

**A validar:** En empresas pequeñas puede ser la misma persona que Persona A.

---

### Persona C: El Titular (Data Subject — External Actor)

**Rol:** Persona natural que ejerce un derecho ARCO+ (cliente, empleado, ex-empleado, candidato)

**Contexto:** No es "usuario" de la plataforma. Interactúa solo a través del formulario público y la URL de seguimiento. La ley define sus derechos; no necesita ser persuadido de usarlos.

**Current workflow (sin la plataforma):** Envía solicitud por email o carta. No recibe confirmación automática. No tiene forma de saber el estado de su solicitud o si fue recibida.

**Key pain:** "Envié mi solicitud hace 3 semanas y no sé si la recibieron. No sé a quién preguntar."

**Success metric:** Recibe confirmación inmediata con número de seguimiento. Puede consultar estado en cualquier momento sin necesidad de contactar a la empresa.

**Nota:** Esta persona no necesita validación — la ley la define.

---

## User Stories / Main Flows

### Flow 1: Titular envía solicitud ARCO+

**Actor:** Titular (Persona C)

**Base legal:** La Ley 21.719 obliga al responsable de datos a facilitar el ejercicio de los derechos ARCO+. El formulario público cumple esta obligación al proveer un canal formal accesible.

**Steps:**
1. Accede a la URL pública de la empresa (ej: empresa.arcolegal.cl/solicitud)
2. Selecciona tipo de derecho ARCO+ (acceso, rectificación, cancelación, oposición, portabilidad, bloqueo)
3. Completa datos de identificación (nombre, RUT, email, teléfono)
4. Describe su solicitud en texto libre
5. Envía el formulario
6. Recibe email de confirmación con número de seguimiento
7. Puede consultar estado ingresando su número en la URL de seguimiento

---

### Flow 2: Operador gestiona nueva solicitud

**Actor:** Operador (Persona A)

**Base legal:** La Ley 21.719 establece un plazo de 30 días corridos para responder. La prórroga de 30 días adicionales requiere justificación y notificación al titular.

**Steps:**
1. Recibe notificación de nueva solicitud (email + notificación en dashboard)
2. Ve la solicitud en el dashboard con el plazo de 30 días ya calculado y días restantes visibles
3. Revisa los datos del titular y el tipo de derecho solicitado
4. Cambia estado a "En Revisión"
5. Inicia flujo de recolección de datos (manual en v1, automatizado en v2+)
6. Compila la respuesta usando plantilla por tipo de derecho
7. Registra la respuesta y cambia estado a "Resuelta"
8. Sistema genera comprobante de cumplimiento automáticamente

---

### Flow 3: Sistema alerta por vencimiento próximo

**Actor:** Sistema (automático)

**Base legal:** El plazo de 30 días corridos es improrrogable salvo la excepción única de 30 días adicionales con justificación establecida por la Ley 21.719.

**Steps:**
1. Diariamente, el sistema revisa todas las solicitudes activas
2. A los 20 días sin respuesta: genera alerta nivel informativo al operador
3. A los 25 días: genera alerta nivel urgente
4. A los 29 días: genera alerta nivel crítico
5. Si el operador solicita prórroga antes del vencimiento: el plazo se extiende 30 días y el titular es notificado automáticamente

---

### Flow 4: Operador recolecta datos del titular (manual — v1)

**Actor:** Operador (Persona A)

**Base legal:** El derecho de acceso establecido por la Ley 21.719 obliga al responsable a entregar toda la información personal que posea del titular, incluyendo datos procesados por encargados de tratamiento (plataformas de terceros que tratan datos en nombre de la empresa). Esto crea la necesidad operativa de buscar en múltiples sistemas.

**Steps:**
1. Abre el flujo "Recolectar Datos" para la solicitud activa
2. Ve el checklist de plataformas configuradas por el administrador (buk.cl, CRM, email, archivos, etc.)
3. Busca manualmente en cada plataforma por nombre/RUT del titular
4. Registra en la plataforma qué datos encontró, en qué plataforma y la fecha
5. Marca cada plataforma como "revisada" o "sin datos encontrados"

---

### Flow 5: Administrador configura la empresa

**Actor:** Administrador (Persona B)

**Base legal:** La empresa como responsable de datos debe designar un canal claro y accesible para recibir solicitudes ARCO+ (Ley 21.719).

**Steps:**
1. Registra su empresa en la plataforma
2. Configura datos básicos (nombre, RUT empresa, dirección)
3. Personaliza el formulario público (URL, logo)
4. Agrega plataformas al checklist de recolección (buk.cl, CRM, otros)
5. Invita operadores con email corporativo
6. Operadores reciben invitación, crean contraseña y acceden al dashboard

---

## Functional Requirements

### 5.1 Intake — Recepción de Solicitudes

- **INTAK-01:** Titular puede acceder a un formulario público sin registro para enviar solicitud ARCO+. *Base legal: Ley 21.719 exige facilitar el ejercicio de derechos sin condiciones.*
- **INTAK-02:** Formulario solicita: tipo de derecho (6 opciones ARCO+), identificación del titular (nombre, RUT, email, teléfono), descripción de la solicitud.
- **INTAK-03:** Titular recibe confirmación por email con número de seguimiento inmediatamente después de enviar la solicitud.
- **INTAK-04:** Sistema verifica identidad mínima del titular (nombre coincide con RUT) antes de procesar la solicitud.
- **INTAK-05:** Operador recibe notificación inmediata de nueva solicitud (email + notificación en dashboard).

### 5.2 Tracking — Gestión de Plazos

- **TRACK-01:** Dashboard con todas las solicitudes activas, su tipo, estado y días restantes visibles en una sola pantalla.
- **TRACK-02:** Cálculo automático del plazo de vencimiento desde fecha de recepción (30 días corridos). *Base legal: plazo establecido por Ley 21.719.*
- **TRACK-03:** Alertas automáticas al operador a los 20, 25 y 29 días de recibida una solicitud sin respuesta.
- **TRACK-04:** Operador puede solicitar prórroga (30 días adicionales) con registro obligatorio de justificación. *Base legal: Ley 21.719 permite una única prórroga justificada.*
- **TRACK-05:** Sistema notifica al titular automáticamente cuando el operador ejerce la prórroga.

### 5.3 Workflow — Cumplimiento de Solicitudes

- **WORK-01:** Operador puede asignar una solicitud a un responsable interno.
- **WORK-02:** Estados de solicitud: Recibida → En Revisión → Resuelta → Cerrada. El sistema registra cada cambio de estado con timestamp y usuario.
- **WORK-03:** Operador registra la respuesta entregada al titular y puede adjuntar documentos.
- **WORK-04:** Plantillas de respuesta por tipo de derecho ARCO+ como punto de partida editable para el operador.
- **WORK-05:** Titular puede consultar el estado de su solicitud ingresando su número de seguimiento en la URL pública.

### 5.4 Integrations — Recolección de Datos

- **INTG-01:** Flujo de recolección manual: checklist configurable de plataformas donde buscar datos del titular, con registro de resultados por plataforma. *(v1 — Phase 2)*
- **INTG-02:** Integración con buk.cl via OAuth para recuperar datos personales del titular (CV, contratos, historial de remuneraciones) de forma automatizada. *(v2 — Phase 3)*
- **INTG-03:** Operador puede revisar y seleccionar qué datos recolectados de plataformas integradas incluir en la respuesta. *(v2 — Phase 3)*
- **INTG-04:** Sistema registra qué datos fueron recolectados, de qué plataforma y en qué fecha para cada solicitud. *(v2 — Phase 3)*

### 5.5 Audit — Trazabilidad

- **AUDIT-01:** Log inmutable por solicitud: cada acción registrada con timestamp, usuario y descripción. *Base legal: Ley 21.719 principio de responsabilidad (accountability) — la empresa debe demostrar cumplimiento.*
- **AUDIT-02:** Comprobante de cumplimiento exportable en PDF con timeline completo de la solicitud.
- **AUDIT-03:** Exportación del historial de solicitudes en CSV para reportes externos.
- **AUDIT-04:** Log de auditoría no puede ser modificado ni eliminado por usuarios del sistema (solo lectura).

### 5.6 Auth — Acceso y Roles

- **AUTH-01:** Administrador puede registrar su organización en la plataforma.
- **AUTH-02:** Administrador puede invitar operadores con email corporativo.
- **AUTH-03:** Autenticación con email y contraseña.
- **AUTH-04:** Roles: Administrador (configuración + acceso completo) y Operador (solo gestión de solicitudes).

---

## Non-Functional Requirements

| ID | Requisito | Justificación |
|----|-----------|---------------|
| NFR-01 | Log de auditoría inmutable — no puede ser modificado ni eliminado por ningún usuario del sistema | Ley 21.719 principio de responsabilidad (accountability): la empresa debe demostrar cumplimiento ante la Agencia. Referencia: AUDIT-04. |
| NFR-02 | Interfaz completamente en español | Mercado objetivo: empresas chilenas. La ley, la regulación y los titulares operan en español. |
| NFR-03 | Tiempo de carga del dashboard inferior a 2 segundos con 100 solicitudes activas | El operador necesita visibilidad inmediata para actuar dentro de plazos legales. Latencia alta puede resultar en solicitudes no vistas. |
| NFR-04 | Disponibilidad 99.5% (uptime) durante horario laboral chileno (lunes a viernes, 8:00–20:00 CLT) | Solicitudes con plazo legal de 30 días corridos no pueden depender de un sistema caído. |
| NFR-05 | Datos de la plataforma respaldados diariamente con retención mínima de 90 días | Continuidad operativa y recuperación ante desastres. Las solicitudes tienen valor probatorio ante fiscalización. |
| NFR-06 | La plataforma debe cumplir con la Ley 21.719 en su propio tratamiento de datos: minimización de datos, base legal para cada tratamiento, derecho de acceso a datos propios | Meta-compliance: la herramienta de compliance debe ser compliant. Credibilidad del producto exige coherencia. |
| NFR-07 | Contraseñas almacenadas con hash seguro (bcrypt o argon2). Tokens de sesión con expiración configurada. | Seguridad básica de autenticación — referencia: AUTH-03. |
| NFR-08 | Soporte para al menos 5 operadores simultáneos por empresa sin degradación de rendimiento | Escalabilidad mínima para PyMEs con equipos medianos. |
| NFR-09 | Datos personales del titular almacenados solo lo operativamente necesario para gestionar la solicitud. No se almacenan datos recolectados de plataformas terceras más allá del registro de fuente y fecha. | Principio de minimización de datos — Ley 21.719. La plataforma gestiona el proceso, no almacena los datos en sí mismos. |

---

## Integration Architecture

### Philosophy: Manual-First, luego Automatizada

La plataforma está diseñada para que una empresa pueda cumplir con sus obligaciones ARCO+ con o sin integraciones de API. Las integraciones aceleran un flujo de trabajo manual existente; no lo definen. El cumplimiento legal es posible desde el primer día, sin configurar ninguna integración.

**Base legal para la recolección de datos desde plataformas de terceros:** El derecho de acceso establecido por la Ley 21.719 obliga al responsable de datos (la empresa) a entregar al titular toda la información personal que posea, incluyendo los datos tratados por encargados de tratamiento — terceras plataformas que procesan datos por cuenta del responsable. Esto incluye plataformas de RRHH (buk.cl), CRMs, sistemas de email marketing, entre otros. La arquitectura de integraciones aborda esta necesidad operativa de forma progresiva: primero manual guiada, luego automatizada.

### v1: Recolección Manual Guiada (Phase 2)

Referencia: INTG-01

Cuando el operador recibe una solicitud de acceso, debe localizar todos los datos personales del titular dispersos en los sistemas de la empresa. En v1, el flujo es:

1. Operador abre el flujo "Recolectar Datos" para la solicitud activa
2. La plataforma presenta un checklist de plataformas configuradas por el administrador (buk.cl, CRM, email, archivos, etc.)
3. Operador busca manualmente en cada plataforma por nombre/RUT del titular
4. Registra los resultados: qué datos encontró, en qué plataforma y la fecha
5. Marca cada plataforma como "revisada" o "sin datos encontrados"

**Por qué manual primero:** Valida el flujo de trabajo antes de automatizarlo. Identifica qué integraciones ahorran más tiempo por solicitud. Reduce la complejidad de Phase 1. Es adoptable sin configuración técnica.

### v2: Recolección Automatizada — buk.cl (Phase 3)

Referencias: INTG-02, INTG-03, INTG-04

Después de validar el flujo manual, la plataforma agrega recolección automatizada comenzando con buk.cl:

1. Administrador conecta la cuenta de buk.cl de la empresa via OAuth
2. Operador activa búsqueda automatizada por RUT del titular para una solicitud activa
3. Plataforma recupera registros relevantes (CV, contratos, historial de remuneraciones)
4. Operador revisa y selecciona qué datos incluir en la respuesta al titular
5. Sistema registra la fuente, la fecha de recolección y el operador que aprobó la selección

**Por qué buk.cl primero:** Es la plataforma de RRHH más común en PyMEs chilenas. Los datos de empleados (actuales y ex-empleados) representan el caso ARCO+ más frecuente.

### Integraciones Futuras (v2+)

- **INTG-05:** Integración con plataformas CRM (Salesforce, HubSpot)
- **INTG-06:** Integración con plataformas de email marketing (Mailchimp, etc.)
- **INTG-07:** API pública para que empresas conecten sus propios sistemas internos

### Criterios de Decisión para Nuevas Integraciones

Una nueva integración se justifica cuando:

- La plataforma es fuente común de datos personales para el cliente objetivo
- La búsqueda manual toma más de 5 minutos por solicitud
- La plataforma tiene API documentada u OAuth estándar disponible

---

## Out of Scope

Las siguientes características están explícitamente excluidas de v1 para mantener el foco en el problema central.

| Feature | Razón |
|---------|-------|
| App móvil nativa | Web-first; mobile en v2+ cuando haya base de usuarios validada |
| Almacenamiento de datos personales del titular | La plataforma gestiona el proceso, no almacena los datos personales en sí mismos (principio de minimización de datos, Ley 21.719) |
| Asesoría legal automatizada | Riesgo regulatorio; la plataforma facilita el proceso operativo, no reemplaza al abogado |
| Integración con Registro Civil (verificación RUT) | Complejidad de acceso a API gubernamental; validación básica de nombre/RUT en v1 |
| Multilenguaje | Mercado chileno en español; i18n es complejidad innecesaria para v1 |
| Multi-empresa (multi-tenant real) | Arquitectura preparada pero funcionalidad en v2+ (MULT-01 en REQUIREMENTS.md) |
| Modelo de negocio / pricing | Se define por separado, fuera de este PRD (decisiones D-05, D-06 de CONTEXT.md) |
| Stack tecnológico | Se define en Phase 1; este PRD describe comportamiento y restricciones, no implementación |

---

## Open Questions

Las siguientes preguntas están sin resolver antes de iniciar Phase 1 y pueden afectar las decisiones de desarrollo.

1. **Validación de identidad del titular (INTAK-04)**
   - *Lo que sabemos:* INTAK-04 especifica "nombre coincide con RUT" como validación mínima.
   - *Lo que no está claro:* Sin acceso a la API del Registro Civil, la validación será básica (coincidencia de cadena, no verificación oficial). Podrían llegar solicitudes con datos incorrectos o fraudulentos.
   - *Impacto en el desarrollo:* La validación manual por el operador es la mitigación en v1. Definir qué nivel de discrepancia activa revisión manual.

2. **Período de gracia para PyMEs (dic 2026 – dic 2027)**
   - *Lo que sabemos:* Fuentes secundarias indican que el primer año de vigencia tendría solo advertencias sin multas para empresas pequeñas.
   - *Lo que no está claro:* Pendiente confirmación oficial en la regulación. No hay resolución publicada aún.
   - *Impacto en el desarrollo:* Si se confirma, cambia la urgencia percibida del mercado en el primer año, pero no la obligación legal real. No afecta decisiones técnicas.

3. **Perfil exacto del primer cliente (D-03)**
   - *Lo que sabemos:* El perfil puede ser PyME chilena (50–500 empleados), firma legal que gestiona compliance para clientes, u otro.
   - *Lo que no está claro:* El perfil afecta la prioridad de features y qué persona es la principal en v1. Una firma legal requiere multi-tenant (v2); una PyME no.
   - *Impacto en el desarrollo:* Puede cambiar la prioridad de MULT-01 en REQUIREMENTS.md y el orden de desarrollo de integraciones.

4. **Hosting y jurisdicción de datos**
   - *Lo que sabemos:* La Ley 21.719 establece requisitos sobre transferencia internacional de datos personales.
   - *Lo que no está claro:* Qué cloud providers y qué regiones cumplen con "jurisdicción adecuada" según la regulación chilena. Pendiente publicación de la lista de países con protección adecuada por la Agencia.
   - *Impacto en el desarrollo:* Afecta la decisión de cloud provider y región en Phase 1. Crítico para NFR-06 (meta-compliance).

---

## Assumptions

Las siguientes hipótesis se asumen como válidas para comenzar Phase 1. Cada una tiene un riesgo explícito si resulta incorrecta.

1. **buk.cl es la plataforma de RRHH más común en PyMEs chilenas.**
   - *Riesgo si es incorrecto:* Si los clientes objetivo usan principalmente Talana u otras plataformas, la prioridad de integración en Phase 3 cambia. No afecta el flujo manual de v1 ni la arquitectura core.

2. **El titular ejerce sus derechos ARCO+ de forma individual, no colectiva.**
   - *Riesgo si es incorrecto:* Si hay ejercicio colectivo o campañas organizadas de solicitudes, el volumen por empresa podría ser significativamente mayor al proyectado. Las NFR de rendimiento (NFR-03, NFR-08) necesitarían revisión.

3. **El operador de compliance es una persona con otro cargo principal (RRHH, administración, legal).**
   - *Riesgo si es incorrecto:* Si los primeros clientes son empresas más grandes con DPO dedicado, las necesidades de workflow son distintas — más volumen, integración con sistemas legales, reportes avanzados. La Persona A cambiaría significativamente.

4. **50–500 empleados es el rango de empresa objetivo para v1.**
   - *Riesgo si es incorrecto:* Si el primer cliente es más pequeño (< 50 empleados), algunas NFR de rendimiento son irrelevantes. Si es más grande (> 500), los requisitos de roles, volumen y reporting cambian.

5. **El plazo de 30 días corridos está confirmado en el texto de la Ley 21.719.**
   - *Riesgo:* BAJO. Confirmado por múltiples fuentes incluyendo el texto oficial de la ley (BCN Chile). Es un dato fundamental y no cambia.

---

*PRD Version: 1.0*
*Created: 2026-04-13*
*Last updated: 2026-04-13*
*Phase: 0 — Fundación Estratégica*
*Next: Phase 1 begins development based on this PRD*
