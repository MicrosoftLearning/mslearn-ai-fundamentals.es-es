---
lab:
  title: Análisis de imágenes en el Portal de la Fundición de IA de Azure
---

# Análisis de imágenes en el Portal de la Fundición de IA de Azure

**Visión de Azure AI** incluye numerosas funcionalidades para comprender el contexto y el contenido de imágenes y extraer información de las mismas. En este ejercicio, usarás Visión de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar imágenes mediante las experiencias integradas de probarlo. 

Supongamos que el minorista ficticio *Northwind Traders* decidió implementar una "tienda inteligente" en la que hay servicios de inteligencia artificial que supervisan la tienda para identificar a aquellos clientes que requieran asistencia y orientan a los empleados para ayudales. Gracias a Visión de Azure AI, las imágenes de las cámaras de la tienda se pueden analizar para proporcionar descripciones acertadas sobre lo que aparezca en ellas.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En una pestaña del explorador, ve a [Fundición de IA de Azure](https://ai.azure.com?azure-portal=true).

1. Inicie sesión con su cuenta. 

1. En la página principal del Portal de la Fundición de IA de Azure, selecciona **Crear un proyecto**. En Fundición de IA de Azure, los proyectos son contenedores que te ayudan a organizar el trabajo.  

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un proyecto seleccionada](./media/azure-ai-foundry-home-page.png)

1. En el panel *Crear un proyecto*, verás un nombre de proyecto generado, que puedes mantener tal cual. Dependiendo de si has creado un centro en el pasado, verás una lista de *nuevos* recursos de Azure que se van a crear o una lista desplegable de centros existentes. Si ves la lista desplegable de centros existentes, selecciona *Crear nuevo centro*, crea un nombre único para el centro y selecciona *Siguiente*.  
 
    ![Captura de pantalla del panel para crear un proyecto con nombres generados automáticamente para el centro y el proyecto](./media/azure-ai-foundry-create-project.png)

    > **Importante**: Necesitarás un recurso de Servicios de Azure AI aprovisionado en una ubicación específica para completar el resto del laboratorio.

1. En el mismo panel *Crear un proyecto*, selecciona **Personalizar** y una de las siguientes **ubicaciones**: *Este de EE. UU., Centro de Francia, Centro de Corea del Sur, Oeste de Europa u Oeste de EE. UU.* para completar el resto del laboratorio. Selecciona **Siguiente** y después **Crear**. 

1. Toma nota de los recursos que se crean: 
    - Servicios de Azure AI
    - Centro de Azure AI
    - Proyecto de Azure AI
    - Cuenta de almacenamiento
    - Key vault
    - Resource group  
 
1. Una vez creados los recursos, se mostrará la página *Información general* de tu proyecto. En el menú izquierdo de la pantalla, selecciona **Servicios de IA**.
 
    ![Captura de pantalla del menú izquierdo en la pantalla del proyecto con Servicios de IA seleccionado](./media/azure-ai-foundry-ai-services.png)  

1. En la página *Servicios de IA*, selecciona el icono *Visión y documento* para probar las funcionalidades de Visión y documento de Azure AI.

    ![Captura de pantalla del icono Visión y documento seleccionado en la página Servicios de IA.](./media/vision-document-tile.png)

## Generación de títulos de imágenes

Vamos a usar la funcionalidad de subtitulación de imágenes de Visión de Azure AI para analizar las imágenes tomadas por una cámara en la tienda de *Northwind Traders*. Los títulos de imágenes están disponibles a través de las características **Título** y **Títulos densos**.

1. En la página *Visión y documento*, desplázate hacia abajo y selecciona **Imagen** en *Ver todas las demás funcionalidades de visión*. A continuación, selecciona el icono **Subtitulación de imágenes**.

    ![Captura de pantalla del icono de subtitulación de imágenes en la sección de imagen de la página Visión y documento.](./media/vision-image-captioning-tile.png)

1. En la página **Agregar subtítulos a imágenes**, revisa el recurso al que estás conectado, que aparece en el subtítulo **Probarlo**. No deberías tener que realizar ningún cambio. (*Nota*: si no personalizaste una ubicación de recurso válida durante la creación de recursos, es posible que se te pida que crees un nuevo recurso de Servicios de Azure AI que se encuentre en una región válida. Tendrás que crear el nuevo recurso para continuar con el laboratorio).  

1. Seleccione [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) para descargar **image-analysis.zip**. Abra la carpeta en el equipo y busque el archivo denominado **store-camera-1.jpg**, que contiene la siguiente imagen:

    ![Imagen de un elemento primario que usa la cámara de un teléfono móvil para capturar una imagen de un elemento secundario en una tienda.](./media/analyze-images-vision/store-camera-1.jpg)

1. Cargue la imagen **store-camera-1.jpg** arrastrándola al cuadro **Arrastrar y colocar archivos aquí** o navegando hasta el en el sistema de archivos.

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

2. En **Elija el modelo que desee probar**, deje seleccionado **Producto precompilado frente a modelo de rango**. En **Elija el idioma**, seleccione **Inglés** o un idioma de su preferencia.

3. Abra la carpeta que contenga las imágenes que descargó y busque el archivo denominado **store-image-2.jpg**, que tiene el siguiente aspecto:

    ![Imagen de una persona con una cesta de la compra en un supermercado](./media/analyze-images-vision/store-camera-2.jpg)

4. Cargue el archivo **store-camera-2.jpg**.

5. Revise la lista de etiquetas extraídas de la imagen y la puntuación de confianza de cada una en el panel de atributos detectados. Aquí, la puntuación de confianza es la probabilidad de que el texto del atributo detectado describa lo que realmente está en la imagen. Observe en la lista de etiquetas que incluya no solo objetos, sino acciones, como *comprando*, *vendiendo* y *de pie*.

    ![Captura de pantalla del panel Detectar atributos en Studio de Visión con puntuaciones de texto y confianza que se muestran junto a la imagen original.](./media/analyze-images-vision/detect-attributes.png)

## Detección de objetos

En esta tarea, se usa la característica **Detección de objetos** de Análisis de imágenes. Detección de objetos detecta y extrae cuadros de límite basados en miles de objetos reconocibles y seres vivos.

1. Vuelve a la página *Visión + Documento* de Fundición de IA de Azure, selecciona la pestaña **Imagen** y selecciona el icono **Detección de objetos comunes**.

1. En **Elija el modelo que desee probar**, deje seleccionado **Producto precompilado frente a modelo de rango**.

1. Abra la carpeta que contenga las imágenes que descargó y busque el archivo denominado **store-camera-3.jpg**, que tiene el siguiente aspecto:

    ![Imagen de una persona con un carro de la compra](./media/analyze-images-vision/store-camera-3.jpg)

1. Cargue el archivo **store-camera-3.jpg**.

1. En el cuadro **Atributos detectados**, observe la lista de objetos detectados y sus puntuaciones de confianza.

1. Mantenga el cursor del mouse sobre los objetos de la lista **Atributos detectados** para resaltar el cuadro de límite del objeto en la imagen.

1. Mueva el control deslizante **Valor de umbral** hasta que se muestre un valor de 70 a la derecha del control deslizante. Observe lo que sucede con los objetos de la lista. El control deslizante del umbral especifica que solo se deberían mostrar los objetos identificados con una puntuación de confianza o una probabilidad superior al umbral.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1.  Abre [Azure Portal]( https://portal.azure.com) y selecciona el grupo de recursos que contenga el recurso que creaste. 
1.  Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Para obtener más información sobre lo que es posible hacer con este servicio, consulte la [página Visión de Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
