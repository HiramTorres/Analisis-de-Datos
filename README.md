# Repositorio de curso introducción al análisis de datos con Python <img src="https://upload.wikimedia.org/wikipedia/commons/c/c3/Python-logo-notext.svg" alt="drawing" width="30"/>  

### _Para este curso se utlizan varias librerias como numpy y pandas ademas de que se trabaja desde ipython_ 

Se inicializa un entorno con el comando de
 ```python -m venv "nombre del archivo"```

y se activa el entorno con el comando 
```env\scripts\activate```

Para desactivar el entorno solo hace falta teclear 
```deactivate```


## Comandos magicos 

> Estos comando se activan con el caracter de % 
- ```%time``` para saber cuanto tiempo le toma a la tarea finalizar por ejemplo:
```
 def super_task():
    import time 
    time.sleep(5)
    print("hola mundo, desde la funcion super_task")
super_task()

%time super_task()

out: 
hola mundo, desde la funcion super_task
Wall time: 5.01 s
```

- ``` %reset``` se limpiara el namespace que se ha construido hasta el momento y borrará variables, paquetes, métodos, funciones, clases, etc. 

```
 %reset

out: 
Once deleted, variables cannot be recovered. Proceed (y/[n])?
```

- ```%run ``` es un comando para ejecutar scrips de python
- ```%who```es para ver todas las varables previamente declaradas

- ``` %load "name file "``` es para imprimir el código que este dentro del scrip de python a ejecutar 
 ``` 
 %load hola_mundo.py

 out:
 print('hola mundo')
 ```
 >Este comando resulta muy útil en casos donde queramos experimentar un poco con el código del archivo, realizando una que otra modificación.
Es importante mencionar que el comando solo carga el contenido del archivo, **si en dado caso modificamos este, los cambios no se verán reflejados en el archivo original.**


 __No son los unicos comandos, pero son probablemente los más importantes__



### Para visualizar el contenido de un archivo.py
Se puede utilizar el comando ```%pycat``` y seguido se coloca el nombre del archivo del cual se quiere saber su contenido
```
%pycat ejemplo.py
```

También se puede visualizar archivos no necesariamente .py con el comando ```%cat```
```
%cat ejemplo.py
```


Un comando que nos ayuda a conocer la lista de comandos es: ```%lsmagic```






## Crear archivos con el Shell interactivo de Ipython

> Ingresanos desde la terminal tecleando ipython y entramos

Podemos crear cualquier sentencia en el lenguaje de python por ejemplo: 

``` 
def suma (a, b):
"""retorna la suma de  a + b """
    return a + b 

a = 10 
b = 30

resultado = suma(a,b)
print(f'El resultado de sumar {a} + {b} es igual a {resultado}')

out :
El ressultado de suma 10 + 20 es igual a 30 


```   
- Con el comando ``` %save "nombre del archivo.py" "lineas que queremos almacenar"``` podemos almacenar líneas de código en un archivo. 

ejemplo: 
   ```%save demo.py 1-9```


- Para almacenar nuevas lineas de código dentro de un archivo se utiliza el comando ```%save -a "nombre del archivo" "líneas a almacenar"```

ejemplo: 
```%save demo.py 12-18```

Utilizando un guión podemos agregar las líneas de código que estan en ese rango, pero si queremos no agregar algunas lineas especificas, podemos utlizarlo con un espacio
ejemplo:
```%save demo.py 12 14 ```
Así almacenará las líneas 12 y 14 solamente 

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

Podemos generar un arreglo de n cantidad de numero aleatorios con la función: ```np.random.randint(n,n-1,p) donde n y n-1 son los limites de donde se tomaran los numeros y p es la longitud maxima que soporta dicho arreglo 
ejemplo: 
```
n [14]: np.random.randint(0,101,50)
Out[14]:
array([15, 81, 59, 77, 53, 30, 84, 31, 57, 79, 69, 33, 34, 82, 27, 76, 94,
        1, 74, 48, 79, 94, 44, 80, 24, 26,  0, 92, 97, 26, 33,  8, 55,  7,
       86, 31, 47, 56, 58, 84, 29, 37, 92, 81, 83, 46, 40, 26, 25, 35])

```

Para visualizar los datos dentro de una arreglo podemos llamarlos atravez de llaves de esta forma: 
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

