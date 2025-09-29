---
lab:
  title: Análisis de imágenes en el Portal de la Fundición de IA de Azure
---

# Análisis de imágenes en el Portal de la Fundición de IA de Azure

**Visión de Azure AI** incluye numerosas funcionalidades para comprender el contexto y el contenido de imágenes y extraer información de las mismas. En este ejercicio, usarás Visión de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar imágenes mediante las experiencias integradas de probarlo. 

Supongamos que el minorista ficticio *Northwind Traders* decidió implementar una "tienda inteligente" en la que hay servicios de inteligencia artificial que supervisan la tienda para identificar a aquellos clientes que requieran asistencia y orientan a los empleados para ayudales. Gracias a Visión de Azure AI, las imágenes de las cámaras de la tienda se pueden analizar para proporcionar descripciones acertadas sobre lo que aparezca en ellas.

Este ejercicio dura aproximadamente **20** minutos.

## Descarga y extracción de archivos de imagen

1. Descargue **[image-analysis.zip](https://aka.ms/mslearn-images-for-analysis)** de `https://aka.ms/mslearn-images-for-analysis`.
1. Extraiga el archivo .zip descargado en una carpeta del equipo.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Recorte de pantalla de la página principal del Portal de la Fundición de IA de Azure.](./media/ai-foundry-portal.png)

1. Desplácese hasta la parte inferior de la página y seleccione el icono **Explorar los servicios de Azure AI**.

    ![Recorte de pantalla del icono "Explorar los servicios de Azure AI".](./media/ai-services.png)

1. En la página "Servicios de Azure AI", seleccione el icono **Visión y documento**.

    ![Recorte de pantalla del icono "Vision y documento".](./media/vision-tile.png)

1. En la página **Visión y documento**, examine la pestaña **Imagen** y seleccione el icono **Subtítulación de imágenes**.

    ![Recorte de pantalla del icono de subtitulación de imágenes.](./media/image-captioning-tile.png)

1. En el panel **Agregar subtítulos a imágenes**, use el botón **Seleccionar un centro** para **crear un centro** con la siguiente configuración:
    - **Nombre del centro**: *escriba un nombre válido para el centro.*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Ubicación**: *seleccione una de las siguientes ubicaciones*/*:
        - Este de EE. UU.
        - Centro de Francia
        - Centro de Corea del Sur
        - Oeste de Europa
        - Oeste de EE. UU.
    - **Conexión de los servicios de Azure AI**: *Creación de un nuevo recurso de Servicios de Azure AI con un nombre válido*
    - **Conectar Búsqueda de Azure AI**: omite la conexión

    \**En el momento de redactar este documento, Visión de Azure AI se admite en centros de conectividad de estas regiones*.

1. Cuando se cree el centro, se le pedirá que cree un proyecto. Escriba un nombre de proyecto adecuado y seleccione **Crear proyecto**.

## Generación de títulos de imágenes

Vamos a usar la funcionalidad de subtitulación de imágenes de Visión de Azure AI para analizar las imágenes tomadas por una cámara en la tienda de *Northwind Traders*. Los títulos de imágenes están disponibles a través de las características **Título** y **Títulos densos**.

1. En el panel de tareas de la izquierda, seleccione **Servicios de AI**.

    *Ahora debe repetir los pasos que usó anteriormente para volver a la interfaz de subtitulación de imágenes y usar el nuevo proyecto basado en el centro.*

1. En la página **Servicios de AI**, seleccione el icono **Visión y documento**. A continuación, en la página **Visión y documento**, en la pestaña **Imagen**, seleccione el icono **Subtítulos de imágenes**.

1. En la página **Agregar subtítulos a imágenes**, en el menú de selección *Servicios conectados de Azure AI*, asegúrese de que se haya seleccionado el recurso de servicios de Azure AI que creó en el centro.

1. Use el vínculo **Examinar un archivo** para cargar la imagen **store-camera-1.jpg** de los archivos que descargó y extrajo anteriormente.

1. Observe la descripción generada, visible en el panel **Atributos detectados** de la derecha de la imagen.

    ![Recorte de pantalla de la página "Agregar subtítulos a imágenes" con una imagen analizada.](./media/image-captioning.png)

    La funcionalidad **Título** proporciona una sola frase en inglés legible que describe el contenido de la imagen.

1. A continuación, use la misma imagen para poner **Títulos densos**. Vuelva a la página **Visión y documento**; para ello, seleccione la flecha **&larr;** *atrás* en la parte superior de la página y, a continuación, en la página **Visión y documento**, en la pestaña **Imagen**, seleccione el icono **Subtítulos densos**.

    La característica **Títulos densos** difiere de la funcionalidad **Títulos**, en la que se proporcionan varios títulos legibles para una imagen: uno que describe el contenido de la imagen y otros, en los que cada uno cubre los objetos esenciales detectados en la imagen. Cada objeto detectado incluye un cuadro de límite, que define las coordenadas de píxel dentro de la imagen asociada al objeto.

1. Vuelva a cargar la imagen **store-camera-1.jpg** y vea los resultados de los subtítulos densos.

    ![Recorte de pantalla de los resultados de subtítulos densos.](./media/dense-captioning.png)

    Mantenga el puntero sobre cualquiera de los subtítulos de la lista **Atributos detectados** y observe que se genera un subtítulo para cada objeto detectado en la imagen.

## Etiquetado de imágenes 

La siguiente característica que probará es la funcionalidad *Extraer etiquetas*. La extracción de etiquetas se basa en miles de objetos reconocibles, incluyendo seres vivos, paisajes y acciones.

1. Vuelva a la página **Visión + documento** seleccionando la flecha **&larr;** *atrás* en la parte superior de la página. A continuación, en la página **Visión y documento**, en la pestaña **Imagen**, seleccione el icono **Extracción de etiquetas comunes**.
1. Cargue el archivo **store-camera-2.jpg** de la carpeta que extrajo anteriormente.
1. Revise la lista de etiquetas extraídas de la imagen y la puntuación de confianza de cada una en el panel de atributos detectados. Aquí, la puntuación de confianza es la probabilidad de que el texto del atributo detectado describa lo que realmente está en la imagen. Observe en la lista de etiquetas que incluya no solo objetos, sino acciones, como *comprando*, *vendiendo* y *de pie*.

    ![Captura de pantalla del panel Detectar atributos en Studio de Visión con puntuaciones de texto y confianza que se muestran junto a la imagen original.](./media/analyze-images-vision/detect-attributes.png)

## Detección de objetos

En esta tarea, se usa la característica **Detección de objetos** de Análisis de imágenes. Detección de objetos detecta y extrae cuadros de límite basados en miles de objetos reconocibles y seres vivos.

1. Vuelva a la página **Visión + documento** seleccionando la flecha **&larr;** *atrás* en la parte superior de la página. A continuación, en la pestaña **Imagen**, seleccione el icono **Detección de objetos comunes**.

1. Cargue el archivo **store-camera-3.jpg**.

1. En el cuadro **Atributos detectados**, observe la lista de objetos detectados y sus puntuaciones de confianza.

    ![Recorte de pantalla de los resultados de subtítulos densos.](./media/object-detection.png)

1. Pruebe a detectar los objetos de la imagen **store-camera-4.jpg**.

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre [Azure Portal]( https://portal.azure.com) y selecciona el grupo de recursos que contenga el recurso que creaste. 
1. Seleccione **Eliminar grupo de recursos** y **escriba el nombre del grupo de recursos** para confirmar. El grupo de recursos se elimina.

## Saber más

Para obtener más información sobre lo que es posible hacer con este servicio, consulte la [página Visión de Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
