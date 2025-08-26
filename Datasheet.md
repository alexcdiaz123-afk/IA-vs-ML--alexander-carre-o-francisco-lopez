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



