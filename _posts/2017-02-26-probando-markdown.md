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