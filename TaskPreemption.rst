##############################
Task preemption
##############################
Co-operative Scheduling
-------------------------
Once started, a task within a co-operative scheduling system will continue to run until it relinquishes control. The call will enable the scheduler which will then check the states of all the tasks within the system and schedule the highest priority ready task.

.. code-block:: c

	#define configUSE_PREEMPTION		0

Pre-emptive Scheduling
-------------------------
Pre-emptive scheduling retains many of the features described above e.g. tasks, task states/queues/ priorities, etc. However, there is one very important difference. In a pre-emptive model, tasks can be forcibly suspended. This is instigated by an interrupt on the CPU.
These interrupts may be from external systems as above or possibly from the system clock. The difference here is that the scheduler is invoked following one of these system events. If a sensor detects an alarm condition, the input circuitry can generate an interrupt to the CPU.

.. code-block:: c

	#define configUSE_PREEMPTION		1