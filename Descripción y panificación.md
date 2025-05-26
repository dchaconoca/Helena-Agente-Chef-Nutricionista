# Agente Generador de Menús para la Semana

## 1. Propósito del Agente

Se trata de un agente tipo chatbot que simula un chef de cocina y nutricionista, y que basado en el contexto del usuario (preferencias alimenticias, objetivos nutricionales, patologías, alergias, disponibilidad, nivel culinario, etc.), genera un menú para la semana. También ofrece la posibilidad de dar recetas o la lista de compras para el menú.

Esto constituiría el MVP para comprobar la habilidad del producto para satisfacer una necesidad.

## 2. Reglas y consideraciones

### Reglas de Negocio

- Chatbot que actúa como chef de cocina y nutricionista.
- Genera menús semanales personalizados. 
- Permite solicitar recetas específicas.
- Genera listas de compras basadas en el menú.
- Permite modificar platos del menú.
- 2 semanas a un mes gratuito, después requiere suscripción.
- Opciones de suscripción mensual y anual.
- Evita repetir platos de una semana a otra.
- En cada nueva sesión, se recuerda el contexto del usuario (si existe) y se pide confirmación. 
- Posibilidad de actualizar el contexto.
- Cancelación o renovación de suscripciones.

### Consideraciones Técnicas

- Acceso e interacción mediante Telegram.
- Almacenamiento de datos (cuenta de usuario, contexto, último menú) en una base de datos, posiblemente Supabase.
- Integración con LLMs para generación de respuestas.
- Exportar menú a Google Sheets.
- Envío de menú por correo electrónico.

### Consideraciones de Seguridad

- Sistema de verificación de identidad del usuario.
- Gestión de acceso según estado de suscripción.
- Almacenamiento seguro de datos de usuario: Identificador del usuario, nombre, fecha de primer acceso, fecha de primera suscripción, fecha de última suscripción, contexto (¿detallado o no?), último menú, email.
- Gestión segura de credenciales (API Keys, acceso a BDs, etc.).
- Protección de información personal.
- Gestión de errores.

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
- **¿Agente multiusuario o venta de agente personalizado e individual?**

## 4. Escenarios Principales

1. **Primer acceso del usuario:** Mensaje de bienvenida con explicación del objetivo del chatbot, creación de cuenta en la base de datos, recopilación de información del usuario (hábitos, objetivo, restricciones, etc.) mediante preguntas, guardado de respuestas como contexto en la base de datos. 
2. **Accesos subsecuentes (usuario existente, sesión gratuita o suscriptor):** Verificación del usuario y el estado de su suscripción, recuperación del contexto de la base de datos, recordatorio del contexto al usuario, confirmación o modificación del contexto por parte del usuario, generación del menú semanal. 
3. **Solicitud de servicios adicionales:** Solicitar cambio de platos del menú, pedir recetas, pedir lista de compras, envío por correo del menú en Google Sheets.
Exportación de información: Envío por correo o exportación a Google Sheets
Gestión de suscripciones: Verificación de límites gratuitos, activación de suscripción

## 5. Planificación

1. **Fase de Diseño (1 semana):**
- Definir arquitectura detallada.
- Diseñar estructura de base de datos.
- Definir flujos de usuario detallados.
- Crear prompts para LLM.

2. **Fase de Desarrollo (2 semanas):**
- Implementar bot de Telegram.
- Configurar base de datos Supabase.
- Desarrollar flujos de trabajo en n8n.
- Integrar LLM para generación de contenido.
- Manejo de errores.
- Implementar sistema de suscripciones.

3. **Fase de Pruebas (1 semana):**
- Pruebas de funcionalidad.
- Pruebas de carga.
- Revisión de seguridad.
- Optimización de prompts para LLM.

4. **Fase de Documentación (1 semana):**
- Crear documentación clara para desarrolladores y usuarios.
- Incluir guías de uso y mantenimiento.

5. **Lanzamiento y Monitoreo (continuo):**
- Lanzamiento de versión beta.
- Monitoreo de uso y rendimiento.
- Recopilación de feedback.
- Mejoras iterativas.