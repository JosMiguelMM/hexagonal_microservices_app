#### `lib/data/README.md`

```markdown
# 📁 lib/data

## 🎯 Propósito

Este directorio contiene la **implementación concreta** de la lógica de acceso a datos y, en algunos casos, puede incluir lógica de negocio específica relacionada con la manipulación de datos. Es la capa que interactúa directamente con fuentes de datos externas (API, base de datos, almacenamiento local, etc.).

## 📦 Contenido Típico

- **Repositorios (Implementación):** Clases que implementan las interfaces definidas en `domain/repositories`. Estos repositorios se encargan de obtener y guardar datos utilizando los _data sources_. Aquí se decide _cómo_ se obtienen los datos.
- **Data Sources:** Clases que encapsulan la interacción con fuentes de datos específicas (por ejemplo, `UserApiDataSource` para interactuar con una API de usuarios, `UserLocalDataSource` para interactuar con una base de datos local).
- **Mappers/DTOs (Data Transfer Objects):** Clases que se utilizan para convertir entre los modelos de datos de `core` y los formatos específicos de las fuentes de datos (por ejemplo, convertir un objeto JSON de una API a un modelo `User`).
- **Modelos de datos (si son diferentes de `core`):** Si las fuentes de datos utilizan modelos de datos diferentes a los modelos compartidos en `core`, se pueden definir aquí modelos específicos para la capa de datos.
- **Implementaciones de servicios de infraestructura:** Implementaciones concretas de las interfaces definidas en lib/core. Por ejemplo `HttpApiClient` (implementación concreta de `ApiClient`), `SharedPreferencesClient`, etc.

## 🧱 Arquitectura (Ejemplo con Repositorios y Data Sources)

Un flujo típico en la capa `data` podría ser:

1.  **`presentation`** solicita datos a un repositorio (interfaz definida en `domain`).
2.  El **repositorio (implementación en `data`)** decide qué _data source_ utilizar (por ejemplo, primero intenta obtener datos de la caché local, y si no están disponibles, los obtiene de la API).
3.  El **data source** obtiene los datos (por ejemplo, realiza una petición HTTP a la API o una consulta a la base de datos).
4.  El **data source** puede utilizar un _mapper_ para convertir los datos al formato de modelo de `core`.
5.  El **repositorio** devuelve los datos a la capa `presentation`.

## 🧪 Testing

La capa `data` es ideal para realizar pruebas unitarias y de integración. Se pueden probar los repositorios y data sources de forma aislada para asegurar que interactúan correctamente con las fuentes de datos. Se pueden utilizar mocks para simular las fuentes de datos externas.

## ❗ Importante

- La capa `data` _depende_ de `core` y `domain`, pero `core` y `domain` _no_ deben depender de `data`. Esta es una regla fundamental de la arquitectura hexagonal.
- La capa de data, es la _implementacion_ de las interfaces definidas en el dominio, por lo que si se cambia la implementacion (por ejemplo, cambiar de una base de datos relacional a una no relacional), el dominio no se ve afectado.
```
