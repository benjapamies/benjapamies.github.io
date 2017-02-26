---
layout: post
title:  "Probando markdown"
date:   2017-02-26 01:49:28 +0100
categories: jekyll update
---
> Bloque de cita para, por ejemplo, empezar los post con una introducción.
> Esta línea también pertenece al mismo bloque.
>
> Este es un post de prueba para probar la sintaxis de markdown.

## Título

### Subtítulo

También se pueden meter bloques de código para ejemplos de algoritmos. 
Por ejemplo, el siguiente es un código en el lenguaje Java.

**_Factorial en Java:_**
{% highlight java %}
/**
 * Cálculo recursivo del factorial de un número
 * 
 * @param num
 * @return El resultado de multiplicar un número por su anterior 
 *     hasta llegar a 1
 */
public static long factorial( long num ) {
    if( num <= 1 ) {
        return 1;
    } else {
        return num * factorial( num - 1 );
    }
}
{% endhighlight %}

Las `palabras importantes` se pueden resaltar y se pueden crear [links][linkado].

Listas:
- Primer elemento de una lista sin numeración
- Segundo elemento de una lista sin numeración
  - Subelemento de una lista sin numeración

1. Primer elemento de una lista numerada
2. Segundo elemento de una lista numerada

Tabla:

Columna alineada a la izquierda | Columna centrada | Columna alineada a la derecha
--- | :-: | --:
HP 250 G5 Z3A41ES | Intel Core I3-5005U/8GB/256SSD/15.6" | 509 €
Acer Aspire R5-571T-596H | Intel Core i5-6200U/8GB/256GB SSD/15.6" Táctil | 819 €

[linkado]: https://github.com/benjapamies