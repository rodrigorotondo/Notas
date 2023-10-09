#modelo 
## Diagrama de secuencia
- Son modelos dinamicos que describen como un grupo de objetos colabora en determinado escenario a traves del tiempo
- En el diagrama de secuencia se representa cada objeto como un rectangulo arriba de su linea de vida
- Los mensajes son flechas entre objetos y el orden de los mensajes esta dado por el eje vertical que se lee arriba hacia abajo
- De los mensajes se escribe por lo menos el nombre aunque tambien se pueden agregar los parametros
- Tambien representan cierto control: iteraciones, condiciones, etc
### Conclusion 
- Ayudan a ver el flujo de control y ordenamiento temporal de los eventos
- ayudan a encontrar los metodos necesarios de los objetos 
- conviene colocar mas a la izquierda los objetos que inician la interaccion y los mas importantes
- como todo diagrama su gran virtud es la simplicidad y el impacto visual, no tiene  que mostrar toda la complejidad del sistema

## Diagrama de clase
- Representan relaciones estaticas entre clases e interfaces (no cambian a traves del tiempo)
- Una clase se representa con un rectangulo con tres divisiones: 
	- una para el nombre
	- una para los atributos
	- una para los metodos
- En ocasiones no usamos las 3 divisiones, sino solo dos (eliminando los atributos) o una (solo con el nombre de la clase)

- Los atributos y metodos 
	- *privados* se pueden indicar precedidos de un signo -
	- Los *publicos* del signo +
	- los *protegidos* del signo #

- No es conveniente utilizar aspectos de la sintaxis que tengan un significado solo en determinado lenguaje

### Conclusion 
- No es necesario representar todas las clases con todos sus detalles
- Conviene representar atributos, asociaciones y generalizacion (la visibilidad, las dependencias y otras propiedades son necesarias solo en algunas ocasiones especiales)
- Conviene dibujar modelos solo de las partes importantes del sistema
- Son herramientas, por lo que el grado de detalles hay que manejarlo desde el punto de vista de la practicidad
- Conviene ordenar los elementos del diagrama para minimizar el cruce de lineas y para que las cosas que son cercanas semanticamente queden cerca fisicamente


