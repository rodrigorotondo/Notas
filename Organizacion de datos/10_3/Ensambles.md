# Introduccion

- Entrenar varios modelos, c/u sobre datos distintos. 
- Cada modelo sobre-ajusta de manera diferente.
- Cada modelo: bajo sesgo, alta varianza.
- Por ejemplo: árboles profundos.

"Un promedio de varias predicciones 'malas' es mejor que una prediccion buena"

# Bias vs variance

## Bias

El error debido al Bias de un modelo es simplemente la diferencia entre el valor esperado del estimador (es decir, la predicción media del modelo) y el valor real.

Cuando se dice que un modelo tiene un bias muy alto quiere decir que el modelo es muy simple y no se ha ajustado a los datos de entrenamiento (suele ser underfitting), por lo que produce un error alto en todas las muestras: entrenamiento, validación y test

## Variance

La varianza de un estimador es cuánto varía la predicción según los datos que utilicemos para el entrenamiento.

Un modelo con varianza baja indica que cambiar los datos de entrenamiento produce cambios pequeños en la estimación.

Al contrario, un modelo con varianza alta quiere decir que pequeños cambios en el dataset conlleva a grandes cambios en el output (suele ser overfitting).


# Concepto ensambles

![[Captura desde 2023-10-08 13-23-36.png]]![[Captura desde 2023-10-08 13-23-45.png]]![[Captura desde 2023-10-08 13-23-54.png]]
Montamos medio modelos que aprenden un solo aspecto del concepto, luego al unirlos llegan a tener un entendimiento global del concepto muy bueno


**Votacion**: Para una nueva instancia, clasificarla con todos los modelos, y devolver la clase más elegida. 

La votación reduce la varianza de la clasificación. (Random Forest)

Si los modelos individuales devuelven probabilidades, se puede hacer una votación ponderada.


# Bagging
![[Captura desde 2023-10-08 13-27-10.png]]


Es una técnica que consiste en construir nuevos conjuntos de entrenamiento usando bootstrap (muestras aleatorias con reemplazo) para entrenar distintos modelos, y luego combinarlos.
![[Captura desde 2023-10-08 13-28-48.png]]

## Pasos
1. Dividimos el conjunto de entrenamiento en distintos subconjuntos, obteniendo como resultado diferentes muestras aleatorias.
	
	a) Las muestras son uniformes (misma cantidad de individuos)

    b) Son muestras con reemplazo (los individuos pueden repetirse en el mismo conjunto de datos) 

2. Entrenamos un modelo con cada subconjunto 

3. Construimos un único modelo predictivo a partir de los anteriores

## Caracteristicas

- Disminuye la varianza en nuestro modelo final
- Muy efectivo en conjuntos de datos con varianza alta
- Puede reducir el overfitting
- Puede reducir el ruido de los outliers (porque no aparecen en todos los datasets)
- Puede mejorar levemente con el voto ponderado


## Problemas al usarlo con arboles

- Si pocos atributos son predictores fuertes, ¡todos los árboles se van a parecer entre sí!  
- Esos atributos terminarán cerca de la raíz, para todos los conjuntos generados con bootstrap.

## Random forest

Igual a bagging tradicional, pero en cada nodo, considerar sólo un subconjunto de m atributos elegidos al azar.
![[Captura desde 2023-10-08 13-38-50.png]]
# Boosting

Alternativa a Bagging.

Buscar nuevos modelos para las instancias **mal clasificadas por los anteriores.**


![[Captura desde 2023-10-08 13-40-26.png]]

1. Comenzar con un modelo (simple) entrenado sobre todos los datos: h₀  

2. En cada iteración i, entrenar hᵢ dando mayor importancia a los datos mal clasificados por las iteraciones anteriores.  

3. Terminar al conseguir cierto cubrimiento, o luego de un número de iteraciones.  

4. Clasificar nuevas instancias usando una votación ponderada de todos los modelos construidos.

![[Captura desde 2023-10-08 13-42-21.png]]![[Captura desde 2023-10-08 13-42-37.png]]

# Modelos exitosos

- AdaBoost
- Gradient Boosting
- XGBoost: eXtreme Gradient Boosting ------------> el mejor


## XGBoost vs Gradient boosting

- La velocidad de entrenamiento de XGBoost es mucho menor gracias a su implementación y a estar mejor orientado al uso eficiente del hardware (GPU)  


- El accuracy (o la métrica adecuada) también es mejor debido a que XGBoost maneja mejor el overfitting mediante regularizaciones (esto lo veremos más adelante)

## Resumen

- Necesita pesos, esto implica que:
	- Debemos adaptar algoritmo de aprendizaje
	- Y tomar muestras con reemplazo según pesos

- Puede sobreajustar
