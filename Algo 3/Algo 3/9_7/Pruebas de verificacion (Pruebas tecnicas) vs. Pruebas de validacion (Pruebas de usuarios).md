***Verificar*** : controlar que hayamos construido el producto tal como pretendimos construirlo

***Validar*** : controlan que hayamos construido el producto que nuestro cliente queria.

# Pruebas de verificacion

Las pruebas de verificación son pruebas que los propios desarrolladores ejecutan
para ver que están logrando que el programa funcione como ellos pretenden

- **Las pruebas unitarias (Unit testing)** verifican pequeñas porciones de código. Por
ejemplo, verifican alguna responsabilidad única de un método.

- **Las pruebas de integración (Integration testing)** prueban que varias porciones de
código, trabajando en conjunto, hacen lo que pretendíamos. Por ejemplo, se trata de
pruebas que involucran varios métodos, clases o incluso subsistemas enteros.

- **Las pruebas de regresión (Regression testing)** garantizan que la aplicación siga
funcionando correctamente después de producirse algún cambio en el código.

- **Las pruebas de punta a punta (E2E o End-to-End testing)** verifican funcionalidades
que atraviesan todas las capas de la aplicación, p. ej. desde la pantalla a la base de datos.

- **Las pruebas de sistema (System testing)** evalúan cómo los diferentes componentes
interactúan juntos en la aplicación completa e integrada.

## Mock

Hay ocasiones en que debemos probar código que necesita de otros objetos, métodos o funciones para poder funcionar: en esas situaciones se utilizan objetos ficticios o dobles de prueba (stubs, mocks, fakes, etc.), que ayudan a aislar el código a probar.

Las pruebas de verificación podrían ser de caja negra o de caja blanca:

• Decimos que una prueba es de **caja negra** cuando la ejecutamos sin mirar el código que estamos probando.

• Cuando, en cambio, analizamos el código durante la prueba, decimos que es una prueba de **caja blanca.**

En general, se prefiere probar el funcionamiento y no verificar la calidad del código.

# Pruebas de Validacion
Para validar que hayamos construido el producto que nuestros clientes querían, se usan pruebas
de aceptación de usuarios (User Acceptance Tests). En general, se suele trabajar con pruebas
de aceptación diseñadas por usuarios – o al menos en conjunto con usuarios, o en el caso extremo, diseñadas por el equipo de desarrollo y validadas por usuarios – pero ejecutadas por el equipo de desarrollo en un entorno lo más parecido posible al que va a utilizar el usuario.
No obstante, cuando un sistema debe salir a producción, se suele poner a disposición de usuarios
reales para que ellos mismos ejecuten las pruebas. Si las pruebas las hacemos en un entorno
controlado por el equipo de desarrollo, se las llama pruebas **alfa.** Si, en cambio,
el producto lo prueba el cliente en su entorno, las llamamos pruebas **beta**.
![[Captura desde 2023-09-10 18-54-04.png]]
Todas estas pruebas que hemos mencionado suponen
que ejecutamos el sistema completo, con sus
conexiones con otros sistemas, con su interfaz de usuario, sus medios de almacenamiento de datos persistentes, etc. Hay ocasiones en que deseamos probar solamente comportamiento, en el sentido de que la lógica de la aplicación es correcta, pero sin interfaz de usuario. Estas pruebas más limitadas se denominan pruebas de comportamiento.




# Ejemplo
Supongamos que un cliente nos pide que desarrollemos un juego
de TaTeTi para celulares. Luego de hablar con él sobre colores,
plataformas, etc., el equipo se pone a trabajar. Al cabo de unos días,
se reúne con el cliente y le muestra el producto: impecable en
diseño, se ejecuta en las plataformas pedidas, juega contra el
usuario… Sin embargo, nuestro cliente no está satisfecho y afirma:
“Esto no es lo que pedí: yo preferiría jugar en red contra otro jugador”.
¿Qué fue lo que falló? Evidentemente, él tenía una expectativa que no fue cubierta:
el juego en red. También hay algo que en el sistema que él no deseaba: la autonomía
de la aplicación, que le permite jugar contra el usuario. Ocurre que las pruebas que
el equipo ejecutó estaban centradas en la verificación: entendimos algo,
diseñamos una solución y verificamos que el programa hace lo que nos propusimos.
Lo que falló fue la validación: lo que construimos no es lo que quiere el usuario.