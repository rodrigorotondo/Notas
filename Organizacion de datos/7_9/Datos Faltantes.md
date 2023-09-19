# Tipos

No son solo NaNs hay diferentes mecanismos, los estandares son:

- Missing completely at random MCAR 
- Missing Not At Random MNAR
- Missing At Random MAR 

## Missing completely at random MCAR

En este caso la razón de la falta de datos es ajena a los datos mismos.  
No existen relaciones con la variable misma donde se encuentran los datos faltantes, o con las restantes variables en el dataset que expliquen porque faltan.

## Missing Not At Random MNAR

La razón por la cual faltan los datos depende precisamente de los mismos datos que hemos recolectado (está relacionado con la razón por  la que falta)

  
**Ejemplo**: Cada vez que una variable debería tener un valor entre 10 y 20, el mismo no se encuentra registrado (independientemente de los valores que tomen las variables restantes)

**Ejemplo2:** universitarios privados no quieren decir cuanto cobran, entonces se puede inferir su ingreso de la cuota de la universidad

## Missing At Random MAR

Punto intermedio entre los dos anteriores. 

  

La causa de los datos faltantes no depende de estos mismos datos faltantes, pero puede estar relacionada con otras variables del dataset.

Por ejemplo: encuestas mal diseñadas


# Estrategias para trabajar con datos faltantes

## Eliminar registros o variables

Si la eliminación de un subconjunto disminuye significativamente la utilidad  de los datos, la eliminación del caso puede no ser efectiva

(No se recomienda en situaciones que no sean MCAR)

## Imputar datos
Utilizar métodos de relleno de faltantes.

### Sustitucion de casos

Se reemplaza con valores no observados. 
Debería ser  realizado por un experto en esos datos

### Se reemplaza utilizando la medida calculada de los  valores presentes. 

Algunas desventajas:

- La varianza estimada de la nueva variable no es válida porque está atenuada  por los valores repetidos
   
- Se distorsiona la distribución

- Las correlaciones que se observen estarán deprimidas debido a la repetición  de un solo valor constante
### Imputación Cold Deck
Selecciona valores o usa relaciones obtenidas de  fuentes distintas de la base de datos actual
![[Captura desde 2023-09-19 14-16-48.png]]
Aqui si no sabemos el barrio, usamos la longitud y latitud para reconstruirlo

### Imputacion Hot Deck
Se reemplazan los faltantes con valores obtenidos de registros que son  los más similares.

(Hay que definir que es similar, K vecinos más cercanos puede servir)
![[Captura desde 2023-09-19 14-21-10.png]]

### Imputacion por regresion

El dato faltante es reemplazado con el valor predicho por un modelo de regresión
![[Captura desde 2023-09-19 14-23-39.png]]


### MICE Multivariate Imputation by CHained Equations

Trabaja bajo el supuesto de que el origen de los faltantes es Missing At Random  (MAR)

Es un proceso de imputación de datos faltantes iterativo, en el cual, en cada iteración cada valor faltante de cada variable se predice en función de las variables restantes.

Esta iteración se repite hasta que se encuentre convergencia en los valores.

Por lo general 10 iteraciones es suficiente.

(En cada iteración genera un dataset)
![[Captura desde 2023-09-19 14-26-35.png]]

![[Captura desde 2023-09-19 14-27-27.png]]