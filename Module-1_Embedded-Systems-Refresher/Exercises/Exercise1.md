
### Exercise1.md

```markdown
# Exercise 1

Explain why this system can fail:

```c
while(1) {
   read_temperature();   // 10ms
   update_display();     // 15ms
}
Motor needs update every 5ms.


**Answer:**

Total loop = 25ms  
Motor misses 5ms deadline → system unstable.

---
