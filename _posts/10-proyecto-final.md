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

### 1. Operaciones Aritméticas Básicas

```python
def sumar(a, b):
    """Suma dos números"""
    return a + b

def restar(a, b):
    """Resta dos números"""
    return a - b

def multiplicar(a, b):
    """Multiplica dos números"""
    return a * b

def dividir(a, b):
    """Divide dos números con manejo de error"""
    if b == 0:
        raise ValueError("Error: División por cero no permitida")
    return a / b
```

### 2. Operaciones Avanzadas

```python
import math

def potencia(base, exponente):
    """Calcula la potencia de un número"""
    return base ** exponente

def raiz_cuadrada(numero):
    """Calcula la raíz cuadrada"""
    if numero < 0:
        raise ValueError("Error: No se puede calcular raíz cuadrada de número negativo")
    return math.sqrt(numero)

def factorial(n):
    """Calcula el factorial de un número"""
    if n < 0:
        raise ValueError("Error: El factorial no está definido para números negativos")
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)
```

### 3. Calculadora Principal

```python
class Calculadora:
    def __init__(self):
        self.historial = []
    
    def agregar_al_historial(self, operacion, resultado):
        """Agrega operación al historial"""
        self.historial.append(f"{operacion} = {resultado}")
    
    def mostrar_historial(self):
        """Muestra el historial de operaciones"""
        if not self.historial:
            print("No hay operaciones en el historial")
            return
        
        print("\n=== HISTORIAL ===")
        for operacion in self.historial:
            print(operacion)
    
    def limpiar_historial(self):
        """Limpia el historial"""
        self.historial.clear()
        print("Historial limpiado")
    
    def ejecutar_operacion(self, operacion, a, b=None):
        """Ejecuta una operación y la agrega al historial"""
        try:
            if operacion == "+":
                resultado = sumar(a, b)
                op_str = f"{a} + {b}"
            elif operacion == "-":
                resultado = restar(a, b)
                op_str = f"{a} - {b}"
            elif operacion == "*":
                resultado = multiplicar(a, b)
                op_str = f"{a} * {b}"
            elif operacion == "/":
                resultado = dividir(a, b)
                op_str = f"{a} / {b}"
            elif operacion == "**":
                resultado = potencia(a, b)
                op_str = f"{a} ** {b}"
            elif operacion == "sqrt":
                resultado = raiz_cuadrada(a)
                op_str = f"√{a}"
            elif operacion == "!":
                resultado = factorial(int(a))
                op_str = f"{int(a)}!"
            else:
                raise ValueError("Operación no válida")
            
            self.agregar_al_historial(op_str, resultado)
            return resultado
        
        except Exception as e:
            print(f"Error: {e}")
            return None
```

### 4. Interfaz de Usuario

```python
def mostrar_menu():
    """Muestra el menú de opciones"""
    print("\n=== CALCULADORA INTERACTIVA ===")
    print("1. Suma (+)")
    print("2. Resta (-)")
    print("3. Multiplicación (*)")
    print("4. División (/)")
    print("5. Potencia (**)")
    print("6. Raíz cuadrada (sqrt)")
    print("7. Factorial (!)")
    print("8. Ver historial")
    print("9. Limpiar historial")
    print("0. Salir")

def obtener_numero(mensaje):
    """Obtiene un número del usuario con validación"""
    while True:
        try:
            return float(input(mensaje))
        except ValueError:
            print("Por favor, ingresa un número válido")

def main():
    """Función principal de la calculadora"""
    calc = Calculadora()
    
    while True:
        mostrar_menu()
        opcion = input("\nSelecciona una opción: ")
        
        if opcion == "0":
            print("¡Gracias por usar la calculadora!")
            break
        
        elif opcion in ["1", "2", "3", "4", "5"]:
            a = obtener_numero("Primer número: ")
            b = obtener_numero("Segundo número: ")
            
            operaciones = {"1": "+", "2": "-", "3": "*", "4": "/", "5": "**"}
            resultado = calc.ejecutar_operacion(operaciones[opcion], a, b)
            
            if resultado is not None:
                print(f"Resultado: {resultado}")
        
        elif opcion == "6":
            a = obtener_numero("Número para raíz cuadrada: ")
            resultado = calc.ejecutar_operacion("sqrt", a)
            if resultado is not None:
                print(f"Resultado: {resultado}")
        
        elif opcion == "7":
            a = obtener_numero("Número para factorial: ")
            resultado = calc.ejecutar_operacion("!", a)
            if resultado is not None:
                print(f"Resultado: {resultado}")
        
        elif opcion == "8":
            calc.mostrar_historial()
        
        elif opcion == "9":
            calc.limpiar_historial()
        
        else:
            print("Opción no válida")

# Ejecutar la calculadora
if __name__ == "__main__":
    main()
```

