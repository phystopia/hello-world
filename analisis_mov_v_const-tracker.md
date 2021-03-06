# Movimiento de Velocidad Constante en Una Dimensión y su Análisis con Tracker

##### Alexander Osorio Caicedo, *M. Sc.*



Estudiaremos el video del movimiento de un cuerpo en una dimensión cuerpo con velocidad constante, usando para ello la aplicación **Tracker**.

## Movimiento en una dimensión con velocidad constante

La velocidad instantánea de un cuerpo se define como la tasa instantánea de cambio de posición con el tiempo:
$$
v = \frac {\mathrm{d}x}{\mathrm{d}t}
$$
Esto quiere decir que podemos encontrar el desplazamiento infinitesimal $ \mathrm{d}x $ durante un intervalo de tiempo $ \mathrm{d}t $ de la siguiente forma:
$$
\mathrm{d}x = v \, \mathrm{d}t
$$
Si queremos conocer el desplazamiento $ \Delta x $ del cuerpo desde  $ t_o = 0 $ hasta un tiempo arbitrario $ t $, este se puede hallar integrando la expresión anterior:
$$
 \int_{x_o}^x \mathrm{d}x =  \int_{t_o = 0}^t v \, \mathrm{d}t 
$$
En el caso de un cuerpo que se desplaza con velocidad *v* constante, 
$$
\int_{x_o}^x \mathrm{d}x = v  \int_{t_o = 0}^t \, \mathrm{d}t
$$

$$
\Delta \, x = v \, \Delta \, t
$$

donde:

$$
\Delta \, x = x - x_o \\
 \Delta \, t = t - t_o
$$

Combinando las ecuaciones $(5)$ y $(6)$ teniendo en cuenta además que $t_o = 0$, encontramos que la posición $x$ del cuerpo en un instante $ t $  está determinada por su velocidad y posición inicial de acuerdo con:
$$
x = v \,  t + x_o
$$
La expresión $(7)$ corresponde, en un gráfico *posición vs. tiempo*, a una linea recta cuya pendiente es igual a la velocidad del cuerpo y el corte con el eje y es su posición inicial.

## ¿Cómo sabremos si un cuerpo se mueve a velocidad constante?

Supongamos que tenemos registrado en video el movimiento descrito por un objeto y queremos saber si dicho objeto se desplazó a velocidad constante. Si pudieramos desplegar en una gráfica los puntos que describen la posición del cuerpo en cada instante de tiempo, la expresión $(7)$ nos dice que, si esos puntos se comportan (ignorando pequeñas desviaciones) como una linea recta podremos decir, con un buen margen de precisión, que ese cuerpo se movió a velocidad constante.

Si consideramos que un video se puede entender como una serie de fotogramas o *cuadros* que se presentan a nuestros ojos con una rapidez suficiente para hacernos creer que se trata de un movimiento continuo, podríamos entonces analizar el movimiento del cuerpo si tuvieramos una herramienta que nos permitiera:

- Identificar a cuántos cuadros por segundo se hizo la grabación, para conocer el tiempo transcurrido entre cada cuadro $(\Delta \, t)$.
- Introducir en el video una unidad de medida para calibrar con ella las distancias.
- Ubicar un sistema de referencia respecto al cual se pueda medir el desplazamiento del objeto $(\Delta x)$.

Tracker fue desarrollado con la idea de resolver este tipo de problemas.

## ¿Qué es Tracker?

