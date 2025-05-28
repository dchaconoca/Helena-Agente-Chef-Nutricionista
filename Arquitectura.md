
# Arquitectura del Chatbot Inteligente con n8n

## Introducción
Chatbot inteligente que utiliza IA (LLM) y que simula un chef de cocina y nutricionista para:

1. Ayudar al usuario a planificar un menú semanal que se adapte perfectamente a sus necesidades nutricionales, restricciones dietéticas, preferencias de sabor y estilo de vida. 
2. Dar recetas de cocina con su lista de compras. 
3. Dar consejos nutricionales y tips de cocina.

Todo basándose en las preferencias del usuario, es decir, su objetivo nutricional, sus patologías, alergias, dietas especiales, gustos, zona geográficas, etc.

Además, envía el menú semanal junto con las recomendaciones por correo (archivo Google Sheets).

En fin, es capaz de conversar sobre cualquier tema de gastronomía y nutrición.

Esto constituiría el MVP para comprobar la habilidad del producto para satisfacer una necesidad y el nivel de aceptación del usuario.

## Descripción General
- Diagrama de arquitectura general.
- Componentes principales del sistema.

- Varios flujos creados en n8n.
- Acceso e interacción mediante Telegram.
- Almacenamiento de datos en una base de datos Supabase: Información de la cuenta de usuario, contexto (preferecnias), último menú, email.
- Integración con LLMs para generación de respuestas: A mayo 2025, Gemini 2.5 Flash Preview Thinking (versión Abril 2025).
- Herramientas utilizadas en los flujos: Google Drive, Google Sheets, Gmail:
    * Exportar menú a Google Sheets.
    * Envío de menú por correo electrónico.

## Flujos de Trabajo en n8n
### Flujo 1: [Nombre del flujo]
- Propósito.
- Descripción de las tareas realizadas.
- Entradas y salidas.

### Flujo 2: [Nombre del flujo]
- Propósito.
- Descripción de las tareas realizadas.
- Entradas y salidas.

### Flujo 3: [Nombre del flujo]
- Propósito.
- Descripción de las tareas realizadas.
- Entradas y salidas.

## Integraciones
- APIs externas utilizadas.
- Servicios de terceros conectados.
- Manejo de autenticación y seguridad.

## Gestión de Datos
- Almacenamiento de datos.
- Formato y estructura de los datos.
- Estrategias de limpieza y validación.

## Escalabilidad y Mantenimiento
- Estrategias para escalar los flujos.
- Monitoreo y depuración.
- Actualización y mejora continua.

## Conclusión
- Resumen de los puntos clave.
- Futuras mejoras y expansiones.

## Anexos
- Recursos adicionales.
- Documentación técnica relevante.
- Referencias.