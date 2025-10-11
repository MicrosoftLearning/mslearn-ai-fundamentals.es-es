---
lab:
  title: Extracción de datos con comprensión de contenidos en el Portal de la Fundición de IA de Azure
---

# Extracción de datos con comprensión de contenidos en el Portal de la Fundición de IA de Azure

El Servicio de comprensión de contenido de IA de Azure proporciona análisis multimodal de documentos, archivos de audio, vídeo e imágenes para extraer información.

En este ejercicio, usará el Servicio de comprensión de contenido de IA de Azure en el Portal de Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para extraer información de las facturas. 

Este ejercicio dura aproximadamente **25** minutos.

## Creación de un proyecto de Fundición de IA de Azure para comprender el contenido

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Recorte de pantalla de la página principal del Portal de la Fundición de IA de Azure.](./media/ai-foundry-portal.png)

1. Desplácese hasta la parte inferior de la página y seleccione el icono **Explorar los servicios de Azure AI**.

    ![Recorte de pantalla del icono "Explorar los servicios de Azure AI".](./media/ai-services.png)

1. En la página Servicios de Azure AI, seleccione **Probar la comprensión de contenidos**.

    ![Recorte de pantalla del botón "Probar la comprensión de contenidos".](./media/try-content-understanding.png)

1. En la página "Comprensión de contenidos", seleccione **Crear un proyecto para comenzar**. A continuación, en el cuadro de diálogo **Crear proyecto**, seleccione el tipo de recurso recomendado (**recurso de Fundición de IA de Azure**):

    ![Recorte de pantalla de los resultados del análisis.](./media/resource-type.png)

1. En la página **Siguiente**, escriba un nombre válido para el proyecto. A continuación, seleccione **Opciones avanzadas** y especifique la siguiente configuración:
    - **Recurso de Fundición de IA de Azure**: *un nombre válido para el recurso de Fundición de IA de Azure*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Región**: seleccione una de las siguientes ubicaciones\*:
        * Oeste de EE. UU.
        * Centro de Suecia
        * Este de Australia

    \**En el momento de redactar este documento, la comprensión de contenidos se admite en estas regiones.*

    ![Captura de pantalla de la configuración del proyecto.](./media/content-project-settings.png)

1. Seleccione **Crear**. Espera hasta que se complete el proceso de configuración. Esto puede tardar unos minutos.

## Extracción de información de una factura

1. Descarga [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. En la página "Comprensión de contenidos", seleccione la pestaña **Probarlo** y, a continuación, seleccione el icono **Extracción de datos de factura**.

    ![Recorte de pantalla de la página "Probarlo" de la comprensión de contenidos.](./media/content-understanding-invoice.png)

    Se proporciona una factura de ejemplo.

1. Seleccione la factura de ejemplo y use el botón **Ejecutar análisis** para extraer información de ella. Una vez completado el análisis, vea los resultados.

    ![Recorte de pantalla de los resultados del análisis de la factura de ejemplo.](./media/sample-invoice-analysis.png)

1. Use el vínculo **Examinar archivos** para cargar el documento **contoso-invoice-1.pdf** que descargó anteriormente y ejecute el análisis en ese archivo.

    ![Recorte de pantalla de los resultados de analizar la factura de Contoso.](./media/contoso-invoice-analysis.png)

    Tenga en cuenta que el analizador de comprensión de contenidos puede extraer información de esta factura, aunque el formato no sea igual que el del ejemplo.

1. En el panel de la derecha donde se muestran los campos extraídos, examine la pestaña **Resultado** para ver la respuesta JSON que se enviaría a una aplicación cliente. Un desarrollador escribiría código para procesar esta respuesta y haría algo con los campos extraídos.

    ![Recorte de pantalla de los resultados de analizar la factura de Contoso.](./media/invoice-analysis-json.png)

## Limpieza

Si has terminado de trabajar con el servicio de comprensión de contenidos, deberías eliminar los recursos que has creado en este ejercicio para evitar incurrir en costes innecesarios de Azure.

- En Azure Portal, elimina el grupo de recursos que has creado en este ejercicio.
