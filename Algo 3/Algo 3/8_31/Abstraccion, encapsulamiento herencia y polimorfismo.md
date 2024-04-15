Estos son los 4 pilares de la [[Programacion orientada a objetos]] si tenemos abstraccion y encapsulamiento son lenguajes  basados en objetos, pero los lenguajes orientados a objetos tienen los 4.

ejemplo: Java


# Abstraccion

Es una de las formas fundamentales en que nosotros como humanos, enfrentamos la complejidad.
Surge de reconocer similitudes entre objetos del mundo real e ignorar por el momento sus diferencias.
Una buena abstracción enfatiza los detalles significativos para el usuario y suprime los irrelevantes.
#principio 
## La abstraccion y sus principios
Una abstracción se enfoca en la vista exterior de un objeto y sirve para separar su comportamiento esencial de su implementación.

## Principio de minimo compromiso:
la interfaz de un objeto solo proporciona su comportamiento esencial.
	esta relacionado con la visibilidad de los metodos del objeto, los metodos a veces deben ser llamados unicamente desde la misma clase, no hay que exponer demas

## Principio del menor asombro 
una abstracción captura todo el comportamiento de algún objeto, ni más ni menos, y no ofrece sorpresas ni efectos secundarios.
	El metodo no debe sorprendernos, aunque se produzca por un error de nombramiento
	solo debe hacer lo que se describe en el nombre digamos.

# Herencia
En el diseño orientado a objetos, reconocer la semejanza entre las cosas nos permite exponer los puntos en común dentro de abstracciones.
La identificación de clases y objetos implica tanto el descubrimiento como la invención.
A través del descubrimiento, llegamos a reconocer las abstracciones que forman el vocabulario del dominio del problema.
A través de la invención, ideamos abstracciones generalizadas.
	Parte de la [[Programacion orientada a objetos]] es descubrir la "conexion" entre los objetos para generalizar abstracciones, esto nos permite utilizar herencia, la cual no debe estar realmente conectado con lo que sucede en la realidad.

## Herencia y la reutilizacion de software
La herencia permite crear una nueva clase aprovechando los miembros de una clase existente (herencia simple, como en Java) o de varias (herencia múltiple, como en C++).

A la clase previamente existente sela conoce como superclase (o clase base), y a las nuevas como subclases (o clases derivadas).
Cada subclase puede convertirse en la superclase de otra.

	Basicamente se crean clases nuevas aprovechando clases ya existentes, en     java solo una, por ejemplo, rottweiler hereda de clase perro el metodo      ladrido().

	los metodos privados y los atributos privadaos NO se heredan pero los        metodos protegidos y los atributos protegidos si


	


## La herencia y las jerarquias de clases

Una subclase agrega sus propios atributos y métodos. Esto la vuelve más
específica que su superclase.
La subclase suele exhibir los comportamientos de su superclase junto con otros
adicionales específicos.
A la herencia se la conoce también como especialización o generalización.
- La superclase directa es la clase de la cual a subclase hereda en forma explícita.
- Una superclase indirecta es cualquier clase que se encuentre arriba de la superclase directa en la jerarquía de clases, que es la jerarquía que define las relaciones de herencia entre las clases


### La clase object en java
Todas las clases de java tienen en la cima de su jerarquia la clase object, hay ejemplos pero realmente dudo que aporten algo relevante.

## Redefinicion de metodos
Cabe destacar entonces que, a menudo, un método de la superclase puede no ser
apropiado para una subclase, ya que en esta se requiere una versión personalizada
del método. En dichos casos, la subclase puede sobrescribir (redefinir) el método
de la superclase con una implementación apropiada (method overriding).
El ejemplo anterior mostró un caso de herencia implícita, ya que todas las clases
heredan de Object. La herencia, en Java, se hace explícita mediante la palabra
reservada extends. Por lo tanto, aunque resulte redundante, podría haberse
declarado la clase Persona de la siguiente manera

public class Persona extends Object

