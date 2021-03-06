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
