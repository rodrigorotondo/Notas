# que es un outlier?
Un outlier es una observación que se desvía tanto de las otras observaciones como para despertar sospechas que fue generado por un mecanismo diferente

- Es un concepto subjetivo al problema
- Son observaciones distantes del resto de los datos
- Pueden deberse a un error de medicion, aleatoriedad, que instancia pertenezca a una familia distinta del resto, etc

Ejemplo1: Una persona de 120 años de edad
Ejemplo2: Una persona de 4 años que mide 1,80 mts

si al ejemplo 2 tomamos un enfoque univariado, todo esta en orden, la altura es normal y la edad tambien.
Si tomamos un enfoque multivariado, es un outlier, pues es muy raro que alguien de 4 años mida 1,80

# Deteccion
La detección de outliers es importante su presencia puede influenciar los resultados  de un análisis estadístico clásico.

En grandes volumenes de datos la deteccion de outliers resulta mas eficiente estudiando todas las variables

# Es necesario eliminarlos?
- Deben ser cuidadosamente inspeccionados

- Pueden estar alertando anomalías, en algunas situaciones nuestra tarea de interés será encontrarlos : 

	- Detección de Fraudes
	- Detección de Fallas  
	- Patologías Médicas

![[Captura desde 2023-09-11 12-53-25.png]]

# Tipos de outlier
![[Captura desde 2023-09-11 12-55-42.png]]


## Univariado

- Son valores atipicos que podemos encontrar en una simple variable
- El problema de los enfoques univariados es que son buenos para la deteccion de extremos pero no en otros casos
- Intentemos no quedarnos solo con los analisis univariados
### Metodos de deteccion

- IQR (rango intercuartilico) Analizar los valores que estan por fuera del IRQ

![[Captura desde 2023-09-11 13-15-06.png]]

#### Z-score 
![[Captura desde 2023-09-11 13-16-03.png]]

Z-score es una metrica que indica cuantas desviaciones estandar tiene una observacion de la media muestral, asuminedo una distribucion gaussiana
Al calcular Z-score para cada muestra debemos fijar un umbral:
 - Un valor como regla de oro es z>3
![[Captura desde 2023-09-11 14-20-06.png]]
![[Captura desde 2023-09-11 14-20-44.png]]
#### Z-score modificado 
La media de la muestra y la desviación estándar de la muestra, pueden verse afectados por los valores extremos presentes en los datos
![[Captura desde 2023-09-11 14-31-18.png]]
regla de oro: Valores mayores a 3.5 son considerados outliers


##### Median absolute Deviation (MAD)
![[Captura desde 2023-09-11 14-32-39.png]]
Es la mediana de los desvíos absolutos respecto de la mediana. 

  Para hacer MAD comparable con la desviación estándar, se normaliza por 0.6745

#### Analisis de box-plot
Los Box-Plots permiten visualizar valores extremos univariados.


Las estadísticas de una distribución univariada

se resumen en términos de cinco cantidades:

- Mínimo/máximo (bigotes)
- Primer y tercer cuantil (caja)
- Mediana (línea media de la caja)
- IQR = Q3 - Q1

![[Captura desde 2023-09-11 14-37-00.png]]


Generalmente la **regla de decisión**:

+/- 1.5*IQR   Outliers moderados

+/-   3 *IQR   Outliers severos


#### Otros
- **indentificar valores extremos a partir de 1, 2 o 3 desvios de la media**

## Multivariados
- Los valores atipicos multivariados se pueden encontrar en un espacio n-dimensional
- Para detectar  valores atipicos en espacios n-dimensionales es necesario ajsutar un modelo.

### Tipos de efectos
#### Efecto enmascaramiento
Se produce cuando un grupo de outliers esconden a otro/s. Es decir, los outliers enmascarados se haran visibles cuando se elimine/n el o los outliers que los esconden

#### Efecto inundacion
Ocurre cuando una observacion solo es outlier en presencia de otra/s observacion/es. Si se quitara/n la/s ultima/s, la primera dejaria de ser un outlier

### Metodos de deteccion
- #### Análisis globales: **Clustering**.

	- Utilizando medidas de distancia como Mahalanobis. Los valores similares son agrupados y los que quedan aislados pueden ser considerados outliers.
![[Captura desde 2023-09-11 13-18-42.png]]

##### Distancia de mahalanobis
Es una medida de distancia entre el punto y un conjunto de observaciones con media y una matriz de covarianza S.
![[Captura desde 2023-09-11 14-45-49.png]]
![[Captura desde 2023-09-11 14-46-21.png]]
![[Captura desde 2023-09-11 14-49-22.png]]

#### Local Outlier factor
- Es un método de detección de outliers basado en distancias.

- Calcula un score de outlier a partir de una distancia que se normaliza por densidad.

![[Captura desde 2023-09-11 13-21-18.png]]

El método LOF valora puntos en un conjunto de datos multivariados. 
Es un **método basado en densidad** que utiliza la búsqueda de vecinos más cercanos.
- Se compara la densidad de cualquier punto de datos con la densidad de sus vecinos
- Parámetro k (cantidad de vecinos) y métrica de distancia

El método calcula los **scores** para cada punto, se debe definir un umbral de corte (depende del dominio)

- Si el score del punto X es 5, significa que la densidad promedio de los vecinos de X es 5 veces mayor que su densidad local

![[Captura desde 2023-09-11 14-56-53.png]]

![[Captura desde 2023-09-11 15-10-36.png]]

**Aclaracion:** Cuán denso es el entorno de un determinado punto?

En las implementaciones de los lenguajes el score está normalizado y generalmente devuelve valores entre 0 y 1
#### Otros
- **Metodos basados en arboles de busqueda: IsolationForest**

- Es un algoritmo no supervisado y no paramétrico basado en árboles de decisión. 

- Idea Principal: los datos anómalos se pueden aislar los datos normales mediante particiones recursivas del conjunto de datos.

![[Captura desde 2023-09-11 15-11-36.png]]
Tomar una muestra de los datos y construir un árbol de aislamiento:

1. Seleccionar aleatoriamente n características .

2. Dividir los puntos de datos seleccionando aleatoriamente un valor entre el mínimo y el máximo de las características seleccionadas.

  
La partición de observaciones se repite recursivamente hasta que todas las observaciones estén aisladas.
![[Captura desde 2023-09-11 15-18-59.png]]
Isolation Forest identifica anomalías como las observaciones con longitudes de ruta promedio cortas en los árboles de aislamiento.

- Utiliza la altura del árbol (cantidad de aristas)

![[Captura desde 2023-09-11 15-20-11.png]]

