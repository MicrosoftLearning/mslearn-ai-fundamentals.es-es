---
lab:
  title: Extracción de datos de documentos en el Portal de la Fundición de IA de Azure
---

# Extracción de datos de documentos en el Portal de la Fundición de IA de Azure

El servicio **Documento de inteligencia de Azure AI** puede analizar y extraer información de formularios y documentos y, a continuación, identificar los nombres de campo y los datos. 

¿Cómo se basa Documento de inteligencia en el reconocimiento óptico de caracteres (OCR)? Aunque el OCR puede leer documentos impresos o manuscritos, el OCR extrae texto en un formato no estructurado que es difícil de almacenar en una base de datos o analizar. Documento de inteligencia da sentido a los datos no estructurados mediante la captura de la estructura del texto, como los campos de datos y la información contenida en tablas. 

En este ejercicio, usarás los modelos precompilados de Documento de inteligencia de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para reconocer los datos de un recibo. 

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

1. En la página *Servicios de IA*, selecciona el icono *Visión y documento* para probar las funcionalidades de Documento de inteligencia de Azure AI.

    ![Captura de pantalla del icono Visión y documento seleccionado en la página Servicios de IA.](./media/vision-document-tile.png)

## Análisis de recibos con Documento de inteligencia de Azure AI en Fundición de IA de Azure 

Ahora está listo para analizar un recibo de la empresa minorista ficticia Northwind Traders.

1. En la página *Visión y documento*, desplázate hacia abajo y selecciona **Documento**. En *Modelos precompilados para documentos específicos*, selecciona el icono **Recibos**.

1. En la lista desplegable en *Probarlo*, ten en cuenta que el recurso de Servicios de Azure AI está seleccionado. Déjalo tal cual.

1. En el equipo, usa [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) para abrir una imagen de ejemplo de un recibo. Guárdalo en tu escritorio o carpeta Descargas. 
 
1. En la Fundición de IA de Azure, en la página *Recibos*, selecciona **Explorar archivos** y ve a la carpeta donde guardaste la imagen. Seleccione la imagen del recibo y, a continuación **Abrir**. La imagen aparece en el lado izquierdo de la pantalla.

    ![Captura de pantalla de un recibo de northwind.](media/document-intelligence/receipt.jpg)

1. A la derecha, seleccione **Ejecutar análisis**.

1. Cuando se ejecuta el análisis, se devuelven los resultados. Observe que el servicio ha reconocido campos de datos específicos, como el nombre del comerciante, la dirección, el número de teléfono y la fecha y hora de la transacción, así como las líneas de pedido, el subtotal, los impuestos y los importes totales. Junto a cada campo hay una probabilidad porcentual de que el campo sea correcto.

    ![Captura de pantalla del resultado del análisis de recibos en el Portal de la Fundición de IA de Azure, que muestra cuadros de límite alrededor de los campos de datos y el texto en esos campos extraídos.](media/receipt-lab-result.png)

En este ejercicio has usado el modelo de recibos precompilado de Documento de inteligencia de Azure AI en el Portal de la Fundición de IA de Azure. A partir de los resultados devueltos, vio cómo Documento de inteligencia pudo identificar campos específicos, lo que permite que los datos de los documentos cotidianos se procesen más fácilmente. Antes de cerrar la demostración, ¿por qué no pruebas algunos de los recibos de ejemplo, incluidos los que están en distintos idiomas?

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

En este ejercicio solo se muestran algunas de las funcionalidades del servicio Documento de inteligencia de IA. Para más información sobre lo que puede hacer con este servicio, consulte la página [Documento de inteligencia](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
