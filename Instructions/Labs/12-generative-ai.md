---
lab:
  title: "Exploración de la inteligencia artificial generativa con Microsoft\_Copilot"
---
# Exploración de la inteligencia artificial generativa con Microsoft Copilot

En este ejercicio, explorará la inteligencia artificial generativa con Microsoft Copilot. 

## Inicio de sesión en Microsoft Copilot

1. Abra [copilot.microsoft.com](https://copilot.microsoft.com?azure-portal=true) e inicie sesión con su cuenta personal de Microsoft.

1. Microsoft Copilot usa inteligencia artificial generativa para mejorar los resultados de búsqueda de Bing. Esto significa que, a diferencia de la búsqueda sola, que devuelve contenidos existentes, Microsoft Copilot puede elaborar nuevas respuestas basadas en el modelado del lenguaje natural y en la información de la web.  

1. Hacia la parte inferior de la pantalla, verá una ventana **Preguntarme cualquier cosa**. Cuando escriba solicitudes en la ventana, Copilot usa todo el subproceso de conversación para devolver respuestas. Por ejemplo, vamos a intentar formular una serie de preguntas sobre viajes.

## Usar solicitudes para generar respuestas

1. Escriba una solicitud: `What are 3 pros and cons of traveling in the winter?`. Verá que aparecen las opciones *Buscar:...* y *Generar...* antes de la respuesta. El modelo usa las respuestas buscadas como información de base para generar respuestas originales. Observe que el final de la respuesta contiene vínculos a sus orígenes. 

![Captura de pantalla de la respuesta de Copilot a una solicitud de viaje con tres viñetas para las ventajas y tres viñetas para los inconvenientes.](./media/generative-ai/bing-copilot-response-traveling.png) 

> **Nota**: si no ve un mensaje **Generar...* o una respuesta de lista de viñetas, aún no ha visto Copilot en acción. Debe volver al menú de inicio de sesión y conectar la cuenta actual que usa con una cuenta personal. 
 
1. Escriba una solicitud: `Find me 3 more pros`. Lo que significa con este mensaje es que le gustaría ver 3 razones más positivas para viajar en el invierno que aún no se han enumerado. Tenga en cuenta que, con esta solicitud, está pidiendo a Copilot que haga dos cosas que la búsqueda por sí sola no hace: utilizar la respuesta del chat anterior para excluir lo que se devuelve en la nueva respuesta y utilizar el tema del chat anterior sin indicarlo explícitamente. 

1. Escriba una solicitud: `Where are 3 places I can go to find fewer crowds?`. 

    > **Nota**: tenga en cuenta que aunque Copilot es capaz de dar una respuesta relacionada, puede eliminar "recuerdos" anteriores del hilo de conversación a medida que continúa. Como resultado, es posible que las respuestas que obtenga no estén directamente relacionadas con viajar en invierno. Esto se debe en gran medida a las limitaciones de entrada de tokens. Cuando el chat "recuerda" partes anteriores de una conversación, es porque ha guardado una cierta cantidad de tokens de la conversación. A medida que se introduzcan nuevos tokens a través de sus nuevas solicitudes y respuestas, el chat dejará de usar los tokens más antiguos. 

1. El botón **Nuevo tema** situado junto a la ventana de chat es útil. Al hacer clic en él, se borra el subproceso de conversación anterior para que las nuevas respuestas del tema no se basen en el tema anterior. Utilice el icono **Nuevo tema** situado junto a la ventana de chat para borrar el historial de mensajes. 

## Probar la generación de imágenes

1. Ahora veamos un ejemplo de generación de imágenes. Escriba una solicitud: `Create an image of an elephant eating a hamburger`. Observe que aparece un mensaje *Voy a intentar crear eso...* antes de que Copilot devuelva una respuesta. 

    ![Captura de pantalla de elefantes comiendo hamburguesas.](./media/generative-ai/dall-e-elephant.png)

    Es importante observar que la respuesta puede parecerse, pero no ser la misma. Esto se debe a que las respuestas son variadas.  

1. En la respuesta, hay texto en la parte inferior que dice "Con tecnología de DALL-E". Tenga en cuenta cómo DALL-E se basa en modelos de lenguaje grande a medida que la entrada del lenguaje natural genera imágenes. 

1. Vuelva al chat de Copilot haciendo clic en el icono de Microsoft Bing en la esquina superior derecha de la pantalla. 

## Probar la generación de código

1. Ahora vamos a ver un ejemplo de generación y traducción de código. Escriba una solicitud: `Use Python to create a list`. 

1. Escriba la solicitud: `Translate that into C#`. Observe que no ha necesitado especificar qué es "eso", ya que Copilot sabe que se refiere al historial de conversaciones.

## Tarea extra

1. Escriba una solicitud: `What are 3 examples of generative AI helping people?`. Esto puede servirle como lluvia de ideas para su propio Copilot.  
