# P1 - Vacuum Cleaner

## Algorithm
The vacuum cleaner starts in the "SPIRAL" state doing a spiral, and remains in the spiral state until de laser detects an obstacle closer than 0.2 or the bumper detects a collision. 

When the state is "FORWARD" or "SPIRAL" and the laser or the bumper detect an obstacle, the state changes to "BACKWARD" and the vacuum cleaner moves backward for a random time in between 0.3 and 0.8 seconds.

Then, the state changes to "RIGHT_TURN" or "LEFT_TURN" depending on the location of the obstacle previously detected, and keeps turning in the chosen direction for a random time in between 0.4 and 1.2 seconds.

After turning for a certain time, the state becomes "FORWARD" and the robot moves backward for a random time in between 1.5 and 2.5 seconds.

Then, the state changes again to the "SPIRAL" state.


## Exploration
Vacuum cleaner image after 36 minutes:

![Vacuum cleaner image](https://github.com/sandrag4/blog-robotica-movil/blob/main/images/p1-screenshot-vacuum_cleaner.png "Vacuum cleaner image")


36 minute video at 4.0x speed:

[Vacuum cleaner video](https://urjc-my.sharepoint.com/:v:/g/personal/s_gonzaleza_2022_alumnos_urjc_es/ERTUxAtbH4hMh4aJHl9zhCcBU8olvQjOd0GuCimk1AFXAw?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=X6INV4)


## Difficulties
The robot got trapped in a small area for an excesive long amount of time, I solved this problem by changing the minimum and maximum time limits in the random time generator, modifing the duration of algorithm's states.



