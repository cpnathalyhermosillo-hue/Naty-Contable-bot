# Workflows operativos (agentes + subagentes)

## 1) Onboarding de cliente contable
1. CRM agente crea ficha de cliente.
2. Agente legal solicita documentos (CSF, e.firma, CSD, contratos).
3. Agente checklist valida integridad.
4. Orquestador habilita carpetas Drive + acceso dashboard.

## 2) Ingesta automática por email/WhatsApp
1. Trigger: llega correo/mensaje.
2. Ingesta descarga adjuntos y normaliza nombre.
3. Clasificador separa XML/PDF/otros.
4. Validador fiscal extrae metadatos.
5. Conciliador crea tarea contable.

## 3) Facturación y timbrado
1. Usuario/cliente captura solicitud.
2. Agente valida reglas SAT internas.
3. Conector PAC timbra.
4. Agente notifica al cliente + guarda XML/PDF.
5. Si falla, abre incidente con causa raíz.

## 4) Manifestación de valor
1. Orquestador crea expediente por operación.
2. Agente documental busca pedimentos, CFDI, BL/guías, pólizas.
3. Agente auditor valida consistencia de importes y fechas.
4. Genera paquete final + checklist de cumplimiento.

## 5) Cierre mensual RESICO
1. Agente conciliador cruza ingresos/egresos.
2. Agente fiscal calcula preliminar.
3. Supervisor QA revisa anomalías.
4. Se emite reporte para aprobación humana.
