# Writing Tau Data

Child of ``Instr Exe Write to File``.  Class is called ``Exe Write Taus``.  Data is retrieved from the ``CRDS Data`` object.  Each instance of the ``CRD Cell Data`` object contains a property called ``taus``.  Writes 

* Double precision float representing time
* 2 32-bit integers which represent the size of the array written to file.  First dimension is the number of cells, the second is the number taus.
* a 2D array of double precision floats to file 

INI file entry is ``CRD Taus``.  Default folder is ``exscalabar\CRD_Taus``

