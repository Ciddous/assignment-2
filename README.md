# Project 2

## 1. Introduction
This project demonstrates process synchronization using semaphores in a shared memory environment. We create four processes, each incrementing a shared memory variable named `total` by a specific amount. The increments for each process are:
- Process 1: 100,000
- Process 2: 200,000
- Process 3: 300,000
- Process 4: 500,000

After each process completes its increments, it prints the current value of `total`. Once all child processes finish, the parent process prints each child's ID in the order they exited, releases shared memory and semaphore resources, and prints "End of Program."

## 2. Expected Output
The output of this project should resemble the following format:

```plaintext
From Process 1: counter = [value].
From Process 2: counter = [value].
From Process 3: counter = [value].
From Process 4: counter = 1100000
Child with ID: 2412 has just exited.
Child with ID: 2411 has just exited.
Child with ID: 2413 has just exited.
Child with ID: 2414 has just exited.
End of Program.

## 3. Project Implementation
