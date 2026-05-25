### GanttChart

#### GanttChart [object]

Use the GanttChart for showing the chronological sequence of activities as bars on the time axis.

Icon

<!-- image -->

Description

The GanttChart visualizes parts on resources. In this context resources are the material flow objects , not the resource objects .

<!-- image -->

In addition to the mere occupancy data, the GanttChart can also display failures of machines, pausing times, and blocking times.

This way the GanttChart immediately shows which machines or stations are overloaded or have a low utilization and which production orders or products have long waiting times during the production process.

To show a tooltip with information about the GanttChart , hover with the mouse over it.

To change the length of the graphic and the anchor points of the GanttChart , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the GanttChart to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; GanttChart on the Home ribbon tab.

<!-- image -->

<!-- image -->

**Note**

The object GanttChart is not part of the Plant Simulation standard program package.

**Note**

If you are using the GanttChart , replace the GanttChart of previous versions with the GanttChart of the current version.

Adjust the source code, which you programmed in SimTalk of previous versions, to the current version, compare Methods of the GanttChart and Attributes of the GanttChart .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Show Parts on Resources in a GanttChart

#### Dialog Box of the GanttChart

Dialog Box of the GanttChart

Double-click the icon of the GanttChart to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Show Chart [button] - GanttChart

##### Collect Data [check box] - Chart

**Collect Data [check box] - GanttChart**

##### Collect Data [check box] - GanttChart

To make the GanttChart collect data during the simulation run, select this check box.

<!-- image -->

Note

You cannot use setData and automatically collect the data simultaneously. When you select Collect Data , do not call the method setData .

To deactivate data collection, clear the check box.

SimTalk

CollectData [SimTalk] - GanttChart

##### Show Chart [button] - GanttChart

To show the data, which the GanttChart collected in the display window, click this button.

<!-- image -->

Define how the GanttChart shows the collected data on the tab Attributes .

<!-- image -->

The GanttChart provides two views:

**Resource View**

Resource View shows the resources which are occupied by the parts. The GanttChart shows the resources along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the resources in the order in which they processed parts for the first time. The resource, which processed a part first, is shown in the first lane in the chart. The resource, which processed a part after that, is shown in the lane below, etc.

You cannot change the order of the resources.

<!-- image -->

With the default settings the GanttChart shows a part on all resources with the same color.

Part View

Part View shows the parts which occupy the resources. The GanttChart shows the parts along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the parts in the order in which they were processed by a resource for the first time. The part, which was processed by a resource first, is shown in the first lane in the chart. The part, which was processed by a resource after that, is shown in the lane below, etc.

You cannot change the order of the parts.

<!-- image -->

With the default settings the GanttChart shows a resource for all parts with the same color.

The displayed resource states refer to the resource which is currently occupied by the displayed part.

<!-- image -->

Show Longer or Shorter Time Intervals

To show longer time intervals, hold down Ctrl and press the -key or roll the mouse wheel backward. This zooms the view in.

To show shorter time intervals, hold down Ctrl and press the + key or roll the mouse wheel forward. This zooms the view out.

To change the displayed time intervals in greater steps , hold down Shift in addition to Ctrl .

To return to the default zoom factor , hold down Ctrl and press the 0 key.

SimTalk

IsShown [SimTalk] - GanttChart

##### Tab Attributes

<!-- image -->

##### Tab Attributes

Tab Attributes [GanttChart]

Set how the GanttChart shows the data it collected on the tab Attributes .

<!-- image -->

**You can:**

- Select the View Mode , i.e., if the GanttChart displays data in the Resource view or the Part view .
- Select to Show Resource Labels [check box] or to hide them.
- Select to Show Bar Text [check box] or to hide it.
- Select to Show Resource States [check box] or to hide them.
- Edit Lanes on which the Gantt data is shown.

###### View Mode

Select the View Mode with which the GanttChart shows the Gantt data .

<!-- image -->

