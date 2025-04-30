---
lab:
  title: Uso de respuesta a preguntas con Language Studio
---

# Uso de respuesta a preguntas con Language Studio

En este ejercicio, usarás Language Studio para crear y entrenar una knowledge base de preguntas y respuestas. El contenido de la knowledge base provendrá de una página de preguntas más frecuentes existente del sitio web de Margie’s Travel, una agencia ficticia de viajes. Después, usará Language Studio para ver cómo funcionaría cuando lo usen los clientes.

Lenguaje de Azure AI incluye funcionalidades de *respuesta a preguntas*, que usará para crear una knowledge base. Las knowledge bases pueden crearse escribiendo pares de preguntas y respuestas manualmente o desde un documento o página web existente. Margie’s Travel quiere usar su documento de preguntas más frecuentes existente.

La característica de respuesta a preguntas del servicio Language permite crear rápidamente una knowledge base, ya sea introduciendo pares de preguntas y respuestas, o desde un documento o página web existentes. A continuación, puede usar algunas funcionalidades integradas de procesamiento de lenguaje natural para interpretar preguntas y encontrar respuestas adecuadas.

## Creación de un recurso de *Language*

Para usar la respuesta a preguntas, necesita un recurso **Language**.

1. En otra pestaña del explorador, abra Azure Portal en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a la suscripción de Azure.

1. Haga clic en el botón **&#65291;Crear un recurso** y busque *servicio de lenguaje*. Seleccione **Crear** un plan de **servicio de lenguaje**. Se le llevará a una página para **Seleccionar características adicionales**. Use la configuración siguiente:
    - **Selección de características adicionales**:
        - **Default features** (Características predeterminadas): *mantenga las características predeterminadas*.
        - **Características personalizadas**: *seleccione respuesta a preguntas personalizadas*.
     - Seleccione **Continuar para crear el recurso**
    ![Creación de un recurso de Servicio de lenguaje con la respuesta a preguntas personalizada habilitada.](media/create-a-bot/create-language-service-resource.png)

1. En la página **Crear Language**, especifique la configuración siguiente:
    - **Detalles del proyecto**
        - **Suscripción**: *su suscripción a Azure*.
        - **Grupo de recursos**: *seleccione un grupo de recursos existente o cree uno*.
    - **Detalles de instancia**
        - **Región**: *Seleccione una región. Si está en el este de EE. UU., use "Este de EE. UU. 2"*      
        - **Nombre**: *un nombre único para el recurso de Language*.
        - **Plan de tarifa**: S (llamadas de 1K por minuto)
    - **Responder preguntas personalizada**
        - **Ubicación de Azure Search**: *cualquier ubicación disponible*.
        - **Plan de tarifa de búsqueda de Azure**: Gratis F (3 índices): (*si este nivel no está disponible, seleccione Básico*)
    - **Aviso de inteligencia artificial responsable**
        - **Al marcar esta casilla, certifico que he revisado y reconocido los términos del aviso de IA responsable**: *Seleccionado*.

1. Seleccione **Revisar y crear** y, luego, **Crear**. Espere a la implementación del servicio Language que admitirá la knowledge base personalizada de respuesta a preguntas.

    > **Nota** Si ya has aprovisionado un recurso de **Azure Cognitive Search** en el plan Gratis, puede que la cuota no te permita crear otro. En ese caso, seleccione un nivel distinto de **Gratis F**.

## Creación de un nuevo proyecto

