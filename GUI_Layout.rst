##############################
GUI Layout for CDGen
##############################
In order to build Graphical User Interface(GUI) for the CDGen application we used Java Swing. 

Scheduler Option
-----------------
In order to allocate a specific task at a specific time a scheduler becomes inevitable in this situtaiton, CDGen offers 3 different scheduling options such as FreeRTOS, POSIX and Rate Monotonic Schedulers. 

* FreeRTOS : FreeRTOS is very strict quality managed, not just in software coding standards and look and feel, but also in implementation.The efficient software timer implementation that does not use any CPU time unless a timer actually needs servicing. Software timers do not contain variables that need to be counted down to zero.

* POSIX is a family of standards, specified by the IEEE, to clarify and make uniform the application programming interfaces (and ancillary issues, such as command line shell utilities) provided by Unix-y operating systems. 

* Rate Monotonic scheduling algorithm is a simple rule that assigns priorities to different tasks according to their time period. That is a task with the smallest time period will have the highest priority and a task with the longest time period will have the lowest priority for execution. 

Task Preemptive Option
-------------------------

Hardware Selection
-------------------------

Model selection
-------------------------