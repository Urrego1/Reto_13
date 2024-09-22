# Reto_13


**1. Desarrollar un algoritmo que imprima de manera ascendente los valores (todos del mismo tipo) de un diccionario.**

```python
def imprimir_valores_ascendentes(diccionario):
    # Obtener los valores del diccionario
    valores = diccionario.values()
    
    # Asegurarse de que todos los valores sean del mismo tipo
    tipo_valor = type(next(iter(valores)))  # Tomar el primer valor para determinar su tipo
    for valor in valores:
        if not isinstance(valor, tipo_valor):
            raise ValueError("Todos los valores del diccionario deben ser del mismo tipo.")
    
    # Ordenar los valores
    valores_ordenados = sorted(diccionario.values())
    
    # Imprimir los valores en orden ascendente
    for valor in valores_ordenados:
        print(valor)

#Ejemplo de uso
diccionario = {
    'a': 3,
    'b': 1,
    'c': 2,
    'd': 6,
    'e': 4,
    'f': 5,
    
}


imprimir_valores_ascendentes(diccionario)
```


**2.Desarrollar una funcion que reciba dos diccionarios como parametros y los mezcle, es decir, que se construya un nuevo diccionario con las llaves de los dos diccionarios; si hay una clave repetida en ambos diccionarios, se debe asignar el valor que tenga la clave en el primer diccionario.**


```python

def mezclar_diccionarios(dic1, dic2):
    # Crear un nuevo diccionario que comienza con las claves y valores del primer diccionario
    nuevo_diccionario = dic1.copy()  # Copiar el primer diccionario

    # Agregar las claves y valores del segundo diccionario
    for clave, valor in dic2.items():
        # Solo agregar la clave si no está ya en el nuevo diccionario
        if clave not in nuevo_diccionario:
            nuevo_diccionario[clave] = valor

    return nuevo_diccionario

# Ejemplo de uso
diccionario1 = {
    'a': 1,
    'b': 2,
}

diccionario2 = {
    'b': 3,
    'c': 4,
}

resultado = mezclar_diccionarios(diccionario1, diccionario2)
print(resultado)

```

**3.Cree un programa que lea de un archivo con dicho JSON y:**

**Imprima los nombres completos (nombre y apellidos) de las personas que practican el deporte ingresado por el usuario.**
**Imprima los nombres completos (nombre y apellidos) de las personas que esten en un rango de edades dado por el usuario.**

