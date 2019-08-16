##############################
Scheduler for CDGen
##############################
Schedulers are inevitable for a code generator which envisage to execute the tasks on any hardware. 
In CDGen offers three different scheduling approach such as. 

* FreeRTOS scheduler
* POSIX/Pthread scheduler
* Rate monotonic scheduler

Scheduler for FreeRTOS
-------------------------
FreeRTOS_ is very strict quality managed, not just in software coding standards and look and feel, but also in implementation. FreeRTOS never performs a non-deterministic operation. The efficient software timer implementation that does not use any CPU time unless a timer actually needs servicing. Software timers do not contain variables that need to be counted down to zero. Direct to task notifications allow fast task signaling, with practically no RAM overhead, and can be used in the majority of inter-task and interrupt to task signalling scenarios. The FreeRTOS queue usage model manages to combine simplicity with flexibility (in tiny code size) - attributes that are normally mutually exclusive. FreeRTOS queues are base primitives on top of which other communications and synchronization primitives are built. The code re-use obtained dramatically reduced overall code size, which in turn assists testing and helps ensure robustness.

Scheduler for POSIX
-------------------------
POSIX_ is a family of standards, specified by the IEEE, to clarify and make uniform the application programming interfaces (and ancillary issues, such as command line shell utilities) provided by Unix-y operating systems. When you write your programs to rely on POSIX standards, you can be pretty sure to be able to port them easily among a large family of Unix derivatives (including Linux, but not limited to it!); if and when you use some Linux API that's not standardized as part of POSIX, you will have a harder time if and when you want to port that program or library to other Unix-y systems (e.g., MacOSX) in the future.

Scheduler for RMS
-------------------------
The Rate Monotonic scheduling(RMS_) algorithm is a simple rule that assigns priorities to different tasks according to their time period. That is a task with the smallest time period will have the highest priority and a task with the longest time period will have the lowest priority for execution. As the time period of a task does not change so not its priority changes over time, therefore Rate monotonic is fixed priority algorithm. The priorities are decided before the start of execution and they do not change over time.

.. _FreeRTOS : https://www.freertos.org/index.html
.. _POSIX : http://www.robelle.com/smugbook/posix.html
.. _RMS : https://www.embedded.com/electronics-blogs/beginner-s-corner/4023927/Introduction-to-Rate-Monotonic-Scheduling