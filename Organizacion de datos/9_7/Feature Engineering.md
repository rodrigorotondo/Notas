
Esta etapa incluye cualquier proceso de modificacion de la forma de los datos (Es comun que los datos sufran algun tipo de transformacion)

- El objetivo prinicpal de esta etapa es mejorar el rendimiento de los modelos creados mediante la transformacion de los datos que utilizan


**Algunas tecnicas**:
- Normalizacion
- Discretizacion
- Lograr normalidad
- Imaginacion (generacion de nuevas variables)

# Normalizacion

Se aplica sobre valores numericos
Consiste en escalar los features de manera que puedan ser mapeados a un rango mas pequeño

Por ejemplo: 0 a 1 o -1 a 1

Es principalmente utilizada cuando:
- Las unidades de medidas dificultan la comparación de features.
- Se quiere evitar que atributos con mayores magnitudes tengan pesos muy diferentes al resto

## Normalizacion - Min Max

Funciona al ver cuánto más grande es el valor actual del valor  mínimo del feature y escala esta diferencia por el rango
![[Captura desde 2023-09-19 14-38-00.png]]

Los valores de normalizacion min-max van de 0 a 1

## Normalizacion Z-score

Los valores para un atributo se normalizan en base a su media y desvío  estándar
![[Captura desde 2023-09-19 14-39-49.png]]

Es útil cuando el verdadero mínimo y máximo del atributo no  son conocidos, o cuando hay valores atípicos que dominan la normalización min-max

## Normalizacion - Decimal scaling

Asegura que cada valor normalizado se encuentra entre -1 y 1
![[Captura desde 2023-09-19 14-41-43.png]]

donde **d** representa el numero de digitos en lso valores de la variable con el valor absoluto mas grande


# Ejemplo histograma
![[Captura desde 2023-09-19 14-43-19.png]]
En el grafico podemos ver una distribucion, como quedaria despues de normalizarla?

![[Captura desde 2023-09-19 14-44-39.png]]

luego de la normalizacion la distribucion queda igual

# Transformaciones para lograr normalidad
![[Captura desde 2023-09-19 14-46-06.png]]
No las vamos a usar en la materia



# Discretizacion

Es una técnica que permite dividir el rango de una variable continua en  intervalos.
Se reducen los valores de una variable contínua a un número reducido de etiquetas

## Binning

Se divide a la variable en un número específico de bins
Los criterios de agrupamiento pueden ser por ejemplo:

- Igual-Frecuencia: La misma cantidad de observaciones en un bin

- Igual-Ancho: Definimos rangos o intervalos de clases para cada bin
   
- Cuantiles: Separar en intervalos utilizando Mediana, Cuantiles, Percentiles.

A su vez para cada uno de los agrupamientos podemos hacer:

- Reemplazo por media o mediana
-  Reemplazo por una etiqueta o valor entero

![[Captura desde 2023-09-19 14-49-22.png]]

### Ejemplo
![[Captura desde 2023-09-19 15-27-04.png]]


# Variables dummies - One Hot Encoding

Algunos métodos analíticos requieren que las variables predictoras sean  numéricas

Cuando tenemos categóricos, podemos recodificar la variable categórica  en una o más **variables Dummies**

![[Captura desde 2023-09-19 15-29-13.png]]


# Generacion de nuevas variables

Feature Engineering también es crear variables nuevas

**Por ejemplo**:  
Sumar fuentes de información para calcular la distancia desde un inmueble en venta al espacio verde más cercano