# Flujos operativos

## Preparación

1. Importa o crea turnos.
2. Normaliza zona horaria, duración, tipo y ubicación.
3. Detecta duplicados con un identificador estable.
4. Asigna equipo según capacidad, competencias y disponibilidad.
5. Publica sólo la información mínima necesaria para cada rol.

## Ejecución

1. Confirma identidad y permiso.
2. Registra traslado de forma explícita.
3. Inicia el turno con control de concurrencia.
4. Registra pausas por separado.
5. Reúne evidencia requerida y valida formato y tamaño.
6. Cierra mediante una transacción idempotente.
7. Genera comprobante y métricas en segundo plano.

## Administración

- Reprograma sin perder historial.
- Cancela con motivo normalizado.
- Corrige mediante eventos compensatorios.
- Filtra por fecha, equipo, tipo y estado.
- Mide puntualidad, duración, traslados, pausas, cierres y excepciones.

## Casos de prueba

- Importación repetida.
- Dos operadores iniciando el mismo turno.
- Cambio de horario de verano.
- Cierre sin evidencia.
- Archivo inválido o demasiado grande.
- Reintento después de error externo.
- Usuario sin permiso administrativo.
