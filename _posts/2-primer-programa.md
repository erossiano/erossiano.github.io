---
layout: post
title: "Lección 2: Tu primer programa en Python"
date: 2022-01-02
categories: python tutorial
---
# Lección 2: Tu primer programa en Python
## Objetivo
Escribirás, ejecutarás y comprenderás tu primer programa en Python, además de aprender cómo usar el intérprete interactivo (REPL) y buenas prácticas básicas.
## Hola Mundo
El clásico primer programa imprime un saludo en pantalla.
```python
print("Hola, mundo")
```
- `print` es una función que muestra texto en la salida estándar.
- Las comillas pueden ser simples o dobles.
### Ejecutar el programa
1. Crea una carpeta de proyecto, por ejemplo `mi_primer_programa`.
2. Dentro, crea un archivo llamado `hola.py` con el código anterior.
3. Abre una terminal/consola, navega a tu carpeta y ejecuta:
```bash
python hola.py
```
4. Deberías ver en pantalla: `Hola, mundo`
## El intérprete interactivo (REPL)
REPL = Read-Eval-Print-Loop
### Iniciar el REPL
Ejecuta en tu terminal:
```bash
python
```
Verás un prompt `>>>`. Aquí puedes escribir código línea por línea y obtener resultados inmediatos.
```python
>>> 2 + 3
5
>>> print("Hola desde el REPL")
Hola desde el REPL
>>> nombre = "Ana"
>>> print(f"Hola, {nombre}!")
Hola, Ana!
```
Para salir del REPL:
```python
>>> exit()
```
o presiona `Ctrl+D` (Linux/macOS) o `Ctrl+Z` (Windows).
## Sintaxis básica
### Comentarios
```python
# Esto es un comentario de una línea
print("Hola, mundo")  # Comentario al final de una línea
"""
Esto es un comentario de varias líneas.
Puede ocupar tantas líneas como necesites.
"""
```
### Variables
En Python no necesitas declarar tipos; el intérprete los infiere.
```python
nombre = "María"
edad = 25
altura = 1.65
estudiante = True
```
### Reglas de nombres de variables
- Comienzan con letra o guion bajo (`_`).
- Pueden contener letras, números y guiones bajos.
- Sensibles a mayúsculas (`edad` ≠ `Edad`).
- Evita palabras reservadas (`if`, `for`, `class`, etc.).
**Buenas prácticas:**
- Nombres descriptivos: `edad_usuario` en vez de `eu`.
- Usa snake_case para variables: `mi_variable`.
- Usa MAYUSCULAS para constantes: `PI = 3.14159`.
## Tipos de datos básicos (introducción)
Python tiene varios tipos de datos fundamentales:
```python
# Enteros (int)
edad = 25
# Flotantes (float)
altura = 1.75
# Cadenas (str)
nombre = "Carlos"
# Booleanos (bool)
estudiante = True
```
Puedes comprobar el tipo con `type()`:
```python
>>> type(edad)
<class 'int'>
>>> type(nombre)
<class 'str'>
```
## Entrada y salida
### Salida con print
```python
print("Hola")           # Una cadena
print(2023)             # Un número
print("a", "b", "c")    # Múltiples valores (separados por espacio)
print("a", "b", sep="-") # Separador personalizado
print("Fin", end="!")    # Cambiar fin de línea
```
### Entrada con input
```python
nombre = input("¿Cómo te llamas? ")
print("Encantado/a,", nombre)
```
- `input` devuelve una cadena (string).
### Conversión de tipos
```python
edad = int(input("¿Cuántos años tienes? "))
print("El próximo año tendrás", edad + 1)
```
- Convierte con `int`, `float`, `str` según necesites.
## Errores comunes del principiante
- Olvidar comillas alrededor de cadenas: `print(Hola)` provoca error; usa `print("Hola")`.
- Mezclar `python` y `python3` en sistemas con ambas versiones.
- Usar comillas curvas (tipográficas) en vez de comillas rectas.
## Ejercicios
1. Crea un script `presentacion.py` que pida tu nombre y ciudad y muestre: `Me llamo <nombre> y vivo en <ciudad>`.
2. Modifica el script para pedir también tu edad e imprime: `En 5 años tendré <edad>`.
3. Usa el REPL para calcular el área de un círculo de radio 3 (`pi*r*r`).
## Resumen
- Ejecutaste tu primer script con `print`.
- Aprendiste a usar el REPL, `input` y conversiones básicas.
- Conociste buenas prácticas iniciales y errores frecuentes.

En la siguiente lección veremos los tipos de datos básicos de Python.

---
## Navegación del Tutorial

← **Anterior:** [Lección 1 - Instalación de Python](1-instalacion-python.md) | **Siguiente:** [Lección 3 - Tipos de Datos Básicos](3-tipos-de-datos-basicos.md) →
