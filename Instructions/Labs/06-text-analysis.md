---
lab:
  title: Análisis de texto en el Portal de la Fundición de IA de Azure
---

# Análisis de texto en el Portal de la Fundición de IA de Azure

El procesamiento de lenguaje natural (NLP) es una rama de inteligencia artificial que se ocupa del lenguaje escrito y hablado. Puede usar NLP para crear soluciones que extraigan el significado semántico de instrucciones habladas o escritas, o que formulen respuestas adecuadas en lenguaje natural.

El servicio Lenguaje de Azure AI incluye Text Analytics, con funcionalidades como el reconocimiento de entidades, la extracción de frases clave, el resumen y el análisis de sentimiento. Por ejemplo, supongamos que el agente de viajes ficticio Margie's Travel anima a los clientes a enviar opiniones de sus estancias en hoteles. Puedes usar el servicio Lenguaje para extraer entidades con nombre, identificar frases clave, resumir texto, etc.

En este ejercicio, usarás Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar reseñas de hoteles. 

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
 
    ![Captura de pantalla del menú de la izquierda en la pantalla del proyecto con áreas de juegos seleccionadas](./media/azure-ai-foundry-playgrounds.png)  

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
