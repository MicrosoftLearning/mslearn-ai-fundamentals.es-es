---
lab:
  title: Explorar Speech Studio
---

# Explorar Speech Studio

El servicio **Voz de Azure AI** transcribe la voz en texto y el texto en voz audible. Puede usar Voz de IA para crear una aplicación que transcriba notas de reuniones o genere texto a partir de la grabación de entrevistas.

En este ejercicio, probará las funcionalidades de Voz de Azure AI mediante Speech Studio de Azure AI. 

## Crear un recurso de *Voz de Azure AI*

Puede usar el servicio Voz creando un recurso de **Voz** o un recurso de **servicios de Azure AI**.

En este ejercicio, creará un recurso de Voz de IA, a menos que ya tenga un recurso que pueda usar.

1. En otra pestaña del explorador, abra [Speech Studio de Azure Al](https://speech.microsoft.com/) e inicie sesión con su cuenta Microsoft.

1. Seleccione **Configuración** y, después, **Crear un recurso.** Configúrelo con los valores siguientes:
    - **Nombre del nuevo recurso**: *escriba un nombre único*.
    - **Suscripción**: *su suscripción a Azure*.
    - **Región**: *Seleccione una [región compatible](https://learn.microsoft.com/azure/ai-services/speech-service/regions)*.
    - **Plan de tarifa**: *FO gratis (si está disponible; de lo contrario, seleccione Estándar S0).*
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
1. Seleccione **Crear recurso**. Espere hasta que se haya creado el recurso y seleccione **Usar recurso**. Se muestra la página Introducción a Voz.

## Explorar conversión de voz en texto en Speech Studio

1. Seleccione [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) para descargar **speech.zip.** Abra la carpeta . 

1. En la página Introducción a Voz, en *Voz* busque *Conversión de voz en texto en tiempo real*. Seleccione **Probar conversión de voz en texto en tiempo real**.

    ![Introducción a Voz](media/recognize-synthesize-speech/try-out-speech-to-text.png)

1. En *Elegir archivos de audio*, seleccione **Examinar archivos** y vaya a la carpeta donde guardó el archivo. Seleccione **WhatAICanDo.m4a** y, después, **Abrir**.

    ![Examinar archivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. El servicio Voz transcribe y muestra el texto en tiempo real. Si tiene audio en el equipo, puede escuchar la grabación a medida que se transcriba el texto.
1. Revise la salida, que debería haber reconocido y transcrito correctamente el audio en texto.

    > **Nota** Si recibe un mensaje de error, espere unos minutos antes de intentarlo de nuevo. El recurso de Voz tarda un poco en estar disponible para su primer uso.

En este ejercicio ha creado un recurso de Voz de IA en Speech Studio. A continuación, ha usado el servicio de conversión de voz en texto en tiempo real para transcribir una grabación de audio. Ha podido ver que se genera la transcripción de texto a medida que se reproduce el archivo de audio.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

En este ejercicio solo se muestran algunas de las funcionalidades del servicio Voz. Para más información sobre lo que puede hacer con este servicio, consulte la [página de Voz](https://azure.microsoft.com/services/cognitive-services/speech-services).
