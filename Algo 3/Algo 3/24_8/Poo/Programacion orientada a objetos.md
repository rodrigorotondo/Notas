cita:
"En vez de un procesador de bits consumiendo estructuras de datos, tenemos un universo de objetos bien comportados, cada uno de ellos pidiendole a otro que cortesmente le realice sus variados deseos"

-pagina 290 revista bytes

Los objetos se desdoblan en un paradigma del tipo "cliente-servidor" uno pide, otro responde.

## Sistemas orientados a objetos

- en la programacion tradicional , los datos son pasivos y se les aplican procesos
- En cambio, cuando se trabaja con objetos , son estos los que actuan para resolver un problema, respondiendo a estimulos (mensajes o eventos) del medio externo
- En sistemas diseñados como un conjunto de servicios, por lo general se tendra un disparador y luego un objeto ira llamando a otro hasta que todo el sistema este en movimiento.

## Objeto

objeto: entidad con comportamiento -> segun fontela

#identidad : lo que lo distingue de otros objetos de las mismas caracteristicas

#estado: los valores de sus atributos

#Comportamiento : sus reacciones ante mensajes recibidos y sus acciones en forma de mensajes enviados, implementados mediante metodos.

## Clases

basicamente plantillas para crear objetos, es importante que al crearlas tengamos las caracteristicas del objeto en 
es buena practica utilizar [[Tell don't ask]] al programar clases.


## #Metodologia

## 1- Encontrar objetos
Comenzamos con el diseño del #modelo
El #modelo  es una **representacion** de un sistema del mundo real que resulta de llevar a cabo el proceso de #abstraccion

la #abstraccion es una simplificacion que incluye solo aquellos detalles relevantes para determinado 

## 2- Determinar mensajes (como deben interactuar los objetos)

### UML: [[Diagramas]]


## 3 - Implementar comportamiento de los objetos
- La mayor parte de los lenguajes agrupan los objetos en *clases*, siendo estas conjuntos de objetos que tienen el mismo comportamiento (entienden los mismos mensajes y responden de la misma manera; si no fuese asi, no diriamos que son de la misma clase)

- Cuando la POO esta implementada con clases, es en la definicion de estas que el programador implementa el comportamiento de los objetos que se crearan a partir de ellas.

- En estos lenguajes, todos los objetos son instancias de clases.

