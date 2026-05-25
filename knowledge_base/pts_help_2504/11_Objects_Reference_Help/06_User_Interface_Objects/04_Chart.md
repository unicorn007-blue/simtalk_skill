### Chart

#### Chart [object]

Use the Chart for presenting current data and results of the simulation run.

Icon

<!-- image -->

Description

Define data to be plotted:

- By using a Table containing the data, such as simulation results.
- By defining Input Channels that record values of attributes of interest of the objects.

A Chart , which you insert into a Frame , provides the Statistics Wizard . Select the command Statistics Wizard on the context menu of the Frame to open it.

<!-- image -->

<!-- image -->

To show a tooltip with information about the Chart , hover with the mouse over it.

<!-- image -->

To show statistics of the Workers managed by the WorkerPool , drag it over a Chart and drop it there. Select the settings that you need.

<!-- image -->

To change the length of the graphic and the anchor points of the Chart , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Chart to your simulation model, click UserInterface &gt; Chart on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

**See also Show Statistics in a Chart Statistics Wizard [described]**

Drag-and-Drop in the Chart

#### Statistics Wizard [described]

A Chart , which you insert into a Frame , shows the Statistics Wizard .

Select the command Statistics Wizard on the context menu of the Frame to open it.

Select the class(es) of object(s) for which you would like to show statistics values in the Chart . The Chart only adds material flow objects to the display for which you selected the check box Resource Statistics on the Tab Statistics .

<!-- image -->

**Note**

If you are working with a model that was created in a previous version of Plant Simulation that still uses the outdated object names of these versions, the dialog shows a + sign in front of the new object names.

- To inherit the settings you select below, select Inherit Settings .
- Select the object classes in the group box Class for which you want to show statistics values in the Chart . The Chart only adds material flow objects to the display for which you selected the check box Resource Statistics on the Tab Statistics . You can select any number of classes .

Select the type of resource(s) for which you would like to show statistical data of the selected object(s) in the Chart under Resource Type on the tab Statistics of an object collecting statistical data. With the check boxes in the Statistics Wizard you can restrict, which objects Plant Simulation shows.

- Production is the default for the Source , Drain , Station , ParallelStation , AssemblyStation , and DismantleStation.
- Transport is the default for the PlaceBuffer , Buffer , Sorter , Track , TwoLaneTrack , Conveyor , AngularConverter , Turntable , Transporter , and Container .

- Storage is the default for the Store .
- Select the criteria according to which Plant Simulation sorts statistical data from the drop-down list Sort Criterion :

To sort the stations by their name in alphabetical order from A to Z, select Sort Criterion &gt; Name .

To sort the stations in the order that meets your needs, drag the stations onto the Chart in the order it is to show them.

To change the order at a later point in time, edit the table of the Input channels by cutting the respective columns of the objects and pasting them in the desired order.

- Select the statistics type: Resource Statistics , Energy Statistics , or Occupancy .
- To also show statistical data of objects contained in Frames contained in the Frame in which the Chart is located, select Include Subframes .
- To reapply the settings while the simulation model is initialized, select Reapply at Init .
- Click OK to display the Chart window with the settings you selected.
- If you drag a material flow object onto a Chart , which you have not configured yet, you have to select the statistics type . By default, you can select Resource or Occupancy . If you activate energy features , you can also select Energy . The different statistics types provide different value sets. The meaning of the different states is described in the Statistics Report under Resource Statistics of Stationary Resources and Energy Statistics - Energy Statistics .
- For the Statistics type &gt; Resource , the Chart shows the Name of the object and the states it is in: Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , or Unplanned

<!-- image -->

.

<!-- image -->

<!-- image -->

- For the Statistics Type &gt; Energy , the Chart shows the energy states of the object:

Working , Setting-up , Operational , Failed , Standby , and Off .

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period , while the values for the energy states refer to the total energy consumption .

<!-- image -->

<!-- image -->

- For the Statistics Type &gt; Occupancy , the Chart shows the Name of the object and the number of parts located on it. The colored bars serve for differentiating between the objects.

<!-- image -->

<!-- image -->

- You can also show the diagram picture of a Chart in an HtmlReport , compare Display a Chart .

#### Drag-and-Drop in the Chart

Drag-and-drop in the Chart performs a number of actions.

| To do this                                                                                            | Drag                            | To    | Acceler ator   |
|-------------------------------------------------------------------------------------------------------|---------------------------------|-------|----------------|
| Show the statistics of a single material flow object                                                  | material flow object            | Chart | *              |
| Show the statistics of multiple material flow objects                                                 | material flow objects           | Chart | *              |
| Show Driving statistics of the Transporter                                                            | Transporter                     | Chart | *              |
| Show Services statistics of the Worker/Exporter                                                       | Worker/Exporter                 | Chart | *              |
| Show Exporter statistics of the Worker/Exporter                                                       | Worker/Exporter                 | Chart | Shift          |
| Show statistics of Workers controlled by a WorkerPool                                                 | WorkerPool                      | Chart | -              |
| Show the frequency distribution of the number of MUs                                                  | PlaceBuffer , Buffer or Store   | Chart | *              |
| Show the frequency distribution for the individual part types of Supermarket                          | Store configured as Supermarket | Chart | -              |
| Show statistics of all resources which are assigned to the LockoutZone                                | LockoutZone                     | Chart | *              |
| Show the contents of a table                                                                          | DataTable , TimeSequence        | Chart | -              |
| Show the value of the Variable you inserted into a Frame                                              | Variable                        | Chart | *              |
| Show statistics of a Frame , which has the user-defined attribute StatisticsObject                    | User-defined object ( Frame )   | Chart | *              |
| Show statistics of the object Workplace within a Frame , which has the user-defined attribute AOLType | User-defined object ( Frame )   | Chart | *              |

The method addObject accomplishes the same as using drag-and-drop actions described above.

**Note**

To delete one of the displayed objects, click Data Table next to Data Source and delete the object from the data table.

To delete the entire contents of the input channels table, hold down Shift while you drag-and-drop a new object onto the Chart .

If you want your own object, which you modeled in a Frame , to behave like one of the built-in Plant Simulation objects when you drag-and-drop it, create a user-defined attribute of data type object for this Frame and name it StatisticsObject . This attribute may designate any of the material flow objects. The Chart then acts as if the object, to which the user-defined attribute refers, was dropped onto the Chart . This way you can show the statistics of a Frame according to your needs.

If your Frame contains a number of objects whose statistics you would like to show, then assign the data type table to the user-defined attribute named StatisticsObject . The first column of the table has to be of data type string . The Chart now acts if all objects contained in the first column of the table were dropped onto the Chart . You can also use a user-defined row index and type in the labels of the input channels.

#### Dialog Box of the Chart

Dialog Box of the Chart

Double-click the icon of the Chart to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Show Chart [button] - Chart

Collect Data [check box] - Chart

**Show Chart [button] - Chart**

##### Show Chart [button] - Chart

To show the data, which the Chart collected in the display window, click this button.

<!-- image -->

<!-- image -->

To open the dialog of the Chart , double-click anywhere in the display window.

To delete one of the displayed objects, click DataTable next to Data Source and delete the object from the input channels table.

To delete the entire contents of the input channels table, hold down Shift while you drag-and-drop a new object onto the Chart .

To show the data, you can also right-click the Chart object in the Frame and select Show on the context menu.

If your Chart contains a large number of values, you can zoom an area of interest by dragging a selection rectangle over the area.

**Accelerators for the Chart**

You can press the following keys on the keyboard in the display window of the Chart to execute these actions:

| To do this                                                  | Press this Keyboard Key   |
|-------------------------------------------------------------|---------------------------|
| Switch between monochrome and color viewing styles          | S                         |
| Show the Export dialog                                      | X                         |
| Maximize the window to full screen                          | M                         |
| Zoom all, i.e., to show all data without a scrollbar.       | Z                         |
| Show the Text/Data export dialog.                           | D                         |
| Show the Print dialog                                       | P                         |
| Scroll both vertical and horizontal scrollbars by one line. | Arrow keys                |
| Page vertical scrollbar.                                    | PgUp/PgDown               |
| Page horizontal scrollbar to the right.                     | Shift+PgUp                |
| Page horizontal scrollbar to the left.                      | Shift+PgDown              |
| Move vertical scrollbar to its first position.              | Home                      |
| Move vertical scrollbar to its last position.               | End                       |
| Move horizontal scrollbar to its left-most position.        | Shift+Home                |
| Move horizontal scrollbar to its right-most position.       | Shift+End                 |

**SimTalk**

IsShown [SimTalk] - Chart Collect Data [check box] - Chart To make a Chart of the Category &gt; Histogram or Plotter collect data during the simulation run, select this check box.

<!-- image -->

To deactivate data collection, clear the check box.

<!-- image -->

<!-- image -->

Tab Data

Tab Data

On the tab Data you can select the Data Source , i.e., which data the Chart displays, from the drop-down list:

<!-- image -->

- Data from a Data Table .
- Data from Input Channels .

**You can also select the Mode :**

- Sample mode shows sampled data after an interval you enter.
- Watch mode updates the data each and every time one of the displayed values changes.
- Plot mode updates the display whenever a simulation event takes place.

In addition, you can select different views on the Data to be displayed.

**See also**

Data Source [Chart]

**Data Source [Chart]**

###### Data Source [Chart]

Select from where the Chart gets the data you want to display.

**Data Table**

For this setting the Chart shows the contents of a DataTable as a diagram.

<!-- image -->

<!-- image -->

Type in the name of and path to the data table containing the data, or click the button and select the table in the dialog Select Object .

Type in the Range of the table cells you want to show.

- To show all cells in all columns and rows, type in {*,*}..{*,*} .
- To show the first four cells of column one, type in {1,1}..{1,4} .
- To show all cells in column one, type in {1,1}..{1,*} .

You can also type in negative numbers:

- To show the one but last column, type in {-2,*}..{-2,*} .
- To show the one but last and the last column of the table, type in {-2,*}..{*,*} .

Input Channels

For this setting the Chart shows the channels contained in the Input Channels table.

<!-- image -->

To open a table into which you type in the input channels, click Input Channels .

These channels are, as a rule, the paths to attributes or methods of objects, whose values you want to display. You can also type in complex expressions, i.e., method calls, formulas, or the sum of two attributes. Also type in row and column headers as labels of the Chart .

<!-- image -->

To delete the entire contents of the input channels table, hold down Shift while you drag-and-drop a new object onto the Chart .

<!-- image -->

<!-- image -->

**Note**

To change the order in which the Chart shows the stations, edit the Table of the Input Channels by cutting the respective columns and pasting them in the desired order.

**Note**

If the amount of data to be displayed is extremely large, it can take some time to show the Chart . This applies, for example, to a table containing several tens of thousands of cells. Some chart types, for example the 3D types, also take a comparatively large amount of time to display.

**Worker Pools**

For this setting the Chart shows the Workers managed by WorkerPools as a diagram.

<!-- image -->

- To open a table into which you type in the WorkerPools to be used, click Worker Pools . Drag the WorkerPools whose Workers you want to show to the cells of the dialog List of Worker Pools to Configure and click OK.

<!-- image -->

- Select how you want to group the Workers . According to the:
- Pool , which uses the entire WorkerPool .
- Creation Table , which only uses the Workers contained in the Workers to Create table of the WorkerPool .
- Select which statistics values for the Occupancy you want to show:
- Operational + failed shows the time during with the Worker was operational plus the time during which he was failed .
- Overall Time

<!-- image -->

<!-- image -->

<!-- image -->

Then continue configuring the Chart on the tab Data .

