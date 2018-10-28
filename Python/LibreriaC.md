# Librería en C++

Se puede inportar librerías compartidas de C en python.

## Crear librería en C
Se crea un archivo en C++ con las funciones que se quieran utilizar como el siguiente:

```
// summer/summer.cpp
extern "C" { //Usa convenciones de c para la funcion
double sum_it(double *array, int size) {
    double ret = 0.;
    for(int i=0; i<size; ++i) {
        ret += array[i];
    }
    return ret;
}
}
```

Se debe compilar el código como `.dll` en Windows o `.so` en linux
ej: `gcc -Wall -O3 -shared summer.cpp -o summer.so`

##Crear librería en python
Se crea una librería que hace de _wrapper_  en python como la siguiente:
```
# summer/__init.py__
import ctypes
from ctype import POINTTER,c_double
import os
import sys
import numpy as np

path = os.path.dirname(__file__)
cdll = ctypes.CDLL(os.path.join(path, "summer.dll" if sys.platform.startswith("win") else "summer.so"))
_sum_it = cdll.sum_it
_sum_it.restype = ctypes.c_double

def sum_it(l):
    if isinstance(l, np.ndarray) and l.dtype == np.float64 and len(l.shape)==1:
        # it's already a numpy array with the right features - go zero-copy
        a = l.ctypes.data_as(POINTER(c_double)) #Pasar puntero tipo double
    else:
        # it's a list or something else - try to create a copy
        arr_t = ctypes.c_double * len(l)
        a = arr_t(*l)
    return _sum_it(a, len(l))
```

### Referencias
* https://stackoverflow.com/questions/44415752/passing-big-complex-arrays-from-python-to-c-whats-my-best-option
* https://stackoverflow.com/questions/46037157/trying-to-convert-numpy-array-with-ctypes-to-c-gives-segmentation-fault