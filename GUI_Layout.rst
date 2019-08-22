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
* Co-operative Scheduling: Once started, a task within a co-operative scheduling system will continue to run until it relinquishes control. The call will enable the scheduler which will then check the states of all the tasks within the system and schedule the highest priority ready task.

* Pre-emptive scheduling retains many of the features described above e.g. tasks, task states/queues/ priorities, etc. However, there is one very important difference. In a pre-emptive model, tasks can be forcibly suspended. This is instigated by an interrupt on the CPU. These interrupts may be from external systems as above or possibly from the system clock. The difference here is that the scheduler is invoked following one of these system events. If a sensor detects an alarm condition, the input circuitry can generate an interrupt to the CPU.

Source selection
-------------------------
Despite the generation, there are also other scheduler specific files which are either licensed under different open source or available ready in other projects. These folder are available in 


Model selection
-------------------------
Despite of few models available within the tool we also extend our support for the other models and inorder to be more dynamic we adapted a open selection for model too. Deviating from our initial proposal of a drop down option. 

*Models should be of version 0.9.5 which can be migrated with a inbuilt tool which comes with APP4MC.
