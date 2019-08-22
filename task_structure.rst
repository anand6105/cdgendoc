##############################
Task Structure
##############################
Tasks in the AMALTHEA software model are the abstract class Process generalizes Tasks and provides the common attributes like the activation that is at runtime level represented by a Stimulus. A Task contains calls either to other Tasks (via inter process activation) or Runnables. These types of calls are included in the callGraph attribute. 

Task structure for POSIX
-------------------------

.. code-block:: cpp


Task structure for RMS
-------------------------

.. code-block:: cpp

Task structure for FreeRTOS
----------------------------

.. code-block:: cpp
