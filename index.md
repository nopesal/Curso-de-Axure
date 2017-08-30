# Apuntes del curso de Axure
Estos son apuntes de un curso de Axure RP 8. Ha sido un curso práctico, por lo que los apuntes están divididos en ejercicios, los cuales pueden verse en el archivo *Ejercicio Axure.rp* ubicado en este repositorio.

## El programa
- En Axure todo funciona con widgets.
- Existen varias librerías de widgets, pinchas y arrastras al lienzo.
- Para insertar una imagen se usa Image, no Placeholder.
- El **Inspector** es lo que sirve para cambiar el estilo de los elementos, y cuando no hay nada seleccionado se cambia el estilo del propio lienzo.
- En el panel **Outline** aparecen los widgets del lienzo, son como las capas del Photoshop. Como consejo, conviene nombrar los elementos que aparecen aquí, por ejemplo, *h1_formulario*.
- En el panel **Masters** se pueden ver elementos guardados para reutilizarlos cuando se necesite, a modo de Símbolos. Un cambio en un elemento Maestro afecta a todos las copias de ese elemento maestro del proyecto.

## Ejercicio de formulario
- El **Submit Button** sirve para desencadenar una validación de un formulario, por ejemplo. Se deben enlazar el resto de elementos al submit en la pestaña de Properties.

## Ejercicio de botones
- Al crear un elemento y personalizarlo se puede guardar el estilo que tiene para aplicarlo posteriormente a otros elementos.
- En el ejercicio, al guardar el estilo, las dimensiones del botón no quedan guardadas. Como apaño, se han ajustado los paddings del botón con el texto, de forma que al crear un nuevo botón y ajustar el tamaño de la caja al texto, el padding hará que tena el tamaño que tenga que tener.
- Para un *hover* y un *click*, lo conveniente es crear cada estilo por separado, y luego, en el botón con el estilo original, vas a la pestaña Properties, y en **Interaction Styles** se puede cambiar el estilo para cada interacción.

## Ejercicio de tooltips
- Se pueden importar librerías para utilizar sus componentes en el proyecto. Se pueden descargar desde la página oficial de Axure. Se descarga y se cargan una vez descargadas haciendo clic en el icono de *hamburger* del panel **Libraries**.
- Se pueden ocultar elementos durante la edición desde el panel *Outline*, pero para ocultar elementos en la interacción se usa el atributo **Hidden**, disponible en la pestaña Properties.
> Una **interacción** se compone por un evento (el desencadenante), casos (el contexto) y un efecto. Ver [Lista de eventos de interacción](https://www.axure.com/support/reference/interactions) para la lista de eventos de interacción.

- Para definir una interacción, en la pestaña de *Properties* están listados los eventos por defecto y pueden añadirse más. En la ventana emergente, se selecciona la acción, el objeto y los elementos que lo componen (pueden ocultarse grupos enteros o no, por ejemplo).
- Utilizando **hotspots** se pueden crear zonas pulsables del tamaño necesario.

## Ejercicio de ventana modal
- Para crear una ventana modal, se puede especificar en las opciones de la animación del evento onClick, **treat as lightbox**, que lo que hace es mostrar la ventana modal con el fondo oscuro, pudiendo incluso modificar el color del fondo.
- Para cerrar la ventana modal, con un aspa por ejemplo, se indica en la animación que se oculte el grupo de la ventana modal simplemente.

## Ejercicio de paneles dinámicos
> Un **panel dinámico** es un elemento que cambia de estado tras una interacción, cuyos estados son como capas superpuestas en el mismo espacio, de forma que se ve la capa que más al frente esté ubicada.

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

## Ejercicio de colapsables
- Si se disponen de varios elementos con un estilo hover pero se quiere que el hover de todos los elementos reaccionen a la vez, se agrupan y se activa el atributo del grupo **Trigger Mouse Interaction Styles**.
- Si se disponen de varios colapsables apilados, al expandirlos taparán los que estén ubicados por debajo. Existe una opción en la configuración del evento de interacción del panel dinámico llamada **Push/Pull Widgets**, que empuja los elementos que ocupen el espacio del panel dinámico.

## Ejercicio de sitemap
- Existe una librería incluida por defecto llamada **Flow**, la cual permite dibujar diagramas de flujo, los cuales son muy útiles a la hora de documentar los prototipos, con la posibilidad de enlazar a las páginas creadas.
- Hay que indicar que la página es de tipo *Flow*, haciendo clic derecho sobre ella en el panel *Pages* y seleccionando *Dyagram Type*.
- Para dibujar el diagrama de flujo, se insertan elementos de la librería en el lienzo y se conectan con la herramienta **Connect** ubicada en la barra de herramientas superior.
- Se puede utilizar el atributo *Reference Page* de los elementos del diagrama para referenciar las páginas que se correspondan con el árbol.
- Para llevar a otra página al ocurrir un evento, se utiliza la acción **Open Link**.
- Para crear un elemento permanente en cuanto a su posición en la página, por ejemplo una cabecera, es necesario convertir el elemento en un panel dinámico. Después, se configura el atributo **Pin to Browser** para especificar la ubicacion deseada del elemento. Si se convierte el elemento en un *Master*, se puede especificar que esté fija su posición siempre en la página en la que se inserte, es decir, que no se puede soltar en el lienzo libremente, se autocoloca.
- Otra cosa muy útil a la hora de documentar son las notas, las cuales están en el panel *Inspector*, bajo la pestaña *Notes* del elemento seleccionado.

## Prototipos en versión móvil
- Existen al parecer plantillas con mockups de móviles, pero Axure no proporciona un mockup de un móvil como opción, hay que meterlo a mano y encajar el lienzo sobre la pantalla del mockup.
- A la hora de compartir un enlace a un prototipo móvil, es conveniente guardar la página en la pantalla de inicio del móvil, para que esta se abra como una web app y no contenga la interfaz del navegador, sino el prototipo a pantalla completa.

## Ejercicio con condicionales
- En la configuración de los casos es posible añadir condicionales, que restringen aún más los casos.
- Es posible definir el tipo de texto que se incluye en un input, por ejemplo, poner que acepte solamente números o que oculte los caracteres insertados para una contraseña.

## Ejercicio con repeaters
> Los **repeaters** permiten generar copias de un mismo objeto tantas veces como se requiera, de forma que editando uno de los campos del repeater, se editan todas sus copias. Pueden expandirse horizontal o verticalmente.

- En las propiedades del repeater se puede ajustar el número de filas. Las columnas sirven a modo de base de datos, de forma que para autorrellenar los campos del objeto repetido, en la configuración del evento *onItemLoad* se puede indicar que se rellenen los textos cogiendo los datos de las columnas previamente definidas.
- Para insertar los valores de las columnas, en la configuración del evento se elige la acción *Set Text*, seleccionando el botón *FX*.
- Los repeaters pueden ordenarse utilizando un *Drop List*, configurando el evento *onSelectionChange* con la acción *Repeaters - Add sort*. Debe añadirse una condición para comporbar que lo seleccionado se corresponde con la ordenación que se quiera.

## Ejercicio con variables
- Axure no tiene memoria. Si se realiza algo en una página, en el momento en que abandones esa página, el contenido que hayas cambiado y el estado en el que se encontrase se perderá. Las **variables** sirven para tratar estos casos. Pueden almacenar cualquier tipo de valor, ya sea número o texto.    
- Se crea una variable en el menú de Axure *Project > Global Variables...*
- Una variable puede asignarse al tratar un evento, seleccionando la acción *Set Variable*. Luego pueden utilizarse estas variables en los condicionales.
