### EnergyAnalyzer

#### EnergyAnalyzer [object]

Use the EnergyAnalyzer for analyzing the energy consumption of the selected machines in your plant.

Icon

<!-- image -->

Description

To add the EnergyAnalyzer to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt; Energy Analyzer on the Home ribbon tab.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**Note**

We modeled the EnergyAnalyzer as an application object in a Frame . For this reason opening help with F1 and What's This Help in the dialogs of the objects do not work.

We modeled the dialogs of the objects with the object Dialog . The windows of the objects do not use the standard Siemens PLM theme, but your Windows theme.

To open help for the object, select Help &gt; Help on Object in its dialog.

To assign a different name or a label to the object, click it with the right mouse button and select Rename .

<!-- image -->

**You can:**

- Add the objects for which the EnergyAnalyzer collects energy consumption data on the Tab Objects .
- Show the collected energy consumption data in a table or in a chart in the Tab Evaluate . In addition you can visualize the values of the individual machines. Show a plot the collected values during the simulation run.
- Select settings for displaying the values on the Tab Settings .

The context menu of the EnergyAnalyzer also provides commands for some of the features described above.

<!-- image -->

##### Tab Evaluate

#### Tab Evaluate

**Tab Evaluate**

**On the tab Evaluate you can:**

- Open the table that shows the collected energy consumption data.
- Show the collected energy consumption data in a chart .
- Display a Visualization of the values of the individual machines in the Frame .
- Plot the collected values continuously during the simulation run.

<!-- image -->

##### Open [EnergyAnalyzer]

To open the table that shows the names and the collected energy values of the selected objects, click Open .

<!-- image -->

- The values in the first three cells are values that the EnergyAnalyzer computes.
- The values in the remaining cells are values that the built-in energy features collected, compare Energy Statistics .

| The Value           | Description                                                                                  | Read-Only Attribute                      |
|---------------------|----------------------------------------------------------------------------------------------|------------------------------------------|
| Energy              | Shows the sum of the entire energy consumption of the station.                               | StatEnergyTotalConsumption               |
| Energy operational  | Shows the portion of the entire energy consumption of the station while it was operational . | StatEnergyOperationalConsu mptionPortion |
| Current power input | Shows the current power input of the station. PowerInput                                     |                                          |

Compare Check the Power Consumption in the Dialogs of the Objects

##### Show [EnergyAnalyzer]

To show a chart of the energy consumption of the selected objects, click Show .

<!-- image -->

The chart of the EnergyAnalyzer shows the energy consumption in kilowatt-hours (kWh). The built-in Energy Statistics chart, on the other hand, shows the energy consumption in percent of 100.

The colors for the energy states are identical in both charts.

<!-- image -->

Compare Check the Power Consumption in the Chart

##### Visualization [EnergyAnalyzer]

To visualize energy consumption of the selected objects with a colored circle around the respective object, click Show .

To hide energy consumption of the selected objects, click Hide .

<!-- image -->

Red means that this object has the highest energy consumption. The red circle automatically has the greatest line width.

<!-- image -->

The color distribution is as follows:

<!-- image -->

For comparing the energy consumptions of the resources, the EnergyAnalyzer show colored bars above the objects in the Frame . To be able to compare them, the graphics must not obscure the bars. For this reason you can set the common z-coordinate of the base area of all bars with the attribute \_3D\_lowerSurface . The default value of 2 makes sure that the built-in graphics are visible. This height corresponds to a consumption of 0.

The EnergyAnalyzer assigns a bar to the maximum value, whose top surface has the height \_3D\_upperSurface . Its default value is 12, so that the bar of the resource with the maximum consumption has a height of 10.

<!-- image -->

For identifying the energy consumption, the EnergyAnalyzer divides the consumption values of the selected resources into four categories. For categorizing the resources it considers their maximum consumption. When this maximum consumption is the value max, the categorizes correspond to these consumption intervals between

1. 0 to 0.4 max
2. 0.4 max to 0.7 max
3. 0.7 max to 0.9 max and
4. 0.9 max to max

A resource of the fourth category, i.e., with the highest consumption, is surrounded by a thick red circle. A resource of the first category, i.e., with low consumption, is surrounded by a thin blue circle.

Above the circles the EnergyAnalyzer show a bar chart which displays the portions of the consumption values during the energy states working , setting-up , operational , failed , on standby , and off .

You can enter the radius of the circle on the tab Settings .

<!-- image -->

**Visualization [EnergyAnalyzer]**

##### Plot

To continuously show the plotted values of the power input of the selected objects during the simulation run, click Show .

<!-- image -->

This only works if you select the check box Monitor energy consumption on the tab Settings .

<!-- image -->

#### Tab Objects

On the tab Objects you can add the objects for which the EnergyAnalyzer collects energy consumption data.

To do so, click Add All . The EnergyAnalyzer then inserts all object for which you selected the check box Active on the tab Energy into the list on the tab.

Instead, you can also select the objects in the Frame , drag them onto the EnergyAnalyzer , and drop them there.

<!-- image -->

To delete one or several of the objects, double-click in the list. Then, delete the contents of the respective cell in the dialog that opens and click OK .

#### Tab Settings

Tab Settings

On the tab Settings you can:

- Select to Monitor energy consumption of the objects or to not monitor it.
- Type in the Graphics layer of the objects.
- Type in the Radius of the energy consumption graphic of the objects.
- Select to show a Display panel of cumulated energy values the objects or to not show it.

##### Tab Settings

<!-- image -->

##### Monitor energy consumption

To continuously monitor the energy consumption of the selected objects, select the check box.

Then you can click Show plot of the power input on the tab Settings to show the plotted values.

**Note**

Monitoring all changes may have detrimental effects on run time of your model.

**Graphics layer [EnergyAnalyzer]**

##### Graphics layer [EnergyAnalyzer]

Type in a sufficiently great negative number to ensure that the energy data is always displayed in front of all objects and vector graphics in the Frame that contains your model.

##### Radius [EnergyAnalyzer]

Type in the radius of the circle that the EnergyAnalyzer draws around the objects to show their energy consumption.

The EnergyAnalyzer uses the radius when you click Visualization on the tab Evaluate .

<!-- image -->

**Display panel [EnergyAnalyzer]**

##### Display panel [EnergyAnalyzer]

To show a display panel with these values, select the check box.

- The cumulated energy consumption of all selected machines.
- The cumulated energy consumption of all selected machines while they were in the energy state operational.
- The current power consumption of all selected machines.
- The former maximum power consumption of all selected machines.

<!-- image -->

#### Navigate Menu

The Navigate Menu provides the command Open Location . It opens the Frame window in which the object is located.

#### Tools Menu

The Tools menu provides these menu commands:

**Set Default Colors**

The menu command Set Default Colors opens the table which contains the default colors for showing the energy states the objects can take. The Chart also uses these colors to show the energy.

<!-- image -->

**Set Colors**

The menu command Set Colors opens the table in which you can customize the default colors for showing the energy states the objects can be in. To restore the default colors, which the energy states in the Chart show as well, select Set Default Colors .

#### Help Menu

The Help Menu provides commands to access its functions.

Contents

The menu command Contents opens the table of contents of the Plant Simulation help.

Help on EnergyAnalyzer

The menu command Help on EnergyAnalyzer opens the help topic pertaining to the EnergyAnalyzer .

