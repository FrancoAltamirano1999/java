# java
Proyecto realizados con java
Descripción del Trabajo:
El jueves 3 de octubre del año 2017, se nos presentó el trabajo práctico de la materia Programación I de la Universidad Nacional General Sarmiento a realizar. Este mismo consistía en recrear un juego ya inventado, pero con una variante que se describirá más adelante. El juego se basaba en un pájaro que debía atravesar unos obstáculos representados como tubos y a
su vez obtener el mayor puntaje “comiendo” alimentos que aparecen aleatoriamente en la pantalla, todo esto sin impactarse con ninguno de los obstáculos o los bordes de la pantalla. La novedad que se implementa en este juego es que el pájaro es vegano y que se añadirían entre los alimentos hamburguesas, que los cuales, restarán puntos para el usuario, pero se podría
contar con un rayo conversor de hamburguesas para convertirlas en verduras y así no perder los puntos logrados.

Clases: variables de instancia y métodos:
En el proyecto realizado, utilizamos cinco Clases: Alimento; Disparo; Juego; Pajaro y Tubo, de las cuales todas se relacionan entre ellas y tienen sus propias variables de instancia y métodos. A continuación, se describe el contenido de cada Clase, sus variables de instancia y una breve explicación de cada uno de los métodos que se encuentran dentro de ellas.

Clase Alimento:
➢	Variables de instancia:

●	double x: Es el valor en la coordenada x que se le asigna a alimento.

●	double y: Es el valor en la coordenada y que se le asigna a alimento.

●	String nombreAlimento: Se utiliza para conocer el nombre actual de un alimento.

●	Image verdura: Dentro de esta variable se guarda una imagen que representa a una verdura o a una hamburguesa cuando se la llame dentro de los métodos en esta clase, y luego se graficará en la pantalla del juego con esa referencia.

➢	Métodos: 

●	void moverIzquierda ( ):
 Este método se encarga de disminuir la x del alimento, dando una sensación de movimiento desde la derecha de la pantalla a la izquierda de la misma.
●	void imprimirse (Entorno e):
Se encarga de dibujar en pantalla la imagen del alimento.
●	void cambiarAlimento ( ):
Realiza un random en un arreglo de alimentos que contienen verduras o hamburguesas, en donde se obtiene aleatoriamente un elemento de este arreglo y se dibuja en pantalla.
●	void newVegetable ( ):
Realiza un random en un arreglo de alimentos que contienen sólo elementos de verduras, en donde se obtiene aleatoriamente un elemento de este arreglo y se dibuja en pantalla.
●	void nuevaUbicacion (Tubo tubo):
Tiene la tarea de generar una verdura o una hamburguesa en una posición aleatoria y recibe tubo como parámetro para posicionarse dentro de un área en donde no se superponga por encima de la imagen del tubo, debido a que el tubo también se posiciona de manera aleatoria en la pantalla.
●	void aparecerDeNuevo (Tubo tubo):
Tomando como parámetro el tubo, una vez que éste llega al límite de la pantalla izquierda y desaparezca para volver a aparecer por el lado derecho de la pantalla, un alimento se elige aleatoriamente para aparecer detrás de él sin colisionar con el tubo.

 Clase Disparo:
➢	Variables de instancia:

●	double x: Es el valor en la coordenada x que se le asigna al disparo que se dibuja en pantalla.

●	double y: Es el valor en la coordenada y que se le asigna al disparo que se dibuja en pantalla.

●	double alto: Es la altura que se utiliza para dibujar un rectángulo que representa al disparo.

●	double ancho: Es la anchura que se utiliza para dibujar un rectángulo que representa al disparo.

➢	Métodos:

●	void moverse ( ):
Incrementa la posición de la x en donde está situada la imagen del disparo para originar un efecto de movimiento desde el la posición del pájaro hasta el límite derecho de la pantalla.
●	void imprimir (Entorno e):
Se encarga de dibujar en pantalla el disparo.

Clase Juego:
➢	Variables de instancia:


●	Pajarraco pajarraco

●	Int Time: La utilizamos para saber el momento en que se tiene que ejecutar una acción en el juego.

●	int puntaje: En esta variable se aloja el conteo de puntos que se establezcan a medida de que se esté ejecutando el juego. En cada nueva ejecución del juego, el valor de esta variable se inicializa en 0.

●	Alimento [ ] alimento: En este arreglo se alojan guardados objetos tipo alimento.

●	Image fondo: Dentro de esta variable se guarda una imagen que representa al fondo inmóvil del juego que se mostrará durante toda la ejecución del mismo. De la misma manera se dibujara la misma imagen al finalizar el juego en la pantalla de “Game Over”.