## Ejercicios Integradores

### Ejercicio 1: Extensión de Funcionalidades
**Objetivo:** Agregar nuevas operaciones a la calculadora

**Tareas:**
1. Implementa operaciones trigonométricas (sin, cos, tan)
2. Agrega conversión entre grados y radianes
3. Implementa logaritmo natural y logaritmo base 10

```python
# Ejemplo de implementación
def seno(angulo, en_grados=True):
    """Calcula el seno de un ángulo"""
    if en_grados:
        angulo = math.radians(angulo)
    return math.sin(angulo)
```

### Ejercicio 2: Validación Avanzada
**Objetivo:** Mejorar el manejo de errores y validación

**Tareas:**
1. Implementa validación para operaciones con números muy grandes
2. Agrega límites para operaciones factoriales
3. Crea mensajes de error más descriptivos

### Ejercicio 3: Calculadora de Expresiones
**Objetivo:** Evaluar expresiones matemáticas completas

**Tareas:**
1. Implementa un parser para expresiones como "2 + 3 * 4"
2. Maneja paréntesis y precedencia de operadores
3. Valida la sintaxis de las expresiones

```python
# Ejemplo usando eval() con validación
def evaluar_expresion(expresion):
    """Evalúa una expresión matemática de forma segura"""
    # Caracteres permitidos
    caracteres_validos = set('0123456789+-*/().^ ')
    
    if not all(c in caracteres_validos for c in expresion):
        raise ValueError("Expresión contiene caracteres no válidos")
    
    # Reemplazar ^ por **
    expresion = expresion.replace('^', '**')
    
    try:
        resultado = eval(expresion)
        return resultado
    except Exception as e:
        raise ValueError(f"Error en la expresión: {e}")
```

### Ejercicio 4: Calculadora Científica
**Objetivo:** Expandir a funcionalidades científicas

**Tareas:**
1. Implementa notación científica
2. Agrega constantes matemáticas (π, e)
3. Implementa conversiones de unidades básicas

### Ejercicio 5: Persistencia de Datos
**Objetivo:** Guardar y cargar historial

**Tareas:**
1. Guarda el historial en un archivo de texto
2. Carga el historial al iniciar la aplicación
3. Implementa exportación del historial en diferentes formatos

```python
import json

def guardar_historial(self, archivo="historial.json"):
    """Guarda el historial en un archivo JSON"""
    try:
        with open(archivo, 'w') as f:
            json.dump(self.historial, f, indent=2)
        print(f"Historial guardado en {archivo}")
    except Exception as e:
        print(f"Error al guardar: {e}")
```

## Criterios de Evaluación

### Funcionalidad (40%)
- [ ] Operaciones básicas funcionan correctamente
- [ ] Manejo adecuado de errores
- [ ] Interfaz de usuario intuitiva
- [ ] Historial funcional

### Código (30%)
- [ ] Código limpio y bien documentado
- [ ] Uso apropiado de funciones y clases
- [ ] Manejo correcto de excepciones
- [ ] Nombres de variables descriptivos

### Creatividad (20%)
- [ ] Funcionalidades adicionales implementadas
- [ ] Mejoras en la interfaz de usuario
- [ ] Soluciones innovadoras a problemas

### Documentación (10%)
- [ ] Comentarios explicativos en el código
- [ ] Documentación de funciones
- [ ] README con instrucciones de uso

## Entrega

**Fecha límite:** [Definir fecha]

**Formato de entrega:**
1. Código fuente en archivo `.py`
2. Archivo README.md con instrucciones
3. Ejemplos de uso y screenshots (opcional)
4. Reflexión sobre el proyecto (1 página)

## Recursos Adicionales

- [Documentación oficial de Python](https://docs.python.org/3/)
- [Tutorial de manejo de excepciones](https://docs.python.org/3/tutorial/errors.html)
- [Guía de estilo PEP 8](https://www.python.org/dev/peps/pep-0008/)

## Conclusión

Este proyecto final integra todos los conceptos fundamentales de programación que hemos aprendido. Es una oportunidad para demostrar tu comprensión de:

- Estructuras de datos y algoritmos
- Programación orientada a objetos
- Manejo de errores y excepciones
- Diseño de interfaces de usuario
- Documentación y buenas prácticas

¡Buena suerte con tu proyecto final!
