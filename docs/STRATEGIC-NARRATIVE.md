# ARCO Legal — Narrativa Estratégica

**Mensaje Clave**: La Ley 21.719 entra en vigencia en diciembre 2026 con multas de hasta 20.000 UTM — y ARCO Legal cubre el ciclo completo de cada solicitud: recepción, gestión dentro del plazo, y recolección de datos desde tus plataformas.

**Audiencia**: Decision-maker en empresa chilena que trata datos personales. Decide si adoptar ARCO Legal como plataforma de compliance antes de que entre en vigencia la Ley 21.719.

**Insights para la decisión**:

- Qué exige la Ley 21.719, cuándo entra en vigencia, y qué sanciones aplica
- Por qué perder una solicitud en cualquier punto del ciclo genera la misma multa
- Cómo ARCO Legal cierra ese ciclo de extremo a extremo, incluyendo la recolección desde los sistemas actuales de la empresa

---

## 1. El Contexto

La Ley 21.719 de Protección de Datos Personales entra en vigencia el **1 de diciembre de 2026**. Aplica a todas las empresas chilenas que tratan datos personales, sin distinción de tamaño o sector.

- Establece los derechos ARCO+: Acceso, Rectificación, Cancelación/Supresión, Oposición, Portabilidad y Bloqueo
- Las empresas tienen **30 días corridos** para responder cada solicitud (ampliables 30 días adicionales con justificación)
- El ente regulador es la **Agencia de Protección de Datos Personales** — autónoma, con facultades sancionatorias desde el día 1

**Sanciones**:

| Gravedad | Multa |
|----------|-------|
| Leve | Hasta 5.000 UTM |
| Grave | Hasta 10.000 UTM |
| Gravísima | Hasta 20.000 UTM (~USD 1.4M) |
| Grandes reincidentes | 2–4% de ingresos anuales |

**Alcance**: Todas las empresas chilenas que traten datos personales — sin excepción de tamaño ni sector.

---

## 2. El Desafío

**El problema real**: Las empresas no tienen infraestructura para gestionar solicitudes ARCO+. No existe canal de recepción, no hay proceso definido, nadie controla los plazos. Cuando llegue la primera solicitud, la mayoría no sabrá cómo recibirla ni quién la atiende.

**Por qué debe resolverse ahora**: La ley entra en vigencia en diciembre 2026. Las multas aplican desde el día 1 para empresas grandes. Construir un proceso desde cero toma tiempo — el margen se reduce.

**Costo de la inacción**:

- Una sola solicitud perdida o respondida fuera de plazo = multa de hasta **5.000 UTM**
- Incumplimiento sistemático = hasta **20.000 UTM** o **2–4% de ingresos anuales**
- Los datos personales del titular pueden estar dispersos en múltiples plataformas (RRHH, CRM, Google Drive, etc.) — encontrarlos manualmente consume horas del equipo y es fuente de errores que derivan en respuestas incompletas o vencidas

---

## 3. La Gran Idea

**Solución**: ARCO Legal es una plataforma que gestiona el ciclo completo de cada solicitud ARCO+: canal único de recepción para titulares, tracking automático de plazos, gestión y respuesta por el operador, y recolección de datos personales desde las plataformas de la empresa.

La plataforma opera con un **sistema de conectores extensible**:

- Conectores oficiales a plataformas de uso masivo (ej. BUK, Google Drive)
- API abierta para conectores custom a sistemas específicos de cada empresa
- Disponible como SaaS o despliegue on-premise para empresas con restricciones de seguridad o regulación sectorial

**Por qué funciona**: Elimina los dos problemas estructurales — la falta de canal de recepción y control de plazos, y la búsqueda manual de datos en múltiples sistemas.

**Impacto esperado**:

| KPI | Objetivo |
|-----|----------|
| % de solicitudes respondidas dentro del plazo legal | 100% |
| % de solicitudes cerradas sin reclamo posterior | >95% |
| Tiempo promedio de respuesta | Reducción vs. proceso manual |
| Horas de equipo en recolección de datos | Reducción significativa vs. búsqueda manual |

---

## 4. Estrategia

### Elección 1: Flujo completo de punta a punta

- **Hacemos**: Cubrimos todo el ciclo — recepción, gestión, respuesta y recolección de datos
- **No hacemos**: Un tracker simple de plazos sin gestión real
- **Evidencia**: El compliance requiere trazabilidad completa — un tracker solo no elimina el riesgo de multas

### Elección 2: Manual-first antes de automatizar

- **Hacemos**: Validamos el workflow con clientes reales antes de invertir en conectores automáticos
- **No hacemos**: Construir integraciones antes de validar que el proceso funciona
- **Evidencia**: Reduce el riesgo de automatizar un proceso aún no probado; el cycle time de las primeras empresas en producción informa qué integrar primero

### Elección 3: PyMEs primero

- **Hacemos**: Nos enfocamos en PyMEs — las más desatendidas, sin DPO ni herramientas propias
- **No hacemos**: Soluciones enterprise con contratos largos e integraciones profundas desde el día 1
- **Evidencia**: Mayor dolor no atendido, menor competencia, ciclo de venta más corto

### Elección 4: Canal único de recepción

- **Hacemos**: Un formulario público como canal oficial de recepción de solicitudes ARCO+
- **No hacemos**: Múltiples canales paralelos (email, WhatsApp, teléfono) sin centralización
- **Evidencia**: Centralizar elimina el riesgo de solicitudes perdidas en canales no monitoreados

### Elección 5: SaaS + opción on-premise

- **Hacemos**: Ofrecemos ARCO Legal como SaaS (default) y como despliegue on-premise
- **No hacemos**: Forzar a todas las empresas al modelo cloud
- **Evidencia**: Sectores como banca, salud y gobierno tienen restricciones sobre dónde pueden residir los datos personales — sin opción on-premise, ese mercado queda fuera

---

## 5. Ejecución

### Roadmap

| Iniciativa | Fase | Dependencias | Métrica de éxito |
|-----------|------|--------------|-----------------|
| Plataforma Core | 1 | Ninguna | Primera solicitud trackeada end-to-end |
| Flujos de Cumplimiento | 2 | Plataforma Core | Primera solicitud respondida con comprobante |
| Conectores e Integraciones | 3 | Clientes en producción | Primera integración automatizada activa |

### Hitos clave

- [ ] Primera solicitud recibida y trackeada end-to-end
- [ ] Primera solicitud gestionada y respondida con comprobante de cumplimiento
- [ ] Primeros clientes en producción → inicio de desarrollo de conectores

### Workflow operacional

Cada solicitud sigue un tablero Kanban con etapas y definición de listo por etapa:

**Recibida → En Revisión → Recolección de Datos → En Respuesta → Respondida → Cerrada**

Los reclamos post-respuesta siguen el mismo flujo identificados como tipo `Reclamo` *(implicancias legales de plazos a confirmar con asesoría especializada)*.

### Métricas de progreso

- Solicitudes procesadas (volumen creciente)
- % respondidas dentro del plazo legal
- Cycle time por solicitud (desagregado por etapa Kanban)
- % cerradas sin reclamo posterior
