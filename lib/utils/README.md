#### `lib/utils/README.md`

```markdown
# 📁 lib/utils

## 🛠️ Propósito

Este directorio contiene **utilidades** y **helpers** que son utilizados por varias partes de la aplicación, pero que no son lo suficientemente importantes como para pertenecer a `core`. Son funciones o clases auxiliares que proporcionan funcionalidad genérica y reutilizable.

## 📦 Contenido Típico

- **Funciones de ayuda (Helper Functions):** Funciones que realizan tareas comunes (por ejemplo, validación de strings, formateo de números, manipulación de listas).
- **Clases de utilidad (Utility Classes):** Clases con métodos estáticos que proporcionan funcionalidad relacionada (por ejemplo, una clase `NetworkUtils` con métodos para verificar la conectividad de red).
- **Widgets de utilidad:** Widgets personalizados que se reutilizan en varias partes de la UI, pero que no son específicos de ninguna pantalla o feature (por ejemplo, un widget `LoadingIndicator` personalizado).
- **Constantes:** Valores constantes _específicos_ para las utilidades. Si son constantes generales de toda la aplicación, deben ir en `core`.

## 📐 Consideraciones de Diseño

- **Funciones Puras:** Las funciones de ayuda deben ser preferiblemente funciones puras (sin efectos secundarios). Esto las hace más fáciles de probar y reutilizar.
- **Sin Estado:** Las clases de utilidad suelen tener métodos estáticos y no mantienen estado.
- **Reutilizable:** Los elementos en `utils` deben ser diseñados para ser reutilizados en diferentes partes de la aplicación.
- **Específicos:** Las utilidades aquí incluidas no deben ser lo suficientemente importantes para ser incluidas en el `core`.
```
