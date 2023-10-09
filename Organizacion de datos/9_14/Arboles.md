
# ID3
- ID3: Iterative Dichotomiser 3 (tree -> árbol)
-  Creado por: Ross Quinlan
-  Genera un árbol de decisión a partir de un conjunto de ejemplos.

Representación de un Árbol de decisión

La salida del algoritmo ID3 se representa como un grafo en forma de árbol, cuyos componentes son:
![[Captura desde 2023-09-26 20-43-24.png]]

## Componentes
- Un nodo principal llamado raíz en la parte superior  
   
-  Nodos terminales, como su nombre lo indica, son nodos donde termina el flujo y que ya no son raíz de ningún otro nodo. Estos nodos terminales deben contener una respuesta, o sea, la clasificación a que pertenece el objeto que ha conducido hasta él.

-  Los demás nodos representan preguntas con respecto al valor de uno de los atributos.  

-  Las líneas representan las posibles respuestas que los atributos pueden tomar.

## Entropia (de la informacion)
La medida del desorden o la medida de la pureza. Básicamente, es la medida de la impureza o aleatoriedad en los datos.

Entropia: Para calcular la entropia de n clases se utiliza la formula:
![[Captura desde 2023-09-26 21-05-21.png]]

**Donde**:
- S: es una lista de valores posibles.
- Pi: es la probabilidad de los valores.
- i: Cada uno de los valores.

**Importante**:

- Para una muestra homogénea la entropía es igual a 0  
- La máxima entropía viene dada por Log2(n), n son los posibles valores de salida.  
Si n =2 (TRUE o FALSE) entonces, la máxima entropía es 1.  
O sea es la máxima incertidumbre

#### Ejemplo
![[Captura desde 2023-09-26 21-07-32.png]]
![[Captura desde 2023-09-26 21-08-13.png]]

**Otro ejemplo**:
![[Captura desde 2023-09-26 21-09-11.png]]

### Ganancia de informacion:
La ganancia de información se aplica para cuantificar qué característica, de un conjunto de datos dados, proporciona la **máxima información** sobre la clasificación.

Si tuviésemos que elegir una sola característica, para clasificar. ¿Cuál sería?

**Ganancia de la informacion**:

![[Captura desde 2023-09-27 00-02-21.png]]

Dónde:

- S: es una lista de valores posibles para un atributo dado: A
- A: Uno de los atributos, en la lista de ejemplo.
- V(A) : Conjunto de valores que A puede tomar
- Sv/S = Probabilidad de un valor, para el atributo A.
- Entropía (Sv), entropía calculada para el valor “v” de A.


### Algoritmo basico

1. Calcular la entropía para todas las clases. 
2. Calcular la entropía para cada valor posible de cada atributo.
3. Seleccionar el mejor atributo basado en la reducción de la entropía. Usando el cálculo de Ganancia de la Información
4. Iterar, para cada sub-nodo. Excluyendo el nodo raíz, que ya fue usado.

### Ejemplo
![[Captura desde 2023-09-27 00-05-53.png]]
![[Captura desde 2023-09-27 00-06-25.png]]
![[Captura desde 2023-09-27 00-07-04.png]]

![[Captura desde 2023-09-27 00-07-35.png]]
![[Captura desde 2023-09-27 00-08-01.png]]
![[Captura desde 2023-09-27 00-08-32.png]]
![[Captura desde 2023-09-27 00-09-00.png]]
![[Captura desde 2023-09-27 00-09-19.png]]
![[Captura desde 2023-09-27 00-13-20.png]]
![[Captura desde 2023-09-27 00-13-54.png]]
![[Captura desde 2023-09-27 00-14-23.png]]
![[Captura desde 2023-09-27 00-14-50.png]]
![[Captura desde 2023-09-27 00-15-11.png]]
![[Captura desde 2023-09-27 00-15-33.png]]
![[Captura desde 2023-09-27 00-15-51.png]]
![[Captura desde 2023-09-27 00-16-13.png]]

![[Captura desde 2023-09-27 00-16-48.png]]

### Resumen

- Un nodo de decisión está asociado a uno de los atributos y tiene 2 o más ramas que salen de él, cada una de ellas representando los posibles valores que puede tomar el atributo asociado.  


- Un nodo-respuesta está asociado a la clasificación que se quiere proporcionar,y nos devuelve la decisión del árbol con respecto al ejemplo de entrada.


## Impureza de gini

La impureza de Gini es una medida de cuán a menudo un elemento elegido aleatoriamente del conjunto sería etiquetado incorrectamente si fue etiquetado de manera aleatoria de acuerdo a la distribución de las etiquetas en el subconjunto

Algunas implementaciones de árboles de decisión utilizan la impureza de Gini en lugar de la ganancia de información, ya que es más fácil de calcular (computacionalmente menos costosa) Ejemplo: Scikit-learn

![[Captura desde 2023-09-27 00-25-03.png]]

### Ejemplo
![[Captura desde 2023-09-27 00-26-43.png]]

![[Captura desde 2023-09-27 00-26-57.png]]

