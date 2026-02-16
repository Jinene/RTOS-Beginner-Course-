# Lesson 4 — How RTOS Solves Timing Issues

- **Scheduler:** Runs tasks based on priority  
- **Preemption:** High-priority interrupts low-priority tasks  
- **Deterministic behavior:** Predictable latency and jitter

Example tasks:

| Task | Period | Priority |
|------|--------|----------|
| Motor Control | 1ms | High |
| Sensor Read   | 5ms | Medium |
| LCD Update    | 20ms | Low |

✅ RTOS ensures motor runs every 1ms.


