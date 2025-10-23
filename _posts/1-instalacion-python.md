---
layout: post
title: "Lección 1: Instalación de Python"
date: 2022-01-01
categories: python tutorial
---

# Lección 1: Instalación de Python

## Introducción

Python es uno de los lenguajes de programación más populares y versátiles del mundo. Es utilizado en desarrollo web, ciencia de datos, inteligencia artificial, automatización y mucho más. En esta primera lección, aprenderemos cómo instalar Python en diferentes sistemas operativos.

## ¿Qué es Python?

Python es un lenguaje de programación de alto nivel, interpretado y de propósito general. Fue creado por Guido van Rossum y lanzado por primera vez en 1991. Sus características principales incluyen:

- **Sintaxis simple y legible**: El código Python es fácil de leer y escribir
- **Interpretado**: No necesita compilación previa
- **Multiplataforma**: Funciona en Windows, macOS, Linux y más
- **Versátil**: Útil para múltiples propósitos y aplicaciones
- **Gran comunidad**: Amplio soporte y abundantes recursos de aprendizaje

## Requisitos del Sistema

Antes de instalar Python, verifica que tu sistema cumple con los siguientes requisitos mínimos:

- **Windows**: Windows 7 o superior
- **macOS**: macOS 10.9 o superior
- **Linux**: Cualquier distribución moderna
- **Espacio en disco**: Al menos 100 MB libres
- **RAM**: Mínimo 512 MB (2 GB recomendado)

## Instalación en Windows

### Paso 1: Descargar Python

1. Visita el sitio web oficial: [python.org](https://www.python.org)
2. Haz clic en "Downloads"
3. Selecciona la última versión estable de Python 3.x
4. Descarga el instalador ejecutable para Windows

### Paso 2: Ejecutar el Instalador

1. Ejecuta el archivo descargado (python-3.x.x.exe)
2. **IMPORTANTE**: Marca la casilla "Add Python to PATH"
3. Haz clic en "Install Now"
4. Espera a que se complete la instalación
5. Haz clic en "Close" cuando finalice

### Paso 3: Verificar la Instalación

Abre el Símbolo del sistema (cmd) y ejecuta:

```bash
python --version
```

Deberías ver algo como: `Python 3.11.0`

## Instalación en macOS

### Método 1: Instalador Oficial

1. Visita [python.org](https://www.python.org)
2. Descarga el instalador para macOS
3. Ejecuta el archivo .pkg descargado
4. Sigue las instrucciones del instalador
5. Verifica la instalación en Terminal:

```bash
python3 --version
```

### Método 2: Usando Homebrew (Recomendado)

Si tienes Homebrew instalado:

```bash
brew install python3
```

## Instalación en Linux

### Ubuntu/Debian

Python suele venir preinstalado, pero para asegurarte de tener la última versión:

```bash
sudo apt update
sudo apt install python3 python3-pip
```

### Fedora/CentOS/RHEL

```bash
sudo dnf install python3 python3-pip
```

### Verificar la Instalación

```bash
python3 --version
pip3 --version
```

## Instalación de pip

pip es el gestor de paquetes de Python. Generalmente se instala automáticamente con Python 3.4+.

Para verificar si pip está instalado:

```bash
pip --version
# o en algunos sistemas:
pip3 --version
```

Si no está instalado, descárgalo desde [get-pip.py](https://bootstrap.pypa.io/get-pip.py) y ejecuta:

```bash
python get-pip.py
```

## Configuración del Entorno de Desarrollo

### Editores de Texto Recomendados

1. **Visual Studio Code**: Gratuito, potente y con excelente soporte para Python
2. **PyCharm**: IDE especializado en Python (versión Community gratuita)
3. **Sublime Text**: Ligero y rápido
4. **Atom**: De código abierto y personalizable
5. **IDLE**: Viene incluido con Python, ideal para principiantes

### Instalación de Visual Studio Code

1. Visita [code.visualstudio.com](https://code.visualstudio.com)
2. Descarga e instala para tu sistema operativo
3. Instala la extensión de Python:
   - Abre VS Code
   - Ve a Extensions (Ctrl+Shift+X)
   - Busca "Python" de Microsoft
   - Haz clic en "Install"

## Configuración de Entornos Virtuales

Los entornos virtuales permiten aislar las dependencias de cada proyecto.

### Crear un Entorno Virtual

```bash
# Navega a tu carpeta de proyecto
cd mi_proyecto

# Crea el entorno virtual
python -m venv venv

# Activa el entorno virtual
# En Windows:
venv\Scripts\activate

# En macOS/Linux:
source venv/bin/activate
```

### Desactivar el Entorno Virtual

```bash
deactivate
```

## Verificación Completa de la Instalación

Crea un archivo llamado `prueba.py` con el siguiente contenido:

```python
import sys

print("¡Python está funcionando correctamente!")
print(f"Versión de Python: {sys.version}")
print(f"Ruta del ejecutable: {sys.executable}")
```

Ejecútalo:

```bash
python prueba.py
```

Si ves los mensajes sin errores, ¡la instalación fue exitosa!

## Solución de Problemas Comunes

### Windows: "python" no es reconocido

**Solución**: Agrega Python al PATH manualmente:
1. Busca "Variables de entorno" en el menú Inicio
2. Edita la variable PATH
3. Agrega la ruta de instalación de Python (ej: C:\Python311)

### macOS/Linux: Conflictos entre Python 2 y Python 3

**Solución**: Usa `python3` y `pip3` explícitamente en lugar de `python` y `pip`

### Problemas de Permisos en Linux

**Solución**: No uses `sudo` para instalar paquetes. Usa entornos virtuales o instala con `pip install --user`

## Recursos Adicionales

- [Documentación oficial de Python](https://docs.python.org)
- [Python para Principiantes](https://www.python.org/about/gettingstarted/)
- [Real Python Tutorials](https://realpython.com)
- [Python Package Index (PyPI)](https://pypi.org)

## Resumen

En esta lección has aprendido:

✓ Qué es Python y por qué es popular  
✓ Cómo instalar Python en Windows, macOS y Linux  
✓ Cómo verificar la instalación  
✓ Cómo instalar y configurar un editor de código  
✓ Cómo crear y usar entornos virtuales  
✓ Cómo solucionar problemas comunes  

## Próximos Pasos

En la próxima lección, escribiremos nuestro primer programa en Python y aprenderemos los conceptos básicos de la sintaxis del lenguaje.

¡Felicidades por completar la primera lección! Ahora estás listo para comenzar a programar en Python.
