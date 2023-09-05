# Clasificacion
cuando resolvemos un problema de clasificacion, buscamos, para ciertos datos de entrada, una categoria c de un conjunto C de categorias posibles. Estas categorias no solo son finitas, sino que ademas son conocidas de antemano

# Regresion logistica

En la regresión logística lo que quiero es categorizar, clasificar. 
Es decir que dado una serie de puntos quiero encontrar una función (no es una recta en este caso) que separe los puntos en dos, en dos conjuntos. 
Y una vez que la encontré puedo determinar para cualquier valor X futuro, el conjunto al cual pertenecerá. Está asociado a problemas de
probabilidad.

## Ejemplo
Una persona quiere comprar una casa y para ello necesita pedir un préstamo hipotecario. Esta persona quiere saber si se lo van a otorgar o no. Pero el único dato fehaciente que tiene es su puntaje crediticio, el cual es de 720

La única información que se tiene es una lista de puntajes crediticios de otras 1000 personas con el resultado del otorgamiento, es decir si el crédito fue otorgado: 1 o bien si no fue otorgado: 0.
![[Captura desde 2023-08-29 20-22-58.png]]
Este grafico realmente no sirve porque es binario
![[Captura desde 2023-08-29 20-25-06.png]]
Acá podemos ver que la curva, para cada valor de X, asigna un valor entre 0 y 1 que indica la probabilidad de que el préstamo sea otorgado. 
Como la curva es creciente, la probabilidad será más alta cuanto el score esté más cerca de 850 y será más baja cuando el score esté cerca de 300. 
Encontrar los parametros optimos para esta curva consiste en construir un estimador de regresión logística.


# Clustering
no tenemos una variable a predecir, necesitamos que los datos que ya tenemos se ordenen de manera intrinsica para un mejor analisis

En este tipo de problemas se trata de agrupar los datos. Agruparlos de tal forma que queden definidos N conjuntos distinguibles, aunque no necesariamente se sepa que signifiquen esos conjuntos.  
El agrupamiento siempre será por características similares.

## K-means
1. El usuario decide la cantidad de grupos

2. K-Means elige al azar K centroides

3. Decide qué grupos están más cerca de cada centroide. Esos puntos forman un grupo

4. K-Means recalcula los centroides al centro de cada grupo

5. K-Means vuelve a reasignar los puntos usando los nuevos centroides. Calcula nuevos grupos

6. K-means repite punto 4 y 5 hasta que los puntos no cambian de grupo.
 ![[Captura desde 2023-08-29 20-43-01.png]]![[Captura desde 2023-08-29 20-44-45.png]]
como se puede ver K-means agrupa los datos por conjuntos y los clasifica

### Pasos por los que pasa K-Means
1. Primero elige la cantidad de clusters en la que lo quiero diferenciar
![[Captura desde 2023-08-29 20-48-42.png]]
2. selecciona puntos K al azar, no necesariamente de los datasets
![[Captura desde 2023-08-29 20-50-02.png]]
![[Captura desde 2023-09-03 16-16-12.png]]
3. Le asigna a cada punto de datos al centroide mas cercano
![[Captura desde 2023-08-29 20-52-00.png]]
![[Captura desde 2023-09-03 16-17-25.png]]

4. computa y posiciona el nuevo centroide de cada cluster 
![[Captura desde 2023-08-29 20-53-20.png]]
![[Captura desde 2023-09-03 16-18-34.png]]

5. reasignar cada punto de datos a un centroide nuevo, si hay alguna reasignacion, volver al paso 4, si no termina
![[Captura desde 2023-09-03 16-21-30.png]]

![[Captura desde 2023-09-03 16-22-08.png]]



## Como saber cuantos conjuntos elegir
### Regla del codo
![[Captura desde 2023-09-03 16-23-33.png]]

### Metodo silhoutte
 Elegimos un rango, ejemplo 1 a 10, y para cada valor:

 Para cada valor de K graficamos la silhouette

 El mejor valor posible es silhouette = 1

 El peor valor posible es silhouette = -1


#### Coeficiente de silhoutte
![[Captura desde 2023-09-03 16-25-09.png]]
![[Captura desde 2023-09-03 16-25-36.png]]
![[Captura desde 2023-09-03 16-26-24.png]]
#### Silhoutte plot
![[Captura desde 2023-09-03 16-27-27.png]]
![[Captura desde 2023-09-03 16-28-13.png]]



## Estadistica de hopkins
La estadística de Hopkins (Lawson y Jurs 1990) se utiliza para evaluar la tendencia de agrupación de un conjunto de datos midiendo la probabilidad de que un conjunto de datos dado sea generado por una distribución de datos uniforme. 

En otras palabras, prueba la aleatoriedad espacial de los datos.
![[Captura desde 2023-08-29 21-06-07.png]]![[Captura desde 2023-08-29 21-06-40.png]]
La idea es comparar una muestra cualquiera con una muestra uniforme (creada de forma aleatoria) y ver cómo se distribuyen los ejemplos (los puntos) en dicho espacio.

Sea D un conjunto de datos reales:

  

1. Tomar una muestra uniformemente de n puntos (p1,…, pn) de D.
2. Calcular la distancia, xi, de cada punto real a cada vecino más cercano. 
	1. Para cada punto pi ∈ D, encuentre su vecino más cercano pj; l
	2. calcular la distancia entre pi y pj y llámela xi=dist(pi , pj)

3. Generar un conjunto de datos simulados (randomD) extraído de una distribución uniforme aleatoria con n puntos (q1,…, qn) y la misma variación que el conjunto de datos reales original D.

4. Calcular la distancia, yi desde cada punto artificial hasta el punto de datos real más cercano.
	1. Para cada punto qi ∈ randomD, encuentre su vecino más cercano qj en D
	2. calcular la distancia entre qi y qj y llámela yi=dist(qi , qj)

5. Calcule la estadística de Hopkins (H) como: la distancia media del vecino más cercano en el conjunto de datos aleatorios dividida por la suma de las distancias medias del vecino más cercano en el conjunto de datos real y simulado.
![[Captura desde 2023-08-29 21-10-39.png]]

### Hipótesis que maneja Hopkins:

- Hipótesis nula: el conjunto de datos D se distribuye uniformemente (es decir, no hay clusters significativos)  

- Hipótesis alternativa: el conjunto de datos D no está uniformemente distribuido (es decir, contiene clusters significativos)

Podemos realizar la prueba de la estadística de Hopkins de forma iterativa, utilizando 0,5 como umbral para rechazar la hipótesis alternativa. 

	- Es decir, si H < 0,5, es poco probable que D tenga conglomerados estadísticamente significativos.

	- O si el valor de la estadística de Hopkins es cercano a 1, entonces podemos rechazar la hipótesis nula y concluir que el conjunto de datos D es significativamente un dato agrupable.