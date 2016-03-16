# Interacting with Plots
Plots on the user interface are based on the canvas plotter [dygraphs](http://dygraphs.com).  As such, the plots utilize many of the same interactive means that dygraphs API defines.  
## Zooming
Zooming in on points is accomplished via left mouse button.  To zoom in on y-values (i.e. to decrease the y-range), simply left click and drag straight down.  To zoom in on particular x-values, left click on the plot and drag right or left.  To return the view to the original setup (i.e. autoscaled to the current view maximum and minimum), double click using the left mouse.
## Right-click Menus
Each plot will contain a right click menu (or context menu).  The right click menu is unique to each implementation of the plot, often containing a list of variables that may be selected for plotting.  
In addition to the variables available for plotting, the right-click menu will contain three selections in common:``Autoscale``, ``Autoscale 1x`` and ``Clear Data``.  ``Autoscale`` sets an adjustable window for plotting along the y-axis.  As the maximum and minimum within the plot window change, the window will adjust automatically.   

> **Code Relation**
> 
> Within the code, this will set the plot limits for the y-axis to the values of ``[null, null]``.

``Autoscale 1x`` forces the plot to scale to the current maximum and minimum. It will do this 1x.  ``Clear Data`` will empty all data arrays associated with a plot thus starting the process of recording over again.

> **Code Relation**
> 
> Data is stored in AngularJS services.  When the user selects clear data, this will empty the data in the arrays within the service. A service is a **singleton** so this means that any other entity using that data that was effected will also be effected.  Some plot directives (such as the Alicat, PAS and CRDS) are reused on the interface, so this applies to them also.