![[Captura desde 2023-09-27 00-30-06.png]]
![[Captura desde 2023-09-27 00-30-33.png]]
![[Captura desde 2023-09-27 00-31-17.png]]
![[Captura desde 2023-09-27 00-31-43.png]]
![[Captura desde 2023-09-27 00-32-06.png]]
![[Captura desde 2023-09-27 00-32-30.png]]![[Captura desde 2023-09-27 00-32-43.png]]![[Captura desde 2023-09-27 00-34-13.png]]
![[Captura desde 2023-09-27 00-34-35.png]]
![[Captura desde 2023-09-27 00-35-10.png]]
![[Captura desde 2023-09-27 00-35-37.png]]
![[Captura desde 2023-09-27 00-36-10.png]]


# C4.5

Se hicieron mejoras a ID3

-  Campos numéricos, rangos continuous
-  Datos faltantes   
-  Poda

## Datos faltantes

- Manejo de los datos de formación con valores de atributos faltantes - C4.5 permite valores de

- los atributos para ser marcado como “?” para faltantes. Los valores faltantes de los atributos

- simplemente no se usan en los cálculos de la ganancia y la entropía.


## Campos numericos o rangos continuos

- Si un atributo A, tiene un rango continuo de valores. El algoritmo puede, dinámicamente crear

- un campo Booleano tal que si A < C Ac = TRUE, sino Ac = FALSE.

### ¿Cómo encontrar ese umbral C?

Vamos a cortar el rango de forma que C nos quede con la mayor ganancia de información.

- Ordenamos A de menor a mayor, por ejemplo.

- Identificamos los valores adyacentes (de la clase que es nuestra salida)

- Detectamos cuando hay un cambio de valor de salida, entonces en esos límites seguramente están nuestros Ci candidatos. 

- Creamos varios Ci, que dividen en dos el rango. Para cada uno de estos rangos calculamos la ganancia de información. Nos quedamos con el que nos da el mejor resultado. (Se puede también quedarse con los N mejor.)

## Poda

El método de poda del árbol consiste en:

-  generar el árbol tal y como hemos visto  


- A continuación, analizar recursivamente, y desde las hojas, qué preguntas (nodos interiores) se pueden eliminar sin que se incremente el error de clasificación con el conjunto de test.   

(Si hay ruido el árbol tendrá un error, es decir cantidad de casos mal clasificados)

Error= Casos bien clasificados / Casos Totales


- Se elimina un nodo interior cuyos sucesores son todos nodos hoja.  

- Se vuelve a calcular el error que se comete con este nuevo árbol sobre el conjunto de test.  

- Si este error es menor que el error anterior, entonces se elimina el nodo y todos sus sucesores(hojas)  

- Se repite.



# Random forest

“Muchos estimadores mediocres, promediados pueden ser muy buenos”

## Bootstrap aggregating

Es una técnica, o meta-algoritmo que dice lo siguiente:

Dado un conjunto de entrenamiento D, de tamaño n, la técnica de bagging generará m nuevos conjuntos de entrenamiento D1,... Di,..., Dm cada uno de tamaño n' tomando muestras aleatorias de D. 

Y  en general n'<n. Siendo n' aproximadamente un 2⁄3 de n.

Suponiendo que tenemos un conjunto de datos, como el que sigue:

-  8 Atributos
-  1 Clase que queremos saber
-  9000 registros
![[Captura desde 2023-09-27 00-59-13.png]]
![[Captura desde 2023-09-27 00-59-46.png]]

### Attribute bagging (o random subspace)

Luego para cada una de las m tablas, escogemos sólo algunos atributos (COLUMNAS) de forma aleatoria también.
¿Con cuantas nos quedamos?  =>Con RAÍZ CUADRADA del número de atributos.  
Cómo acá hay 8 atributos, tomamos Round(√8) = 3  
(Esto es recomendable sobre todo cuando hay muchas columnas)

![[Captura desde 2023-09-27 01-01-06.png]]

Ahora tenemos m tablas reducidas en atributos y para cada una de ellas entrenamos un árbol

- Para cada árbol calculamos su matriz de confusión:

![[Captura desde 2023-09-27 01-02-30.png]]

Entonces calculamos la tasa de error de cada árbol, esto es:  
FALSOS POSITIVOS + FALSOS NEGATIVOS SOBRE EL TOTAL DE EJEMPLOS CLASIFICADOS  
(Sobre un conjunto de entrenamiento o sobre un porcentaje del conjunto utilizado)  
  

- Nos quedamos con el mejor árbol de los m, y repetimos el proceso K veces. 
- Al final vamos a tener K árboles.


**(FP + FN) / TOTAL = Tasa de error**

## Como clasificar una vez terminado el proceso?

Luego para clasificar un nuevo ejemplo hacemos lo siguiente:
Ejecutamos el caso que queremos probar por cada uno de los K arboles
Si la mayoría de los casos devolvió que la categoría final es CATEGORIA-A,
entonces nos quedamos con ese valor de salida.

![[Captura desde 2023-09-27 01-04-27.png]]
