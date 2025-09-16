---
lab:
  title: Análisis de imágenes en el Portal de la Fundición de IA de Azure
---

# Análisis de imágenes en el Portal de la Fundición de IA de Azure

**Visión de Azure AI** incluye numerosas funcionalidades para comprender el contexto y el contenido de imágenes y extraer información de las mismas. En este ejercicio, usarás Visión de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar imágenes mediante las experiencias integradas de probarlo. 

Supongamos que el minorista ficticio *Northwind Traders* decidió implementar una "tienda inteligente" en la que hay servicios de inteligencia artificial que supervisan la tienda para identificar a aquellos clientes que requieran asistencia y orientan a los empleados para ayudales. Gracias a Visión de Azure AI, las imágenes de las cámaras de la tienda se pueden analizar para proporcionar descripciones acertadas sobre lo que aparezca en ellas.

Este ejercicio dura aproximadamente **20** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicies sesión. 

1. En el explorador, accede a `https://ai.azure.com/managementCenter/allResources` y selecciona **Crear nuevo**. A continuación, elija la opción para crear un **recurso de Centro de IA**.

1. En el asistente para *crear un proyecto*, escribe un nombre válido y si se te sugiere un centro existente, selecciona la opción para crear uno *nuevo*. 

1. Expande *Opciones avanzadas* para especificar los siguientes valores para tu proyecto:
    - **Suscripción** : su suscripción a Azure.
    - **Grupo de recursos**: crea o selecciona un grupo de recursos
    - **Región**: selecciona una de las siguientes ubicaciones:
        * Este de EE. UU.
        * Centro de Francia
        * Centro de Corea del Sur
        * Oeste de Europa
        * Oeste de EE. UU.

    Seleccione **Crear**. Espera a que se cree el proyecto y el centro. Esto puede tardar unos minutos.

1. Cuando se cree el proyecto, se te llevará a la página *Información general* de los detalles del proyecto. Selecciona **Servicios de IA** en el menú de la izquierda. 

    >*Nota*: Expanda el menú para leer su contenido haciendo clic en el icono "expandir" de arriba. 

1. En la página *Servicios de IA*, selecciona el icono *Visión y documento* para probar las funcionalidades de Visión y documento de Azure AI.

    ![Captura de pantalla del icono Vision + Documento de Fundición de IA de Azure.](./media/vision-document-tile.png)

## Generación de títulos de imágenes

Vamos a usar la funcionalidad de subtitulación de imágenes de Visión de Azure AI para analizar las imágenes tomadas por una cámara en la tienda de *Northwind Traders*. Los títulos de imágenes están disponibles a través de las características **Título** y **Títulos densos**.

1. En la página *Visión y documento*, desplázate hacia abajo y selecciona **Imagen** en *Ver todas las demás funcionalidades de visión*. A continuación, selecciona el icono **Subtitulación de imágenes**.

    ![Captura de pantalla del icono de subtitulación de imágenes en la sección de imagen de la página Visión y documento.](./media/vision-image-captioning-tile.png)

1. En la página **Agregar leyendas a imágenes**, en el menú de selección *Servicios de Azure AI conectados*, observe que se ha seleccionado el recurso de *Servicios de Azure AI* que creó. No deberías tener que realizar ningún cambio. 

    >*Nota*: Si no personalizó una ubicación de recurso válida durante la creación del recurso, es posible que se le pida que cree un nuevo recurso de los servicios de Azure AI que se encuentre en una región válida. Tendrá que crear el nuevo recurso para continuar con el laboratorio.  

1. Descargue **image-analysis.zip** abriendo la dirección URL `https://aka.ms/mslearn-images-for-analysis` en una nueva pestaña del explorador. Al usar la dirección URL se debe descargar automáticamente una carpeta en el equipo. 

1. Vaya a la carpeta *Descargas* del equipo y, a continuación, identifique la carpeta descargada. Haga clic con el botón derecho en la carpeta descargada. Seleccione *Extraer todo...*. A continuación, seleccione *Extraer* para descomprimir su contenido. La carpeta descomprimida aparecerá en la pantalla.  

1. En la carpeta descomprimida, busque el archivo denominado **store-camera-1.jpg**; que contiene la siguiente imagen:

    ![Imagen de un elemento primario que usa la cámara de un teléfono móvil para capturar una imagen de un elemento secundario en una tienda.](./media/analyze-images-vision/store-camera-1.jpg)

