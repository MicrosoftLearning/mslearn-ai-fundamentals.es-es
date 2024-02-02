---
lab:
  title: "Uso del reconocimiento del lenguaje conversacional con Language\_Studio"
---

# Uso del reconocimiento del lenguaje conversacional con Language Studio

Cada día, aumentan las expectativas de que los equipos puedan usar la inteligencia artificial para comprender comandos en lenguaje natural, ya sea escritos o hablados. Por ejemplo, es posible que desee que un sistema domótico controle los dispositivos de su casa mediante comandos de voz como "enciende la luz" o "enciende el ventilador". Los dispositivos con tecnología de inteligencia artificial pueden comprender estos comandos y actuar en consecuencia.

En este ejercicio, usará Language Studio para crear y probar un proyecto que envíe instrucciones a dispositivos como luces o ventiladores. Usará las funcionalidades del servicio Reconocimiento del lenguaje conversacional para configurar el proyecto. 

## Creación de un recurso de *Language*

Puede usar muchas características de Lenguaje de Azure AI con un recurso de **Lenguaje** o **servicios de Azure AI**. Hay algunas instancias en las que solo se puede usar un recurso de Lenguaje. Para el siguiente ejercicio, usaremos un recurso de **Lenguaje**. Si aún no lo ha hecho, cree un recurso de **Language** en la suscripción de Azure.

