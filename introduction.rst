##############################
Introduction to CDGen
##############################

Overview
-------------------------

The CDGen is an application using Eclipse APP4MC for model to text conversion using the System Model to enhance cost-effectiveness and decreasing the chance of errors when compared to manual coding. The main outputs of this application are C and Header files which hold all the details of the model for the compilation and building process(generating executables for running on the Processor). Based on the  Eclipse Modeling Framework, its capabilities not only include hardware and software modeling but in addition, tools for visualization and processing. The application will be added to the set of tools of Eclipse APP4MC.

.. image:: cdgen_logo.png
	:align: center


The project deals with creating an application which is capable of generating the code from the System Model. The System Model contains the information required to simulate, analyze and optimize performance. It contains extensive information about software, hardware, timing behavior, and constraints for the system under development.  This application is planned in a systematic approach with a lot of flexibility. CDGen enhances a user-friendly experience. Below is the list of action items in the plan.

Requirement
-------------------------
*	APP4MC_	V 0.9.5 
*	JAVA_ 10 SE
*	Scheduler_ SourceCode	

Configuration
-------------------------
There are 6 main scheduling configuration available in this tool:

*	FreeRTOS Preemptive Scheduler
*	FreeRTOS Cooperative Scheduler
*	POSIX Preemptive Scheduler
*	POSIX Cooperative Scheduler
*	Rate Monotonic Preemptive Scheduler
* 	Rate Monotonic Cooperative Scheduler


Deliverables
-------------------------
*	SourceCode_ for the CDGen
*	Documentation

.. _SourceCode : https://github.com/rprasathg/cdgen
.. _APP4MC : https://www.eclipse.org/app4mc/downloads/
.. _JAVA : https://www.oracle.com/technetwork/java/javase/downloads/java-archive-javase10-4425482.html
.. _Scheduler : https://git.eclipse.org/c/app4mc/org.eclipse.app4mc.examples.git/commit/?id=69a0a24f120bb0d79cbd688081ca697368e252f7







