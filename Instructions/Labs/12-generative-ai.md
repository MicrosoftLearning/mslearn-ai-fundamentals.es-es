---
lab:
  title: Exploración de la IA generativa en el Portal de la Fundición de IA de Azure
---

# Exploración de la IA generativa en el Portal de la Fundición de IA de Azure

La IA generativa describe una categoría de funcionalidades dentro de la IA que crean contenido. Las personas interactúan normalmente con la IA generativa que se ha integrado en aplicaciones de chat. En este ejercicio, probarás la IA generativa en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes. 

## Creación de un proyecto en el portal de Azure AI Foundry

Comencemos creando un proyecto de Fundición de IA de Azure.

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un agente seleccionada.](./media/azure-ai-foundry-home-page.png)

1. En la página principal, selecciona **+ Crear un agente**.

1. En el asistente para **Crear un agente**, escribe un nombre válido para el proyecto. 

1. Selecciona **Opciones avanzadas** y especifica los siguientes valores:
    - **Recurso de Fundición de IA de Azure**: *mantén el nombre predeterminado*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Región**: selecciona una de las siguientes ubicaciones:
        * Este de EE. UU.
        * Centro de Francia
        * Centro de Corea del Sur
        * Oeste de Europa
        * Oeste de EE. UU.

1. Selecciona **Crear** y revisa la configuración. Espera hasta que se complete el proceso de configuración.

    >**Nota**: si recibes un error de permisos, selecciona el botón **Corregirlo** para agregar los permisos adecuados para continuar.

1. Cuando se crea el proyecto, se te mostrará de forma predeterminada el área de juegos Agents en el portal de la Fundición de IA de Azure, que debe tener un aspecto similar a la siguiente imagen:

    ![Captura de pantalla de los detalles de un proyecto de Azure AI en el Portal de la Fundición de IA de Azure.](./media/ai-foundry-project-2.png)

1. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**.

## Exploración de la IA generativa en el área de juegos de chat de Fundición de IA de Azure

1. En la página de áreas de juegos de Fundición de IA de Azure, selecciona **Probar el área de juegos de chat**. El área de juegos de chat es una interfaz de usuario que te permite probar la creación de una aplicación de chat con diferentes modelos de IA generativa.  

1. Para usar el área de juegos de chat, debes asociarla a un modelo implementado. En el área de juegos de chat, selecciona **Crear una implementación**. Busca y selecciona **GPT-4**. 

1. En la ventana *Implementar modelo*, mantén la selección y el nombre predeterminados y selecciona **Implementar**. El modelo puede tardar un momento en implementarse. Para comprobar el estado de la implementación, selecciona *Modelos y puntos de conexión* en el menú de la izquierda, bajo *Mis recursos*.
1. En el área de juegos de chat, puedes usar tu modelo implementado cuando aparezca en el menú de selección *Implementación*. Asegúrate de que esté seleccionado el modelo que has implementado. Recuerda que debes seleccionar **Aplicar cambios** después de realizar cualquier cambio en la *Configuración*. 

1. Ten en cuenta las siguientes formas de mejorar las respuestas de un asistente de IA generativa:
    - Comienza con una meta específica de lo que quieres que haga el asistente
    - Itera en función de mensajes y respuestas anteriores para refinar el resultado
    - Proporciona un origen para establecer la respuesta en un ámbito de información específico
    - Agrega contexto para maximizar la idoneidad y relevancia de la respuesta
    - Establece expectativas claras para la respuesta

1. Vamos a intentar generar una respuesta mediante una indicación con una meta específica. En el cuadro del chat, escribe la siguiente indicación:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Revisa la respuesta. **Nota**: Ten en cuenta que la respuesta específica que recibas puede variar debido a la naturaleza de la IA generativa.
 
1. Vamos a probar otra indicación: Escribe lo siguiente:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Revisa la respuesta, que debe proporcionar algunos lugares para alojarse en París.

1. Vamos a iterar sobre la base de las indicaciones y respuestas anteriores para mejorar el resultado. Escriba la siguiente indicación:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Revisa la respuesta, que debe proporcionar opciones para comer cerca de una ubicación de la respuesta anterior. 

1. Ahora, vamos a proporcionar un origen para fundamentar la respuesta en un ámbito de información específico Escribe lo siguiente: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Revisa la respuesta, que debe proporcionar información basada en el sitio web proporcionado. 

1. Vamos a intentar agregar contexto para maximizar la relevancia de la respuesta. Escriba la siguiente indicación: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Revisa la respuesta y el razonamiento de la misma.  

1. Ahora vamos a establecer expectativas claras para la respuesta Escriba la siguiente indicación:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Revisa la respuesta, que debe proporcionar una lista numerada de lugares de interés para ver en París.

1. Cuando hayas terminado, puedes cerrar la ventana del explorador.
