# MAX Tasks
Most analog and digital communication is performed directly through DAQmx, the native DAQ driver for communication with National Instruments devices.  All communication with NI devices is configured through Tasks in MAX.  To view available tasks or to create new ones, the user must

* navigate to the remote system (**exscalabar**)
* select *Data Neighborhood* to expand this folder 
* select *NI-DAQmx Tasks* to view the currently configured tasks

![MAX Task list](daqmx tasks.png)
The user may directly interact with the hardware via the preconfigured tasks by selecting double-clicking on the task and clicking the run button (see below).  The user will have the same options as with running a VI - run once or run continuously.  How the user desires to interact with the task will determine how they use this button.  For some operations, such as digital outputs, they are defined to be **1 Sample (on demand)** as in the image below.  In this case, the user will likely want to run continuously, so that they may toggle the switch without having to hit the run button every time they are testing.

![Running a DAQmx task](running daqmx task.png)