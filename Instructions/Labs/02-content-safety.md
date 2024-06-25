---
lab:
  title: Explorar Servicios de Azure AI
---

# Explorar Servicios de Azure AI

Los servicios de Azure AI ayudan a los usuarios a crear aplicaciones de IA con API y modelos precompilados y personalizables. En este ejercicio, echará un vistazo a uno de los servicios de Content Safety Studio: Seguridad del contenido de Azure AI.

Content Safety Studio permite explorar cómo se puede moderar el contenido de texto e imagen. Puede ejecutar pruebas en texto o imágenes de ejemplo y obtener una puntuación de gravedad que va de "segura" a "alta" para cada categoría. En este ejercicio de laboratorio, creará un recurso de servicio único en Content Safety Studio y probará sus funcionalidades. 

> **Nota** El objetivo de este ejercicio es obtener una idea general de cómo se aprovisionan y usan los servicios de Azure AI. Content Safety se usará como ejemplo, pero no se espera que obtenga un conocimiento completo de la seguridad del contenido en este ejercicio.

## Navegación por Content Safety Studio 

![Captura de pantalla de la página de aterrizaje de Content Safety Studio.](./media/content-safety/content-safety-getting-started.png)

1. Abra [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). Si no ha iniciado sesión, deberá hacerlo. Seleccione **Iniciar sesión** en la parte superior derecha de la pantalla. Use el correo electrónico y la contraseña asociados a la suscripción de Azure para iniciar sesión. 

1. Content Safety Studio está configurado para los servicios de Azure AI, como muchos otros estudios. En el menú de la parte superior de la pantalla, haga clic en el icono de la izquierda de *Azure AI*. Verá una lista desplegable de otros estudios diseñados para el desarrollo con servicios de Azure AI. Puede volver a hacer clic en el icono para ocultar la lista.

![Captura de pantalla del menú de Content Safety Studio con una selección de alternancia abierta para cambiar a otros estudios.](./media/content-safety/studio-toggle-icon.png)  

## Asociación de un recurso a Studio 

Antes de usar Studio, es necesario asociar un recurso de servicios de Azure AI con Studio. Dependiendo de Studio, se podría encontrar con que necesita un recurso de servicio único específico o podría usar un recurso general de varios servicios. En el caso de Content Safety Studio, se puede usar el servicio mediante la creación de un recurso de *Content Safety* de un solo servicio o un recurso general de varios servicios de *Servicios de Azure AI*. En los pasos siguientes, crearemos un recurso Content Safety de un solo servicio. 

1. En la parte superior derecha de la pantalla, haga clic en el icono **Configuración**. 

![Captura de pantalla del icono de Configuración en la parte superior derecha de la pantalla, junto a la campana, el signo de interrogación y los iconos de sonrisa.](./media/content-safety/settings-toggle.png)

2. En la página **Configuración**, verá una pestaña *Directorio* y una pestaña *Recurso*. En la pestaña *Recurso*, seleccione **Crear un nuevo recurso**. Esto le llevará a la página para crear un recurso en Azure Portal.

> **Tenga en cuenta** que la pestaña *Directorio* permite a los usuarios seleccionar directorios diferentes desde los que podrá crear recursos. No es necesario cambiar la configuración a menos que se desee usar otro directorio. 

![Captura de pantalla de dónde seleccionar la creación de un nuevo recurso en la página de configuración de Content Safety Studio.](./media/content-safety/create-new-resource-from-studio.png)

