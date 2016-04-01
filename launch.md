# Operational Overview
Below is an [activity diagram](https://www.ibm.com/developerworks/rational/library/2802.html) demonstrating the launch sequence of the system.  When running in the LabVIEW environment for debugging purposes, the user will start the program by running ``Launcher`` found in the ``Main Launch`` folder (the only file in the folder) in the project.  The ``Launcher`` VI has one thing that it does - it simply launches the ``Controller`` actor object.

As with every ``Actor`` object, the ``Controller`` has a set of actions that it will perform.  Each ``Actor`` in the system will run the ``Actor::Pre Launch Init`` when launched.  In the EXSCALABAR DAQ, this is where all configuration will occur.  If an error is thrown here, then the ``Actor`` *should* shutdown without sending a last ack to the actor in which it is nested.  In the case of the ``Controller``, this means that a fail at launch will result in a failure to launch.  The error is fatal because the ``Controller`` is the hub of all activity - most messages will pass through this ``Actor`` at some point.

![](Launch Activity.jpg)


If the launch is successful, the ``Actor::Actor Core`` process will kick off and continue until a stop message is sent.  A stop message may be sent by the user via a command to halt the system *or* if an error is thrown and not handled properly in the core itself.

