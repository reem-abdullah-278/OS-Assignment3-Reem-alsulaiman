#Assignment 3 - Complete Documentation

Student Name: Reem Abdullah Al-Sulaiman
Student ID: 444052278
Date Submitted: May7,2026

🎥 VIDEO DEMONSTRATION LINK (REQUIRED)
Video Link:https://drive.google.com/file/d/1pRfpKzbWp2b9jbhKvPXgyYPrO-mgg3YQ/view?usp=sharing
Video filename:44052278_Assignment3_Synchronization.mp4

Verification:
✔ Link is accessible
✔ Video is 3-5 minutes
✔ Shows code and commits
✔ Clear audio

---

# Part 1: Development Log

Entry 1 - April 29, 8:00 PM
What I implemented: Forked the repository and set my student ID.
Challenges encountered: Understanding the structure of the project.
How I solved it: Carefully read the README file.
Testing approach: Compiled and ran the program.
Time spent: 30 minutes

Entry 2 -April 30, 8:00 PM
What I implemented: Added ReentrantLock to protect shared counters.
Challenges encountered: Determining where to place lock and unlock.
How I solved it: Used try-finally blocks to ensure safe unlocking.
Testing approach: Checked correctness of counter values.
Time spent: 45 minutes

Entry 3 - May 1,8:00 PM
What I implemented: Protected executionLog using lock.
Challenges encountered: Preventing concurrent modification issues.
How I solved it: Wrapped log updates inside lock.
Testing approach: Ran program multiple times.
Time spent: 30 minutes
Entry 4 - May 3, 8:00 PM
What I implemented: Added Semaphore to control CPU access.
Challenges encountered: Understanding acquire and release methods.
How I solved it: Applied semaphore around execution section.
Testing approach: Verified that only one thread runs at a time.
Time spent: 40 minutes
---

# Part 2: Technical Questions

Question 1:
Two race conditions exist in the original code. First, multiple threads update shared counters like contextSwitchCount simultaneously, which may lead to incorrect values. Second, executionLog can be accessed by multiple threads at the same time, which may cause inconsistent data or runtime exceptions. Synchronization ensures that only one thread modifies shared data at a time.

Question 2:
ReentrantLock is used to protect shared resources such as counters and logs to ensure thread safety. Semaphore is used to control access to CPU, allowing only one thread to execute at a time. Locks ensure safe data modification, while semaphore controls resource access.

Question 3:
Deadlock occurs when threads wait indefinitely for resources held by each other. Two prevention techniques include using try-finally blocks and avoiding nested locks. In my implementation, I ensured all locks and semaphores are released properly using try-finally.

Question 4:
I used one lock (coarse-grained locking) for all counters. This simplifies the implementation and reduces the chance of errors. Fine-grained locking can improve performance but increases complexity. Since the counters are simple, one lock is sufficient and effective.

---

# Part 3: Synchronization Analysis

Critical Section #1:
Variables: contextSwitchCount, completedProcessCount, totalWaitingTime
Why they need protection: They are shared between multiple threads
Synchronization mechanism used: ReentrantLock
Justification: Prevents race conditions and ensures correct values

Critical Section #2:
Resource: executionLog
Why it needs protection: Multiple threads write to it simultaneously
Synchronization mechanism used: ReentrantLock
Justification: Prevents data corruption and exceptions

Critical Section #3:
Purpose of semaphore: Control access to CPU
Number of permits: 1 (binary semaphore)
Where implemented: Around process execution
Synchronization mechanism used: Semaphore
Effect on program behavior: Ensures only one thread executes at a time

---

# Part 4: Testing and Verification

Test 1: Consistency Check
I ran the program multiple times and observed consistent results. Synchronization ensures stable and correct output even with multiple threads.

Test 2: Exception Testing
I tested for ConcurrentModificationException and no errors occurred during execution.

Test 3: Correctness Verification
I verified that counters and waiting time values are correct after execution.

Test 4: Different Scenarios
I tested the program with different values and it behaved correctly in all cases.

---

# Part 5: Reflection and Learning

I learned that synchronization is essential in multithreaded programs to prevent race conditions and ensure data consistency. Using locks protects shared data, while semaphores control access to shared resources. These concepts are important in operating systems and real-world applications.

Real-world applications:
1. Banking systems where multiple transactions occur simultaneously
2. Database systems where multiple users access shared data

How I would explain synchronization:
Synchronization ensures that multiple threads do not access shared resources at the same time, similar to taking turns to use a resource.

---

# Part 6: GitHub Repository Information

Repository URL:https://github.com/reem-abdullah-278/OS-Assignment3-Reem-alsulaiman
Number of commits: 4

Commit messages:
1. Set student ID
2. Added ReentrantLock
3. Added Semaphore
4. Final commit

---

# Summary

Total time spent: 3-4 hours

Key takeaways:
1. Importance of synchronization
2. Using locks and semaphores
3. Preventing race conditions

Most challenging aspect: Understanding synchronization concepts
What I'm most proud of: Successfully implementing thread-safe code

End of Documentation
