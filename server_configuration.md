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

* ``Port`` - This is the key for the serial port that the device or device cluster will communicate on.  The value usually is the string *COM* followed by a number.
* ``Serial Config.baud rate`` - Defines the baud rate for device communication.
* ``Serial Config.data bits`` - Defines the number of data bits in the communication.
* ``Serial Config.stop bits`` - Defines the number of stop bits.  This value will be 0 for 0 bits, 10 for 1 bit and 20 for 2 bits.
* ``Serial Config.parity`` - Defines the parity of the communication
* ``Serial Config.flow control`` = 0
* ``Serial Config.endModeforReads`` - Integer defining how the end is determined for reading from the port.  These values are:
  * 0 = 
  * 1 = 
  * 2 = 
* ``Serial Config.endModeforWrites`` Similar to ``endModeforReads``.  Integers are defined in same manner.
* ``Msg Config.sendEndEn`` - Boolean indicating whether a terminating character is sent with a write to the port.
* ``Msg Config.suppEnEnRd`` - Boolean indicating whether to supress the end of a read with a termination character (i.e. reads will terminate on timeout or when a specific number of bytes is read from the port).
* ``Msg Config.termChar`` - Hexadecimal value indicating what the termination character for communication is. 10 will be a new line character and 13 will be a carriage return.
* ``Msg Config.EnTermChar`` - Boolean determining whether a termination character is used or not.

## Device Specific Configuration
### Alicat
