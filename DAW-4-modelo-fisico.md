# Modelo Físico - Proveedores

## Tablas del Modelo Físico

### Entidades Principales

Proveedores(PK.IdProveedor,Nombre,Dirección,Localidad,Provincia)

Piezas(PK.IdPieza,Nombre,Color,Precio,FK.IdCategoria)

Categorias(PK.IdCategoria,Nombre)

### Tablas de Relación

Suministros(PK.IdSuministro,FK.IdProveedor,FK.IdPieza,Cantidad,Fecha)

