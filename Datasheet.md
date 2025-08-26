
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






