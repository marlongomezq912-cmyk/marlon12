# marlon12
trabajo de fundamentos de la programacion
# busqueda_matriz.py

def buscar_valor(matriz, valor_buscado):
    for i in range(len(matriz)):
        for j in range(len(matriz[i])):
            if matriz[i][j] == valor_buscado:
                return True, (i, j)
    return False, None

# Definición de matriz 3x3
matriz = [
    [4, 8, 15],
    [16, 23, 42],
    [1, 2, 3]
]

# Mostrar la matriz
print("Matriz:")
for fila in matriz:
    print(fila)

# Ingreso del valor a buscar
valor = int(input("Ingresa el valor a buscar en la matriz: "))

# Llamada a la función
encontrado, posicion = buscar_valor(matriz, valor)

# Resultado
if encontrado:
    print(f"✅ Valor {valor} encontrado en la fila {posicion[0]}, columna {posicion[1]}.")
else:
    print(f"❌ Valor {valor} no encontrado en la matriz.")
    # ordenar_fila.py
ordenar_fila.py
def bubble_sort(fila):
    n = len(fila)
    for i in range(n):
        for j in range(0, n - i - 1):
            if fila[j] > fila[j + 1]:
                fila[j], fila[j + 1] = fila[j + 1], fila[j]
    return fila

# Matriz de ejemplo 3x3
matriz = [
    [12, 9, 4],
    [7, 5, 11],
    [3, 14, 2]
]

print("Matriz original:")
for fila in matriz:
    print(fila)

# Selección de la fila a ordenar
indice = int(input("Ingresa el índice de la fila a ordenar (0, 1 o 2): "))

# Validación de índice y ordenación
if 0 <= indice < len(matriz):
    matriz[indice] = bubble_sort(matriz[indice])
    print("\nMatriz con la fila ordenada:")
    for fila in matriz:
        print(fila)
else:
    print("❌ Índice de fila inválido.")


