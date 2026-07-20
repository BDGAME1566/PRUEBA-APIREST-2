# Reto Técnico - Blazor Web App + API REST

## Descripción

Aplicación desarrollada en **Blazor Web App** (.NET 8, modo de interactividad Server) que consume una **API REST** para obtener y visualizar la información en una grilla.

La aplicación consume directamente el endpoint proporcionado, autenticándose mediante **Bearer Token**, y muestra los datos obtenidos de forma dinámica.

## Estructura del proyecto

```
RetoTecnico/
```

## Requisitos

- .NET SDK 8.0 o superior
- Conexión a Internet para acceder a la API

Verificar la instalación de .NET con:

```bash
dotnet --version
```

## Cómo ejecutar el proyecto

1. Abrir una terminal en la carpeta del proyecto.

```bash
cd RetoTecnico
```

2. Ejecutar la aplicación.

```bash
dotnet run
```

3. Abrir la URL indicada en la consola (por ejemplo `https://localhost:xxxx`).

La aplicación cargará automáticamente la información consumiendo la API REST.

## API consumida

**Endpoint**

```
https://mainserver.ziursoftware.com/Ziur.API/basedatos_01/ZiurServiceRest.svc/api/DocumentosFillsCombos
```

La autenticación se realiza mediante **Bearer Token** configurado en el servicio encargado de realizar las peticiones HTTP.

## Arquitectura y decisiones técnicas

- **Blazor Web App (.NET 8) con Interactive Server**, aprovechando el modelo de renderizado interactivo del servidor.
- **Separación de responsabilidades**, organizando el proyecto en modelos, servicios y componentes.
- **Inyección de dependencias**, registrando el `HttpClient` mediante `AddHttpClient`.
- **Consumo asíncrono** de la API utilizando `async` y `await`.
- **Deserialización automática** de la respuesta JSON hacia el modelo utilizado por la aplicación.
- **Manejo de estados de carga y errores**, mejorando la experiencia del usuario durante el consumo de la API.

## Estructura esperada de la respuesta

```json
[
  {
    "Codigo": 29,
    "Descripcion": "Ajuste al Inventario",
    "VActiva": false
  },
  {
    "Codigo": 51,
    "Descripcion": "Avance Produccion",
    "VActiva": false
  },
  {
    "Codigo": 17,
    "Descripcion": "Balance Inicial",
    "VActiva": false
  }
]
```