## La herencia y los constructores
Los constructores no se heredan. En Java, todas las clases tienen un constructor por
defecto: el constructor sin parámetros. Igual que con todos los constructores, su primera
tarea es llamar al constructor de su superclase directa, para asegurar que las variables de
instancia heredadas de la superclase se inicialicen. Esto es así, porque siempre que se crea
un objeto de una subclase se empieza una cadena de llamadas a los constructores,
donde el constructor de la subclase, antes de realizar sus propias tareas, invoca al
constructor de la superclase, ya sea en forma explícita (por medio de super) o implícita
(llamando al constructor por defecto de la superclase). De igual forma, si la superclase
deriva de otra clase, el constructor de la superclase invoca al constructor de la
siguiente clase más arriba en la jerarquía, y así sucesivamente.
Si se declara un constructor con parámetros, el constructor por defecto deja
de estar disponible y, para poder instanciar objetos sin pasar argumentos, es
necesario declarar un nuevo constructor sin parámetros.

## Herencia y super
Cuando un método de una subclase sobrescribe un método de una superclase, se puede acceder al método de la superclase desde la subclase, si se antepone al nombre del método la palabra clave super y un separador punto (.)

## La herencia y las clases abstractas

A veces, todo o parte del comportamiento de ciertos objetos es demasiado específico
como para implementarlo en una superclase. En tales casos, el método se debe
declarar anteponiéndole la palabra reservada abstract en la superclase e
implementarse en cada subclase. Así, por contener al menos un método abstracto,
también la superclase debe definirse anteponiéndole la palabra reservada
abstract. En consecuencia, ya no será posible crear objetos de esa clase, porque las clases
abstractas no son instanciables. El siguiente ejemplo muestra cómo en la clase
abstracta PoligonoRegular se declara el método abstracto calcularArea, el cual se implementa luego en las clases TrianguloEquilatero y Cuadrado, dos subclases de PoligonoRegular
![[Captura desde 2023-08-31 16-07-21.png]]


## Limitacion de la herencia multiple
La herencia simple soluciona de raíz el problema básico de la herencia múltiple:
el problema del diamante (llamado así por la forma que tiene el diagrama de clases
donde ocurre este problema). Supongamos que la clase Vehiculo define un método avanzar. Las clases Auto y Lancha extienden Vehiculo: un auto es un vehículo y una lancha también es un vehículo, por lo tanto ambas clases heredan el método avanzar.
Ahora bien, dado que un vehículo anfibio es un auto y también es una lancha, podría declararse mediante herencia múltiple que VehiculoAnfibio extiende Auto y Lancha. ¿Qué comportamiento debería tener entonces un vehículo anfibio: el método avanzar que hereda de Auto o el que hereda de Lancha?
![[Captura desde 2023-08-31 16-16-58.png]]

## Limitacion de la herencia simple
La inexistencia de la herencia múltiple podría resultar limitante para ciertos
diseños. Por ejemplo, ¿qué tienen en común un celular y una paloma mensajera?
La respuesta es que ambos permiten enviar mensajes, por eso podrían modelarse mediante Celular y PalomaMensajera, dos subclases de la clase abstracta EnviadorDeMensajes que deberían implementar el método abstracto enviar declarado en esa clase. Sin embargo, este diseño es muy limitado, ya que la herencia simple impide que Celular herede también de Telefono, o que PalomaMensajera herede de Animal, dos clases llenas de funcionalidad.
![[Captura desde 2023-08-31 16-19-21.png]]

## Herencia (generalizacion) vs Realizacion

La solución consiste modelar como realizaciones todas las relaciones con
EnviadorDeMensajes, que no sería una clase sino una interfaz (interface)
implementada por Celular (que extiende Telefono) y por PalomaMensajera
(que extiende Animal). Haciendo que, en las realizaciones, los métodos de las
interfaces carezcan de implementaciones, se evita el problema del diamante.
![[Captura desde 2023-08-31 16-20-38.png]]

# Encapsulamiento
El término encapsulamiento suele
utilizarse para referirse a:
1. la agrupación de estado y comportamiento en una unidad conceptual (la clase);
2. la aplicación de mecanismos de restricción de acceso a los atributos y métodos;
3. el ocultamiento de información como principio de diseño.

