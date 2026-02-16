
# MCU Architecture Diagram

                +-----------------------+
                |        CPU Core       |
                |  (Registers, ALU)     |
                +----------+------------+
                           |
        -----------------------------------------
        |                 |                     |
   +----v----+      +-----v-----+        +------v------+
   |  Flash  |      |   RAM     |        | Peripherals |
   | Program |      | Stack/    |        | GPIO, UART  |
   | Memory  |      | Heap      |        | Timers, ADC |
   +---------+      +-----------+        +-------------+

Description:
- Flash stores program code
- RAM stores variables and stack
- CPU executes instructions
- Peripherals connect to real world
📄 02_Super_Loop_Model.md
# Super Loop Architecture

                +------------------+
                |      main()      |
                +---------+--------+
                          |
                     while(1)
                          |
        -----------------------------------------
        |              |              |
   read_sensor()   control_motor()  update_lcd()
        |              |              |
        -----------------------------------------
                          |
                       repeat forever

Important:
- Execution is sequential
- No priority
- No real multitasking
- Timing depends on total loop time
📄 03_Interrupt_Flow.md
# Interrupt Execution Flow

Normal Execution:

main() ---> Task A ---> Task B ---> Task C

Interrupt Occurs!

1. CPU saves context
2. Jump to ISR
3. Execute ISR
4. Restore context
5. Return to previous task

Flow:

Task A running
      |
      |  <--- Interrupt Signal
      v
+-------------------+
|   ISR Function    |
+-------------------+
      |
      v
Return to Task A
📄 04_RealTime_Timeline.md
# Real-Time Timing Diagram

Example Tasks:

Motor Control: Period = 1ms
Sensor Read:   Period = 5ms
Display:       Period = 20ms

Time (ms) →

0    1    2    3    4    5    6    7    8    9   10

Motor:  X    X    X    X    X    X    X    X    X
Sensor: X                         X
Display: X

X = Task execution

Without RTOS:
Motor might miss some slots.

With RTOS:
Scheduler ensures correct timing.
📄 05_BareMetal_vs_RTOS.md
# Bare-Metal vs RTOS Comparison

Bare-Metal:

while(1) {
    task1();
    task2();
    task3();
}

Characteristics:
- Sequential
- No priority
- Hard to scale
- Timing depends on total loop


RTOS:

Task1 (High Priority)
Task2 (Medium Priority)
Task3 (Low Priority)

Scheduler decides execution order.

Characteristics:
- Preemptive
- Priority-based
- Deterministic
- Scalable
📄 06_Task_State_Model.md (Preparation for Module 3)
# Task State Model (RTOS)

           +------------+
           |  Running   |
           +-----+------+
                 |
                 | Preempted
                 v
           +------------+
           |   Ready    |
           +-----+------+
                 |
                 | Waiting for event
                 v
           +------------+
           |  Blocked   |
           +------------+

States:

Running  -> Currently executing
Ready    -> Waiting for CPU
Blocked  -> Waiting for event (queue, semaphore, delay)
