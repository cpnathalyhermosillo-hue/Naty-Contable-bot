# Plan maestro: Sistema Cognitivo Contable (México)

## 1) Objetivo de negocio
Implementar un sistema de agentes y subagentes para automatizar procesos contables/fiscales en México (facturación, timbrado, manifestación de valor, seguimiento de clientes, operación RESICO y marketing), con un despliegue rápido de frontend en Vercel y backend sobre servicios de Google.

## 2) Arquitectura propuesta (MVP en 4 semanas)

### Frontend (rápido en Vercel)
- Next.js + Tailwind + dashboard responsive (desktop/laptop/móvil).
- Módulos: clientes, bandeja de documentos, tareas, alertas SAT, campañas de contenido, WhatsApp.

### Backend (ecosistema Google)
- **Google Cloud Run**: API principal (FastAPI o Node).
- **Cloud SQL (PostgreSQL)**: base de datos multi-cliente.
- **Cloud Storage**: XML/PDF/CFDI/documentos.
- **Pub/Sub + Cloud Tasks**: colas para jobs de OCR, validación fiscal y recordatorios.
- **Gmail API + Drive API + Calendar API**: lectura de emails, archivos, agenda.
- **Vertex AI / Gemini**: extracción inteligente y clasificación documental.

### Integraciones clave México
- Proveedor PAC vía API para timbrado/cancelación de CFDI.
- Conectores SAT (según proveedor autorizado) para estatus y validaciones.
- WhatsApp Business API (Meta/Twilio/WATI) para onboarding y recordatorios.

## 3) Agentes y subagentes (estilo SDD + orquestador)

### Orquestador principal
- Recibe eventos (email, WhatsApp, carga manual, vencimientos).
- Divide tareas entre subagentes y aplica políticas de seguridad.

### Subagentes
1. **Ingesta documental**: lee email, descarga adjuntos, clasifica CFDI/estados de cuenta/constancias.
2. **Validador fiscal**: revisa RFC, uso CFDI, régimen, claves, inconsistencias.
3. **Conciliación contable**: cruza movimientos vs CFDI y sugiere pólizas.
4. **Timbrado/facturación**: genera/cancela CFDI vía PAC.
5. **Manifestación de valor**: arma expediente, checklist y exportables.
6. **CRM contable**: seguimiento por cliente (pendientes, riesgos, SLA).
7. **Marketing IA**: genera contenido para redes, agenda publicaciones y mide leads.
8. **Supervisor QA**: verifica reglas de negocio antes de enviar resultados.

## 4) Modelo de datos mínimo
- `tenants` (despacho/empresa)
- `clients` (clientes finales)
- `tax_profiles` (régimen, obligaciones, certificados)
- `documents` (metadata + hash + origen)
- `invoices` (CFDI emitidos/recibidos)
- `tasks` (workflow y estado)
- `agent_runs` (auditoría de decisiones)
- `campaigns` (contenido y resultados)

## 5) Seguridad y cumplimiento
- Cifrado en tránsito y en reposo.
- Control de acceso por roles (despacho/cliente/operador).
- Auditoría completa de acciones de agentes.
- Separación estricta de datos por cliente (multi-tenant seguro).

## 6) Roadmap recomendado

### Fase 1 (Semana 1-2)
- Dashboard base + alta de clientes.
- Ingesta email/Drive + clasificador documental.
- Workflow de tareas contables.

### Fase 2 (Semana 3)
- Facturación/timbrado con PAC.
- Conciliación y alertas RESICO.
- WhatsApp automatizado para recordatorios.

### Fase 3 (Semana 4)
- Automatización de contenido social.
- Métricas de negocio y tablero ejecutivo.
- Endurecimiento de seguridad y auditoría.

## 7) Entregables que ya puedes operar
- Workflows operativos (docs/workflows_operativos.md).
- Prompts base de agentes (prompts/prompts_agentes.md).
- Skill reusable para orquestación contable (skills/conta-orquestador).
