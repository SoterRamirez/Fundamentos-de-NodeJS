# Fundamentos de NodeJS

## Node: orígenes y filosofía

Sabias que NodeJs es una de las formas mas rapidas de desarrollar ejecutar y correr código en el servidor de forma muy escaladle.

Como funciona desde los fundamentos, core y como podemos tulizarlo para producción.

¿Qué es NodeJS?  Un entorno de ejecución de JavaScript fuera del navegador. Se crea en 2009 orientado a servidores.

### ¿Y por que es tan importante?

¿Fuera del navegador? No necesita un navegador, se puede ejecutar en:

- Servidores
- Herramientas
  - Transpiladores, scraping, automatización...

### Características de NodeJS

#### Concurrencia

- Todas sus entradas son Monohilo, con entradas y salidadas asíncronas.
- Un proceso por cada núcleo del procesador.

Esto siguiente es super importante para Node.

#### Motor v8

- Entorno de ejecución de JS creado por Google, y libre desde 2008.
- Escrito en C++
- Convierte JS en código máquina en lugar de interpretarlo en tiempo real.

El motor v8 lo que hace es convertir código js a codigo maquina y es extremadamente rápido, este código maquina nos va a permitir que nuestras aplicaciones por un lado tienen un error de sintaxis fallen en el momento que iniciamos y no en el momento que llegaste a ese punto de sintaxis, por lo cual nos muchísima robustación a nuestro código. Lo segundo es que al estar escrito en c++ va a ser extremadamente rápido.

Este motor es libre OpenSource 

#### Módulos

Todo lo que no sea sintaxis de programación, son módulos. Muchos módulos vienen por defecto en el paquete de Node. Puedes crear tus propios módulos.



#### Orientado a eventos

Hay un buble de eventos que se ejecutan constantemente, puedes oriantar tu código de forma reactiva.

Cuando suseda X cosa, que se ejecute esto otro.

## EventLoop: asíncrona por diseño

Imagines que un Eventloop es un circulo que va dando vueltas y vueltas.

![img](https://i.ibb.co/j42621b/event-loop.png)

**Event Queue:** Contiene todos los eventos que se generan por nuestro código (Funciones, peticiones, etc.), estos eventos quedan en una cola que van pasando uno a uno al Event Loop.

**Event Loop:** Se encarga de resolver los eventos ultra rápidos que llegan desde el Event Queue. En caso de no poder resolverse rápido, enviá el evento al Thread Pool.

**Thread Pool:** Se encarga de gestionar los eventos de forma asíncrona. Una vez terminado lo devuelve al Event Loop. El Event Loop vera si lo pasa a Event Queue o no.