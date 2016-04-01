# Operational Overview
Below is an [activity diagram](https://www.ibm.com/developerworks/rational/library/2802.html) demonstrating the launch sequence of the system.  When running in the LabVIEW environment for debugging purposes, the user will start the program by running ``Launcher`` found in the ``Main Launch`` folder (the only file in the folder) in the project.  The ``Launcher`` VI has one thing that it does - it simply launches the ``Controller`` actor object.

As with every ``Actor`` object, the ``Controller`` has a set of actions that it will perform.  Each ``Actor`` in the system will run the ``Actor::Pre Launch Init`` when launched.  In the EXSCALABAR DAQ, this is where all configuration will occur.  If an error is thrown here, then the 

![](Launch Activity.jpg)

