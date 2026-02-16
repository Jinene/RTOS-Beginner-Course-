

```markdown
# Exercise 2

Why should an ISR be short?

**Answer:**  
Long ISR blocks CPU, other interrupts, and main loop → increases latency and jitter.
Exercise3.md
# Exercise 3

Is this multitasking?

```c
while(1) {
   if(flag_uart) process_uart();
   if(flag_adc) process_adc();
}
Answer:
No, it is sequential polling, not true multitasking.

