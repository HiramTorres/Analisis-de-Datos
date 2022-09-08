# Numpy 

Podemos crear arreglos de objetos iterables utilizando array 

```
import numpy as np 

lista = [1,2,3,4]

np.array(lista)

out: array([lista])

```

### Atributos 

* Dimesiones
Para saber la cantidad de dimensiones que tiene un arreglo podemos utilizar el 
atributo de ``` lista.ndim```

* Cantidad de objetos que posee el arreglo
Se puede ver con usando ``` lista.size```

* Tamaño en bytes de cada elemento dentro del arreglo
Usando: ``` lista.itemsize```

* Conocer la forma del arreglo
Utilizando: ``` lista.shape```


---

Para hacer un arreglo de numpy se debe agregar con el comando ```np.array()```
Ejemplo: 
```
n = np.array([1,2,3,4,5])
```

Para crear un arreglo apartir de un rango predefinido podemos utilizar el comando ```np.arange(n,n-1)``` puede llevar un tercer argumento el cual dice los saltos que da la cuenta
ejemplo: 
```
n = np.arange(10,100,2) # Rango de 10 al 100-1 con saltos de 2 en 2 
```

Podemos también crear arreglos de puros ceros con el comando ```np.zeros(n)``` donde "n" es la cantidad de ceros.

y al igual que ceros podemos itilizar ```np.ones(n)``` que es lo mismo pero con 1 

ejemplo:
```
In [12]: np.zeros(20)
Out[12]:
array([0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0., 0.,
       0., 0., 0.])

In [13]: np.ones(20,dtype=int)
Out[13]: array([1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1])
```

Podemos generar un arreglo de n cantidad de numero aleatorios con la función: ```np.random.randint(n,n-1,p)``` donde n y n-1 son los limites de donde se tomaran los numeros y p es la longitud maxima que soporta dicho arreglo 
ejemplo: 
```
n [14]: np.random.randint(0,101,50)
Out[14]:
array([15, 81, 59, 77, 53, 30, 84, 31, 57, 79, 69, 33, 34, 82, 27, 76, 94,
        1, 74, 48, 79, 94, 44, 80, 24, 26,  0, 92, 97, 26, 33,  8, 55,  7,
       86, 31, 47, 56, 58, 84, 29, 37, 92, 81, 83, 46, 40, 26, 25, 35])

```

Para visualizar los datos dentro de una arreglo podemos llamarlos a través de llaves de esta forma: 
```
In [18]: datos = np.random.randint(0,10,5)

In [19]: datos[0]
Out[19]: 2

In [20]: datos[-1]
Out[20]: 9

In [22]: datos[3]
Out[22]: 2
```

También se pueden cambiar los valores de los arreglos utilizando esta forma:
```
In [23]: datos[1]=100

In [24]: datos
Out[24]: array([  2, 100,   8,   2,   9])
```

### Subarreglos
Se pueden generar subarreglos de los ya establecidos, y estos tomandolos como las listas en python, el primer argumento va el inicio el segundo el final y el tercero la cantidad de saltos que gustemos de ```n[inicio:fin:saltos]``` todo separado con doble punto ejemplo:
```
In [25]: n = np.random.randint(0,20,20)

In [26]: n
Out[26]:
array([ 7, 12,  1, 10,  7,  3, 13, 14, 11,  1,  1, 17,  0,  9, 13, 13,  0,
        8,  6,  0])
In [28]: n[3:10:2]
Out[28]: array([10,  3, 14,  1])

```

Para obtener un subarreglo solo con ciertos indices seleccionados, se puede obtener con: 
```
In [29]: n
Out[29]:
array([ 7, 12,  1, 10,  7,  3, 13, 14, 11,  1,  1, 17,  0,  9, 13, 13,  0,
        8,  6,  0])

In [30]: n[[0,1,3,7]]
Out[30]: array([ 7, 12, 10, 14])
```
Otra forma en la cual se pueden obtener es con lista de tipo booleno. Ejemplo: 
```
In [33]: n = np.random.randint(0,100,7)

In [34]: n
Out[34]: array([53, 42, 10, 67, 70, 98, 59])

In [35]: n[[True,False,False,True,False,True,True]]
Out[35]: array([53, 67, 98, 59])
```
Tomando en cuenta que la longitud del arreglo en booleano de ser igual a la longitud del arreglo n 

