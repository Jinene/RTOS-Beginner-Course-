
# Lesson 3 — Super Loop Architecture

Classic embedded design:

```c
while(1) {
   read_sensor();
   control_motor();
   update_display();
}


Sequential execution

No real multitasking

Timing issues if tasks take variable time

Problem: If a task takes too long, other tasks are delayed → system fails hard real-time constraints.



