## Documentación del Proyecto Flutter: `hexagonal_microservices_app`

### Configuración del Entorno de Desarrollo y Creación del Proyecto

Este documento detalla los pasos para configurar el entorno de desarrollo Flutter y crear el proyecto `hexagonal_microservices_app` siguiendo una arquitectura hexagonal (arquetipo móvil).

#### 1. Configuración del Entorno de Desarrollo

**Requisitos Previos:**

- **Flutter SDK:** Asegúrate de tener la última versión estable del Flutter SDK instalada y configurada en tu sistema. Puedes seguir las instrucciones oficiales de instalación en [https://flutter.dev/docs/get-started/install](https://flutter.dev/docs/get-started/install). Es _fundamental_ que verifiques que Flutter esté correctamente configurado ejecutando `flutter doctor` en tu terminal. Este comando te indicará si hay algún problema con tu instalación (variables de entorno, herramientas de línea de comandos de Android, etc.).

- **Android Studio:** Descarga e instala Android Studio desde [https://developer.android.com/studio](https://developer.android.com/studio). Durante la instalación, asegúrate de instalar el _Android SDK_ y las _Android SDK Build-Tools_ recomendadas. También es importante instalar un _Android Virtual Device (AVD)_ para emular dispositivos Android. Android Studio proporciona un gestor de AVD muy fácil de usar.

- **Xcode (solo para desarrollo en iOS):** Si planeas desarrollar para iOS, necesitarás una Mac con Xcode instalado. Descarga Xcode desde la Mac App Store. Después de la instalación, abre Xcode y acepta los términos y condiciones. También es recomendable instalar las herramientas de línea de comandos de Xcode ejecutando `xcode-select --install` en tu terminal. Configura el simulador de iOS dentro de Xcode.

- **Editores / IDEs:** Si bien Android Studio y XCode son fundamentales, para la edicion de codigo se puede utilizar VS Code, Android Studio o algun otro editor de codigo con soporte para Dart y Flutter. Se recomienda instalar las extensiones de Dart y Flutter.

#### 2. Creación del Proyecto Flutter

Una vez que tengas tu entorno configurado, crea el nuevo proyecto Flutter con el nombre `hexagonal_microservices_app` ejecutando el siguiente comando en tu terminal:

```bash
flutter create hexagonal_microservices_app
```

Este comando creará una estructura de proyecto Flutter básica.

#### 3. Implementación de la Estructura de Carpetas (Arquitectura Hexagonal)

El proyecto utiliza la siguiente estructura de carpetas, basada en el arquetipo móvil y los principios de la arquitectura hexagonal:

```
lib/
├── core/      # Componentes centrales y transversales de la aplicación.
├── data/      # Implementación concreta de acceso a datos y lógica de negocio.
├── domain/    # Reglas de negocio y entidades del dominio.
├── presentation/ # Capa de presentación (UI) y gestión de estado.
└── utils/     # Utilidades y helpers.
```

Ya has creado esta estructura, lo cual es excelente. A continuación, detallaremos el contenido de cada directorio.

#### 4. Configuración del Archivo `pubspec.yaml`

El archivo `pubspec.yaml` (que ya has proporcionado) está configurado correctamente con las dependencias necesarias:

```yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8 # Iconos estilo iOS
  http: ^1.1.0 # Para peticiones HTTP
  provider: ^6.0.5 # Gestión de estado simple
  flutter_bloc: ^8.1.3 # Gestión de estado con BLoC
```

- **http:** Se utiliza para hacer llamadas a APIs, crucial para un backend de microservicios.
- **provider:** Una forma sencilla y eficiente de gestionar el estado de la app a nivel de widgets. Una buena opción para empezar, especialmente si no estás familiarizado con BLoC.
- **flutter_bloc:** Una librería más robusta para gestión del estado que implementa el patrón BLoC (Business Logic Component). Ofrece una separación clara entre la lógica de presentación y la lógica de negocio.
- **cupertino_icons:** Proporciona iconos al estilo de iOS.

Para instalar estas dependencias, ejecuta el siguiente comando en la raíz del proyecto (donde se encuentra `pubspec.yaml`):

```bash
flutter pub get
```

#### 5. Verificación

- **Instalación de Dependencias:** Asegúrate de que el comando `flutter pub get` se ejecute sin errores. Esto descargará e instalará todas las dependencias listadas en `pubspec.yaml`.

- **Estructura de Carpetas:** Verifica que la estructura de carpetas dentro de `lib/` coincida exactamente con la descrita en el punto 3.

- **Compilación:** Intenta compilar el proyecto para asegurarte de que no hay errores de configuración:

  ```bash
  flutter build apk  # Para Android
  flutter build ios  # Para iOS (solo en macOS)
  ```

  O bien, puedes ejecutarlo en un emulador/simulador o dispositivo físico:

  ```bash
   flutter run
  ```