SimTalk

DataRange [SimTalk]

DataTable [SimTalk] - Chart

InputChannels [SimTalk]

UseInputChannels [SimTalk]

See also

Show Worker Statistics in a Chart

###### Data [Chart]

Select how the Chart shows the data to be visualized.

<!-- image -->

- In Rows or
- In Columns

This way you can present different views of the same record.

<!-- image -->

**SimTalk**

**DataInColumn [SimTalk]**

**Mode [drop-down list] - Chart**

###### Mode [drop-down list] - Chart

Select the Mode with which the Chart updates the displayed data.

<!-- image -->

- Sample mode updates the Chart periodically after the interval you enter.

Type in the time span ( Interval ) after which the Chart takes the next sample.

- Watch mode updates the Chart whenever the watchable input data changes.

The column Watchable in the window Show Attributes and Methods , shows the methods and attributes which Plant Simulation can watch.

<!-- image -->

- Plot mode updates the Chart whenever a simulation event takes place.

**SimTalk**

update [SimTalk] - Chart ]

NumIntervals [SimTalk]

Mode [SimTalk] - Chart

SampleInterval [SimTalk]

Tab Display

Tab Display

Select how the Chart shows the data on the tab Display .

The tab Display provides the settings listed in the table of contents to the left.

For the Category &gt; Histogram , you can show the data Accumulated .

<!-- image -->

For the Category &gt; Plotter , you can show the data as a Step Curve .

<!-- image -->

###### Chart Category

Category [drop-down list]

Select the category for displaying the data.

<!-- image -->

**· Chart**

Shows a number of values or several sets of a number of values.

**· Histogram**

Shows the frequency distribution for one or several input channels. For this setting you can select the check box Accumulated .

**Note**

The input channels for Histograms should to be watchable to show exact values.

**· Plotter**

Shows the progression of one or more values over time. For this setting you can select the check box Step Curve .

**· 3D Chart**

Shows a 3D Chart embedded in the 3D display window with the settings you select. You cannot open the 3D Chart in a window of its own by clicking Show Chart .

**Note**

The category 3D Chart does not have any effect in a 2D Only model. Here Plant Simulation shows the Chart as an icon.

**· 3D Histogram**

Shows a 3D Histogram embedded in the 3D display window with the settings you select. You cannot open the 3D Histogram in a window of its own by clicking Show Chart .

**Note**

The category 3D Histogram does not have any effect in a 2D Only model. Here Plant Simulation shows the Chart as an icon.

**· XY Graph**

Shows a number of x-y pairs of values or several sets of x-y pairs of values. This setting is only active if you select Table File as the Data Source .

The XY Graph shows the range like this:

- The x values are contained in the first row or column.
- The range determines the y values. The first row or column, which contains the x values, will automatically be excluded.

**Note**

If you select another Category , the Chart in 3D automatically shows the graphic of this category in the Frame .

<!-- image -->

**Category [drop-down list]**

<!-- image -->

**SimTalk**

Category [SimTalk]

putValuesIntoTable [SimTalk] - Chart

resetValues [SimTalk]

**Category - 3D Chart**

The Category 3D Chart shows a 3D Chart embedded in the 3D display window with the settings you select.

**Note**

You cannot open the 3D Chart in a window of its own by clicking Show Chart .

<!-- image -->

**Note**

The category 3D Chart does not have any effect in a 2D Only model. Here Plant Simulation shows the Chart as an icon.

The category 3D Chart has these properties:

- It has a fixed Font Size . Only the setting Bold affects it. For a Width and/or Height greater than 5 meters, the font size is absolutely fixed. For a size smaller than 5 meters the font size scales down with all other display elements.
- It uses the settings for the Color and the Line Weight , which you select on the Tab Color , for the setting Chart Type &gt; Line . It does neither use a Marker Type nor a Line Style .
- It enables you to hide the Base plate and the background of the displayed data by setting the Opacity of the Background and the Desk to 0 on the Tab Color . This way you can create a transparent chart which you can lay on top of other graphics or objects.
- Its Base plate has a thickness of 20 cm by default. If you set the Opacity of the Background to 0 , it has a thickness of 10 cm. For a Width and/or Height smaller than 5 meters, the thickness scales down with all other display elements. If the minimum size is 2.5 m for example, the chart with a base plate has a thickness of 10 cm and a thickness of 5 cm without a base plate.

A 3D Chart attached to the wall of your factory might look like this.

See also Category [drop-down list]

<!-- image -->

**Category - 3D Histogram**

The Category 3D Histogram shows a 3D Histogram embedded in the 3D display window with the settings you select.

<!-- image -->

**Note**

The category 3D Histogram does not have any effect in a 2D Only model. Here Plant Simulation shows the Histogram as an icon.

The category 3D Histogram has these properties:

- It has a fixed Font Size . Only for the setting bold affects it. For a Width and/or Height greater than 5 meters, the font size is absolutely fixed. For a size smaller than 5 meters the font size scales down with all other display elements.
- It uses the settings for the Color and the Line Weight , which you select on the Tab Color , for the setting Chart Type &gt; Line . It does neither use a Marker Type nor a Line Style .
- It enables you to hide the Base plate and the background of the displayed data by setting the Opacity of the Background and the Desk to 0 on the Tab Color . This way you can create a transparent histogram which you can lay on top of other graphics or objects.
- Its Base plate has a thickness of 20 cm by default. If you set the Opacity of the Background to 0 , it has a thickness of 10 cm. For a Width and/or Height smaller than 5 meters, the thickness scales down with all other display elements. If the minimum size is 2.5 m for example, the chart with a base plate has a thickness of 10 cm and a thickness of 5 cm without a base plate.

**See also**

Category [drop-down list]

**Chart Type [drop-down list]**

###### Chart Type [drop-down list]

Select the Type of Chart which displays the values of the simulation run. A record consists of the entries of a row or a column, depending on the setting you selected under Display &gt; Data .

<!-- image -->

Depending on the Category you selected, the Chart provides some or all of these chart types:

| Chart type            | Description                                                                                                                                                                                                                    |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Columns               | Shows each record as a column. When displaying several records, the Chart places the columns next to each other. Compares values across categories.                                                                            |
| Stacked Columns       | Shows each record as a column. When displaying several records, the Chart places the columns of the individual records on top of each other. It stacks positive values upward, negative values downward.                       |
| 100 % Stacked Columns | Shows each record as a column, stacked one on top of the other, showing the respective percentage of the entire set of 100 percent.                                                                                            |
| Bars                  | Shows each record as bars positioned horizontally on top of each other. When displaying several records, the Chart places the bars of the individual records next to each other. Compares values across categories.            |
| Stacked Bars          | Shows each record as a set of bars stacked horizontally next to each other. Positive values are stacked to the right, negative values are stacked to the left.                                                                 |
| 100 % Stacked Bars    | Shows each record as a set of bars, one stacked horizontally next to each other, showing its respective percentage of the entire set of 100 percent.                                                                           |
| Area                  | Shows each record as areas. When displaying several records, the Chart stacks the areas from the individual records one behind the other.                                                                                      |
| Stacked Area          | Shows each record as areas. When displaying several records, the Chart stacks the areas from the individual records one on top of the other. Displays the trend of the contribution of each value over time or categories.     |
| 100 % Stacked Area    | Shows each record as a set of areas, one stacked on top of the other, showing the respective percentage of the entire set of 100 percent. Displays the trend of the percentage each value contributes over time or categories. |
| Line                  | Shows each record as a line.                                                                                                                                                                                                   |
| Line with Markers     | Shows each record as a line with markers.                                                                                                                                                                                      |
| Spline                | Shows each record as a curve.                                                                                                                                                                                                  |
| Spline with Markers   | Shows each record as a curve with markers.                                                                                                                                                                                     |

| Chart type                | Description                                                                                                                                                                                                                                                                                       |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Markers                   | Shows each record as a set of different markers.                                                                                                                                                                                                                                                  |
| Points and Best Fit Line  | Shows each record as a set of data points, and fits the best straight line to them. The line is calculated from least-squares-approximations of the data set.                                                                                                                                     |
| Points and Best Fit Curve | Shows each record as a set of data points, and fits the best curved line to them. The line is calculated from least-squares-approximations of the data set.                                                                                                                                       |
| Pie                       | Shows each record as a slice of a pie, depicting its percentage of the whole. Enter a negative prefix, so that the Chart offsets this slice from the rest of the pie. Use the scrollbar to scroll from record to record. Displays the contribution of each value to a total.                      |
| XY Points                 | Shows the x-y pairs as data points. The first record contains the x- coordinates. The Chart interprets all additional records as the associated y-coordinates. Compares pairs of values.                                                                                                          |
| Line                      | Shows the x-y pairs as data points and connects them with a line. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                                                       |
| Sticks                    | Shows a vertical bar for each x-y pair, starting from the zero line. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                                                    |
| Area                      | Shows the points belonging to the x-y pairs connected and fills the areas thus created. The first record contains the x-coordinates. The Chart interprets all additional records as the associated y-coordinates.                                                                                 |
| 3D Columns                | Shows each record as columns stacked in three-dimensional space. To turn the chart left or right, enter an angle of Rotation or drag the horizontal slider in the display window. To turn the chart up or down, enter the Height or drag the vertical slider in the display window.               |
| 3D Wire Frame             | Shows each record as wire-frames stacked in three-dimensional space. To turn the chart left or right, you can enter an angle of Rotation or you can drag the horizontal slider in the display window. To turn the chart up or down, you can enter the Height or you can drag the vertical slider. |

**Chart Type [drop-down list]**

<!-- image -->

**SimTalk**

ChartType [SimTalk]

Rotation [SimTalk] - Chart

Height [SimTalk] - 3D charts

See also

Data [Chart]

###### 3D Effect

Select one of the 3D effects .

<!-- image -->

- None adds no 3D effect to the Chart Type you selected.
- Shadow adds a black shadow to the chart type.
- 3D adds three-dimensional depth to the chart type.

<!-- image -->

<!-- image -->

- Gradient Bars adds an effect between a gradient and a 3D look to the chart types Columns and Bars .
- Contoured for the chart types 3D Columns and 3D Surface .

<!-- image -->

<!-- image -->

**Note**

Some chart types do not provide 3D Effects .

**SimTalk**

Effect [SimTalk]

**Graph/table [drop-down list]**

###### Graph/table [drop-down list]

Select how the Chart shows the records.

<!-- image -->

- Graph shows the records as a graph only in the Chart window.
- Table shows the records as a table only in the Chart window.

<!-- image -->

<!-- image -->

- Graph and Table shows the records as a graph and as a table in the Chart window.

<!-- image -->

**SimTalk**

GraphTable [SimTalk]

###### Display in Frame

Display in Frame

Display in Frame [check box] - Chart

To display the Chart itself in the Frame in 2D and 3D, instead of the icon of the object, select this check box.

Then type in the Width and the Height of the Chart and set the 3D Image Quality .

<!-- image -->

We advise increasing the size of the icon of the Chart in the Frame : Hold down Shift+Ctrl , grab one of the four corners of the icon with the mouse and drag the icon to a convenient size.

<!-- image -->

| Display in Frame On   | Display in Frame Off   |
|-----------------------|------------------------|

**Note**

When you select Display in Frame , you cannot freely combine Line Styles and Line Weights of the Chart .

**SimTalk**

DisplayInFrame [SimTalk]

**Width [text box] - display in frame**

When you activate Display in Frame , you can type in the Width and the Height of the Chart in meters.

<!-- image -->

**Height [text box] - display in frame**

