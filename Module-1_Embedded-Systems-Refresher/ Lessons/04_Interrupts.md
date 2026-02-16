
```markdown
# Lesson 4 — Interrupts

**Definition:** A hardware signal that temporarily stops the main program to run an ISR (Interrupt Service Routine).

**Example:**

```c
void EXTI0_IRQHandler(void) {
   led_toggle();
}


Rules for ISRs:

Keep short

Avoid blocking or delays