1. Cargue la imagen **store-camera-1.jpg** seleccionando *Examinar un archivo*. Puede encontrar la imagen en la carpeta *Descargas* del sistema de archivos.

1. Observe la descripción generada, visible en el panel **Atributos detectados** de la derecha de la imagen.

    La funcionalidad **Título** proporciona una sola frase en inglés legible que describe el contenido de la imagen.

1. A continuación, use la misma imagen para poner **Títulos densos**. Vuelve a la página **Visión + documento** seleccionando la flecha *atrás* en la parte superior de la página. En la página *Visión y documento*, selecciona la pestaña **Imagen** y, a continuación, selecciona el icono **Subtitulación densa**.

    La característica **Títulos densos** difiere de la funcionalidad **Títulos**, en la que se proporcionan varios títulos legibles para una imagen: uno que describe el contenido de la imagen y otros, en los que cada uno cubre los objetos esenciales detectados en la imagen. Cada objeto detectado incluye un cuadro de límite, que define las coordenadas de píxel dentro de la imagen asociada al objeto.

1. Mantenga el puntero sobre uno de los títulos de la lista de atributos **Detectados** y observe lo que sucede dentro de la imagen.

    ![Se muestran la imagen y sus títulos.](./media/analyze-images-vision/dense-captioning.png)

    Mueva el cursor del mouse sobre los otros títulos de la lista y observe cómo cambia el rectángulo de selección de la imagen para resaltar la parte de la imagen usada para generar el título.

## Etiquetado de imágenes 

La siguiente característica que probará es la funcionalidad *Extraer etiquetas*. La extracción de etiquetas se basa en miles de objetos reconocibles, incluyendo seres vivos, paisajes y acciones.

1. Vuelve a la página *Visión + Documento* de Fundición de IA de Azure, selecciona la pestaña **Imagen** y selecciona el icono **Extracción de etiquetas comunes**.

1. Abra la carpeta que contenga las imágenes que descargó y busque el archivo denominado **store-image-2.jpg**, que tiene el siguiente aspecto:

    ![Imagen de una persona con una cesta de la compra en un supermercado](./media/analyze-images-vision/store-camera-2.jpg)

1. Cargue el archivo **store-camera-2.jpg**.

1. Revise la lista de etiquetas extraídas de la imagen y la puntuación de confianza de cada una en el panel de atributos detectados. Aquí, la puntuación de confianza es la probabilidad de que el texto del atributo detectado describa lo que realmente está en la imagen. Observe en la lista de etiquetas que incluya no solo objetos, sino acciones, como *comprando*, *vendiendo* y *de pie*.

    ![Captura de pantalla del panel Detectar atributos en Studio de Visión con puntuaciones de texto y confianza que se muestran junto a la imagen original.](./media/analyze-images-vision/detect-attributes.png)

## Detección de objetos

En esta tarea, se usa la característica **Detección de objetos** de Análisis de imágenes. Detección de objetos detecta y extrae cuadros de límite basados en miles de objetos reconocibles y seres vivos.

1. Vuelve a la página *Visión + Documento* de Fundición de IA de Azure, selecciona la pestaña **Imagen** y selecciona el icono **Detección de objetos comunes**.

1. Abra la carpeta que contenga las imágenes que descargó y busque el archivo denominado **store-camera-3.jpg**, que tiene el siguiente aspecto:

    ![Imagen de una persona con un carro de la compra](./media/analyze-images-vision/store-camera-3.jpg)

1. Cargue el archivo **store-camera-3.jpg**.

1. En el cuadro **Atributos detectados**, observe la lista de objetos detectados y sus puntuaciones de confianza.

1. Mantenga el cursor del mouse sobre los objetos de la lista **Atributos detectados** para resaltar el cuadro de límite del objeto en la imagen.

1. Mueva el control deslizante **Valor de umbral** hasta que se muestre un valor de 70 a la derecha del control deslizante. Observe lo que sucede con los objetos de la lista. El control deslizante del umbral especifica que solo se deberían mostrar los objetos identificados con una puntuación de confianza o una probabilidad superior al umbral.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abre [Azure Portal]( https://portal.azure.com) y selecciona el grupo de recursos que contenga el recurso que creaste. 
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Para obtener más información sobre lo que es posible hacer con este servicio, consulte la [página Visión de Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
