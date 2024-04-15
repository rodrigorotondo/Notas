Paradigma de programación donde los programas se construyen componiendo y aplicando funciones. En este paradigma declarativo, las definiciones de funciones son árboles de expresiones que asocian valores a otros valores, en lugar de una secuencia de instrucciones que actualizan el estado de ejecución del programa, como ocurre en los paradigmas imperativos.

# Caracteristicas

1. Programas como funciones
2. Funciones puras
3. Datos inmutables
4. Funciones de primera clase
5. Funciones de orden superior
6. Composicion de funciones
7. Recursividad

# Programas como funciones

**Estructura de un programa**: un programa consiste en una lista
de definiciones de funciones.

**Ejecución de un programa:** consiste en aplicar las funciones a
sus argumentos, según las bases establecidas a partir de 1936 por
el **Cálculo Lambda**

**comentario**: entra argumento, sale resultado

# Funciones puras

**Determinismo**: Ante los mismos argumentos, una función pura
retorna el mismo valor. Esto conlleva la transparencia referencial
(una función pura puede reemplazarse por su valor de retorno)

**Ausencia de efectos colaterales (side effects)**: Además del
valor de retorno, una función pura no tiene ningún efecto visible
sobre el ambiente desde el cual se la invoca.

**Consecuencia práctica**: Se hacen más fáciles las Pruebas Unitarias

# Datos inmutables

- Después de creado un dato, su estado no cambia más.
- **Las funciones no modifican los datos recibidos como argumentos**: los valores retornados siempre están alojados en otras ubicaciones de memoria (las estructuras de datos son persistentes).

**Consecuencia práctica**: Se facilita la Programación Concurrente

# Funciones de primera clase

- Soportan las operaciones posibles para las otras entidades del lenguaje.

Pueden:
• ser asignadas a una variable,
• ser pasadas como argumento y
• ser retornadas por una función.

# Funciones de orden superior

• Tienen alguna de las siguientes capacidades (o ambas):
• Recibir funciones como argumento
• Retornar una función

# Composicion de funciones

• Consiste en combinar funciones para formar otra:
• El valor resultante se calcula aplicando una función a los argumentos. Luego se aplica otra al resultado, y así sucesivamente.

# Recursividad

Sin asignaciones de variables y ni construcciones estructuradas como
la secuencia y la iteración, la repetición de instrucciones se logra
mediante funciones de orden superior o funciones recursivas:

• Una función recursiva es aquella que contiene, en el bloque de
instrucciones que la definen, una llamada a la propia función,
permitiendo que una operación se realice una y otra vez, hasta
alcanzar el caso base.