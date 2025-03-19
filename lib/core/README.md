#### `lib/core/README.md`

```markdown
# 📁 lib/core

## ✨ Propósito

Este directorio contiene los componentes **centrales** y **transversales** de la aplicación. Aquí residen elementos que son fundamentales para el funcionamiento general y que son utilizados por múltiples partes de la aplicación. Es el "corazón" de la arquitectura.

## 📦 Contenido Típico

- **Modelos de datos compartidos:** Clases que representan estructuras de datos comunes utilizadas en toda la aplicación (por ejemplo, un modelo `User` que se usa tanto en la capa de presentación como en la de datos). Estos modelos _no_ deben contener lógica de negocio, solo la estructura de los datos.
- **Constantes:** Valores constantes globales (por ejemplo, URLs de API base, claves de configuración, nombres de rutas). Esto centraliza la configuración y evita la duplicación de código.
- **Excepciones personalizadas:** Clases de excepción específicas de la aplicación que se lanzan cuando ocurren errores. Esto permite un manejo de errores más granular y controlado.
- **Servicios de infraestructura:** Abstracciones de servicios que interactúan con recursos externos (por ejemplo, una interfaz `ApiClient` para realizar peticiones HTTP, una interfaz `DatabaseClient` para acceder a una base de datos, una clase para acceder al almacenamiento local con `shared_preferences`). La _implementación concreta_ de estos servicios va en `data/`.
- **Extensiones:** Métodos de extensión de Dart que añaden funcionalidad a clases existentes (por ejemplo, extensiones para formatear fechas, validar strings, etc.).
- **Tipos de datos abstractos:** Define interfaces o clases abstractas que se utilizan para desacoplar el _dominio_ de implementaciones.

## 📐 Consideraciones de Diseño

- **Alta Cohesión, Bajo Acoplamiento:** Los elementos en `core` deben estar altamente relacionados entre sí y tener dependencias mínimas con otras partes de la aplicación.
- **Reutilizable:** Los componentes en `core` deben ser diseñados para ser reutilizados en diferentes partes de la aplicación.
- **Independiente de la UI:** `core` no debe tener ninguna dependencia directa con la capa de presentación (`presentation`). Debe ser completamente independiente de la interfaz de usuario.
- **Independiente de la implementacion:** `core` no debe tener ninguna dependencia directa con la capa de datos (`data`). Se define la _abstracción_ pero no la _implementación_
```
