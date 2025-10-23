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
3. Abre una terminal en esa carpeta y ejecuta:

```bash
python hola.py
# o, según tu sistema
python3 hola.py
```

Deberías ver: `Hola, mundo`.

## Usar el REPL (interactivo)

Puedes ejecutar Python de forma interactiva para probar expresiones rápidamente.

```bash
python
# o
python3
```

Ejemplo de sesión REPL:

```
>>> 2 + 3
5
>>> print("Hola")
Hola
>>> nombre = "Ana"
>>> f"Hola, {nombre}!"
'Hola, Ana!'
```

Salir del REPL:

- Escribe `exit()` o presiona `Ctrl+D` (macOS/Linux) o `Ctrl+Z` luego Enter (Windows).

## Comentarios y estilo

- Comentarios de una línea comienzan con `#`.

```python
# Esto es un comentario
print("Python")  # Comentario al final de línea
```

- Usa nombres descriptivos para variables: `contador_usuarios`, `precio_total`.
- Sigue PEP 8 (estilo de código): sangría de 4 espacios, nombres_con_guiones_bajos, líneas <= 79 caracteres cuando sea posible.

## Entrada y salida básicas

### Entrada desde teclado

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
2. Modifica el script para pedir también tu edad e imprime: `En 5 años tendré <edad+5>`.
3. Usa el REPL para calcular el área de un círculo de radio 3 (`pi*r*r`).

## Resumen

- Ejecutaste tu primer script con `print`.
- Aprendiste a usar el REPL, `input` y conversiones básicas.
- Conociste buenas prácticas iniciales y errores frecuentes.

En la siguiente lección veremos los tipos de datos básicos de Python.
