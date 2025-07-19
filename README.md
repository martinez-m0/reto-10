# reto-10
# suma y resta de matriz
    def suma_resta_matrices(matriz1, matriz2, operacion):
        if len(matriz1) != len(matriz2) or len(matriz1[0]) != len(matriz2[0]):
            print("Error: Las matrices deben tener el mismo tamaño para sumar o restar.")
            return None
        resultado = []
        for i in range(len(matriz1)):
            fila = []
            for j in range(len(matriz1[0])):
                if operacion == "suma":
                    fila.append(matriz1[i][j] + matriz2[i][j])
                elif operacion == "resta":
                    fila.append(matriz1[i][j] - matriz2[i][j])
            resultado.append(fila)
        return resultado

    # Ejemplo de uso
    A = [[1, 2], [3, 4]]
    B = [[5, 6], [7, 8]]
    resultado = suma_resta_matrices(A, B, "suma")
    print("Resultado suma:", resultado)
    resultado = suma_resta_matrices(A, B, "resta")
    print("Resultado resta:", resultado)  


# producto de matrices
    def leer_matriz(filas, columnas, nombre="matriz"):
    print(f"Ingrese los valores de la {nombre}:")
    matriz = []
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Elemento [{i+1}][{j+1}]: "))
            fila.append(valor)
        matriz.append(fila)
    return matriz

    def producto_matrices(matriz1, matriz2):
        filas_a = len(matriz1)
        columnas_a = len(matriz1[0])
        filas_b = len(matriz2)
        columnas_b = len(matriz2[0])
        if columnas_a != filas_b:
            print("Error: El número de columnas de la primera matriz debe ser igual al número de filas de la segunda matriz.")
            return None
        resultado = []
        for i in range(filas_a):
            fila_resultado = []
            for j in range(columnas_b):
                suma = 0
                for k in range(columnas_a):
                    suma += matriz1[i][k] * matriz2[k][j]
                fila_resultado.append(suma)
            resultado.append(fila_resultado)
        return resultado

    # Lectura de dimensiones para la primera matriz
    filas_a = int(input("Ingrese el número de filas de la primera matriz: "))
    columnas_a = int(input("Ingrese el número de columnas de la primera matriz: "))
    matriz_a = leer_matriz(filas_a, columnas_a, "primera matriz")


# matriz transpuesta

    def leer_matriz(filas, columnas):
        print("Ingrese los valores de la matriz:")
        matriz = []
        for i in range(filas):
            fila = []
            for j in range(columnas):
                valor = int(input(f"Elemento [{i+1}][{j+1}]: "))
                fila.append(valor)
            matriz.append(fila)
        return matriz

    def transponer_matriz(matriz):
        # Validar que la matriz no esté vacía y tenga filas y columnas
        if not matriz or not matriz[0]:
            print("Error: La matriz debe tener al menos una fila y una columna.")
            return None
        filas = len(matriz)
        columnas = len(matriz[0])
        transpuesta = []
        for j in range(columnas):
            fila_transpuesta = []
            for i in range(filas):
                fila_transpuesta.append(matriz[i][j])
            transpuesta.append(fila_transpuesta)
        return transpuesta

    # Lectura de dimensiones
    filas = int(input("Ingrese el número de filas de la matriz: "))
    columnas = int(input("Ingrese el número de columnas de la matriz: "))

    # Validación de dimensiones
    if filas < 1 or columnas < 1:
        print("Error: La matriz debe tener al menos una fila y una columna.")
    else:
        matriz = leer_matriz(filas, columnas)
        resultado = transponer_matriz(matriz)
        if resultado:
            print("La matriz transpuesta es:")
            for fila in resultado:
                print(fila)

    # Lectura de dimensiones para la segunda matriz
    filas_b = int(input("Ingrese el número de filas de la segunda matriz: "))
    columnas_b = int(input("Ingrese el número de columnas de la segunda matriz: "))
    matriz_b = leer_matriz(filas_b, columnas_b, "segunda matriz")

    # Producto de matrices
    resultado = producto_matrices(matriz_a, matriz_b)
    if resultado:
        print("El producto de las matrices es:")
        for fila in resultado:
            print(fila)

# Suma de una columna dada de una matriz

    def sumar_columna(matriz, columna):
        if columna < 0 or columna >= len(matriz[0]):
            print("Error: Índice de columna fuera de rango.")
            return None
        suma = 0
        for i in range(len(matriz)):
            suma += matriz[i][columna]
        return suma

    # Ejemplo de uso
    A = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    columna = 1
    resultado = sumar_columna(A, columna)
    print(f"Suma de la columna {columna}: {resultado}")


# Suma de una fila dada de una matriz
    def sumar_fila(matriz, fila):
        if fila < 0 or fila >= len(matriz):
            print("Error: Índice de fila fuera de rango.")
            return None
        return sum(matriz[fila])

    # Ejemplo de uso
    A = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    fila = 2
    resultado = sumar_fila(A, fila)
    print(f"Suma de la fila {fila}: {resultado}")
  
