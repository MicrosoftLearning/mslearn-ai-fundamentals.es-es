---
lab:
  title: Exploración de voz en el Portal de la Fundición de IA de Azure
---

# Exploración de voz en el Portal de la Fundición de IA de Azure

Voz de Azure AI transcribe la voz en texto y convierte el texto en voz audible. Puede usar Voz de AI para crear una aplicación que pueda transcribir notas de una reunión o generar texto a partir de la grabación de entrevistas, o para admitir un asistente de IA interactivo que pueda responder a comandos y consultas hablados.

En este ejercicio, usará Voz de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para explorar las funcionalidades principales de Voz de Azure AI. 

Este ejercicio dura aproximadamente **15** minutos.

## Creación de un proyecto en el portal de Azure AI Foundry

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Recorte de pantalla de la página principal del Portal de la Fundición de IA de Azure.](./media/ai-foundry-portal.png)

1. Desplácese hasta la parte inferior de la página y seleccione el icono **Explorar los servicios de Azure AI**.

    ![Recorte de pantalla del icono "Explorar los servicios de Azure AI".](./media/ai-services.png)

1. En la página "Servicios de Azure AI", seleccione el icono **Voz**.

    ![Recorte de pantalla del icono Voz.](./media/speech.png)

1. En la página **Voz**, seleccione **Ir al área de juegos de Voz**. A continuación, cuando se le solicite, cree un proyecto con la siguiente configuración:
    - **Nombre del proyecto**: *escriba un nombre válido para el proyecto.*
    - **Configuración avanzada**:
        - **Suscripción**: *suscripción a Azure*
        - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
        - **Región**: *seleccione cualquier región **recomendada de Fundición de IA***
        - **Fundición de IA o Azure OpenAI**: *cree un nuevo recurso de Fundición de IA de Azure con un nombre válido*

1. Seleccione **Crear**. Espera a que se cree el proyecto. Esto puede tardar unos minutos.

1. Cuando se cree el proyecto, se le llevará a un área de juegos de **Voz** (si no es así, en el panel de tareas de la izquierda, seleccione **Áreas de juegos** y abra el área de juegos de Voz desde allí).

    El área de juegos de Voz es una interfaz de usuario que le permite probar algunas funcionalidades de Voz de Azure AI.  

## Exploración de la conversión de voz en texto en el área de juegos de voz de Fundición de IA de Azure

Vamos a probar la *conversión de voz en texto* en el área de juegos de voz de Fundición de IA de Azure.

1. En una nueva pestaña del explorador, descargue **[speech.zip](https://aka.ms/mslearn-speech-files)** desde `https://aka.ms/mslearn-speech-files` en una nueva pestaña del explorador. Después de descargar el archivo, extráigalo en una carpeta local. 

1. De nuevo en el Portal de la Fundición de IA de Azure, en la página Voz, en la pestaña **Conversión de voz en texto**, seleccione **Transcripción en tiempo real**.

1. En **Cargar archivos**, seleccione **Examinar archivos** y cargue **WhatAICanDo.m4a** desde la carpeta para descargarlo y extraerlo.

    El servicio Voz transcribe y muestra el texto en tiempo real. Si tiene audio en el equipo, puede escuchar la grabación a medida que se transcriba el texto.

    ![Recorte de pantalla de la interfaz de transcripción en tiempo real en el área de juegos de Voz.](./media/real-time-transcription.png)

1. Revise el resultado. 

    >*Sugerencia*: Para ver la salida completa, es posible que tenga que minimizar el panel *Configurar*. Para minimizarlo, seleccione el icono situado a la derecha del encabezado *Configurar*.

    En la salida, en **Texto**, puede ver el audio transcrito en texto.

## Exploración de la conversión de texto a voz en el área de juegos de Voz de la Fundición de IA de Azure

Ahora veamos cómo Voz de Azure AI puede generar voz audible a partir de texto.

1. En el área de juegos de Voz, seleccione la pestaña **Texto a voz** y asegúrese de que se ha seleccionado **Galería de voz**.
1. Vea las voces disponibles y seleccione una (como *Ava Multilingüe*).
1. En el panel **Detalles de voz**, seleccione la pestaña **Probarlo**. A continuación, escriba texto (por ejemplo, `The rain in Spain stays mainly in the plain`) y use el botón **Reproducir** para sintetizar la voz del texto.

    ![Recorte de pantalla de la interfaz de la galería de voz en el área de juegos de Voz.](./media/voice-gallery.png)

    El texto se habla mediante la voz seleccionada. Puede probar otras voces para comparar la salida hablada.

## Limpieza

Si no tienes previsto hacer más ejercicios, elimina los recursos que ya no necesites. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione **Eliminar grupo de recursos** y **escriba el nombre del grupo de recursos** para confirmar. El grupo de recursos se elimina.

## Saber más

Este ejercicio ha demostrado una de las muchas funcionalidades del servicio Voz. Para más información sobre lo que puede hacer con este servicio, consulte la [página de Voz](https://azure.microsoft.com/services/cognitive-services/speech-services).
