# FlowZapas - Sistema de Gestión

Proyecto desarrollado para la cátedra de Metodología de Sistemas II (TFI).

## Integrantes
- Paliza
- Monteros
- Peralta

## Descripción del Proyecto
FlowZapas es una solución integral orientada a la gestión de inventario, ventas y facturación para locales comerciales de calzado. La aplicación está construida sobre la plataforma .NET 8 aplicando los principios de Clean Architecture (Arquitectura Limpia) para asegurar una alta mantenibilidad, desacoplamiento y escalabilidad.

## Arquitectura de la Solución
El proyecto se organiza en las siguientes capas:

- **FlowZapas.Domain**: Contiene las entidades principales del negocio, reglas de dominio y enums. No posee dependencias externas.
- **FlowZapas.Application**: Define la lógica de negocio, casos de uso, interfaces de repositorios, DTOs y validaciones. Depende únicamente de `Domain`.
- **FlowZapas.Infrastructure**: Implementa el acceso a datos (Entity Framework Core / SQL), servicios externos y persistencia. Depende de `Application`.
- **FlowZapas.API**: Capa de presentación y puntos de entrada HTTP mediante ASP.NET Core Web API. Expone los endpoints y configura la inyección de dependencias. Depende de `Application` e `Infrastructure`.

## Requisitos Previos
- .NET 8 SDK
- Visual Studio 2022 o Visual Studio Code
- Motor de base de datos SQL compatible

## Ejecución Local
1. Clonar el repositorio.
2. Restaurar dependencias:
   ```bash
   dotnet restore
   ```
3. Ejecutar la API:
   ```bash
   dotnet run --project FlowZapas.API
   ```
