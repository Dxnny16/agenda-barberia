# Análisis: agenda de citas para una barbería

## Contexto
Caso hipotético: el dueño de una barbería nueva necesita una agenda de citas
para llevar el control de los cortes de su negocio.

## Usuarios
| Rol | Qué necesita |
|---|---|
| Dueño | Ver ganancias, saber qué barbero es el más solicitado, administrar servicios y precios |
| Recepcionista | Ver horarios y disponibilidad de los barberos, agendar citas (por llamada o en persona) y avisar al barbero |
| Barbero | Ver sus citas del día, sus horarios y el nombre del cliente |
| Cliente | Agendar su cita por llamada o por el sistema (V2) |

## Información que maneja el sistema
- Servicios, con precio y duración aproximada
- Barberos: nombre, apellidos y horario
- Clientes: nombre y número de contacto
- Citas: fecha, hora, barbero y servicio
- Días y horarios de apertura de la barbería

## Reglas del negocio
1. No se agendan citas durante el tiempo de preparación posterior a la apertura.
2. La duración del servicio bloquea el horario del barbero.
3. Si el barbero ya tiene una cita en ese horario, no se puede agendar otra encima.
4. Si llega un cliente sin cita, la recepcionista le asigna el primer horario libre sin generar choques.
5. El cliente tiene 10 minutos de tolerancia; después se marca como "no se presentó" y se libera el horario.
6. Se registra la asistencia del barbero para habilitar las citas del día; si falta, el cliente decide reagendar o cambiar de barbero.

## Riesgos identificados
- Clientes que no llegan, cancelan o piden reagendar
- Dos personas intentando agendar el mismo horario al mismo tiempo
- Fallo al registrar una cita
- Ausencia del barbero o de la recepcionista

## Criterio de éxito
El dueño puede llevar el control de su negocio, ver un reporte semanal y
tener un flujo ordenado entre la llegada del cliente y su servicio.

## Versión 1 (MVP)
**Incluye:**
- La recepcionista agenda citas cuando el cliente llama
- El sistema impide citas empalmadas
- El barbero consulta sus citas del día
- Cancelar una cita

**Queda para la V2:**
- Que el cliente agende por sí mismo
- Notificaciones
- Reportes de ganancias
- Registro de asistencia y "no se presentó"
- Reagendar citas

## Decisiones pendientes
- Cuánto tiempo exacto se bloquea después de la apertura
- Si un servicio puede terminar después de la hora de cierre
- Descansos o comida de los barberos
- Con cuánta anticipación se puede cancelar
- Estados de una cita (agendada, completada, cancelada...)