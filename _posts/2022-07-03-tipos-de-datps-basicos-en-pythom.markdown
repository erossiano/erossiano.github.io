---
layout: post
title:  "Tipos de datos bàsicos en Python"
date:   2022-07-03 15:07:39 -0500
categories: python
---
Como en la mayoria de lenguajes de programaciòn, Python, tambien maneja unos tipos basicos de datos.  Estos coresponden al los datos numericos y caracteres.

Dentro de los datos numericos tenemos:

### Enteros (`int`)###
Los cuales corresponden a numeros positivos y negativos sin punto decimal.  Ejemplo:

{% highlight console %}
1, 
2, 
-1,
-900,
800
{% endhighlight %}

### Decimales (`float`)###
Corresponden a numeros positivos o negativos con una parte entera y otra decimal, separdos por un punto. Ejemplo

{% highlight console %}
1.0
-10.895
900.15
-58.6
{% highlight %}

### Caracter (`chr`)###
Corresponde a un solo caracter alfanumerico, simbolo, signo.  Generalmente se usa comilla simple para representarlos. Por ejemplo:

{% highlight console %}
'1'
'A'
'ñ'
'*'
'+'
'?'
{% highlight %}


###Cadena de Texto ò caracteres (str)###
Corresponde a cualquier cadena de caracteres.  Se usan comillas dobles para representarlos, aunque es posible usar comilla simple. Por ejemplo:

{% highlight console %}
"Pablito clavo un clavito"
"Hola mundo"
"python"
"a"
{% highlight %}

### Booleano (`bool`)###
Este tipo nos permite representar el valor de Falso (False) o Verdadero (Truth).

{% highlight console %}
True
False
{% highlight %}


## Conversion de tipos de datos ##
Existe la posibilidad de convertir estos tipos de datos entre si, por ejemplo:

{% highlight python %}
entero = 56
decimal 11.52
cadena = "Pablito clavo un clavito"
boleano = True
{% highlight %}

Los valores decimales y boleanos pueden convertirse en enteros.  Asimismo, los decimales pueden ser convertidos en enteros. Por ejemplo:

Para los enterios
{% highlight python %}
print(int(decimal))
#=>11

print(int(boleano))
#=>1
{% highlight %}

Para los decimales
{% highlight python %}
print(float(entero))
#=>56.0

print(float(boleano))
#=>1.0
{% highlight %}

Para la conversiòn de caracteres, es posible realizar la conversion de entero a caracter mediante  `chr()` o de caracter a entero mediante `ord()`.  Ejemplo:

Para los decimales
{% highlight python %}
print(chr(entero))
#=>'8'

print(ord("a"))
#=>97
{% highlight %}

Ahora, para las cadenas de texto, se permite la conversion de cualquier tipo de dato a `str`. Por ejemplo:
{% highlight python %}
print(str(entero))
#=>"56"

print(str(decimal))
#=>"11.52"

print(str(boleano))
#=>True
{% highlight %}

Adicionalmente a estos tipos de datos exiten unos [tipos de datos complejos][next-post].

[next-post]: https://erossiano.github.io/python/2022/07/04/tipos-de-datos-complejos.html