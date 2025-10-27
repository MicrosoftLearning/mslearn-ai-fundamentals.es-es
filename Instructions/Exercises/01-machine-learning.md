---
lab:
  title: Exploración del aprendizaje automático automatizado
---

# Exploración del aprendizaje automático automatizado

En este ejercicio, usará el aprendizaje automático automatizado para entrenar y evaluar un modelo de aprendizaje automático. Después, implementará y probará el modelo entrenado.

> **Nota**: Este ejercicio está diseñado para enseñarle los pasos que debe realizar para entrenar y probar un modelo mediante***Azure Machine Learning***. Si tiene una suscripción a Azure con permisos suficientes, puede aprovisionar un área de trabajo de Azure Machine Learning y usarla en el ejercicio. Sin embargo, Azure Machine Learning está diseñado para soluciones de aprendizaje automático de escala empresarial en las que intervienen grandes volúmenes de datos y proceso basado en la nube. Algunas operaciones de Azure Machine Learning requieren aprovisionar el proceso, lo que puede tardar mucho tiempo. Si no tiene acceso a Azure o si tiene que completar el ejercicio en un tiempo determinado, también se proporciona una aplicación***ML Lab*** basada en el explorador. Esta aplicación incluye la funcionalidad principal de Azure ML que se usa en este ejercicio y puede usarla para entrenar y probar modelos de aprendizaje automático reales, como lo haría en Azure ML. Aunque la interfaz de usuario de ML Lab no es*idéntica* a Azure Machine Learning, es lo suficientemente similar como para hacer que la transición a Azure Machine Learning sea intuitiva. Tenga en cuenta que la aplicación ML Lab se ejecuta en el explorador, por lo que si actualiza la página en cualquier momento se reiniciará la aplicación.

Este ejercicio se realiza normalmente en**35** minutos (menos si usa la aplicación ML Lab basada en el explorador).

## Creación de un área de trabajo

Un área de trabajo se usa para mantener todos los recursos de aprendizaje automático juntos, lo que facilita la administración de los datos, el código, los modelos y otros recursos en un solo lugar.

