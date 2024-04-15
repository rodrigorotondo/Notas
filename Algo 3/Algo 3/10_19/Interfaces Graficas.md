# Graphical User Interface (GUI)

Interaccion a traves de elementos graficos.
Posibilita una interaccion amigable e intuitiva

# Terminales de texto y programacion secuencial


![[Captura desde 2023-10-29 22-15-07.png]]

Esto seria un REPL (read evaluate print loop)

# Terminales de texto y programas con menus

![[Captura desde 2023-10-29 22-17-04.png]]
Secuencial pero bifurcada
# Terminales WIMP y programacion por eventos

![[Captura desde 2023-10-29 22-21-16.png]]
**WIMP :** windows, icons, menu, pointer

# Eventos

- Un objeto que representa algo interesante que ocurre en un sistema.

- Los eventos son previstos, pero no planeados (se conoce que pueden ocurrir,
pero no las circunstancias o el momento en el que lo harán).

- Las aplicaciones arrancan iniciando una cola de eventos y luego se quedan
esperando que ocurran eventos.

- Los eventos se procesan en orden, obteniéndolos de la cola de eventos.

- Los eventos pueden ser provocados por el usuario o por el sistema.

## Eventos de usuario

■ clic del mouse
■ pulsación de una tecla
■ movimiento del mouse
■ pérdida de foco

## Eventos del sistema

■ intervalo del reloj,
■ cierre del sistema


# Desarrollo de aplicaciones con GUI en java

## AWT

**AWT** (Abstract Window Toolkit) es un kit de herramientas de gráficos, interfaz de usuario y sistema de ventanas. Es el kit original de Java. 
Cuando Sun Microsystems lanzó Java en 1995, AWT suministró solo un nivel de abstracción muy fino sobre la interfaz de usuario nativa subyacente. Por ello, un programa con GUI escrito usando AWT luce como una aplicación nativa de Microsoft Windows cuando se ejecuta en Windows, pero el mismo programa luce como una aplicación de Apple Macintosh cuando se ejecuta en una Mac, etc.
Sin embargo, algunos desarrolladores de aplicaciones prefieren que sus
aplicaciones se vean exactamente igual en todas las plataformas.


# Swing

**Swing** es el segundo kit de herramientas de gráficos, interfaz de usuario y
sistema de ventanas de Java, lanzado en 1997 por Sun Microsystems.

Los componentes de este kit son mostrados y controlados directamente por
código Java independiente de la plataforma (son componentes ligeros, dado
que no se usan componentes nativos del sistema de ventanas propio del sistema operativo subyacente).

Además, al estar enteramente desarrollados en Java, su portabilidad es mayor,
asegurando un comportamiento idéntico en diferentes plataformas.

# JavaFX

**JavaFX** es una plataforma de software para crear aplicaciones de escritorio, así como Rich Internet Applications (RIAs), esto es, aplicaciones web con características y capacidades de aplicaciones de escritorio.

JavaFX tiene soporte para computadoras de escritorio y navegadores web en
Microsoft Windows, Linux y macOS, así como también para dispositivos móviles con iOS y Android.

Fue lanzado en 2008 por Sun Microsystems para reemplazar a Swing como la
biblioteca GUI estándar para Java SE, pero actualmente ya no forma parte
de las ediciones estándar, mientras que Swing y AWT permanecen incluidas.
En 2018, Oracle hizo que JavaFX fuera parte de OpenJDK (como OpenJFX).

## Funcionalidades

• Gráficos 2D y 3D acelerados
• Controles, diseños y cuadros/tablas de la GUI
• Soporte de audio y video
• Efectos y animaciones
• Compatibilidad con HTML5
• CSS, FXML y más...

## Motores de renderizado

En Windows, por ejemplo, se utiliza Direct3D, mientras que en la mayoría
de los demás sistemas se utiliza OpenGL.

# Model-View-Controller

En el patrón de arquitectura MVC, las responsabilidades están divididas.
Se puede implementar de más de una forma. Una posibilidad se describe a continuación.

Los datos con que opera el sistema y las operaciones para procesarlos se implementan en el modelo.

El usuario interactúa con la vista, la cual provee getters y setters para acceder
a los contenidos de sus componentes, incluyendo métodos para registrar los
objetos listeners, que en esta arquitectura son parte del controlador, ya que
es éste quien responde a los eventos que se producen en la vista, accediendo
a esta o al modelo según corresponda (mediante llamadas a métodos).
![[Captura desde 2023-10-29 22-36-39.png]]

# Herramientas

**Scene Builder** es un editor WYSIWYG de código abierto para JavaFX que crea vistas basadas en FXML. También tiene buen soporte de CSS y contiene un analizador de CSS.

**Scenic View** es una herramienta que ayuda a depurar aplicaciones. La herramienta encuentra aplicaciones JavaFX en ejecución y permite navegar a través de grafos de escena e inspeccionar las propiedades de nodos específicos.

**JavaFX Ensemble** proporciona demos y ejemplos para la mayoría de las funcionalidades de JavaFX, incluido su código fuente. La mayoría de las demostraciones son interactivas y permiten probar cómo se comporta alguna característica en tiempo de ejecución.

**e(fx)clipse** es un complemento para Eclipse que le agrega al IDE mucho soporte para JavaFX de gran utilidad

