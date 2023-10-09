XGBoost fue diseñado para Big Data, es decir para conjuntos de datos grandes y complejos. Sin embargo a fines de entender el algoritmo principal lo usaremos con un conjunto de datos simple (y para el caso de regresión).

![[Captura desde 2023-10-08 17-23-24.png]]

![[Captura desde 2023-10-08 19-57-20.png]]![[Captura desde 2023-10-08 19-57-43.png]]![[Captura desde 2023-10-08 19-58-02.png]]![[Captura desde 2023-10-08 19-58-17.png]]

# Regularizacion
![[Captura desde 2023-10-08 20-05-55.png]]![[Captura desde 2023-10-08 20-06-02.png]]![[Captura desde 2023-10-08 20-06-08.png]]![[Captura desde 2023-10-08 20-06-12.png]]![[Captura desde 2023-10-08 20-06-15.png]]![[Captura desde 2023-10-08 20-06-17.png]]

# Bias vs Variance

## Bias
El error de sesgo (bias) es un error de “suposiciones erróneas” en el algoritmo de aprendizaje. Un sesgo alto puede hacer que un algoritmo pierda las relaciones relevantes entre las características dadas y los resultados esperados (underfitting)

## Variance
La varianza es un error de sensibilidad a pequeñas fluctuaciones en el conjunto de entrenamiento. Una varianza alta puede resultar de un algoritmo que modela hasta el ruido aleatorio en los datos de entrenamiento (overfitting).

# Vuelta a regularizacion
![[Captura desde 2023-10-08 20-08-31.png]]
![[Captura desde 2023-10-08 20-08-35.png]]![[Captura desde 2023-10-08 20-08-38.png]]![[Captura desde 2023-10-08 20-08-40.png]]

# Volvemos a XGBoost y al calculo de similarity score

![[Captura desde 2023-10-08 20-23-32.png]]![[Captura desde 2023-10-08 20-23-34.png]]![[Captura desde 2023-10-08 20-23-48.png]]![[Captura desde 2023-10-08 20-23-53.png]]![[Captura desde 2023-10-08 20-23-57.png]]![[Captura desde 2023-10-08 20-24-04.png]]![[Captura desde 2023-10-08 20-24-11.png]]![[Captura desde 2023-10-08 20-24-14.png]]![[Captura desde 2023-10-08 20-24-16.png]]![[Captura desde 2023-10-08 20-24-19.png]]![[Captura desde 2023-10-08 20-24-21.png]]![[Captura desde 2023-10-08 20-24-24.png]]![[Captura desde 2023-10-08 20-24-26.png]]![[Captura desde 2023-10-08 20-24-28.png]]![[Captura desde 2023-10-08 20-24-30.png]]![[Captura desde 2023-10-08 20-24-33.png]]

# Calcular la respuesta de XGBoost

![[Captura desde 2023-10-08 20-32-12.png]]![[Captura desde 2023-10-08 20-32-16.png]]![[Captura desde 2023-10-08 20-32-18.png]]![[Captura desde 2023-10-08 20-32-22.png]]![[Captura desde 2023-10-08 20-32-25.png]]