- El primer significado de encapsulamiento refleja el hecho de que los objetos son entidades que agrupan los atributos y los métodos que operan sobre ellos. Así, un objeto es una cápsula cuyo interior (su implementación) sólo se debería poder utilizar a través de puntos de contacto con el exterior (su interfaz) bien definidos.

- El segundo significado se refiere al control de la accesibilidad o visibilidad de los métodos y atributos desde el exterior, mediante palabras claves (especificadores de acceso), que definen qué miembros son la interfaz y cuáles la implementación. 

- Finalmente, el ocultamiento de información es un principio que sugiere que, para obtener un buen diseño, todos los detalles de la implementación deben ser invisibles desde el exterior.


En Java, la declaración de una clase de objetos garantiza la primera acepción
de encapsulamiento. Sin embargo, esto no garantiza de ningún modo el
ocultamiento de la información (tercera acepción). Este se consigue manteniendo
los atributos privados y que el acceso a los mismos se lleve a cabo mediante
métodos públicos (segunda acepción). Java ofrece cuatro niveles de accesibilidad para los miembros de una clase: visibilidad de paquete (por defecto) y la que se obtiene al anteponerle a cada declaración alguno de los especificadores de acceso public, private o protected.

# Polimorfismo
se denomina así a la capacidad de contener valores de distintos tipos (en el caso de las variables polimórficas) o a la capacidad de recibir argumentos de diferentes tipos (en el caso de los métodos polimórficos).

## Polimorfismo ad-hoc
funciona con un número limitado y conocido de tipos, no necesariamente relacionados
entre sí 
## Polimorfismo universal
funciona con un número prácticamente infinito de tipos relacionados entre sí

## Polimorfismo por sobrecarga
Dentro de una misma clase, es posible escribir dos o más métodos con el mismo nombre pero diferente firma (signature). El resultado es un polimorfismo aparente, ya que no se trata de un método que puede recibir muchos tipos de argumentos, sino que hay varios métodos con el mismo nombre, y durante el proceso de compilación se elije cuál usar según el o los argumento(s) pasado(s).

## Polimorfismo por coercion
Aplicar coerción sobre alguien significa forzar su voluntad o su conducta. En programación, significa forzar a que un dato de un tipo sea tratado como si fuera de otro tipo. Por ejemplo, coerción es la operación realizada para convertir (de manera implícita) un argumento al tipo del parámetro correspondiente. En este caso, también se trata de un polimorfismo aparente, ya que la conversión que ocurre no cambia el hecho de que el método, en realidad, trabaja con un único tipo. 

## Polimorfismo parametrico
Cuando se escribe código genérico, es decir, sin mencionar ningún tipo de datos específico, para que pueda ser usado con datos que serán tratados de manera idéntica
independientemente de su tipo, se está aprovechando el polimorfismo paramétrico.
En Java, a esta variante de polimorfismo se la conoce como Generics. En el siguiente ejemplo, la clase PilaGenerica puede usarse para instanciar pilas específicas para cualquier tipo de objeto.
![[Captura desde 2023-08-31 16-40-02.png]]
## Polimorfismo por inclusion
El polimorfismo por inclusión, también conocido como polimorfismo por herencia o polimorfismo de subclases (o de subtipos), es la variante más común encontrada en la [[Programacion orientada a objetos]] y, por ello, la mayoría de las veces se lo denomina polimorfismo a secas. Se basa en el hecho de que las superclases incluyen a todas las instancias de sus subclases o, dicho de otra forma, todos los objetos de una subclase son también objetos de las superclases de esta. Por ello, aunque se declare un atributo, una variable local, un parámetro o el contenido de una colección como siendo de una superclase, en realidad puede referirse a cualquier instancia de esa clase o de alguna sus subclases. Los objetos no pierden sus características (estado y comportamiento) al ser referenciados de esta manera, por lo que es posible invocar los métodos que estos hayan sobrescrito, y su comportamiento será el esperado.