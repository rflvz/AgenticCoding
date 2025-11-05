# Modelo Físico - Cadena Editorial

## Tablas del Modelo Físico

### Entidades Principales

Sucursales(PK.IdSucursal,Domicilio,Teléfono)

Empleados(PK.NIF,Nombre,Apellidos,Teléfono,FK.IdSucursal)

Revistas(PK.IdRevista,Título,NumRegistro,Periodicidad,Tipo)

Periodistas(PK.NIF,Nombre,Apellidos,Teléfono,Especialidad)

Secciones(PK.IdSeccion,Título,Extensión)

Ejemplares(PK.IdEjemplar,Fecha,NumPaginas,EjemplaresVendidos,FK.IdRevista)

### Tablas de Relación

PublicacionRevistas(PK.IdPublicacion,FK.IdSucursal,FK.IdRevista)

ArticulosPeriodistas(PK.IdArticulo,FK.NIFPeriodista,FK.IdRevista)

SeccionesRevistas(PK.IdSeccionRevista,FK.IdRevista,FK.IdSeccion)

