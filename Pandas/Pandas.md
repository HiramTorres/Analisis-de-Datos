# Pandas

Para importar el paquete Pandas, podemos hacer uso de la siguiente línea de código:

```python
import pandas as pd
```
## Series 
Con ```pd.Series``` podemos crear una serie de datos, que es una lista de valores que se pueden acceder por índices.

```python
s = pd.Series([1,2,3,4,5])

out: 
0    1
1    2
2    3
3    4
dtype: int64
```

```python
pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'], dtype='float64', name='series')
```

Podemos también utilizar diccionarios para crear una serie de datos: 

```python
colores = {
    'rojo': '100',
    'azul': '200',
    'verde': '300'
    }
```

    
```python
pd.Series(colores)

out: 
rojo    100
azul    200
verde   300
dtype: int64
```

Podemos ingresar directamente al valor de cada elemento de la serie de la siguiente forma: 

```python 
a = pd.Series(colores)
a['rojo']

out: 100
```	
---

## isnull - notnull

```python
import numpy as np

a = pd.Series([1,2,np.nan,np.nan,3,4,np.nan,5])
out:
0    1.0
1    2.0
2    NaN
3    NaN
4    3.0
5    4.0
6    NaN
7    5.0
dtype: float64
```