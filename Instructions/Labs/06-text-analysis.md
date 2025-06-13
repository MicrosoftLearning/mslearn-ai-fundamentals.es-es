---
lab:
  title: Análisis de texto en el Portal de la Fundición de IA de Azure
---

# Análisis de texto en el Portal de la Fundición de IA de Azure

El procesamiento de lenguaje natural (NLP) es una rama de inteligencia artificial que se ocupa del lenguaje escrito y hablado. Puede usar NLP para crear soluciones que extraigan el significado semántico de instrucciones habladas o escritas, o que formulen respuestas adecuadas en lenguaje natural.

El servicio Lenguaje de Azure AI incluye Text Analytics, con funcionalidades como el reconocimiento de entidades, la extracción de frases clave, el resumen y el análisis de sentimiento. Por ejemplo, supongamos que el agente de viajes ficticio Margie's Travel anima a los clientes a enviar opiniones de sus estancias en hoteles. Puedes usar el servicio Lenguaje para extraer entidades con nombre, identificar frases clave, resumir texto, etc.

En este ejercicio, usarás Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar reseñas de hoteles. 

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicies sesión. 

1. En el explorador, ve a `https://ai.azure.com/managementCenter/allResources` y selecciona **Crear**. A continuación, elige la opción para crear un *nuevo recurso de Fundición de IA de Azure*.

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

    Espera a que se cree el proyecto y el centro.

1. Cuando se cree el proyecto, se te dirigirá a una página *Información general* de los detalles del proyecto.

1. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**.

1. En la página *Áreas de juegos*, selecciona el icono de **Área de juegos de lenguaje** para probar algunas funcionalidades de Lenguaje de Azure AI.

## Extracción de entidades con nombre con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure

Las *entidades con nombre* son palabras que describen personas, lugares y objetos con nombres propios. Vamos a usar la funcionalidad de extracción de entidades con nombre de Lenguaje de Azure AI para identificar tipos de información en una reseña.

1. En el área de juegos de lenguaje, selecciona **Extraer información**. A continuación, selecciona el icono **Extraer entidades con nombre**. 

1. En *Ejemplo*, copia y pega la siguiente revisión:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selecciona **Ejecutar**. Revise el resultado. Observa en la sección *Detalles* cómo las entidades extraídas incluyen información adicional como puntuaciones de confianza y tipo. La puntuación de confianza representa la probabilidad de que el tipo identificado pertenezca realmente a esa categoría.

## Extracción de frases clave con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure

Las *frases clave* son los fragmentos de información más importantes del texto. Vamos a usar la funcionalidad de extracción de frases clave de Lenguaje de Azure AI para extraer información importante de una reseña.

1. En el área de juegos de lenguaje, selecciona **Extraer información**. Luego selecciona el icono **Extraer frases clave**. 

1. En *Ejemplo*, copia y pega la siguiente revisión:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selecciona **Ejecutar**. Revise el resultado. Observe las diferentes frases extraídas en la sección *Detalles*. Estas frases deben contribuir más al significado del texto.

## Resumen del texto con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure
 
1. Echemos un vistazo a las funcionalidades de resumen de Lenguaje de Azure AI. En el área de juegos de idioma, selecciona *Resumir información* y, a continuación, selecciona el icono **Resumir texto**.

1. En *Ejemplo*, copia y pega la siguiente revisión:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selecciona **Ejecutar**. Revise el resultado. Observa que el *resumen extractivo* en *Detalles* proporciona puntuaciones de clasificación para las oraciones más destacadas.   

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre **Azure Portal** en [https://portal.azure.com](https://portal.azure.com) y selecciona el grupo de recursos que contiene los recursos que creaste.

1. Selecciona los recursos y selecciona **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminarán los recursos.

## Saber más

Para más información sobre lo que puede hacer con este servicio, consulte la [página del servicio Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
