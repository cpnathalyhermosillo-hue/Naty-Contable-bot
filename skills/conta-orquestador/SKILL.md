---
name: conta-orquestador
description: Orquesta agentes y subagentes para operación contable/fiscal en México. Úsala cuando el usuario pida automatizar facturación, timbrado, ingesta documental, RESICO, seguimiento de clientes o workflows contables con IA.
---

# Conta Orquestador Skill

## Cuándo usar
- Cuando se necesite diseñar o ejecutar flujos contables con agentes.
- Cuando se pida arquitectura con frontend en Vercel y backend en Google.
- Cuando se requieran prompts operativos para subagentes de contabilidad.

## Flujo mínimo
1. Identificar evento de entrada (email, WhatsApp, dashboard, vencimiento).
2. Delegar a subagentes: ingesta -> validación -> conciliación -> acción fiscal.
3. Generar salida auditable: decisión, evidencia, responsable, fecha.
4. Escalar a revisión humana si hay riesgo alto fiscal o faltan documentos.

## Subagentes sugeridos
- Ingesta documental
- Validador fiscal CFDI
- Conciliador contable
- Timbrado/PAC
- CRM y seguimiento
- Marketing y contenido
- QA de cumplimiento

## Entregables estándar
- Checklist de cumplimiento
- Resumen ejecutivo
- Tareas siguientes por prioridad
- Registro de auditoría

## Referencias
- Arquitectura y plan: `references/arquitectura_contable.md`
- Prompts de producción: `references/prompts_operativos.md`
