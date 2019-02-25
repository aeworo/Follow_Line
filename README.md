1. Realizamos un filtro de color en el espacio hsv usando la biblioteca de opencv, de los datos que obtenemos del sensor cámara, para quedarnos sólo con la carretera por la que va a circular el coche. El resultado será una zona en blanco que es la carretera y la negra el resto.

2. Teniendo ya todo lo anterior, el siguiente paso es conseguir los dos puntos extremos de la linea roja. Para ello miramos siempre la fila 365 y añadimos al array izquierdo la columna donde 'value' es 255 y al array derecho la columna donde 'value' es -255. 'Value' es la diferencia entre el pixel actual y el anterior.

3. En este paso calculamos la posición media de la carretera, teniendon en cuenta varios casos:
  3.1. Array izquierdo  y array derecho estan llenos, la posición intermedia será la suma de los dos entre 2.
  3.2. Array izquierdo lleno y derecho vacío, la posición intermedia será la suma del array izquierdo más las columnas entre 2.
  3.3. Array izquierdo vacío y derecho lleno, la posición media será array derecho en la posicion cero entre 2.
  3.4. Si están los dos vacíos, los rellenamos, los sumamos y dividimos entre 2. Obtenemos la posición media.
  
4. Por último, con un controlador P le damos velocidad de avance y giro probando diferentes valores para cada una.


