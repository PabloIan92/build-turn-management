# Modelo de datos

## Entidades

- `Operator`: identificador, alias, rol y estado.
- `Team`: identificador, nombre operativo genérico, miembros y capacidad.
- `Appointment`: identificador, origen externo opcional, ventana, tipo, ubicación aproximada, equipo, estado y versión.
- `Travel`: turno, inicio, fin, origen y destino minimizados.
- `Break`: operador, tipo, inicio y fin.
- `Evidence`: turno, tipo, referencia privada, hash, fecha y autor.
- `Receipt`: turno, número interno, referencia privada y estado.
- `AuditEvent`: actor, acción, entidad, fecha, correlación y metadatos no sensibles.

No guardes contraseñas, tokens, firmas o imágenes en filas de negocio. Conserva referencias con acceso restringido.

## Estados

`planned -> assigned -> traveling -> in_progress -> awaiting_evidence -> completed`

Ramas: `planned|assigned -> cancelled`, `planned|assigned -> rescheduled`, `in_progress|awaiting_evidence -> blocked` y `blocked -> in_progress|cancelled`.

Valida cada transición en el servidor, registra actor y motivo, y aplica control de versión.

## Invariantes

- Un turno completado requiere cierre, actor y evidencia exigida.
- Una persona no puede tener dos turnos activos incompatibles.
- El fin nunca precede al inicio.
- Toda operación externa conserva un identificador de idempotencia.
- Los reportes se derivan de eventos confirmados.
