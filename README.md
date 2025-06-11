# Philosophers

> "I never thought philosophy would be so deadly."

## 🧠 Summary

This project simulates the classical Dining Philosophers Problem using threads and mutexes. It is part of the 42 School curriculum and focuses on handling concurrency, synchronization, and avoiding deadlocks in C.

---

## 🚀 What I Learned

This project helped me understand and gain hands-on experience in several key areas of systems programming:

### ✅ Thread Management
- How to create, manage, and synchronize **multiple threads** using `pthread_create`, `pthread_join`, and `pthread_detach`.
- Representing each philosopher as a thread and safely managing their lifecycle.

### ✅ Mutexes and Synchronization
- Using **mutexes** to avoid data races and manage shared resources (forks).
- Implementing **mutex-protected** sections to prevent conflicting access to critical data.
- Avoiding **deadlocks** by controlling the order of fork acquisition.

### ✅ Time Management
- Measuring precise time intervals using `gettimeofday` and implementing custom sleep functions.
- Ensuring state changes and death detection occur with strict time constraints (e.g., detecting death within 10ms).

### ✅ Robust C Programming
- Respecting the 42-Norm coding style and memory management rules.
- Avoiding memory leaks, segmentation faults, and ensuring thread-safe operations.

### ✅ Debugging Concurrent Programs
- Learning how **non-determinism** affects concurrent programs and how to debug such behavior.
- Building **tools and test cases** to simulate different scenarios and edge cases (like one philosopher, starvation, etc.)

---

## 💡 Why It Was Important

Before this project, I had limited experience with real-world multi-threaded programming. While I understood the theory of threads and mutexes, this project forced me to **build a working system** where any mistake could cause:

- Philosophers to die unexpectedly
- Deadlocks where no one can eat
- Overlapping or missing log messages

This hands-on implementation taught me that **concurrency isn't just theory—it’s about precision, discipline, and attention to detail.**

---

## 🧩 Project Description

- Each philosopher is a **thread**.
- Forks are represented using **mutexes**.
- A philosopher needs two forks (left and right) to eat.
- The simulation stops when:
  - A philosopher dies.
  - Every philosopher has eaten at least `number_of_times_each_philosopher_must_eat` times (optional argument).