# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 29, 2026, 1:20 PM]
**What I did**: 
Forked the repository and set up my student ID
**Details**: 
 Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (445052171)
- Compiled and ran the program successfully
**Challenges**: 
linking github ,git and vs togather
**Solution**: 
Used the VS Code "Accounts" icon to sign in to GitHub and used the Command Palette ($Ctrl+Shift+P$) to clone my forked repository directly into a local folder.
**Time spent**: 
1hour
---

### Entry 2 - [March 30, 2026, 10:00 AM]
**What I did**: 
Implemented Feature 1: Process Priority.
**Details**: 
Modified the Process class to include an integer field for priority (1-5).

Updated the process creation logic to assign a random priority to each process.

Added a print statement to display the priority when a process enters the ready queue.
**Challenges**: 
Ensuring the random priority was generated within the specific 1-5 range.
**Solution**: 
Used Random.nextInt(5) + 1 to shift the range from 0–4 to 1–5.

**Time spent**: 30 minutes

---

### Entry 3 - [March 30, 2026, 3:30 PM]
**What I did**: 
Implemented Feature 2: Context Switch Counter.
**Details**: 
Declared a static counter variable in the SchedulerSimulation class.

Added logic to increment this counter every time a new process thread starts running.

Printed the final total at the very end of the simulation.
**Challenges**: 
The counter was initially too high because it counted the very first process as a "switch."
**Solution**: 
Adjusted the final output to print counterContextSwitch - 1 to accurately reflect the number of times the CPU changed from one process to another.
**Time spent**: 
45 minutes
---

### Entry 4 - [March 31, 2026, 11:45 AM]
**What I did**: 
mplemented Feature 3: Track Waiting Time and Summary Table
**Details**: 
Added creationTime, completionTime, and waitingTime fields to the Process class. Captured System.currentTimeMillis() at construction (Arrival) and when isFinished() becomes true (Completion). Calculated waiting time using the formula: $WT = Completion - Arrival - Burst$. Implemented a processList to store finished processes for the final summary.
**Challenges**: 
The waiting time was being calculated in milliseconds, which resulted in very large numbers that were hard to read in the table
**Solution**: 
sed String.format with %-12.3f sec and divided the milliseconds by 1000.0 to display the waiting time in a cleaner "seconds" format.
**Time spent**: 
1.5 hours
---

### Entry 5 - [Date and Time]
**What I did**: 
Final Code Review, Documentation, and Video Recording
**Details**: 
Verified that all ANSI colors were functioning and the table borders aligned correctly.Completed the REFLECTION.md and ANSWERS.md files using technical terms like "Thread Lifecycle" and "Round-Robin." Recorded the demonstration video showing the code execution and my unique student ID (445052171)
**Challenges**: 
Ensuring the Google Drive link was accessible to "Anyone with the link" so the professor doesn't encounter a permission error.
**Solution**: 
Tested the link in an Incognito/Private browser window to confirm it worked without being logged in.
**Time spent**: 
1 hour
---



## Summary

**Total time spent on assignment**: [~5.5 hours.]

**Most challenging part**: 
The hardest part was definitely Feature 3 (Waiting Time). In my code, the processes keep stopping and starting because of the "Time Quantum," so I couldn't just use a simple timer. I had to make sure creationTime was saved the exact moment the process was born and completionTime was saved only when it finally finished its last turn. The math ($Wait = Finish - Start - Burst$) was confusing at first because if I didn't divide the result by 1000.0, the numbers in the table were huge and didn't make sense. It took a lot of trial and error to get the columns in the summary table to line up perfectly.
**Most interesting learning**: 
found it fascinating to observe how the Thread Lifecycle actually dictates the process statistics. Using currentThread.join() was a "lightbulb moment" for me—it showed me how the main scheduler thread pauses and synchronizes with the process threads. Seeing my student ID (445052171) act as a seed for the Random class was also interesting, as it proved how a single number can determine the entire "fate" of the simulation, from the number of processes to the length of their bursts.the 
**What I would do differently next time**: 
Next time, I would spend more time reading the assignment instructions before I start typing any code. I realized halfway through that there were specific rules about using my university email and making separate commits for every feature. To solve problems better, I would try to fix one small piece at a time instead of trying to do the whole thing at once. This would make the "messy" parts of the code easier to handle and keep the project more organized from the start.
