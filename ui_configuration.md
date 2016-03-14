# Configuration

The user interface uses a configuration file to determine how certain aspects are displayed.  The file is written in javasctript object notation (JSON).  The file is called ``ui.json`` and resides in the main client directory (i.e. same place ``index.html``).  

This configuration file is used to primarily define how plots are rendered, but contains two additional entries:

* ``name`` - this is a string that defines system name (in this case this is EXSCALABAR).
* ``version`` - this defines the current version of the user interface.  This value should only be adjust in conjunction with the ``package.json`` file.  The ``gulp.js`` file 

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
* **``ygrid``**: boolean indicating whether to display the ygrid in the plot.
* **``xgrid``**: boolean indicating whether to display the xgrid in the plot.

For the array data, there does not need to be a 1:1 correspondence between the number of entities being graphed and the number of entries in the arrays.  The plots will be rendered in order using the existing values and when there are no futher values to be used, the arrays will be recycled (i.e. the values will be populated by beginning at the front of the array and working backward).

As an example of this in action, let us say we have two devices with the following plotting entries:

```json
"vaisala": {
    "color": [
      "red"
    ],
    "strokeWidth": [
      2
    ],
    "pattern": [
      null,
      "DASHED_LINE",
      "DOTTED_LINE"
    ],
    "xGrid": true,
    "yGrid": true
  }
```
In this case, we will plot three lines, all red with a stroke width of 2.  The first line is solid, the second is dashed and the third is dotted.

## Additional Plotting Inputs
In addition to the values settable by for all plots as defined above, the user may also configure the names of the CRD and PAS cell plots.  In each of these objects, there is a field called ``names``.  This field represents an array of strings that will be visible to the right of the plot.  These represent the names of the cells and the user may use this field to distinguish or provide specificity to the visual representation of the data.
