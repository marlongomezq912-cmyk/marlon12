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
    
# Datos de temperaturas: [ciudad][semana][día]
temperaturas = [
    # Ciudad 1
    [
        [30, 31, 32, 33, 34, 35, 36],  # Semana 1
        [31, 32, 33, 34, 35, 36, 37],  # Semana 2
    ],
    # Ciudad 2
    [
        [25, 26, 27, 28, 29, 30, 31],
        [26, 27, 28, 29, 30, 31, 32],
    ],
    # Ciudad 3
    [
        [20, 21, 22, 23, 24, 25, 26],
        [21, 22, 23, 24, 25, 26, 27],
    ]
]

# Nombres de ciudades (para mostrar)
ciudades = ["Ciudad A", "Ciudad B", "Ciudad C"]

# Calcular promedio por ciudad y semana
for i in range(len(temperaturas)):  # Iterar sobre ciudades
    print(f"\nPromedios para {ciudades[i]}:")
    for j in range(len(temperaturas[i])):  # Iterar sobre semanas
        suma = 0
        for k in range(len(temperaturas[i][j])):  # Iterar sobre días
            suma += temperaturas[i][j][k]
        promedio = suma / len(temperaturas[i][j])
        print(f"  Semana {j + 1}: {promedio:.2f} °C")


Promedios para Ciudad A:
  Semana 1: 33.00 °C
  Semana 2: 34.00 °C

Promedios para Ciudad B:
  Semana 1: 28.00 °C
  Semana 2: 29.00 °C

Promedios para Ciudad C:
  Semana 1: 23.00 °C
  Semana 2: 24.00 °C

  # Datos de ejemplo: temperaturas por ciudad y semana
temperaturas = {
    "CiudadA": [[25, 26, 27, 24], [26, 25, 27, 28], [24, 26, 25, 23], [25, 27, 26, 28]],
    "CiudadB": [[30, 31, 29, 30], [31, 30, 29, 28], [30, 30, 30, 29], [29, 30, 31, 32]],
    "CiudadC": [[15, 16, 14, 15], [16, 15, 14, 15], [15, 14, 13, 16], [14, 15, 16, 15]],
}
def calcular_temperatura_promedio(datos_temperatura):
    """
    Calcula la temperatura promedio para cada ciudad.

    Parámetros:
    datos_temperatura (dict): Diccionario con nombres de ciudades como claves y listas de semanas como valores.
                              Cada semana es una lista con temperaturas diarias.

    Retorna:
    dict: Diccionario con el promedio de temperatura para cada ciudad.
    """
    promedios = {}
    
    for ciudad, semanas in datos_temperatura.items():
        suma_total = 0
        conteo = 0
        for semana in semanas:
            suma_total += sum(semana)
            conteo += len(semana)
        promedio = suma_total / conteo if conteo > 0 else 0
        promedios[ciudad] = round(promedio, 2)  # redondeamos a 2 decimales
    
    return promedios
if __name__ == "__main__":
    temperaturas = {
        "CiudadA": [[25, 26, 27, 24], [26, 25, 27, 28], [24, 26, 25, 23], [25, 27, 26, 28]],
        "CiudadB": [[30, 31, 29, 30], [31, 30, 29, 28], [30, 30, 30, 29], [29, 30, 31, 32]],
        "CiudadC": [[15, 16, 14, 15], [16, 15, 14, 15], [15, 14, 13, 16], [14, 15, 16, 15]],
    }

    resultado = calcular_temperatura_promedio(temperaturas)
    print("Promedio de temperaturas por ciudad:")
    for ciudad, promedio in resultado.items():
        print(f"{ciudad}: {promedio}°C")
        # Función para calcular el descuento
def calcular_descuento(monto_total, porcentaje_descuento=10):
    """
    Calcula el descuento aplicado a una compra.

    :param monto_total: float, monto total de la compra
    :param porcentaje_descuento: float, porcentaje de descuento (por defecto 10%)
    :return: float, monto del descuento
    """
    descuento = monto_total * (porcentaje_descuento / 100)
    return descuento


# Programa principal
if __name__ == "__main__":
    # Primera llamada: solo monto (usa el 10% por defecto)
    monto1 = 200
    descuento1 = calcular_descuento(monto1)
    total1 = monto1 - descuento1

    print(f"Compra: ${monto1}")
    print(f"Descuento aplicado (10%): ${descuento1}")
    print(f"Monto final a pagar: ${total1}\n")

    # Segunda llamada: monto y porcentaje definido por el usuario
    monto2 = 350
    descuento2 = calcular_descuento(monto2, 15)
    total2 = monto2 - descuento2

    print(f"Compra: ${monto2}")
    print(f"Descuento aplicado (15%): ${descuento2}")
    print(f"Monto final a pagar: ${total2}")
Compra: $200
Descuento aplicado (10%): $20.0
Monto final a pagar: $180.0

Compra: $350
Descuento aplicado (15%): $52.5
Monto final a pagar: $297.5
# Crear un diccionario llamado 'informacion_personal' con información ficticia
informacion_personal = {
    "nombre": "Lucía Martínez",
    "edad": 28,
    "ciudad": "Quito",
    "profesion": "Ingeniera Civil"
}
informacion_personal["ciudad"] = "Guayaquil"  # Cambiamos de Quito a Guayaquil


informacion_personal["cargo"] = "Supervisora de obra"


if "telefono" not in informacion_personal:
    informacion_personal["telefono"] = "0999999999"  # Número ficticio

if "edad" in informacion_personal:
    del informacion_personal["edad"]

print("Diccionario final con la información personal:")
print(informacion_personal)
Diccionario final con la información personal:
{
    'nombre': 'Lucía Martínez',
    'ciudad': 'Guayaquil',
    'profesion': 'Ingeniera Civil',
    'cargo': 'Supervisora de obra',
    'telefono': '0999999999'
}