3. En la página *Crear Content Safety* de [Azure Portal](https://portal.azure.com?azure-portal=true), se deben configurar varios detalles para crear el recurso. Configúrelo con los valores siguientes:
    - **Suscripción**: *su suscripción a Azure*.
    - **Grupo de recursos**: *cree o seleccione un grupo de recursos con un nombre único*.
    - **Región**: *Elija cualquier región disponible. Si está en el este de EE. UU., use "Este de EE. UU. 2"*.
    - **Nombre**: *escriba un nombre único*.
    - **Plan de tarifa**: F0 gratis.

4. Seleccione **Revisar y crear** y revise la configuración. Seleccione **Crear**. La pantalla indicará cuándo se ha completado la implementación. 

*¡Felicidades! Acaba de crear o aprovisionar un recurso de servicios de Azure AI. Particularmente, el que ha aprovisionado es un recurso de Content Safety de un solo servicio.*

5. Cuando finalice la implementación, abra una nueva pestaña y vuelva a [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). 

6. Vuelva a seleccionar el icono **Configuración** en la parte superior derecha de la pantalla. Esta vez debería ver que el recurso recién creado se ha agregado a la lista.  

>**Nota**: Si usa una suscripción a Cloud Slice, puede omitir los pasos 7-12 e ir al paso 13. Si no usa ninguna, continúe con el paso 7.

7. Seleccione **Ver todas las propiedades en Azure Portal** en la parte inferior de la pantalla *Configuración*. 

![Captura de pantalla del vínculo Ver todas las propiedades en Azure Portal.](./media/content-safety/view-all-properties.png)

8. En Azure Portal, seleccione el recurso *Content Safety* que acaba de crear. Después, en el panel de la izquierda, seleccione **Control de acceso (IAM)**. A continuación, en el panel abierto, seleccione **Agregar** junto al signo más y seleccione **Agregar asignación de roles**. 

![Captura de pantalla de dónde seleccionar la opción Agregar asignación de roles en el panel Control de acceso.](./media/content-safety/access-control-step-one.png)

9. Busque la opción **Usuario de Cognitive Services** en la lista de roles y selecciónela. Luego, seleccione **Siguiente**. 

10. Use la siguiente configuración para asignar el rol a su propio usuario: 
    - **Asignar acceso a**: seleccione el *usuario, el grupo o la entidad de servicio*.
    - **Miembros**: haga clic en *Seleccionar miembros*.
        - En el panel *Seleccionar miembros* abierto, busque su nombre. Haga clic en el ícono más que hay al lado de su nombre. Después, haga clic en **Seleccionar**.
    - **Descripción**: *déjela en blanco*

11. Seleccione **Revisar y asignar** y, a continuación, seleccione **Revisar y asignar** de nuevo para agregar la asignación de roles.    

12. Vuelva a Content Safety Studio en [https://contentsafety.cognitive.azure.com](https://contentsafety.cognitive.azure.com). Después, seleccione el icono **Configuración** de la parte superior derecha de la pantalla. 

![Captura de pantalla del icono de Configuración en la parte superior derecha de la pantalla, junto a la campana, el signo de interrogación y los iconos de sonrisa.](./media/content-safety/settings-toggle.png)
 
13. Seleccione el recurso del servicio de Azure AI que acaba de crear. Asegúrese de que en *Asignaciones de roles actuales* vea tanto *Usuario de Cognitive Services* como *propietario*.

![Captura de pantalla de las asignaciones de roles actuales.](./media/content-safety/access-control-check-step.png)

14. Haga clic en **Usar recurso** en la parte inferior de la pantalla. Volverá a la página principal de Studio. Ya se puede empezar a usar Studio con el recurso recién creado.

## Probar la moderación de texto en Content Safety Studio

1. En la página principal de Content Safety Studio, en *Ejecutar pruebas de moderación*, vaya al cuadro **Moderar contenido de texto**  y haga clic en **Probar**.
1. En Ejecutar una prueba sencilla, haga clic en **Contenido seguro**. Observe que el texto guardado se muestra en la lista a continuación. 
1. Haga clic en **Ejecutar prueba**. La ejecución de una prueba llama al modelo de aprendizaje profundo de Content Safety Service. El modelo de aprendizaje profundo ya se ha entrenado para reconocer contenido no seguro.
1. En el panel *Resultados*, inspeccione los resultados. Hay cuatro niveles de gravedad que van de "segura" a "alta" y cuatro tipos de contenido dañino. ¿El servicio de inteligencia artificial de Seguridad del contenido considera que este ejemplo es aceptable o no? Lo que es importante tener en cuenta es que los resultados están dentro de un intervalo de confianza. Un modelo bien entrenado, como uno de los modelos estándar de Azure AI, puede devolver resultados que tengan una alta probabilidad de coincidir con los resultados de etiquetas aplicadas por humanos. Cada vez que ejecute una prueba, vuelva a llamar al modelo. 
1. Ahora pruebe otro ejemplo. Seleccione el texto de Contenido violento con errores ortográficos. Compruebe que el contenido aparece en el cuadro siguiente.
1. Haga clic en **Ejecutar prueba** y vuelva a inspeccionar los resultados en el panel de resultados. 

Puede ejecutar pruebas en todos los ejemplos proporcionados y, a continuación, inspeccionar los resultados.

## Restaurar las claves y el punto de conexión

Estas funcionalidades que ha probado se pueden programar en todo tipo de aplicaciones. Las claves y el punto de conexión que se usan para el desarrollo de aplicaciones se pueden encontrar tanto en Content Safety Studio como en Azure Portal. 

1. En Content Safety Studio, vuelva a la página **Configuración** con la pestaña *Recursos* seleccionada. Busque el recurso que usó. Desplácese por ahí para ver el punto de conexión y la clave del recurso. 
1. En Azure Portal, verá que se trata del *mismo* punto de conexión y de claves *diferentes* para el recurso. Para comprobarlo, vaya a [Azure Portal](https://portal.azure.com?auzre-portal=true). Busque *Content Safety* en la barra de búsqueda superior. Encuentre el recurso y haga clic en él. En el menú de la izquierda, busque en *Administración de recursos* para encontrar *Claves y puntos de conexión*. Seleccione **Claves y puntos de conexión** para ver el punto de conexión y las claves del recurso. 

Una vez que haya terminado, se puede eliminar el recurso Content Safety de Azure Portal. Eliminar el recurso es una manera de reducir los costes que se acumulan cuando el recurso existe en la suscripción. Para ello, vaya a la página **Información general** del recurso Content Safety. En la parte superior de la pantalla, seleccione **Eliminar**.