- Resource View shows the resources which are occupied by the parts. The GanttChart shows the resources along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the resources in the order in which they processed parts for the first time. The resource, which processed a part first, is shown in the first lane in the chart. The resource, which processed a part after that, is shown in the lane below, etc.

You cannot change the order of the resources.

<!-- image -->

For parts being transported by a Transporter or carried by a Worker , Resource View shows the Transporter or the Worker as the resource instead of the Track or the Footpath .

With the default settings the GanttChart shows a part on all resources with the same color.

- Part View shows the parts which occupy the resources. The GanttChart shows the parts along the vertical axis and the elapsing time along the horizontal axis.

**Note**

The GanttChart shows the parts in the order in which they were processed by a resource for the first time. The part, which was processed by a resource first, is shown in the first lane in the chart. The part, which was processed by a resource after that, is shown in the lane below, etc.

You cannot change the order of the parts.

<!-- image -->

With the default settings the GanttChart shows a resource for all parts with the same color.

You can select the respective view mode on the drop-down list or on the context menu.

The displayed resource states refer to the resource which is currently occupied by the displayed part.

<!-- image -->

You can adjust the timescale of the GanttChart by holding down Ctrl while rolling the mouse wheel:

- Hold down Ctrl and roll the mouse forward to show shorter time intervals. This shows additional details of the displayed data.
- Hold down Ctrl and roll the mouse backward to show shorter time intervals. This shows a rough overview of the data.

When you roll the mouse over a bar, Resource View highlights the respective part on all resources. Part View highlights the respective resource for all parts.

This way you can follow the way of the part across the simulation.

In Resource View the Tooltip shows the name of the part, its absolute path , the start date , the end date , and the duration .

<!-- image -->

If several parts are located on the same station, the Tooltip shows information about these parts. The part that moved last onto the station is located at the top of the list.

<!-- image -->

In Part View the Tooltip shows the name of the part, the occupied resource , the start date , the end date , and the duration .

<!-- image -->

Resource View refreshes the display of the GanttChart continuously during the simulation.

You have to manually refresh Part View by pressing F5 or by selecting the context menu command Refresh .

To show the labels of the resource objects instead of their names in the column to the left, use Show Resource Labels .

**View Mode**

To show or hide the Gantt bar text of the resources, use Show Bar Text . The Gantt bar texts can overlap.

To show or hide the resource states, use Show Resource States .

To set the distance of the Gantt bars to the top and the height of the bars , use Edit Lanes .

To set if the GanttChart shows the parts which occupy resources in Part View or the occupied resources in Resource View , use the attribute ShowPartView .

SimTalk

ShowPartView [SimTalk]

See also

setData [SimTalk]

getData [SimTalk]

setLanes [SimTalk]

getLanes [SimTalk]

###### Show Resource Labels [check box]

To show the labels of the resources , select this check box.

<!-- image -->

<!-- image -->

To hide the labels of the resources and to show the names of the resources instead, clear the check box.

<!-- image -->

**SimTalk**

ShowResourceLabels [SimTalk]

###### Show Bar Text [check box]

Show Bar Text [check box]

To show the text on the Gantt bars , select this check box.

<!-- image -->

Bar texts can overlap. The bar text shows the name of the part.

<!-- image -->

To hide the bar text of the resource, clear the check box.

<!-- image -->

**SimTalk**

**ShowBarText [SimTalk]**

###### Show Resource States [check box]

To show the states of the resources as colored bars below the timeline, select this check box.

<!-- image -->

The colors of the parts are the same as the LED colors of the objects, compare LEDs and States of the Material Flow Objects .

<!-- image -->

To hide them, clear the check box.

<!-- image -->

**SimTalk**

ShowResourceStates [SimTalk]

**Edit Lanes**

###### Edit Lanes

Click Edit Lanes and enter the distance of the Gantt bars to the top and the height of the bars themselves .

<!-- image -->

<!-- image -->

To apply the changed values, click Apply in the dialog getLanes and then Apply in the dialog of the GanttChart .

<!-- image -->

