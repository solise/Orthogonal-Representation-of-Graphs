# Orthogonal Representation of Graphs
Para la utilización de los programas realizados en Matlab y Octave sólo es necesario conocer la forma de los datos de entrada y la forma de los datos de salida para que los algoritmos funcionen correctamente:

1. INPUT: Matriz de adyacencia. La matriz de adyacencia la toma el programa de Matlab de un fichero *.txt*. Para indicar el nombre del fichero donde se quiere tomar la matriz basta indicarlo en la primer línea del fichero *\pruebafichero.m* o *\pruebaficherotabu.m* justamente donde pone

fid = fopen('input.txt','r');

El formato de la matriz de adyacencia del grafo consiste en poner un grafo por cada línea del fichero (puede haber más de uno). Cada grafo comienza por una abrir llave y termina con punto y coma y cerrar llave, es decir, {: : : ; }. Dentro de estas llaves se colocan los 1's
o 0's propios de la matriz de adyacencia separados por un espacio en blanco. Para cambiar a otra fila se utiliza ';'.

Ejemplo de un grafo con 5 vértices:
{0 0 1 1 0;0 0 0 1 1;1 0 0 0 1;1 1 0 0 0;0 1 1 0 0;}

2. OUTPUT: Valores de Rango ortogonal. La salida no se da por pantalla de comandos sino a través de un fichero *.txt*. El nombre del fichero de salida se puede modificar en la segunda línea del fichero *\pruebafichero.m* o *\pruebaficherotabu.m* justamente donde pone

fid2 = fopen('output.txt', 'w');

El formato de salida consta de 2 columnas básicas. La primera es un contador que indica el orden del grafo según estaba colocado en
el fichero de entrada (mantiene el orden de los grafos del fichero de entrada) y la segunda columna indica el valor del rango ortogonal
estimado por el algoritmo.

Ejemplo de salida para un fichero con 3 grafos de 6 vértices
1 4
2 4
3 4

En la práctica, se han utilizado ficheros de tipo [Graph6](https://reference.wolfram.com/language/ref/format/Graph6.html) para trabajar con los grafos debido a que se generaban mediante [Nauty](http://www3.cs.stonybrook.edu/~algorith/implement/nauty/implement.shtml). Para poder convertir estos grafos de tipo .g6 al tipo de matriz de adyacencia que admite el programa se ha realizado también un pequeño programa en *Mathematica* que convierte grafos en formato *.g6* a un fichero *.txt* con el formato de entrada de los algoritmos implementados. También se puede utilizar este programa para pasar de un formato de matriz de adyacencia propio de *Mathematica* al correspondiente válido para ponerlo como entrada de los dos programas desarrollados en este trabajo.
