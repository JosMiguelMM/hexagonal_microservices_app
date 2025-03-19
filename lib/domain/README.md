#### `lib/domain/README.md`

```markdown
# 📁 lib/domain

## 🧠 Propósito

Este directorio contiene las **reglas de negocio** y las **entidades** del dominio de la aplicación. Es el núcleo de la lógica de la aplicación y es independiente de cualquier framework o tecnología específica. Aquí se define _qué_ hace la aplicación, no _cómo_ lo hace.

## 📦 Contenido Típico

- **Entidades:** Clases que representan los objetos de negocio principales de la aplicación (por ejemplo, `User`, `Product`, `Order`). Estas entidades _pueden_ contener lógica de negocio relacionada con su propio estado (por ejemplo, un método `User.isValid()` para validar los datos de un usuario). Generalmente, estas entidades son las que se definen en el `core`.
- **Casos de uso (Use Cases / Interactors):** Clases que encapsulan una única acción o operación de negocio (por ejemplo, `GetUserUseCase`, `CreateProductUseCase`, `LoginUseCase`). Los casos de uso orquestan la interacción entre las entidades y los repositorios.
- **Repositorios (Interfaces):** Interfaces que definen los métodos para acceder a datos (por ejemplo, `UserRepository`, `ProductRepository`). La _implementación_ concreta de estos repositorios se encuentra en la capa `data`. Definir las interfaces en `domain` permite desacoplar la lógica de negocio de la implementación del acceso a datos.
- **Reglas de validación:** Lógica para validar la consistencia de los datos del dominio (por ejemplo, validación de formato de correo electrónico, reglas de negocio complejas). Esto puede estar dentro de las entidades o en clases de validación separadas.
- **Eventos de dominio:** (Opcional) Clases que representan eventos que ocurren en el dominio (por ejemplo, `UserCreated`, `OrderShipped`). Estos eventos se pueden utilizar para notificar a otras partes de la aplicación sobre cambios en el estado del dominio.
- **Excepciones de dominio:** Excepciones específicas que son lanzadas por la lógica de dominio.

## ⚙️ Flujo Típico (con Casos de Uso y Repositorios)

1.  La capa de presentación (`presentation`) llama a un **caso de uso**.
2.  El **caso de uso** utiliza las **entidades** y los **repositorios** (a través de sus interfaces) para realizar la operación de negocio.
3.  El **caso de uso** puede devolver un resultado o lanzar una excepción.

## 🧪 Testing

La capa `domain` es ideal para realizar pruebas unitarias. Se pueden probar los casos de uso y las entidades de forma aislada, utilizando mocks para simular los repositorios. Como la capa `domain` no depende de ningún framework, las pruebas son rápidas y fáciles de escribir.

## ❗ Importante

- La capa `domain` es **independiente** de las capas `data` y `presentation`. No debe tener ninguna dependencia directa con ellas.
- La capa `domain` _puede_ depender de `core` (para utilizar modelos de datos compartidos, constantes, etc.).
- El `domain` es el _corazón_ de la aplicación. Debe ser lo más estable posible y cambiar solo cuando cambian las reglas de negocio.
```
