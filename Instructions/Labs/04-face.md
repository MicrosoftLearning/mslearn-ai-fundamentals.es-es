---
lab:
  title: "Detección de caras en Vision\_Studio"
---

# Detección de caras en Vision Studio

Las soluciones de visión suelen requerir inteligencia artificial para poder detectar caras humanas. Supongamos que la empresa minorista Northwind Traders quiere saber dónde están ubicados sus clientes dentro de una tienda para darles una mejor atención. Una manera de lograrlo es determinar si hay caras en las imágenes y, si es así, devolver las coordenadas del rectángulo de selección que muestran su ubicación.

Para probar las funcionalidades de detección de caras del servicio Face de Azure AI, usará [Azure Vision Studio](https://portal.vision.cognitive.azure.com/). Es una plataforma basada en la interfaz de usuario que le permite explorar las características de Visión de Azure AI sin necesidad de escribir código.

## Creación de un grupo de recursos de *servicios de Azure AI*

Puede usar el servicio Face de Azure AI con un recurso de varios servicios, como los **servicios de Azure AI**. Si aún no lo ha hecho, cree un recurso de **servicios de Azure AI** en la suscripción de Azure.

1. En otra pestaña del explorador, abra Azure Portal en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a la suscripción de Azure.

1. Haga clic en el botón **&#65291;Crear un recurso** y busque *Servicios de Azure AI*. Seleccione **Crear** un plan de **servicios de Azure AI**. Se le dirigirá a una página para crear un recurso de servicios de Azure AI. Configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: *Seleccione la región geográfica más cercana. Si está en el este de EE. UU., use "Este de EE. UU. 2"*.
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

## Detección de caras en Vision Studio 

1. En un explorador web, vaya a **Vision Studio** en [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. En la página de aterrizaje de **Introducción a Vision**, seleccione la pestaña **Face** y, después, seleccione el icono **Detectar caras en una imagen**.

1. En el subtítulo **Probar**, confirme la política de uso de recursos después de leerla, y active la casilla.  

1. Seleccione cada una de las imágenes de ejemplo y observe los datos de detección de caras que se devuelven.

1. Ahora vamos a probar con algunas de nuestras propias imágenes. Seleccione [**https://aka.ms/mslearn-detect-faces**](https://aka.ms/mslearn-detect-faces) para descargar **detect-faces.zip.**. A continuación, abra la carpeta en el equipo.

1. Busque el archivo denominado **store-camera-1.jpg**, que contiene la siguiente imagen:

    ![Una imagen de las personas de una tienda.](./media/create-face-solutions/store-camera-1.jpg)

1. Cargue **store-camera-1.jpg** y revise los detalles de detección de caras que se devuelven.

1. Busque el archivo denominado **store-camera-2.jpg**, que contiene la siguiente imagen:

    ![Imagen de más personas en una tienda.](./media/create-face-solutions/store-camera-2.jpg)

1. Cargue **store-camera-2.jpg** y revise los detalles de detección de caras que se devuelven.

1. Busque el archivo denominado **store-camera-3.jpg**, que contiene la siguiente imagen:

    ![Una imagen de la gente en una tienda con una planta ocultando una cara.](./media/create-face-solutions/store-camera-3.jpg)

1. Cargue **store-camera-3.jpg** y revise los detalles de detección de caras que se devuelven. Observe cómo Azure AI Face no ha detectado la cara oculta.

En este ejercicio, ha explorado cómo los servicios de Azure AI pueden detectar caras en imágenes. Si tiene tiempo, no dude en probar las imágenes de ejemplo o algunas de sus propias imágenes.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1. Abra **Azure Portal** en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) y seleccione el grupo de recursos que contiene el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Para obtener más información sobre lo que puede hacer gracias a este servicio, consulte la [página del servicio Face de Azure AI](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity).
