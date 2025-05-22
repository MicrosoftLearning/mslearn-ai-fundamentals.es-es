---
lab:
  title: Extracción de datos de documentos en el Portal de la Fundición de IA de Azure
---

# Extracción de datos de documentos en el Portal de la Fundición de IA de Azure

El servicio **Documento de inteligencia de Azure AI** puede analizar y extraer información de formularios y documentos y, a continuación, identificar los nombres de campo y los datos. 

¿Cómo se basa Documento de inteligencia en el reconocimiento óptico de caracteres (OCR)? Aunque el OCR puede leer documentos impresos o manuscritos, el OCR extrae texto en un formato no estructurado que es difícil de almacenar en una base de datos o analizar. Documento de inteligencia da sentido a los datos no estructurados mediante la captura de la estructura del texto, como los campos de datos y la información contenida en tablas. 

En este ejercicio, usarás los modelos precompilados de Documento de inteligencia de Azure AI en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para reconocer los datos de un recibo. 

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
