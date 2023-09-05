kmeans, regresion lineal y otros [[Metodos de clasificacion]] deben ser entrenados
![[Captura desde 2023-09-03 16-38-34.png]]
Con nuestros datos utilizaremos una parte para entrenar a nuestro modelo predictivo y otra parte para probar a nuestro modelo, arriba se puede observar que se separaria en train y test.
A su vez podemos partir el conjunto de entrenamiento entre entrenamiento y validacion, eso se llama **Cross Validation** 
# Conjuntos de entrenamiento y prueba

en cada fold vamos cambiando entre datos de entrenamiento y prueba 
![[Captura desde 2023-08-29 21-21-35.png]]
tambien podemos hacer esta division
![[Captura desde 2023-08-29 21-22-04.png]]

# Conjuntos balanceados

![[Captura desde 2023-08-29 21-23-35.png]]
los conjuntos deben estar balanceados, si un algoritmo se entrena con datos fraudulentos bancarios de menos, probablemente tilde a todos los casos de transacciones validas, si hacemos lo contrario, tilda a todos de fraudulentos, en ambos casos no sirve

# Overfitting
![[Captura desde 2023-08-29 21-26-37.png]]
Sucede cuando tengo un modelo que pruebo con los datos de prueba y al terminar (con un rango de suceso alto digamos 90%) lo llevo a los datos de prueba y cae (digamos a un 60%), el modelo esta sobreentrenado, (es como si se hubiera aprendido los datos de memoria) entonces, al ser llevado a un caso distinto no lo puede identificar