**Height [text box] - display in frame**

When you activate Display in Frame , you can type in the Height and the Width of the Chart in meters.

<!-- image -->

**3D Image Quality [drop-down list]**

Select the 3D Image Quality with which the Chart shows the image in 3D.

3D Image Quality is only available when you activate Display in Frame .

The 3D Image Quality is only active if 3D is active in your model.

<!-- image -->

- High quality results in high resolution and improved image quality with bad performance.
- Balanced results in medium resolution, is a good compromise between image quality and performance.
- High performance results in low resolution and bad image quality with better performance.

<!-- image -->

**Note**

If you opened the Frame window in 2D and in 3D at the same time, the display quality suffers in 3D. To fix this, close the Frame window in 2D.

**SimTalk**

ImageQuality3D [SimTalk]

DisplayInFrame [SimTalk]

See also

Display in Frame [check box] - Chart

**Gap When Null [check box]**

###### Gap When Null [check box]

To interrupt the line, which the Chart draws for values that are not defined, select this check box. To continue drawing the line, clear the check box.

<!-- image -->

**Undefined Value**

Type in the value that the Chart takes to be as an undefined value. If a point takes this value, the Chart does not display it. The default value is -999999 , i.e., a value that most likely none of the values to be displayed ever takes.

<!-- image -->

**SimTalk**

**GapWhenNull [SimTalk]**

NullValue [SimTalk]

###### Accumulated [check box] - Chart

To create an accumulated histogram, select this check box.

As the Chart then adds the sum of all previous values to each value, the last value thus will be 100 percent.

Note

The Chart only shows the check box for the Category &gt; Histogram .

SimTalk

Accumulated [SimTalk]

**Step Curve [check box]**

###### Step Curve [check box]

To show a step curve instead of straight lines connecting the data points, select this check box.

<!-- image -->

<!-- image -->

A step curve might show some trends more clearly but might not quite be as accurate as the straight lines.

**Note**

The Chart only shows the check box for the Category &gt; Plotter .

<!-- image -->

**SimTalk**

##### StepCurve [SimTalk]

Tab Axes

Tab Axes

Select how Plant Simulation shows the axes used in the Chart on the tab Axes .

The tab shows different settings depending on the Category you selected.

<!-- image -->

###### Grid Lines Y-Axis

Grid Lines Y-Axis

To show Grid Lines on the Y-Axis in the display window of the Chart , select this check box.

To hide them, clear the check box.

SimTalk

XGrid [SimTalk]

YGrid [SimTalk]

Interval

Type in the Interval between the grid lines on the y-axis. It sets the distance of the horizontal grid lines and the labels on the y-axis.

If you do not type a value into the text box, Plant Simulation determines a meaningful interval based on the displayed values.

SimTalk

YGridLineInterval [SimTalk]

###### Grid Lines X-Axis

To show Grid Lines on the X-Axis in the display window of the Chart , select this check box. To hide them, clear the check box.

Type in the maximum Number of grid lines that the Chart shows on the x-axis.

SimTalk

YGrid [SimTalk]

XGrid [SimTalk]

XGridlines [SimTalk]

Number

Type in the Number of grid lines which the Chart shows on the x-axis. The Chart also shows a label for each grid line on the x-axis. If you are displaying a large number of data sets, it makes sense to enter a smaller number so that the labels can be shown completely.

If the number of grid lines is greater than the number of data sets on the x-axis, the Chart only shows as many grid lines as there are data sets.

If the number of grid lines is less than the number of data sets, the Chart reduces the number of grid lines and labels.

Note

For the Category &gt; XY-Graph , the Chart only evaluates the Number , if you also type a fixed Range X , i.e., if you did not type in an asterisk * .

SimTalk

XGridlines [SimTalk]

###### Logarithmic Y-Axis

To activate Logarithmic scaling on the y-axis, select this check box.

This is useful if the data to be displayed is scattered across several orders of magnitude. Logarithmic representation cannot show negative values.

**Note**

If you activate Logarithmic Y-Axis , you also have to type in a value greater than 0 , for example 0.1 , for the Range Y , so that Plant Simulation can display the scale logarithmically.

SimTalk

YLog [SimTalk]

###### Logarithmic X-Axis

To activate Logarithmic scaling on the x-axis, select this check box.

This is useful if the data to be displayed is scattered across several orders of magnitude. Logarithmic representation cannot show negative values.

Note

Logarithmic X-axis is only available for the Chart Type &gt; XY-Graph .

Note

Plant Simulation does not show the check box Logarithmic X-Axis for all Chart Types .

SimTalk

XLog [SimTalk]

###### Number of Values [text box]

Number of Values [text box]

Type in the Number of Values , which the Chart collects over time per channel.

The setting Number of Values applies to the Category &gt; Plotter .

The more values the Chart collects, the more memory Plant Simulation uses. Once the Chart reaches the number you entered, it starts dropping the least recent values.

SimTalk

NumValues [SimTalk]

See also

Category [drop-down list]

Scrollbar [check box]

To add a scrollbar to the Chart window for the Category &gt; Plotter , select this check box.

Clear the check box to not add a scrollbar.

If the scrollbar is active, you can type in a Feed Rate in grid units, which sets the number of grid units by which the Chart scrolls, when it reaches the right border of the display.

SimTalk

ScrollBar [SimTalk]

See also

Category [drop-down list]

**Feed Rate [text box]**

###### Feed Rate [text box]

Type in the Feed Rate in grid units. It sets the number of grid units by which the Chart scrolls, once it reaches the right border of the display.

The setting Feed Rate applies to the Category &gt; Plotter .

You can type in a value between 0.1 and 12 .

Type in 0.1 for smooth scrolling, type in 12 for scrolling the entire page.

SimTalk

**FeedRate [SimTalk]**

See also

Category [drop-down list]

Step Size [text box]

Type in a Step Size . This is the width of the intervals into which the Chart divides the frequency distribution.

The setting Step Size applies to the Category &gt; Histogram .

SimTalk

StepSize [SimTalk]

See also

Category [drop-down list]

###### Range Y

Type in the first value of the Range the Chart is to display on the y-axis into the left text box.

<!-- image -->

The default setting 0 ... * means that Plant Simulation shows the vales between 0 and the largest displayed value.

**Note**

When you activate Logarithmic Y-Axis , you also have to type in a value greater than 0 , for example 0.1 , for the Range Y , so that Plant Simulation can display the scale logarithmically.

Type in the last value of the range the Chart is to display scaled on the y-axis into the right text box.

Use the asterisk * to designate open or semi-open ranges along the y-axis and along the x-axis.

Compare these examples:

| Type in   | To do this                                                                           |
|-----------|--------------------------------------------------------------------------------------|
| *…*       | Show the values between the smallest and the greatest displayed value on the y-axis. |
| 0…*       | Show the values between 0 and the greatest displayed value on the y-axis.            |
| * …7.5    | Show the values between the smallest displayed value and 7.5 on the y-axis.          |
| -20 …20   | Show the values between -20 and +20 on the y-axis.                                   |

**Note**

If you specify neither Title nor Subtitle , the Chart might, under certain circumstances, cut off the upper part of the Range Y .

Type a blank space into the text box Subtitle to prevent this.

SimTalk

YScaleMin [SimTalk]

YScaleMax [SimTalk]

**See also XScaleMin [SimTalk] XScaleMax [SimTalk]**

**Range X**

###### Range X

Type in the first value of the Range , which the Chart is to display scaled on the x-axis in the left text box.

<!-- image -->

Type in the last value of the Range , which the Chart is to display scaled on the x-axis in the right text box. The default setting 0 … 0 means that Plant Simulation shows the entire range of definition.

Ir you are only displaying part of the range, the Chart shows a horizontal scrollbar, allowing you to scroll through the entire range of definition.

For the Category &gt; Histogram , the Range X directly defines the range of definition. Type 0 into the right text box, so that the Chart dynamically adjusts the upper bound. Type the size of the intervals, into which the Chart divides the frequency distribution, into the text box Step size .

For the Category &gt; Plotter , the Range X defines the time span, which the Chart shows in the display. You can also define the Feed Rate by which the Chart scrolls when it reaches the right-hand side of the display. Type in a number between 0.1 and 12 . The number 0.1 stands for smooth scrolling, while 12 scrolls the entire page.

Use the asterisk * to designate open or semi-open ranges along the x-axis. You can also use it to designate dynamic upper limits for the Histogram .

Compare these examples:

| Type in   | To do this                                                                  |
|-----------|-----------------------------------------------------------------------------|
| *…*       | Show the values between the smallest and the greatest displayed value.      |
| 0…*       | Show the values between 0 and the greatest displayed value on the x-axis.   |
| * …7.5    | Show the values between the smallest displayed value and 7.5 on the x-axis. |
| -20 …20   | Show the values between -20 and +20 on the x-axis.                          |

Negative values and 0 are useful for charts of category XY Graph .

SimTalk

XScaleMin [SimTalk]

XScaleMax [SimTalk]

<!-- image -->

Tab Labels

Tab Labels [Chart]

Type in a Title , a Subtitle , and labels for the X-Axis , the Y-Axis and the Z-Axis of the Chart .

Select if and where Plant Simulation shows the Legend and type in Annotations on the tab Labels .

<!-- image -->

**Note**

If you type in neither Title nor Subtitle , the Chart might, under certain circumstances, cut off the upper part of the Y Range . Enter a blank space into the text box Subtitle to prevent this.

See also

Title [text box] - Chart

Subtitle [text box] - Chart

X-Axis [text box] - Chart

Y-Axis [text box] - Chart

Z-Axis [text box] - Chart Title [text box] - Chart Type any text that Plant Simulation shows as the title of the Chart in the Chart window into this text box.

<!-- image -->

Select a font for the Title , select if you want to use Bold face and/or Italic face, and select a relative Size on the Tab Font .

SimTalk

Title [SimTalk]

###### Subtitle [text box] - Chart

Subtitle [text box] - Chart

Type any text that Plant Simulation shows as the subtitle of the Chart in the Chart window into this text box.

<!-- image -->

Select a font Subtitle , select if you want to use Bold face, and/or Italic face on the Tab Font .

SimTalk

SubTitle [SimTalk]

X-Axis [text box] - Chart

Type in any text that the Chart shows in the Chart window on the x-axis.

<!-- image -->

###### Y-Axis [text box] - Chart

Y-Axis [text box] - Chart

Type in any text that the Chart shows in the Chart window on the y-axis.

<!-- image -->

###### Z-Axis [text box] - Chart

Type in any text that Chart shows in the Chart window on the z-axis.

Note

The Chart only shows the text box when you select one of the 3D Chart Types &gt; 3D Columns / 3D Wire Frame or 3D Surface .

SimTalk

ZLabel [SimTalk]

###### Legend

Select if and on which side of the Chart window Plant Simulation shows the legend for the values which the Chart displays.

<!-- image -->

- Off , i.e., no legend.
- On the Right , in one line.
- On the Right , in two lines .
- On the Right , stacked .

Shows the input channels from bottom to top instead of from top to bottom. It is especially well suited for the Chart Types &gt; Stacked Columns and 100 % Stacked Area .

- On the Left , in one line.
- On the Left , in two lines .
- At the Top , in one line.
- At the Top , in two lines .
- At the Bottom , in one line.
- At the Bottom , in two lines .

**SimTalk**

LegendLocation [SimTalk]

###### Annotations [button]

To open the table Annotations , click this button.

<!-- image -->

Add additional lines and text to the Chart .

<!-- image -->

**· Type**

Select the Type of the annotation:

