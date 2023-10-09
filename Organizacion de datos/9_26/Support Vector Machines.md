![[Captura desde 2023-10-02 15-27-15.png]]![[Captura desde 2023-10-02 15-27-35.png]]
# Clasificadores basados en el margen, respecto del umbral
![[Captura desde 2023-10-02 15-46-37.png]]![[Captura desde 2023-10-02 15-47-30.png]]
![[Captura desde 2023-10-02 15-48-24.png]]
Trazamos el umbral

![[Captura desde 2023-10-02 15-48-32.png]]![[Captura desde 2023-10-02 15-48-45.png]]![[Captura desde 2023-10-02 15-48-51.png]]![[Captura desde 2023-10-02 15-49-00.png]]![[Captura desde 2023-10-02 15-49-06.png]]![[Captura desde 2023-10-02 15-49-18.png]]![[Captura desde 2023-10-02 15-49-30.png]]![[Captura desde 2023-10-02 15-49-35.png]]![[Captura desde 2023-10-02 15-49-40.png]]![[Captura desde 2023-10-02 15-49-49.png]]![[Captura desde 2023-10-02 15-49-58.png]]![[Captura desde 2023-10-02 15-50-05.png]]![[Captura desde 2023-10-02 15-50-10.png]]![[Captura desde 2023-10-02 15-50-16.png]]![[Captura desde 2023-10-02 15-50-23.png]]![[Captura desde 2023-10-02 15-50-30.png]]![[Captura desde 2023-10-02 15-50-38.png]]![[Captura desde 2023-10-02 15-50-45.png]]![[Captura desde 2023-10-02 15-51-57.png]]![[Captura desde 2023-10-02 15-52-05.png]]![[Captura desde 2023-10-02 15-54-05.png]]![[Captura desde 2023-10-02 15-54-09.png]]![[Captura desde 2023-10-02 15-54-14.png]]![[Captura desde 2023-10-02 15-54-17.png]]![[Captura desde 2023-10-02 15-54-21.png]]![[Captura desde 2023-10-02 15-54-38.png]]![[Captura desde 2023-10-02 15-54-57.png]]![[Captura desde 2023-10-02 15-55-02.png]]![[Captura desde 2023-10-02 15-55-05.png]]![[Captura desde 2023-10-02 15-55-08.png]]
![[Captura desde 2023-10-04 12-54-02.png]]
## como mejorar?

Los Maximal Margin Classifiers y los Support Vector Classifiers (clasificadores de márgenes blandos) no pueden clasificar problemas que no son linealmente separables.

# Support vector machines


![[Captura desde 2023-10-04 12-54-02.png]]![[Captura desde 2023-10-04 12-54-22.png]]![[Captura desde 2023-10-04 12-54-37.png]]![[Captura desde 2023-10-04 12-55-38.png]]![[Captura desde 2023-10-04 12-55-53.png]]
## SVM: Kernel polinomico
![[Captura desde 2023-10-04 12-56-18.png]]![[Captura desde 2023-10-04 12-56-31.png]]![[Captura desde 2023-10-04 12-56-43.png]]![[Captura desde 2023-10-04 12-56-55.png]]

Con d=4, repite el proceso agregando una dimensión adicional. Lo mismo para cualquier d=n.

**En resumen**: 

1. El Kernel Polinómico de SVM sistemáticamente incrementa las dimensiones seteando d, desde 1 (o el valor base de las observaciones) hasta el valor del parámetro.

2. Calcula en cada caso las relaciones entre las observaciones para encontrar un hiper-plano que parta el conjunto en 2. 

3. Usando validación cruzada, en cada caso calcula el error y se queda con el mejor d.
# SVM Kernel Radial

![[Captura desde 2023-10-04 13-01-02.png]]

![[Captura desde 2023-10-04 13-01-20.png]]SVM: The kernel trick

Las Kernel Functions, sólo calculan la relación entre pares de observaciones como si estuviesen en otra dimensión, pero no realizan una verdadera transformación del espacio.

Este truco del Kernel, reduce la cantidad de tiempo de cómputo necesario ya que evita toda la matemática relacionada a la transformación del espacio.

Además permite que se realicen los cálculos del Kernel Radial en infinitas dimensiones.