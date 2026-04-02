# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is a program that is currently in execution, and it is considered heavyweight because each process has its own memory space and system resources. A thread is a smaller unit inside a process that performs a task, and threads share the same memory and resources of the process, so they are lightweight and faster to create than processes. Another difference is that communication between threads is faster because they share the same memory, while processes require inter-process communication.

We used threads in this assignment instead of separate processes because the scheduler simulation runs multiple processes as threads inside the same program and manages them using the ready queue. For example, in SchedulerSimulation.java, each process is executed as a thread using Thread.start() and paused using Thread.sleep() to simulate CPU burst time during Round-Robin scheduling. This makes threads more suitable than separate processes because they are easier to control and switch between inside the simulation. 

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

In Round-Robin scheduling, if a process does not finish during its time quantum, the CPU stops executing it and performs a context switch to another process. The unfinished process is placed at the end of the ready queue and waits until its turn comes again. When it gets the CPU again, it continues execution from where it stopped.

Example from my output:
```
P2 executing quantum [4000ms]
P2 completed quantum 4000ms │ Overall progress: 70%
Remaining time: 1705ms
P2 yields CPU for context switch

P2 (Priority: 2) enters the ready queue │ Burst time: 5705ms
```

**Explanation of example:**
This snippet shows that P2 did not complete its burst time in one quantum. The scheduler moved it back to the ready queue, allowing other processes to run. This re-queueing behavior ensures that no single process monopolizes the CPU, making scheduling fair and predictable. The behavior is implemented in the schedule() method of SchedulerSimulation.java, which checks remaining burst time and re-queues the process if necessary.
---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**



1. **New**:P1 is in the New state when the Process object is created but before Thread.start() is called.

2. **Runnable**: After Thread.start(), P1 enters Runnable and waits in the ready queue for the scheduler to select i

3. **Running**: When the scheduler picks P1 from the ready queue, it enters Running and executes for a time quantum using the run() method.

4. **Waiting**:A thread enters Waiting if it pauses, for example using Thread.sleep(), but in my simulation P1 never had to wait for resources, so it skipped this state.

5. **Terminated**: P1 enters Terminated after completing its burst time. The scheduler prints that P1 finished execution, marking the end of the thread lifecycle

 

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web server handling multiple users

**Description**: 
A web server receives requests from many users at the same time. Each request can be handled by a separate thread, and the CPU switches between these threads to process them.

**Why Round-Robin works well here**: 
Round-Robin scheduling works well because it gives each thread a small time slice so all users get a chance to be served without one request taking all the CPU time. This improves fairness and makes the server more responsive for multiple users.

### Example 2: Operating system running multiple applications

**Description**: 
An operating system runs many programs at the same time, such as a browser, music player, and text editor. Each program may have threads that need CPU time to run.

**Why Round-Robin works well here**: 
Round-Robin scheduling allows each program’s thread to get CPU time in turns. This prevents one program from blocking others and makes the system feel smooth and responsive for the user. It also ensures fair sharing of CPU resources between applications.

---

## Summary

**Key concepts I understood through these questions:**
1. The difference between a thread and a process
2. How Round-Robin scheduling works,especially what happens when a process does not finish within its time quantum,inculding context switches and queue behavior
3. The lifecycle of a thread.

**Concepts I need to study more:**
1. Writing code that handles multiple threads and simulates scheduling.
2. ore about Java thread management.
