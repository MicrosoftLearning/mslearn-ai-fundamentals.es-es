---
lab:
  title: Lectura de texto en Estudio de Visión
---

# Lectura de texto en Estudio de Visión

En este ejercicio, usará el servicio Azure AI para explorar las funcionalidades de reconocimiento óptico de caracteres de Visión de Azure AI. Usará Vision Studio para experimentar con la extracción de texto de imágenes, sin tener que escribir ningún código.

Uno de los desafíos más habituales de Computer Vision es detectar e interpretar el texto incrustado en una imagen. Esto se conoce como reconocimiento óptico de caracteres (OCR). En este ejercicio, usará un recurso de servicios de Azure AI que incluye los servicios de Visión de Azure AI. Después, usará Vision Studio para probar el OCR con diferentes tipos de imágenes.

## Creación de un grupo de recursos de *servicios de Azure AI*

Es posible usar las funcionalidades de OCR de Visión de Azure AI con un recurso multiservicio de **servicios de Azure AI**. Si aún no lo ha hecho, cree un recurso de **servicios de Azure AI** en la suscripción de Azure.

1. En otra pestaña del explorador, abra **Azure Portal** en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a la suscripción de Azure.

1. Haga clic en el botón **&#65291;Crear un recurso** y busque *Servicios de Azure AI*. Seleccione **Crear** un plan de **servicios de Azure AI**. Se le dirigirá a una página para crear un recurso de servicios de Azure AI. Configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: Este de EE. UU.
    - **Nombre**: *escriba un nombre único*.
    - **Plan de tarifa**: *Estándar S0.*
    - **Al marcar esta casilla, confirmo haber leído y comprendido todos los términos que aparecen a continuación**: *Seleccionado*.

1. Seleccione **Revisar y crear**, a continuación, **Crear** y espere a que se complete la implementación.

## Conecte el recurso del servicio de Azure AI a Vision Studio

A continuación, conecte el recurso del servicio de Azure AI que aprovisionó anteriormente a Vision Studio.

1. En otra pestaña del explorador, vaya a **Vision Studio** en [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Inicie sesión con su cuenta y asegúrese de usar el mismo directorio que el que usó al crear el recurso para los servicios de Azure AI.

1. En la página principal de Vision Studio, seleccione **Ver todos los recursos** en el encabezado **Introducción a Visión**.

    ![El vínculo del recurso Ver todo está resaltado en Introducción a Visión en Vision Studio.](./media/analyze-images-vision/vision-resources.png)

1. En la página **Seleccione un recurso con el que trabajar**, mantenga el cursor del mouse sobre el recurso que creó anteriormente en la lista y active la casilla situada a la izquierda del nombre del recurso. A continuación, seleccione **Seleccionar como recurso predeterminado**.

    > **Nota:**: Si el recurso no apareciera en la lista, es posible que tenga que **Actualizar** la página.

    ![Se muestra el cuadro de diálogo Seleccionar un recurso con el que trabajar con el recurso de Cognitive Services cog-ms-learn-vision-SUFFIX resaltado y activado. El botón Seleccionar como recurso predeterminado está resaltado.](./media/analyze-images-vision/default-resource.png)

1. Cierre la página de configuración seleccionando la "x" en la parte superior derecha de la pantalla.

## Extracción de texto de imágenes en Vision Studio
    
1. En un explorador web, vaya a **Vision Studio** en [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. En la página de aterrizaje **Introducción a Visión**, seleccione **Reconocimiento óptico de caracteres** y, a continuación, el icono **Extraer texto de imágenes**.

1. En el subtítulo **Probar**, confirme la política de uso del recurso después de leerla activando la casilla.  

1. Seleccione [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images) para descargar **ocr-images.zip**. A continuación, abra la carpeta.

1. En el portal, seleccione **Buscar archivo** y vaya a la carpeta del equipo donde descargó **ocr-images.zip**. Seleccione **advert.jpg** y seleccione **Abrir**.

1. Ahora revise lo que se devuelve:
    - En **Atributos detectados**, cualquier texto encontrado en la imagen se organiza en una estructura jerárquica de regiones, líneas y palabras.
    - En la imagen, la ubicación del texto se indica mediante un cuadro de límite, como se muestra aquí:

    ![Imagen del texto de la imagen descrita](media/read-text-computer-vision/text-bounding-boxes.png)

1. Ahora puede probar otra imagen. Seleccione **Buscar archivo** y vaya a la carpeta donde guardó los archivos desde GitHub. Seleccione **letter.jpg**.

    ![Imagen de una carta mecanografiada.](media/read-text-computer-vision/letter.jpg)

1. Revise los resultados de la segunda imagen. También debe devolver el texto y los cuadros de límite del texto. Si tiene tiempo, pruebe **note.jpg** y **receipt.jpg**.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abra **Azure Portal** en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) y seleccione el grupo de recursos que contiene el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Para más información sobre lo que puede hacer con este servicio, consulte la documentación de Visión de Azure AI sobre el [reconocimiento óptico de caracteres](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr).
