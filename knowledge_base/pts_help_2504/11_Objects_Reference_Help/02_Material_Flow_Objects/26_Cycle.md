### Cycle

Use the Cycle for synchronizing the transfer of parts from station to station.

**Icon**

<!-- image -->

**Description**

Use the Cycle to only move a part on to the next station within a balanced line, when all stations have finished processing their parts and when none of the stations is failed, paused, or unplanned. In addition, the successor of the balanced line has to be ready to receive the part. To define the balanced line, type the name of the First Station and of the Last Station into the text boxes. All stations between the first and the last station, which are connected with Connectors , form the balanced line. Each station has to have a predecessor and a successor and can only have a single predecessor and a single successor.

**Note**

At the moment only objects of type Station and AssemblyStation can be part of the balanced line. If an AssemblyStation is part of the balanced line, the Cycle only continues balancing if the assembly process has been finished.

**Note**

A Front -triggered Exit Control is only called for the last station of the cycle defined by the object Cycle as the Destination for all other stations of the cycle is already set. Use a Rear -triggered Exit Control instead.

**Note**

A Pull Control is not called for the stations of the object Cycle .

You can insert as many Cycle objects as you need into your simulation model. They all work independent of each other. If you use several Cycle objects, make sure to only assign each station to a single Cycle object.

If you did not define any stations for the balanced line yet, drag a Station or an AssemblyStation onto the icon of the object Cycle and drop it there, Plant Simulation enters it as the first station of the balanced line. If you drag another object onto it and drop it there, Plant Simulation enters it as the last station. If you already defined the last station and would like to change it, hold down Shift , drag the object, which you would like to use as the last station of the balanced line over the Cycle and drop it there.

To show a tooltip with information about the Cycle , hover with the mouse over it.

<!-- image -->

<!-- image -->

<!-- image -->

To change the length of the graphic and the anchor points of the Cycle , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Cycle to your simulation model, click MaterialFlow &gt; Cycle on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

**Dialog Box of the Object Cycle**

See also

Balance a Production Line

#### Dialog Box of the Object Cycle

Dialog Box of the Cycle

Double-click the icon of the Cycle to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Active [check box] - Cycle

To synchronize the transfer of MUs from station to station, select this check box.

<!-- image -->

Then a part is only moved on to the next station within the balanced line, when all stations have finished processing their parts and when none of the stations is failed, paused or unplanned.

To deactivate line balancing, clear the check box.

SimTalk

Active [SimTalk] - Cycle

**First Station**

###### First Station

Type in the name of the first station of the group of stations, which you want to balance. Or click the ellipsis button and select a material flow object in the dialog Select Object .

<!-- image -->

All stations between the First Station and the Last Station which are connected with Connectors form the balanced line.

If you did not define any stations for the balanced line yet, drag a Station or an AssemblyStation onto the icon of the object Cycle and drop it there, Plant Simulation enters it as the first station of the balanced line.

If you drag another object onto it and drop it there, Plant Simulation enters it as the last station.

If you already defined the last station and would like to change it, hold down Shift , drag the object, which you would like to use as the last station of the balanced line over the Cycle , and drop it there. The status bar shows which object you are setting.

<!-- image -->

###### Last Station

Type in the name of the last station of the group of stations, which you want to balance. Or click the ellipsis button and select a material flow object in the dialog Select Object .

<!-- image -->

All stations between the First Station and the Last Station , which are connected with Connectors form the balanced line.

If you did not define any stations for the balanced line yet, drag a Station or an AssemblyStation onto the icon of the object Cycle and drop it there, Plant Simulation enters it as the first station of the balanced line.

If you drag another object onto it and drop it there, Plant Simulation enters it as the last station.

If you already defined the last station and would like to change it, hold down Shift , drag the object, which you would like to use as the last station of the balanced line over the Cycle , and drop it there. The status bar shows which object you are setting.

SimTalk

GetLastStation [SimTalk]

setFirstAndLastStation [SimTalk]

See also

Select Object [for controls]

**Empty Cycle Allowed [check box]**

###### Empty Cycle Allowed [check box]

To allow parts on the balanced stations to be moved on, although no part is ready to move on from the predecessor of the balanced line, select this check box. This results in an idle cycle.

<!-- image -->

**SimTalk**

EmptyCycleAllowed [SimTalk]

###### Part Can Only Enter on Cycle [check box]

To allow parts to enter the Cycle only if the cycle moves all MUs by one station on and is thus empty, select this check box.

<!-- image -->

To allow parts to enter the Cycle at any time, clear the check box.

SimTalk

EntranceOnlyOnCycle [SimTalk]

**Tab Statistics**

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the Object Cycle

Methods of the Object Cycle

The object Cycle provides:

- The method setFirstAndLastStation [SimTalk] .
- The Methods of the Material Flow Objects .
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

##### setFirstAndLastStation [SimTalk]

Sets the First Station and the Last Station of the balanced line which the Cycle station designated by &lt;Path&gt; synchronizes.

Remarks

All stations between these station, which are connected with Connectors , form the balanced line.

Type

Method

Syntax

&lt; Path &gt;.setFirstAndLastStation(FirstStation:path, LastStation:path) → boolean

**Parameters**

- The parameter FirstStation of data type object/path designates the First Station .
- The parameter LastStation of data type object/path designates the Last Station .

Return Value

The return value has the data type boolean .

Example

MyCycleObject.setFirstAndLastStation(MyStation1,MyStation4)

SimTalk

First Station

Last Station

GetFirstStation [SimTalk]

GetLastStation [SimTalk]

##### Read-Only Attributes of the Cycle

Read-Only Attributes of the Cycle

The Cycle provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print Cycle.GetFirstStation
```

##### GetFirstStation [SimTalk]

Returns the first station of the balanced line which the Cycle designated by &lt;Path&gt; synchronizes.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetFirstStation -&gt; object

Return Value

The return value has the data type object .

Example

print MyCycleObject.GetFirstStation

See also

First Station

**GetLastStation [SimTalk]**

##### GetLastStation [SimTalk]

Returns the last station of the balanced line which the Cycle designated by &lt;Path&gt; synchronizes.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetLastStation -&gt; object

Return Value

The return value has the data type object .

Example

print MyCycleObject.GetLastStation

See also

Last Station

##### Attributes of the Object Cycle

\_Attributes of the Object Cycle

The object Cycle provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyCycleObjekt.Active := true
print MyCycleObject.EmptyCycleAllowed
posit := MyStation.Cont.XPos
```

Active [SimTalk] - Cycle

Active [SimTalk] - Cycle

Activates line balancing with the Cycle designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Active:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCycleObject.Active := true
```

See also

Active [check box] - Cycle

##### EmptyCycleAllowed [SimTalk]

Sets if parts within the Cycle designated by &lt;Path&gt; can be moved on, although no part is ready to move on from the predecessor of the synchronized stations ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EmptyCycleAllowed:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCycleObject.EmptyCycleAllowed := true
```

See also

Empty Cycle Allowed [check box]

**EntranceOnlyOnCycle [SimTalk]**

##### EntranceOnlyOnCycle [SimTalk]

Sets if parts are allowed to enter the Cycle designated by &lt;Path&gt; only when the cycle moves all MUs by one station on ( true ).

Remarks

Specify false to allow parts to enter the Cycle at any time.

Type

Attribute

Syntax

&lt; Path &gt;.EmptyCycleAllowed:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCycleObject.EmptyCycleAllowed := true
```

See also

Part Can Only Enter on Cycle [check box]

**Fluid Objects**

