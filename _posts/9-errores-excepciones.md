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

- Coloca dentro de try el código propenso a fallos.
- Usa except para capturar tipos específicos de excepción.
- Puedes encadenar varios except.

## Captura genérica y el objeto de excepción
Si no conoces el tipo exacto, puedes capturar de forma genérica, pero úsalo con moderación.

```python
try:
    proceso_riesgoso()
except Exception as e:
    print(f"Ocurrió un error inesperado: {type(e).__name__}: {e}")
```

Ventajas: no se te escapan errores. Desventajas: puede ocultar problemas que deberías tratar explícitamente.

## Clausulas else y finally
- else: se ejecuta si no se lanzó ninguna excepción en el bloque try.
- finally: se ejecuta siempre, ocurra o no una excepción (útil para liberar recursos).

```python
archivo = None
try:
    archivo = open("datos.txt", "r", encoding="utf-8")
    contenido = archivo.read()
except FileNotFoundError:
    print("El archivo no existe.")
else:
    print("Lectura exitosa. Longitud:", len(contenido))
finally:
    if archivo:
        archivo.close()
        print("Archivo cerrado (finally).")
```

## Levantar excepciones con raise
Puedes forzar condiciones de error cuando detectes estados inválidos.

```python
def retirar(saldo, monto):
    if monto <= 0:
        raise ValueError("El monto debe ser positivo")
    if monto > saldo:
        raise RuntimeError("Fondos insuficientes")
    return saldo - monto

try:
    nuevo = retirar(100, 150)
except ValueError as e:
    print("Valor inválido:", e)
except RuntimeError as e:
    print("Operación inválida:", e)
```

## Crear tus propias excepciones
Hereda de Exception para definir errores de dominio.

```python
class ErrorBanco(Exception):
    """Excepción base para el dominio bancario."""

class FondosInsuficientes(ErrorBanco):
    pass

class MontoInvalido(ErrorBanco):
    pass

def retirar(saldo, monto):
    if monto <= 0:
        raise MontoInvalido("El monto debe ser positivo")
    if monto > saldo:
        raise FondosInsuficientes("Fondos insuficientes")
    return saldo - monto

try:
    retirar(100, 150)
except MontoInvalido as e:
    print("Error de monto:", e)
except FondosInsuficientes as e:
    print("Error de fondos:", e)
```

## Excepciones comunes en Python
- SyntaxError: error de sintaxis (se detecta antes de ejecutar). No se puede capturar con try/except en el mismo bloque donde ocurre.
- NameError: variable no definida.
- TypeError: operación con tipos incompatibles.
- ValueError: valor con tipo correcto pero contenido inválido.
- IndexError / KeyError: índices o claves inexistentes.
- FileNotFoundError / PermissionError: problemas de archivos.
- ZeroDivisionError: división por cero.
- AssertionError: cuando falla una aserción.

Ejemplos rápidos:

```python
# NameError
print(variable_inexistente)

# TypeError
len(10)

# ValueError
int("abc")

# IndexError
[1, 2][5]

# KeyError
{"a": 1}["b"]
```

## Buenas prácticas
- Captura primero excepciones específicas y al final una genérica si aporta valor.
- No silencies errores: registra o reporta el problema.
- Usa finally o context managers (with) para liberar recursos.
- Valida inputs temprano y usa raise para estados inválidos.
- Mantén mensajes de error claros y accionables.

### Context managers en vez de try/finally

```python
# Equivalente a abrir/cerrar con try/finally
with open("datos.txt", "r", encoding="utf-8") as f:
    contenido = f.read()
# f se cierra automáticamente al salir del bloque
```

## Ejercicios prácticos

1) Conversor robusto
- Escribe una función leer_entero(mensaje) que pida input hasta recibir un entero válido, usando try/except y devolviendo el valor.

2) División segura
- Escribe dividir_seguro(a, b) que devuelva a/b o None si b es 0, registrando el error sin detener el programa.

3) Abrir archivo con reporte
- Implementa abrir_y_contar(ruta) que intente leer un archivo y devuelva el número de líneas. Usa except FileNotFoundError y finally para asegurar el cierre.

4) Validación con raise
- Implementa registrar_usuario(nombre, edad). Lanza ValueError si nombre está vacío o edad < 0. Escribe pruebas que verifiquen que se lanzan las excepciones.

5) Excepciones personalizadas
- Define excepciones PedidoVacio y StockInsuficiente. Implementa procesar_pedido(carrito, stock) que lance dichas excepciones según corresponda y pruébalo con try/except.

6) Reintentos controlados
- Escribe una función fetch(url, reintentos=3) que atrape excepciones de red (p.ej., requests.exceptions.RequestException), espere incrementalmente y reintente hasta agotar. Usa finally para registrar el intento.

Sugerencia: agrega logs con logging.exception(...) para incluir traceback en el registro.

## Recursos adicionales
- Documentación oficial: https://docs.python.org/3/tutorial/errors.html
- Jerarquía de excepciones: https://docs.python.org/3/library/exceptions.html
