# Command Pattern
The command pattern is [a common software pattern](http://www.oodesign.com/command-pattern.html) often found in scripted programming languages.  The command pattern consists of a root object which contains a single common method.  This method in other implementations might be called ``Execute``.  An invoking module will the instantiate and have a concrete method for handling the command. 

The command pattern in LabVIEW is similar to the queued message handler.  In the queued message handler, one might find 

## Implementation
The implementation of the ``Command`` object can be located in the EXSCALABAR LabVIEW project under the folder ``Support``.  The class is abstract in the sense that it is not intended to be called without a concrete implementation.  The ``Command`` has the following properties and methods:

### The ``response`` property
The response property is a queue containing a boolean value.  This property is utilized in the ``Send Command and Wait for Response`` method to determine whether the command was successfully implemented.

### The ``Handle Command`` method
This method is the primary method of the ``Command`` class.  This method *must* be overridden (a requirment)  

