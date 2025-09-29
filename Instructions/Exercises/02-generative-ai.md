---
lab:
  title: Exploración de la IA generativa en el Portal de la Fundición de IA de Azure
---

# Exploración de la IA generativa en el Portal de la Fundición de IA de Azure

La IA generativa describe una categoría de funcionalidades dentro de la IA que crean contenido. A menudo, las personas interactúan con la inteligencia artificial generativa que se ha integrado en aplicaciones de chat. En este ejercicio, probarás la IA generativa en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes. 

Este ejercicio dura aproximadamente **20** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Recorte de pantalla de la página principal del Portal de la Fundición de IA de Azure.](./media/ai-foundry-portal.png)

1. En la sección **Explorar modelos y capacidades**, busque `gpt-4o`. A continuación, en los resultados de la búsqueda, seleccione el modelo **gpt-4o** para ver sus detalles.

    ![Recorte de pantalla de la página de detalles de gpt-4o.](./media/gpt-4o-details.png)

1. Seleccione **Usar este modelo**.

1. En el asistente para **Crear un proyecto**, escribe un nombre válido para el proyecto. A continuación, expanda **Opciones avanzadas** para especificar la siguiente configuración para el proyecto:
    - **Recurso de Fundición de IA de Azure**: *escriba un nombre válido para el recurso de Fundición de IA.*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Región**: seleccione de cualquiera de las **regiones **recomendadas de Fundición de IA\*.
    
    \**Las implementaciones de modelos están restringidas por cuotas regionales. Si selecciona una región en la que no tiene cuota disponible suficiente, puede que tenga que seleccionar una región alternativa para un nuevo recurso más adelante.*

1. Seleccione **Crear**. Espera a que se cree el proyecto. Esto puede tardar unos minutos.

    Si se le pide que implemente el modelo en otra región, use la configuración predeterminada para hacerlo.

## Exploración de la IA generativa en el área de juegos de chat de Fundición de IA de Azure

1. Una vez creado el proyecto, en el panel de tareas de la izquierda, seleccione **Áreas de juegos**. 

    >*Sugerencia*: Si es necesario, expanda el menú para leer su contenido haciendo clic en el icono "expandir" de arriba.

1. En la página de áreas de juegos de Fundición de IA de Azure, selecciona **Probar el área de juegos de chat**. Cierre cualquier sugerencia o paneles de inicio rápido que se abran.

    El área de juegos de chat es una interfaz de usuario que te permite probar la creación de una aplicación de chat con diferentes modelos de IA generativa.

    ![Recorte de pantalla de la página de detalles de gpt-4o.](./media/chat-playground.png)

    >*Sugerencia*: Si no ve el panel **Configuración** en la pantalla del área de juegos de Chat, expanda el tamaño de la ventana.  

1. Para usar el área de juegos de chat, debes asociarla a un modelo implementado. En el panel **Configuración** del área de juegos de Chat, asegúrese de que se ha seleccionado el modelo **gpt-4o** que implementó anteriormente. 

    >*Nota*: Debe seleccionar *Aplicar cambios* cada vez que realice cambios en el panel **Configuración**.

1. En el panel **Configuración**, observe las instrucciones y el contexto predeterminados del modelo, que deben ser similares a:

    `You are an AI assistant that helps people find information.`

    Estos tipos de instrucciones se conocen normalmente como *indicaciones del sistema* y se usan para proporcionar instrucciones y restricciones para las respuestas del modelo.

1. Revise el panel *Historial de chat*, que contiene algunas indicaciones de ejemplo que le ayudarán a empezar y un cuadro de consultas para escribir sus propias indicaciones. 

1. Vamos a intentar generar una respuesta mediante una indicación con una meta específica. En el cuadro del chat, escribe la siguiente indicación:

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Revise la respuesta. Tenga en cuenta que la respuesta específica que recibe puede variar debido a la naturaleza de la IA generativa.

1. Vamos a probar otra indicación: Escribe lo siguiente:

    ```prompt
    Where's a good location in the city to stay?
    ```

1. Revisa la respuesta, que debe proporcionar algunos lugares para alojarse en París. Observe que la sesión de chat conserva el contexto de las indicaciones anteriores, por lo que sabe que "la ciudad" en cuestión es París.

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

## Visualización del código de cliente

1. En la parte superior de la página "Área de juegos de chat", seleccione **Ver código**.
1. Revise los ejemplos de código, que se proporcionan para varios lenguajes de programación, SDK y opciones de autenticación.

    Estos ejemplos de código pueden ayudar a los desarrolladores a empezar a trabajar rápidamente al compilar aplicaciones cliente que chateen con el modelo implementado.

1. Cierre la ventana de código de ejemplo.

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre **Azure Portal** en [https://portal.azure.com](https://portal.azure.com) y selecciona el grupo de recursos que contiene los recursos que creaste.
1. Seleccione **Eliminar grupo de recursos** y **escriba el nombre del grupo de recursos** para confirmar. El grupo de recursos se elimina.
