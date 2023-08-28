
## Distribucion continua
![[Captura desde 2023-08-23 17-16-06.png]]
 


es de distribucion continua porque el soporte continuo aumenta en un rango continuo  
la cantidad es discreta.


![[Captura desde 2023-08-23 17-18-30.png]]
el error aqui es que este soporte es discreto, los meses del año son discretos (mes 1, mes 2, mes 3) si fuese de tiempo, seria distinto

## Bins/Histograma

![[Captura desde 2023-08-23 17-21-10.png]]

por un lado agregar bins (barras) permite ver en mejor las cantidades de personas encuestadas, pero tambien complejiza el grafico

![[Captura desde 2023-08-23 17-23-31.png]]

aqui se pueden observar distintos tipos de distribuciones

### Errores comunes
![[Captura desde 2023-08-23 17-24-52.png]]

en los graficos se deberia empezar de 0, no en un valor arbitrario

![[Captura desde 2023-08-23 17-25-42.png]]

elegir un numero apropiado de bins es importante

![[Captura desde 2023-08-23 17-53-24.png]]

los limites de los bins deben ser interpretables, no deben caer en lugares al azar

![[Captura desde 2023-08-23 17-54-40.png]]

## Density plot
#plot 
![[Captura desde 2023-08-23 17-56-46.png]]
Un gráfico de densidad visualiza la distribución de datos en un intervalo o período de tiempo continuo. Este gráfico es una variación de un Histograma que usa el suavizado de cerner para trazar valores, permitiendo distribuciones más suaves al suavizar el ruido. Los picos de un gráfico de densidad ayudan a mostrar dónde los valores se concentran en el intervalo.  
  
Una ventaja de los gráficos de densidad sobre los histogramas es que son mejores para determinar la forma de distribución porque no se ven afectados por el número de contenedores utilizados (cada barra utilizada en un histograma típico). Un histograma que consta de solo 4 compartimientos no producirá una forma de distribución lo suficientemente distinguible como lo haría un histograma de 20 compartimientos. Sin embargo, con los gráficos de densidad esto no es un problema.  
  
  
• La densidad a la izquierda es poco interpretable  
• ya no sabemos las cantidades  
  
• se suavizan los bordes y eso no tiene sentido, hay alguien que cobre menos de 0?