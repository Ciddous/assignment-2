# Project 2

# 1. Introduction
This project demonstrates process synchronization using semaphores in a shared memory environment. We create four processes, each incrementing a shared memory variable named `total` by a specific amount. The increments for each process are:
- Process 1: 100,000
- Process 2: 200,000
- Process 3: 300,000
- Process 4: 500,000

After each process completes its increments, it prints the current value of `total`. Once all child processes finish, the parent process prints each child's ID in the order they exited, releases shared memory and semaphore resources, and prints "End of Program."

# 2. Expected Output
The output of this project should resemble the following format:

From Process 1: counter = [value].
From Process 2: counter = [value].
From Process 3: counter = [value].
From Process 4: counter = 1100000
Child with ID: 2412 has just exited.
Child with ID: 2411 has just exited.
Child with ID: 2413 has just exited.
Child with ID: 2414 has just exited.
End of Program.

# 3. Project Implementation
The project is implemented by the following steps

1. Define Shared Memory and Semaphores
   * Use SHMKEY to create a shared memory segment for the variable total
   * Define a structure to hold total which all processes can access

2. Initialize the Semaphores
   * A signle semaphore has control to the critical section
   * POP and VOP functions contol entry and exit for the critical section
  
3. Define Increment Functions
   * Define four separate process functions which each increment total by the target process value
  
4. Create Shared Memory and Attach to Address Space
   * Use shmget to create shared memory and smhmat to attach it to each process address space
  
5. Fork Processes
   * fork() is used to create four child processes each calling it's respective function to increment total
  
6. Wait and Print the Process IDs
   * The parent process waits for each child process to finish and then stores the ID and prints it out
  
7. Release the Resources
   * Shared memory and semaphores are detached and deallocated

# 4. Testing the Project
To ensure the project is working we need to run it multiple times to verify that
* Correct formatting and output
* Final counter value at 1,100,000
* Each process ID is printed as it finishes
* Parent process runs last

If all these things run as they are supposed to, then the project is fully functional. Throught multiple test below we can see that this is the case

![project2](https://github.com/user-attachments/assets/2bc86626-c16b-4573-9180-9d6a6cb5fe60)

# 5. Conclusion
The project effectively demonstrates process synchronization using semaphores, it also highlights the user of forking, shared memory, and semaphore mechanisms in programming.
