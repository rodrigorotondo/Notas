#Metodologia 
Analicemos la construcción de **pruebas de caja negra**. La clave aquí es
seleccionar los casos de prueba con la mayor probabilidad de encontrar errores.
Lo que podríamos hacer es **establecer precondiciones y postcondiciones**. Con
las precondiciones podemos obtener casos de excepción y con las postcondiciones las
posibles salidas. Cada postcondición debería al menos definir una prueba.


# Ejemplo:
supongamos que lo que debemos probar es una función que retorna el factorial de un entero n pasado como argumento, que no sea mayor que 30.
Se prueban valores de los casos principales, casos borde y excepcionales, todos ellos
agrupados en clases de equivalencia
![[Captura desde 2023-09-10 20-05-38.png]]
