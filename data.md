# Data
Data retrieved from the various entities are registered at startup as *emiters* with a data value reference (DVR) that is maintained as a property of the ``Controller`` object called ``MAP DVR``.  When data is broadcast by the various emitters, then the DVR will capture these broadcasts and make them accessible to the various processes that require them.

## The ``Data`` Object
  
All emitters broadcast an object with a common parent.  That parent is called ``Data``.  The ``Data`` object may be found in the library ``Base Data Class`` which contains a lot of basic data object as well as the root ``Data`` object.  This object has the following properties:

* ``measTime`` - a timestamp representing when the data was collected.
* ``Data ID`` - unique string to represent the object.
* ``write time`` - boolean indicating whether the time is to be sent with any data string.

The ``Data`` object also contains some methods that are intended to be implemented by the child.  There are two serialization methods intended to ease sharing of data throughout the system:

* ``Serialize - JSON`` - generates a JSON string that may be used to be broadcast to the client in response to http requests. 
* ``Serialize - Text`` - generates a string array that may be used to generate a string for writing to an ASCII file.

A companion abstract method to the method ``Serialize to Text`` is the method

* ``Generate Unique Header``

Structure of MAP.  

How it is populated