**[Tracker](http://physlets.org/tracker/)** es una aplicación gratuita, multiplataforma (Windows, macOS, Linux) y de [código abierto](https://github.com/OpenSourcePhysics/tracker) desarrollada por Douglas Brown, que forma parte de los Recursos Computacionales para la Enseñanza que integran [The Open Source Physics Project](https://www.compadre.org/osp/?).

Tracker es una poderosa herramienta que combina el análisis de video y la creación de modelos computacionales construida sobre el framework Java del Open Source Physics (*OSP*), diseñada específicamente para la enseñanza de la Física.

En este Tutorial explicaremos cómo usar Tracker para el análisis de videos y su uso en un curso de Física.



## Análisis de un movimiento usando Tracker

El movimiento que analizaremos se encuentra en el video *pasco005.avi* que se encuentra en *Documentos/Tracker/Recursos/Videos*. A partir del análisis de un movimiento iremos introduciendo los elementos necesarios para  herramienta. Acuda a la Ayuda para un conocimiento más detallado del programa.

Recomendamos que cree una copia del video y la almacene en una carpeta creada especialmente para este proyecto. Un nombre sugerido es *Documentos/mov_1D*.

![ventana de inicio de tracker](/Users/aronnax/OneDrive/Documents/physica/tracker-01.png)

> Página de inicio de Tracker.

Al abrir el programa este nos presenta un entorno disponible para desarrollar nuestro proyecto. En Tracker se conoce como *pestaña* y consta de una serie de ventanas. La ventana principal albergará el video y las herramientas de seguimiento. Las ventanas laterales presentan los datos recogidos tanto en forma de gráficos preliminares como en forma de tablas. Bajo la ventana principal se encuentran además (escondidas) dos ventanas auxiliares, aunque por ahora no hablaremos de ellas.



### Incorporación del video en Tracker

![imagen 1](http://f.cl.ly/items/2z0O2U3g341u31112X1Q/Image%202019-05-30%20at%201.57.05%20PM.png)

> Incorporación de un video en Tracker.

Para iniciar el análisis del video, arrástrelo a la ventana principal o use el botón *Abrir Archivo*. 



### Configuración del clip

![video-clip](http://f.cl.ly/items/3S313Y0r3G0f1s1h2230/tracker-m1-im-03.png)

> Configuración del clip.

Los controles del reproductor situados en la parte inferior de la ventana principal nos permiten observar el video e identificar los cuadros que utlizaremos para el análisis. En este caso utilizaremos el video completo.

En Tracker, un *clip* es la sección del video donde se realizará el análisis. Esta ventana se puede seleccionar el cuadro desde donde queremos comenzar a analizar el movimiento y el cuadro final

Esta ventana también nos informa cual es la tasa. En este caso se trata de un video tomado a aproximadamente 10 cuadros por segundo, o a una décima de segundo por cuadro. Las cámares de dispositivos actuales graban video a una tasa típica de 30 cuadros/s. Esta información es útil nos permite ver que aunque el movimiento dura sólo un segundo

### Creación de una vara de calibración

![vara de calibración](http://f.cl.ly/items/0s0E2R0a1G2G093S0e1z/tracker-m1-im-05.png)

> Vara de calibración incorpoarada al video.
>

Primero debe identificarse un objeto de longitud conocida que se encuentre a la misma distancia de la cámara que el objeto que se va a analizar. Como puede observarse, en este video se dispuso una regla de 90 cm a lo largo del carril con ese objetivo.
Para observar mejor sus extremos se amplió la imagen al 400% de su tamaño original. Nótese que Tracker ya había ampliado la imagen al 235% para que coincidiera con el tamaño de la ventana (*To Fit* en la herramienta de Ampliación). Si los extremos del objeto que servirá como unidad de medida se salen del cuadro, pueden buscarse moviendo las guías de la  que aparecen a los lados derecho e inferior de la ventana.
Se oprime el botón *Calibración*, donde seleccionamos una nueva *Vara de Calibración*. Debemos identificar en el video la posición del extremo 1 (normalmente el izquierdo)  

### Ubicación del origen del sistema de coordenadas

![sistema de coordenadas](http://f.cl.ly/items/0h0T2O2j1u3m1m1o3q1i/tracker-m1-im-06.png)

> Ubicación del origen del sistema de coordenadas.

Después de tener una unidad de medida, ahora es necesario disponer de un eje de coordenadas. Este se crea con el botón *Ejes de Coordenadas*. El sistema coordenado se puede arrastrar al lugar que se quiera como el origen haciendo clic en su centro. En este caso escogimos dicho origen como la posición inicial del carro m~1~.

### Creación de una masa puntual

![creación masa puntual](http://f.cl.ly/items/1f0g2y3Q0U291u0n0C0v/tracker-m1-im-07.png)

> Configuración de una masa puntual.

Para nuestro análisis describiremos el carro como una partícula o masa puntual. Notemos que elegir un punto del carro como  que esto en ningún caso disminuye la precisión de nuestros resultados, pues en este caso el carro se mueve como un sólo cuerpo. El carro tiene un punto claro que permite su seguimiento a lo largo del movimiento. En la ventana de configuración de la masa puntual podemos cambiar su nombre, color y forma de la "huella" que va a dejar la masa puntual a lo largo de su recorrido. Para cierto tipo de análisis (cálculos de energía y momento lineal), es necesario conocer la masa del objeto a analizar. En este caso no es necesario, pero de todas formas se introdujo este valor aprovechando que está reportado en el video.

### Seguimiento cuadro por cuadro de la partícula a estudiar

![](http://f.cl.ly/items/041A2y24380u1U0B3G1X/tracker-m1-im-08.png)

> Registro de la posición del cuerpo cuadro a cuadro.

Con la masa puntual visible en en la parte superior se busca el punto que se va a seguir, y usando la combinación ⬆︎+ *clic* se registra su posición. El programa automáticamente pasara al siguiente cuadro del clip, donde se repite el procedimiento anterior. Esto continuará hasta llega al último cuadro.







###Uso de la Herramienta de Análisis

Enlace a video

En la modalidad *Auto-ajuste*  el programa busca automáticamente la línea recta que mejor describe el comportamiento de los puntos registrados. Utilizando un principio estadísitico conocido como *regresión lineal por el método de mínimos cuadrados* encontramos que la recta que mejor describe el comportamiento de los puntos tiene los siguientes parámetros:

- Pendiente, $ A =   0,3511 \pm 8,5 \times 10^{-4} $

- Corte con el eje y, $ B = 6,150 \times 10^{-3} \pm 1,5 \times 10^{-3} $

Donde hemos incluido el error estándar correspondiente a cada uno de dichos valores, aportado también por el ajuste.

Otro valor importante reportado por el programa es el valor del error cuartico medio del ajuste obtenido (*rms dev*)

$ rms \, dev = 4,022  \times  10^{-3} $

Este valor es mejor entre más cerecano se encuentre a cero.

## Interpretación física de los resultados

Ahora nos corresponde darle un significado físico a los resultados numéricos hallados.

La gráfica posición vs. t 

A partir del análisis realizado al inicio, sabemos que si la gráfica *posición vs. tiempo* los puntos se pueden ajustar adecuadamente a una linea recta, se trata de un movimiento de velocidad constante, donde los parámetros de pendiente (*A*) y corte con el eje *y* (*B*) corresponden a la velocidad del objeto y su posición inicial, respectivamente.

Por lo tanto podemos decir que el carro se desplazó durante el intervalo registrado en el video con una velocidad:

$ v = (0,3511 \pm 8,5 \times 10^{-4}) \, \frac{m}{s} $

$ v = (35,11 \pm 8,5 \times 10^{-2}) \, \frac{cm}{s} $

y que el carro se encontraba inicialmente a una distancia del origen del sistema de coordenadas:

$ x_o = (6,150 \times 10^{-3} \pm 1,5 \times 10^{-3}) \, m $

El movimiento del cuerpo puede describirse con la siguiente expresión:

$ x = (0,3511 \pm 8,5 \times 10^{-4}) \frac{m}{s} \, t + (6,150 \times 10^{-3} \pm 1,5 \times 10^{-3})\,m $

La *incertidumbre relativa* con la que nuestros resultados permiten determinar la velocidad del carro m~1~ es:

$ \frac {\Delta \, v} {v} = \frac {8,5 \times 10^{-4}}{0,3511} = 2,71 \times 10^{-3} $ o $ \frac {\Delta \, v} {v} = 0,271 \%  $

## Ejercicios

El uso de Tracker para el análisis de movimientos permite responder de manera practica preguntas que, de otra manera,  

### Cambio de posición del origen del sistema de coordenadas

¿Cómo cambiarán el gráfico *posición vs. tiempo* y los parámetros de movimiento si ubica el origen del sistema de coordenadas en un lugar a la izquierda de la posición inicial del carro?

¿Qué ocurrirá si ubica el origen del sistema de coordenadas a la derecha de la posición inicial del carro?





 