---
layout: post
title: "Lección 10: Proyecto Final - Calculadora Interactiva"
date: 2025-10-23
categories: proyecto calculadora
---
# Lección 10: Proyecto Final - Calculadora Interactiva

## Introducción

En este proyecto final, desarrollaremos una calculadora interactiva que integra todos los conceptos aprendidos a lo largo del curso: variables, operadores, estructuras de control, funciones y manejo de errores.

## Objetivos del Proyecto

- Aplicar conocimientos de programación en un proyecto completo
- Implementar una interfaz de usuario funcional
- Practicar el manejo de errores y validación de entrada
- Desarrollar habilidades de debugging y testing

## Calculadora - Funcionalidades Básicas

### 1. Operaciones Aritméticas

```python
def sumar(a, b):
    return a + b

def restar(a, b):
    return a - b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    if b == 0:
        raise ValueError("No se puede dividir por cero")
    return a / b
```

### 2. Operaciones Avanzadas

```python
import math

def potencia(base, exponente):
    return base ** exponente

def raiz_cuadrada(numero):
    if numero < 0:
        raise ValueError("No se puede calcular raíz cuadrada de número negativo")
    return math.sqrt(numero)

def porcentaje(numero, porcentaje):
    return (numero * porcentaje) / 100
```

### 3. Clase Principal de Calculadora

```python
class Calculadora:
    def __init__(self):
        self.historial = []
    
    def calcular(self, operacion, num1, num2=None):
        resultado = None
        
        try:
            if operacion == 'sumar':
                resultado = sumar(num1, num2)
            elif operacion == 'restar':
                resultado = restar(num1, num2)
            elif operacion == 'multiplicar':
                resultado = multiplicar(num1, num2)
            elif operacion == 'dividir':
                resultado = dividir(num1, num2)
            elif operacion == 'potencia':
                resultado = potencia(num1, num2)
            elif operacion == 'raiz':
                resultado = raiz_cuadrada(num1)
            elif operacion == 'porcentaje':
                resultado = porcentaje(num1, num2)
            else:
                raise ValueError("Operación no válida")
            
            self.historial.append(f"{operacion}: {num1}, {num2} = {resultado}")
            return resultado
            
        except Exception as e:
            print(f"Error en cálculo: {e}")
            return None
    
    def mostrar_historial(self):
        print("\nHistorial de operaciones:")
        for operacion in self.historial:
            print(operacion)
```

### 4. Interfaz de Usuario

```python
def menu():
    print("\n=== CALCULADORA INTERACTIVA ===")
    print("1. Sumar")
    print("2. Restar")
    print("3. Multiplicar")
    print("4. Dividir")
    print("5. Potencia")
    print("6. Raíz cuadrada")
    print("7. Porcentaje")
    print("8. Ver historial")
    print("9. Salir")
    print("=================================")

def main():
    calc = Calculadora()
    
    while True:
        menu()
        opcion = input("\nSeleccione una opción: ")
        
        if opcion == '9':
            print("¡Hasta luego!")
            break
        
        if opcion == '8':
            calc.mostrar_historial()
            continue
        
        try:
            num1 = float(input("Ingrese el primer número: "))
            
            if opcion != '6':  # Raíz cuadrada solo necesita un número
                num2 = float(input("Ingrese el segundo número: "))
            else:
                num2 = None
            
            operaciones = {
                '1': 'sumar',
                '2': 'restar',
                '3': 'multiplicar',
                '4': 'dividir',
                '5': 'potencia',
                '6': 'raiz',
                '7': 'porcentaje'
            }
            
            if opcion in operaciones:
                resultado = calc.calcular(operaciones[opcion], num1, num2)
                if resultado is not None:
                    print(f"\nResultado: {resultado}")
            else:
                print("Opción no válida")
        
        except ValueError as e:
            print(f"Error: {e}")
        except Exception as e:
            print(f"Error inesperado: {e}")

if __name__ == "__main__":
    main()
```

## Ejercicios Integrativos

### Ejercicio 1: Operaciones con Memoria
Añade funcionalidad para almacenar un resultado en memoria (M+, M-, MR, MC).

### Ejercicio 2: Conversión de Unidades
Implementa conversiones entre:
- Temperatura (Celsius, Fahrenheit, Kelvin)
- Longitud (metros, pies, pulgadas)
- Peso (kilogramos, libras, onzas)

### Ejercicio 3: Cálculos Estadísticos
Agrega funciones para:
- Media aritmética
- Mediana
- Moda
- Desviación estándar

### Ejercicio 4: Modo Científico
Añade operaciones científicas:
- Funciones trigonométricas (sin, cos, tan)
- Logaritmos (log, ln)
- Factorial

### Ejercicio 5: Guardado de Historial
Implementa la capacidad de:
- Guardar el historial en un archivo de texto
- Cargar historial previo
- Exportar resultados a CSV

## Criterios de Evaluación

1. **Funcionalidad (40%)**
   - Todas las operaciones básicas funcionan correctamente
   - Implementación de al menos 3 ejercicios integrativos
   - Manejo adecuado de errores

2. **Código (30%)**
   - Código limpio y organizado
   - Uso apropiado de funciones y clases
   - Nombres de variables descriptivos
   - Comentarios claros

3. **Interfaz de Usuario (20%)**
   - Menú intuitivo y fácil de usar
   - Mensajes de error informativos
   - Experiencia de usuario fluida

4. **Documentación (10%)**
   - README con instrucciones de uso
   - Documentación de funciones (docstrings)
   - Ejemplos de uso

## Requisitos de Entrega

1. **Archivo principal**: `calculadora.py`
2. **Archivo README**: Con instrucciones de instalación y uso
3. **Archivo de pruebas**: `test_calculadora.py` (opcional pero recomendado)
4. **Comentarios**: En el código explicando la lógica

## Recursos Adicionales

- [Documentación de Python - Math Module](https://docs.python.org/3/library/math.html)
- [Tutorial de Clases en Python](https://docs.python.org/3/tutorial/classes.html)
- [Manejo de Excepciones en Python](https://docs.python.org/3/tutorial/errors.html)

## Conclusión

Este proyecto final integra todos los conceptos fundamentales de programación que hemos aprendido. Es una oportunidad para demostrar tu comprensión de:

- Estructuras de datos y algoritmos
- Programación orientada a objetos
- Manejo de errores y excepciones
- Diseño de interfaces de usuario
- Documentación y buenas prácticas

**¡Buena suerte con tu proyecto final!**

---
## Navegación del Tutorial

← **Anterior:** [Lección 9 - Errores y Excepciones](9-errores-excepciones.md)
