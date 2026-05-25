### AGVPool

Use the AGVPool for creating automated guided vehicles (AGVs). You can then model AGV systems in your installation in which the AGVs are not bound to a permanently installed route network.

Icon

<!-- image -->

**Description**

You might model the supervisor of an plant or the foreman of a shop with it. The AGVPool creates automated guided vehicles . You can then model AGV systems in your installation in which the AGVs are not bound to a permanently installed route network.

<!-- image -->

This is especially helpful if you need to produce smaller lot sizes with a high variant mix on a single production line. Instead of fixed production lines you can then use AGVs to transport the loaded products through a modular structured installation. The AGVs can, depending on the situation, create and change virtual tracks on which they drive.

The AGVPool in 3D looks like this:

<!-- image -->

As opposed to 2D the AGVPool does initially not show any AGV in 3D. To see the AGVs in 3D, select the check box Show Content on the tab Graphics of the AGVPool .

<!-- image -->

Then, click Start Simulation .

<!-- image -->

<!-- image -->

Use the object Marker to set way points along which the AGV drives from the AGVPool to its destination .

To show a tooltip with information about the AGVPool , hover with the mouse over it.

To change the length of the graphic and the anchor points of the AGVPool , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the AGVPool to your simulation model, click Resources &gt; AGVPool on the Home ribbon tab.

See also

Model an Automated Guided Vehicle System (AGVS)

#### Dialog Box of the AGVPool

Dialog Box of the AGVPool

Double-click the icon of the AGVPool to open its dialog box.

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

<!-- image -->

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

###### AGV [text box]

Select the vehicle that you want to use for the Automated Guided Vehicle ( AGV ) of the Automated Guided Vehicle System (AGVS) in your model.

<!-- image -->

**Note**

By default, the Transporter in the folder MUs in the Class Library is the AGV . For this reason the methods, attributes, and read-only attributes of the Transporter apply to the AGV as well.

Plant Simulation creates the specified Amount of AGVs during the init phase of the simulation run.

**Note**

In the current version the SankeyDiagram does not record the AGV that is driving freely within the area.

For the AGV that drives freely within the area, you can define these settings for the Distance Control :

<!-- image -->

Length Zone 1 , ΔWidth Zone 1 , Length Zone 2 , and ΔWidth Zone 2

SimTalk

AGV [SimTalk]

AGVPool [SimTalk] of the Transporter

StoppingCounter [SimTalk] of the Transporter

See also

setRoute [SimTalk] - Transporter

setRouteSegments [SimTalk]

**Amount [text box] - AGVPool**

###### Amount [text box] - AGVPool

Type in the number of vehicles that you want to use for the Automated Guided Vehicle System (AGVS).

<!-- image -->

Plant Simulation creates the specified amount of AGVs during the init phase of the simulation run.

SimTalk

Amount [SimTalk] - AGVPool

###### Shift Calendar [AGVPool]

<!-- image -->

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the AGVPool works.

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the objects into the list of the objects on the tab Resources of the ShiftCalendar .

You can edit the contents of the text boxes with the commands on the Context Menu of Embedded Lists .

SimTalk

ShiftCalendarObject [SimTalk] - material flow objects

ShiftCalendar [object]

Select Object [for controls]

**Tab Statistics [AGVPool]**

##### Tab Statistics [AGVPool]

The tab Statistics shows the most important statistics values.

| Item English              | Description                                                                                                                                                       | Read-only attribute                              | Item German                         |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------|
| Paused                    | Shows the portion of the statistics collection period during which the AGVPool was paused.                                                                        | StatPausingCount [SimTalk]                       | Pausiert                            |
| Unplanned                 | Shows the portion of the statistics collection period during which the AGVPool was unplanned, i.e., is not scheduled to work to the statistics collection period. | StatUnplannedPortio n [SimTalk]                  | Ungeplant                           |
| Average Traveled Distance | Shows the average distance in meters which the AGV traveled from the AGVPool to its destination .                                                                 | StatAverageTraveled Distance [SimTalk] - AGVPool | Durchschnittlich zurückgelegter Weg |

<!-- image -->

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object, or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

Navigate Menu The commands are described under the Navigate Menu . View Menu View Menu The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] Assigned AGVs [AGVPool] Associated Shift Calendar SimTalk updateDialog [SimTalk] See also View Menu [general description]

**Assigned AGVs [AGVPool]**

###### Assigned AGVs [AGVPool]

Opens a list showing all the AGVs that the AGVPool manages.

<!-- image -->

**SimTalk**

getAssignedAGVsTable [SimTalk]

Tools Menu

The Tools Menu provides these menu commands: Edit Controls &gt; Init control Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

**Methods of the AGVPool**

#### \_Methods of the AGVPool

The AGVPool provides:

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

getAssignedAGV [SimTalk]

getAssignedAGV [SimTalk]

