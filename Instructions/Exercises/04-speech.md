---
lab:
  title: Exploración de voz en el Portal de la Fundición de IA de Azure
---

# Exploración de voz en el Portal de la Fundición de IA de Azure

El servicio **Voz de Azure AI** transcribe la voz en texto y el texto en voz audible. Puede usar Voz de IA para crear una aplicación que transcriba notas de reuniones o genere texto a partir de la grabación de entrevistas.

En este ejercicio, usarás Voz de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para transcribir audio mediante experiencias de prueba integradas. 

Este ejercicio dura aproximadamente **15** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicies sesión. 

1. En el explorador, accede a `https://ai.azure.com/managementCenter/allResources` y selecciona **Crear nuevo**. A continuación, elija la opción para crear un **recurso de Fundición de IA de Azure**.

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

    Seleccione **Crear**. Espera a que se cree el proyecto. Esto puede tardar unos minutos.

1. Cuando se cree el proyecto, se te dirigirá a una página *Información general* de los detalles del proyecto.
 
1. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**.

    >*Nota*: Expanda el menú para leer su contenido haciendo clic en el icono "expandir" de arriba.

1. En la página de áreas de juegos de Fundición de IA de Azure, seleccione **Probar el área de juegos de Voz**. El área de juegos de Voz es una interfaz de usuario que le permite probar algunas funcionalidades de Voz de Azure AI.

## Exploración de la conversión de voz en texto en el área de juegos de voz de Fundición de IA de Azure

Vamos a probar la *conversión de voz en texto* en el área de juegos de voz de Fundición de IA de Azure. 

1. En la página *Voz*, desplácese hacia abajo y seleccione **Transcripción en tiempo real**.

1. Descargue **speech.zip** abriendo la dirección URL `https://aka.ms/mslearn-speech-files` en una nueva pestaña del explorador. Al usar la dirección URL se debe descargar automáticamente una carpeta en el equipo. 

1. Vaya a la carpeta *Descargas* del equipo y, a continuación, identifique la carpeta descargada. Haga clic con el botón derecho en la carpeta descargada. Seleccione *Extraer todo...*. A continuación, seleccione *Extraer* para descomprimir su contenido. La carpeta descomprimida aparecerá en la pantalla. Cierre la carpeta descomprimida. Observe que la carpeta descomprimida ahora también está en la carpeta *Descargas*.    

1. En el portal de Voz de Fundición de IA de Azure, en *Cargar archivos*, seleccione **Examinar archivos**. Vaya a la carpeta descomprimida. Seleccione **WhatAICanDo.m4a** y, después, **Abrir**.

    ![Examinar archivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. El servicio Voz transcribe y muestra el texto en tiempo real. Si tiene audio en el equipo, puede escuchar la grabación a medida que se transcriba el texto.

1. Revise el resultado. 

    >*Nota*: Para ver la salida completa, es posible que tenga que minimizar el panel *Configurar*. Para minimizarlo, seleccione el icono situado a la derecha del encabezado *Configurar*.

1. En la salida, en *Texto*, puede ver el audio transcrito en texto. 

En este ejercicio, has probado los servicios de Voz de Azure AI en el Área de juegos de voz de Fundición de IA de Azure. Luego has usado la transcripción en tiempo real para transcribir una grabación de audio. Ha podido ver que se genera la transcripción de texto a medida que se reproduce el archivo de audio.

## Limpieza

Si no tienes previsto hacer más ejercicios, elimina los recursos que ya no necesites. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Este ejercicio ha demostrado una de las muchas funcionalidades del servicio Voz. Para más información sobre lo que puede hacer con este servicio, consulte la [página de Voz](https://azure.microsoft.com/services/cognitive-services/speech-services).
