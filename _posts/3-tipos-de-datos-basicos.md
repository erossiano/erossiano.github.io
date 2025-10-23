---
layout: post
title: "Lección 3: Tipos de datos básicos en Python"
date: 2022-07-03
categories: python tutorial
---
# Lección 3: Tipos de datos básicos en Python
En esta lección veremos los tipos fundamentales: números, cadenas, booleanos y None.
## Números
- Enteros: int
- Flotantes: float
- Complejos: complex
```python
x = 10        # int
pi = 3.1416   # float
z = 2 + 3j    # complex
```
Operaciones aritméticas:
```python
2 + 3    # 5
7 - 4    # 3
6 * 8    # 48
9 / 2    # 4.5 (float)
9 // 2   # 4 (división entera)
9 % 2    # 1 (módulo)
2 ** 3   # 8 (potencia)
```
Funciones útiles: `abs`, `round`, `pow`, `min`, `max`.
## Cadenas (str)
```python
s = "Python"
len(s)          # 6
s.lower()       # 'python'
s.upper()       # 'PYTHON'
s.startswith("Py")  # True
"hola" + " " + "mundo"  # 'hola mundo'
```
Slicing (rebanadas):
```python
s = "Python"
s[0]       # 'P'
s[-1]      # 'n'
s[0:3]     # 'Pyt'
s[:3]      # 'Pyt'
s[3:]      # 'hon'
s[::-1]    # 'nohtyP' (invertida)
```
Cadenas multilínea y f-strings:
```python
mensaje = """Este es
un texto
de varias líneas"""
nombre = "Ana"
edad = 30
print(f"Me llamo {nombre} y tengo {edad} años.")
```
Las cadenas son inmutables (no pueden modificarse en su lugar).
## Booleanos (bool)
Valores: `True` y `False` (primera letra mayúscula).
Operadores de comparación:
```python
3 > 2      # True
2 == 2     # True
2 != 3     # True
"a" in "casa"   # True
```
Operadores lógicos:
```python
True and False  # False
True or False   # True
not True        # False
```
Precedencia: `not` > `and` > `or`.
## None
`None` representa la ausencia de valor.
```python
resultado = None
if resultado is None:
    print("Sin resultado todavía")
```
## Conversión de tipos
```python
int("42")      # 42
float("3.14")  # 3.14
str(123)       # '123'
bool(0)        # False
bool(1)        # True
```
## Ejercicios
1. Dado `s = "programación"`, imprime sus 5 primeros caracteres.
2. Calcula el área de un rectángulo con base 5.5 y altura 3 usando variables.
3. Escribe un f-string que muestre: "Mi nombre es <nombre> y tengo <edad> años".
## Resumen
- Números: int, float, complex y operaciones.
- Cadenas: métodos, slicing e inmutabilidad.
- Booleanos y operadores lógicos.
- `None` y conversiones de tipos.

---
## Navegación del Tutorial

← **Anterior:** [Lección 2 - Primer Programa](2-primer-programa.md) | **Siguiente:** [Lección 4 - Tipos de Datos Complejos](4-tipos-de-datos-complejos.md) →
