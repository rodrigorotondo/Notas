
1. Gradient Boost crea una cadena de árboles de profundidad fija. 

2. Comienza con un solo valor, un nodo hoja. Y luego calcula árboles para calcular el error cometido por el anterior.

3. Cada árbol está ponderado por un factor constante llamado learning rate o tasa de aprendizaje.
	1. Los árboles están restringidos en su crecimiento



![[Captura desde 2023-10-08 16-59-38.png]]


![[Captura desde 2023-10-08 16-59-53.png]]![[Captura desde 2023-10-08 17-00-02.png]]![[Captura desde 2023-10-08 17-00-07.png]]![[Captura desde 2023-10-08 17-00-17.png]]![[Captura desde 2023-10-08 17-00-22.png]]
# Bias vs Variance

## Bias

El error debido al Bias de un modelo es simplemente la diferencia entre el valor esperado del estimador (es decir, la predicción media del modelo) y el valor real.

Cuando se dice que un modelo tiene un bias muy alto quiere decir que el modelo es muy simple y no se ha ajustado a los datos de entrenamiento (suele ser underfitting), por lo que produce un error alto en todas las muestras: entrenamiento, validación y test

## Variance

La varianza de un estimador es cuánto varía la predicción según los datos que utilicemos para el entrenamiento.

Un modelo con varianza baja indica que cambiar los datos de entrenamiento produce cambios pequeños en la estimación.

Al contrario, un modelo con varianza alta quiere decir que pequeños cambios en el dataset conlleva a grandes cambios en el output (suele ser overfitting).
![[Captura desde 2023-10-08 17-03-31.png]]

# Ejemplo:

![[Captura desde 2023-10-08 17-04-09.png]]![[Captura desde 2023-10-08 17-04-18.png]]![[Captura desde 2023-10-08 17-04-21.png]]![[Captura desde 2023-10-08 17-04-23.png]]![[Captura desde 2023-10-08 17-04-26.png]]![[Captura desde 2023-10-08 17-04-28.png]]

Seguimos añadiendo árboles, hasta que los residuos no cambien significativamente o bien alcanzamos un número preestablecido de árboles seteado como parámetro.

Finalmente para estimar un nuevo valor, cuando el método termina de entrenar, procedemos como antes, usando el valor inicial y sumando los residuos ponderados de cada árbol.
![[Captura desde 2023-10-08 17-10-12.png]]
