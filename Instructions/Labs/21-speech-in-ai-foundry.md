---
lab:
  title: Exploración de voz en el Portal de la Fundición de IA de Azure
---

# Exploración de voz en el Portal de la Fundición de IA de Azure

El servicio **Voz de Azure AI** transcribe la voz en texto y el texto en voz audible. Puede usar Voz de IA para crear una aplicación que transcriba notas de reuniones o genere texto a partir de la grabación de entrevistas.

En este ejercicio, usarás Voz de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para transcribir audio mediante experiencias de prueba integradas. 

## Creación de un proyecto en el portal de Azure AI Foundry

1. En una pestaña del explorador, ve a [Fundición de IA de Azure](https://ai.azure.com?azure-portal=true).

1. Inicie sesión con su cuenta. 

1. En la página principal del Portal de la Fundición de IA de Azure, selecciona **Crear un proyecto**. En Fundición de IA de Azure, los proyectos son contenedores que te ayudan a organizar el trabajo.  

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un proyecto seleccionada](./media/azure-ai-foundry-home-page.png)

1. En el panel *Crear un proyecto*, verás un nombre de proyecto generado, que puedes mantener tal cual. Dependiendo de si has creado un centro en el pasado, verás una lista de *nuevos* recursos de Azure que se van a crear o una lista desplegable de centros existentes. Si ves la lista desplegable de centros existentes, selecciona *Crear nuevo centro*, crea un nombre único para el centro y selecciona *Siguiente*.  
 
    ![Captura de pantalla del panel para crear un proyecto con nombres generados automáticamente para el centro y el proyecto](./media/azure-ai-foundry-create-project.png)

> **Importante**: Necesitarás un recurso de Servicios de Azure AI aprovisionado en una ubicación específica para completar el resto del laboratorio.

1. En el mismo panel *Crear un proyecto*, selecciona **Personalizar** y elige una de las siguientes **Ubicaciones**: Este de EE. UU., Centro de Francia, Centro de Corea del Sur, Oeste de Europa u Oeste de EE. UU. para completar el resto del laboratorio. Después selecciona **Crear**. 

1. Toma nota de los recursos que se crean: 
- Servicios de Azure AI
- Centro de Azure AI
- Proyecto de Azure AI
- Cuenta de almacenamiento
- Key vault
- Resource group  
 
1. Una vez creados los recursos, se mostrará la página *Información general* de tu proyecto. En el menú izquierdo de la pantalla, selecciona **Servicios de IA**.
 
    ![Captura de pantalla del menú izquierdo en la pantalla del proyecto con Servicios de IA seleccionado](./media/azure-ai-foundry-ai-services.png)  

1. En la página *Servicios de IA*, selecciona el icono de *Voz* para probar las funcionalidades de Voz de Azure AI.

    ![Captura de pantalla del icono Voz seleccionado en la página Servicios de IA](./media/speech-tile.png)

## Exploración de la conversión de voz en texto en el área de juegos de voz de Fundición de IA de Azure

Vamos a probar la *conversión de voz en texto en tiempo real* en el área de juegos de voz de Fundición de IA de Azure. 

1. En la página *Voz*, desplázate hacia abajo y selecciona **Voz a texto en tiempo real** en *Probar funcionalidades de Voz*. Se abrirá *Área de juegos de voz*. 

1. Seleccione [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) para descargar **speech.zip.** Abra la carpeta . 

1. En *Cargar archivos*, selecciona **Examinar archivos** y ve a la carpeta donde guardaste el archivo. Seleccione **WhatAICanDo.m4a** y, después, **Abrir**.

    ![Examinar archivos](media/recognize-synthesize-speech/browse-files-speech.png)

1. El servicio Voz transcribe y muestra el texto en tiempo real. Si tiene audio en el equipo, puede escuchar la grabación a medida que se transcriba el texto.

1. Revise la salida, que debería haber reconocido y transcrito correctamente el audio en texto.

En este ejercicio, has probado los servicios de Voz de Azure AI en el Área de juegos de voz de Fundición de IA de Azure. A continuación, ha usado el servicio de conversión de voz en texto en tiempo real para transcribir una grabación de audio. Ha podido ver que se genera la transcripción de texto a medida que se reproduce el archivo de audio.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

En este ejercicio solo se muestran algunas de las funcionalidades del servicio Voz. Para más información sobre lo que puede hacer con este servicio, consulte la [página de Voz](https://azure.microsoft.com/services/cognitive-services/speech-services).