The GanttChart always collects data in lane 1. Specify your own data with the method setData to distribute them across several lanes.

SimTalk setLanes [SimTalk] getLanes [SimTalk] setData [SimTalk]

##### Tab Parts [GanttChart]

###### Tab Parts [GanttChart]

Add the parts that the GanttChart is to display on the tab Parts .

First, clear the check box Inheritance so that it is looks like this . Then drag the part types, which you would like to watch, from the Class Library to an empty row on the tab.

<!-- image -->

Instead, you can also select the part in the Class Library , drag it on the icon of the GanttChart , and drop it there. This automatically deactivates inheritance and adds the part to an empty row on the tab Parts .

You can watch classes of parts or individual instances of parts.

You can edit the content of the text boxes with the commands on the Context Menu of Embedded Lists .

SimTalk

Parts [SimTalk]

##### Tab Resources [GanttChart]

Add the resources that the GanttChart is to display on the tab Resources .

The GanttChart considers the material flow objects as resources, not the resource objects .

If you want to watch all resources in the simulation model, leave the tab Resources empty. The GanttChart then shows all resources on which parts, which you set on the tab Parts , move during the simulation.

First, clear the check box Inheritance so that it is looks like this . Then drag the resource types, which you would like to watch, from the Class Library to an empty row on the tab.

Instead, you can also select one or several resources in the Frame , drag it/them on the icon of the GanttChart , and drop it/them there. This automatically deactivates inheritance and adds the resources to an empty row each on the tab Resources .

<!-- image -->

You can watch resource classes or individual resource instances.

You can edit the content of the text boxes with the commands on the Context Menu of Embedded Lists .

**SimTalk**

Resources [SimTalk] - GanttChart

ShowResourceLabels [SimTalk]

ShowResourceLabels [SimTalk]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

##### Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

**Methods of the GanttChart**

#### \_Methods of the GanttChart

The GanttChart provides:

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

**exportChart [SimTalk]**

##### exportChart [SimTalk]

Exports the GanttChart designated by &lt;Path&gt; to an HTML file.

Type

Method

Syntax

```simtalk
< Path >.exportChart(FileName:string[, TimeScale:real])
```

**Parameters**

- The parameter FileName of data type table designates the table into which Plant Simulation writes the HTML file.
- The optional parameter TimeScale of data type real designates the time scale. The time scale is shown in pixels per second.
- For the value of 0.5 a Gantt event that has a duration of 60 seconds is displayed by a bar of a length of 30 pixels.

**Examples**

MyGanttChart.exportChart("MyExportedGanttChart.html", 0.5)

// exports the file to the folder in which the simulation model is located

MyGanttChart.exportChart("D:\MyModels\MyExportedGanttChart.html") // exports the file to the designated folder

##### getData [SimTalk]

Returns the data which the GanttChart designated by &lt;Path&gt; shows and writes it to a table.

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getData(DataTable:table)

Parameter

The parameter DataTable of data type table designates the table into which Plant Simulation writes data that the GanttChart shows.

The format of the data table is described under setData .

Example

MyGanttChart.getData(MyGanttDataTable)

SimTalk

setData [SimTalk]

##### getHTMLCode [SimTalk] - GanttChart

getHTMLCode [SimTalk] - GanttChart