- Select 0: Vertical Line to show a vertical line.
- Select 1: Horizonal Line to show a horizontal line.
- Select 2: X-axis Label for labeling the x-axis.
- Select 3: Y-axis Label for labeling the y-axis.

Select 4: Text for any text.

**· Value**

Type in the value where the Chart displays the line in the Chart window.

For a horizontal line or for an annotation of the Y-axis or for this is the Y-value.

For a vertical line or for an annotation of the X-axis this is X-value.

Type in Y-values in the Y scale of the Chart .

Type in X-values in the X scale of the Chart . For a bar chart the value 3.5 means that the X-value is placed between the third and the fourth bar.

**· From**

Type in the starting point of the line here. If you do not type in a value, the Chart extends an existing line.

This way you can not only create horizontal and vertical lines but also diagonal lines.

For a horizontal line or for text this is an X-value. For a vertical line this is a Y-value.

**· To**

Type in the end point of the line here.

**Annotations [button]**

If you do not type a value into the cells From and To , the Chart draws the line from the left to right, or from the top to the bottom of the display window.

For a horizontal line this is an X-value. For a vertical line this is a Y-value.

**· Color**

Type in the number of the color of the line here. Define colors on the Tab Color .

**· Style**

For lines of Type 0 or 1 , you can type in the line style.

For text of Type 4 , you can type in the marker style.

|   Value | Line style                | Marker style               |
|---------|---------------------------|----------------------------|
|       0 | a thin solid line         | text only without a marker |
|       1 | a dashed line             | a plus sign                |
|       2 | a dotted line             | a cross                    |
|       3 | a dash-dot line           | a circle                   |
|       4 | a dash-dot-dot line       | a filled circle            |
|       5 | a medium thin solid line  | a square                   |
|       6 | a thick solid line        | a filled square            |
|       7 | a grid tick               | a diamond                  |
|       8 | a grid line               | a filled diamond           |
|       9 | none                      | upward triangle            |
|      10 | a medium thick solid line | solid upward triangle      |
|      11 | an extra thick solid line | downward triangle          |
|      12 | none                      | solid downward triangle    |
|      13 | none                      | small plus                 |
|      14 | none                      | small cross                |
|      15 | none                      | small circle               |
|      16 | none                      | small solid circle         |
|      17 | none                      | small square               |
|      18 | none                      | small solid square         |
|      19 | none                      | small diamond              |
|      20 | none                      | small solid diamond        |

|   Value | Line style   | Marker style                  |
|---------|--------------|-------------------------------|
|      21 | none         | small upward triangle         |
|      22 | none         | small solid upward triangle   |
|      23 | none         | small downward triangle       |
|      24 | none         | small solid downward triangle |
|      25 | none         | large plus                    |
|      26 | none         | large cross                   |
|      27 | none         | large circle                  |
|      28 | none         | large solid circle            |
|      29 | none         | large square                  |
|      30 | none         | large solid square            |
|      31 | none         | large diamond                 |
|      32 | none         | large solid diamond           |
|      33 | none         | large upward triangle         |
|      34 | none         | large solid upward triangle   |
|      35 | none         | large downward triangle       |
|      36 | none         | large solid downward triangle |
|      92 | none         | arrow north                   |
|      93 | none         | arrow north east              |
|      94 | none         | arrow east                    |
|      95 | none         | arrow south east              |
|      96 | none         | arrow south                   |
|      97 | none         | arrow south west              |
|      98 | none         | arrow west                    |
|      99 | none         | arrow north west              |

**· Text**

Type in any text that describes the line here. You can optionally enter the following two-character prefix codes, consisting of the pipe symbol ( | ) and a letter. These control at which position in the graph the text will be positioned:

| Prefix   | Position                        |
|----------|---------------------------------|
| &#124;l  | left inside edge of the graph   |
| &#124;L  | left outside edge of the graph  |
| &#124;r  | right inside edge of the graph  |
| &#124;R  | right outside edge of the graph |
| &#124;c  | centered inside of the graph    |

**Remarks**

Plant Simulation always shows user-defined annotations in the foreground. In previous versions this was not the case if the Y-Axis showed time values. As the Chart component, which Plant Simulation uses, cannot display times, Plant Simulation creates the captions for time values on the Y-Axis and the horizontal grid lines as annotations .

If you do add your own annotations to such a Chart , Plant Simulation now shows all annotations , including the grid lines, in the foreground. In this case, we recommend to hide the grid lines or to set the Color of the grid to a light color, for example to light gray.

SimTalk

getAnnotations [SimTalk]

setAnnotations [SimTalk]

See also

Add Labels and a Legend

Tab Color

Tab Color [Chart]

Select a Color for the Grid , the Background , the Desk , the Text , for the plotted data (numbers 1 through 14), and for additional colors on the tab Color .

You can Add or Delete a color. You can also select the Opacity , a Line Style , and a Line Weight . For certain chart types you can also select a Marker Size .

If you would like the Chart to inherit color attributes, make sure that the inheritance check box for on the right-hand side of the tab looks like this .

<!-- image -->

**SimTalk**

setColor [SimTalk] setLineStyle [SimTalk] getColor [SimTalk] getLineStyle [SimTalk] See also Color [Chart]

**Color [Chart]**

###### Color [Chart]

The Chart shows the number of the color or the name of item for which you define the color in the column Color .

<!-- image -->

- Grid (number -3 )

Is the color the Chart uses for displaying the grid, i.e., the bounding rectangles, and the grid lines of the graph proper in the Chart window.

- Background (number -2 ) Is the color the Chart uses for displaying the background of the graph proper in the Chart window.
- Desk (number -1 ) Is the color the Chart uses for displaying the area located outside of the bounding rectangle of the graph's grid in the Chart window.
- Text (number 0 )

Is the color the Chart uses for displaying text.

- Colors (numbers 1 through 14 )

1 through 14 are the predefined colors of the input channels of the displayed data.

You can add additional colors and define their properties to meet your modeling needs.

<!-- image -->

Double-click the Color box to open the MS Windows dialog Colors where you define colors.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

setColor [SimTalk]

**getColor [SimTalk]**

###### Opacity

Type in a number for the opacity of the color. Type in 0 for an entirely transparent color, type in 255 for a completely opaque color.

Semi-transparent colors will, for example, increase the readability of the Chart Type &gt; Area .

<!-- image -->

SimTalk

setColor [SimTalk]

getColor [SimTalk]

###### Line Style

To change the properties of the line with which the Chart shows the values, click the down-arrow in the cell whose property you want to change.

Then select another Line Weight and another Marker Type from the drop-down lists.

**Note**

If you select Display in Frame , you cannot freely combine line styles and Line Weights of the Chart .

Select the line style with which the Chart shows the values.

The Chart uses these settings for the Chart Types &gt; Line and Spline .

<!-- image -->

SimTalk setLineStyle [SimTalk] getLineStyle [SimTalk]

**Line Weight**

###### Line Weight

Select the Line Weight with which the Chart shows the values.

<!-- image -->

<!-- image -->

###### Marker Type

Select the Marker Type with which the Chart shows the values.

The Chart uses these settings for the Chart Types &gt; Line with Markers and Spline with Markers .

<!-- image -->

<!-- image -->

**Add [color]**

###### Add [color]

To add additional colors to the color table, click Add .

<!-- image -->

Define a color in the dialog Colors , and click OK to add that color to the bottom of the Color table.

Double-click the Color box to open the MS Windows dialog Color where you define colors.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

###### Delete [color]

To delete the color you selected from the Color Table , click this button.

<!-- image -->

**Marker Size**

###### Marker Size

Select the size of the markers from the drop-down list.

The setting Marker Size applies to the settings Chart Types &gt; Line with Markers and Spline with Markers .

<!-- image -->

**See also**

Chart Type [drop-down list]

Tab Font

Tab Font [Chart]

Select a font, text effects and a zoom factor for the Labels , the Title and the Subtitle , and for data displayed as a Table on the tab Font .

<!-- image -->

**Note**

MS UI Gothic is intended for our Japanese users. The English or German version of Microsoft Windows might not provide this font by default.

**See also Labels [Chart] Title [font] - Chart Subtitle [font] - Chart Table [font] - Chart**

Plant Simulation Help

Unpublished work. © 2025 Siemens

11-4935

**Labels [Chart]**

###### Labels [Chart]

Select a font from the drop-down list for the labels .

<!-- image -->

This font does not apply to the Title , the Subtitle and to data displayed in Table format in the Chart window.

Bold

To apply bold face to all labels, select Bold . This does not apply to the Title , the Subtitle and to data displayed in Table format in the Chart window.

Italic

To italicize all labels, select Italic . This does not apply to the Title , the Subtitle and to data displayed in Table format in the Chart window.

Size

Select a size for the lettering for all labels. This does not apply to the Title , the Subtitle and to data displayed in Table format in the Chart window.

**Note**

The numbers in the drop-down list are not actual point sizes, but set a factor which the Chart uses for sizing labels.

SimTalk

LabelFont [SimTalk]

###### Title [font] - Chart

Select a font from the drop-down list for the Title of the Chart displayed in the Chart window.

<!-- image -->

Bold

To apply bold face to the Title of the Chart , which is displayed in the Chart window, select Bold .

Italic

To italicize the Title of the Chart , which is displayed in the Chart window, select Italic .

Size

Select a size for the lettering from the drop-down list for the Title of the Chart displayed in the Chart window.

Note

The numbers in the drop-down list are not actual point sizes, but set a factor that the Chart uses for sizing labels.

SimTalk

TitleFont [SimTalk]

**Subtitle [font] - Chart**

###### Subtitle [font] - Chart

Select a font from the drop-down list for the Subtitle of the Chart , which is displayed in the Chart window.

<!-- image -->

Bold

To apply bold face to the Subtitle of the Chart , which is displayed in the Chart window, select Bold .

Italic

To italicize the Subtitle of the Chart , which is displayed in the Chart window, select Italic .

SimTalk

SubtitleFont [SimTalk]

###### Table [font] - Chart

Select a font from the drop-down list for data which the Chart shows in Table format in the Chart window.

<!-- image -->

Size

Select a size for data, which the Chart shows in Table format in the Chart window.

**Note**

The numbers in the drop-down list are not actual point sizes, but set a factor the Chart uses for sizing labels.

SimTalk

TableFont [SimTalk]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The commands are described under the View Menu .

SimTalk

updateDialog [SimTalk]

Tools Menu

Tools Menu

The Tools Menu provides the commands listed in the table of contents to the left.

###### Use Metric Prefix [command]

Activates or deactivates if the Chart shows a unit prefix on the y-axis for very great or very small values, for example 100K instead of 100000.

| The prefix   | stands for   |
|--------------|--------------|
| p            | pico         |
| n            | nano         |
| u            | micro        |
| m            | milli        |
| K            | kilo         |
| M            | million      |
| B            | billion      |
| T            | trillion     |

**SimTalk**

UseMetricPrefix [SimTalk]

**Reset Values [command]**

###### Reset Values [command]

Deletes all values which the Chart collected.

SimTalk

resetValues [SimTalk]

###### Print [Chart]

Opens the dialog Print . Select a printer from the drop-down list.

Click Setup to open the Properties dialog of the selected printer and modify settings there.

SimTalk

showPrintDialog [SimTalk] - Chart

**Copy to Clipboard**

###### Copy to Clipboard

Copies the content of the Chart window as a bitmap to the clipboard.

SimTalk

copyBitmapToClipboard [SimTalk] - Chart

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Chart**

#### \_Methods of the Chart

The Chart provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

addObject [SimTalk] - Chart

