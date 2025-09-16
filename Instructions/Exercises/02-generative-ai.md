---
lab:
  title: Exploración de la IA generativa en el Portal de la Fundición de IA de Azure
---

# Exploración de la IA generativa en el Portal de la Fundición de IA de Azure

La IA generativa describe una categoría de funcionalidades dentro de la IA que crean contenido. Las personas interactúan normalmente con la IA generativa que se ha integrado en aplicaciones de chat. En este ejercicio, probarás la IA generativa en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes. 

Este ejercicio dura aproximadamente **20** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicies sesión. 

1. En el explorador, accede a `https://ai.azure.com/managementCenter/allResources` y selecciona **Crear nuevo**. A continuación, elija la opción para crear un **recurso de Fundición de IA de Azure**.

1. En el asistente para *Crear un proyecto*, escribe un nombre válido para el proyecto.

1. Expande *Opciones avanzadas* y especifica los siguientes valores para el proyecto:
    - **Suscripción** : su suscripción a Azure.
    - **Grupo de recursos**: crea o selecciona un grupo de recursos
    - **Región**: selecciona una de las siguientes ubicaciones:
        * Este de EE. UU.
        * Centro de Francia
        * Centro de Corea del Sur
        * Oeste de Europa
        * Oeste de EE. UU.

    Seleccione **Crear**. Espera a que se cree el proyecto. Esto puede tardar unos minutos.

1. Cuando se cree el proyecto, se te dirigirá a una página *Información general* de los detalles del proyecto.

1. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**. 

    >*Nota*: Expanda el menú para leer su contenido haciendo clic en el icono "expandir" de arriba.

## Exploración de la IA generativa en el área de juegos de chat de Fundición de IA de Azure

1. En la página de áreas de juegos de Fundición de IA de Azure, selecciona **Probar el área de juegos de chat**. El área de juegos de chat es una interfaz de usuario que te permite probar la creación de una aplicación de chat con diferentes modelos de IA generativa.  

    >*Nota*: Si no ve que el panel *Configuración* aparece en la pantalla del área de juegos de chat, expanda el tamaño de la ventana.  

1. Para usar el área de juegos de chat, debes asociarla a un modelo implementado. En el panel *Configuración* del área de juegos de chat, seleccione **+Crear una implementación**. Si se le solicita, seleccione *A partir de modelos base*; de lo contrario, continúe con el paso siguiente. 

1. Busque el modelo **gpt-4o** y seleccione **Confirmar**. Mantenga el nombre del modelo predeterminado, el tipo de implementación y los detalles de la implementación. Después, seleccione **Implementar**.

1. En el área de juegos de chat, puedes usar tu modelo implementado cuando aparezca en el menú de selección *Implementación*. Cierre cualquier sugerencia o paneles de inicio rápido que se abran. 

    >*Nota*: Debe seleccionar **Aplicar cambios** cada vez que realice cambios en *Configuración*. 

1. Vaya al panel *Historial de chat*. Usará el cuadro de consulta para escribir las indicaciones. 

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

1. Revise la respuesta. **Nota**: Ten en cuenta que la respuesta específica que recibas puede variar debido a la naturaleza de la IA generativa.
 
1. Vamos a probar otra indicación: Escribe lo siguiente:

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Revisa la respuesta, que debe proporcionar algunos lugares para alojarse en París.

1. Vamos a iterar sobre la base de las indicaciones y respuestas anteriores para mejorar el resultado. Escriba lo siguiente:
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Revisa la respuesta, que debe proporcionar opciones para comer cerca de una ubicación de la respuesta anterior. 

1. Ahora, vamos a proporcionar un origen para fundamentar la respuesta en un ámbito de información específico Escribe lo siguiente: 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Revisa la respuesta, que debe proporcionar información basada en el sitio web proporcionado. 

1. Vamos a intentar agregar contexto para maximizar la relevancia de la respuesta. Escriba lo siguiente: 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Revisa la respuesta y el razonamiento de la misma.  

1. Ahora vamos a establecer expectativas claras para la respuesta Escriba lo siguiente:
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Revisa la respuesta, que debe proporcionar una lista numerada de lugares de interés para ver en París.

1. Cuando hayas terminado, puedes cerrar la ventana del explorador.

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre **Azure Portal** en [https://portal.azure.com](https://portal.azure.com) y selecciona el grupo de recursos que contiene los recursos que creaste.

1. Selecciona los recursos y selecciona **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminarán los recursos.
