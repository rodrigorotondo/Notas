Se denomina **persistencia** la capacidad de un objeto de trascender el tiempo o el espacio. Permite que un objeto sea usado en diferentes momentos, por el mismo programa o por otros, así como en diferentes instalaciones de hardware.

Un **objeto persistente** es aquel que conserva su estado en un medio de almacenamiento permanente, pudiendo ser reconstruido por el mismo u otro proceso, de modo tal que al reconstruirlo se encuentre en el mismo estado en que se lo guardó. Al objeto no persistente se lo denomina **efímero**.

# Jerarquia de clases IO

![[Captura desde 2023-10-18 19-23-19.png]]

# Patron decorator en IO

Los diseñadores del lenguaje pensaron que utilizar la herencia para componer las combinaciones de funcionalidades más comunes requeridas para el manejo de archivos habría resultado en una verdadera explosión de clases.

Por eso, diseñaron las clases para el manejo de archivos siguiendo el
patrón de diseño Decorator.

En lugar de usar la herencia para agregar funcionalidad a las clases, este patrón permite agregar funcionalidad a los objetos individuales (en tiempo de ejecución).