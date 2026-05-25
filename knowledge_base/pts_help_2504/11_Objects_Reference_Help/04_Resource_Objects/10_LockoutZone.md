### LockoutZone

Use the LockoutZone for combining a group of material flow objects. If one of these stations fails, all other stations within the lockout zone stop processing their parts as well.

Icon

<!-- image -->

Remarks

The LockoutZone controls the failures of all assigned stations. It then returns the total availability of the assigned stations.

You can insert more than one LockoutZone into a simulation model. The LockoutZones can overlap, meaning that a station can be assigned to more than one LockoutZone .

You have to define failure profiles for at least one of the stations assigned to the LockoutZone . As soon as one of the stations fails, the LockoutZone stops all processing operations of all assigned stations, meaning it sets their attribute Stopped to true . You can select if the LockoutZone stops the processing operations immediately or when the service arrives.

<!-- image -->

The stations only start processing parts again after all failures were removed. They then only use up the respective remaining processing time.

You can also determine what happens if the stations start processing parts again by programming a Resume Control .

In case one of the stations is paused if the LockoutZone intends to stop, this station does not start or restart processing after the pause is over.

You can assign any of the built-in Material Flow Objects or Fluid Objects to the LockoutZone . For stations, you yourself modeled in a Frame , the LockoutZone sets the attribute Stopped of that Frame to true . You then have to model an adequate reaction to the attribute. In addition, you can also add a Worker or the WorkerPool .

If the station that triggers the lockout zone is assigned to more than one LockoutZone , all stations of all LockoutZones will be stopped. If the station that triggers the lockout zone is assigned to only one LockoutZone , it only stops the station that you assigned to it.

To show a tooltip with information about the LockoutZone , hover with the mouse over it.

To change the length of the graphic and the anchor points of the LockoutZone , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the LockoutZone to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; LockoutZone on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Model a Lockout Zone

#### Dialog Box of the LockoutZone

Dialog Box of the LockoutZone

Double-click the icon of the LockoutZone to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**See also**

**Active [check box] - LockoutZone**

##### Active [check box] - LockoutZone

Active [check box] - LockoutZone

To activate the LockoutZone , select this check box. It then creates failures and stops the processing operations of all assigned objects, when one of these stations fails.

<!-- image -->

To deactivate it, clear the check box.

SimTalk

Active [SimTalk] - LockoutZone

See also

Objects [LockoutZone]

Tab Controls

Tab Controls [LockoutZone]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Set-up Control .

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

Specifying a control overrules the default behavior of the LockoutZone . This means that you yourself are responsible for stopping all processing operations of the assigned objects by assigning true to their attribute Stopped .

When you want the objects to continue processing parts, you have to make sure to terminate stopped mode by assigning false to the attribute Stopped .

See also

Stopped [SimTalk] - material flow objects

Stop Control [LockoutZone]

Resume Control [LockoutZone]

Stop Mode [drop-down list]

**Stop Control [LockoutZone]**

###### Stop Control [LockoutZone]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Stop Control , which is called if one of the stations assigned to the LockoutZone fails and thus stops processing parts.

<!-- image -->

The anonymous identifier @ designates the triggering station, the anonymous identifier ? designates the LockoutZone .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

StopCtrl [SimTalk]

**See also**

**Use a Stop Processing Control**

###### Resume Control [LockoutZone]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Resume Control , which is called when all failures of the assigned stations were removed and the stations can thus resume processing parts .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

ResumeCtrl [SimTalk]

**See also Select Object [for controls]**

Use a Resume Processing Control

###### Stop Mode [drop-down list]

Stop Mode [drop-down list]

Select the Stop Mode of the LockoutZone .

<!-- image -->