Adds the designated object to the Chart designated by &lt;Path&gt;.

Remarks

This works the same way as if you dragged the object to the Chart and dropped it there.

Type

Method

Syntax

&lt; Path &gt;.addObject(Object:object) → boolean

Parameter

The parameter Object of data type object designates the name of the object.

Return Value

The return value has the data type boolean .

Example

MyChart.addObject(MyExporter)

See also

Drag-and-Drop in the Chart

##### copyBitmapToClipboard [SimTalk] - Chart

Copies the contents of the display window of the Chart designated by &lt;Path&gt; to the clipboard as a bitmap.

Type

Method

Syntax

```simtalk
< Path >.copyBitmapToClipboard([Width:integer, Height:integer])
```

**Parameters**

- The optional parameter Width of data type integer designates the width of the bitmap in pixels.
- The optional parameter Height of data type integer designates its height.

**Example**

MyChart.copyBitmapToClipboard MyChart.copyBitmapToClipboard(180,120)

**SimTalk**

copyBitmapToFile [SimTalk] - Frame

copyBitmapToIcon [SimTalk]

See also

Copy to Clipboard

##### copyBitmapToFile [SimTalk] - Chart

Copies the graphic of the window of the Chart designated by &lt;Path&gt; to a file as a .png file.

Type

Method

Syntax

&lt; Path &gt;.copyBitmapToFile(FileName:string, Width:integer, Height:integer)

**Parameters**

- The parameter FileName of data type string designates the name of the file to which Plant Simulation writes the .png file.
- The parameter Width of data type integer designates the width of the bitmap.
- The parameter Height of data type integer designates the height of the bitmap.

**Example**

.Models.MyChart.copyBitmapToFile("myChartImage",180,120)

**SimTalk**

copyBitmapToClipboard [SimTalk] - Chart

copyBitmapToIcon [SimTalk]

**copyBitmapToIcon [SimTalk]**

##### copyBitmapToIcon [SimTalk]

Copies the graphic of the window of the Chart designated by &lt;Path&gt; to an icon of the designated object.

Remarks

copyBitmapToIcon applies to the icon of the addressed instance not to the icon of the object class.

Type

Method

Syntax

```simtalk
< Path >.copyBitmapToIcon(Destination:object, IconNumberOrName:integer/ string[ ,Width:integer, Height:integer])
```

**Parameters**

- The parameter Destination of data type object designates the object into which the bitmap is to be copied.
- The parameter IconNumberOrName of data type integer or string designates the icon. If the object does not have an icon with the name or the number respectively yet, Plant Simulation creates a new icon.
- The optional parameter Width of data type integer designates the width of the bitmap.
- The optional parameter Height of data type integer designates the height of the bitmap.

If you do not specify the optional parameters, Plant Simulation uses the current width and height of the Chart .

**Example**

MyChart.copyBitmapToIcon(Station1, -1)

**SimTalk**

copyBitmapToClipboard [SimTalk] - Chart

copyBitmapToFile [SimTalk] - Chart getAnnotations [SimTalk]

Returns the contents of the table Annotations of the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getAnnotations(AnnotationsToGet:table)

Parameter

The parameter AnnotationsToGet of data type table designates the table into which the annotations table is going to be written.

Example

MyChart.getAnnotations(MyAnnotationsTable)

SimTalk

setAnnotations [SimTalk]

Annotations [button]

See also

Add Labels and a Legend

**getColor [SimTalk]**

**getColor [SimTalk]**

Returns the RGB value of the color of an item in the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getColor(ColorNo:integer[, byref Opacity:integer]) -&gt; integer

**Parameters**

- The parameter ColorNo of data type integer designates the color of the element.
- Grid (number -3 )

Is the color the Chart uses for displaying the grid, i.e., the bounding rectangles, and the grid lines of the graph proper in the Chart window.

- Background (number -2 )

Is the color the Chart uses for displaying the background of the graph proper in the Chart window.

- Desk (number -1 )

Is the color the Chart uses for displaying the area located outside of the bounding rectangle of the graph's grid in the Chart window.

- Text (number 0 )

Is the color the Chart uses for displaying text.

- Colors ( numbers 1 through 14 )

1 through 14 are the predefined colors of the input channels of the displayed data.

<!-- image -->

- The optional parameter Opacity of data type integer designates the opacity of the color.

**Return Value**

The return value has the data type integer .

**Example**

```simtalk
var rgb: integer := Chart.getColor(3)  -- reads the RGB color value of color 3
var opacity: integer
Chart2.setColor(3, Chart1.getColor(3, opacity), opacity) -- copies the color value and the opacity of color 3 of Chart1 to Chart2
```

**SimTalk**

setColor [SimTalk]

See also

Color [Chart]

**getHTMLCode [SimTalk] - Chart**

##### getHTMLCode [SimTalk] - Chart

Returns the chart graphic as HTML code in the format SVG of the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getHTMLCode([Caption:string, Width:integer, Height:integer, inMM:boolean]) → string
```

**Parameters**

- The optional parameter Caption of data type string designates the desired caption of the graphic. Specify the caption to show the chart with this caption.
- The optional parameter Width of data type integer designates the desired Width of the graphic.
- The optional parameter Height of data type integer designates the desired Height of the graphic. If you do not specify the width and the height, Plant Simulation uses the width and the height of the Chart window.
- The optional parameter inMM of data type boolean specifies if the width and the height of the graphic was specified in millimeters (true) or in pixels (false).

Return Value

The return value has the data type string .

**Example**

```simtalk
print MyChart.getHTMLCode
```

See also

**Display a HtmlReport**

**getLineStyle [SimTalk]**

Returns the settings of the line style in the Chart designated by &lt;Path&gt; and writes them into the passed parameters.

Type

Method

Syntax

```simtalk
< Path >.getLineStyle(ColorNumber:integer, byRef Style:string, byRef Weight:string, byRef Marker:string)
```

**Parameters**

The parameter ColorNumber of data type integer designates the Color .

- Grid (number -3 )

Is the color the Chart uses for displaying the grid, i.e., the bounding rectangles, and the grid lines of the graph proper in the Chart window.

- Background (number -2

Is the color the Chart uses for displaying the background of the graph proper in the Chart window.

- Desk (number -1 )

Is the color the Chart uses for displaying the area located outside the bounding rectangle of the graph's grid in the Chart window.

- Text (number 0 )

Is the color the Chart uses for displaying text.

- Colors (numbers 1 through 14 )

1 through 14 are the predefined colors of the input channels of the displayed data.

<!-- image -->

**getLineStyle [SimTalk]**

- The local variable Style of data type string , to which the value is assigned, designates the Line Style .
- The local variable Weight of data type string , to which the value is assigned, designates the Line Weight .
- The local variable Marker of data type string , to which the value is assigned, designates the Marker Type .

**Example**

```simtalk
var s,w,m : string
MyChart.getLineStyle(1,s,w,m)
print s," ",w," ",m
```

SimTalk

setLineStyle [SimTalk]

See also

Color [Chart]

##### printChart [SimTalk]

Prints the contents of the window of the Chart designated by &lt;Path&gt; to the default printer.

Type

Method

Syntax

```simtalk
< Path >.printChart([Width:real, Height:real, Orientation:integer])
```

**Parameters**

- The optional parameter Width of data type real designates the width of the printed Chart in millimeters.
- The optional parameter Height of data type real designates the height of the printed Chart in millimeters.
- The optional parameter Orientation of data type integer designates the orientation of the printed Chart . You can specify 0 for the printer Default , 1 for Landscape , or 2 for Portrait .

**Example**

MyChart.printChart MyChart.printChart(160,150,2)

**See also**

**Print [Chart]**

putValuesIntoTable [SimTalk] - Chart

Writes the collected values of the Chart designated by &lt;Path&gt; into the designated table.

Remarks

putValuesIntoTable is especially useful if you selected the Category &gt; Histogram or the Category &gt; Plotter as then the Chart collects values over time which you cannot easily access in any other way.

Type

Method

Syntax

&lt; Path &gt;.putValuesIntoTable(DestinationTable:table)

Parameter

The parameter DestinationTable of data type table designates the table.

Example

MyChart.putValuesIntoTable(MyDataTable)

See also

Category [drop-down list]

##### resetValues [SimTalk]

Resets the collected values for the Category &gt; Histogram and the Category &gt; Plotter of the Chart designated by &lt;Path&gt;.

Remarks

resetValues deletes the existing data and starts collecting data anew.

You can, for example, use it to record a weekly histogram or to suppress data collected during the ramp-up phase.

Type

Method

Syntax

&lt; Path &gt;.resetValues

Example

MyChart.resetValues

See also

Copy to Clipboard

Category [drop-down list]

##### setAnnotations [SimTalk]

##### setAnnotations [SimTalk]

Sets the table Annotations of the Chart designated by &lt;Path&gt;.

<!-- image -->

**Remarks**

Plant Simulation always shows user-defined annotations in the foreground. In previous versions this was not the case if the Y-Axis showed time values. As the Chart component, which Plant Simulation uses, cannot display times, Plant Simulation creates the captions for time values on the Y-Axis and the horizontal grid lines as annotations .

If you do add your own annotations to such a Chart , Plant Simulation now shows all annotations , including the grid lines, in the foreground. In this case, we recommend to hide the grid lines or to set the Color of the grid to a light color, for example to light gray.

Type

Method

Syntax

&lt; Path &gt;.setAnnotations(AnnotationsToSet:table)

**Parameter**

The parameter AnnotationsToSet of data type table designates the table that contains the contents of the annotations table.

By entering the following information into the table, you can add additional lines and text to the Chart :

- Type

Select the Type of the annotation:

Select

0: Vertical Line to show a vertical line.

Select

1: Horizonal Line to show a horizontal line.

Select

2: X-axis Label for labeling the x-axis.

Select

3: Y-axis Label for labeling the y-axis.

Select

4: Text for any text.

**· Value**

Enter the value where the Chart displays the line in the Chart window.

For a horizontal line or for an annotation of the Y axis or for this is the Y value.

For a vertical line or for an annotation of the X axis this is X value.

Enter Y values in the Y scale of the Chart .

Enter X values in the X scale of the Chart . For a bar chart the value 3.5 means that the X value is placed between the third and the fourth bar.

**· From**

Enter the starting point of the line here. If you do not enter a value, the Chart extends an existing line.

This way you can not only create horizontal and vertical lines but also diagonal lines.

For a horizontal line or for text this is an X value. For a vertical line this is a Y value.

**· To**

Enter the end point of the line here.

If you do not enter a value into the cells From and To , the Chart draws the line from the left to right, or from the top to the bottom of the display window.

For a horizontal line this is a X value. For a vertical line this is a Y value.

**· Color**

Enter the number of the color of the line here. Define colors on the Tab Color .

**· Style**

For lines of Type 0 or 1 , you can enter the line style.

For text of Type 4 , you can enter the marker style.

|   Value | Line style          | Marker style               |
|---------|---------------------|----------------------------|
|       0 | a thin solid line   | text only without a marker |
|       1 | a dashed line       | a plus sign                |
|       2 | a dotted line       | a cross                    |
|       3 | a dash-dot line     | a circle                   |
|       4 | a dash-dot-dot line | a filled circle            |

|   Value | Line style                | Marker style                  |
|---------|---------------------------|-------------------------------|
|       5 | a medium thin solid line  | a square                      |
|       6 | a thick solid line        | a filled square               |
|       7 | a grid tick               | a diamond                     |
|       8 | a grid line               | a filled diamond              |
|       9 | none                      | upward triangle               |
|      10 | a medium thick solid line | solid upward triangle         |
|      11 | an extra thick solid line | downward triangle             |
|      12 | none                      | solid downward triangle       |
|      13 | none                      | small plus                    |
|      14 | none                      | small cross                   |
|      15 | none                      | small circle                  |
|      16 | none                      | small solid circle            |
|      17 | none                      | small square                  |
|      18 | none                      | small solid square            |
|      19 | none                      | small diamond                 |
|      20 | none                      | small solid diamond           |
|      21 | none                      | small upward triangle         |
|      22 | none                      | small solid upward triangle   |
|      23 | none                      | small downward triangle       |
|      24 | none                      | small solid downward triangle |
|      25 | none                      | large plus                    |
|      26 | none                      | large cross                   |
|      27 | none                      | large circle                  |
|      28 | none                      | large solid circle            |
|      29 | none                      | large square                  |
|      30 | none                      | large solid square            |
|      31 | none                      | large diamond                 |
|      32 | none                      | large solid diamond           |
|      33 | none                      | large upward triangle         |

|   Value | Line style   | Marker style                  |
|---------|--------------|-------------------------------|
|      34 | none         | large solid upward triangle   |
|      35 | none         | large downward triangle       |
|      36 | none         | large solid downward triangle |
|      92 | none         | arrow north                   |
|      93 | none         | arrow north east              |
|      94 | none         | arrow east                    |
|      95 | none         | arrow south east              |
|      96 | none         | arrow south                   |
|      97 | none         | arrow south west              |
|      98 | none         | arrow west                    |
|      99 | none         | arrow north west              |

**· Text**

Enter any text that describes the line here. You can optionally enter the following two-character prefix codes, consisting of the pipe symbol ( | ) and a letter. These control at which position in the graph the text will be positioned:

| Prefix   | Position                        |
|----------|---------------------------------|
| &#124;l  | left inside edge of the graph   |
| &#124;L  | left outside edge of the graph  |
| &#124;r  | right inside edge of the graph  |
| &#124;R  | right outside edge of the graph |
| &#124;c  | centered inside of the graph    |

**Examples**

MyChart.Annotations := setAnnotations(myAnnotationTable)

```simtalk
-- Generation of a box plot for data with the discriptive statistics in tablefile 'StatisticData'
var AnnotationsTab:table;var Q0,Q25,Q50,Q75,Q100, yScaleMax, yScaleMin,delta, Mu:real;
var cNo:integer;var ValName:string
Chart.active := false
AnnotationsTab := Chart.Annotations;
AnnotationsTab.delete
yScaleMin := 1E300 -- all parts of the box plot must be visible
yScaleMax := 0
delta := 0.1 -- width of the column for the interval from the lower to the upper quartile (must be positive and < 0.5)
cNo := 3 -- blue, color for the intervals
Chart.title := "Box Plot"
for var ValNo := 1 to StatisticalData.xDim
	ValName := StatisticalData[ValNo, 0]
	Q0   := StatisticalData[ValNo, "Minimum"]
	Q25  := StatisticalData[ValNo, "Lower Quartile"]
	Q50  := StatisticalData[ValNo, "Median"]
	Q75  := StatisticalData[ValNo, "Upper Quartile"]
	Q100 := StatisticalData[ValNo, "Maximum"]
	Mu   := StatisticalData[ValNo, "Mean Value"]
	if Q0>Q25 OR Q25>Q50 OR Q50>Q75 OR Q75>Q100 OR Mu>Q100 OR Mu<Q0 Promptmessage(to_str("Invalid statistical data ", when strLen(ValName) < 1 then to_str("in column ",valNo) else to_str("for '",ValName,"'"),"."))
	end
	yScaleMax := max(yScaleMax,Q100)
	yScaleMin := min(yScaleMin,Q0)
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 0, ValNo,Q25,Q0,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 0, ValNo,Q100,Q75,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 0, ValNo + delta,Q25,Q75,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 0, ValNo delta,Q25,Q75,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 1, Q25, ValNo delta, ValNo + delta,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 1, Q50, ValNo delta, ValNo + delta,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 1, Q75, ValNo delta, ValNo + delta,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 1, Q0, ValNo delta, ValNo + delta,cNo,0 )
	AnnotationsTab.writeRow(1, AnnotationsTab.ydim + 1, 1, Q100, ValNo delta, ValNo + delta,cNo,0 )
