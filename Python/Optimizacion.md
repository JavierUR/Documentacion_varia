# Optimización de código

Existen diferentes métodos para optimizar el codigo de python.

## Herramientas
Primero es necesario Encontrar que parte del código es lenta. Se pueden usar las siguientes herramientas con ipython:

### %time y %timeit
Permiten saber cuanto se demora en ejcecutar un script o funcion

%time corre el código una sola vez

* uso 
```
%time function
```
%timeit entrega el tiempo promedio de ejecucion

* uso
```
%timeit function()
```

### %prun y %lprun
Permiten analizar el codigo en más detalle
%prun permite ver cuanto timepo ocupan las funciones llamadas

* uso
```
%prun function
```
%lprun permite ver cuanto se demora cada linea del programa, especificando una funcion

* Instalacion
{pip|conda} install line-profiler
* Uso:

Cargar extensión
```
%load_ext line_profiler
```
Testear una función
```
%lprun -f function function()
```
Tambien puede ser útil guardar el resultado en un archivo
```
%lprun -s -f function -T file.log function()
```

## Métodos
### Uso de código C
Se puede aumetnar la velocidad usando implementando directamente un código en C++ e importarlo a python, o usar un método dinámico como Numba o Cython.

#### Links/Referencias
* http://pynash.org/2013/03/06/timing-and-profiling/
* https://jakevdp.github.io/blog/2015/02/24/optimizing-python-with-numpy-and-numba/
* https://flothesof.github.io/optimizing-python-code-numpy-cython-pythran-numba.html
* https://stackoverflow.com/questions/44415752/passing-big-complex-arrays-from-python-to-c-whats-my-best-option
