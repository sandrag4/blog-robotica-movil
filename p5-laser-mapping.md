# P5 - Laser mapping

## Exploración (navegación)
Se mueve hacia abajo hasta que el láser se encuentra con un obstáculo de frente, en ese momento gira a la derecha si tiene hueco y las celdillas a la derecha no fueron exploradas, si no, gira a la izquierda y avanza en esa dirección durante una distancia determinada o hasta que se encuentra con un obstáculo de frente, en ese momento si la dirección previa fue hacia abajo, gira hacia arriba y si fue hacia arriba, gira hacia abajo y avanza recto hasta encontrarse un obstáculo, en ese momento vuelve a repetir este proceso.
Si no es capaz de encontrar una dirección para explorar o todas las celdillas de la zona fueron exploradas, utilizará un algoritmo de bfs para buscar una celdilla a la que ir.


## Probabilidad (construcción del mapa)
Cada cierta distancia, cada vez que cambia de dirección y cada vez que se mueve a una celdilla lejana, obtiene los datos del laser y para cada rayo calcula la probabilidad de que las celdillas que están en ese rayo estén libres o ocupadas. Calculo la probabilidad sumando el logaritmo si está ocupada y restando el logaritmo si está libre. Además engordo los obstáculos 2 celdillas por delante del obstáculo y unas cuantas por detrás. Después paso los logaritmos a probabilidades y esas probabilidades las convierto en pixeles en escala de grises para visualizar el mapa.


## Imagen
![Imagen](https://github.com/sandrag4/blog-robotica-movil/blob/main/images/p5-screenshot-laser_mapping.png "Imagen")


## Video
video:
[video](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/IQC_9KH8Mh3mTZ6jWTbpVUgtAYV2XOPwWPWK1PypGttiNhs?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=AU44eJ)
