---
lab:
  title: Extracción de datos de formulario en Document Intelligence Studio
---

# Extracción de datos de formulario en Document Intelligence Studio

Documento de inteligencia de Azure AI puede analizar y extraer información de formularios y documentos y, a continuación, identificar los nombres de campo y los datos. 

¿Cómo se basa Documento de inteligencia en el reconocimiento óptico de caracteres (OCR)? Aunque el OCR puede leer documentos impresos o manuscritos, el OCR extrae texto en un formato no estructurado que es difícil de almacenar en una base de datos o analizar. Documento de inteligencia da sentido a los datos no estructurados mediante la captura de la estructura del texto, como los pares clave-valor e la información contenida en tablas. 

En este ejercicio, echará un vistazo a un modelo precompilado en Documento de inteligencia que está entrenado para reconocer los datos de los recibos. 

> **NOTA** Documento de inteligencia de Azure AI es el nuevo nombre de Azure Form Recognizer. Es posible que todavía vea Azure Form Recognizer en Azure Portal o Document Intelligence Studio.

## Crear recurso de *Documento de inteligencia*

Puede usar Documento de inteligencia de Azure AI mediante la creación de un recurso de *Documento de inteligencia* o un recurso de *servicios de Azure AI*. En este ejercicio, creará un recurso de *Documento de inteligencia*, si aún no tiene uno.

1. En otra pestaña del explorador, abra [Document Intelligence Studio](https://formrecognizer.appliedai.azure.com/studio) e inicie sesión con su cuenta Microsoft.
1. Seleccione **Configuración** y seleccione la pestaña **Recurso**. Seleccione **Crear un nuevo recurso**.
1. En el cuadro de diálogo Crear recurso, escriba lo siguiente:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Nuevo nombre de recurso**: *escriba un nombre único*.
    - **Ubicación**: *Seleccione una región*.
    - **Plan de tarifa**: *FO gratis (si está disponible; de lo contrario, seleccione SO estándar)*.
1. Seleccione **Continuar** y, a continuación, **Finalizar**. Espere a que se implemente el recurso.

    >**Nota** Si el recurso aún no se muestra, es posible que tenga que **actualizar** la página.

Mantenga abierto Document Intelligence Studio.

## Analizar una recepción en Document Intelligence Studio

Ahora está listo para analizar un recibo de la empresa minorista ficticia Northwind Traders.

1. Seleccione [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) para descargar un documento de ejemplo en el equipo. Abra la carpeta . 
1. Seleccione **Form Recognizer Studio** para volver a la página **Introducción a Document Intelligence Studio** y, en Recibos, seleccione **Probar.**
1. En la lista desplegable Precompilado, asegúrese de que la opción **Recibos** está seleccionada.
1. Seleccione **Buscar archivos** y vaya a la carpeta donde guardó la imagen. Seleccione la imagen del recibo y, a continuación **Abrir**. La imagen aparece en el lado izquierdo de la pantalla.

    ![Recibo de Northwind.](media/document-intelligence/northwind-receipt.jpg)

1. A la derecha, seleccione **Ejecutar análisis**.
1. Cuando se ejecuta el análisis, se devuelven los resultados. Observe que el servicio ha reconocido campos de datos específicos, como el nombre del comerciante, la dirección, el número de teléfono y la fecha y hora de la transacción, así como las líneas de pedido, el subtotal, los impuestos y los importes totales. Junto a cada campo hay una probabilidad porcentual de que el campo sea correcto.

En este ejercicio ha usado Document Intelligence Studio para crear un recurso de Documento de inteligencia. A continuación, ha usado el servicio para analizar un recibo. A partir de los resultados devueltos, vio cómo Documento de inteligencia pudo identificar campos específicos, lo que permite que los datos de los documentos cotidianos se procesen más fácilmente. Antes de cerrar Document Intelligence Studio, ¿por qué no prueba algunos de los recibos de ejemplo, incluidos los que están en distintos idiomas?

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó.
1. Seleccione el recurso, seleccione **Eliminar** y, a continuación, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

En este ejercicio solo se muestran algunas de las funcionalidades del servicio Documento de inteligencia de IA. Para más información sobre lo que puede hacer con este servicio, consulte la página [Documento de inteligencia](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
