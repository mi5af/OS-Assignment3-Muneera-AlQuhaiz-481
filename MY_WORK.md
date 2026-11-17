# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Muneera Fahd AlQuhaiz] |
| **Student ID** | [446051584] |
| **University Email** | [446051584]@std.psau.edu.sa |
| **GitHub Username** | [mi5af] |
| **Repository Link** | [https://github.com/mi5af/OS-Assignment3-Muneera-AlQuhaiz-481] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 8, 2026, 5:00 PM]
**What I did**: forked the repository and rename it to my name, verified public visibility

**Details**:
- forked makopt/OS-Assignment3-Starter-481 and renamed the fork to OS-Assignment3-Muneera-AlQuhaiz-481
- verified the repository visibility is public

**Challenges**:none

**Solution**:-

**Time spent**: 10 minutes

---

### Entry 2 - [November 13, 2026, 9:30 PM]
**What I did**: set my student ID in SchedulerSimulationSync.java, Implemented feature 1 by protecting the shared ready queue with a reentranlock 

**Details**:
- updated the studentID variable on line 304 with my actual ID
- Imported java.util.concurrent.locks.Reentrant.Lock in schedulerSimulationSync.java
- Declared a Reentrantlock queueLock inside The ReadyQueue class
- Protected all methods accessing or modifying the shared list and map (add,poll, processOf and snapshot) using lock() and a try/finally block to ensure locks are always released safely
- committed and pushed the change with a clear commit message
**Challenges**: ensuring that the return statements inside poll() and other methods do not bypass the lock releas

**Solution**: placed the try block after lock.lock() and put unlock() inside the finally block to guarantee it excuses regardless of returns or exceptions

**Time spent**: 45 minutes

---

### Entry 3 - [November 15, 2026, 8:30 PM]
**What I did**: Implemented feature 2 by protecting the shared statistic counter with a ReentrantLock

**Details**:
- Declared a ReentrantLook statsLook inside the SharedStates class 
- Protected all three updater methods (incrementContextSwitch, incrementCompletedProcess, addServiceTime) and getter methods (getCompletedProcessCount, getContextSwitchCount, getTotalServiceTime) using lock() and try/finally blocks
- Chose a single lock granularity for all statistics since updates are independent counters, simplifying management and preventing race condition during read and write
- committed and pushed the change with a clear commit message

**Challenges**:
 Ensuring that both readers and writers are fully protected to avoid reading stale or inconsistent counter value during verification

**Solution**: Applied the lock symmetrically across all getters and updaters in sharedStats

**Time spent**: 40 minutes

---

### Entry 4 - [November 16, 2026, 11:02 PM]
**What I did**:Implemented Feature 3 by replacing busy waiting with a counting semaphore and handled clean shutdown.

**Details**:
- Declared a Semaphore semaphore = new Semaphore(0) inside ReadyQueue.
- Called semaphore.release() inside add() whenever a process is added to the queue and added acquireProcess() inside CpuWorker to block threads safely instead of spinning in a busy waiting loop.
- Removed the Thread.sleep(20) polling loop and ensured busyWaitPolls remains at 0.
- Implemented clean shutdown by calling readyQueue.releaseAll(SharedStats.totalCPUs) when the last process completes waking up any blocked CPU threads so they terminate properly without hanging.
- Committed and pushed the changes with a clear commit message.

**Challenges**:Ensuring that CPUs blocked on acquire() do not hang indefinitely after all processes finish execution.

**Solution**:Added a check and a broadcast release (releaseAll) when the completed process count reaches the total process count.

**Time spent**: 30 minutes

---

### Entry 5 - [Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [3 hours]

**Most challenging part**:Replacing busy waiting with a counting semaphore and ensuring CPU threads terminated cleanly without hanging.

**Most interesting learning**:How locks and semaphores protect shared data and make multi-threading safe and efficient.

**What I would do differently next time**:tart a bit earlier and commit more frequently across different days.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I learned that synchronization is very important when multiple threads run at the same time. Without protection, threads can try to access the same shared data, which causes race conditions and wrong results. Using ReentrantLock helps us achieve mutual exclusion so only one thread enters the critical section at a time. I also learned how a counting semaphore can control access and help threads wait safely instead of wasting CPU time. It was surprising to see how easily a small timing window can break the whole program when updates overlap.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part of this assignment was implementing Feature 3 and making sure the CPU threads stopped correctly at the end. At first, when I used the counting semaphore, the CPU threads kept waiting forever and the program did not finish. I had to understand how to use releaseAll() when the last process finished so all waiting CPUs could wake up and terminate safely. This helped me understand blocking and unblocking states in multi-threading.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[To overcome my challenges, I read the instructions and the README file very carefully. When my code did not work or stayed stuck, I added print statements to see where the threads were waiting. I also tested my code after each small change to make sure it passed the verification checks. When I faced errors with the semaphore, I reviewed how acquire() and release() work in Java. Asking for step-by-step guidance also helped me understand each part clearly.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization concepts are used in many real-world applications where multiple users or processes share resources. For example, in online banking, multiple users might try to withdraw money from the same account at the same time, so locks are needed to prevent double spending. Another example is ticket booking systems, where a seat must be locked so two people cannot book the same seat simultaneously. Print queues also use queues and locks to handle print jobs from different computers in the correct order.]

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[When running the original starter code, the verification failed because of a race condition in the unprotected code. A lost update happens when two CPU threads read the same counter value, and one thread writes its updated value before the other, overwriting and losing an increment. This happens on real machines even without RaceWindow because the CPU scheduler can pause a thread at any nanosecond during read-modify-write. It is hard to detect because it happens randomly depending on thread timing.]

Verification block of the **original starter**:
```
[Context switches (quanta executed)     expected 18       observed 15       ✘ MISMATCH
  Completed processes                    expected 12       observed 10       ✘ MISMATCH
  Total service time (ms)                expected 24000    observed 19000    ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 4821     ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.

⛔️ WATCHDOG: the simulation did not finish (45 s). A process was lost, or a CPU is blocked forever...]
```

Verification block of **my final version**:
```
[Context switches (quanta executed)     expected 18       observed 18       ✔
  Completed processes                    expected 12       observed 12       ✔
  Total service time (ms)                expected 24000    observed 24000    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.]
```

**Explanation of the timeline:**
[1. Read: CPU-1 reads the shared contextSwitchCount and sees the value 5.
 2. Preemption / Pause: Right after reading, CPU-1 is paused (or preempted). At the exact same moment, CPU-2 reads the same shared contextSwitchCount and also sees 5.
 3. Write (CPU-1): CPU-1 adds 1 to its value (5 + 1 = 6) and writes 6 back to contextSwitchCount.
 4. Write (CPU-2): CPU-2 also adds 1 to its value (5 + 1 = 6) and writes 6 back to contextSwitchCount.
 5. The Bug: Even though two processes started execution, the counter only increased from 5 to 6 instead of 7. One increment was completely los]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[ We protected critical sections like ReadyQueue.poll(), ReadyQueue.add(), and the statistics updaters using ReentrantLock. For statistics, we used a single lock (statsLock) because the counters are independent and simple, which avoids deadlocks and keeps the code clean. The ready queue uses a different lock (queueLock) to manage thread safety for the list and map separately. A default ReentrantLock is non-fair, meaning threads get the lock in an arbitrary order rather than strict FIFO, which can cause thread starvation.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[In the starter code, CPUs used a busy-waiting loop with Thread.sleep(20) to constantly check an empty queue, which wasted CPU cycles and resulted in a high number of busy-waiting polls. Our counting semaphore represents the number of available processes in the ready queue, starting with an initial value of 0. After the initial processes are added in main(), the semaphore is released accordingly. The last CPU calls release(totalCPUs) at the end to wake up all waiting threads so they can terminate cleanly; otherwise, they would block forever.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[This setup is similar to the Producer-Consumer problem, where main() and uncompleted processes act as producers adding to the queue, and CPU workers act as consumers taking processes to execute.]

**Semaphores for a bounded queue (name and initial value)**:
[For a bounded queue of capacity K, the three semaphores needed would be empty (initialized to K), full (initialized to 0), and mutex (initialized to 1).]

**Deadlock scenario and prevention**:
[ A deadlock can happen if a thread acquires the mutex lock before waiting on a full/empty semaphore when the buffer is full, preventing the consumer from ever reaching the mutex to take an item. To prevent this, we must break the hold-and-wait condition by acquiring semaphores before entering the critical section with the mutex.]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
