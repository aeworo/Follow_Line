En esta práctica, el objetivo es programar un coche de fórmula 1 simulado para que recorra todo el circuito siguiendo la línea roja trazada en el suelo.
Para llevar a cabo dicha implementación, he divido en dos la solución: La percepción y el manejo y control.

**1. PERCEPCIÓN**

EL primer paso es extraer las imágenes que nos proporcionan los sensores, en nuestro caso la cámara.
Una vez sacada, la convertimos al espacio HSV al ser esa más robusta a cambios de luminosidad y lo filtramos mediante funciones de opencv para quedarnos solo con la linea roja. Como resultado la línea roja, la pinta de color blanco y el resto de negro y  esa línea blanca es la que tendrá que seguir nuestro robot.
<img src="https://i.ibb.co/LzpSPyQ/followline.png" />

**2. MANEJO Y CONTROL**






