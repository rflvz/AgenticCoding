# Modelo Físico - Agencia de Viajes

## Tablas del Modelo Físico

### Entidades Principales

Sucursales(PK.IdSucursal,Dirección,Localidad,Provincia,Teléfono)

Clientes(PK.NIF,Nombre,Apellidos,Teléfono,Email)

Vuelos(PK.IdVuelo,FechaHoraSalida,FechaHoraLlegada,Origen,Destino,NumPlazasTotales)

Hoteles(PK.IdHotel,Nombre,Dirección,Localidad,Provincia,Teléfono,NumEstrellas)

### Tablas de Relación

ReservasVuelos(PK.IdReservaVuelo,FK.IdCliente,FK.IdVuelo,FK.IdSucursal,Clase)

ReservasHoteles(PK.IdReservaHotel,FK.IdCliente,FK.IdHotel,FK.IdSucursal,Regimen,FechaEntrada,FechaSalida)