1. En una pestaña nueva del explorador, abra el portal de Language Studio en [https://language.azure.com](https://language.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a su suscripción de Azure.
1. Si se le pide que elija un recurso de Language, seleccione la configuración siguiente:
    - **Directorio de Azure**: *directorio de Azure que contiene la suscripción*.
    - **Suscripción de Azure**: *su suscripción de Azure*.
    - **Recurso de lenguaje**: *el recurso de lenguaje que creó anteriormente.*

    Si ***no*** se le pide que elija un recurso de Language, puede deberse a que tiene varios recursos de Language en la suscripción, en cuyo caso:
    1. En la barra de la parte superior de la página, seleccione **Configuración (&#9881;)**.      
    1. En la página **Configuración,** vea la pestaña **Recursos**.
    1. Selecciona el recurso de lenguaje que acabas de crear y selecciona **Cambiar recurso**.
    1. En la parte superior de la página, selecciona **Language Studio** para volver a la página principal de Language Studio.

1. En la parte superior del portal de Language Studio, en el menú **Crear**, seleccione **Custom question answering** (Respuesta a preguntas personalizada).

    ![Responder preguntas personalizada](media/create-a-bot/create-custom-question-answering.png)

1. En la página **Elegir idioma para *el recurso***, seleccione **Quiero seleccionar el idioma al crear un proyecto en este recurso** y haga clic en **Siguiente**.
  ![Quiero seleccionar el lenguaje](media/create-a-bot/create-project.png)

1. En la página **Enter basic information** (Escribir información básica), escriba los detalles siguientes y haga clic en **Siguiente**:
    - **Language resource** (Recurso de Language): *elija el recurso de lenguaje*.  
    - **Azure search resource** (Recurso de Azure Search): *elija el recurso de Azure Search*.
    - **Nombre**: `MargiesTravel`
    - **Descripción**: `A simple knowledge base`
    - **Idioma de origen**: inglés.
    - **Respuesta predeterminada cuando no se devuelve ninguna respuesta**: `No answer found`
1. En la página **Revisar y finalizar**, seleccione **Crear proyecto**.
1. Se le llevará a la página **Manage sources** (Administrar orígenes). Seleccione **&#65291;Agregar origen** y seleccione **URL**.
1. En el cuadro **Agregar direcciones URL**, seleccione **+ Agregar URL**. Escriba lo siguiente y seleccione **Agregar todo**:
    - **Nombre de dirección URL**: `MargiesKB`
    - **URL**: `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/natural-language/margies_faq.docx`
    - **Classify file structure** (Clasificar estructura de archivos): *Detectar automáticamente*
1. Seleccione **Agregar todas**.  

 ![Agregar dirección URL](media/create-a-bot/add-url.png)

## Edición de la base de conocimiento

La base de conocimiento se basa en los detalles del documento de preguntas más frecuentes y en algunas respuestas predefinidas. Puede agregar pares personalizados de preguntas y respuestas para complementarlos.

1. Expanda el panel izquierdo y seleccione **Editar knowledge base**. A continuación, seleccione **+** para agregar un nuevo par de preguntas.
1. En el cuadro de diálogo **Agregar un nuevo par de preguntas y respuestas**, en la **Pregunta** escriba `Hello`y, en la **Respuesta** escriba `Hi`, a continuación, seleccione **Listo**.
1. Expanda **Preguntas alternativas** y seleccione **+ Agregar pregunta alternativa**. A continuación, escriba `Hiya` como expresión alternativa para "Hola".
1. En la parte superior del panel **Pares de preguntas y respuestas**, seleccione **Guardar** para guardar la knowledge base.

## Entrenamiento y prueba de la base de conocimiento

Ahora que tiene una knowledge base, puede probarla.

1. En la parte superior del panel **Pares de preguntas y respuestas**, seleccione **Probar** para probar la knowledge base.
1. En el panel de prueba, en la parte inferior, escriba el mensaje `Hi`. Después de hacerlo, debería aparecer la respuesta *Hola*.
1. En el panel de prueba, en la parte inferior, escriba el mensaje `I want to book a flight`. Se debe devolver una respuesta adecuada de las preguntas más frecuentes.

    > **Nota** La respuesta incluye una *rspuesta corta*, además de un fragmento de respuesta *más detallado*: el fragmento de respuesta muestra el texto completo en el documento de preguntas más frecuentes de la pregunta coincidente más parecida, mientras que la respuesta corta se extrae del fragmento de manera inteligente. Puede controlar si la visualización de la respuesta corta es de la respuesta; para ello, seleccione la casilla **Display short answer** (Mostrar respuesta corta) en la parte superior del panel de prueba.

1. Pruebe otra pregunta, como `How can I cancel a reservation?`
1. Cuando haya terminado de probar la knowledge base, seleccione **Probar** para cerrar el panel de prueba.

## Implementar el proyecto

Puede implementar la knowledge base como una aplicación cliente para responder a preguntas.

1. En el panel izquierdo, seleccione **Implementar knowledge base**.
1. En la parte superior de la página, seleccione **Implementar**. Un cuadro de diálogo le preguntará si desea implementar el proyecto. Seleccione **Implementar**.

 ![Implemente la knowledge base.](media/create-a-bot/deploy-knowledge-base.png)

## Limpieza

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costes innecesarios.

1. Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó. 
1. Seleccione el recurso y seleccione **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

- Para obtener más información sobre el servicio de respuesta a preguntas, vea la [documentación](https://docs.microsoft.com/azure/cognitive-services/language-service/question-answering/overview).
