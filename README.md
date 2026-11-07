# Hotel Cinco Estrellas

Base de datos relacional en **MySQL** para la gestión completa de un hotel: reservaciones, habitaciones, clientes, empleados, servicios, facturación y promociones por temporada.

## Overview

El proyecto va desde el modelo entidad-relación hasta una base de datos final con lógica de negocio dentro de la propia base:

- **29 tablas normalizadas**: hotel, habitación, tipo de habitación, reserva, cliente, huésped acompañante, empleados, departamento, servicio, consumo, factura, temporada, paquete promocional, queja, satisfacción, cancelación y más.
- **Triggers** que mantienen la base consistente sin intervención: cambiar el estado de la habitación al ocupar o liberar, validar fechas y precios, aplicar penalizaciones por cancelación, detectar clientes potenciales VIP y llevar la bitácora de habitaciones.
- **Procedimientos almacenados** para la operación diaria, por ejemplo:
  - `sp_registrar_reserva_con_temporada`: crea la reserva con el precio de la temporada.
  - `sp_verificar_disponibilidad_habitaciones`: consulta qué habitaciones están libres.
  - `sp_asignar_upgrade_vip`: sube de categoría a los clientes VIP.
  - `sp_cancelar_reserva` y `sp_procesar_pago_penalizacion`: cancelaciones y cobro de penalizaciones.
  - `sp_factura_rapida`, `sp_display_checkout_total` y `sp_reporte_ingresos_por_mes`: facturación y reportes.
- **Vistas y funciones** para reportes.
- **30 consultas** de ejemplo sobre la base final.

## Estructura

```
Base de datos final y 30 consultas/   Dump final (v8) y las 30 consultas
Iteraciones de la Base de datos/      Dumps v1 a v8 y modelo de MySQL Workbench (.mwb)
Iteraciones del ER/                   Versiones del diagrama entidad-relación
UML_Proyecto_Final.pdf                Diagrama UML
Docuemnto_Proyecto_Fina_Hotel_MAFIA.pdf  Documento del proyecto
Guia_Triggers_Stored_Procedures.pdf   Guía de triggers y procedimientos
```

## Cómo usarlo

1. Instala MySQL 8 (o usa MySQL Workbench).
2. Importa la base final:
   ```bash
   mysql -u root -p < "Base de datos final y 30 consultas/Dump_Proyecto_Final_BD_v8_Final.sql"
   ```
3. Corre las consultas de `30 Consultas.sql`.

## Autor

Christofer Castañeda (con el equipo "MAFIA" del proyecto final de Bases de Datos)
