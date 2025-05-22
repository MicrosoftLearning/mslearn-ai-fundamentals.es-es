---
lab:
  title: Exploración de voz en el Portal de la Fundición de IA de Azure
---

# Exploración de voz en el Portal de la Fundición de IA de Azure

El servicio **Voz de Azure AI** transcribe la voz en texto y el texto en voz audible. Puede usar Voz de IA para crear una aplicación que transcriba notas de reuniones o genere texto a partir de la grabación de entrevistas.

En este ejercicio, usarás Voz de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para transcribir audio mediante experiencias de prueba integradas. 

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
 
1. En el menú de la izquierda de la pantalla, selecciona **Áreas de juegos**.

1. En la página *Áreas de juegos*, selecciona el icono de **Área de juegos de voz** para probar algunas funcionalidades de Voz de Azure AI.

## Exploración de la conversión de voz en texto en el área de juegos de voz de Fundición de IA de Azure

Vamos a probar la *conversión de voz en texto* en el área de juegos de voz de Fundición de IA de Azure. 

1. En la página *Voz*, desplázate hacia abajo y selecciona **Transcripción en tiempo real** en *Probar funcionalidades de Voz*. Se abrirá *Área de juegos de voz*. 

1. Seleccione [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) para descargar **speech.zip.** Abra la carpeta . 

1. En *Cargar archivos*, selecciona **Examinar archivos** y ve a la carpeta donde guardaste el archivo. Seleccione **WhatAICanDo.m4a** y, después, **Abrir**.

    ![Examinar archivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. El servicio Voz transcribe y muestra el texto en tiempo real. Si tiene audio en el equipo, puede escuchar la grabación a medida que se transcriba el texto.

1. Revise la salida, que debería haber reconocido y transcrito correctamente el audio en texto.

En este ejercicio, has probado los servicios de Voz de Azure AI en el Área de juegos de voz de Fundición de IA de Azure. Luego has usado la transcripción en tiempo real para transcribir una grabación de audio. Ha podido ver que se genera la transcripción de texto a medida que se reproduce el archivo de audio.

## Limpieza

Si no tienes previsto hacer más ejercicios, elimina los recursos que ya no necesites. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Este ejercicio ha demostrado una de las muchas funcionalidades del servicio Voz. Para más información sobre lo que puede hacer con este servicio, consulte la [página de Voz](https://azure.microsoft.com/services/cognitive-services/speech-services).
