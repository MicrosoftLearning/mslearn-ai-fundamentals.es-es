---
lab:
  title: Análisis de texto con Language Studio
---

# Análisis de texto con Language Studio

En este ejercicio explorará las funcionalidades del lenguaje de Azure AI mediante el análisis de algunas reseñas de hoteles de ejemplo. Usará Language Studio para comprender si las reseñas son principalmente positivas o negativas.

El procesamiento de lenguaje natural (NLP) es una rama de inteligencia artificial que se ocupa del lenguaje escrito y hablado. Puede usar NLP para crear soluciones que extraigan el significado semántico de instrucciones habladas o escritas, o que formulen respuestas adecuadas en lenguaje natural.

Por ejemplo, supongamos que el agente de viajes ficticio Margie's Travel anima a los clientes a enviar opiniones de sus estancias en hoteles. Puede usar el servicio de lenguaje para identificar frases clave, determinar qué revisiones son positivas y cuáles negativas, o analizar el texto de reseña en busca de menciones de entidades conocidas como ubicaciones o personas.

Lenguaje de Azure AI incluye funcionalidades de análisis de texto y NLP. Estos incluyen la identificación de frases clave en texto y la clasificación del texto en función de la opinión.

## Creación de un recurso de *Language*

Puede usar muchas características de lenguaje de Azure AI con un recurso **Language** o **servicios de Azure AI**. Hay algunas instancias en las que solo se puede usar un recurso Language. Para el siguiente ejercicio, usaremos un recurso de **Language**. Si aún no lo ha hecho, cree un recurso de **Language** en la suscripción de Azure.

1. En otra pestaña del explorador, abra Azure Portal en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a la suscripción de Azure.

1. Haga clic en el botón **&#65291;Crear un recurso** y busque *servicio de lenguaje*. Seleccione **Crear** un plan de **servicio de lenguaje**. Se le llevará a una página para **Seleccionar características adicionales**. Mantenga la selección predeterminada y haga clic en **Continuar para crear el recurso**. 

1. En la página **Crear lenguaje**, configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: Este de EE. UU.
    - **Nombre**: *escriba un nombre único*.
    - **Plan de tarifa**: *Gratis o S si Gratis no está disponible*
    - **Al marcar esta casilla, confirmo haber leído y comprendido todos los términos que aparecen a continuación**: *Seleccionado*.

1. Seleccione **Revisar y crear**, a continuación, **Crear**, y espere a que se complete la implementación.

## Configuración del recurso en Lenguaje de Azure AI Studio

1. En otra pestaña del explorador, abra **Language Studio** en [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true) e inicie sesión.

1. Cuando se le pida **Seleccionar un recurso de Azure**, realice las siguientes configuraciones:
    - **Directorio de Azure**: *Directorio predeterminado, el directorio que usa*
    - **Suscripción de Azure**: *Seleccione la suscripción que usa*
    - **Tipo de recurso**: idioma
    - **Nombre de recurso**: *seleccione el recurso de servicio de lenguaje que acaba de crear*

A continuación, seleccione **Done** (Listo).

> **Importante**: A partir de julio de 2023, los servicios de Azure AI abarcan todos los anteriormente conocidos como Applied AI Services y Azure Applied AI Services. Algunas interfaces de usuario siguen actualizando su referencia de `Cognitive Services` a `Azure AI services`. Los dos nombres hacen referencia al mismo tipo de recurso.

> **Nota**: Si ***no*** se le pide que elija un recurso Language, puede deberse a que tiene varios en la suscripción, en cuyo caso:
> 1. En la barra de la parte superior de la página, seleccione **Configuración (&#9881;)**. 
> 1. En la página **Configuración,** vea la pestaña **Recursos**.
> 1. Seleccione el recurso que acaba de crear y seleccione **Cambiar recurso**. Asegúrese de que la identidad administrada está **habilitada**.
> ![Habilite el recurso Language.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. En la parte superior de la página, selecciona **Language Studio** para volver a la página principal de Language Studio.

## Análisis de revisiones en Language Studio

1. En un explorador web, vaya a **Language Studio** en [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true).

1. En la página de aterrizaje de **Le damos la bienvenida a Language Studio**, seleccione la pestaña **Clasificar texto** y, a continuación, seleccione el icono **Analizar opiniones y mi opinión**.

1. En *Seleccione el idioma de texto*, seleccione **inglés**.

1. En *Seleccione el recurso de Azure*, seleccione el recurso.

1. En *Escriba su propio texto, cargue un archivo o use uno de nuestros textos de ejemplo*, copie y pegue la siguiente reseña:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Active la casilla para confirmar que la demostración incurrirá en uso y puede incurrir en costos y, a continuación, seleccione **Ejecutar**.

1. Revise el resultado. Tenga en cuenta que el *documento* se analiza para la opinión, así como cada *oración*. Seleccione **Oración 1** para mostrar el análisis de sentimiento de esa oración. 

Observe que hay una opinión general seguida de puntuaciones junto a tres categorías, *puntuación positiva*, *puntuación neutra*, *puntuación negativa*. En cada una de las categorías, se proporciona una puntuación entre 0 y 1. Estas puntuaciones de confianza indican la probabilidad de que el texto proporcionado corresponda a un determinado sentimiento. 

Vuelva a seleccionar **Oración 1** para cerrar.

1. Desplácese hacia arriba para seleccionar **Borrar cuadro de texto**y copie y pegue la siguiente reseña:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. Seleccione **Ejecutar**. Revise la salida y revise el nivel de opinión y confianza.

1. Seleccione **Borrar cuadro de texto** de nuevo y copie y pegue la siguiente reseña:

    >Muy ruidoso y las habitaciones son diminutas The Lombard Hotel, San Francisco, USA 5/9/2018 El hotel está situado en la calle Lombard, que es una calle de SEIS carriles muy transitada directamente desde el puente Golden Gate. Tráfico desde la mañana hasta altas horas de la noche, especialmente los fines de semana. El ruido no sería tan malo si las habitaciones estuvieran mejor aisladas, pero no lo están. Tuve que ponerme algodones en los oídos para poder dormir; estaba demasiado cansado para disfrutar de la ciudad al día siguiente. Las habitaciones son DIMINUTAS. Escogí la habitación porque tenía dos camas queen size, pero la habitación apenas tenía espacio para acomodarlas. Somos una familia de cuatro personas y nos sentimos muy apretados. Con todo esto, las habitaciones están limpias y han hecho un esfuerzo por actualizarlas. El hotel está en el distrito de Marina con muchos buenos lugares para comer, a poca distancia de Presidio. Puede ser un buen hotel para adultos jóvenes que se acuestan tarde y disponen de un buen presupuesto.

1. Seleccione **Ejecutar** y revise la opinión junto con el nivel de confianza. Examine el texto y compare el texto con el análisis de sentimiento que devolvió el servicio.

En este ejercicio ha usado Language Studio para crear un nuevo recurso Language o usar un recurso Language existente. Ha habilitado el recurso en Configuración antes de probar el servicio de minería de opiniones. Ha probado el servicio con tres fragmentos de texto.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abra **Azure Portal** en [https://portal.azure.com](https://portal.azure.com) y seleccione el grupo de recursos que contiene el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, a continuación, **Sí** para confirmar. A continuación, se elimina el recurso.

## Saber más

Para más información sobre lo que puede hacer con este servicio, consulte la [página del servicio Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
