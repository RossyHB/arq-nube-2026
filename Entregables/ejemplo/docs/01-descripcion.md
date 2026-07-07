# 01 — Descripción de la aplicación

## ¿Qué hace la app?

**TurnApp** es una aplicación web para gestión de turnos médicos. Permite que pacientes saquen turnos en línea y que profesionales de salud gestionen su agenda del día.

## ¿Por qué la eligieron?

Muchos consultorios siguen coordinando turnos por WhatsApp o llamadas telefónicas, lo que genera superposiciones, olvidos y mala experiencia. TurnApp resuelve ese problema con una interfaz simple y sin fricción.

## ¿A quién está dirigida?

Consultorios y clínicas pequeñas, y sus pacientes.

## Base de datos: PostgreSQL

Elegimos una base de datos **relacional** porque los datos tienen relaciones claras: pacientes → turnos → profesionales. Necesitamos consistencia transaccional para evitar que dos pacientes reserven el mismo horario. PostgreSQL además tiene soporte nativo para tipos de fecha y hora, lo que simplifica las consultas de agenda.
