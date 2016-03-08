# Configuration

The user interface uses a configuration file to determine how certain aspects are displayed.  The file is written in javasctript object notation (JSON).  The file is called ``ui.json`` and resides in the main client directory (i.e. same place ``index.html``).  

## Configuring How Plots are Displayed
The configuration file may determine how individual plots are rendered.  At the time of writing this documentation, the configuration file contained the following keys for configuration plots:

* **crdplot**: This is the plot that contains derived CRD data such as ringdown times, extinction, etc.
* **pasplot**: Displays 1 Hz data from the photoacoustic spectrometer.
* **flowplot**: Displays 1 Hz data from the Alicats including pressure, temperature and flow rate.
* **ppt**: Displays 1 Hz data returned from the Honeywell pressure transducers.  These meters return pressure and temperature.

Each section of the configuration file associated with plotting may contain the following entries for configuring the plots:

* **``color``**: array of strings containing colors for rendering the individual plots on the graph
* **``strokewidth``**: array of integers that contain the width of the strokes for rendering the lines.
* **``pattern``**: array of strings that represent the dygraph associated stroke patterns.  The value can be ``null``.  If the value is ``null``, then line will be solid.  Available dygraph values are:
  * ``DASHED_LINE``
  * ``DOTTED_LINE``