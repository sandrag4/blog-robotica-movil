# P6 - Marker visual loc

## Exploración (navegación)
El robot se mueve en linea recta hacia delante (estado "FORWARD") durante un tiempo aleatorio de entre 16 y 30 segundos o hasta que el láser detecta un obstáculo cercano.

Cuando el láser detecta un obstáculo cercano, mira la distancia a obstáculos de cada rayo del láser para decidir si el robot gira hacia la derecha o hacia la izquierda.

Después el robot retrocede (estado "BACKWARD") durante un tiempo de entre 0.6 y 1.2 segundos.

Cuando el robot termina de retroceder, el robot gira en la dirección elegida (estado "RIGHT_TURN" o estado "LEFT_TURN") durante un tiempo de entre 1.2 y 2.8 segundos. Cuando pasa este tiempo, si hay obstáculos cercanos justo delante del robot sigue girando hasta que esos obstáculos dejan de estar delante. Si no hay obstáculos delante del robot, puede volver a moverse en linea recta hacia delante (estado "FORWARD").


## Autolocalización
Cuando el robot ve una baliza:
- Se obtiene la posición en el mundo (x, y, z, yaw) de la baliza
- Se obtiene pose_t, pose_r y la distancia del robot a la baliza

Si la distancia de la cámara a la baliza es menor de 3.5 metros y mayor de 0.5 metros:
- Se calcula RT de la baliza respecto al mundo
- Se calcula RT de la baliza respecto a la cámara
- Se calcula RT de la cámara respecto a la baliza
- Se calcula RT del robot respecto del mundo
- De la RT del robot respecto del mundo se obtine x, y, yaw estimadas de la posición en el mundo del robot
- Se guarda la posición y orientación estimadas y la posición y orientación de la odometría del robot.

Si no se ve ninguna baliza o la baliza observada no está dentro del rango de distancia mencionado anteriormente:
- Se calcula la diferencia entre la odometría en el momento actual y la odometría guardada la última vez que se vio una baliza.
- Se le suma a la última posición y orientación estimada la diferencia en la odometría


## Imagen
![Imagen](https://github.com/sandrag4/blog-robotica-movil/blob/main/images/p6-screenshot-marker_visual_loc.png "Imagen")


## Video
[video](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/IQAFeuQMsKXoTbMl9161MH01AQmCdegdDwS2v-dqjbomAVo?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=j8BzXu)
