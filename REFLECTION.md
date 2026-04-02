# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer:**

In this assignment, I learned how multithreading allows multiple tasks to execute within the same program while sharing memory and resources. I understood how threads are created in Java using Thread.start() and how they move between different states such as Runnable, Running, Waiting, and Terminated during execution. I also learned how methods like Thread.sleep() can be used to simulate CPU burst time in scheduling algorithms like Round-Robin. Another important concept I understood was how Thread.join() helps control execution order by making the scheduler wait until the current thread finishes its turn before moving to the next process. I was surprised by how the ready queue changes dynamically when processes do not finish within their time quantum and return back to the queue. This helped me understand how context switching works in CPU scheduling. Overall, the assignment helped me connect theoretical scheduling concepts with practical implementation using Java threads.

---

## Question 2: What was the most challenging part of this assignment?

**Your Answer:**
The most challenging part of this assignment for me was working with commits and implementing Feature 3, which was tracking the waiting time of processes. The commit part was difficult because it was my first time using GitHub, Git, and Visual Studio together while following a specific commit order. I had to make sure each feature was added step by step and committed correctly, which required extra attention. Feature 3 was especially challenging because the waiting time was not updating correctly at first, and it was difficult to understand where the update should happen inside the scheduler logic. I had to go back to the lecture slides to better understand how waiting time should be calculated during Round-Robin scheduling. It was confusing to determine the correct place in the simulation to track the waiting time while processes were moving in and out of the ready queue. However, working on this problem helped me better understand how process timing works inside CPU scheduling algorithms.

---

## Question 3: How did you overcome the challenges you faced?

**Your Answer:**

To overcome the challenges I faced, I carefully reviewed the assignment requirements and my code. For the waiting time feature, I created a separate copy of the code to experiment safely without affecting the original program. In this copy, I used temporary print statements to track variables and verify that the waiting time calculations were correct. Once I confirmed the logic worked, I applied the correct changes back to the main code. For the Git and commit challenges, I followed a step-by-step process to ensure my changes were properly committed and pushed. This methodical approach helped me understand the code better and debug it confidently while keeping the original program intact

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**Your Answer:**
Multithreading is useful in real-world applications where multiple tasks must run at the same time without slowing down the program. For example, in music or video streaming apps, one thread can handle downloading content while another plays the media, preventing interruptions or freezes. In social media apps, threads allow background updates, notifications, and user interactions to happen simultaneously. From this assignment, I learned how threads share memory and are scheduled by the CPU using time slices, which helps prevent one task from blocking others. Understanding thread states and the scheduler’s behavior also shows why tasks are executed fairly and efficiently. This knowledge helps me see how software ensures smooth performance and responsiveness in multi-tasking environments. Using threads in such scenarios improves user experience and prevents delays in critical tasks.



