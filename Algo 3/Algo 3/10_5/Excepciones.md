# Definicion

Una excepción es un objeto que se usa para comunicar una situación anómala desde un entorno que la detecta al ámbito desde el cual fue invocado un método.

Se “lanza” cuando en el contexto del método no hay suficiente información para resolver una anomalía, por lo que se debe salir del mismo hacia el módulo que lo invocó informando esta situación, pero **sin provocar la finalización del programa** ni enviar mensajes a un presunto usuario del que no se sabe nada.

# Partes

“Una excepción es un objeto que se usa para comunicar una situación anómala desde un entorno que la detecta al ámbito desde el cual fue invocado un método”.

1. **Una excepción es un objeto**: en efecto, las excepciones son objetos con identidad,comportamiento y estado. En los lenguajes con clases, son instancias de ciertas clases especiales.
2. **Se envía desde un entorno que la detecta**: habitualmente hay un método que crea y lanza un objeto de excepción porque no puede resolver el problema en su ámbito.
3. **Se envía al ámbito desde el cual fue invocado un método**: el objeto viaja desde el método que detectó el problema hasta el ámbito desde el cual ese método fue invocado. Este ámbito podrá recibir ese objeto y ver de qué manera tratar el problema.
4. **Se usa para comunicar una situación anómala**: su principal uso es la comunicación entre dos ámbitos, el que detecta el problema y el que debe lidiar con el mismo.

# Jerarquia de excepciones

![[Captura desde 2023-10-18 18-18-09.png]]

Los errores no se pueden salvar, las excepciones si

# Checked vs Unchecked

Existen dos tipos de excepciones: verificadas (checked) y no verificadas (unchecked). Las excepciones verificadas extienden Exception (pero no RuntimeException) y, para poder compilar el programa, deben ser declaradas (con throws) o atrapadas (con try..catch..finally). Las excepciones no verificadas extienden RuntimeException o Error, y no es obligatorio declararlas ni atraparlas


no verificada --------> compila
verificada -------------> no compila
# Bloque try

En el bloque try se encierra el código que podría provocar errores durante la ejecución y lanzar excepciones. En el o los bloque(s) catch se encierra el código que se ejecuta cuando se atrapa una excepción del tipo indicado en el parámetro. En el bloque finally (que es optativo cuando ya se definió, por lo menos, un bloque catch) se encierra el código que debe ejecutarse siempre, se haya o no lanzado y atrapado una excepción.
El bloque try debe preceder a, por lo menos, un bloque catch o al bloque finally.
Si se definen dos o más bloques catch, los bloques que atrapan las excepciones más específicas deben aparecer primero y los que atrapan las más generales deben aparecer por último.