- Stop immediately stops the processing operations of all stations that are part of the LockoutZone as soon as one of the stations assigned to it fails. None of the other stations in the model are stopped! Within this period of time additional failures can take place for the assigned stations, several failures of differing stations can thus overlap. The stations only start processing parts again after all failures were removed. They then only use up the remaining processing time.
- Stop when service arrives only stops the stations assigned to the LockoutZone when the repair services, which the failed station requested, are assigned. Depending on your modeling situation this can be at a different point in time. If you model Footpaths on which the Worker walks to the station, Plant Simulation considers the Worker as received once he has reached the station. For Exporters/ Workers who can be beamed, the service is considered to be received once the Broker has assigned the service. This matches the behavior of the Receive Control .

The LockoutZone does not affect the Recovery Time and the Cycle Time of the stations which it controls. The LockoutZone stops these objects and records statistics values for the state Stopped . If you deactivate the LockoutZone while it is in the process of stopping other stations, Plant Simulation immediately releases all objects stopped by the LockoutZone . If you reset your model, all objects change their state from stopped to operational .

SimTalk

StopMode [SimTalk]

See also

Use a Stop Processing Control

Stopped [state, material flow objects]

Stopped [SimTalk] - LockoutZone

Stop the Associated Stations Immediately After a Failure

Stop the Associated Stations When the Repair Man Arrives Tab Objects Tab Objects Assign resource objects to the LockoutZone on the tab Objects .

A resource is any of the built-in Material Flow Objects , or a Frame in which you modeled a machine, whose Working hours you would like to control with the LockoutZone . In addition, you can also add a Worker or the WorkerPool .

<!-- image -->

You can manipulate the contents of the list window with the commands of the Context Menu of Embedded Lists .

See also

Objects [LockoutZone]

**Objects [LockoutZone]**

###### Objects [LockoutZone]

Assign resources to the LockoutZone on the tab Objects .

- Before you can type in data, click the Inheritance check box so that it looks like this .
- Type the path to and the name of the resource object in a cell. Or
- Drag the resource object to the icon of the LockoutZone and drop it there. You can also select and then drag-and-drop multiple objects at the same time!

<!-- image -->

You can manipulate the contents of the list window with the commands of the Context Menu of Embedded Lists .

SimTalk

addObject [SimTalk] - LockoutZone

Objects [SimTalk] - LockoutZone

See also

Show Assigned Objects [LockoutZone]

##### Tab Statistics [LockoutZone]

The tab Statistics shows the most important statistical data of the LockoutZone .

| Item English                         | Description                                                                                                                            | Read-only attribute                         | Item German                            |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|----------------------------------------|
| Stopped Portion                      | Shows the portion of the statistics collection period during which the stations were stopped by a LockoutZone in percent.              | StatStoppedPo rtion [SimTalk] - LockoutZone | Angehalten Anteil                      |
| Stopped Count                        | Shows how often the LockoutZone stopped the stations.                                                                                  | StatStoppedCo unt [SimTalk] - LockoutZone   | Angehalten Anzahl                      |
| Stopped durations total time         | Shows the total time during which the LockoutZone stopped the processing operations of the assigned stations.                          | StatStoppedTi me [SimTalk]                  | Angehaltendauern Gesamtzeit            |
| Stopped durations mean time          | Shows the mean time during which the LockoutZone stopped the processing operations of the assigned stations.                           | StatStoppedM u [SimTalk] - LockoutZone      | Angehaltendauern mittlere Zeit         |
| Stopped durations Standard Deviation | Shows the standard deviation of the time during which the LockoutZone stopped the processing operations of the assigned stations.      | StatStoppedDe lta [SimTalk] - LockoutZone   | Angehaltendauern Standardabweichu ng   |
| Stopped intervals mean time          | Shows the mean time of the intervals during which the LockoutZone stopped the processing operations of the assigned stations.          | StatStoppedInt ervalMu [SimTalk]            | Angehaltenabstan d mittlere Zeit       |
| Stopped intervals Standard Deviation | Shows the standard deviation of the intervals during which the LockoutZone stopped the processing operations of the assigned stations. | StatStoppedInt ervalDelta [SimTalk]         | Angehaltenabstan d Standardabweichu ng |

**Tab Statistics [LockoutZone]**

<!-- image -->

