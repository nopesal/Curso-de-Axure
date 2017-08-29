# Apuntes del curso de Axure

## El programa
- En Axure todo funciona con widgets.
- Existen varias librerías de widgets, pinchas y arrastras al lienzo.
- Para insertar una imagen se usa Image, no Placeholder.
- El **Inspector** es lo que sirve para cambiar el estilo de los elementos, y cuando no hay nada seleccionado se cambia el estilo del propio lienzo.
- En el panel **Outline** aparecen los widgets del lienzo, son como las capas del Photoshop. Como consejo, conviene nombrar los elementos que aparecen aquí, por ejemplo, *h1_formulario*.
- En el panel **Masters** se pueden ver elementos guardados para reutilizarlos cuando se necesite, a modo de Símbolos.

## Ejercicio de formulario
- El **Submit Button** sirve para desencadenar una validación de un formulario, por ejemplo. Se deben enlazar el resto de elementos al submit en la pestaña de Properties.

## Ejercicio de botones
- Al crear un elemento y personalizarlo se puede guardar el estilo que tiene para aplicarlo posteriormente a otros elementos.
- En el ejercicio, al guardar el estilo, las dimensiones del botón no quedan guardadas. Como apaño, se han ajustado los paddings del botón con el texto, de forma que al crear un nuevo botón y ajustar el tamaño de la caja al texto, el padding hará que tena el tamaño que tenga que tener.
- Para un *hover* y un *click*, lo conveniente es crear cada estilo por separado, y luego, en el botón con el estilo original, vas a la pestaña Properties, y en **Interaction Styles** se puede cambiar el estilo para cada interacción.

## Ejercicio de tooltips
- Se pueden importar librerías para utilizar sus componentes en el proyecto. Se pueden descargar desde la página oficial de Axure. Se descarga y se cargan una vez descargadas haciendo clic en el icono de *hamburger* del panel **Libraries**.
- Se pueden ocultar elementos durante la edición desde el panel *Outline*, pero para ocultar elementos en la interacción se usa el atributo **Hidden**, disponible en la pestaña Properties.
- Una **interacción** se compone por un evento (el desencadenante), casos (el contexto) y un efecto. Ver este enlace https://www.axure.com/support/reference/interactions para la lista de eventos de interacción.
- Para definir una interacción, en la pestaña de Properties están listados los eventos por defecto y pueden añadirse más. En la ventana emergente, se selecciona la acción, el objeto y los elementos que lo componen (pueden ocultarse grupos enteros o no, por ejemplo).
- Utilizando **hotspots** se pueden crear zonas pulsables del tamaño necesario.

## Ejercicio de ventana modal
- Para crear una ventana modal, se puede especificar un las opciones de la animación del evento onClick, **treat as lightbox**, que lo que hace es mostrar la ventana modal con el fondo oscuro, pudiendo incluso modificar el color del fondo.
- Para cerrar la ventana modal, con un aspa por ejemplo, se indica en la animación que se oculte el grupo de la ventana modal simplemente.

## Ejercicio de paneles dinámicos
- Un **panel dinámico** es un elemento que cambia de estado tras una interacción, cuyos estados son como capas superpuestas en el mismo espacio, de forma que se ve la capa que más al frente esté ubicada.
- Para crear un panel dinámico se hace clic derecho sobre un elemento y se selecciona *Convert to Dynamic Panel*.
- Cada panel dinámico tiene un contenido y se abre en una página de Axure aparte. Es **importante** que los elementos estén ubicados en el origen de los ejes de coordenadas (x=0, y=0).
- En la configuración del evento se debe selecciona *Set Panel State* como la acción a realizar por la interacción. Indicando *Next* irá de panel en panel sin rotar. Para crear un bucle debe seleccionarse *Wrap from last to first*.

## Ejercicio del switch y pestañas
- Hay que intentar que los paneles dinámicos tengan el mismo alto y ancho que el contenido que incluyen.
- Para hacer un switch (interruptor), se crea un panel dinámico con dos estados (ON/OFF), de forma que cuando se haga clic en uno, se cambie el estado del panel al estado correspondiente.
- El estado de un panel dinámico puede cambiarse al siguiente (con *Next*), o asignarle directamente un estado en concreto.
- Para hacer pestañas, se crea un panel dinámico con tantos estados como pestañas haya, de forma que las pestañas cambien el estado del panel al que corresponda. Se debería poner un estilo seleccionado a las pestañas al hacer clic en ellas, es decir, al asignar un estilo *Selected*, pero este estilo no se verá a menos que el elemento esté seleccionado. Para que el elemento quede seleccionado, hay que asignar una acción en *onClick* para activar o desactivar el atributo *Selected*. Además, hay que indicar a Axure que sólo una de las pestañas puede estar seleccionada a la vez. Para ello se configura el atributo *Selection Group* de cada pestaña.
- Si se desea mostrar como seleccionada una pestaña por defecto, el evento *onPageLoad* activa acciones al cargar la página, pudiendo activar el atributo *Selected*. Si no, es más sencillo activar a mano el atributo en *Properties* del elemento.
- Para copiar el estilo de un elemento a otros elementos, se usa la herramienta **Painter**, ubicada en el menú *More* en la barra de herramientas superior. Es posible copiar además los estilos que tiene los *MouseOver* y *Selected*.  
- Para animar el contenido de las pestañas, por ejemplo, un deslizamiento lateral, se puede configurar en las opciones del evento *onClick* al cambiar el panel dinámico de estado.
