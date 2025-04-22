---
lab:
  title: Exploración de la IA generativa en el Portal de la Fundición de IA de Azure
---

# Exploración de la IA generativa en el Portal de la Fundición de IA de Azure

La IA generativa describe una categoría de funcionalidades dentro de la IA que crean contenido. Las personas interactúan normalmente con la IA generativa que se ha integrado en aplicaciones de chat. En este ejercicio, probarás la IA generativa en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes. 

## Creación de un proyecto en el portal de Azure AI Foundry

1. En una pestaña del explorador, ve a [Fundición de IA de Azure](https://ai.azure.com?azure-portal=true).

1. Inicie sesión con su cuenta. 

1. En la página principal del Portal de la Fundición de IA de Azure, selecciona **Crear un proyecto**. En Fundición de IA de Azure, los proyectos son contenedores que te ayudan a organizar el trabajo.  

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un proyecto seleccionada](./media/azure-ai-foundry-home-page.png)

1. En el panel *Crear un proyecto*, verás un nombre de proyecto generado, que puedes mantener tal cual. Dependiendo de si has creado un centro en el pasado, verás una lista de *nuevos* recursos de Azure que se van a crear o una lista desplegable de centros existentes. Si ves la lista desplegable de centros existentes, selecciona *Crear nuevo centro*, crea un nombre único para el centro y selecciona *Siguiente*.  
 
    ![Captura de pantalla del panel para crear un proyecto con nombres generados automáticamente para el centro y el proyecto](./media/azure-ai-foundry-create-project.png)

> **Importante**: Necesitarás un recurso de Servicios de Azure AI aprovisionado en una ubicación específica para completar el resto del laboratorio.

1. En el mismo panel *Crear un proyecto*, selecciona **Personalizar** y elige una de las siguientes **Ubicaciones**: Este de EE. UU., Centro de Francia, Centro de Corea del Sur, Oeste de Europa u Oeste de EE. UU. para completar el resto del laboratorio. Después selecciona **Crear**. 

1. Toma nota de los recursos que se crean: 
- Servicios de Azure AI
- Centro de Azure AI
- Proyecto de Azure AI
- Cuenta de almacenamiento
- Key vault
- Resource group  
 
1. Una vez creados los recursos, se mostrará la página *Información general* de tu proyecto. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**.
 
    ![Captura de pantalla del menú izquierdo en la pantalla del proyecto con Servicios de IA seleccionado](./media/azure-ai-foundry-playgrounds.png)  

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

1. Vamos a iterar sobre la base de las indicaciones y respuestas anteriores para mejorar el resultado. Escribe la siguiente indicación:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Revisa la respuesta, que debe proporcionar opciones para comer cerca de una ubicación de la respuesta anterior. 

1. Ahora, vamos a proporcionar un origen para fundamentar la respuesta en un ámbito de información específico Escribe lo siguiente: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Revisa la respuesta, que debe proporcionar información basada en el sitio web proporcionado. 

1. Vamos a intentar agregar contexto para maximizar la relevancia de la respuesta. Escribe la siguiente indicación: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Revisa la respuesta y el razonamiento de la misma.  

1. Ahora vamos a establecer expectativas claras para la respuesta Escribe la siguiente indicación:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Revisa la respuesta, que debe proporcionar una lista numerada de lugares de interés para ver en París.

1. Cuando hayas terminado, puedes cerrar la ventana del explorador.