next
delta := (Q100 - Q0)/10
Chart.yScaleMax := Q100 + delta
Chart.yScaleMin := Q0 - delta
Chart.active := true
```

**SimTalk**

getAnnotations [SimTalk]

**See also Annotations [button] Add Labels and a Legend**

##### setColor [SimTalk]

##### setColor [SimTalk]

Sets the Color of an item of the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setColor(ColorNo:integer, RGB:integer[, Opacity:integer])

**Parameters**

- The parameter ColorNumber of data type integer designates the color of the item.
- Grid (number -3)

Is the color the Chart uses for displaying the grid, i.e., the bounding rectangles, and the grid lines of the graph proper in the Chart window.

- Background (number -2) Is the color the Chart uses for displaying the background of the graph proper in the Chart window.
- Desk (number -1)

Is the color the Chart uses for displaying the area located outside the bounding rectangle of the graph's grid in the Chart window.

- Text (number 0)

Is the color the Chart uses for displaying text.

- Colors (numbers 1 through 14)

1 through 14 are the predefined colors of the input channels of the displayed data.

<!-- image -->

- The parameter RGB of data type integer designates the red, green, and blue component of this color.
- The optional parameter Opacity of data type integer designates the opacity of the color.

Enter 0 for an entirely transparent color, enter 255 for a completely opaque color. Semi-transparent colors will, for example, increase the readability of the Chart Type &gt; Area .

**Example**

```simtalk
MyChart.setColor(1, makeRGBValue(255,128,0))      -- sets the first color to orange
MyChart.setColor(2, makeRGBValue(255,0,0), 127))  -- sets the second color to a semi-transparent red
MyChart.setColor(-2, makeRGBValue(255,255,0))     -- sets the background color to yellow
```

**SimTalk**

getColor [SimTalk]

See also

Color [Chart]

##### setLineStyle [SimTalk]

setLineStyle [SimTalk]

Sets the settings of the line style of the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setLineStyle(ColorNumber:integer, LineStyle:string[, LineWeight:string, Marker:string])
```

**Parameters**

- The parameter ColorNumber of data type integer designates the Color .
- Grid (number -3 )

Is the color the Chart uses for displaying the grid, i.e., the bounding rectangles, and the grid lines of the graph proper in the Chart window.

- Background (number -2 )

Is the color the Chart uses for displaying the background of the graph proper in the Chart window.

- Desk (number -1 )

Is the color the Chart uses for displaying the area located outside the bounding rectangle of the graph's grid in the Chart window.

- Text (number 0 )

Is the color the Chart uses for displaying text.

- Colors (numbers 1 through 14 )

1 through 14 are the predefined colors of the input channels of the displayed data.

You can also add additional colors and define their properties to meet your modeling needs.

<!-- image -->

- The parameter LineStyle of data type string designates the Line Style .

You can also specify a shortened string to the method, which has to have a length of least three characters. You can, for example, specify ". ." or ". . ." instead of ". . . . . . . . ." to create a dotted line. You can also specify "\_ \_" instead of "\_ \_ \_ \_ \_ \_" to create a dashed line.

You can also specify minus signs instead of underscores, for example "- -" instead of underscores "\_ \_" .

- The optional parameter LineWeight of data type string designates the Line Weight . If you do not specify it, Plant Simulation keeps the previous LineWeight .
- The optional parameter Marker of data type string designates the Marker Type .

<!-- image -->

**Example**

<!-- image -->

**See also**

getLineStyle [SimTalk]

##### setWindowPosition [SimTalk] - Chart

Sets the position of the window of the Chart designated by &lt;Path&gt; and its width and height.

Type

Method

Syntax

```simtalk
< Path >.setWindowPosition(X:integer, Y:integer, Width:integer, Height:integer)
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the window.
- The parameter Y of data type integer designates its y-coordinate.
- The parameter Width of data type integer designates its width.
- The parameter Height of data type integer designates its height.

**Example**

MyChart.setWindowPosition(200,100,240,250)

##### showPrintDialog [SimTalk] - Chart

Opens the dialog Print of the Chart designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.showPrintDialog([Width:real, Height:real])
```

**Parameters**

- The optional parameter Width of data type real designates the width of the printed Chart in millimeters.
- The optional parameter Height of data type real designates the height of the printed Chart in millimeters.

**Example**

MyChart.showPrintDialog MyChart.showPrintDialog(140,120)

**See also**

Print [Chart]

update [SimTalk] - Chart

Refreshes the displayed Chart designated by &lt;Path&gt; with the current values.

Remarks

If the Chart is a Plotter in Sample mode, the method update has an additional effect, namely that a new data point is set, i.e., the Chart samples one more time, even then when the Chart is closed and the method returns false for this reason.

Type

Method

Syntax

&lt; Path &gt;.update -&gt; boolean

Return Value

The return value has the data type boolean .

true if the Chart is open.

false if it is closed.

Example

MyChart.update

See also

Mode [drop-down list] - Chart

#### Read-Only Attributes of the Chart

Read-Only Attributes of the Chart

The Chart provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyChart.UUID

#### Attributes of the Chart

\_Attributes of the Chart

The Chart provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyChart.DataRange := "{0,0}..{2,4}"
print MyChart.DataRange
posit := Station.Cont.XPos
```

##### Accumulated [SimTalk]

Sets if the Chart designated by &lt;Path&gt; creates an accumulated histogram ( true ) or not ( false ).

Remarks

Applies to the setting Category &gt; Histogram .

The accumulated histogram adds the sum of all previous values to each value. The last value thus is 100 percent.

Compare this example

| X Value                  |   1 |   2 |   3 |   4 |   5 |
|--------------------------|-----|-----|-----|-----|-----|
| Y Value, not accumulated |   0 |  25 |  30 |  23 |  12 |
| Y Value, accumulated     |  10 |  35 |  65 |  88 | 100 |

Type

Attribute

Syntax

&lt; Path &gt;.Accumulated:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.Accumulated := true
```

See also

Accumulated [check box] - Chart

Category [drop-down list]

##### Category [SimTalk]

Category [SimTalk]

Sets the Category that the Chart designated by &lt;Path&gt; displays.

Type

Attribute

Syntax

```simtalk
< Path >.Category:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Chart" , "Histogram" , "Plotter" , "3D Chart" , or "3D Histogram" .

Example

```simtalk
MyChart.Category := "Plotter"
```

See also

Category [drop-down list]

##### ChartType [SimTalk]

Sets the Chart Type that the Chart designated by &lt;Path&gt; displays.

Remarks

For the 3D Chart Types you can also set the Height and the Rotation .

Syntax

```simtalk
< Path >.ChartType:string
```

Assignment Value

You can assign a value of data type string .

<!-- image -->

**Example**

```simtalk
MyChart.ChartType := "Stacked Bars"
```

**See also**

Chart Type [drop-down list]

Rotation [SimTalk] - Chart

##### CollectData [SimTalk] - Chart

Sets if the Chart designated by &lt;Path&gt; of type Histogram or Plotter collects data ( true ) or does not collect data ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.CollectData:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.CollectData := true
```

See also

Collect Data [check box] - Chart

##### DataInColumn [SimTalk]

Sets if the Chart designated by &lt;Path&gt; shows the data in Columns ( true ) or in Rows ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.DataInColumn:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyChart.DataInColumn := true

See also

Data [Chart]

**DataRange [SimTalk]**

