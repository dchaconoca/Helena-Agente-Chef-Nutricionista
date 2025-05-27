
# Helena: Asistente Chef de cocina y Nutricionista
## Chatbot Inteligente con n8n

## 1. Propósito del Agente

Chatbot inteligente que utiliza IA (LLM) y que simula un chef de cocina y nutricionista para:

1. Ayudar al usuario a planificar un menú semanal que se adapte perfectamente a sus necesidades nutricionales, restricciones dietéticas, preferencias de sabor y estilo de vida. 
2. Dar recetas de cocina con su lista de compras. 
3. Dar consejos nutricionales y tips de cocina.

Todo basándose en las preferencias del usuario, es decir, su objetivo nutricional, sus patologías, alergias, dietas especiales, gustos, zona geográficas, etc.

Además, envía el menú semanal junto con las recomendaciones por correo (archivo Google Sheets).

En fin, es capaz de conversar sobre cualquier tema de gastronomía y nutrición.

Esto constituiría el MVP para comprobar la habilidad del producto para satisfacer una necesidad y el nivel de aceptación del usuario.

## 2. Reglas y consideraciones

### Reglas de Negocio

- Chatbot que actúa como chef de cocina y nutricionista.
- Genera menús semanales personalizados. 
- Permite solicitar recetas específicas.
- Genera listas de compras basadas en el menú o las recetas.
- Evita repetir platos de una semana a otra.
- Posibilidad de actualizar el contexto.
- Posibilidad de exportar el menú a Google Sheets y enviarlo por correo.
- Capaz de guardar la información del usuario para evitar repeticiones.
- Elimina la información del usuario si este se lo pide.

### Consideraciones Técnicas

- Varios flujos creados en n8n.
- Acceso e interacción mediante Telegram.
- Almacenamiento de datos en una base de datos Supabase: Información de la cuenta de usuario, contexto (preferecnias), último menú, email.
- Integración con LLMs para generación de respuestas: A mayo 2025, Gemini 2.5 Flash Preview Thinking (versión Abril 2025).
- Herramientas utilizadas en los flujos: Google Drive, Google Sheets, Gmail:
    * Exportar menú a Google Sheets.
    * Envío de menú por correo electrónico.

### Consideraciones de Seguridad

- Gestión de errores.

A futuro:

- Sistema de verificación de identidad del usuario.
- Gestión de acceso según estado de suscripción.
- Mayor protección de información personal.

### Consideraciones suplementarias 

Estas consideraciones permitirán afinar las funcionalidades existentes o definir evoluciones futuras.

1. Integración con plataformas de pago y suscripción:
- ¿Qué plataforma de pago se utilizará para gestionar las suscripciones?
- ¿Se implementará renovación automática?
- ¿Habrá diferentes niveles de suscripción?

2. Almacenamiento y privacidad:
- ¿Cómo se gestionará el cumplimiento de normativas de privacidad?

5. Escalabilidad:
- ¿Cuántos usuarios concurrentes se espera tener?
- ¿Qué modelos LLM se utilizarán y cómo se gestionará su costo?

## 3. Funcionalidades adicionales a futuro

Más allá del MVP:
- Implementar un mecanismo de feedback para mejorar la aplicación.
- Incluir valores nutricionales en los menús y recetas.
- Otros canales de acceso además de Telegram (app móvil, web, Whatsapp).
- Gestión del historial de menús más allá del último generado, para consulta por parte del usuario.
- Posibilidad de almacenar platos preferidos del usuario para incluirlos con frecuencia en el menú.
- Incluir base de datos con recetas propias.
- Incluir base de datos con información nutricional, de expertos nutricionista.
- Reemplazar el flujo en n8n por herramientas más robustas.

## 4. Escenarios Principales

1. **Primer acceso del usuario:** Mensaje de bienvenida con explicación del objetivo del chatbot, creación de cuenta en la base de datos, recopilación de información del usuario (hábitos, objetivo, restricciones, etc.) mediante preguntas, guardado de respuestas como contexto en la base de datos. 
2. **Accesos subsecuentes (usuario existente):** Recuperación de la información del usuario. Respuestas basadas en las preferencias del usuario (contexto): Cambio del menú, recetas, lista de compras, consejos nutricionales, tips de cocina, etc.
3. **Solicitud de servicios adicionales:** 
- Extracción del menú a Google Sheets y envío por correo.
- Modificación de las preferencias del usuario (contexto) o el correo.
- Eliminación de la información del usuario.