Returns the chart graphic as HTML code in the format SVG of the GanttChart designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getHTMLCode([Caption:string, Scale:real]) → string
```

**Parameters**

- The optional parameter Caption of data type string designates the desired caption of the graphic. Specify the caption to show the GanttChart with this caption.
- The optional parameter Scale of data type real designates the scaling of the graphic.

Return Value

The return value has the data type string .

Example

```simtalk
HtmlReport.content := "<<" + GanttChart.getHtmlCode("Test (half size)", 0.5) + ">>"
HtmlReport.show
```

**See also**

Display a HtmlReport

##### getLanes [SimTalk]

Returns the lanes which you defined for the GanttChart designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getLanes(TableToWrite:table)

Parameter

The parameter TableToWrite of data type table designates the table into which Plant Simulation writes lanes of the GanttChart .

A lane is defined by the settings Top and Height . Both have the data type integer .

<!-- image -->

**Example**

MyGanttChart.getLanes(MyLanesTable)

SimTalk

setLanes [SimTalk]

See also

Edit Lanes

**setData [SimTalk]**

##### setData [SimTalk]

Sets the data which the GanttChart designated by &lt;Path&gt; is going to show.

Remarks

You cannot manually set the data and automatically collect the data simultaneously. When you use the method setData , set CollectData to false .

Type

Method

Syntax

&lt; Path &gt;.setData(DataTable:table)

**Parameter**

The parameter DataTable of data type table designates the table that contains the data which the GanttChart is going to show.

The table has eight columns. The figure below shows the data types of the columns. The first three columns have to contain data. Of the second three columns one column at least has to contain data.

<!-- image -->

Each row in the table describes a Gantt event that is visualized as a bar.

- Start Date denotes the start date of the event.

- End Date denotes the end date of the event.
- Resource . Depending on the data of the following three columns Resource either denotes the resource that takes the specified state, or the specified part, or both. You can type in the path of the resource in the Frame or you can drag the resource on the respective cell and drop it there, or enter free resource text.
- Resource State denotes the state in which the Resource is. You can enter one of these states: Working , Setting-up , Waiting , Blocked , PoweringUpDown , Failed , Stopped , Paused , or Unplanned . The value does not have to correspond to any existing material flow instance.
- Part denotes the part that is processed by the resource. Type in the path of the parts class, a colon, and the number of the part instance. You can, for example, enter .MUs.Part:1 . Instead, you can also enter free part text.
- Part Name is any string that the GanttChart shows as a Tooltip .
- Lane denotes the lane of the Gantt event.
- Color denotes the color of the Gantt event. If you do not enter a color, Plant Simulation automatically assigns a color, in Resource View according to the part, in Part View according to the resource.

**Example**

MyGanttChart.setData(MyGanttData)

SimTalk

getData [SimTalk]

setLanes [SimTalk]

See also

Show Chart [button] - GanttChart

CollectData [SimTalk] - GanttChart

**setLanes [SimTalk]**

##### setLanes [SimTalk]

Sets the lanes which the GanttChart designated by &lt;Path&gt; is to show.

Type

Method

Syntax

&lt; Path &gt;.setLanes(TableToRead:table)

**Parameter**

The parameter TableToRead of data type table designates the table which contains the lanes that the GanttChart shows.

A lane is defined by the settings Top and Height . Both have the data type integer .

<!-- image -->

**Example**

```simtalk
MyGanttChart.setLanes(MyLanesTable)
MyGanttChart.ShowResourceStates := true
```

**SimTalk**

getLanes [SimTalk]

Edit Lanes

See also

Show Chart [button] - GanttChart

##### update [SimTalk] - GanttChart

Refreshes the displayed GanttChart designated by &lt;Path&gt; with the current values.

Type

Method

Syntax

Path .update

Example

MyGanttChart.update

#### Read-Only Attributes of the GanttChart

Read-Only Attributes of the GanttChart

The GanttChart provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyGanttChart.UUID
```

#### Attributes of the GanttChart

##### \_Attributes of the GanttChart

The GanttChart provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyGanttChart.IsShown := true
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyGanttChart.IsShown
posit := Station.Cont.XPos
```

CollectData [SimTalk] - GanttChart

Sets if the GanttChart designated by &lt;Path&gt; collects data ( true ) or does not collect data ( false ).

Remarks

You cannot use setData and automatically collect the data simultaneously. When you assign true to CollectData , do not call the method setData .

Type

Attribute

Syntax

```simtalk
< Path >.CollectData:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyGanttChart.CollectData := true
```

SimTalk

setData [SimTalk]

See also

Collect Data [check box] - GanttChart

##### EnableVisualTracking [SimTalk]

Activates ( true ) or deactivates ( false ) visual tracking of parts or resources in the GanttChart designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EnableVisualTracking:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyGanttChart.EnableVisualTracking := true

See also

Show Chart [button] - GanttChart

##### IsShown [SimTalk] - GanttChart

IsShown [SimTalk] - GanttChart

Activates ( true ) or deactivates ( false ) the display of the GanttChart designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.IsShown:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyGanttChart.IsShown := false
```

