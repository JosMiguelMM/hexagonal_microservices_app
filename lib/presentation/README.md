#### `lib/presentation/README.md`

```markdown
# 📁 lib/presentation

## 🖼️ Propósito

Este directorio contiene la capa de **presentación** de la aplicación. Aquí se encuentran todos los elementos relacionados con la interfaz de usuario (UI) y la gestión del estado de la UI.

## 📦 Contenido Típico

- **Widgets:** Componentes de la interfaz de usuario de Flutter. Se organizan generalmente por pantalla o feature.
- **Screens/Pages:** Representan las diferentes pantallas de la aplicación. Cada pantalla suele estar compuesta por varios widgets.
- **BLoC (Business Logic Components) / Cubit:** Clases que gestionan el estado de la UI y la lógica de presentación. Se utilizan para separar la lógica de la UI de los widgets, haciendo que el código sea más limpio, testeable y mantenible. Se prefieren los Cubits sobre los BLoCs para casos de uso más simples.
- **Providers:** (Si se utiliza `provider` en lugar de o junto con BLoC/Cubit) Clases que proporcionan datos y gestionan el estado de la UI.
- **Rutas (Routing):** Configuración de la navegación entre las diferentes pantallas de la aplicación.
- **Temas (Theming):** Estilos visuales y temas para la aplicación.
- **Localización (Localization):** Soporte para múltiples idiomas.
- **Formularios (Forms):** Widgets y lógica para manejar la entrada de datos del usuario.
- **Animaciones (Animations):** Animaciones personalizadas para la UI.

## 🧱 Arquitectura (Ejemplo con BLoC)

1.  El **usuario interactúa** con un widget (por ejemplo, presiona un botón).
2.  El **widget** envía un evento al **BLoC**.
3.  El **BLoC** procesa el evento, posiblemente interactuando con la capa `domain` (a través de los casos de uso).
4.  El **BLoC** emite un nuevo estado.
5.  El **widget** se reconstruye en respuesta al nuevo estado, mostrando la información actualizada.

## 🧪 Testing

La capa `presentation` se puede probar utilizando:

- **Widget Tests:** Para probar widgets individuales en aislamiento.
- **Integration Tests:** Para probar la interacción entre múltiples widgets y capas de la aplicación.

## ❗ Importante

- La capa `presentation` _depende_ de `domain` (para interactuar con la lógica de negocio a través de casos de uso) y _puede depender_ de `core`.
- La capa `presentation` _no debe_ depender directamente de `data`. Toda la interacción con la capa de datos debe pasar por la capa `domain`.
- El presentation solo deberia encargarse de _mostrar_ datos y de _capturar_ las acciones del usuario. Toda la lógica de negocio se delega al `domain`.
```
