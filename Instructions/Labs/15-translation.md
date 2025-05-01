---
lab:
  title: Exploración del Traductor de Azure AI
---

# Exploración del Traductor de Azure AI

> **Nota** Para completar este laboratorio, necesitará una [suscripción de Azure](https://azure.microsoft.com/free?azure-portal=true) en la que tenga acceso de administrador.

La inteligencia artificial (IA) puede ayudar a simplificar la traducción entre idiomas, lo que ayuda a eliminar las barreras a la comunicación entre países y culturas.

Para probar las funcionalidades del servicio Traductor de Azure AI, lo examinaremos en acción en Azure Portal. Los mismos principios y funcionalidad se aplican en soluciones reales, como sitios web o aplicaciones de teléfono.

## Creación de un recurso de *Traductor*

Para poder usar el servicio Translator, crea un recurso de **Translator** o un recurso de **Servicios de Azure AI**.

Para este ejercicio, crearás un recurso de **Traductor** en la suscripción a Azure.

1. En otra pestaña del explorador, abra Azure Portal en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con su cuenta Microsoft.

1. Haz clic en el botón **&#65291;Crear un recurso** y busca *Traductor*. Seleccione **Crear**. Se te dirigirá a una página para crear un recurso de Traductor. Configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: *elija cualquier región disponible*.
    - **Nombre**: *escriba un nombre único*.
    - **Plan de tarifa**: estándar S0

1. Revise y cree el recurso y espere a que finalice la implementación. A continuación, vaya al recurso implementado.

## Exploración del servicio Traductor 

Podemos explorar las funcionalidades del servicio Traductor en Azure Portal. 

1. En Azure Portal, en el recurso implementado, revisa la página *Información general*.

    ![Captura de pantalla de la página de información general del recurso de Traductor.](media/use-translator/translator-azure-portal.png)

1. En la sección *Probarlo* de la página de información general, en la sección *Desde: Detección automática*, escribe el texto `Welcome to Azure AI Fundamentals`. Observa que el JSON que aparece en correspondencia en la sección *Ver solicitud*. 

1. En la sección *Ver respuesta*, visualiza el JSON. Entre bastidores, se ha enviado una *solicitud* al servicio Traductor. La *respuesta* incluye el idioma de origen detectado con una puntuación de confianza, una traducción con el alfabeto del idioma de salida y el código de idioma de salida. 

1. La demostración de la sección *Probarlo* muestra el aspecto que tendría si hubieras creado una aplicación de traducción sencilla con una interfaz de usuario. En el caso de la demostración, tan pronto como escribes texto, se realiza la solicitud al servicio Traductor. ¿Cómo podrías realizar esta solicitud? Consulta la pestaña *Código de ejemplo*. Aquí verás ejemplos de código en diferentes lenguajes de programación que se podrían usar para realizar la solicitud. 

1. Identifica las líneas de los ejemplos de código en los que necesitas incluir la **clave** y el **punto de conexión** del servicio Traductor. Con la clave y el punto de conexión, podrías enviar una solicitud al servicio Traductor y recibir una respuesta como viste en la demostración. 

1. Navega por el menú izquierdo. En *Administración de recursos*, seleccione *Claves y puntos de conexión*. Si fueras a crear una aplicación, encontrarías la clave y el punto de conexión aquí. 

## Limpieza

1. Elimina el recurso una vez que hayas terminado de usarlo. 

## Saber más

Para más información sobre lo que puede hacer con este servicio, consulte la [página de Translator](https://learn.microsoft.com/en-us/azure/ai-services/translator/translator-overview).
