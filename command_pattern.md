# Command Pattern
The command pattern is [a common software pattern](http://www.oodesign.com/command-pattern.html) often found in scripted programming languages.  The command pattern consists of a root object which contains a single common method.  This method in other implementations might be called ``Execute``.  An invoking module will the instantiate and have a concrete method for handling the command. 

The command pattern in LabVIEW is similar to the queued message handler.  In the queued message handler, one might find 

## Implementation
The implementation of the ``Command`` object can be located in the EXSCALABAR LabVIEW project under the folder ``Support``.  The class is abstract in the sense that it is not intended to be called without a concrete implementation.  The ``Command`` has the following properties and methods:

### The ``response`` property
The response property is a queue containing a boolean value.  This property is utilized in the ``Send Command and Wait for Response`` method to determine whether the command was successfully implemented.

### The ``Handle Command`` method
This method is the primary method of the ``Command`` class.  This method *must* be overridden (a requirement).  This is the method in which the code to be executed will be contained.  This method is **protected** and called by the **public** function ``Execute``.

### The ``Execute`` method
This is the outward facing method that will be called by the invoker and is therefore **public**. In this method, the ``Handle Command`` method is called followed by the ``Command Reply`` method which will be used to indicate that the command was successful to the sender.  This method is static and reentrant.

### The ``Send Command and Wait for Response`` method
This method can be called by the sender of the command to 1) send the command to be handled and 2) wait for a response to determine whether the comand was successful.  This method:

1. Sets up the response queue (calls ``Obtain Queue`` and stuffs the reference into the ``response`` property).
2. Sends the command via the command queue.
3. Waits for a response as to whether the command was correctly executed
4. Destroys the response queue via ``Release Queue``. 

This method is **public**, static and reentrant.

### The ``Command Reply`` method
This method is used simply to send a reply to the sender of the command to indicate the success of the command.  If the ``response`` queue is no good, this method does nothing.  This method is **private**, static and reentrant.