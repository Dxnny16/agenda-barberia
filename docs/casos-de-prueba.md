## Casos de prueba
1.- El barbero tiene una cita de 10:00 a 10:45. Piden una cita de 11:00 a 11:30     - Sí se puede
2.- El barbero tiene una cita de 10:00 a 10:45. Piden una cita a las 10:30 a 11:00 - No se puede (se empalma)
3.- Un barbero termina una cita a las 10:45 y otro cliente quiere agendar una a las 10:45 - si se puede
4.- Un cliente quiere agendar una cita a las 20:40 a 21:10 y la barberia cierra a las 21:00 - no se puede (ya no hay servicio)
5.- Un cliente quiere agendar una cita a las 8:40 a 9:10 y la barberia abre a las 9:00 - no se puede (no hay servicio)
6.- Dos clientes hacen una cita a las 10:45 pero con diferente barbero - si se puede (solo si hay disponibilidad con cada barbero)
7.- Un cliente quiere agendar una cita a las 13:20 pero el barbero tiene un horario de descanso de 13:00 - 14:00 - no se puede porque el barbero esta en horario de descanso
