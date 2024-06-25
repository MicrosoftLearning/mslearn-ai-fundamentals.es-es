---
lab:
  title: "Explorar Copilot en Microsoft\_Edge"
---
# Explorar Microsoft Copilot en Microsoft Edge

En este ejercicio, explorará algunas de las formas en que Microsoft Copilot puede usar la IA generativa para ayudarle a ser más productivo al crear contenido nuevo. En el escenario de este ejercicio, empezará con algunas notas de alto nivel para una idea empresarial y usará Copilot en Microsoft Edge para ayudarle a desarrollar un plan de negocio y una presentación para posibles inversores.

Este ejercicio debería tardar en completarse **40** minutos aproximadamente.

> **Nota**: En este ejercicio, se supone que tiene una [cuenta de Microsoft personal](https://signup.live.com) (por ejemplo, una cuenta de outlook.com) con la que ha iniciado sesión en [Microsoft Edge](https://www.microsoft.com/edge/download) en el equipo.

## Uso de Copilot para explorar un documento e investigar una idea

Para iniciar la exploración de la IA generativa, vamos a usar Microsoft Copilot en Edge para examinar un documento existente y extraer información de ella.

1. En Microsoft Edge, vaya a [OneDrive](https://onedrive.live.com) en `https://onedrive.live.com` e inicie sesión con su cuenta de Microsoft personal. Una vez ahí, cierre los mensajes de bienvenida o las ofertas que se muestran.
1. En otra pestaña del explorador, abra el documento [Business Idea.docx](https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx) desde `https://github.com/MicrosoftLearning/mslearn-ai-fundamentals/raw/main/data/generative-ai/Business%20Idea.docx`. A continuación, cuando el documento se abra en Edge, seleccione la opción **Guardar una copia en OneDrive** y guarde el documento en la carpeta **Documentos** de OneDrive. A continuación, el documento debe abrirse automáticamente en Microsoft Word Online.

    > **Sugerencia**: Si no ve la opción de guardar una copia del archivo en OneDrive, descárguelo en el equipo local. A continuación, en OneDrive, abra la carpeta **Documentos** y use el botón **+ Agregar nuevo** para cargar el archivo **Business Idea.docx** desde el equipo local a OneDrive.

1. Vea el texto de **Business Idea.docx**, que describe algunas ideas de alto nivel para un negocio de limpieza en la ciudad de Nueva York.
1. Use el icono de **Copilot** en la barra de herramientas de Edge para abrir el panel Copilot, como se muestra aquí:

    ![Captura de pantalla del panel Copilot en Microsoft Edge.](./media/generative-ai/edge-copilot.png)

1. En el panel Copilot, desplácese hacia abajo para ver todo el contenido según sea necesario y asegúrese de que la pestaña **Chat** esté seleccionada y de que el estilo conversacional esté establecido en **Más equilibrado**, lo que garantizará que Copilot responda con un equilibrio de creatividad y precisión fáctica.
1. En el cuadro de chat de la parte inferior del panel Copilot, escriba la siguiente indicación:

    ```
    What is this document about?
    ```

    Si se le solicita, confirme que desea permitir que Copilot acceda a la página.

1. Revise la respuesta de Copilot, que debe resumir los puntos principales del documento, como se muestra aquí:

    ![Captura de pantalla del panel Copilot con una respuesta.](./media/generative-ai/copilot-response.png)

    > **Nota**: La respuesta específica puede variar.

1. Escriba lo siguiente:

    ```
    How do I go about setting up a business in New York?
    ```

1. Revise la respuesta, que debe contener algunos consejos y vínculos a recursos para ayudarle a empezar a establecer una empresa en Nueva York, y puede incluir algunas indicaciones de seguimiento sugeridas para obtener más información.

    > **Importante**: La respuesta generada por IA se basa en la información pública en la Web. Aunque puede ser útil ayudarle a comprender los pasos necesarios para establecer un negocio, no se garantiza que sea 100 % preciso. No reemplace la necesidad de asesoramiento profesional.

## Uso de Copilot para crear contenido para un plan de negocio

Ahora que ha realizado algunas investigaciones iniciales, vamos a que Copilot le ayude a desarrollar un plan de negocio para su empresa de limpieza.

1. Con el documento **Business Idea.docx** abierto en Microsoft Edge, en el panel Copilot, escriba la siguiente indicación:

    ```
    Suggest a name for my cleaning business
    ```

1. Revise las sugerencias y seleccione un nombre para su empresa de limpieza (o continúe enviando indicaciones hasta encontrar un nombre que desee).
1. Escriba la siguiente indicación y reemplace *Contoso Cleaning* por el nombre de la empresa de su elección:

    ```
    Write a business plan for "Contoso Cleaning" based on the information in this document. Include an executive summary, market overview, and financial projections.
    ```

1. Revise la respuesta y, en la salida, use el icono **Copiar** (&#128461;) para copiarlo en el Portapapeles. A continuación, seleccione todo el texto del documento **Business Ideas.docx** y pegue el texto copiado en el documento para reemplazarlo. Por último, ordene el texto pegado reemplazando el texto inicial en la respuesta (en el que Copilot reconoció la instrucción) por un encabezado para el nombre de la empresa de limpieza. Debería terminar con un documento de plan de negocio, similar al siguiente:

    ![Captura de pantalla de un documento de Word con un plan de negocio generado por Copilot.](./media/generative-ai/generated-content.png)

1. En el panel Copilot, escriba la indicación siguiente:

    ```
    Create a corporate logo for the cleaning company. The logo should be round and include an iconic New York landmark.
    ```

1. Revise la respuesta, que debe presentar cuatro opciones para un logotipo creado por Microsoft Designer.
1. Use más indicaciones para iterar en el diseño (por ejemplo, `Make it green and blue`) hasta que tenga un logotipo con el que esté satisfecho.
1. Haga clic con el botón derecho en el diseño del logotipo que prefiera y cópielo en el Portapapeles. Después, péguelo en la parte superior del documento del plan de negocio, de la siguiente manera:

    ![Captura de pantalla de un documento de Word con una imagen generada por Copilot.](./media/generative-ai/generated-image.png)

1. Cierre la pestaña Microsoft Word y vuelva a la carpeta **Documentos** de OneDrive.

## Uso de Copilot para crear contenido para una presentación

Con la ayuda de Copilot, ha creado un borrador de un plan de negocio para la idea de un negocio de limpieza. Ahora necesitará una presentación eficaz para convencer a un inversor de prestarle la financiación para iniciar el negocio.

1. En la carpeta **Documentos** de OneDrive, agregue una nueva **presentación de PowerPoint**.

    Si el panel**Designer** se abre automáticamente, ciérrelo.

1. En la diapositiva de título de la presentación, escriba el nombre de la empresa de limpieza como título y `Investor Opportunity` como subtítulo.
1. Agregue una nueva diapositiva con el diseño de diapositiva **Dos contenidos** (que incluye un título y dos marcadores de posición para el contenido).
1. Cambie el título de la diapositiva a `Benefits of Hiring a Commercial Cleaner`.
1. En el panel Copilot, escriba la indicación siguiente:

    ```
    Write a summary of the benefits of using a corporate cleaning company for your business. The summary should consist of five short bullet points.
    ```

1. Copie la respuesta de Copilot al Portapapeles y péguela en el marcador de posición de contenido izquierdo. A continuación, elimine la oración inicial que reconoce la solicitud y vuelva a aplicar formato al texto en el marcador de posición hasta que esté satisfecho.
1. En el panel Copilot, escriba la indicación siguiente:

    ```
    Create a photorealistic image of a clean office.
    ```

1. Cuando Copilot haya generado una imagen que le guste, cópiela en el Portapapeles y péguela en el marcador de posición de contenido de la derecha de la diapositiva.

    Si el panel **Designer** se abre automáticamente, seleccione un diseño de diapositivas que desee. A continuación, cierre el panel **Designer**.

1. Aplique cualquier nuevo formato adicional que considere necesario hasta que tenga una diapositiva similar a esta:

    ![Captura de pantalla de una presentación de PowerPoint con contenido generado por Copilot.](./media/generative-ai/powerpoint-slide.png)

1. En la barra de título de PowerPoint, seleccione el nombre de presentación predeterminado (**Presentación**) y cámbielo a `Business Presentation.pptx`.
1. Cierre la pestaña PowerPoint y vuelva a la carpeta **Documentos** de OneDrive.

## Uso de Copilot para redactar un correo electrónico

Ha creado algunas garantías para ayudarle a empezar a trabajar con su negocio. Ahora es el momento de comunicarse con un inversor que busque financiar alguna startup.

1. Use el **Iniciador de aplicaciones** en el extremo izquierdo de la barra de título de OneDrive para abrir **Outlook**.
1. Cree un nuevo correo electrónico y rellene el cuadro **Para** con su propia dirección de correo electrónico.
1. En el panel Copilot, seleccione la pestaña **Redactar**. A continuación, establezca las siguientes opciones para crear contenido nuevo:
    - **Escribe sobre**: `Request a meeting with an investment bank to discuss funding for a commercial cleaning business.`
    - **Tono**: Profesional
    - **Format**: Email
    - **Longitud**: Mediana
1. Seleccione **Generar borrador** y revise la salida generada.
1. Use el contenido generado para completar el correo electrónico, como se muestra aquí:

    ![Captura de pantalla de un mensaje de correo electrónico generado por Copilot.](./media/generative-ai/generated-email.png)

    Puede enviarse el correo electrónico a sí mismo si lo desea.

## Desafío

Ahora ha visto cómo usar Copilot para investigar ideas y generar contenido, ¿por qué no intentar explorar más? Para iniciar una nueva sesión de Copilot, en la pestaña **Chat**, seleccione el icono **Nuevo tema** situado junto al cuadro de indicaciones y, a continuación, intente usar Copilot para planear un evento para promover la alfabetización infantil en una biblioteca local. Algunas cosas que podría probar incluyen:

- Investiga algunas sugerencias para animar a los niños a leer a una edad temprana.
- Crea un folleto o póster para el evento.
- Redacta un correo electrónico para una campaña para invitar a los autores locales de contenido para niños a asistir y hablar en el evento.
- Crea una presentación para iniciar el evento.

Use su imaginación como guste y explore cómo Copilot puede ayudarle a encontrar información, generar y refinar texto, crear imágenes y responder preguntas.


## Conclusión

En este ejercicio, ha usado Copilot en Microsoft Edge para buscar información y generar contenido. Esperamos que haya visto cómo usar la IA generativa en un copiloto puede ayudar con la productividad y la creatividad.

Aunque los servicios gratuitos usados en estos ejercicios son sin duda muy eficaces, puede lograr aún más con servicios como [Copilot para Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/copilot-for-microsoft-365), en el que Microsoft Copilot se integra en las aplicaciones de productividad de Windows y Microsoft Office, proporcionando ayuda muy contextualizada con tareas comunes. Microsoft 365 le permite aportar la eficacia de la IA generativa a los datos y procesos empresariales, al tiempo que se integra en la infraestructura de TI existente para garantizar una solución fácil de administrar y proteger.