1. Abra el portal para el entorno que desea usar en este laboratorio e inicie sesión si se le solicita:
    - [Estudio de Azure Machine Learning](https://ml.azure.com){:target="_blank"} basado en Azure en`https://ml.azure.com`
    - [ML Lab](https://aka.ms/ml-lab){:target="_blank"} basado en el explorador en`https://aka.ms/ml-lab`

    > **Sugerencia**: Si Estudio de Azure Machine Learning se abre en un área de trabajo existente, vaya a la página**Todas las áreas de trabajo**.

1. Cree una nueva área de trabajo con un nombre adecuado.

    Si usa Azure Machine Learning, no necesita un*centro* para este ejercicio. Elija la configuración avanzada adecuada en función de las restricciones de directiva de la suscripción de Azure.

1. Una vez creada el área de trabajo, selecciónela para ver su página**principal**.

    Tenga en cuenta que el área de trabajo tiene varias páginas, que se muestran en el panel de navegación de la izquierda. Puede expandir y contraer este panel mediante el menú **&#9776;** de la parte superior.

## Descargar datos

En este ejercicio, usará un conjunto de datos de ventas de helados para entrenar un modelo que prediga la demanda de helados en un día determinado, en función de las características estacionales y meteorológicas.

1. En una nueva pestaña del explorador, descargue**[ml-data.zip](https://aka.ms/mslearn-ml-data)** de`https://aka.ms/mslearn-ml-data` a su equipo local.
1. Extraiga el archivo**ml-data.zip** descargado para ver los archivos que contiene. Tenga en cuenta que uno de estos archivos es**ice-cream.csv**, que contiene los datos de ventas de helados necesarios para este ejercicio.

## Uso del aprendizaje automático automatizado para entrenar un modelo

El aprendizaje automático automatizado le permite probar varios algoritmos y parámetros para entrenar varios modelos e identificar el que se ajusta mejor a sus datos.

1. En el portal, vea la página**ML automatizado** (en**Creación**).

1. Cree un nuevo trabajo de ML automatizado con la siguiente configuración, usando**Siguiente** cuando sea necesario para avanzar por la interfaz de usuario:

    > **Sugerencia**: Si no se proporciona información explícita para una configuración en los pasos siguientes, use el valor predeterminado.

    **Configuración básica**:

    - Asigne un**nombre de trabajo** único para el trabajo de aprendizaje automático automatizado

   **Tipo de tarea y datos**:

    - Establezca el tipo de tarea en**Regresión**.
    - Cree un nuevo recurso de datos***tabulares*** denominado**ice-cream**.
        - Cargue el archivo**ice-cream.csv** local en el almacenamiento del área de trabajo predeterminada.
        - Incluya<u>solo</u> las columnas siguientes (*Date* es única para cada fila y agrega funcionalidad predictiva por sí sola):
            - **DayOfWeek**
            - **Month**
            - **Temperatura**
            - **Rainfall**
            - **IceCreamsSold**
        - Cree el recurso de datos.
    - Asegúrese de que el recurso de datos**ice-cream** recién creado está seleccionado antes de pasar al paso siguiente.

    > **Nota**: Si va a usar una suscripción de Azure para la que no es administrador, es posible que la directiva no haya permitido el acceso basado en claves al almacenamiento. En este caso, deberá trabajar con el administrador para permitir el acceso basado en claves o volver a configurar el área de trabajo de Azure Machine Learning para usar la autenticación de Entra ID para acceder al almacenamiento. Si no puede hacerlo, use la aplicación***ML Lab*** basada en el explorador para este ejercicio.

    **Configuración de la tarea**:

    - Establezca la**columna de destino** (la etiqueta que queremos que el modelo prediga) en**IceCreamsSold**.
    - Establezca**Opciones de configuración adicionales**:
        - Establezca la**métrica Principal** en la métrica que desea usar para evaluar el rendimiento del modelo. En este ejercicio, use la puntuación de*R<sup>2</sup>*.
        - Seleccione los algoritmos del modelo que desea probar (o déjelos todos seleccionados).
    - Establezca la**configuración de ingeniería de características**:
        - use esta configuración para personalizar la ingeniería de características (cómo se preparan las características de datos para el entrenamiento del modelo)
    - Establezca**Límites**:
        - use los límites para finalizar el trabajo de entrenamiento al principio en función de criterios específicos. En este ejercicio, establezca los límites siguientes:
            - **Umbral de puntuación de métrica**: 0,9
            - **Tiempo de espera del experimento (minutos)**: 15
        
        > **Nota** Es importante establecer estos límites al usar Azure Machine Learning, ya que la ejecución de trabajos de entrenamiento para cada posible algoritmo y combinación de ingeniería de características podría tardar horas.

    **Proceso:**

    - Usar el proceso**sin servidor**

    **Revisar**

    - Revise la configuración y compruébela cuidadosamente. A continuación, envíe el trabajo de entrenamiento. Se inicia automáticamente.

1. espere a que el trabajo finalice.

    > **Sugerencia**: Si usa Azure Machine Learning, es posible que tarde un rato; ahora podría ser un buen momento para hacer una pausa.

## Revisión del mejor modelo

Una vez completado el trabajo de aprendizaje automático automatizado, puede revisar el mejor modelo que haya entrenado.

1. En la pestaña**Información general** de la página de detalles del trabajo, vea la información sobre el trabajo y anote el mejor resumen del modelo.
  
1. Seleccione el**Nombre del algoritmo** para el mejor modelo a fin de ver sus detalles. A continuación, en la página de detalles del trabajo secundario, vea las pestañas siguientes:
    - **Información general**: Detalles generales del trabajo secundario.
    - **Modelo**: Información sobre el modelo que se entrenó.
    - **Métricas**: métricas de evaluación y visualizaciones para el modelo en función de los datos de prueba utilizados durante el proceso de entrenamiento.
    - **Salidas y registros**: información registrada durante el proceso de entrenamiento.

## Implementación y prueba del modelo

1. En la pestaña**Modelo** del mejor modelo entrenado por el trabajo de aprendizaje automático automatizado, seleccione**Implementar** para implementar el modelo en un punto de conexión en tiempo real.

    Seleccione las opciones**Instancias** y**Máquina virtual** adecuadas para el proceso en el que se ejecutará el punto de conexión implementado (que puede depender de la cuota disponible en la suscripción de Azure) y asigne los nombres de**punto de conexión** e**implementación** adecuados.

1. Espere a que aparezca una notificación de que se ha completado la implementación.

    > **Sugerencia**: En Estudio de Azure Machine Learning, la implementación de puntos de conexión puede tardar entre 5 y 10 minutos.

## Prueba del modelo implementado

Ahora puede probar el servicio implementado.

1. En el menú de navegación, seleccione la página**Puntos de conexión** y abra el punto de conexión en tiempo real que creó.

1. En la página del punto de conexión, vea la pestaña**Prueba**.

1. En el**panel de datos de entrada para evaluar el punto de conexión**, reemplace la plantilla JSON por los datos de entrada siguientes:

    ```json
   {
     "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
   }
    ```

1. Haga clic en el botón**Probar**.

1. Revise los resultados de la prueba, que incluyen un número previsto de alquileres en función de las características de entrada similar a lo siguiente:

    ```JSON
   [
       120.16208168753236
   ]
    ```

    El panel de prueba tomó los datos de entrada y utilizó el modelo entrenado para devolver el número de alquileres previsto.

## Visualización del código para consumir el modelo

Ahora que tiene un modelo predictivo, los desarrolladores pueden crear aplicaciones que lo consuman.

1. En la página punto de conexión en tiempo real, vea la pestaña**Consumir**.
1. Revise el código de ejemplo para consumir el modelo.

## Si el tiempo lo permite

Si desea experimentar más con el aprendizaje automático automatizado, pruebe a entrenar un modelo de**clasificación** basado en el archivo**penguins.csv** que se incluyó en el archivo de**ml-data.zip** que descargó anteriormente. Use todas las columnas de este conjunto de datos.

Después de entrenar e implementar un modelo de clasificación, puede probarlo en el punto de conexión con el siguiente código JSON:

```json
{
    "input_data": {
    "columns": [
        "CulmenLength",
        "CulmenDepth",
        "FlipperLength",
        "BodyMass"
    ],
    "index": [0],
    "data": [[45.2,13.8,215,4750]]
    }
}
```

## Limpieza

Si ha usado Azure Machine Learning para completar este ejercicio, debe eliminar los recursos que ha creado para evitar el uso innecesario de Azure.

1. En[Estudio de Azure Machine Learning](https://ml.azure.com), en la pestaña**Puntos de conexión**, seleccione el punto de conexión que ha implementado. A continuación, seleccione**Eliminar** y confirme que quiere eliminar el punto de conexión.

    Eliminar el proceso garantiza que no se cobren los recursos de proceso en la suscripción. Sin embargo, se le cobrará un importe reducido por el almacenamiento de datos, siempre que el área de trabajo de Azure Machine Learning exista en la suscripción. Si ha terminado de explorar Azure Machine Learning, puede eliminar el área de trabajo de Azure Machine Learning y los recursos asociados.

Para eliminar el área de trabajo:

1. En[Azure Portal](https://portal.azure.com), en la página**Grupos de recursos**, abra el grupo de recursos que haya especificado al crear el área de trabajo de Azure Machine Learning.
2. Haga clic en**Eliminar grupo de recursos**, escriba el nombre del grupo de recursos para confirmar que quiere eliminarlo y seleccione**Eliminar**.
