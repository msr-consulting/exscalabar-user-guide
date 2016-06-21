# Current Value Table
## Object
Control values are synchronized between the client and server side via a current value table.  The current Value table functionality is wrapped in an object called ``CVT``.  ``CVT`` is contained within a session so that it may be shared across the multiple structures that require access to the current value table.  The ``CVT Session`` is a property of the superclass ``Ex Nested``.  

The CVT structure will look something like this:

```
+-- Group_1
| +-- tag_0: val
| +-- tag_1: val
...
+-- Group_2
| +-- tag_0: val
| +-- Nested_Group_1
| | +-- tag_0: val
| | +-- tag_1: val
| +-- tag_1:val
...
```

The ``CVT`` object contains the following public methods:

### ``initialize Session Data``
This is called when the first ``CVT`` session is created.  This function simply initializes the only property of the class ``CVT`` with a new variant.

### ``Insert Data``
This is one of the two primary public functions.  Aside from the input ``CVT Session In`` and ``Error In``, this method contains three inputs:

* ``Group``: This is a string which will identify the group that this data belongs to.  
* ``tag``: This is a string and is the name of the data that will be associated with the value of interest.
* ``Data``: This is a variant is the actual data that we wish to store.

This function takes these inputs and calls the following private method:

#### ``Insert Data Core``

This is similar to the method ``Insert Data`` but it has one extra input.  This input is called ``Nested?``.  If the ``Group`` input of ``Insert Data`` contains a ``.``, this will indicate that the group is a nested group


## Members

| Group    | tag      | Description |
| :------- | :------- | :---------- |
| pas      | 
| pas.spk  | fcenter  | Center frequency of the speaker chirp |
|          | df       | Bandwidth in Hz of the chirp |
|          | cycle    | Boolean indicating whether the speaker is set to automatically cycle |
|          | length   | Length of speaker activation if cycle is TRUE |
|          | period   | Period in seconds over which speaker cycles to ON |
|          | enabled  | Current speaker state.  TRUE is ON. |
|          | vrange   | |
|          | voffset  |  |
|          | ienabled | Array of booleans indicating speaker state for individual cells |
| pas.las  | vrange   | Array of floats that define the laser modulation range |
|          | voffset  | Array of floats that define the laser modulation offset |
| Filter   | period   |  |
|          | length   |   |
|          | auto     |  |
| general  | filter_pos | | 
|          | denuder_pos | |
|          | inlet  | |
| crd      | klaser | Array that represents the laser gains for the red, blue 0 and blue 1 lasers respectively. |
| crd      | enable | Boolean array containing the enable state of the lasers in this order - red, blue0, and blue1 |