See also

Show Chart [button] - GanttChart

##### NumVisibleBars [SimTalk]

Sets the maximum number of visible bars in the GanttChart designated by &lt;Path&gt;.

Remarks

The default setting is 100000. If this number is exceeded, older bars will not be shown any more.

You can reduce this number if performance is impaired.

Type

Attribute

Syntax

&lt; Path &gt;.NumVisibleBars:integer

**Assignment Value**

You can assign a value of data type integer .

Example

MyGanttChart.NumVisibleBars := 8000

See also

Show Chart [button] - GanttChart

**Parts [SimTalk]**

##### Parts [SimTalk]

Sets the parts, i.e., the MUs that the GanttChart designated by &lt;Path&gt; visualizes.

Remarks

You can watch classes of parts or you can watch individual instances of parts.

Type

Attribute

Syntax

< Path >.Parts:array

Assignment Value

You can assign a value of data type array .

Example

```simtalk
MyGanttChart.Parts := [*.MUs.Entity]   // all parts of this class
MyGanttChart.Parts := [*.MUs.Entity:1] // the part with the number 1
```

See also

Tab Parts [GanttChart]

##### Resources [SimTalk] - GanttChart

Sets the resources, i.e., the material flow objects that the GanttChart designated by &lt;Path&gt; visualizes.

Remarks

You can watch classes of resources or you can watch individual instances of resources.

Type

Attribute

Syntax

&lt; Path &gt;.Resources:array

Assignment Value

You can assign a value of data type array .

Example

MyGanttChart.Resources := [Source, Station, Station1, Drain]

See also

Tab Resources [GanttChart]

##### ShowBarText [SimTalk]

ShowBarText [SimTalk]

Sets if the GanttChart designated by &lt;Path&gt; shows the part name as text on the Gantt bar ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowBarText:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyGanttChart.ShowBarText := true

See also

Show Bar Text [check box]

##### ShowPartView [SimTalk]

Sets if the GanttChart designated by &lt;Path&gt; shows the resources in the Resource View ( false ) or the parts in the Part View ( true ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowPartView:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyGanttChart.ShowPartView := true

See also

Show Chart [button] - GanttChart

##### ShowResourceLabels [SimTalk]

Sets if the GanttChart designated by &lt;Path&gt; shows the labels of the resources ( true ) or their names ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowResourceLabels:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyGanttChart.ShowResourceLabels := true

See also

Show Resource Labels [check box]

##### ShowResourceStates [SimTalk]

Sets if the GanttChart designated by &lt;Path&gt; shows the states of the resources as color of the bars ( true ) or not ( false ).

Remarks

Attribute

Type

The colors of the parts are the same as the LED colors of the objects.

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyGanttChart.setLanes(MyLanesTable)
MyGanttChart.ShowResourceStates := true
```

See also

Show Resource States [check box]

LEDs and States of the Material Flow Objects in 2D

**TimeScale [SimTalk]**

##### TimeScale [SimTalk]

Sets the time scale of the GanttChart designated by &lt;Path&gt;. Plant Simulation applies this value when opening the GanttChart .

Remarks

The unit of the time scale is logical pixels per second. For a time scale of 0.5 Plant Simulation shows a Gantt event with a duration of 60 seconds with a bar of a length of 30 logical pixels.

Type

Attribute

Syntax

&lt; Path &gt;.TimeScale:integer

Assignment Value

You can assign a value of data type real .

Specify 0 to use the default time scaling.

Example

```simtalk
MyGanttChart.TimeScale := 2.5
```

See also

Show Chart [button] - GanttChart

