#################################
Task Structure and Task Creation
#################################
Tasks in the AMALTHEA software model are the abstract class Process generalizes Tasks and ISR, and provides the common attributes like the activation that is at runtime level represented by a Stimulus. A Task contains calls either to other Tass (via inter process activation) or Runnables. These types of calls are included in the callGraph attribute. 

Task structure and creation for RMS
-----------------------------------
Rate Monotonic Scheduler is based on the Project RTFParallella_. More details are available in the corresponding documentation.

Task structure and creation for FreeRTOS
----------------------------------------

.. code-block:: c

	xTaskCreate( v<TaskName>, "<TaskName>", 
		configMINIMAL_STACK_SIZE, 
		NULL1, 
		<TaskPriority>, 
		NULL2 );

Argument

*	TaskName - pointer to task Handler function
*	"<TaskName>" - Name of the task, used during debugging.
*	configMINIMAL_STACK_SIZE - Stack size allocated for the specific task.
* 	Null1 - Task parameter passed when task is called
* 	<TaskPriority> - Priority of task based on which scheduling happens.
* 	NULL2 - Used to pass a handle to the created task out of the xTaskCreate() function. xCreatedTask is optional and set to NULL in CdGen.

.. code-block:: c

	void v<TaskName>( )
	{
		portTickType xLastWakeTime;
		for( ;; )
		{
			//cIN operation
			cIN_<TaskName>();

			
			//Runnable call
			<Runnable1 Name>();
			<Runnable2 Name>();
			.
			.
			<Runnable'n' Name>();

			updateDebugFlag(<debugMessage>);
			sleepTimerMs(<TaskExecutionTime> , <TaskID>);
			<taskSpecificCounter>++;
			traceTaskPasses(<TaskID>, <taskSpecificCounter>);
			traceRunningTask(<TaskID>);

			//cOUT operation
			cOUT_<TaskName>();

			taskYIELD();
			vTaskDelayUntil(&xLastWakeTime, <TaskPeriod>);

		}	
	}

In FreeRTOS Task handler are running in an infinite loop however the vTaskDelayUntil specifies absolute time at which the task wishes to unblock so that other tasks are executed. In this tool the task structures are defined in such a way that inherits implicit communication over other communication semantics. As per Implicit communication semmantics, Cin operation happens at the begining of the task and Cout operation happens at the end of execution of the task. In a realtime situation runnables are executed in the exucution time whereas inorder to hold the core we use the sleepTimerMs in addition to the Runnable calls as the holding the core in the Runnable level prescision is possible but at times the time taken per runnable falls less than milliseconds.


Task structure and creation for POSIX
-----------------------------------------

.. code-block:: c

	pthread_create (&thread[<Task2ThreadMapID>], &attr, v<TaskName>, (void *)arg);

Argument 

*	thread -  returns the thread id.
*	attr - Set to NULL if default thread attributes are used.
*	v<TaskName> - Task handler.
*	*arg - pointer to argument of function. 

.. code-block:: c

	void v<TaskName>( )
	{
		for( ;; )
		{
			//cIN operation
			cIN_<TaskName>();
			
			//Runnable call
			<Runnable1 Name>();
			<Runnable2 Name>();
			.
			.
			<Runnable'n' Name>();

			updateDebugFlag(<debugMessage>);
			sleepTimerMs(<TaskExecutionTime> , <TaskID>);
			<taskSpecificCounter>++;
			traceTaskPasses(<TaskID>, <taskSpecificCounter>);
			traceRunningTask(<TaskID>);

			//cOUT operation
			cOUT_<TaskName>();

			pthread_exit((void*) t);
		}	
	}

Like in FreeRTOS, Task handler have infinite loop and here pthread_exit does the role of vTaskDelayUntil to unblock the core. In POSIX too, Implicit communication is implemented.  

Note
-----
LET(Logical Execution Time) is another semantics which is used often in the research area as this is very easy in analysis of task. In both POSIX and FreeRTOS, the cOUT operation is performed after the vTaskDelayUntil and pthread_exit in FreeRTOS and POSIX respectively. In RMS both implicit and LET frame works are available it is altered just by selecting appropriate framework for execution.

.. _RTFParallella : https://rtfparallella.readthedocs.io/en/latest/index.html