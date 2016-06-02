# Files
The server will generate several different files depending on configuration settings and user input.  These are:

* the main file - this is the primary source of data and may be mirrored to two drives depending on the initial user settings.
* CRD tau data - this is a record of all taus calculated by the system.
* PAS frequency data - this is frequency data related to the PAS operation.
* A log file.

The location of the main data file is found on an auxilary drive connected to the PXI chassis via a USB port.  Drives are labeled in order and start at ``u:``.
Drives may be accessed via an FTP tool such as [FileZilla](https://filezilla-project.org) 

## File Writing Functionality
All files are written using the same actor object - ``File Actor``.  





