---
layout: post
title:  "Instalación rápida de Python"
date:   2021-07-01 10:22:44 -0500
categories: Python
---

Phyton es un lenguaje de programación de facil aprendizaje.  Este lenguaje es usado para solucionar de manera facil una gran cantidad de problemas.  Debido a su corta curva de aprendizaje, casi, desde el primer dia en que empiezas a aprenderlo.

En esta entrada, explicare como instalar la ultima version de Python en Windows.

#### Primero ####
Se debe identificar que versión de windows ternemos `x86` ó `x64`. Para lo cual, debe hacer lo siguiente:
1. Hacer clic derecho en el menu inicio.
2. Seleccionar la opción `Sistema`.
3. Ubicar la descripción `Tipo de Sistema`, la cual debe ser `Sistema operativo de 64 bits, procesador x64` para sistemas 64 bits ó x86-based PC para sistemas 32 bits.

#### Segundo ####
Descargar el instalador de Python apropiado para tu sistema Windows, desde la su [página oficial] [pagina-oficial].

#### Tercero ####
Una vez descargado el instalador, hacerle doble clic y seguir las instrucciones.  Usualmente, debes dejar las opciones por defecto y presionar el boton siguiente, siguiente hasta completar la instalación.

#### Cuarto ####
Al terminar, solo debes verificar que la instalacion culmino correctamente y verificar que los ejecutables de Python fueron agregados como variable de entorno.  Para esto, solo debes abrir un terminal presionando `Tecla Windows + R` en el escritorio de windows.  Y escribir `cmd`.

Se abrira una ventana del terminal de comandos de windows.  Aqui, escribiras el siguiente comando
`python --version`.  

{% highlight console %}
C:\>python --version
Python 3.10.5

C:\>
{% endhighlight %}

Si el mensaje de respuesta es: `Python 3.10.5`, haz terminado exitosamente la instalación.

Si por el contrario, obtienes el siguiente error:
{% highlight console %}
C:\>python --version
"python" no se reconoce como un comando interno o externo,
programa o archivo por lotes ejecutable.

C:\>
{% endhighlight %}

Debes verificar que, la ruta de instalacion de Python este agregada al PATH de Windows haciendo lo siguiente:
1. Sigue [**Primero**](#primero) hasta el paso 2.
2. Seleccionar la opción `Configuración avanzada del sistema`.
3. Hacer clic en el boton `Variables de entorno`
4. En la seccion Variables de entorno, buscar la variable `path` y.
5. Seleccionar `path` y darle clic en el boton `Editar`.
6. Agregar la ruta en donde se encuentra instalado Python. Para la version 3.10 usualmente es `C:\Python310`
7. Comprobar segun el paso [**Cuarto**](#cuarto)


Ya que lograste instalar Python, puedes continuar aprendiendo con [Mi primer programa en Python][next-post]


[pagina-oficial]: https://www.python.org/downloads/windows/
[next-post]: https://erossiano.github.io/python/2022/07/01/mi-primer-programa.html

