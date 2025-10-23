---
layout: post
title: "Lección 5: Control de flujo"
date: 2022-07-05
categories: python tutorial
---

# Lección 5: Control de flujo

Aprenderás condicionales, ciclos, y palabras clave como break, continue y else/for.

## Condicionales

```python
x = 10
if x > 0:
    print("positivo")
elif x == 0:
    print("cero")
else:
    print("negativo")
```

Operador ternario:

```python
paridad = "par" if x % 2 == 0 else "impar"
```

## Bucles while

```python
n = 5
while n > 0:
    print(n)
    n -= 1
else:
    print("Fin del while")
```

## Bucles for

```python
for c in "Python":
    print(c)
```

Con range:

```python
for i in range(3):
    print(i)  # 0,1,2
```

Con enumerate y zip:

```python
nombres = ["Ana", "Luis"]
edades = [30, 25]
for i, nombre in enumerate(nombres):
    print(i, nombre)
for n, e in zip(nombres, edades):
    print(n, e)
```

## break y continue

```python
for i in range(10):
    if i == 3:
        continue  # salta el 3
    if i == 7:
        break     # detiene el bucle
    print(i)
```

## Comprensiones y any/all

```python
cuadrados = [x*x for x in range(5)]
hay_par = any(x % 2 == 0 for x in range(5))
todos_mayores = all(x > -1 for x in range(5))
```

## Match (Python 3.10+)

```python
status = 404
match status:
    case 200:
        msg = "OK"
    case 404:
        msg = "No encontrado"
    case _:
        msg = "Otro"
```

## Ejercicios

1. Recorre del 1 al 100 e imprime Fizz si múltiplo de 3, Buzz si de 5 y FizzBuzz si de ambos.
2. Pide números al usuario hasta que escriba `salir`; calcula suma y promedio.
3. Usa `match` para mapear códigos 1-7 a días de la semana.

## Resumen

- if/elif/else y operador ternario
- while y for con else
- break/continue, enumerate/zip
- comprensiones, any/all, y match
