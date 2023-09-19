#Metodologia 
Fue la primera práctica basada en automatización de pruebas bien soportada por
herramientas. Fue presentada por Kent Beck en el marco de Extreme Programming
y enseguida surgieron frameworks para llevarla a la práctica.
Básicamente, TDD incluye tres subprácticas:

**Automatización**: las pruebas del programa deben ser hechas en código (general-
mente siguiendo las reglas "arrange, act, assert" o "given, when, then"), y con la
sola ejecución del código de pruebas debemos saber si lo que estamos probando
funciona bien o mal.

arrange -> arreglar -> declaramos cosas
act -> actuar -> hacemos cosas
assert -> asegurar -> nos fijamos que den el resultado esperado


**Test-First**: las pruebas se escriben antes del propio código a probar.
 
**Refactorización posterior**: para mantener la calidad del código, se lo cambia
sin cambiar la funcionalidad, manteniendo las pruebas como reaseguro.
Aclaración: TDD denomina “pruebas” a las pruebas unitarias.

# Ciclo TDD

![[Captura desde 2023-09-10 20-22-41.png]]
![[Captura desde 2023-09-10 20-23-32.png]]

# Ventajas
●Las pruebas en código sirven como documentación del uso esperado de lo que se está probando,
sin ambigüedades.

● Las pruebas escritas con anterioridad ayudan a entender mejor lo que se está por desarrollar.

● Las pruebas escritas con anterioridad suelen incluir más casos de pruebas negativas que las
que escribimos a posteriori.

● Escribir las pruebas antes del código a probar minimiza el condicionamiento del autor por lo
ya construido. También da más confianza al programador sobre el hecho de que el código
que escribe siempre funciona.

● Escribir las pruebas antes del código a probar permite especificar el comportamiento sin
restringirse a una única implementación.

● La automatización permite independizarse del factor humano y facilita la repetición de las
mismas pruebas a un costo menor.

● La refactorización constante facilita el mantenimiento de un buen diseño a pesar de los
cambios que, en caso de no hacerla, lo degradarían.