●	Image piso: Dentro de esta variable se guarda una imagen que representa un piso inmóvil del juego que se mostrará durante toda la ejecución del mismo para dar un efecto de profundidad, superponiendose por encima de las imágenes que aparezcan en pantalla de los tubos.

●	boolean colisionTubo: con esta variable se controla el corte del juego cuando el paja toca un tubo.

●	Tubo [ ] tubosSuperiores: En este arreglo se guardan objetos tipo Tubo.

●	Tubo [ ] tubosInferiores: En este arreglo se guardan objetos tipo Tubo.

●	int distanciaParaTubosYalimentos: esta variable es utilizada para dejar una distancia (en el eje de las  abscisas) para los objetos (Alimento y Tubo), de manera que no queden superpuesto y que entren tres objetos a largo de la pantalla.

●	Disparo disparo [ ]: En este arreglo se guardan objetos de tipo disparo.



➢	Métodos: 

●	boolean colision (Alimento verdura):
Retorna un valor booleano si el pájaro colisiona con un alimento.
●	boolean colisionBordes ( ):
Retorna un valor booleano si el pájaro colisiona con el borde superior o inferior de la pantalla.
●	boolean colisionConTubo (Tubo tubo):
Retorna un valor booleano si el pájaro colisiona con alguno de los tubos superiores o inferiores de la pantalla.
●	  boolean colisionDisparoHamburguesa (Alimento verdura, Disparo disparo):
Este método se encarga de verificar y retornar un valor booleano si el disparo efectuado por el pájaro impacta con una hamburguesa.
●	void puntos (Alimento verdura):
Lleva a cabo el conteo del puntaje de la partida que se está ejecutando, ya sea, sumando puntos cada vez que el pájaro coma una verdura o su disparo impacte con una hamburguesa y logre convertirla, o resta puntos cada vez que el pájaro coma una hamburguesa.
●	void inicializarTodo ( ):
Realiza la inicialización de todo lo necesario para el juego.

Clase Pajaro:

➢	Variables de instancia:

●	double x: Es el valor en la coordenada x que se le asigna a la imagen del pájaro que se dibuja en pantalla.

●	double y: Es el valor en la coordenada y que se le asigna a la imagen del pájaro que se dibuja en pantalla.

●	Image pajaro: Dentro de esta variable se guarda una imagen que representa a un pájaro cuando se dibuje en la pantalla del juego.
	
❖	El invariante de representación de x y la y deben respetar que al momento de inicializar el juego se debe graficar un pájaro posicionado a la mitad de la parte izquierda de la pantalla entre el límite izquierdo y la mitad de la pantalla misma, en sentido vertical.

➢	Métodos:

●	 void volar ( ):
Disminuye la elevación del pájaro en el eje y, para que de esta manera se tenga un mejor control en el manejo del pájaro.
●	void caer ( ):
Disminuye la posición del pájaro en pantalla constantemente.
●	void imprimir ( ):
Se encarga de dibujar en pantalla la imagen del pájaro.
●	Disparo disparar (Disparo disparo):
Este método realiza la creación de un objeto tipo disparo.

Clase Tubo:

➢	Variables de instancia:

●	double x: Es el valor en la coordenada x que se le asigna al tubo que se dibuja en pantalla.

●	double y: Es el valor en la coordenada y que se le asigna al tubo que se dibuja en pantalla.

●	Image tubo: Dentro de esta variable se guarda una imagen que representa a un tubo cuando se dibuje en la pantalla del juego.


➢	Métodos:

●	void moverIzquierda ( ):
Este método se encarga de disminuir la x de la imagen del tubo, dando una sensación de movimiento desde la derecha de la pantalla a la izquierda de la misma.
●	 void imprimirSuperior (Entorno e):
Este método consiste en graficar los tubos en la parte superior de la pantalla.
●	void imprimirInferior (Entorno e):
Este método consiste en graficar los tubos en la parte inferior de la pantalla.
●	void aparecerDeNuevoSuperior ( ):
Genera un nuevo tubo superior en la parte derecha de la pantalla cuando otro tubo superior deja de aparecer en la parte izquierda de la pantalla. También, por medio de un random, se encarga de modificar el alto del tubo nuevo.
●	void aparecerDeNuevoInferior (Tubo tuboSuperior ):
Genera un nuevo tubo inferior en la parte derecha de la pantalla cuando otro tubo inferior deja de aparecer en la parte izquierda de la pantalla. También se modifica su altura para dar una abertura entre los tubos para que el pájaro pueda pasar y a su vez para que no choque con el tubo superior.
●	void bajar (Tubo tuboInferior):
Decrementa las adyacentes del tubo superior hasta encontrarse con el margen del tubo inferior y se detiene para no colisionar con el mismo.


