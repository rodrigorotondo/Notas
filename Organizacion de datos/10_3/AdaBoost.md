
# Introduccion
La técnica detrás de AdaBoost consiste en entrenar un predictor, un clasificador base (por ejemplo un árbol de decisión), verificar los errores que comete y entrenar luego otro predictor que corrija estos errores, (estas instancias mal clasificadas). AdaBoost repite este proceso hasta disminuir el error o encontrar un clasificador perfecto.

Utiliza para verificar el error el mismo conjunto de entrenamiento. Solo que, antes de entrenar el siguiente predictor, pondera las instancias mal clasificadas, aumentando su peso relativo. De esta manera el siguiente predictor entrenado estará focalizado en corregir los errores del primero.

# Contras

El entrenamiento de AdaBoost no puede hacerse en paralelo (como los árboles de Random Forest) y es por lo tanto poco escalable.

# Implementacion

La implementación más común es con árboles.

A diferencia de Random Forest, donde tenemos N árboles completos (de distinta profundidad pero completos), en AdaBoost tenemos un bosque de tocones (stumps)

![[Captura desde 2023-10-08 13-56-23.png]]

![[Captura desde 2023-10-08 14-33-43.png]]![[Captura desde 2023-10-08 14-33-54.png]]![[Captura desde 2023-10-08 14-33-59.png]]![[Captura desde 2023-10-08 14-34-03.png]]![[Captura desde 2023-10-08 14-34-08.png]]![[Captura desde 2023-10-08 14-34-11.png]]![[Captura desde 2023-10-08 14-34-14.png]]![[Captura desde 2023-10-08 14-34-24.png]]![[Captura desde 2023-10-08 14-34-34.png]]![[Captura desde 2023-10-08 14-34-40.png]]![[Captura desde 2023-10-08 14-34-43.png]]![[Captura desde 2023-10-08 14-34-46.png]]![[Captura desde 2023-10-08 14-34-53.png]]![[Captura desde 2023-10-08 14-34-55.png]]![[Captura desde 2023-10-08 14-34-58.png]]![[Captura desde 2023-10-08 14-35-00.png]]![[Captura desde 2023-10-08 14-35-02.png]]![[Captura desde 2023-10-08 14-35-06.png]]![[Captura desde 2023-10-08 14-35-07.png]]![[Captura desde 2023-10-08 14-35-09.png]]![[Captura desde 2023-10-08 14-35-11.png]]![[Captura desde 2023-10-08 14-35-14.png]]![[Captura desde 2023-10-08 14-35-16.png]]![[Captura desde 2023-10-08 14-35-18.png]]![[Captura desde 2023-10-08 14-35-20.png]]![[Captura desde 2023-10-08 14-35-22.png]]![[Captura desde 2023-10-08 14-35-24.png]]

# Resumen

1. AdaBoost combina un montón de weak learners (estimadores pobres) para hacer clasificaciones. Estos weak learners, son generalmente stumps (tocones).

2. Algunos tocones tienen más peso que otros en la votación final, tienen más que decir (amount of say)

3. Cada uno de estos tocones está construido teniendo en cuenta los errores del tocón anterior.
	1. Lo podemos hacer usando una función de impureza de Gini ponderada, para cada ejemplo
	2. O simplemente regenerando los datos como vimos en este ejemplo