The Statistics Report shows the Stopped Time of the individual material flow objects.

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu [LockoutZone]

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Assigned Objects [LockoutZone]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

###### Show Assigned Objects [LockoutZone]

Selects the objects which are assigned to the LockoutZone as resources in the Frame window.

**In 2D it looks like this:**

<!-- image -->

**In 3D it looks like this:**

<!-- image -->

Instead, you can also select Show Assigned Objects on the context menu of the LockoutZone in the Frame .

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the LockoutZone

Methods of the LockoutZone

The LockoutZone provides:

- The method addObject [SimTalk] - LockoutZone .
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

addObject [SimTalk] - LockoutZone

Adds a single object to the LockoutZone designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.addObject(NameOfObject:path) → boolean
```

Parameter

The parameter NameOfObject of data type path designates the name of the object you want to add.

Return Value

The return value has the data type boolean .

Example

MyLockoutZone.addObject(MyParallelStation)

SimTalk

Objects [SimTalk] - LockoutZone

See also

Tab Objects

#### Read-Only Attributes of the LockoutZone

\_Read-Only Attributes of the LockoutZone

The LockoutZone provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyLockoutZone.StatStoppedCount

**StatStoppedCount [SimTalk] - LockoutZone**

Returns how often the LockoutZone designated by &lt;Path&gt; stopped the assigned stations.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedCount → integer

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

print MyLockoutZone.StatStoppedCount

See also

Tab Statistics [LockoutZone]

StatStoppedDelta [SimTalk] - LockoutZone

Returns the standard deviation of the time during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

< Path >.StatStoppedDelta → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

print MyLockoutZone.StatStoppedDelta

See also

Tab Statistics [LockoutZone]

##### StatStoppedIntervalDelta [SimTalk]

Returns the standard deviation of the intervals during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedIntervalDelta → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

print MyLockoutZone.StatStoppedIntervalDelta

See also

Tab Statistics [LockoutZone]

StatStoppedIntervalMu [SimTalk]

Returns the mean time of the intervals during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

< Path >.StatStoppedIntervalMu → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

print MyLockoutZone.StatStoppedIntervalMu

See also

Tab Statistics [LockoutZone]

##### StatStoppedIntervalTime [SimTalk]

Returns the total time of the intervals during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

< Path >.StatStoppedIntervalTime → time

Return Value

The return value has the data type time .

Example

print MyLockoutZone.StatStoppedIntervalTime

See also

Tab Statistics [LockoutZone]

StatStoppedMu [SimTalk] - LockoutZone

Returns the mean time during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

< Path >.StatStoppedMu → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

print MyLockoutZone.StatStoppedMu

See also

Tab Statistics [LockoutZone]

##### StatStoppedPortion [SimTalk] - LockoutZone

Returns the portion of the statistics collection period during which the stations were stopped by the LockoutZone designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedPortion → real

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

print MyLockoutZone.StatStoppedPortion

See also

Tab Statistics [LockoutZone]

###### StatStoppedTime [SimTalk]

StatStoppedTime [SimTalk]

Returns the total time during which the LockoutZone designated by &lt;Path&gt; stopped the processing operations of the assigned stations.

Type

Read-only attribute

Syntax

< Path >.StatStoppedTime → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

```simtalk
print MyLockoutZone.StatStoppedTime
```

See also

Tab Statistics [LockoutZone]

#### Attributes of the LockoutZone

\_Attributes of the LockoutZone

The LockoutZone provides:

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
MyLockoutZone.StopMode := "stop when service arrives"
print MyLockoutZone.StopMode
posit := Station.Cont.XPos
```

##### Active [SimTalk] - LockoutZone

Active [SimTalk] - LockoutZone

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