---

## Vectorizar funciones 

Para vectorizar una función lo que debemos de hacer es: 
```
In [42]: def operacion(valor):
    ...:     return (valor**2)+2
    ...:

In [43]: for valor in n:
    ...:     print(operacion(valor))
    ...:
2811
1766
102
4491
4902
9606
3483
```

Una vez obtenida la lista de la funcion la cual queremos vectorizar 
```
In [44]: vector = np.vectorize(operacion)

In [45]: vector
Out[45]: <numpy.vectorize at 0x1fa0960e370>

In [46]: vector(n)
Out[46]: array([2811, 1766,  102, 4491, 4902, 9606, 3483])
```

> Se puede tambien utilizar la función ```lambda```.Las expresiones lambda se usan idealmente cuando necesitamos hacer algo simple y estamos más interesados en hacer el trabajo rápidamente en lugar de nombrar formalmente la función. Las expresiones lambda también se conocen como funciones anónimas.
Las expresiones lambda en Python son una forma corta de declarar funciones pequeñas y anónimas (no es necesario proporcionar un nombre para las funciones lambda).
```
In [48]: square = lambda x: x**2

In [49]: square(2)
Out[49]: 4
```
---

## Matrices

Las matrices son creadas con arreglos de *numpy* y son listas con listas por ejemplo: 
```
A = np.array([
[1,2,3,4,5],
[10,20,30,40,50],
[100,200,300,400,500]
])

In [10]: A
Out[10]:
array([[  1,   2,   3,   4,   5],
       [ 10,  20,  30,  40,  50],
       [100, 200, 300, 400, 500]])
```
Para saber las dimensiones que tiene un arreglo, podemos hacer uso del atributo ```.ndim```
por ejemplo: 
```
In [11]: A.ndim
Out[11]: 2
```
y el atributo ```.shape``` 
```
In [12]: A.shape
Out[12]: (3, 5)
```
> El axi0 = Filas 
El axi1 = Columnas

Por ejemplo: 
``` 
In [13]: A
Out[13]:
array([[  1,   2,   3,   4,   5],
       [ 10,  20,  30,  40,  50],
       [100, 200, 300, 400, 500]])


In [14]: A[0][0] # Axi0 = 0 y axi1 = 0
Out[13]: 1

In [15]: A[1][2] # Axi0 = 1 y Axi1 = 2
Out[15]: 30

``` 
Asi podemos obtener elementos de la matriz , aunque también hay otra forma: ```A[axi0,axi1]```
```
In [16]: A[1,2]
Out[16]: 30

In [17]: A[2,4]
Out[17]: 500
```
Para pbtener subconjuntos de las matrices se puede utilizando la forma: 
```
In [18]: A[1,:4]
Out[18]: array([10, 20, 30, 40])

In [19]: A[:2,2:]
Out[19]:
array([[ 3,  4,  5],
       [30, 40, 50]])
```
También se pueden seleccionar valores en especifico por ejemplo: 
```
In [21]: A
Out[21]:
array([[  1,   2,   3,   4,   5],
       [ 10,  20,  30,  40,  50],
       [100, 200, 300, 400, 500]])

In [22]: A[1,[2,4]] # Sacar solo ciertos valores especificos 
Out[22]: array([30, 50])
```

## Métodos de agregación 

 Con el método ```.std()``` podemos obtener la desviación estandar del arreglo
 ```
In [23]: A.std()
Out[23]: 157.21323099535866
 ```

Otro método es ```.sum()```con el cual podemos saber la suma de todo el arreglo 
```
In [24]: A.sum()
Out[24]: 1665
```
Conocer también el valor ```.min()```o el valor ```.max()```
```
In [25]: A.min()
Out[25]: 1

In [26]: A.max()
Out[26]: 500
```
Para saber el primerdio ```.mean()```
```
In [27]: A.mean()
Out[27]: 111.0
```

## Transponer las matrices 

Solo utilizando esta forma ```.T```
```
In [28]: A.T
Out[28]:
array([[  1,  10, 100],
       [  2,  20, 200],
       [  3,  30, 300],
       [  4,  40, 400],
       [  5,  50, 500]])
```
