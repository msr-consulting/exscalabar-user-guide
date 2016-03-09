# Configuration
The server is configured via an INI file located on the server under the folder ``c:\exscalabar\cfg`` called ``exscalabar.ini``.  The file is written in the standard [INI format](https://en.wikipedia.org/wiki/INI_file); that is, a file broken out into sections (denoted by square braces) containing a series of key-value pairs.  Below is a description of the functionality defined in the INI file.

## Serial Device Configuration
Serial devices are those that are communicating on a serial port, either via RS232 or RS485.  Devices are configured for a common serial port.  Devices defined in the file are:

* ``Alicat`` - Alicat flow controllers and meters
* ``PPT`` - Honeywell pressure transducers
* ``Vaisala`` - Vaisala hygrometers
* ``Meerstetter`` - Meerstetter TECs
* ``TEC`` - TE Tech TEC

Each serial device contains common parameters for configuring communication on the serial port.  These parameters are:

* ``Port`` = COM2
* ``Serial Config.baud rate`` = 19200
* ``Serial Config.data bits`` = 8
* ``Serial Config.stop bits`` = 10
* ``Serial Config.parity`` = 0
* ``Serial Config.flow control`` = 0
* ``Serial Config.endModeforReads`` = 2
* ``Serial Config.endModeforWrites`` = 2
* ``Msg Config.sendEndEn`` = TRUE
* ``Msg Config.suppEnEnRd`` = FALSE
* ``Msg Config.termChar`` = 13
* ``Msg Config.EnTermChar`` = TRUE