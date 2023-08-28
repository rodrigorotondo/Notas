- la clase es una plantilla que define las caracteristicas y el comportamiento de los objetos
- instancia es el objeto que vive en memoria


# Que es un objeto?
- es una entidad con comportamiento

## que lo define?
- Identidad 
	- Lo que lo distingue de otros objetos con las mismas caracteristicas
- Estado
	- Los valores de sus atributos
- Comportamiento
	- la reaccion a diferentes mensajes, la caracterizan los metodos


# Ojo con la ambiguedad
	Siempre aclarar si se trata de una instancia o de una clase, restan puntos.

hacer research sobre objetos mutables e inmutables

# Relaciones estaticas
son los niveles de visibilidad que controlan el acceso a los atributos y metodos de clase
## Publico
Permite el acceso desde cualquier parte
## Privado
Solo se puede acceder dentro de la propia clase

## Protegido 
Solo se puede acceder desde sus clases y subclases

# Tipo de relacion
formas en las que las clases pueden interactuar y conectarse entre si para modelar relaciones
## Asociacion
- dos objetos interactuan y quedan relacionados
- no dependen fuertemente de la existencia del otro (si uno desaparece el otro no se muere)
- (un profe tiene muchos cursos)
- (Una universidad tiene muchos alumnos)
## Agregacion
- Distintos ciclos de vida
- Hay una dependencia
- (un auto tiene 4 ruedas, puedo sacarle una rueda y ponersela a otro auto)
- (es un caso mas fuerte que asociacion)

## Composicion
- Tienen igual ciclo de vida
- Los objetos contenidos no tienen sentido fuera de la clase contenedora
- (un Cuerpo y sus organos, un organo no tiene sentido fuera del cuerpo)

## Dependencia
- una clase (o metodo) usa otro objeto o clase en alguna capacidad.
- (la calculadora que usa la biblioteca de operaciones)

## Generalizacion
- Una superclase define atributos y comportamientos comunes, mientras que las subclases los heredan
- Las subclases pueden agregar o modificar lo que necesiten
- (un tren y un auto son un vehiculo)
- (pato es un animal)
- (casa es un inmueble)
- (heladera es un tipo de electrodomestico)
- ....es un....

## Realizacion
- Una clase abstracta/ interfaz es implementada por otra clase
- (la bicicleta implementa orientable_girar y auto implementa orientable_girar pero gira de distinta manera)
	- ...implementa....|
