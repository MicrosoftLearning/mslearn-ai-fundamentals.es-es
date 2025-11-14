---
lab:
  title: Análisis de texto en el Portal de la Fundición de IA de Azure
---

# Análisis de texto en el Portal de la Fundición de IA de Azure

Lenguaje de Azure AI incluye Text Analytics, con funcionalidades como el reconocimiento de entidades, la extracción de frases clave, el resumen y el análisis de sentimiento. Por ejemplo, supongamos que el agente de viajes ficticio Margie's Travel anima a los clientes a enviar opiniones de sus estancias en hoteles. Puedes usar el servicio Lenguaje para extraer entidades con nombre, identificar frases clave, resumir texto, etc.

En este ejercicio, usarás Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar reseñas de hoteles. 

Este ejercicio dura aproximadamente **20** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el[Portal de la Fundición de IA de Azure](https://ai.azure.com) en`https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de**Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel**Ayuda** si está abierto):

    ![Recorte de pantalla de la página principal del Portal de la Fundición de IA de Azure.](./media/ai-foundry-portal.png)

1. Desplácese hasta la parte inferior de la página y seleccione el icono**Explorar los servicios de Azure AI**.

    ![Recorte de pantalla del icono "Explorar los servicios de Azure AI".](./media/ai-services.png)

1. En la página "Servicios de Azure AI", seleccione el icono**Idioma y traductor**.

    ![Recorte de pantalla del icono Idioma y traductor.](./media/language-tile.png)

1. En la página**Idioma y traductor**, seleccione**Probar el área de juegos de idioma**. A continuación, cuando se le solicite, cree un proyecto con la siguiente configuración:
    - **Nombre del proyecto**:*escriba un nombre válido para el proyecto.*
    - **Configuración avanzada**:
        - **Suscripción**:*suscripción a Azure*
        - **Grupo de recursos**:*crea o selecciona un grupo de recursos*
        - **Región**:*seleccione cualquier región**recomendada de Fundición de IA***
        - **Fundición de IA o Azure OpenAI**:*cree un nuevo recurso de Fundición de IA de Azure con un nombre válido*

1. Seleccione**Crear**. Espera a que se cree el proyecto. Esto puede tardar unos minutos.

1. Cuando se cree el proyecto, se le llevará a un área de juegos de**Idioma** (si no es así, en el panel de tareas de la izquierda, seleccione**Áreas de juegos** y abra el área de juegos de Idioma desde allí).

    El área de juegos de Idioma es una interfaz de usuario que le permite probar algunas funcionalidades de Lenguaje de Azure AI.  

## Uso de Lenguaje de Azure AI para analizar texto

Lenguaje de Azure AI ofrece una amplia variedad de funcionalidades de análisis de texto.

### Extracción de entidades con nombre con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure

Las*entidades con nombre* son palabras que describen personas, lugares y objetos con nombres propios. Vamos a usar la funcionalidad de extracción de entidades con nombre de Lenguaje de Azure AI para identificar tipos de información en una reseña.

1. En el área de juegos de lenguaje, selecciona**Extraer información**. A continuación, selecciona el icono**Extraer entidades con nombre**. 

1. En*Ejemplo*, escriba la siguiente reseña:

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Selecciona**Ejecutar**. Revise el resultado.

    ![Recorte de pantalla de la interfaz "Extraer entidades con nombre" en el área de juegos de Idioma.](./media/entity-extraction.png)

    Observa en la sección*Detalles* cómo las entidades extraídas incluyen información adicional como puntuaciones de confianza y tipo. La puntuación de confianza representa la probabilidad de que el tipo identificado pertenezca realmente a esa categoría.

### Extracción de frases clave con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure

Las*frases clave* son los fragmentos de información más importantes del texto. Vamos a usar la funcionalidad de extracción de frases clave de Lenguaje de Azure AI para extraer información importante de una reseña.

1. En el área de juegos de lenguaje, selecciona**Extraer información**. Luego selecciona el icono**Extraer frases clave**. 

1. En*Ejemplo*, escriba la siguiente reseña:

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Selecciona**Ejecutar**. Revise el resultado.

    ![Recorte de pantalla de la interfaz "Extraer frases clave" en el área de juegos de Idioma.](./media/key-phrases.png)

    Observe las diferentes frases extraídas en la sección*Detalles*. Estas frases deben contribuir más al significado del texto.

### Resumen del texto con Lenguaje de Azure AI en el Portal de la Fundición de IA de Azure
 
Echemos un vistazo a las funcionalidades de resumen de Lenguaje de Azure AI.

1. En el área de juegos de idioma, selecciona**Resumir información** y, a continuación, selecciona el icono**Resumir texto**.

1. En*Ejemplo*, escriba la siguiente reseña:
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Selecciona**Ejecutar**. Revise el resultado.

    ![Recorte de pantalla de la interfaz de resumen de texto en el área de juegos de Idioma.](./media/summarize-text.png)

    Observa que el*resumen extractivo* en*Detalles* proporciona puntuaciones de clasificación para las oraciones más destacadas.

### Análisis de sentimiento en el texto

El análisis de sentimiento es una tarea común al analizar texto como reseñas de hoteles.

1. En el área de juegos de Idioma, seleccione**Clasificar texto**. A continuación, seleccione el icono**Analizar opinión**.

1. En*Ejemplo*, escriba la siguiente reseña:
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. Selecciona**Ejecutar**. Revise el resultado.

    ![Recorte de pantalla de la interfaz de análisis sentimiento en el área de juegos de Idioma.](./media/sentiment-analysis.png)

    Observe que el análisis genera una puntuación general de opinión y puntuaciones individuales para cada oración.

## Detección del idioma y traducción de texto

Lenguaje de Azure AI permite detectar el idioma en el que está escrito el texto. Además, Traductor de Azure AI permite traducir fácilmente texto de un idioma a otro.

### Detectar idioma

Comencemos por detectar el idioma en el que se escribe una reseña.

1. En el panel**Clasificar texto**, seleccione el icono**Detectar idioma**.

1. En*Ejemplo*, escriba la siguiente reseña:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Selecciona**Ejecutar**. Revise el resultado.

    ![Recorte de pantalla de la interfaz "Detectar idioma" en el área de juegos de Idioma.](./media/detect-language.png)

    Observe el idioma detectado es el francés. 

### Traducción de texto

Ahora vamos a traducir la reseña en francés al inglés.

1. En la parte superior de la página, use el vínculo**&larr;** (atrás) junto al título de la página del**área de juegos de Idioma** para ver todas las áreas de juego disponibles.
1. En la lista de áreas de juegos, abra el**área de juegos de Traductor**.
1. En el área de juegos de Traductor, seleccione**Traducción de texto**.
1. En el panel**Configurar**, seleccione las siguientes opciones de idioma:
    - **Traducir de**: Francés
    - **Traducir a**: Inglés
1. En*Ejemplo*, escriba la reseña en francés:
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Seleccione**Traducir**. Revise el resultado.

    ![Recorte de pantalla de la interfaz de traducción de texto en el área de juegos de Traductor.](./media/text-translation.png)

    Observe que la reseña en francés se traduce al inglés.

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre**Azure Portal** en[https://portal.azure.com](https://portal.azure.com) y selecciona el grupo de recursos que contiene los recursos que creaste.
1. Seleccione**Eliminar grupo de recursos** y**escriba el nombre del grupo de recursos** para confirmar. El grupo de recursos se elimina.

## Saber más

Para más información sobre lo que puede hacer con este servicio, consulte la[página del servicio Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
