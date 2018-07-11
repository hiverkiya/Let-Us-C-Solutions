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
    
        // Name of program mainreturn.cpp
        #include <iostream>
        using namespace std;
 
        int main(int argc, char** argv)
        {
    cout << "You have entered " << argc
         << " arguments:" << "\n";
 
    for (int i = 0; i < argc; ++i)
        cout << argv[i] << "\n";
 
    return 0;
        }
    (d) getppid() : returns the process ID of the parent of the calling process. If the calling process was created by the fork() function and the parent process still exists at the time of the getppid function call, this function returns the process ID of the parent process. Otherwise, this function returns a value of 1 which is the process id for init process.getpid() : returns the process ID of the calling process. This is often used by routines that generate unique temporary filenames.
    (e) Can be done just by litte logical analysis.
    (f) To prevent of zombie processes you need to tell the parent to wait for the child, until the child's terminates the process.
      You need to use the waitpid() function that is included in the library 'sys/wait.h'
    (g)Signal is a notification, a message sent by either operating system or some application to your program (or one of its threads).

        Each signal identified by a number, from 1 to 31. Signals don’t carry any argument and their names are mostly self explanatory.         For instance SIGKILL or signal number 9 tells the program that someone tries to kill it.
    (h)Signals are used for a wide variety of purposes in Unix programming, and we've already used them in smaller contexts.a program       that handles a signal, either by ignoring it or taking some action when the signal is delivered is described as signal handler.For      rest of answer prefer [This Site](https://en.wikipedia.org/wiki/C_signal_handling)
    (i)No, you can't catch the uncatchable signals as it is always caught by the default handler implemented by the kernel. SIGKILL always terminates the process. Even if the process attempts to handle the SIGKILL signal by registering a handler for it, still the control would always land in the default SIGKILL handler which would terminate the program. This is what happens when you try to shut down your system. First, the system sends a SIGTERM signal to all the processes and waits for a while giving those processes a grace period. If it still doesn't stop even after the grace period, the system forcibly terminates all the process by using SIGKILL signal.
    (j)#include<stdio.h>
        #include<signal.h>
    #include<unistd.h>

    void sig_handler(int signo)
    {
     if (signo == SIGINT)
    printf("received SIGINT\n");
    }

    int main(void)
    {
     if (signal(SIGINT, sig_handler) == SIG_ERR)
     printf("\ncan't catch SIGINT\n");
     // A long long wait so that we can easily issue a signal to this process
     while(1) 
    sleep(1);
     return 0;
    }


    (k) 
    
        /* A C program that does not terminate when Ctrl+C is pressed */
        #include <stdio.h>
        #include <signal.h>
 
        /* Signal Handler for SIGINT */
        void sigintHandler(int sig_num)
        {
    /* Reset handler to catch SIGINT next time.
       Refer http://en.cppreference.com/w/c/program/signal */
    signal(SIGINT, sigintHandler);
    printf("\n Cannot be terminated using Ctrl+C \n");
    fflush(stdout);
        }
 
        int main ()
    {
    /* Set the SIGINT (Ctrl-C) signal handler to sigintHandler 
       Refer http://en.cppreference.com/w/c/program/signal */
    signal(SIGINT, sigintHandler);
 
    /* Infinite loop */
    while(1)
    {        
    }
    return 0;
        }
Please Refer [GeeksforGeeks](https://www.geeksforgeeks.org/write-a-c-program-that-doesnt-terminate-when-ctrlc-is-pressed/) and [Quora](https://www.quora.com/What-is-the-difference-between-the-SIGINT-and-SIGTERM-signals-in-Linux-What%E2%80%99s-the-difference-between-the-SIGKILL-and-SIGSTOP-signals) for much brief explanations.
