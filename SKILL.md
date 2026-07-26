---
name: build-turn-management
description: Diseña, implementa, audita o mejora sistemas de turnos operativos, cuadrillas y servicios en campo. Úsalo para agendas, asignaciones, traslados, pausas, evidencia de cierre, comprobantes, tableros, métricas e integraciones con calendarios, hojas de cálculo o almacenamiento, sin incorporar datos reales ni credenciales.
---

# Build Turn Management

Construye sistemas de turnos trazables, configurables y seguros.

## Flujo de trabajo

1. Identifica actores, permisos, calendario, zonas horarias y volumen esperado.
2. Define el modelo y las transiciones con [data-model.md](references/data-model.md).
3. Diseña recorridos operativos y administrativos con [workflows.md](references/workflows.md).
4. Separa dominio, persistencia, interfaz e integraciones.
5. Implementa operaciones idempotentes y concurrencia segura.
6. Protege datos y credenciales siguiendo [security.md](references/security.md).
7. Prueba reglas, permisos, reintentos, cambios de horario y cierres incompletos.
8. Entrega migraciones, configuración sintética, pruebas y guía de despliegue.

## Principios

- Modela cada cambio como transición explícita; no infieras estados desde colores o texto visual.
- Conserva fecha-hora en UTC y zona horaria del negocio.
- Usa identificadores opacos y estables.
- Registra auditoría separada de los datos editables.
- Trata fotos, firmas y comprobantes como referencias protegidas.
- Mantén secretos fuera del código y usa datos sintéticos.

## Alcance

Incluye importación desde calendarios, asignación de equipos, traslado, inicio y cierre, pausas, evidencias, cancelaciones, reprogramaciones, paneles, reportes y métricas. Para nómina, adelantos y pagos usa `$build-workforce-payments`.

## Entregables mínimos

- Mapa de roles y permisos.
- Modelo de datos y máquina de estados.
- Contratos de servicios o API.
- Validaciones y estrategia de concurrencia.
- Pruebas de dominio y permisos.
- Lista de variables de entorno sin valores reales.
- Plan de migración, respaldo y reversión.
