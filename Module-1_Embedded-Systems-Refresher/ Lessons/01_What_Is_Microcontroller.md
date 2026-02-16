01_What_Is_Microcontroller.md
# Lesson 1 — What Is a Microcontroller?

A **microcontroller (MCU)** is a small computer on a single chip. It contains:

- CPU (processor core)
- RAM (volatile memory)
- Flash memory (program storage)
- Peripherals (GPIO, UART, SPI, I2C, Timers, ADC…)

**Examples:**

- STM32F4  
- ESP32  
- ATmega328P  

**How it Works:**

1. MCU powers on  
2. Reads reset vector  
3. Loads stack pointer  
4. Executes main program  

**Bare-metal execution example:**

```c
int main() {
    init();
    while(1) {
        // your logic
    }
}


✅ Outcome: Understand MCU architecture and bare-metal execution.

