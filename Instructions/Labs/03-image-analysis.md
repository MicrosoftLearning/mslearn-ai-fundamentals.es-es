---
lab:
  title: Análisis de imágenes en el Portal de la Fundición de IA de Azure
---

# Análisis de imágenes en el Portal de la Fundición de IA de Azure

**Visión de Azure AI** incluye numerosas funcionalidades para comprender el contexto y el contenido de imágenes y extraer información de las mismas. En este ejercicio, usarás Visión de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para analizar imágenes mediante las experiencias integradas de probarlo. 

Supongamos que el minorista ficticio *Northwind Traders* decidió implementar una "tienda inteligente" en la que hay servicios de inteligencia artificial que supervisan la tienda para identificar a aquellos clientes que requieran asistencia y orientan a los empleados para ayudales. Gracias a Visión de Azure AI, las imágenes de las cámaras de la tienda se pueden analizar para proporcionar descripciones acertadas sobre lo que aparezca en ellas.

## Creación de un proyecto en el portal de Azure AI Foundry

Comencemos creando un proyecto de Fundición de IA de Azure.

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un agente seleccionada.](./media/azure-ai-foundry-home-page.png)

1. En la página principal, selecciona **+ Crear un agente**.

1. En el asistente para **Crear un agente**, escribe un nombre válido para el proyecto. 

1. Selecciona **Opciones avanzadas** y especifica los siguientes valores:
    - **Recurso de Fundición de IA de Azure**: *mantén el nombre predeterminado*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Región**: selecciona una de las siguientes ubicaciones:
        * Este de EE. UU.
        * Centro de Francia
        * Centro de Corea del Sur
        * Oeste de Europa
        * Oeste de EE. UU.

1. Selecciona **Crear** y revisa la configuración. Espera hasta que se complete el proceso de configuración.

    >**Nota**: si recibes un error de permisos, selecciona el botón **Corregirlo** para agregar los permisos adecuados para continuar.

1. Cuando se crea el proyecto, se te mostrará de forma predeterminada el área de juegos Agents en el portal de la Fundición de IA de Azure, que debe tener un aspecto similar a la siguiente imagen:

    ![Captura de pantalla de los detalles de un proyecto de Azure AI en el Portal de la Fundición de IA de Azure.](./media/ai-foundry-project-2.png)
 
1. En una nueva ventana del explorador, abre la [página de exploración de servicios de Azure AI](https://ai.azure.com/explore/aiservices).

1. En la página *Servicios de IA*, selecciona el icono *Visión y documento* para probar las funcionalidades de Visión y documento de Azure AI.

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

1.  Abre [Azure Portal]( https://portal.azure.com) y selecciona el grupo de recursos que contenga el recurso que creaste. 
1.  Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Para obtener más información sobre lo que es posible hacer con este servicio, consulte la [página Visión de Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
