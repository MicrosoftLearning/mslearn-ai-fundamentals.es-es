---
lab:
  title: Extracción de datos con comprensión de contenidos en el Portal de la Fundición de IA de Azure
---

# Extracción de datos con comprensión de contenidos en el Portal de la Fundición de IA de Azure

**Servicio de comprensión de contenido de IA de Azure (versión preliminar)** usa la IA generativa para procesar contenido de cualquier tipo (documentos, imágenes, vídeos y audio) en un formato de salida definido por el usuario.

En este ejercicio, usarás el Servicio de comprensión de contenido de IA de Azure en el Portal de la Fundición de IA de Azure, la plataforma de Microsoft para crear aplicaciones inteligentes, para reconocer los datos de las facturas. 

Este ejercicio dura aproximadamente **25** minutos.

## Creación de un proyecto de Fundición de IA de Azure y una tarea de comprensión del contenidos

1. En un explorador web, abre el [Portal de la Fundición de IA de Azure](https://ai.azure.com) en `https://ai.azure.com` e inicia sesión con tus credenciales de Azure. Cierra las sugerencias o paneles de inicio rápido que se abran la primera vez que inicias sesión y, si es necesario, usa el logotipo de **Fundición de IA de Azure** en la parte superior izquierda para navegar a la página principal, que es similar a la siguiente imagen (cierra el panel **Ayuda** si está abierto):

    ![Captura de pantalla de la página principal de Fundición de IA de Azure con la opción de crear un agente seleccionada.](./media/azure-ai-foundry-home-page.png)

1. En una nueva ventana del explorador, abre la [página de exploración de servicios de Azure AI](https://ai.azure.com/explore/aiservices).

1. En la página *Servicios de IA*, seleccione el icono *Probar comprensión de contenidos*.

1. Seleccione **Seleccionar o crear un proyecto para comenzar**. 

1. Seleccione **+Crear un proyecto**.

1. En el asistente, escriba un nombre válido para el proyecto. 

1. Selecciona **Opciones avanzadas** y especifica los siguientes valores:
    - **Recurso de Fundición de IA de Azure**: *mantén el nombre predeterminado*
    - **Suscripción**: *suscripción a Azure*
    - **Grupo de recursos**: *crea o selecciona un grupo de recursos*
    - **Región**: selecciona una de las siguientes ubicaciones:
        * Oeste de EE. UU.
        * Centro de Suecia
        * Este de Australia

1. Seleccione **Crear**. Espera hasta que se complete el proceso de configuración. Esto puede tardar unos minutos.

    >**Nota**: si recibes un error de permisos, selecciona el botón **Corregirlo** para agregar los permisos adecuados para continuar.

1. Cuando se cree el proyecto, se le llevará de forma predeterminada a la ventana de creación de tareas de comprensión de contenidos. Use la siguiente configuración para crear una tarea de comprensión de contenidos:
    - **Nombre de tarea**: `contoso-invoice`
    - **Descripción**: `An invoice analysis task`
    - *Selección del análisis de contenido de un solo archivo*
    - **Configuración avanzada**: *mantenga el valor predeterminado*.

1. Selecciona **Crear** y espera a que la tarea se cree. 

1. Selecciona la tarea **contoso-invoice**. 

## Análisis de una factura con el Servicio de comprensión de contenido de IA de Azure de Fundición de IA de Azure 

Supongamos que deseas extraer los datos de muchas facturas para colocarlos en una base de datos. Puedes usar el Servicio de comprensión de contenido de IA de Azure para analizar una factura y crear un analizador que pueda analizar otras facturas similares. Comencemos definiendo el esquema.

#### Definición del esquema 

1. En la página *Definir esquema*, puedes agregar archivos de prueba. Descarga [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Carga el archivo en la página **Definir esquema**. Seleccione la plantilla **Extracción de datos de factura**. La plantilla de extracción de datos de factura tiene campos de datos seleccionados previamente que el analizador intentará detectar. 

    ![Captura de pantalla de la página Definir esquema en la herramienta de comprensión de contenidos.](./media/content-understanding/define-schema.png)

1. Seleccione **Crear**. Ahora tienes la capacidad de modificar el esquema agregando o eliminando campos. Cuando hayas terminado de revisar los campos, selecciona **Guardar**.

    ![Captura de pantalla de la página Definir esquema después de seleccionar Crear.](./media/content-understanding/define-schema-2.png)

1. Espera a que se ejecute el análisis. Esta operación puede tardar unos minutos.

#### Prueba del analizador 

1. Cuando finalice el análisis, podrás ver cómo lo ha hecho el analizador en la página *Probar analizador*. Revise la pestaña *Campos* (*Nota*: Es posible que tenga que expandir la ventana para ver los resultados completos). ¿Estos datos se alinean con lo que ve en la factura? 
    ![Captura de pantalla de la página Probar analizador con la pestaña Resultados de campo resaltada.](./media/content-understanding/test-analyzer-fields.png)

1. Observa la *puntuación de confianza* junto a cada campo. La puntuación de confianza representa que tanta confianza tiene el modelo en que su resultado es preciso. Los resultados con puntuaciones de confianza más próximos al 100 % indican una mayor confianza en la predicción.

1. Revise la pestaña *Resultado*. La misma información que ve representada en la pestaña "Campos" se encuentra en la pestaña "Resultados" en JSON. El JSON muestra cómo se ve la información cuando se envía y recibe de una aplicación cliente. 

    ![Captura de pantalla de la página Probar analizador con la pestaña Resultados resaltada.](./media/content-understanding/test-analyzer-result.png)

1. El servicio de comprensión de contenidos debe haber identificado correctamente el texto que corresponde a los campos del esquema. Si no lo hubieras hecho, podrías usar la página *Etiquetado de datos* para cargar otro formulario de ejemplo e identificar explícitamente el texto correcto para cada campo. Cuando esté satisfecho con lo bien que el analizador puede detectar los datos de la factura, seleccione la pestaña **Lista de analizadores**. 

#### Compilación del analizador 

Ahora que has entrenado un modelo para extraer campos de una factura de ejemplo, puedes compilar un analizador para usarlo con formularios similares. Al compilar un analizador, puedes implementar el modelo y usarlo para automatizar otras tareas de la factura.

1. En la pestaña *Lista de analizadores*, seleccione **+Crear analizador**. Escribe lo siguiente: 
    - **Nombre**: `invoice-analyzer`
    - **Descripción**: `An invoice analyzer`

    ![Captura de pantalla de la página Compilar analizador.](./media/content-understanding/build-analyzer.png)

1. Seleccione **Compilar**. Espera a que el nuevo analizador esté listo (usa el botón Actualizar para comprobar). El analizador usa un modelo predictivo basado en el esquema que has definido y probado en los pasos anteriores. 
1. Ahora vamos a probar el analizador que has compilado. Descarga una factura diferente de Contoso [contoso-invoice-2.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf) de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf`.
1. Vuelva a la página *Lista de analizadores* y seleccione el vínculo invoice-analyzer. Se mostrarán los campos definidos en el esquema del analizador.
1. En la página invoice-analyzer, selecciona *Probar*.
1. Usa el botón **+ Cargar archivos de prueba** para cargar *contoso-receipt-2.pdf*. Selecciona **Ejecutar análisis** para extraer los datos de campo del formulario de prueba. Revisa los resultados de la prueba.

    ![Captura de pantalla de los resultados de la prueba del analizador que has compilado.](./media/content-understanding/build-analyzer-2.png)

1. Selecciona la pestaña *Ejemplo de código*. Busca el *punto de conexión* en el código. En la fase *Compilar analizador* del proceso, implementaste el modelo de comprensión de contenidos en un punto de conexión. El punto de conexión se puede usar en el código del mismo modo como lo ves en el ejemplo, para incorporar el modelo en un proceso repetible en una aplicación.  

    ![Captura de pantalla del ejemplo de código del analizador que has compilado.](./media/content-understanding/code-example.png)

## Limpieza

Si has terminado de trabajar con el servicio de comprensión de contenidos, deberías eliminar los recursos que has creado en este ejercicio para evitar incurrir en costes innecesarios de Azure.

- En el Portal de la fundición de IA de Azure, ve al proyecto contoso-receipt y elimínalo.
- En Azure Portal, elimina el grupo de recursos que has creado en este ejercicio.
