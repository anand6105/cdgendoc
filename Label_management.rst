##############################
Label Management for CDGen
##############################

Label Management is performed based on the Software Model. This application formulates a table with <Label> <Task> <ProcessingUnit>. Based on this table we classify the labels into three main category. This classification helps in optimizing memory usage. In this Software model labels are mapped to the their corresponding runnables which are inturn, mapped to their respective task(s). The processing unit corresponding to the label in the table is from the corresponding task.

* Shared label - Shared among cores

* Core label - Shared among tasks

* Task label - Task specific labels

 
Label management for shared labels
----------------------------------
Shared labels are labels which are common to many tasks which are mapped to different cores of the same hardware. These labels are further classified into their types and counted. Read and write are performed from Copy In function and Copy out function respectively. Here we intialise those memory and function definition and declaration,

Below are function template for read and write

.. code-block:: cpp

   void shared_label_<labelSize>_write(int label_indx,<labelDataType> payload)

   <labelDataType> shared_label_<labelSize>_read(int label_indx)

In read operation a particular memory index is targeted and read whereas in the write operation the same memory from which it is read is written back with payload parameter holding the value to be written, It is achieved by indexing the shared labels. 

Label management for core labels
---------------------------------
Core labels are shared among tasks which are mapped to the same core. As the file structure are devised in such a way those are core specific. In adittion to the read and the write operations which are performed from Copy In and Copy out function respectively in the label file it is also intialised outside as a generic one.

Label management for Task labels
---------------------------------
Task labels are labels which are specific to a certain tasks. These labels are defined as local variables within the scope of the task.

*Inorder to encounter each cOUT operation, Incrementation of the variable is implemented just before the write operation.



