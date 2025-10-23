---
layout: post
title: "Lección 4: Tipos de datos complejos"
date: 2022-07-04
categories: python tutorial
---

# Lección 4: Tipos de datos complejos

En esta lección aprenderás a trabajar con listas, tuplas, conjuntos y diccionarios.

## Listas (list)

- Ordenadas, mutables, permiten duplicados.

```python
nums = [1, 2, 3]
nums.append(4)
nums[0] = 10
nums.extend([5, 6])
nums.remove(3)
ultimo = nums.pop()  # saca el último
```

Slicing y copias:

```python
sub = nums[1:3]
copia = nums[:]  # copia superficial
```

Comprensiones de listas:

```python
cuadrados = [n*n for n in range(6)]  # [0,1,4,9,16,25]
pares = [n for n in range(10) if n % 2 == 0]
```

## Tuplas (tuple)

- Ordenadas, inmutables.

```python
t = (1, 2, 3)
a, b, c = t  # desempaquetado
```

Usos: coordenadas, claves de diccionario, retorno múltiple.

## Conjuntos (set)

- No ordenados, únicos, mutables (pero sus elementos deben ser hashables).

```python
s = {1, 2, 2, 3}   # {1, 2, 3}
s.add(4)
s.discard(2)
```

Operaciones de teoría de conjuntos:

```python
a = {1,2,3}
b = {3,4}
a | b   # unión -> {1,2,3,4}
a & b   # intersección -> {3}
a - b   # diferencia -> {1,2}
a ^ b   # diferencia simétrica -> {1,2,4}
```

## Diccionarios (dict)

- Pares clave-valor, mutables.

```python
persona = {"nombre": "Ana", "edad": 30}
persona["ciudad"] = "Lima"
edad = persona.get("edad", 0)
for k, v in persona.items():
    print(k, v)
```

Comprensiones de diccionarios:

```python
cuadrados = {n: n*n for n in range(5)}
```

## Copias y mutabilidad

- Copia superficial vs profunda:

```python
import copy

lista = [[1,2], [3,4]]
shallow = list(lista)
deep = copy.deepcopy(lista)
lista[0][0] = 99
# shallow se ve afectada; deep no
```

## Elegir la estructura adecuada

- Lista: colección ordenada y modificable
- Tupla: datos inmutables o retornos múltiples
- Set: colección sin duplicados y operaciones de pertenencia rápidas
- Dict: mapeo clave-valor

## Ejercicios

1. Dada una lista de palabras, crea un set con las únicas y ordénalas al imprimir.
2. Construye un dict que mapee cada letra de una palabra a su conteo.
3. Dada una lista de números, crea una nueva lista con los números al cuadrado que sean pares.

## Resumen

Manejaste colecciones complejas de Python: list, tuple, set y dict, incluidas comprensiones y operaciones clave.