1. En otra pestaña del explorador, abra Azure Portal en [https://portal.azure.com](https://portal.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a la suscripción de Azure.

1. Haga clic en el botón **&#65291;Crear un recurso** y busque *servicio de lenguaje*. Seleccione **Crear** un plan de **servicio de lenguaje**. Se le llevará a una página a *Seleccionar características adicionales**. Mantenga la selección predeterminada y haga clic en **Continuar para crear el recurso**. 

1. En la página **Crear lenguaje**, configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: Este de EE. UU.
    - **Nombre**: *escriba un nombre único*.
    - **Plan de tarifa**: *F0 o S gratis si F0 no está disponible*
    - **Al marcar esta casilla, confirmo haber leído y comprendido todos los términos que aparecen a continuación**: *Seleccionado*.

1. Seleccione **Revisar y crear**, a continuación, **Crear**, y espere a que se complete la implementación.


### Creación de una aplicación de reconocimiento del lenguaje conversacional

Para implementar el reconocimiento del lenguaje natural con el reconocimiento del lenguaje conversacional, se crea una aplicación y luego se agregan entidades, intenciones y expresiones para definir los comandos que quiera que ejecute la aplicación.

1. En una pestaña nueva del explorador, abra el portal de Language Studio en [https://language.azure.com](https://language.azure.com?azure-portal=true) e inicie sesión con la cuenta de Microsoft asociada a su suscripción de Azure.

1. Si se le pide que elija un recurso de Language, seleccione la configuración siguiente:
    - **Directorio de Azure**: *directorio de Azure que contiene la suscripción*.
    - **Suscripción de Azure**: *su suscripción de Azure*.
    - **Recurso de lenguaje**: *el recurso de lenguaje que creó anteriormente.*

   Si ***no*** se le pide que elija un recurso de Language, puede deberse a que tiene varios recursos de Language en la suscripción, en cuyo caso:
    1. En la barra de la parte superior de la página, seleccione **Configuración (&#9881;)**.
    2. En la página **Configuración,** vea la pestaña **Recursos**.
    3. Selecciona el recurso de lenguaje que acabas de crear y selecciona **Cambiar recurso**.
    4. En la parte superior de la página, selecciona **Language Studio** para volver a la página principal de Language Studio.

1. En la parte superior del portal, en el menú **Crear nuevo**, seleccione **Comprensión del lenguaje de conversación**.

1. En el cuadro de diálogo **Crear un proyecto**, en la página **Escribir información básica**, escriba los detalles siguientes y seleccione **Siguiente**:
    - **Nombre**: *cree un nombre único*
    - **Idioma principal de las expresiones**: *Inglés*
    - **Enable multiple languages in project** (Habilitar varios idiomas en el proyecto): *no seleccionar*
    - **Descripción**: `Simple home automation`

    > **Sugerencia**: Anote el *nombre del proyecto y lo usará más adelante*.

1. En la página **Revisar y finalizar**, seleccione **Crear**.

### Creación de intenciones, expresiones y entidades

Una *intención* es una acción que quiere realizar; por ejemplo, encender una luz o apagar un ventilador. En este caso, definirá dos intenciones: una para encender un dispositivo y otra para apagarlo. Para cada intención, especificará *expresiones* de ejemplo que indican el tipo de lenguaje utilizado para indicar la intención.

1. En el panel **Definición de esquema**, asegúrese de que **Intención** esté seleccionado y, luego, seleccione **Agregar**, y agregue una intención con el nombre `switch_on` (en minúsculas) y seleccione **Agregar intención**.

    ![Seleccione Agregar en Intenciones en el panel Compilación de esquema.](media/conversational-language-understanding/build-schema.png)

    ![Agregue la intención switch_on y seleccione Agregar intención.](media/conversational-language-understanding/add-intent.png)

1. Haga clic en la intención **switch_on**. Se le llevará a la página **Etiquetado de datos**. En la lista desplegable **Intención**, seleccione **switch_on**. Junto a la intención **switch_on**, escriba la expresión `turn the light on` y presione **Entrar** para enviar esta expresión a la lista.

    ![Agregue una expresión al conjunto de entrenamiento escribiendo "activar la luz" en Expresión.](media/conversational-language-understanding/add-utterance-on.png)

1. El servicio de lenguaje necesita al menos cinco ejemplos de expresiones diferentes para cada intención a fin de entrenar suficientemente el modelo de lenguaje. Agregue cinco ejemplos más de expresiones para la intención **switch_on**:  
    - `switch on the fan`
    - `put the fan on`
    - `put the light on`
    - `switch on the light`
    - `turn the fan on`

1. En el panel **Labeling entities for training** (Etiquetado de entidades para el entrenamiento) en el lado derecho de la pantalla, seleccione **Etiquetas** y luego **Add entity** (Agregar entidad). Escriba `device` (en minúsculas), seleccione **Lista** y seleccione **Agregar entidad**.

    ![Agregue una entidad, seleccionando Etiquetas en las entidades de etiquetado para el panel de entrenamiento y, a continuación, seleccione Agregar entidad.](media/conversational-language-understanding/add-entity.png)

    ![Escriba el dispositivo en Nombre de entidad y seleccione Lista y, a continuación, seleccione Agregar entidad.](media/conversational-language-understanding/add-entity-device.png)

1. En la expresión ***encender el ventilador***, resalte la palabra "ventilador". A continuación, en la lista que aparece, en el cuadro *Buscar una entidad* seleccione **dispositivo**.

    ![Resalte el ventilador de palabras en la expresión y seleccione dispositivo.](media/conversational-language-understanding/switch-on-entity.png)

1. Haga lo mismo para todas las expresiones. Etiquete el resto de las expresiones de *ventilador* o *luz* con la entidad **dispositivo**. Cuando haya terminado, compruebe que tiene las expresiones siguientes y asegúrese de seleccionar **Guardar cambios**:

    | **intención** | **expresión** | **entidad** |
    | --------------- | ------------------ | ------------------ |
    | switch_on   | Activar el ventilador      | Dispositivo: *seleccionar ventilador* |
    | switch_on   | Activar la luz    | Dispositivo: *seleccionar luz* |
    | switch_on   | Encender la luz | Dispositivo: *seleccionar luz* |
    | switch_on   | Encender el ventilador     | Dispositivo: *seleccionar ventilador* |
    | switch_on   | Encender el ventilador   | Dispositivo: *seleccionar ventilador* |
    | switch_on   | Encender la luz   | Dispositivo: *seleccionar luz* |

    ![Cuando finalice, seleccione Guardar cambios.](media/conversational-language-understanding/save-changes.png) 

1. En el panel de la izquierda, seleccione **Definición de esquema** y compruebe que la intención **switch_on** se muestra ahí. A continuación, seleccione **Agregar** y agregue una nueva intención con el nombre `switch_off` (en minúsculas).

    ![Vuelva a la pantalla Compilar esquema y agregue una intención de switch_off.](media/conversational-language-understanding/add-switch-off.png) 

1. Seleccione la intención **switch_off**. Se le llevará a la página **Etiquetado de datos**. En la lista desplegable **Intención**, seleccione **switch_off**. Junto a la intención **switch_off**, agregue la expresión `turn the light off`.

1. Agregue cinco ejemplos más de expresiones a la intención **switch_off**.
    - `switch off the fan`
    - `put the fan off`
    - `put the light off`
    - `turn off the light`
    - `switch the fan off`

1. Etiquete las palabras *luz* o *ventilador* con la entidad **dispositivo**. Cuando haya terminado, compruebe que tiene las expresiones siguientes y asegúrese de seleccionar **Guardar cambios**:  

    | **intención** | **expresión** | **entidad** | 
    | --------------- | ------------------ | ------------------ |
    | switch_off   | Desactivar el ventilador    | Dispositivo: *seleccionar ventilador* | 
    | switch_off   | Desactivar la luz  | Dispositivo: *seleccionar luz* |
    | switch_off   | Apagar la luz | Dispositivo: *seleccionar luz* |
    | switch_off   | Apagar el ventilador | Dispositivo: *seleccionar ventilador* |
    | switch_off   | Apagar el ventilador | Dispositivo: *seleccionar ventilador* |
    | switch_off   | Apaga la luz | Dispositivo: *seleccionar luz* |

### Entrenamiento del modelo

Ahora está listo para usar las intenciones y entidades que ha definido a fin de entrenar el modelo de lenguaje conversacional de la aplicación.

1. En el lado izquierdo de Language Studio, seleccione **Trabajos de entrenamiento** y, después, **Iniciar un trabajo de entrenamiento**. Use la configuración siguiente:
    - **Entrenar un nuevo modelo**: *debe estar seleccionado y tiene que elegir un nombre de modelo*
    - **Modo de entrenamiento**: Entrenamiento estándar (gratis)
    - **División de datos**: *seleccione Automatically split the testing set from the training data, keep default percentages (Dividir automáticamente el conjunto de pruebas de los datos de entrenamiento, mantener los porcentajes predeterminados)*
    - En la parte inferior de la página, seleccione **Entrenar**.

1. Espere a que se complete el entrenamiento.

### Implementación y prueba del modelo

Para usar el modelo entrenado en una aplicación cliente, debe implementarlo como un punto de conexión al que las aplicaciones cliente puedan enviar nuevas expresiones; a partir de las cuales se predecirán las intenciones y entidades.

1. En el lado izquierdo de Language Studio, seleccione **Implementar un modelo**.

1. Seleccione el nombre del modelo y, luego, haga clic en **Agregar implementación**. Use estos valores de configuración:
    - **Cree o seleccione un nombre de implementación existente**: *seleccione Crear un nuevo nombre de implementación. Agregar un nombre único*
    - **Asigne un modelo entrenado al nombre de la implementación**: *seleccione el nombre del modelo entrenado*.
    - Seleccione **Implementar**.

    > **Sugerencia**: Anote el *nombre de la implementación*, ya que lo usará más adelante. 

1. Cuando se haya implementado el modelo, seleccione **Probar implementaciones** en el lado izquierdo de la página y, después, seleccione el modelo implementado en **Nombre de implementación**.

1. Escriba el texto siguiente y, después, seleccione **Ejecutar la prueba**:

    `switch the light on`

    ![Para probar el modelo, seleccione el modelo implementado y escriba texto y seleccione Ejecutar la prueba.](media/conversational-language-understanding/test-model.png) 

    Revise el resultado que se devuelve y observe que incluye la intención pronosticada (que debe ser **switch_on**) y la entidad pronosticada (**device**) con una puntuación de confianza que indica la probabilidad que el modelo ha calculado para la intención y la entidad pronosticadas. En la pestaña JSON se muestra la confianza comparativa para cada posible intención (la que tiene la puntuación de confianza más alta es la intención pronosticada).

1. Borre el cuadro de texto y pruebe el modelo con las expresiones siguientes en *Enter your own text (Escriba su propio texto)* :
    - `turn off the fan`
    - `put the light on`
    - `put the fan off`

Acaba de configurar correctamente un proyecto de lenguaje conversacional y ha definido entidades, intenciones y expresiones definidas. Ha visto cómo entrenar e implementar un modelo en Language Studio. Y lo ha probado con ambas expresiones que ha definido, y algunas que no había definido de manera explícita, pero que el modelo pudo determinar.

> **NOTA**: El reconocimiento del lenguaje conversacional proporciona la inteligencia para interpretar la intención de la entrada; no realiza ninguna acción como encender la luz o el ventilador. Un desarrollador tendría que compilar una aplicación que use el modelo de Reconocimiento del lenguaje conversacional para determinar la intención del usuario y, después, automatizar la acción adecuada.

## Limpiar

Si no tiene previsto realizar más ejercicios, elimine los recursos que ya no necesite. Esto evita la acumulación de costos innecesarios.

1.Abra [Azure Portal]( https://portal.azure.com) y seleccione el grupo de recursos que contenga el recurso que creó. 1.Seleccione el recurso y **Eliminar** y, después, **Sí** para confirmar. A continuación, se eliminará el recurso.

## Saber más

Esta aplicación solo muestra algunas de las funcionalidades de la característica Conversational Language Understanding del servicio Language. Para obtener más información sobre lo que se puede hacer con este servicio, consulte la [página de reconocimiento del lenguaje conversacional](https://docs.microsoft.com/azure/cognitive-services/language-service/conversational-language-understanding/overview).