##### DataRange [SimTalk]

Sets the data range, which the objects table of the Chart designated by &lt;Path&gt; uses.

Remarks

The data range applies for these settings.

<!-- image -->

Type

Attribute

Syntax

```simtalk
< Path >.DataRange:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyChart.DataRange := "{*,*}..{*,*}    // no limitations MyChart.DataRange := "{1,1}..{1,4}"   // designates the first four rowns in the first column MyChart.DataRange := "{1,1}..{1,*}"   // designates the entire first column MyChart.DataRange := "{-2,*}..{-2,*}" // designates the one but last column DataTable MyChart.DataRange := "{-2,*}..{*,*}"  // designates the two last columns of the DataTable
```

**See also**

**Data Source [Chart]**

##### DataTable [SimTalk] - Chart

Sets the table containing the data, which the Chart designated by &lt;Path&gt; displays.

<!-- image -->

Type

Attribute

Syntax

```simtalk
< Path >.DataTable:object
```

Assignment Value

You can assign a value of data type object .

Example

```simtalk
MyChart.DataTable := DataTable
```

See also

Data Source [Chart]

##### DisplayInFrame [SimTalk]

Displays the contents of the Chart designated by &lt;Path&gt; in the Frame itself when you insert it into a Frame ( true ) or in its icon ( false ).

Remarks

If you assign true the attribute sets the resolution of the chart in the 3D window.

<!-- image -->

| Display in Frame On   | Display in Frame Off   |
|-----------------------|------------------------|

**Note**

If you set DisplayInFrame to true , you cannot freely combine line styles and line weights of the Chart .

Type

Attribute

Syntax

&lt; Path &gt;.DisplayInFrame:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyChart.DisplayInFrame := true

See also

Display in Frame [check box] - Chart Line Style Line Weight

##### Effect [SimTalk]

Sets the 3D effect for a number of Chart Types of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Effect:string
```

Assignment Value

You can assign a value of data type string .

You can specify "None" , "Shadow" , or "3D" .

Example

```simtalk
MyChart.Effect := "3D"
```

See also

Chart Type [drop-down list]

3D Effect

**FeedRate [SimTalk]**

##### FeedRate [SimTalk]

Sets the feed rate by which the Chart designated by &lt;Path&gt; scrolls, when it reached the right-hand side of the display.

Remarks

Applies for the setting Category &gt; Plotter .

Type

Attribute

Syntax

```simtalk
< Path >.FeedRate:real
```

Assignment Value

You can assign a value of data type real .

Specify 0.1 for smooth scrolling.

Specify 12 to scroll the entire page.

Example

```simtalk
MyChart.ScrollBar := true
MyChart.FeedRate := 4
```

SimTalk

ScrollBar [SimTalk]

See also

Feed Rate [text box]

Scrollbar [check box]

Category [drop-down list]

##### FirstInterval [SimTalk]

Sets the smallest value that the Histogram of the Chart designated by &lt;Path&gt; shows.

Type

Attribute

Syntax

&lt; Path &gt;.FirstInterval:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.FirstInterval := 2
```

See also

Range X

**GapWhenNull [SimTalk]**

##### GapWhenNull [SimTalk]

Sets if the Chart designated by &lt;Path&gt; interrupts the line it draws for values that are not defined ( true ) or if it continues drawing the line ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.GapWhenNull:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyChart.GapWhenNull := false

SimTalk

NullValue [SimTalk]

See also

Gap When Null [check box]

##### GraphTable [SimTalk]

Sets what the Chart designated by &lt;Path&gt; shows.

Type

Attribute

Syntax

```simtalk
< Path >.GraphTable:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Graph" , "Table" , or "Graph and Table" .

Example

```simtalk
MyChart.GraphTable := "Graph and Table"
```

See also

Graph/table [drop-down list]

##### Height [SimTalk] - 3D charts

Height [SimTalk] - 3D charts

Sets the height of the viewing angle for 3D Chart Types of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Height:integer
```

Assignment Value

You can assign a value of data type integer .

You can enter a number between -50 and 50 .

Example

```simtalk
MyChart.ChartType := "3D Columns"
MyChart.Height := 45
```

See also

Chart Type [drop-down list]

##### ImageQuality3D [SimTalk]

Sets the image quality with which the image of the Chart designated by &lt;Path&gt; is shown in the Frame .

Remarks

This applies if you assigned true to the attribute DisplayInFrame . Then you can select the 3D Image Quality with which the Chart shows the image in 3D. The 3D Image Quality is only active in a 3D model.

Type

Attribute

Syntax

&lt; Path &gt;.ImageQuality3D:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "High quality" results in high resolution and improved image quality with bad performance.
- "Balanced" results in medium resolution, is a good compromise between image quality and performance.
- "High performance" results in low resolution and bad image quality with better performance.

**Example**

MyChart.ImageQuality3D := "Balanced"

SimTalk

DisplayInFrame [SimTalk]

See also

3D Image Quality [drop-down list]

Display in Frame [check box] - Chart

##### InputChannels [SimTalk]

InputChannels [SimTalk]

Designates a table containing the definitions of all input channels of the Chart designated by &lt;Path&gt;.

Remarks

When you assign a table InputChannels with the assignment operator := , Plant Simulation deactivates inheritance.

Any other kind of writing access, as shown in the example above, does not deactivate inheritance. This means that one of these accesses changes the table which the input channels table shares with its origin.

Type

Attribute

Syntax

```simtalk
< Path >.InputChannels:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
MyChart.InputChannels.delete
MyChart.InputChannels.insertList(1,1,table.copy)
MyChart.Inputchannels := MyDataTable.copy({0,0}..{*,*})
print MyChart.InputChannels[1,1]
```

See also

Data Source [Chart]

IsShown [SimTalk] - Chart

Activates ( true ) or deactivates ( false ) the display of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.IsShown:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.IsShown := false
```

See also

Show Chart [button] - Chart

**LabelFont [SimTalk]**

##### LabelFont [SimTalk]

LabelFont and its sub-attribute set the properties of the Labels of the axes in the Chart designated by &lt;Path&gt;.

Remarks

**Note**

MS UI Gothic is intended for our Japanese users. The English or German version of Microsoft Windows might not provide this font by default.

Type

Attribute

Syntax

```simtalk
< Path >.LabelFont:string < Path >.LabelFont.Size:integer < Path >.LabelFont.Bold:boolean < Path >.LabelFont.Italic:boolean
```

Assignment Value

You can assign a value of data type string .

You can specify one of these fonts:

Arial

Arial Narrow

Comic Sans MS

Courier New

Haettenschweiler

Lucida Console

MS UI Gothic

Tahoma

Times New Roman

Trebuchet MS

Verdana

**Example**

```simtalk
MyChart.LabelFont:= "Tahoma"
```

**Size**

The sub-attribute Size , of data type integer , sets the font Size . You can enter a number between 1 and 8 .

**Example**

```simtalk
MyChart.LabelFont.Size := 4
```

**Bold**

The sub-attribute Bold , of data type boolean , sets if the Chart shows the labels in bold face ( true or not ( false ).

**Example**

```simtalk
MyChart.LabelFont.Bold := true
```

**Italic**

The sub-attribute Italic , of data type boolean , sets if the Chart shows the labels in italics ( true ) or not ( false ).

**Example**

```simtalk
MyChart.LabelFont.Italic := false
```

**See also**

**Labels [Chart]**

##### LegendLocation [SimTalk]

LegendLocation [SimTalk]

Sets the type and the position of the Legend which the Chart designated by &lt;Path&gt; shows.

Type

Attribute

Syntax

&lt; Path &gt;.LegendLocation:string

Assignment Value

You can assign a value of data type string .

**Example**

MyChart.LegendLocation := "Left"

**See also**

Legend , drop-down list

<!-- image -->

##### Mode [SimTalk] - Chart

Sets the mode with which the Chart designated by &lt;Path&gt; operates.

Remarks

This applies to the setting Category &gt; Histogram .

Type

Attribute

Syntax

```simtalk
< Path >.Mode:string
```

Assignment Value

You can assign a value of data type string .

You can specify.

- "Sample" mode updates the Chart regularly within a predefined period.
- "Watch" mode updates the Chart when the values to be displayed change.
- "Plot" mode updates the Chart whenever a simulation event takes place.

**Example**

```simtalk
Mode.Sampler := "Plot"
```

See also

Mode [drop-down list] - Chart

Category [SimTalk]

##### NullValue [SimTalk]

NullValue [SimTalk]

Sets the value the Chart designated by &lt;Path&gt; takes to be as an undefined value.

Remarks

When a point takes this value, the Chart does not display it.

The default value is -999999.

Type

Attribute

Syntax

```simtalk
< Path >.NullValue:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyChart.NullValue := -1
```

See also

GapWhenNull [SimTalk]

##### NumIntervals [SimTalk]

Sets into how many intervals the Chart designated by &lt;Path&gt; divides the frequency distribution for a Histogram .

Type

Attribute

Syntax

```simtalk
< Path >.NumIntervals:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.NumIntervals := 8
```

See also

Range X

**NumValues [SimTalk]**

##### NumValues [SimTalk]

Sets the number of values which the Chart designated by &lt;Path&gt; collects over time per channel.

Remarks

Note

This applies to the setting Category &gt; Plotter .

The more values the Chart collects, the more memory Plant Simulation uses.

Type

Attribute

Syntax

&lt; Path &gt;.NumValues:integer

Assignment Value

You can assign a value of data type integer .

Example

MyChart.NumValues := 5000

See also

Number of Values [text box]

Category [SimTalk]

Rotation [SimTalk] - Chart

Sets the angle of rotation for 3D Chart Types of the Chart designated by &lt;Path&gt; in degrees.

Type

Attribute

Syntax

```simtalk
< Path >.Rotation:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.ChartType := "3D Columns"
MyChart.Rotation := 90
```

See also

Chart Type [drop-down list]

##### SampleInterval [SimTalk]

SampleInterval [SimTalk]

Sets the period of time between two successive sampling actions for the Chart designated by &lt;Path&gt; for Sample mode.

Type

Attribute

Syntax

< Path >.SampleInterval:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyChart.SampleInterval := 3600
MyChart.sampleInterval := 0 // Prevents the Chart from being updated. // To update values, use the method 'update'.
```

See also

Mode [drop-down list] - Chart

##### ScrollBar [SimTalk]

Sets if the Chart designated by &lt;Path&gt; shows a scrollbar ( true ) or not ( false ).

Remarks

This applies to the setting Category &gt; Plotter .

Type

Attribute

Syntax

```simtalk
< Path >.ScrollBar:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.ScrollBar := true
MyChart.FeedRate := 4
```

SimTalk

FeedRate [SimTalk]

See also

Scrollbar [check box]

Feed Rate [text box]

Category [SimTalk]

**SizeInFrame [SimTalk]**

##### SizeInFrame [SimTalk]

Sets the Width and the Height of the Chart designated by &lt;Path&gt; in length units when it is shown in the Frame .

Type

Attribute

Syntax

< Path >.SizeInFrame:array[2]

Assignment Value

You can assign a value of data type array with two values of data types integer .

Example

```simtalk
MyChart.SizeInFrame := [6, 4.5]
```

See also

Width [text box] - display in frame

Height [text box] - display in frame StepCurve [SimTalk]

Sets if the Chart designated by &lt;Path&gt; creates a step curve ( true ) or not ( false ).

Remarks

Applies to the Category &gt; Plotter .

Type

Attribute

Syntax

