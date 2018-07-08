# [Chapter 23: C Under Linux] Solutions

## [A]
    
    (a) True
    (b) False (There could be some variations in various distributions)
    (c) False (Generally, the scheduling unit on Linux is referred to as a KSE, a "kernel scheduling entity". On modern Linux systems, each thread is a KSE.)
    (d) False
    (e) False
    (f) True
    (g) True
    (h) False
    (i) True
    (j) False
    (k) False
    (l) False
    (m) False
    (n) False
    (o) False
    (p) True
    (q) True
    (r) True
    (s) True
    
## [B]

    (a) 2^4 i.e, 16 Total Processes.
    
    (b) A process which has finished the execution but still has entry in the process table to report to its parent process is known as a zombie process.A process whose parent process no more exists i.e. either finished or terminated without waiting for its child process to terminate is called an orphan process.
    (c)
    (d) getppid() : returns the process ID of the parent of the calling process. If the calling process was created by the fork() function and the parent process still exists at the time of the getppid function call, this function returns the process ID of the parent process. Otherwise, this function returns a value of 1 which is the process id for init process.getpid() : returns the process ID of the calling process. This is often used by routines that generate unique temporary filenames.
    (e) 
    (f) To prevent of zombie processes you need to tell the parent to wait for the child, until the child's terminates the process.
      You need to use the waitpid() function that is included in the library 'sys/wait.h'
    (g)
    (h)
    (i)
    (j)
    (k)