Returns the AGV designated by the number in the AGVPool designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAssignedAGV(No:integer)
-> object
```

Parameter

The parameter No of data type integer designates the number of the AGV that is assigned.

Return Value

The return value has the data type object .

Example

```simtalk
print MyAGVPool.getAssignedAGV(2) -- might, for example,
return .UserObjects.MyAGV:2
```

See also

Assigned AGVs [AGVPool]

##### getAssignedAGVsTable [SimTalk]

Returns the table containing the assigned AGVs of the AGVPool designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAssignedAGVsTable([AssignedAGVs:table])
-> any
```

Parameter

The optional parameter AssignedAGVs of data type table designates the name of the table into which the AGVs will be written.

If you do not specify the optional parameter, Plant Simulation returns an array with the assigned automated guided vehicles ( AGVs ).

Return Value

The return value has the data type any .

Examples

MyAGVPool.getAssignedAGVsTable(myAssignedAGVsTable) // writes the AGVs into the specified table

MyAGVPool.getAssignedAGVsTable // writes the AGVs to an array

See also

Assigned AGVs [AGVPool]

##### getIdleAGV [SimTalk]

getIdleAGV [SimTalk]

Returns an AGV of the AGVPool designated by &lt;Path&gt; for which the attribute IsIdle has the value true.

Remarks

getIdleAGV also sets the attribute IsIdle of the returned AGV to false. You yourself are responsible to set IsIdle to true again if the AGV is to be available again, normally when the AGV has reached the end of the route.

Type

Method

Syntax

```simtalk
< Path >.getIdleAGV → object
```

Return Value

The return value has the data type object .

VOID if no idle AGV is available.

Example

```simtalk
waituntil AGVPool.NumIdleAGVs > 0
var AGV := AGVPool.getIdleAGV
```

SimTalk

IsIdle [SimTalk] - Transporter

NumIdleAGVs [SimTalk]

See also

Fine-position an AGV

#### Read-Only Attributes of the AGVPool

\_Read-Only Attributes of the AGVPool

The AGVPool provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyAGVPool.StatAverageTraveledDistance

##### NumIdleAGVs [SimTalk]

NumIdleAGVs [SimTalk]

Returns the number of AGVs of the AGVPool designated by &lt;Path&gt; for which the attribute IsIdle returned true.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumIdleAGVs → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
waituntil AGVPool.NumIdleAGVs > 0
var AGV := AGVPool.getIdleAGV
```

SimTalk

IsIdle [SimTalk] - Transporter

getIdleAGV [SimTalk]

See also

Fine-position an AGV

Video on YouTube

[https://youtu.be/PYXYutlaGOs?si=G\_5eRYYGFXUoUrSv&amp;t=36](https://youtu.be/PYXYutlaGOs?si=G_5eRYYGFXUoUrSv&t=36)

##### StatAverageTraveledDistance [SimTalk] - AGVPool

Returns the average distance in meters which the AGVs of the AGVPool designated by &lt;Path&gt; traveled.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatAverageTraveledDistance → length

Return Value

The return value has the data type length .

Example

print AGVPool.StatAverageTraveledDistance

#### Attributes of the AGVPool

\_Attributes of the AGVPool

The AGVPool provides:

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
MyAGVPool.BrokerPath := mybroker
MyAGVPool.AGV := ".UserObjects.MyAGV"
```

##### AGV [SimTalk]

Sets the AGVs which the AGVPool designated by &lt;Path&gt; creates.

Remarks

**Note**

By default the Transporter in the folder MUs in the Class Library is the AGV . For this reason the methods, attributes, and read-only attributes of the Transporter apply to the AGV as well.

Plant Simulation creates the specified Amount of vehicles during the init phase of the simulation run.

**Note**

In the current version the SankeyDiagram does not record the AGV , that is driving freely within the area.

Type

Attribute

Syntax

&lt; Path &gt;.AGV:path

Assignment Value

You can assign a value of data type path .

Examples

```simtalk
MyAGVPool.AGV := ".UserObjects.MyAGV"
var AGV : object := AGVPool.Cont
AGV.setRoute([M1,M2,M3,M4])
waituntil AGV.DestinationWasReached
AGV.setRoute([M1,M2,M3,M4])
```

SimTalk

setRoute [SimTalk] - Transporter

setRouteSegments [SimTalk]

**AGV [SimTalk]**

**Amount [SimTalk] - AGVPool**

See also

AGV [text box]

##### Amount [SimTalk] - AGVPool

Sets the amount of AGVs which the AGVPool designated by &lt;Path&gt; creates.

Remarks

Plant Simulation creates the specified Amount of AGVs during the init phase of the simulation run.

Type

Attribute

Syntax

```simtalk
< Path >.Amount:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyAGVPool.Amount := 2
```

See also

Amount [text box] - AGVPool

AGV [SimTalk]

#### Marker

