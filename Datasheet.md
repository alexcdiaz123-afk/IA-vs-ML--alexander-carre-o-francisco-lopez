
 # A) NumPy – Creación y manipulación de arreglos
(arrays, reshape, concatenar, operaciones básicas):

# creacion de arrays:

import numpy as np

arr = np.array([1, 2, 3, 4, 5])
print(arr)

matriz = np.array([[1, 2, 3], [4, 5, 6]])
print(matriz)

salida:

[1 2 3 4 5]
[[1 2 3]
 [4 5 6]]

 # Reshape (cambio de forma):

 arr = np.arange(12)  
print("Array original:", arr)

matriz = arr.reshape(3, 4)  
print("Array reshapeado a 3x4:\n", matriz)

salida:

Array original: [ 0  1  2  3  4  5  6  7  8  9 10 11]
Array reshapeado a 3x4:
 [[ 0  1  2  3]
 [ 4  5  6  7]
 [ 8  9 10 11]]

 # Concatenar:

 a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
concatenado = np.concatenate((a, b))
print("Concatenación:", concatenado)

salida:

Concatenación: [1 2 3 4 5 6]

 # Operaciones básicas:

 x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

print("Suma:", x + y)
print("Multiplicación:", x * y)
print("Cuadrado:", x**2)

salida:

Suma: [5 7 9]
Multiplicación: [ 4 10 18]
Cuadrado: [1 4 9]

# B)NumPy – Operaciones estadísticas y funciones avanzadas:
import numpy as np
# Estadistica (mean, std, sum)#
matriz1 = np.array([2,2,2,2,2,3])

mean = np.mean(matriz1)
std = np.std(matriz1)
sum = np.sum(matriz1)

print("la media es", matriz1)
print("la desviacion es ", std)
print("la suma tota es ", sum)

salida: 

la media es [2 2 2 2 2 3]
la desviacion es  0.3726779962499649
la suma tota es  13

# Range, linspace

arange = np.arange(0,21,1)
linspace = np.linspace(0,1,10)

print("usando arange ", arange)
print("usando linspace ", linspace)

salida:

usando arange  [ 0  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20]
usando linspace  [0.         0.11111111 0.22222222 0.33333333 0.44444444 0.55555556
 0.66666667 0.77777778 0.88888889 1.  

 # Random
random =np.random.rand(2,2)
print("Una matriz random:\n", random)

salida:

Una matriz random:
 [[0.66039606 0.02429358]
 [0.23859785 0.80662667]]

# Algebra lineal-Producto-Trasposicion-Inversa
matrizA =np.array([[2,1],[3,3]])
matrizB = np.array([[4,4],[8,8]])

dot =np.dot(matrizA, matrizB)
transpose = np.transpose(matrizB)
linalg = np.linalg.inv(matrizA)

print("El producto punto es\n ", dot)
print("La transpuesta es\n ", transpose)
print("La inversa es\n ", linalg)

salida:

El producto punto es
  [[16 16]
 [36 36]]
La transpuesta es
  [[4 8]
 [4 8]]
La inversa es
  [[ 1.         -0.33333333]
 [-1.          0.66666667]]

# C) Pandas – Creación y manipulación de DataFrames y Series:

# Crear una Serie:

import pandas as pd

serie = pd.Series([10, 20, 30, 40], index=["a", "b", "c", "d"])
print(serie)

salida:

a    10
b    20
c    30
d    40
dtype: int64

#  Crear un DataFrame:

data = {
    "Nombre": ["Ana", "Luis", "Carlos"],
    "Edad": [23, 30, 35],
    "Ciudad": ["Bogotá", "Medellín", "Cali"]
}
df = pd.DataFrame(data)
print(df)

salida:

    Nombre    Edad    Ciudad
0     Ana      23    Bogotá
1    Luis      30    Medellín
2    Carlos    35    Cali

df = pd.DataFrame({
    "Producto": ["Laptop", "Celular", "Tablet"],
    "Precio": [2000, 800, 1200]
})
print(df)

salida:

    Producto  Precio
0   Laptop    2000
1   Celular     800
2   Tablet    1200

# Seleccionar columnas:

print("Columna Precio:")
print(df["Precio"])

salida:

Columna  Precio:
0        2000
1        800
2        1200
Name: Precio, dtype: int64

# Ver tipos de datos:

print(df.dtypes)

salida:

Producto    object
Precio       int64
dtype: object

# D) Pandas – Operaciones avanzadas en DataFrames (filtros, groupby, merge/join, manejo de valores nulos, exportación/importación).

data ={
    'Nombre': ['Ana', 'Luis'],
    'Edad':  [20,45],
    'Ciudad': ['Bogota','Chia'],
    'Puntaje': [None, 70],
}
df= pd.DataFrame(data)
print(df)

salida:

Nombre  Edad  Ciudad  Puntaje
0    Ana    20  Bogota      NaN
1   Luis    45    Chia     70.0

# Nulos (isnull-fillna-dropna)


print(df.isnull())


df_sin_nulos = df.dropna()


df_filled = df.fillna({
    'Nombre': 'Desconocido',
    'Edad': df['Edad'].mean(),
    'Puntaje': df['Puntaje'].mean()
})
print(df_filled)

salida:

 Nombre   Edad  Ciudad  Puntajes
0   False  False   False      True
1   False  False   False     False
  Nombre  Edad  Ciudad  Puntajes
0    Ana    20  Bogota      70.0
1   Luis    45    Chia      70.0

# Filtros (loc, condicionales)


filtro_puntaje = df_filled[df_filled['Puntajes'] > 50]
print(filtro_puntaje)


filtro_ciudad = df_filled[df_filled['Ciudad'] == 'Bogota']
print(filtro_ciudad)

salida: 

Nombre  Edad  Ciudad  Puntajes
0    Ana    20  Bogota      70.0
1   Luis    45    Chia      70.0
  Nombre  Edad  Ciudad  Puntajes
0    Ana    20  Bogota      70.0

# Agrupar datos Grouby

grupo = df_filled.groupby('Ciudad')['Puntajes'].mean()
print(grupo)

salida: 

Ciudad
Bogota    70.0
Chia      70.0
Name: Puntajes, dtype: float64

# Merge/ jois entre los DataFrames

info_extra = pd.DataFrame({
    'Ciudad': ['Madrid', 'Sevilla', 'Valencia'],
    'Región': ['Centro', 'Sur', 'Este']
})
df_completo = pd.merge(df_filled, info_extra, on='Ciudad', how='left')
print(df_completo)

salida:

Nombre  Edad  Ciudad  Puntajes Región
0    Ana    20  Bogota      70.0    NaN
1   Luis    45    Chia      70.0    NaN

# Exportar he Imporar

df_completo.to_csv('datos_exportados.csv', index=False)

df_importado = pd.read_csv('datos_exportados.csv')
print(df_importado)

salida :

Nombre  Edad  Ciudad  Puntajes  Región
0    Ana    20  Bogota      70.0     NaN
1   Luis    45    Chia      70.0     NaN