It then creates and forwards failures for the assigned objects.

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyLockoutZone.Active := true
```

See also

Active [check box] - LockoutZone

##### Objects [SimTalk] - LockoutZone

Sets the resource objects which you want to assign to the LockoutZone designated by &lt;Path&gt;.

Remarks

The LockoutZone also returns these resources.

Type

Attribute

Syntax

< Path >.Objects:array

Assignment Value

You can assign a value of data type array which contains the resources.

Examples

```simtalk
var a :
object[] := [MyStation1, MyStation2]
LockoutZone.Objects := a
print MyLockoutZone.Objects // might, for example,
return [*.Models.MyEnginePlant.Station1, *.Models.MyEnginePlant.Frame, *.Models.MyEnginePlant.Station2, *.Models.MyEnginePlant.Station3, *.Models.MyEnginePlant.ParallelStation]
```

See also

Tab Objects

**ResumeCtrl [SimTalk]**

##### ResumeCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method when all failures of the objects assigned to the LockoutZone designated by &lt;Path&gt; were removed and the objects can thus continue processing parts.

Type

Attribute

Syntax

< Path >.ResumeCtrl:method

**Assignment Value**

You can assign a value of data type method .

**Examples**

```simtalk
MyLockoutZone.ResumeCtrl := &myResumeCtrl
var row: integer := ReportStopping.ydim
ReportStopping["Last Failed Station",row] := @.name
ReportStopping["End Stopping",row] := eventcontroller.simTime
ReportStopping["Duration",row] := ReportStopping["End Stopping",row] ReportStopping["Start Stopping",row]
```

See also

Resume Control [LockoutZone]

##### StopCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method when one of the objects assigned to the LockoutZone designated by &lt;Path&gt; fails.

The anonymous identifier @ designates the triggering station, the anonymous identifier ? designates the LockoutZone .

Type

Attribute

Syntax

< Path >.StopCtrl:method

**Assignment Value**

You can assign a value of data type method .

**Examples**

```simtalk
MyLockoutZone.StopCtrl := &myStopCtrl
var row:integer := ReportStopping.ydim + 1
ReportStopping["First Failed Station",row] := @.name
ReportStopping["Start Stopping",row] := eventcontroller.simTime
```

See also

Stop Control [LockoutZone]

##### StopMode [SimTalk]

StopMode [SimTalk]

Sets the Stop Mode of the LockoutZone designated by &lt;Path&gt;.

Remarks

The LockoutZone does not affect the Recovery Time and the Cycle Time of the stations which it controls. The LockoutZone stops these objects and records statistics values for the state stopped . If you deactivate the LockoutZone while it is in the process of stopping other stations, Plant Simulation immediately releases all objects stopped by the LockoutZone . When you reset your model, all objects change their state from stopped to operational .

Type

Attribute

Syntax

&lt; Path &gt;.StopMode

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type string .

You can specify:

- "Stop immediately" immediately stops the processing operations of all other objects within the LockoutZone as soon as one of the objects assigned to the LockoutZone fails.

The objects do not fail! Within this period of time additional failures can take place for the assigned stations, several failures of differing objects can thus overlap. The stations only start processing parts again after all failures were removed. They only use up the remaining processing time.

- "Stop when service arrives" only stops the objects assigned to the LockoutZone when the services, which the failed station requested, are assigned.

Depending on your modeling situation this can be at a different point in time. If you modeled Footpaths on which the Worker walks to the station, Plant Simulation considers the Worker as received once he has reached the station. For Exporters/Workers who can be beamed, the service is considered to be received once the Broker has assigned the service. This matches the behavior of the Receive Control .

**Example**

```simtalk
MyLockoutZone.StopMode := "Stop when Service arrives"
```

SimTalk

Stopped [SimTalk] - LockoutZone

See also

Stop Mode [drop-down list]

Stopped [state, material flow objects]

##### Stopped [SimTalk] - LockoutZone

Stopped [SimTalk] - LockoutZone

Sets if the LockoutZone designated by &lt;Path&gt; is stopped ( true ) or if it is not stopped ( false ).

Remarks

Stopped means that all of the processing operations of the objects, which the LockoutZone controls, come to a halt.

Syntax

<!-- image -->

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

**Example**

```simtalk
MyLockoutZone.Stopped := true
```

