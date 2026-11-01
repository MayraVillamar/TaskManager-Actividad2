# Declaración de Uso de Inteligencia Artificial (AI_DECLARATION.md)

## a. Herramientas de IA utilizadas y momentos de uso
Se utilizó la herramienta **Gemini (Google)** en las siguientes etapas del proyecto:
1. **Fase de Arquitectura y Estructuración:** Generación de la plantilla base HTML5 e integración visual con Tailwind CSS via CDN.
2. **Fase de Lógica de JS:** Implementación del patrón de Eventos Personalizados (`CustomEvent`) para el desacoplamiento del Dashboard y sincronización reactiva.
3. **Fase de Depuración:** Corrección de la lógica de ordenamiento mutable/inmutable sobre el arreglo de tareas.

## b. Prompts clave utilizados durante el desarrollo

### Prompt 1 (Diseño de la estructura JS Vanilla y Reactividad sin Frameworks):
> *"Crea una estructura en JavaScript Vanilla ES6+ para un TaskManager que utilice un patrón de pub/sub o CustomEvents para notificar cuando la lista de tareas cambia, actualizando un dashboard de métricas sin re-renderizar manualmente en cada función."*

### Prompt 2 (Manejo de asincronía y persistencia):
> *"Genera una función asíncrona en JS que consulte `https://jsonplaceholder.typicode.com/todos` con `fetch()`, verifique si `localStorage` está vacío para guardar únicamente 5 elementos iniciales sin duplicar, y capture posibles errores de red mostrando un toast visual."*

## c. Ajustes manuales y correcciones al código sugerido por la IA
- **Formateo de Fechas:** El código sugerido por la IA generaba fechas en formato ISO completo (`YYYY-MM-DDTHH:mm:ss`), por lo que se ajustó manualmente mediante una función auxiliar para mostrar la fecha en formato local amigable (`DD/MM/YYYY`).
- **Validación de Formularios:** Se agregó una capa extra de validación manual para evitar el registro de espacios en blanco en los campos de texto (`title.trim() === ''`).
- **Mapeo de Datos de la API:** La API externa devuelve los datos con la propiedad `completed`, mientras que el esquema interno requiere un objeto extendido con `priority` y `createdAt`. Se ajustó manualmente la función de carga inicial para inyectar estos valores por defecto.
  
