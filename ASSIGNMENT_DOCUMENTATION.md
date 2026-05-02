# Assignment 3 - Complete Documentation

**Student Name**: [Your Full Name]  
**Student ID**: [Your ID]  
**Date Submitted**: [Submission Date]

---

## 🎥 VIDEO DEMONSTRATION LINK (REQUIRED)

> **⚠️ IMPORTANT: This section is REQUIRED for grading!**
> 
> Upload your 3-5 minute video to your **PERSONAL Gmail Google Drive** (NOT university email).
> Set sharing to "Anyone with the link can view".
> Test the link in incognito/private mode before submitting.

**Video Link**: [Paste your personal Gmail Google Drive link here]

**Video filename**: `[YourStudentID]_Assignment3_Synchronization.mp4`

**Verification**:
- [ ] Link is accessible (tested in incognito mode)
- [ ] Video is 3-5 minutes long
- [ ] Video shows code walkthrough and commits
- [ ] Video has clear audio
- [ ] Uploaded to PERSONAL Gmail (not @std.psau.edu.sa)

---

## Part 1: Development Log (1 mark)

Document your development process with **minimum 3 entries** showing progression:

### Entry 1 - [APr 29, 9 PM]
**What I implemented**: 
I started by checking the assignment files and reading the README.md instructions to understand what is required

**Challenges encountered**: 
at first I was not fully sure about the difference between the tasks especially the difference between locks and semaphores

**How I solved it**: 
I read the assignment requirements carefully and focused on the tasks one by one

**Testing approach**: 
no code testing yet I only reviewed the project files and requirements

**Time spent**: 
1h

---

### Entry 2 - [APr 30, 11 PM ]
**What I implemented**: 
I changed the studentID  in SchedulerSimulationSync.java to my actual student ID

**Challenges encountered**: 
no Challenges , i have donet before in ASS1

**How I solved it**: 
-------------------
**Testing approach**: 
I saved the file and checked that the student ID appears correctly in the code

**Time spent**: 
30 min
---

### Entry 3 - [MAY 1, 7 PM]
**What I implemented**: 
I reviewed the Java code and tried to understand how the scheduler works and the process class, run() method, and sharedresources class

**Challenges encountered**: 
The code was long and I needed time to understand where the things required of me

**How I solved it**: 
I followed the code step by step and identified the important things

**Testing approach**: 
I ran the program to see the output and understand how the code work
**Time spent**: 
2h
---

### Entry 4 - [MAY 2, 6pm]
**What I implemented**: 
I completed Task 1 and Task 2 I added locks to protect the shared counters and the execution log.
**Challenges encountered**: 
I was not sure at first where to place the lock code.
**How I solved it**: 
I added the lock inside SharedResources and used try-finally when updating shared data.
**Testing approach**: 
I saved, compiled, and ran the program to check that it works.
**Time spent**:
1.30h

---

### Entry 5 - [MAY 2, 8:30 PM]
**What I implemented**: 
I completed Task 3 by adding a Semaphore to control CPU access.

**Challenges encountered**: 
I had some confusion with acquire(), release(), and the try-catch-finally structure.

**How I solved it**: 
I used acquire() before execution and release() inside finally.

**Testing approach**: 
I compiled and ran the program and checked that the final output appears.

**Time spent**: 
About 2 hour
---

## Part 2: Technical Questions (1 mark)

### Question 1: Race Conditions
**Q**: Identify and explain TWO race conditions in the original code. For each:
- What shared resource is affected?
- Why is concurrent access a problem?
- What incorrect behavior could occur?

**Your Answer**:
A race condition happens when more than one thread uses the same shared data at the same time One example is contextSwitchCount++, because two threads may update it together and one update can be lost. Another example is executionLog.add(message), because executionLog is a shared ArrayList and it is not thread-safe. This could make the log incorrect or cause an error
---

### Question 2: Locks vs Semaphores
**Q**: Explain the difference between ReentrantLock and Semaphore. Where did you use each in your code and why?

**Your Answer**:
ReentrantLock is used to protect shared data so only one thread can change it at a time. I used it for the counters and executionLog, Semaphore is used to control access to a limited resource, I used Semaphore with one permit so only one process can use the CPU at a time
---

### Question 3: Deadlock Prevention
**Q**: What is deadlock? Explain TWO prevention techniques and what you did to prevent deadlocks in your code.

**Your Answer**:
Deadlock happens when threads keep waiting for each other and the program cannot continue To prevent this, I used try-finally so the lock and semaphore are always released I also kept the locked sections short and only locked the parts that update shared data
---

### Question 4: Lock Granularity Design Decision 
**Q**: For Task 1 (protecting the three counters), explain your lock design choice:
- Did you use ONE lock for all three counters (coarse-grained) OR separate locks for each counter (fine-grained)?
- Explain WHY you made this choice
- What are the trade-offs between the two approaches?
- Given that the three counters are independent, which approach provides better concurrency and why?

**Your Answer**:
I used one lock for the three counters. This is called coarse-grained locking. I chose it because it is simple and easy to understand. Fine-grained locking uses separate locks and gives better concurrency because the counters are independent.
However one lock still protects the counters correctly

---

## Part 3: Synchronization Analysis (1 mark)

### Critical Section #1: Counter Variables

**Which variables**: 

**Why they need protection**: 

**Synchronization mechanism used**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Justification**: 

---

### Critical Section #2: Execution Log

**What resource**: 

**Why it needs protection**: 

**Synchronization mechanism used**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Justification**: 

---

### Critical Section #3: CPU Semaphore

**Purpose of semaphore**: 

**Number of permits and why**: 

**Where implemented**: 

**Code snippet**:
```java
// Paste your implementation here
```

**Effect on program behavior**: 

---

## Part 4: Testing and Verification (2 marks)

### Test 1: Consistency Check
**What I tested**: Running program multiple times to verify consistent results

**Testing procedure**: 
```bash
# Commands used (run the program at least 5 times)
```

**Results**: 
(Show that running multiple times produces consistent, correct results)

**Why synchronization is necessary**: 
(Explain what race conditions COULD occur without synchronization, even if you didn't observe them. Explain which shared resources need protection and why.)

**Conclusion**: 

---

### Test 2: Exception Testing
**What I tested**: Checking for ConcurrentModificationException

**Testing procedure**: 

**Results**: 

**What this proves**: 

---

### Test 3: Correctness Verification
**What I tested**: Verifying correct final values (total burst time, context switches, etc.)

**Expected values**: 

**Actual values**: 

**Analysis**: 

---

### Test 4: Different Scenarios
**Scenario tested**: [e.g., different time quantum, more processes, etc.]

**Purpose**: 

**Results**: 

**What I learned**: 

---

## Part 5: Reflection and Learning

### What I learned about synchronization:

[6-8 sentences about key concepts, challenges, insights]

---

### Real-world applications:

Give TWO examples where synchronization is critical:

**Example 1**: 

**Example 2**: 

---

### How I would explain synchronization to others:

[Explain to someone who just finished Assignment 1 - use simple terms and analogies]

---

## Part 6: GitHub Repository Information

**Repository URL**: 

**Number of commits**: 

**Commit messages**: 
1. 
2. 
3. 
4. 

---

## Summary

**Total time spent on assignment**: 

**Key takeaways**: 
1. 
2. 
3. 

**Most challenging aspect**: 

**What I'm most proud of**: 

---

**End of Documentation**
