# MAX Tasks
Most analog and digital communication is performed directly through DAQmx, the native DAQ driver for communication with National Instruments devices.  All communication with NI devices is configured through Tasks in MAX.  To view available tasks or to create new ones, the user must

* navigate to the remote system (**exscalabar**)
* select *Data Neighborhood* to expand this folder 
* select *NI-DAQmx Tasks* to view the currently configured tasks

![MAX Task list](daqmx tasks.png)
The user may directly interact with the hardware via the preconfigured tasks by selecting double-clicking on the task and clicking the run button (see below).  The user will have the same options as with running a VI - run once or run continuously.  How the user desires to interact with the task will determine how they use this button.  For some operations, such as digital outputs, they are defined to be **1 Sample (on demand)** as in the image below.  In this case, the user will likely want to run continuously, so that they may toggle the switch without having to hit the run button every time they are testing.

![Running a DAQmx task](running daqmx task.png)

## Description of the Tasks

### Hardware in MAX

The hardware in MAX is defined under *Devices and Interfaces* in the system *exscalabar*.  Under *Devices and Interfaces*, the user can expand the tab for the chassis labeled as ``NI PXIe-1078``.  The the individual pieces of the chassis are defined under this tab and are numbered according to their position in the chassis.  The first slot is always the computer itself, ``NI PXIe-8135``. 

The individual cards follow after the computer.  All cards are aliased such that their names reflect the initially intended function of the card.   The cards are currently defined as follows:

2. ``PXIe-8431/8`` - this is the 8 channel RS485 card.
3. ``PXIe-6124``  aliased as ``CRD_Blue`` - this card is a high speed, 4 channel AI card intended to capture the blue ringdown signal.
4. This slot is currently unoccupied.
5. ``PXI-6132`` aliased as ``CRD_Red`` - this card is another high speed, 4 channel AI card intended to capture the red ringdown signal.  This card can capture 4 channels of AI simultaneously at up to 2.5 MHz per channel.
6. ``PXI-6704`` aliased as ``TEC_AO`` - this task was originally intended to define analog outputs for TECs similar to those of the AOP.  These required a DC signal that could be adjusted aperiodically.  As the original TECs have been replaced with the Meerstetter TECs, the AO on these channels have been reappropriated for other tasks.
7. ``PXI-6225`` aliased as ``PAS_HK`` - this card was intended to capture housekeeping data associated with the photoacoustic spectorometer.
8. ``PXI-6225`` aliased as ``CRD_HK`` - this card is a multifunction DAQ card intended to handle the housekeeping operations associated with the CRD.
9. ``PXI-7842R`` - this card is not aliased and is the multifunction, reconfigurable DAQ card that handles much of the PAS IO.  This card requires an FPGA bitfile to operate.

### Task Definitions

#### ``PAS_HK``

This task contains much of the PAS housekeeping AI associated with DAQmx.  The DAQ rate for this card is 10 kHz and the DAQ is multiplexed.  Aside from the photodiode signals, these signals are averaged at the DAQ rate (1 Hz) to produce a single value for data presentation. The AI are defined as follows:

##### Photodiode Time Domain Signals

These are the signals acquired from the photodiode for each PAS cell.

* ``Photodiode_1`` 
* ``Photodiode_2``
* ``Photodiode_3``
* ``Photodiode_4``
* ``Photodiode_5``

##### Laser RMS

These signal is obtained from the box located atop the cell.  This value may also be calculated from the corresponding photodiode signal acquired above.

* ``lRMS_1``
* ``lRMS_2``
* ``lRMS_4``
* ``lRMS_5``

##### Cell Thermistor Temperatures

These signals represent the two thermistor temperatures that associated with each cell.  These thermistor temperatures are acquired via the box atop the cell.

* ``Tcell_11``
* ``Tcell_12``
* ``Tcell_21``
* ``Tcell_22``
* ``Tcell_31``
* ``Tcell_32``
* ``Tcell_41``
* ``Tcell_42``
* ``Tcell_51``
* ``Tcell_52``


#### ``CRDS Blue AI``

This task defines all of the AI associated with the blue laser CRD.  This card samples 4 channels simultaneously at 4 MHz per channel.  The channels are defined within the task as:

* ``Dry``
* ``Dry_Filtered``
* ``High_RH``
* ``Med_RH``

> **Code Connection**
>
> These channel are set to sample at 4 MHz in the MAX task configuration, but the clock for these tasks (defined below) is configured in the method ``eCRDS::Configure Blue``.  The clock will run a fixed number of time (2000) each time the lasers fire and the analog input in this task will sample on each rising edge of this clock.

#### ``CRDS Blue Laser Output``

This task has a single, counter output for firing the blue laser. 

> **Code Connection**
> 
> This channel is stored in the object called ``eCRDS`` under the property called ``Blue Tasks.DO``.  The clock for this output is setup in the method ``eCRDS::Configure Blue``.  Currently, the clock is hard coded for a 1 kHz repetition rate with a 50% duty cycle and will sync to the first rising edge of the red laser.

#### ``CRD Laser Gain``

This task consists of several analog outputs that allow the user to adjust the gain of the CRD lasers aperiodically.  This task is designed to run on demand.  The channels are defined as follow:

* ``Red`` - adjust the gain of the red laser
* ``Blue0`` - adjust the gain of one of the blue lasers
* ``Blue1`` - adjust the gain of the other blue laser

#### ``PMT Gain``

As the above task, but allows the user to adjust the gains of the PMTs on the CRD cells.  The channels are defined as follows:

* ``Cell 0``
* ``Cell ``
* ``Cell 2``
* ``Cell 3``
* ``Cell 4``

#### ``Filter Valve CMD``

Task defines two digital outputs that allow the user to control the two valves associated with the sample/filter line.  In most cases, the two outputs should be operated together, but the user may wish to have individual control.  Because the position of the valve (i.e. closed or open) is defined by the orientation of the valve in the line, it can not be determined beforehand what the meaning of high and low are.  This has to be determined empirically.

#### ``Acquire Ctr``

#### ``General Input``

This task is intended to define digital inputs that are general to the instrument at large (i.e. not owned by a single entity such as the PAS or CRDS in the DAQ system) and currently contains two inputs as defined below:

* ``Blocked Pump`` - input defining whether the pump is currently blocked
* ``Interlock`` - signal generated by switches on the box containing the lasers.  When this signal goes low, the box is open.

#### ``PAS_TEC_En``



