# Data
Data retrieved from the various entities are registered at startup as *emiters* with a data value reference (DVR) that is maintained as a property of the ``Controller`` object called ``MAP DVR``.  When data is broadcast by the various emitters, then the DVR will capture these broadcasts and make them accessible to the various processes that require them.

## The ``Data`` Object
  
All emitters broadcast an object with a common parent.  That parent is called ``Data``.  This object has the following properties:

* ``Time`` - a timestamp representing when the data was collected.

Structure of MAP.  

How it is populated

