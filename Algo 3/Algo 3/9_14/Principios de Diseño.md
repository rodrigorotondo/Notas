#Metodologia 

# Tell don't ask

Principio de diseño orientado a objetos en el que se basa la buena práctica de evitar solicitarle a un objeto que indique su estado y luego llevar a cabo una acción basándose en este, en lugar de solicitarle al objeto que lleve a cabo la acción él mismo.

## Ejemplos de incumplimiento

**Clases anemicas**: clases sin comportamiento, solo tienen getters, setters y atributos

**Flags over objects**: los objetos tienen atributos que el mismo no usa, pero son consultados por otros objetos

# Principio de minimo compromiso

Principio de diseño orientado a objetos que propone que la interfaz de un objeto solo proporcione su comportamiento esencial, nada más.

comentario: basicamente dejemos en privado todas los metodos que no sean necesarios que el usuario vea.

## Ejemplo

Si la interfaz Vehiculo declara el método estacionar y la clase Auto define además los métodos arrancar, frenar, transferir, lavar, etc., al Valet de un hotel le pasaríamos un Vehiculo, no un Auto.

# Principio del menor asombro

Principio de diseño orientado a objetos que propone que una abstracción capture todo el comportamiento de algún objeto, ni más ni menos, y no ofrezca sorpresas ni efectos secundarios que vayan más allá del alcance de la abstracción

comentario: basicamente que las funciones sean intuitivas, (por intuitivas me refiero a que no pase algo completamente *inesperado*)

ejemplo: usar == en vez de *equals* es **muy** mala idea
explicacion: == compara direcciones de memoria e *equals* compara valores, hay que usar el **correcto**


# Principio del menor conocimiento

propone que un método M de una clase C solo debería invocar métodos de:

• la propia clase C;
• los objetos que son atributos de C;
• los objetos recibidos por M como argumentos;
• los objetos instanciados en M.

comentario: Hace la del *neoliberal*  **Privatiza, privatiza PRIVATIZA** 

un metodo solo debe hablar con clases amigas.

# Don't repeat yourself

promueve la reducción de la duplicación de toda "pieza de información", abarcando:

• datos almacenados en una base de datos;
• código fuente de un programa de software;
• información textual o documentación.

Cuando el principio DRY se aplica de forma eficiente, los cambios en cualquier parte del proceso requieren ediciones en un único lugar

comentario: no copies y pegues, tenes que ser **original** hermano

# You Ain’t Gonna Need It (no lo vas a necesitar)

propone no agregar nunca una funcionalidad excepto cuando sea necesaria.
Es fundamental resistir la tentación de escribir código que no es necesario, pero que podría serlo en el futuro.

# KISS (Keep it simple, stupid!) Mantenlo simple, estupido!

propone que la mayoría de sistemas funcionan mejor si se mantienen simples que si se hacen complejos.

Por ello, la simplicidad debe ser mantenida como un objetivo clave del diseño, y cualquier complejidad accidental debe ser evitada.
## Ejemplos de incumplimiento

**Spaghetti code**: bueno, eso

**Frankencode**: de varias modificaciones y cambio de versiones quedan cosas muy complejas de cada version del programa


# EDP (Explicit Dependencies Principle) Principio de dependencias explícitas

Principio de diseño orientado a objetos que propone que los métodos y las clases deben requerir explícitamente (generalmente a través de parámetros de método o parámetros de constructor) cualquier objeto de colaboración que necesiten para funcionar correctamente.
Cuesta más mantener las clases con dependencias implícitas (que usan objetos que existen solo en el código dentro de sus métodos y no en su interfaz pública) que aquellas con dependencias explícitas.

## Ejemplo de incumplimiento

Si en un metodo de una clase C instancio una clase B se incumple esta regla, hay que declarar las dependencias en los parametros o el constructor de la clase


#  Principio de optimización de Knuth

propone que no se refactorice el código que aún no funciona completamente

comentario: si funciona, **NO LO ARREGLES**

# Principio de separación de preocupaciones

propone separar un sistema informático en partes distintas, tal que cada parte se enfoca una funcionalidad o un interés delimitado. Por ejemplo, la "lógica de negocios" del software es una preocupación, y la interfaz a través de la cual una persona utiliza esta lógica es otra. Cambiar una no debe requerir cambiar la otra.


comentario: basicamente **divide and conquer**

# SOLID
**S**ingle responsability Principle
**O**pen/closed Principle 
**L**iskov sustitucion Principle
**I**nterface segregation Principle
**D**ependency Inversion Principle

## Single responsability (responsabilidad unica)

propone que cada clase debe tener un único motivo para cambiar.

Un gran número de métodos públicos es un indicio de que una clase hace muchas cosas. Generalmente conviene separar los métodos públicos en distintas clases.

## Open/closed

Principio de diseño orientado a objetos que propone que el comportamiento de una clase debe estar abierto a la extensión, pero cerrado a la modificación (se debe poder extender sin modificar el código existente).

## Liskov sustitucion

propone que los objetos de las subclases deben poder sustituir a las instancias de las superclases sin alterar el correcto funcionamiento del programa.

## (Interface Segregation Principle) Principio de segregación de la interfaz

propone que deben crearse pequeñas interfaces específicas para los clientes en lugar de una general.
De este modo, quienes implementen una interfaz no se verán forzados a implementar partes (métodos o propiedades) que no les sean útiles.

comentario: cada interfaz que creemos debe implementar solo una cosa ( o la minima posible ) asi podemos implementarla en los casos necesarios, sin adosarle funciones o metodos extras a clases que no los necesitan

## (Dependency Inversion Principle) Principio de inversión de la dependencia

propone que:

• Los módulos de alto nivel no deberían depender de módulos de bajo nivel.
Ambos deberían depender de abstracciones.

• Las abstracciones no deberían depender de detalles (implementaciones concretas).
Las detalles deberían depender de abstracciones.

comentario: basicamente todo tiene que bajar desde una abstraccion pero una abstraccion no depender de algo.

# FIRST

Principio de diseño para pruebas que es el acrónimo de las cinco características que deben tener nuestros tests unitarios para ser considerados pruebas con calidad.

**F**ast
**I**ndependent
**R**epeatable
**S**elf-checking
**T**imely

o rapido, independiente, repetible, autovalidado, oportuno

