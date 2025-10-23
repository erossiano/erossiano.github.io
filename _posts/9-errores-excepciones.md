---
layout: post
title: "9. Errores y Excepciones en Python"
date: 2025-10-23 09:00:00 -0500
categories: [python, fundamentos]
tags: [errores, excepciones, try-except, finally]
---
# 9. Errores y Excepciones en Python

En esta lección veremos cómo manejar errores (excepciones) en Python para evitar que un programa se detenga inesperadamente y, en su lugar, responder de forma controlada.

## ¿Qué es una excepción?

Una excepción es un evento que interrumpe el flujo normal del programa cuando ocurre una condición anómala. Si no se maneja, Python detiene la ejecución y muestra un traceback.

Ejemplo de excepción no manejada:
```python
# ZeroDivisionError
resultado = 10 / 0
print(resultado)
```

## Manejo básico con try/except

La estructura mínima para capturar errores es:
```python
try:
    # código que puede fallar
    x = int(input("Ingresa un número: "))
    y = 10 / x
    print("Resultado:", y)
except ZeroDivisionError:
    print("No puedes dividir entre cero.")
except ValueError:
    print("Debes ingresar un número entero.")
```

- Coloca dentro de `try` el código propenso a fallos.
- Usa `except` para capturar tipos específicos de excepción.
- Puedes encadenar varios `except`.

## Captura genérica y el objeto de excepción

Si no conoces el tipo exacto, puedes capturar de forma genérica, pero úsalo con moderación:
```python
try:
    resultado = 100 / int(input("Divisor: "))
except Exception as e:
    print(f"Error: {e}")
```

**Precaución**: capturar `Exception` es demasiado amplio y puede enmascarar errores. Mejor sé específico.

## El bloque else

Se ejecuta solo si no hubo excepciones:
```python
try:
    resultado = 10 / 2
except ZeroDivisionError:
    print("Error de división")
else:
    print("Operación exitosa. Resultado:", resultado)
```

## El bloque finally

Se ejecuta siempre, haya o no excepción. Es ideal para limpiar recursos (cerrar archivos, conexiones, etc.):
```python
archivo = None
try:
    archivo = open("datos.txt", "r")
    contenido = archivo.read()
except FileNotFoundError:
    print("Archivo no encontrado.")
finally:
    if archivo:
        archivo.close()
    print("Bloque finally ejecutado.")
```

## Lanzar excepciones con raise

Puedes lanzar errores intencionalmente:
```python
def calcular_raiz(num):
    if num < 0:
        raise ValueError("No se puede calcular raíz de número negativo")
    return num ** 0.5

try:
    print(calcular_raiz(-4))
except ValueError as e:
    print(f"Error: {e}")
```

## Excepciones personalizadas

Puedes crear tus propias excepciones heredando de `Exception`:
```python
class EdadInvalidaError(Exception):
    pass

def registrar_usuario(edad):
    if edad < 18:
        raise EdadInvalidaError("Debes ser mayor de 18 años")
    print("Usuario registrado.")

try:
    registrar_usuario(15)
except EdadInvalidaError as e:
    print(e)
```

## Excepciones más comunes

- **ZeroDivisionError**: División por cero.
- **ValueError**: Conversión de tipo inválida.
- **TypeError**: Operación con tipos incompatibles.
- **FileNotFoundError**: Archivo no existe.
- **IndexError**: Índice fuera de rango.
- **KeyError**: Clave no existe en diccionario.
- **AttributeError**: Atributo no existe en objeto.
- **ImportError**: Módulo no encontrado.

## Jerarquía de excepciones

Python organiza excepciones en una jerarquía. Capturar una clase base captura todas las derivadas:
```python
try:
    x = int("abc")
except (ValueError, TypeError):
    print("Error de tipo o valor")
```

## Buenas prácticas

### Ser específico

Captura solo las excepciones que sabes manejar:
```python
# Mal
try:
    x = int(input())
except:
    pass  # Silencia TODO, incluyendo KeyboardInterrupt

# Bien
try:
    x = int(input())
except ValueError:
    print("Entrada inválida")
```

### No silenciar errores

Registra o reporta el error:
```python
import logging

try:
    resultado = operacion_riesgosa()
except Exception as e:
    logging.error(f"Error en operación: {e}")
    raise  # relanza la excepción
```

### Resumen de principios

- No silencies errores: registra o reporta el problema.
- Usa `finally` o context managers (`with`) para liberar recursos.
- Valida inputs temprano y usa `raise` para estados inválidos.
- Mantén mensajes de error claros y accionables.

### Context managers en vez de try/finally

```python
# Equivalente a abrir/cerrar con try/finally
with open("datos.txt", "r", encoding="utf-8") as f:
    contenido = f.read()
# f se cierra automáticamente al salir del bloque
```

## Ejercicios prácticos

1) **Conversor robusto**
   - Escribe una función `leer_entero(mensaje)` que pida input hasta recibir un entero válido, usando try/except y devolviendo el valor.

2) **División segura**
   - Escribe `dividir_seguro(a, b)` que devuelva a/b o None si b es 0, registrando el error sin detener el programa.

3) **Abrir archivo con reporte**
   - Implementa `abrir_y_contar(ruta)` que intente leer un archivo y devuelva el número de líneas. Usa `except FileNotFoundError` y `finally` para asegurar el cierre.

4) **Validación con raise**
   - Implementa `registrar_usuario(nombre, edad)`. Lanza `ValueError` si nombre está vacío o edad < 0. Escribe pruebas que verifiquen que se lanzan las excepciones.

5) **Excepciones personalizadas**
   - Define excepciones `PedidoVacio` y `StockInsuficiente`. Implementa `procesar_pedido(carrito, stock)` que lance dichas excepciones según corresponda y pruébalo con try/except.

6) **Reintentos controlados**
   - Escribe una función `fetch(url, reintentos=3)` que atrape excepciones de red (p.ej., requests.exceptions.RequestException), espere incrementalmente y reintente hasta agotar. Usa `finally` para registrar el intento.

Sugerencia: agrega logs con `logging.exception(...)` para incluir traceback en el registro.

## Recursos adicionales

- Documentación oficial: https://docs.python.org/3/tutorial/errors.html
- Jerarquía de excepciones: https://docs.python.org/3/library/exceptions.html

---
## Navegación del Tutorial

← **Anterior:** [Lección 8 - Programación Orientada a Objetos](8-programacion-orientada-objetos.md) | **Siguiente:** [Lección 10 - Proyecto Final](10-proyecto-final.md) →