&lt; Path &gt;.StepCurve:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.StepCurve := true
```

See also

Step Curve [check box]

Category [drop-down list]

##### StepSize [SimTalk]

StepSize [SimTalk]

Sets the width of the intervals into which the Chart designated by &lt;Path&gt; divides the frequency distribution.

Remarks

Applies to the Category &gt; Histogram .

Type

Attribute

Syntax

```simtalk
< Path >.StepSize:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyChart.StepSize := 5
```

See also

Step Size [text box]

Category [drop-down list]

##### SubTitle [SimTalk]

Sets the Subtitle which the Chart designated by &lt;Path&gt; displays in the Chart window.

Type

Attribute

Syntax

```simtalk
< Path >.SubTitle:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyChart.SubTitle := "line 1, block"
```

See also

Subtitle [font] - Chart

**SubtitleFont [SimTalk]**

##### SubtitleFont [SimTalk]

SubtitleFont and its sub-attributes set the properties of the Subtitle in the Chart window of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.SubtitleFont:string < Path >.SubtitleFont.Bold:boolean < Path >.SubtitleFont.Italic:boolean
```

**Assignment Value**

You can assign a value of data type string .

You can specify the name of one of these fonts:

Arial

Arial Narrow

Comic Sans MS

Courier New

Haettenschweiler

Lucida Console

MS UI Gothic

Tahoma

Times New Roman

Trebuchet MS

Verdana

**Note**

MS UI Gothic is intended for our Japanese users. The English or German version of Microsoft Windows might not provide this font by default.

**Example**

```simtalk
MyChart.SubtitleFont:= "Verdana"
```

**Bold**

The sub-attribute Bold , of data type boolean , sets if the Chart shows the subtitle in bold face ( true ) or not ( false ).

**Example**

```simtalk
MyChart.SubtitleFont.Bold := true
```

Italic

The sub-attribute Italic , of data type boolean , sets if the Chart shows the subtitle in italics ( true ) or not ( false ).

**Example**

```simtalk
MyChart.SubtitleFont.Italic := false
```

**See also**

Subtitle [font] - Chart

**TableFont [SimTalk]**

##### TableFont [SimTalk]

TableFont and its sub-attributes set the properties of the labels which the Chart designated by &lt;Path&gt; shows as a Table in the Chart window.

Remarks

**Note**

MS UI Gothic is intended for our Japanese users. The English or German version of Microsoft Windows might not provide this font by default.

Type

Attribute

Syntax

```simtalk
< Path >.TableFont:string < Path >.TableFont.Size:integer
```

**Example**

```simtalk
MyChart.TableFont:= "Tahoma"
```

Size

The sub-attribute Size , of data type integer , sets the font size .

You can specify a number between 1 and 8 .

Assignment Value

You can assign a value of data type string .

You can specify the name of one of these fonts:

| Arial            |
|------------------|
| Arial Narrow     |
| Comic Sans MS    |
| Courier New      |
| Haettenschweiler |

| Lucida Console   |
|------------------|
| MS UI Gothic     |
| Tahoma           |
| Times New Roman  |
| Trebuchet MS     |
| Verdana          |

**Example**

MyChart.TableFont.Size := 4

**See also**

Table [font] - Chart

Labels [Chart]

##### Title [SimTalk]

Title [SimTalk]

Sets the Title which the Chart designated by &lt;Path&gt; shows in the Chart window.

Type

Attribute

Syntax

```simtalk
< Path >.Title:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyChart.Title := "Engine assembly"
```

See also

Title [font] - Chart

##### TitleFont [SimTalk]

The attribute TitleFont and its sub-attributes set the properties of the Title in the Chart window of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.TitleFont:string < Path >.TitleFont.Size:integer < Path >.TitleFont.Bold:boolean < Path >.TitleFont.Italic:boolean
```

**Assignment Value**

You can assign a value of data type string .

You can specify one of these fonts:

| Arial            |
|------------------|
| Arial Narrow     |
| Comic Sans MS    |
| Courier New      |
| Haettenschweiler |
| Lucida Console   |
| MS UI Gothic     |
| Tahoma           |
| Times New Roman  |
| Trebuchet MS     |
| Verdana          |

**Note**

MS UI Gothic is intended for our Japanese users. The English or German version of Microsoft Windows might not provide this font by default.

**TitleFont [SimTalk]**

**Example**

```simtalk
MyChart.TitleFont:= "Trebuchet MS"
```

**Size**

The sub-attribute Size , of data type integer , sets the font Size . You can enter a number between 1 and 8 .

**Example**

```simtalk
MyChart.TitleFont.Size := 4
```

**Bold**

The sub-attribute Bold , of data type boolean , sets if the Chart shows the title in bold face ( true ) or not ( false ).

**Example**

```simtalk
MyChart.TitleFont.Bold := true
```

**Italic**

The sub-attribute Italic , of data type boolean , sets if the Chart shows the title in italics ( true ) or not ( false ).

**Example**

```simtalk
MyChart.TitleFont.Italic := false
```

**See also**

Title [font] - Chart

##### UseInputChannels [SimTalk]

Sets if the Chart designated by &lt;Path&gt; takes data it displays from input channels ( true ) or from a DataTable you defined ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.UseInputChannels:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyChart.UseInputChannels := true

See also

Data Source [Chart]

**UseMetricPrefix [SimTalk]**

##### UseMetricPrefix [SimTalk]

Sets if the Chart designated by &lt;Path&gt; shows a unit prefix on the y-axis for very great or very small values, for example 100K instead of 100000, ( true ) or not ( false ).

**Remarks**

| The prefix   | stands for   |
|--------------|--------------|
| p            | pico         |
| n            | nano         |
| u            | micro        |
| m            | milli        |
| K            | kilo         |
| M            | million      |
| B            | billion      |
| T            | trillion     |

Type

Attribute

Syntax

&lt; Path &gt;.UseMetricPrefix:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.UseMetricPrefix := true
```

See also

Use Metric Prefix [command]

##### XGrid [SimTalk]

Sets if the Chart designated by &lt;Path&gt; shows the grid on the x-axis in the Chart window ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.XGrid:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.XGrid := true
```

See also

Grid Lines X-Axis

**XGridlines [SimTalk]**

##### XGridlines [SimTalk]

Sets the number of grid lines that the Chart designated by &lt;Path&gt; shows on the x-axis.

Remarks

The Chart also shows a label for each grid line on the x-axis. If you are displaying a large number of data sets, it makes sense to enter a smaller number so that the labels can be shown completely.

If the number of grid lines is greater than the number of data sets on the x-axis, the Chart only shows as many grid lines as there are data sets. If the number of grid lines is smaller than the number of data sets, the Chart reduces the number of grid lines and labels.

**Note**

If you select the Category &gt; XY-Graph , the Chart only evaluates the Number if you also enter a fixed Range X , i.e., if you did not enter an asterisk * .

Type

Attribute

Syntax

```simtalk
< Path >.XGridlines:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.XGridlines := 10
```

See also

Number of grid lines

Category [drop-down list]

Range X

##### XLabel [SimTalk]

Sets the label of the x-axis which the Chart designated by &lt;Path&gt; shows in the Chart window.

Remarks

Applies to the 3D chart types 3D Columns , 3D Wire Frame , and 3D Surface .

Type

Attribute

Syntax

&lt; Path &gt;.XLabel:string

Assignment Value

You can assign a value of data type string .

Example

MyChart.XLabel := "Month"

SimTalk

YLabel [SimTalk]

See also

X-Axis [text box] - Chart

**XLog [SimTalk]**

##### XLog [SimTalk]

Sets if the x-axis of the Chart designated by &lt;Path&gt; uses a logarithmic representation ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.XLog:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.XLog := true
```

SimTalk

YLog [SimTalk]

See also

Logarithmic X-Axis

##### XRange [SimTalk]

Sets the time span, in seconds of simulation time, which the Chart designated by &lt;Path&gt; shows in the display.

Remarks

Applies to the Category &gt; Plotter .

Type

Attribute

Syntax

< Path >.XRange:time

Assignment Value

You can assign a value of data type time .

Example

MyChart.XRange := 3600

See also

Range X

Category [drop-down list]

##### XScaleMax [SimTalk]

XScaleMax [SimTalk]

Sets the upper bound for scaling on the x-axis of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.XScaleMax:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.XScaleMax := 3
```

SimTalk

XScaleMin [SimTalk]

See also

Range X

##### XScaleMin [SimTalk]

Sets the lower bound for scaling on the x-axis of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.XScaleMin:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.XScaleMin := 2
```

SimTalk

XScaleMax [SimTalk]

See also

Range X

**YGrid [SimTalk]**

##### YGrid [SimTalk]

Sets if the Chart designated by &lt;Path&gt; shows the grid on the y-axis in the Chart ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.YGrid:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.YGrid := false
```

SimTalk

XGrid [SimTalk]

See also

Grid Lines Y-Axis

##### YGridLineInterval [SimTalk]

Sets the interval between the grid lines on the y-axis of the Chart designated by &lt;Path&gt;.

Remarks

YGridLineInterval sets the distance of the horizontal grid lines and the labels on the y-axis.

Specify 0 to make Plant Simulation determine a meaningful interval based on the displayed values.

Type

Attribute

Syntax

&lt; Path &gt;.YGridLineInterval:real

**Assignment Value**

You can assign a value of data type real .

Example

MyChart.YGridLineInterval := 2

See also

Interval

##### YLabel [SimTalk]

YLabel [SimTalk]

Sets the label of the y-axis that the Chart designated by &lt;Path&gt; shows in the Chart window.

Remarks

Applies to the 3D chart types 3D Columns , 3D Wire Frame , and 3D Surface .

Type

Attribute

Syntax

&lt; Path &gt;.YLabel:string

Assignment Value

You can assign a value of data type string .

Example

MyChart.YLabel := "Number of Trunks"

SimTalk

XLabel [SimTalk]

See also

Y-Axis [text box] - Chart

##### YLog [SimTalk]

Activates logarithmic representation ( true ) of the y-axis of the Chart designated by &lt;Path&gt; or deactivates it ( false ).

Remarks

If you activate YLog , you also have to enter a value greater than 0 , for example 0.1 , for the YScaleMin , so that Plant Simulation can display the scale logarithmically.

Type

Attribute

Syntax

```simtalk
< Path >.YLog:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyChart.YLog := false
```

SimTalk

XLog [SimTalk]

See also

Logarithmic Y-axis

YScaleMin [SimTalk]

##### YScaleMax [SimTalk]

YScaleMax [SimTalk]

Sets the upper bound of the range on the y-axis of the Chart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.YScaleMax:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.YScaleMax := 1.5
```

SimTalk

YScaleMin [SimTalk]

See also

Range Y

##### YScaleMin [SimTalk]

Sets the lower bound of the range on the y-axis of the Chart designated by &lt;Path&gt;.

Remarks

If you activate YLog , you also have to enter a value greater than 0 , for example 0.1 , for the YScaleMin , so that Plant Simulation can display the scale logarithmically.

Type

Attribute

Syntax

```simtalk
< Path >.YScaleMin:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyChart.YScaleMin := 0.5
```

SimTalk

YScaleMax [SimTalk]

See also

Range Y

**ZLabel [SimTalk]**

##### ZLabel [SimTalk]

Sets the label of the z-axis that the Chart designated by &lt;Path&gt; shows in the Chart window.

Remarks

Applies to the 3D chart types 3D Columns , 3D Wire Frame , and 3D Surface .

Type

Attribute

Syntax

```simtalk
< Path >.ZLabel:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyChart.ZLabel := "Number of Stacked Rows"
```

See also

Z-Axis [text box] - Chart

