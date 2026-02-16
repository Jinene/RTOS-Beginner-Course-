# Exercise 3

Is this multitasking?

```c
while(1) {
   if(flag_uart) process_uart();
   if(flag_adc) process_adc();
}
Answer:
No, it is sequential polling, not true multitasking.
