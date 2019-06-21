En esta práctica, el objetivo es programar un coche de fórmula 1 simulado para que recorra todo el circuito siguiendo la línea roja trazada en el suelo.
Para llevar a cabo dicha implementación, he divido en dos la solución: La percepción y el manejo y control.

**1. PERCEPCIÓN**

EL primer paso es extraer las imágenes que nos proporcionan los sensores, en nuestro caso la cámara.
Una vez sacada, la convertimos al espacio HSV al ser esa más robusta a cambios de luminosidad y lo filtramos mediante funciones de opencv para quedarnos solo con la linea roja. Como resultado la línea roja, la pinta de color blanco y el resto de negro y  esa línea blanca es la que tendrá que seguir nuestro robot.


<img src="https://i.ibb.co/LzpSPyQ/followline.png" />

**2. MANEJO Y CONTROL**

Para dirigir y manejar los movimientos del robot he usado un controlador PD, que básicamente me servirá para corregir de forma proporcional el error cometido al conducir, es decir el salirme de la línea, y aumentar la estabilidad de mi coche. Para ello:

1. Sacamos la parte central de la carretera, que es simplemente dividir entre dos las posiciones de las columnas de la imagen filtrada.

2. Luego sacamos la posición en la que está el fórmula 1, y el error será la diferencia entre dicha posición y la centrar de la imagen antes saca en el punto 1.

3. A continuación aplicaré el controlador PD tanto al giro como a la velocidad de avance, lo cual consistirá en multiplicar por dos contantes Kp y Kd la velocidad de giro y la de avance. El valor de dischas constantes es experimental, es decir he ido probando hasta encontrar los valores ideales. 
Tengo un umbral de velocidad lineal, el cual dependiendo de la velocidad de giro aumentará o disminuirá. Y la de giro, aumentará o disminuirá dependiendo del valor de la desvición.

4. Con todo eso, ahora solo mandamos ordenes de avance o giro al coche con valores los de avance o los de giro calculados anteriorme.

[Enlace] (https://www.youtube.com/watch?v=6ECD9tS1CTk)

**CONCLUSIONES**

El controlador PD no ha sido muy difícil de implementar porque en internet hay muchísima documentación con ejemplos, lo más laborioso ha sido encontrar el valor de las constantes pertinentes.




