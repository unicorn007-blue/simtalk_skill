#### Methods of the Material Flow Objects

Methods of the Material Flow Objects

All material flow objects share the methods described below. The sub-chapters about the objects list additional methods for these objects.

**A method**

- gets information from an object and returns a value.
- computes a value.
- starts one or several actions that control the behavior of the object.

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

In our description we grouped the methods according to their functions.

**See also**

- \_Methods for the State
- \_Methods for Accessing the Contents

Methods for Setting-Up

- \_Methods for Defining Failures

Methods for Accessing Statistics

- \_Methods of Sensors
- \_Methods of Curved Objects in 2D
- \_Methods of the Importer

Methods of the Workplace

##### Methods for the State

- \_Methods for the State

The material flow objects provide the methods listed in the table of contents to the left for returning the state in which they are.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

bwBlockList [SimTalk] - material flow objects

Returns the blocking list in the backward direction for the objects Conveyor and Track designated by &lt;Path&gt;.

Remarks

Specify the optional parameter BackwardBlockingList of data type table to write the objects contained in the Backward Blocking List into this list.

If you do not specify the parameter, bwBlockList returns an array containing the objects contained in the Backward Blocking List . The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

In addition, Plant Simulation does not enter a MU into the Forward/Backward Blocking List if it is located on a moving Transporter .

Plant Simulation removes a MU , which is located on the loading space of a Container/Transporter , from the Forward/Backward Blocking List if the Container/Transporter itself is moved.

**Note**

If you enter a certain position on the destination object using the parameter of data type length , the MU does not enter itself into the Forward/Backward Blocking List as Plant Simulation cannot watch at which point in time this position is available again.

**Note**

The TwoLaneTrack provides a Backward Blocking List for each of its two lanes, i.e., for Lane A and for Lane B .

Type

Method

Syntax

```simtalk
< Path >.bwBlockList([BackwardBlockingList:table]) → any
```

**Parameter**

The optional parameter BackwardBlockingList of data type table designates the name of the table. This can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns.

Column 1 has the data type object and contains all MUs that attempted to leave the succeeding object and wanted to move onto the object at its exit, i.e., were moving in a backward direction from the successor, but could not.

Column 2 contains the simulation time at which the MUs attempted to enter the object. The number of rows matches the number of MUs in the blocking list.

Return Value

The return value has the data type any .

**Example**

```simtalk
MyTrack.bwBlockList(myBackwardBlocklist)
numAGV := myBackwardBlocklist.ydim
print "Number of AGVs wanting to use the track:"
print numAGV
```

**See also**

Backward Blocking List

bwBlockList [SimTalk] - lane A or B

BwBlockListEntry1 [SimTalk]

BlockingStarttime [SimTalk]

Check the Contents List of the Stations endFailure [SimTalk] - material flow objects Terminates the failure of the object designated by &lt;Path&gt; and sets the attribute Failed to false.

Remarks

When you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method &lt;name of the station&gt;.failImp.import .

When you requested the service for removing the failure with the method &lt;name of the station&gt;.failImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.failImp.releaseExporters .

Type

Method

Syntax

&lt; Path &gt;.endFailure

Example

MyStation.endFailure

SimTalk

startFailure [SimTalk] - material flow objects

startFailureIn [SimTalk] - material flow objects

releaseExporters [SimTalk]

import [SimTalk] - importer

See also

Failed [state - material flow objects]

endFailureIn [SimTalk] - material flow objects

Terminates the failure of the object designated by &lt;Path&gt;.

Remarks

endFailureIn schedules a DisruptionEnd event.

When the event is processed, the failure ends and the attribute Failed is set to false. The time interval has to be equal to or greater than zero.

**Note**

If no failure is active at the point in time when the event is processed, the method has no effect.

**Note**

When using the method startFailureIn we recommend to deactivate the internal failure generator by clearing the check box Active .

**Note**

If the object does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100 percent.

**Note**

When you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method &lt;name of the station&gt;.failImp.import .

When you requested the service for removing the failure with the method &lt;name of the station&gt;.failImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.failImp.releaseExporters .

Type

Method

Syntax

&lt; Path &gt;.endFailureIn(EndFailureIn:time)

**Parameter**

The parameter EndFailureIn of data type time designates the time after which the failure ends.

**Example**

station.endFailureIn(60) // ends the failure in 1 minute

**SimTalk**

startFailure [SimTalk] - material flow objects

startFailureIn [SimTalk] - material flow objects

releaseExporters [SimTalk]

import [SimTalk] - importer

See also

Active [check box] - failures

Failed [state - material flow objects]

Failed [SimTalk] - material flow objects

endPause [SimTalk] - material flow objects

Ends the pause of the object designated by &lt;Path&gt; and sets the attribute Pause to false.

Type

Method

Syntax

&lt; Path &gt;.endPause

Example

MyStation.endPause

SimTalk

startPause [SimTalk] - material flow objects

startPauseIn [SimTalk] - material flow objects

See also

Pause [SimTalk] - material flow objects

Paused [state, material flow objects]

endPauseIn [SimTalk] - material flow objects

Ends the pause of the object designated by &lt;Path&gt; after the designated time and then sets the attribute Pause to false.

Type

Method

Syntax

&lt; Path &gt;.endPauseIn(EndPauseIn:time)

Parameter

The parameter EndPauseIn of data type time designates the time after which the pause ends.

The time has to be equal to or greater than zero.

Example

MyTrack.endPauseIn(60)

SimTalk

startPause [SimTalk] - material flow objects

startPauseIn [SimTalk] - material flow objects

See also

Pause [SimTalk] - material flow objects

Paused [state, material flow objects]

**endSetupIn [SimTalk]**

endSetupIn [SimTalk]

Terminates setting-up the object designated by &lt;Path&gt; after the specified time.

Type

Method

Syntax

&lt; Path &gt;.endSetupIn(EndSetupIn:time)

Parameter

The parameter EndSetupIn of data type time designates the time after which setting-up ends.

The time has to be equal to or greater than zero.

Example

ParallelStation.endSetupIn(15:00.00)

See also

Methods for Setting-Up eraseFailureEvents [SimTalk] - material flow objects Deletes failure events of the object designated by &lt;Path&gt;.

Remarks

The methods startFailure , startFailureIn , endFailure , and endFailureIn entered the failure events into the list of scheduled events in the EventController .

You can, for example, use eraseFailureEvents to terminate an existing failure and delete the entered remove failure events at the same time, as these would terminate the new failure too early.

Type

Method

Syntax

&lt; Path &gt;.eraseFailureEvents

Example

MyStation.eraseFailureEvents

SimTalk

startFailure [SimTalk] - material flow objects

startFailureIn [SimTalk] - material flow objects

endFailure [SimTalk] - material flow objects

endFailureIn [SimTalk] - material flow objects

See also

Failed [state - material flow objects]

List of Events erasePauseEvents [SimTalk] - material flow objects Deletes pause and unpause events of the object designated by &lt;Path&gt;.

Remarks

The methods startPause , startPauseIn , endPause , and endPauseIn entered the pause and unpause events into the list of scheduled events in the EventController .

You can, for example, use erasePauseEvents to terminate an existing pause and delete the entered remove pause events at the same time, as these would terminate the new pause too early.

Type

Method

Syntax

&lt; Path &gt;.erasePauseEvents

Example

MyStation.erasePauseEvents

SimTalk

startPause [SimTalk] - material flow objects

startPauseIn [SimTalk] - material flow objects

Priority [failure importer]

endPauseIn [SimTalk] - material flow objects

See also

Paused [state, material flow objects]

exitBlockList [SimTalk] - material flow objects

Returns the exit blocking list of the object designated by &lt;Path&gt;.

Remarks

For objects with several processing places next to each other, such as the ParallelStation , the Exit Blocking List also contains the position of the place for which the part is entered. If you need this information, you have to specify a table instead of writing the data to an array .

Specify the optional parameter ExitBlockingList of data type table to write the objects contained in the Exit Blocking List into this list.

Do not specify the optional parameter ExitBlockingList to return an array containing the objects contained in the Exit Blocking List . The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

Type

Method

Syntax

```simtalk
< Path >.exitBlockList([ExitBlockingList:table])
-> object[]
```

**Parameter**

The optional parameter ExitBlockingList of data type table designates the name of the table. This can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns. Column 1 has the data type object and contains the MUs that unsuccessfully tried to exit the object. Column 2 contains the simulation time at which the MUs attempted to enter the object.

For the ParallelStation Plant Simulation lists in the third and fourth column onto which processing place the MU wanted to move. The number of rows matches the number of MUs in the blocking list.

Return Value

The return value is an array of data type object .

Example

ParallelStation.exitBlockList(myExitBlockList)

SimTalk BlockingStarttime [SimTalk] exitBlockList [SimTalk] - Store exitBlockList [SimTalk] - lane A or B See also Exit Blocking List Check the Contents List of the Stations

###### fwBlockList [SimTalk] - material flow objects

Returns the blocking list in the forward direction of the material flow object designated by &lt;Path&gt;.

Remarks

**Note**

If you only need the first entry of the Forward Blocking List , use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

Specify the optional parameter of data type table to write the objects contained in the Forward Blocking List into this list.

Do not specify the optional parameter to return an array containing the objects contained in the Forward Blocking List . The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

For objects with several processing places next to each other, such as the ParallelStation and the Store the forward blocking list also contains the position of the place for which the part is entered. If you need this information, you have to specify a table instead of writing the data to an array .

**Note**

If you enter a certain position on the destination object using the parameter of data type length , the MU does not enter itself into the Forward/Backward Blocking List as Plant Simulation cannot watch at which point in time this position is available again.

In addition Plant Simulation does not enter a MU into the Forward/Backward Blocking List if it is located on a moving Transporter .

Plant Simulation removes a MU , which is located on the loading space of a Container/Transporter , from the Forward/Backward Blocking List if the Container/Transporter itself is moved.

**Note**

If the predecessor is a FlowControl or a Sorter , the Forward Blocking List contains this FlowControl or Sorter instead of the MU .

Type

Method

**Syntax**

```simtalk
< Path >.fwBlockList([ForwardBlockingList:table])
-> object[]
```

Parameter

The optional parameter ForwardBlockingList of data type table designates the name of the table. This can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns. Column 1 has the data type object and contains the MUs that unsuccessfully tried to move to the object. Column 2 contains the simulation time at which the MUs attempted to enter the object. For the object ParallelStation the third and fourth columns hold the processing place onto which the MU attempted to move. The number of rows matches the number of MUs in the blocking list.

Return Value

The return value is an array of data type object .

Example

```simtalk
MyTrack.fwBlockList(myForwardBlocklist)
numAGV := myForwardBlocklist.ydim
print "Number of AGVs wanting to use the track:"
print numAGV
```

SimTalk

FwBlockListEntry1 [SimTalk]

fwBlockList [SimTalk] - material flow objects

BlockingStarttime [SimTalk]

See also

Forward Blocking List

Check the Contents List of the Stations

###### receptive [SimTalk]

Checks if the material flow object designated by &lt;Path&gt; can receive a MU (true) or not (false).

Remarks

Instead of passing an MU , you can also pass void.

Not all checks can be executed for these objects: Converter , AngularConverter , Turntable , Turnplate , PickAndPlace Robot , AssemblyStation and TwoLaneTrack . For these objects the dimension of the MU is relevant. For MU instances receptive returns true even if the station is not set up for the MU or if the station is not in the correct position to receive the MU .

For the Workplace Plant Simulation also considers Workers who are assigned but still on their way to this Workplace when checking if the Capacity of the Workplace is exhausted.

Type

Method

Syntax

```simtalk
< Path >.receptive(MU:object) → boolean
```

**Parameter**

The parameter MU of data type object designates the class or an instance of a MU .

Return Value

The return value has the data type boolean .

Examples

```simtalk
print Station.receptive(.MUs.Part:4320)
var b: boolean
b:= Station.receptive(void)
```

See also

Capacity [text box] - Workplace

Capacity [SimTalk] - Workplace

###### redraw [SimTalk]

Updates the display of the MUs on the material flow object designated by &lt;Path&gt;.

Remarks

Note

redraw also reevaluates the values of the Display Panel of the object and redraws the display panel in 2D.

Note

A 3D Only model does not provide the method redraw .

Type

Method

Syntax

&lt; Path &gt;.redraw

Example

MyConveyor.redraw

See also

Update the Display Panel [object]

###### restartCycle [SimTalk]

restartCycle [SimTalk]

Opens the entrance of the material flow object designated by &lt;Path&gt; and starts a new cycle for the time at which parts can enter the object. This means that the entrance will be opened the next time after the Cycle Time has elapsed.

Type

Method

Syntax

&lt; Path &gt;.restartCycle

Example

MyStation.restartCycle

See also

Cycle Time

###### setDim [SimTalk]

Sets the dimension, i.e., the number of storage places of the material flow object designated by &lt;Path&gt;.

Remarks

Only the ParallelStation , the Store , and the Transporter provide this method.

Type

Method

Syntax

```simtalk
< Path >.setDim(XDim:integer[, YDim:integer:=1]) → boolean
```

**Parameters**

- The parameter XDim of data type integer designates the dimension on the x-axis.
- The optional parameter YDim of data type integer designates the dimension on the y-axis.

**Default Value of the Parameter**

If you only specify the X-dimension, Plant Simulation automatically enters 1 for the Y-dimension.

Return Value

The return value has the data type boolean .

false if the dimension could not be changed.

**Example**

ParallelStation.setDim(20,20) Store.setDim(1000,1200) .mus.transporter.setdim(50,30)

###### startFailure [SimTalk] - material flow objects

Fails the object designated by &lt;Path&gt; immediately for the specified time and sets the attribute Failed to true. startFailure(TimeSpan) fails the object designated by &lt;Path&gt; for the specified time and sets the attribute Failed to true.

Remarks

**Note**

If you call startFailure with a parameter and the object does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100%. startFailure then schedules a DisruptionEnd event.

**Note**

If you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method &lt;name of the station&gt;.failImp.import .

If you requested the service for removing the failure with the method &lt;name of the station&gt;.failImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.failImp.releaseExporters .

Type

Method

Syntax

< Path >.startFailure < Path >.startFailure(DurationOfFailure:time)

Parameter

The parameter DurationOfFailure of data type time sets the duration of the failure.

The time interval has to be equal to or greater than zero.

Example

MyStation.startFailure MyStation.startFailure(str_to_time("1:30.12")) MyStation.startFailure(60) // duration 60 seconds

SimTalk endFailure [SimTalk] - material flow objects endFailureIn [SimTalk] - material flow objects import [SimTalk] - importer releaseExporters [SimTalk] See also Failed [state - material flow objects] Failed [SimTalk] - material flow objects startFailureIn [SimTalk] - material flow objects Fails the object designated by &lt;Path&gt; after the specified time and sets the attribute Failed to true.

Remarks

**Note**

If no failure is active at the point in time when the event is processed, the method has no effect.

**Note**

If the object does not have a failure profile yet, Plant Simulation creates a failure profile with an availability of 100%.

**Note**

When using the method startFailureIn we recommend to deactivate the internal failure generator by clearing the check box Active .

**Note**

If you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method &lt;name of the station&gt;.failImp.import .

If you requested the service for removing the failure with the method &lt;name of the station&gt;.failImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.failImp.releaseExporters .

Type

Method

Syntax

&lt; Path &gt;.startFailureIn(StartFailureIn:time)

Parameter

The parameter StartFailureIn of data type time designates the time after which the failure starts.

The time interval has to be equal to or greater than zero.

**Example**

MyStation.startFailureIn(10)

**SimTalk**

endFailure [SimTalk] - material flow objects

endFailureIn [SimTalk] - material flow objects

import [SimTalk] - importer

releaseExporters [SimTalk]

See also

Failed [state - material flow objects]

Failed [SimTalk] - material flow objects

Active [check box] - failures startPause [SimTalk] - material flow objects Pauses the object designated by &lt;Path&gt; immediately and sets the attribute Pause to true. startPause(TimeSpan) pauses the object for the specified time and sets the attribute Pause to true.

Type

Method

Syntax

```simtalk
< Path >.startPause < Path >.startPause(TimeSpan:time)
```

Parameter

The parameter TimeSpan of data type time designates the time after which, in relation to the simulation time, the object returns to the non-paused state.

The time interval has to be equal to or greater than zero.

Examples

```simtalk
MyStation.startPause
MyStation.startPause(60)
@.startPause
@.startPause(60)
```

SimTalk

endPause [SimTalk] - material flow objects

endPauseIn [SimTalk] - material flow objects

See also

Paused [state, material flow objects]

Pause [SimTalk] - material flow objects

###### startPauseIn [SimTalk] - material flow objects

Pauses the object designated by &lt;Path&gt; after the specified time and sets the attribute Pause to true.

Type

Method

Syntax

&lt; Path &gt;.startPauseIn(StartPauseIn:time)

Parameter

The parameter StartPauseIn of data type time designates the time after which the pause starts.

The time interval has to be equal to or greater than zero.

Example

ParallelStation.startPauseIn(10) // in 10 seconds

SimTalk

endPause [SimTalk] - material flow objects

endPauseIn [SimTalk] - material flow objects

Pause [SimTalk] - material flow objects

See also

Paused [state, material flow objects]

startProcessing [SimTalk] - material flow objects

Starts processing the part if the attribute AutomaticProcessing of the object designated by &lt;Path&gt; is set to false.

Remarks

The ParallelStation starts processing if the attribute StartProcessingWhenFull is true and it is to start processing the part early.

While startProcessing is being executed the station simultaneously requests Workers .

**Note**

You can only call the method for the Station , the ParallelStation , the AssemblyStation , the DismantleStation , and the Drain as these are the only objects for which you can clear Automatic Processing .

Type

Method

Syntax

&lt; Path &gt;.startProcessing

Example

MyStation.startProcessing MyParallelStation.startProcessing

SimTalk

AutomaticProcessing [SimTalk]

StartProcessingWhenFull [SimTalk]

See also

Automatic Processing

###### unblock [SimTalk]

Unblocks the object, which intends to move onto the object designated by &lt;Path&gt;.

Remarks

When the object is unblocked, the MU can enter the object.

Type

Method

Syntax

&lt; Path &gt;.unblock(MUorSorter:object)

**Parameter**

The parameter MUorSorter of data type object can either be a MU or a Sorter . Make sure that you only unblock a MU or a Sorter respectively, which are contained in the blocking list!

**Example**

```simtalk
var blockList: table, n: integer // @,?: the object for which a pull control was called
?.fwBlockList(blockList)
n := 1
?.unblock(blockList[1,n]) // n sets the row in the blockList, i.e. // the MU to be unblocked
```

##### Methods for Accessing the Contents

\_Methods for Accessing the Contents

The material flow objects provide the methods listed in the table of contents to the left for accessing their Contents .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### contentsAndReservedList [SimTalk]

Returns a table or an array containing all MUs which are located in the contents list of the object designated by &lt;Path&gt;, plus the MU for which a place was reserved on the object.

**Remarks**

**Note**

Contents and Reserved Places applies to the stationary material flow objects which can accept parts, to the Workplace , and to the Conveyor .

<!-- image -->

Plant Simulation considers a place as being reserved if, for example, a Worker was requested to carry a part to the target object as this object is available to accept this part.

Plant Simulation also considers a place as being reserved if, for example, a PickAndPlace robot to rotate to the part to pick it up and to transport it to the target object as it can now receive it.

Plant Simulation highlights the reservation in the table in color.

A Store with a Z-Dimension greater than 1 highlights the sub-tables containing reserved places with the same color. In addition the name of the subtable contains the number of the contained objects and the reserved place in the title bar of the window.

<!-- image -->

Type

Method

**Syntax**

```simtalk
< Path >.contentsAndReservedList([ContentsAndReservedPlaces:table]) → any
```

**Parameter**

The optional parameter ContentsAndReservedPlaces of data type table designates the name of the table (a DataTable or a local variable) into which the contents will be written. Plant Simulation automatically generates the format of this table and deletes any existing format and contents of the table.

If you do not specify the optional parameter, Plant Simulation returns an array with the MUs that are located on the object and for which a place is reserved.

Return Value

The return value has the data type any .

**Example**

```simtalk
print Store.contentsAndReservedList // might, for example,
return this array  in the Console // [[*.MUs.Part:2, *.MUs.Part:5, *.MUs.Part:15], [*.MUs.Part:17, *.MUs.Part:19, *.MUs.Part:21], [*.MUs.Part:22, *.MUs.Part:23, *.MUs.Part:24]][[*.MUs.Part:25, *.MUs.Part:27, *.MUs.Part:30], [*.MUs.Part:33, *.MUs.Part:36, *.MUs.Part:39], [*.MUs.Part:42, *.MUs.Part:45, *.MUs.Part:48]][[*.MUs.Part:51, *.MUs.Part:54, *.MUs.Part:57], [*.MUs.Part:60, *.MUs.Part:63, *.MUs.Part:66], [*.MUs.Part:69, *.MUs.Part:72, *.MUs.Part:75]]
```

**SimTalk**

ReservedFor [SimTalk]

ReservedPlace [SimTalk]

See also

Contents and Reserved Places

Model a Worker Who Waits for a Free Target contentsList [SimTalk] - material flow objects Returns an array containing the entire contents, i.e., all MUs located in the contents list of the object designated by &lt;Path&gt;.

<!-- image -->

**Parameter**

The optional parameter ContentsList of data type table designates the name of the table (a DataTable or a local variable) into which the contents will be written. Plant Simulation automatically generates the format of this table and deletes any existing format and contents of the table.

If you do not specify the optional parameter, Plant Simulation returns an array with the MUs that are located on the object.

- Station.contentsList(MyDataTable)

The point-oriented objects with a capacity of 1 part show the path in the list. The data type of the columns is object .

<!-- image -->

- Buffer.contentsList(MyDataTable)

The point-oriented objects with a capacity of more than 1 part show the path of the parts, which are located on it. The capacity determines how many parts it shows. The data type of the columns is object .

<!-- image -->

- ParallelStation.contentsList(MyDataTable)

The ParallelStation shows the path of the current parts in the list. The position of the part in the table matches the position of the part in its x-y coordinate system. The data type of the columns is object .

<!-- image -->

- Store.contentsList(MyDataTable)

The objects Store , Container , and Transporter , which can stack parts, show the stacked parts in subtables. The identifier of the subtable contains the number of stacked parts. To show the individual stacked parts in the subtable, double-click the respective cell in the contents list.

<!-- image -->

- Sorter.contentsList(MyDataTable)

The Sorter shows the path of the parts that are located on it. The capacity or the number of parts that are located on the Sorter determine how many parts it shows. The column has the data type object .

**Note**

Plant Simulation shows the parts on the Sorter in reverse order, meaning that the part that exits last is located on the first occupied place. The part that is going to exit next is located on the last place.

- Conveyor.contentsList(MyDataTable)

The length-oriented objects Conveyor , Track , and Transporter show the path of the part in the contents table, i.e., the names and the numbers of the current parts. In addition, it shows the position of the MUs on the object.

The column Object shows the path to the part , the column From shows the start position of the MU , and the column To shows the end position in the length unit you selected under File &gt; Model Settings/ Preferences &gt; Units Length . The number of rows matches the number of MU located on the object. The data type of column 1 is object , of the second and third column it is length .

<!-- image -->

- Cycle\_NW.A.contentsList(MyDataTable)

The length-oriented object TwoLaneTrack shows the path of the current part, in the contents table for lane A and lane B separately. In addition, it shows the position of the MUs on the object.

<!-- image -->

- Portioner.contentsList(MyDataTable)

The fluid objects DePortioner and Portioner show the path of the MU in the list, which is emptied or filled. The column has the data type object .

<!-- image -->

- SourceMilk.contentsList(MyDataTable)

The fluid objects FluidSource , FluidDrain , Pipe , and Tank show the material that flows through them. The column has the data type string .

<!-- image -->

- Mixer.contentsList(MyDataTable)

The fluid object Mixer shows the material in column 1 and the contained amount in column 2, while the starting materials flow into it. Column 1 has the data type string , column 2 has the data type real . As soon as the Mixer starts the mixing process, the contents list only shows the product in column 1.

<!-- image -->

- Workplace1.contentsList(MyDataTable)

The resource object Workplace shows the path of the Worker in the list. The column has the data type object .

<!-- image -->

- Worker2Parts.contentsList(MyDataTable)

The resource object Worker , who carries stacked parts, shows the stacked parts in subtables. The identifier of the subtable contains the number of stacked parts. To show the individual stacked parts in the subtable, double-click the respective cell in the contents list.

<!-- image -->

**Return Value**

The return value has the data type any .

Is an array containing all MUs which are located on the object if you do not specify the optional parameter.

**Examples**

```simtalk
machine.contentsList(myContentsList)
sumValue := contentsMachine.sumAttr("Value")
print "Total value in machine:"
print sumValue
print Track.contentsList // might, for example,
return // [.MUs.Transporter:49, 21.31726, 22.81726][.MUs.Transporter:50, 19.81726, 21.31726][.MUs.Transporter:51, 18.31726, 19.81726][.MUs.Transporter:52, 16.81726, 18.31726] in the Console
print Store.contentsList // might, for example,
return // [[*.MUs.Part:2, *.MUs.Part:5, *.MUs.Part:15], [*.MUs.Part:17, *.MUs.Part:19, *.MUs.Part:21], [*.MUs.Part:22, *.MUs.Part:23, *.MUs.Part:24]][[*.MUs.Part:25, *.MUs.Part:27, *.MUs.Part:30], [*.MUs.Part:33, *.MUs.Part:36, *.MUs.Part:39], [*.MUs.Part:42, *.MUs.Part:45, *.MUs.Part:48]][[*.MUs.Part:51, *.MUs.Part:54, *.MUs.Part:57], [*.MUs.Part:60, *.MUs.Part:63, *.MUs.Part:66], [*.MUs.Part:69, *.MUs.Part:72, *.MUs.Part:75]] in the Console
```

**SimTalk**

Cont [SimTalk] - material flow objects

contentsList [SimTalk] - lane A or B

See also

Contents [material flow objects]

Check the Contents List of the Stations deleteMovables [SimTalk] - material flow objects Deletes all MUs which are located on the object designated by &lt;Path&gt;.

Remarks

If &lt;Path&gt; designates a Frame , deleteMovables deletes all MUs on all objects, which are located in the Frame or in sub-Frames .

**Note**

deleteMovables does not delete any Workers in the object or the Frame .

Type

Method

Syntax

&lt; Path &gt;.deleteMovables

Example

ParallelStation.deleteMovables

See also

<!-- image -->

Delete MUs

on the Home Ribbon Tab

Contents [material flow objects]

mu [SimTalk] - material flow objects

Returns the MU specified by the index whose booking point is located on the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.mu([Index:integer:=1]) → object
```

Parameter

Specify the optional parameter Index of data type integer to return the MU designated by the parameter.

For a parameter greater than the number of parts booked on the object, Plant Simulation returns VOID.

Specify -1 for length-oriented objects to return the last MU .

Do not specify the optional parameter to return the first MU .

**Default Value of the Parameter**

The default value is 1, i.e., the first MU .

**Note**

For the object Buffer Plant Simulation returns the MUs in the Buffer in the order in which they entered the Buffer , independent of the Buffer Type ( Stack or Queue ) you selected. The method mu does not refer to the storage place of the MU in the Buffer , but is just a counter for the MUs located in the Buffer . To access the next MU , which will exit the Buffer according to the Buffer Type &gt; Stack or Queue , use the read-only attribute Cont .

**Return Value**

The return value has the data type object .

**Example**

```simtalk
var i : integer // returns all MUs
for i := 1 to ParallelStation.numMu
	print ParallelStation.mu(i).name
next
```

SimTalk Cont [SimTalk] - Comment muPart [SimTalk] See also Contents [material flow objects] Buffer Type [drop-down list]

###### muPart [SimTalk]

Returns the MU specified by the index , that is located on the object designated by &lt;Path&gt; as a whole or in part.

Type

Method

Syntax

```simtalk
< Path >.muPart([Index:integer:=1]) → object
```

**Parameter**

Specify the optional parameter Index of data type integer to return the MU designated by the parameter of data type integer .

Specify -1 for length-oriented objects to return the last muPart .

Do not specify the optional parameter to return the first available muPart .

MUs may also be located with a segment of their length on a length-oriented object. This is the case if a MU moved in part only onto a new object, but its rear end is still located on the previous object. This we call a MU part, whereas MUs that are located in their entirety on the object are also considered mu parts.

The MUs named A, B, C, D, E, and F are located on the length-oriented objects Line1 , Line2 , and Line3 . The booking points of all MUs are located at their front end.

<!-- image -->

**Example**

```simtalk
print line2.MUPart(4)
```

The return values for muPart for the example above are listed in this table:

##### Methods for Setting-Up

| Call            | Returns   |
|-----------------|-----------|
| line1.MUPart(1) | MUA       |
| line1.MUPart(2) | VOID      |
| line2.MUPart(1) | MUD       |
| line2.MUPart(2) | MUC       |
| line2.MUPart(3) | MUB       |
| line2.MUPart(4) | MUA       |
| line2.MUPart(5) | VOID      |

**Default Value of the Parameter**

The default value is 1, meaning the first MU .

Return Value

The return value has the data type object .

VOID if no muPart is located on the object or if the muPart called does not exist.

**Example**

line1.muPart(1) // returns VOID line2.muPart(1) // returns the part named C

SimTalk

mu [SimTalk] - material flow objects

See also

Contents [material flow objects]

Methods for Setting-Up

Methods for Setting-Up

The material flow objects provide the method setupFor [SimTalk] for setting them up.

Also compare:

- The method endSetupIn [SimTalk] .
- These read-only attributes:

NumPartsSinceSetup [SimTalk] IsSetupFor [SimTalk] ResSetup [SimTalk] - material flow objects

You can also define how to set up a material flow object on the Tab Set-Up .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### setupFor [SimTalk]

###### setupFor [SimTalk]

Starts setting-up the object designated by &lt;Path&gt; for a part type.

Remarks

Plant Simulation uses the Set-up Time you entered for the object on the tab Times .

**Note**

If the object cannot be set up at the current point in time, for example because it is failed, Plant Simulation does not attempt to set the object up anew.

**Note**

You can start a new setup process while a station is working. Resource statistics counts the time during which the station is setting-up as Set-up Time not as Working Time .

Type

Method

Syntax

&lt; Path &gt;.setupFor(setupFor:any[, PerformSetup:boolean]) → boolean

**Parameter**

- The parameter setupFor of data type any designates the MU for which the object is going to set up:
- The parameter setupFor of data type object designates a specific MU instance for which the object is going to set up.
- The parameter setupFor of data type object designates the MU class for which the object is going set up.
- The parameter setupFor of data type string designates the type of MU for which the object is going set up.
- The optional parameter PerformSetup of data type boolean determines if the object only sets the current type of part ( false ) or if the object actually sets-up at all ( true ).

If you do not specify the parameter, Plant Simulation sets the station up, as if you had passed true .

**Return Value**

The return value has the data type boolean .

false if the object cannot be set up, for example because it is failed.

**Example**

```simtalk
waituntil ParallelStation.empty prio 1
```

ParallelStation.setupFor(@)

SimTalk

AutomaticSetup [SimTalk]

IsSetupFor [SimTalk]

ResSetup [SimTalk] - material flow objects

See also

Set-up For

Set-up Time [general description]

Methods for Defining Failures

\_Methods for Defining Failures

Within a production environment production resources such as machines, vehicles, and workers may fail for unpredictable reasons. For simulating failures, the production resources have a failure generator whose settings you can select on the Tab Failures . Alternatively you can also define failures with availability and MTTR (mean time to repair). In addition you can set between which points in time ( Start and Stop ) these failures take place.

Failures may have different reasons, called failure profiles , which may overlap. A machine might, for example, fail because a tool breaks or because a motor fails. Both reasons for the failure of the production resource take place within different time intervals and require different repairing durations. You can define the interval , the duration , the availability , the MTTR , the start , and stop time on the Tab Failures .

You can select a probability distribution for each of the times. Some distributions require additional information.

Plant Simulation provides the methods listed in the table of contents to the left for defining several failures of the material flow objects.

The objects address failure profile methods as sub-methods of Failures .

The window Show Attributes and Methods shows the identifier Failures but not the methods proper of the failures.

The figure below illustrates the information using the example of the object Station .

<!-- image -->

**Example**

```simtalk
MyExporter.Failures.createFailure("NameOfNewFailure")
MyExporter.Failures.createFailure.NameOfNewFailure.Active := true
```

**See also**

Tab Failures [general description]

Methods of the Failure Profiles

Attributes for Defining Failures

Attributes of the Failure Profiles

###### count [SimTalk]

Returns how many failure profiles the object designated by &lt;Path&gt; has.

Remarks

The List of Failure Profiles shows how many failure profiles the object has.

Type

Method

Syntax

```simtalk
< Path >.Failures.count → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var i : integer
for var i := 1 to Machine.Failures.count
	Machine.Failures.getFailure(i).active := true
next
```

See also

List of Failure Profiles

**createFailure [SimTalk]**

###### createFailure [SimTalk]

Creates a new failure profile for the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.Failures.createFailure(Name:string) < Path >.Failures.createFailure(Name:string[, Availability/Interval:real/ string, MTTR/Duration:any, Mode:string, Start:any, Stop:any, Active:boolean])
```

**Parameters**

- The parameter Name of data type string designates the name of failure profile .
- The optional parameter Availability / Interval designates the availability or the failure interval:
- To set the availability, specify a numerical value of data type real or integer .
- To set the type and the parameters of the distribution function for the failure interval, specify a string , for example ("Uniform, 1:00, 2:30") .
- To set the failure interval to a constant value, specify a value of data type time .
- The optional parameter MTTR / Duration designates the MTTR or the failure duration:
- If you set the availability with the parameter Availability above, this parameter sets the MTTR. If not, it designates the failure duration. You can specify the MTTR as a numerical value or as a string .
- If you specified the MTTR as a string , you can also specify the bounds, for example ("1:00, 0:05, 20:00") . You can specify the failure duration as a numerical value or as a string .

A numerical value sets a constant failure duration, a string sets the type and the parameters of the distribution function.

- The optional parameter Mode of data type string sets the Failure Mode of the failure profile . If you do not specify this parameter, the failure relates to the Simulation Time .
- The optional parameter Start of data type any sets the point in time of the first failure.
- To set a constant point in time, specify a numerical value. 0 designates that the point in time of the first failure is determined by the failure interval.
- To set the type and the parameters of the distribution function, specify a string .
- The optional parameter Stop of data type any sets the point in time from with on no more failures will be created for this failure profile.

You can specify "SimulationTime" , "OperatingTime" , or "ProcessingTime" .

- To set a constant point in time, specify a numerical value. 0 designates that Plant Simulation creates failures infinitely.
- To set the type and the parameters of the distribution function, specify a string .
- The optional parameter Active of data type boolean sets if the failure profile is active ( true ) or not active ( false ).

**Examples**

```simtalk
MyAssembly.createFailure("MyProfile2", "Uniform, 1:00, 2:00", "Normal, 5:00, 30, 0, 30:00", "OperatingTime", "Uniform, 0:00, 5:00", 0, false)
MyPlaceBuffer.Failures.createFailure("NameOfNewFailure")
MyPlaceBuffer.Failures.NameOfNewFailure.Start := str_to_time("1:00:00") // no failures during the first hour
```

MyStation.Failures.createFailure("MyProfile1", 80, 60, "ProcessingTime") // Availability 80%, MTTR 60 seconds

**SimTalk**

**deleteFailure [SimTalk]**

See also

**New [failure]**

List of Failure Profiles

###### deleteFailure [SimTalk]

deleteFailure [SimTalk]

Deletes the specified failure profile of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.Failures.deleteFailure(FailureProfile:string)

Parameter

The parameter FailureProfile of data type string designates the name of failure profile .

Example

MyExporter.Failures.deleteFailure("NameOfFailureProfile")

SimTalk

createFailure [SimTalk]

See also

Delete [failure]

List of Failure Profiles getFailure [SimTalk]

Returns the specified failure profile of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.Failures.getFailure(NameOrNumber:any)

Parameter

The parameter NameOrNumber of data type any designates the name or the number of the failure profile .

Example

```simtalk
for var i := 1 to Machine.failures.count
	Machine.failures.getFailure(i).Active := true
next
```

See also

Tab Failures [general description]

List of Failure Profiles

###### getTable [SimTalk] - failure profile

getTable [SimTalk] - failure profile

Returns the parameters of the failure profiles of the object designated by &lt;Path&gt;, which you defined on the tab Failures .

Type

Method

Syntax

<!-- image -->

**Parameter**

The parameter Parameters of data type table designates the DataTable into which the method writes the values.

The List of Failure Profiles looks like this:

<!-- image -->

**Example**

MyMachine.Failures.getTable(FailuresTable)

SimTalk

setTable [SimTalk] - failure profile

See also

Tab Failures [general description]

List of Failure Profiles

###### setTable [SimTalk] - failure profile

setTable [SimTalk] - failure profile

Sets the failure profiles of the object designated by &lt;Path&gt; in a table.

Type

Method

Syntax

&lt; Path &gt;.setTable(FailuresTable:table)

Parameter

The parameter FailuresTable of data type table designates the DataTable in which you defined the failure profiles .

The List of Failure Profiles looks like this:

<!-- image -->

<!-- image -->

**Example**

MyMachine.Failures.setTable(MyDataTable)

SimTalk

getTable [SimTalk] - failure profile

See also

Tab Failures [general description]

List of Failure Profiles

Methods of the Failure Profiles

Methods of the Failure Profiles

The stationary material flow objects provide the method reset for the failure profiles.

Plant Simulation addresses the methods of the failure profiles as sub-methods of Failures .

Example

MyStation.Failures.MyFailureProfile.reset

The window Show Attributes and Methods shows the identifier Failures for failures, but not the actual attributes of the failure profile.

<!-- image -->

See also

Tab Failures [general description]

Methods of the Failure Profiles

##### Attributes for Defining Failures

\_Attributes of the Failure Profiles

###### reset [SimTalk] - failure profile

Resets the failure profile designated by &lt;NameOfFailureProfile&gt; of the object designated by &lt;Path&gt;. It then computes a new failure event.

Remarks

If the failure profile was failed at the moment, Plant Simulation terminates the failure. Then new times for Start , Stop , and Interval are determined.

If the simulation time of the EventController does not yet exceed the newly determined Stop time, a new failure event is scheduled.

If the newly determined Start time is located in the future, the failure is scheduled for this point in time. If it is not located in the future, the failure is scheduled with the newly determined interval.

You can use the method reset to force a recalculation of the failure event after you changed the parameters of the failure profile. If you change the parameter of the failure profile, this normally only affects the next failure. If you change the Availability , for example, the first computed failure event is retained, and the new availability will only be used for computing the start of the following failure.

**Note**

We recommend to only reset the failure profile in exceptional cases, as the failure portions that Plant Simulation determined, can change. You might, for example, reset the profile when a defective machine is replaced with another machine and when the new machine has another failure behavior.

Do not use the method reset , if you want to continually change the availability during the simulation and if the change should take effect immediately instead of only for the next failure. This could, for example, be the case if the availability depends on the part to be processed. In this case you should use several failure profiles and always activate the failure profile depending on the respective part type. Thus Plant Simulation then uses the expected failure portions.

Type

Method

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.reset

**Example**

MyStation.Failures.MyFailureProfile.reset Methods for Accessing Statistics Methods for Accessing Statistics The material flow objects provide the methods listed in the table of contents to the left for accessing the statistics values they collected.

<!-- image -->

The Tab Statistics shows the most important statistics values.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

initStat [SimTalk] - material flow objects

Resets statistics of the object designated by &lt;Path&gt; and starts collecting statistics anew.

Remarks

You can, for example, use initStat if you do not want to include the statistics of the initial stage of the simulation run.

**Note**

If you reset the statistics of a MU class with initStat , this also resets statistics of the instances.

Type

Method

Syntax

< Path >.initStat

**Example**

// method "resetStatistics" storeA25.initStat // reset statistics

SimTalk

StatisticsStartRes [SimTalk]

###### statistics [SimTalk] - material flow objects

Outputs statistics of the object designated by &lt;Path&gt;.

Remarks

If you do not specify a parameter, Plant Simulation outputs statistics to a table on your computer screen.

Type

Method

Syntax

```simtalk
< Path >.statistics < Path >.statistics(Table:table_path) < Path >.statistics(FileName:string[, CodePage:string:="UTF-8"])
```

**Parameters**

- The parameter Table of data type table\_path writes the data to the specified table.
- The parameter FileName of data type string writes the table to the specified file. Plant Simulation will overwrite existing entries.

If you specify a file name, use the optional parameter CodePage of data type string to set the encoding you want to use: ANSI , UTF-8 , or Unicode .

**Default Value of the Parameter**

The default value is UTF-8 .

**Note**

This only works if you activate Resource statistics .

**Note**

Plant Simulation provides more statistics values than the table, which the method statistics returns, provides.

**Example**

```simtalk
MyStation.statistics                // shows on the computer screen
MyStation.statistics(Stat_Tab)      // outputs to a table
MyStation.statistics("statistics")  // outputs to a file
```

The statistics table shows the statistical data for the material flow objects:

| Item          | Description                                                                                                                                                                                                                                                                                        | Read-only Attribute                            |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|
| Name          | Shows the name of the object the statistics were collected for ( string ).                                                                                                                                                                                                                         | -                                              |
| Time          | Shows the time of the statistics query ( time ).                                                                                                                                                                                                                                                   | -                                              |
| Start (R)     | Shows the time the resource statistics collection period of the object started ( time ).                                                                                                                                                                                                           | -                                              |
| Entries       | Shows the number of MUs that entered the object as an integer . When a MU enters the object, it only counts the MU itself, not its contents: When a Container holding several parts enters the object, the number of entries increases by 1, not by the number of parts located on the Container ! | StatNumIn [SimTalk] - material flow objects    |
| Exits         | Shows the number of MUs that exited the object as an integer . When a MU exits the object, it only counts the MU itself, not its contents: When a Transporter holding several MUs leaves the object, the number of exits increases by 1, not by the number of MUs the Transporter transports!      | StatNumOut [SimTalk] - material flow objects   |
| Contents      | Shows the number of MUs , which are located on the object as an integer . The rules described under Entries apply.                                                                                                                                                                                 | NumMU[SimTalk] - material flow objects         |
| Predeposition | Shows the number of MUs , which are located on the object at the beginning of the statistics collection period. The rules described under Entries apply ( integer ).                                                                                                                               | StatPredeposition [SimTalk]                    |
| Min_Cont      | Shows the minimum number of MUs , which were located on the                                                                                                                                                                                                                                        | StatMinNumMU [SimTalk] - material flow objects |

| Item                     | Description                                                                                                                                                                                    | Read-only Attribute                                      |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------|
|                          | object as an integer . The rules described under Entries apply.                                                                                                                                |                                                          |
| Max_Cont                 | Shows the maximum number of MUs , which were located on the object as an integer . The rules described under Entries apply.                                                                    | StatMaxNumMU [SimTalk] - material flow objects           |
| %age_RelOccu (%_Util)    | Shows the capacity-based ratio of the time during which the object was occupied, not paused and not failed to the time during which the object was not paused and not failed as a real number. | StatRelativeOccupation [SimTalk] - material flow objects |
| %age_RelOccuIR (%_tUtil) | Shows the capacity-based ratio of the time during which the object was occupied in relation to the statistics collection period ( real ).                                                      | StatRelativeOccupation [SimTalk] - material flow objects |
| %age_Wo                  | Shows the ratio of the time during which the object was Working to the statistics collection period.                                                                                           | StatWorkingPortion [SimTalk]                             |
| Working                  | Shows how often the object was working ( integer ).                                                                                                                                            | StatWorkingCount [SimTalk]                               |
| WorkingTime              | Shows the total time during which the object was working ( time ).                                                                                                                             | StatWorkingTime [SimTalk]                                |
| Wo_Mu                    | Shows the mean duration of the time spans during which the object was working ( time ).                                                                                                        | StatWorkingMu [SimTalk]                                  |
| Wo_Delta                 | Shows the standard deviation of the time spans during which the object was working from the mean value ( time ).                                                                               | StatWorkingDelta [SimTalk]                               |
| %age_SU                  | Shows the ratio of the time during which the object was Setting-Up to the statistics collection period ( real ).                                                                               | StatSetUpPortion [SimTalk]                               |
| SetUp                    | Shows how often the object was setting-up ( integer ).                                                                                                                                         | StatSetUpCount [SimTalk]                                 |

| Item           | Description                                                                                          | Read-only Attribute                               |
|----------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------|
| SetUpTime      | Shows the total time during which the object was setting-up ( time ).                                | StatSetupTime [SimTalk]                           |
| SU_Mu          | Shows the mean duration of a set-up process ( time ).                                                | StatSetUpMu [SimTalk]                             |
| SU_Delta       | Shows the standard deviation of the set-up from the mean value ( time ).                             | StatSetUpDelta [SimTalk]                          |
| SetUpTime (Wa) | Shows the total time during which the object was setting-up and waiting ( time ).                    | provided for backward compatibility, is always -1 |
| SetUpTime (Wo) | Shows the total time during which the object was setting-up and working ( time ).                    | provided for backward compatibility, is always -1 |
| SetUpTime (B)  | Shows the total time during which the object was setting-up and blocked ( time ).                    | provided for backward compatibility, is always -1 |
| %age_Wa        | Shows the ratio of the time during which the object was Waiting to the statistics collection period. | StatWaitingPortion [SimTalk]                      |
| Waiting        | Shows how often the object was waiting ( integer ).                                                  | StatWaitingCount [SimTalk]                        |
| WaitingTime    | Shows the total time during which the object was waiting ( time ).                                   | StatWaitingTime [SimTalk]                         |
| Wa_Mu          | Shows the mean duration of the objects waiting period ( time ).                                      | StatWaitingMu [SimTalk]                           |
| Wa_Delta       | Shows the standard deviation of the waiting periods from the mean value ( time ).                    | StatWaitingDelta [SimTalk]                        |
| %age_B         | Shows the ratio of the time during which the object was Blocked to the statistics collection period. | StatBlockingPortion [SimTalk]                     |
| Blocked        | Shows the number of times during which the object was blocked ( integer ).                           | StatBlockingCount [SimTalk]                       |

| Item         | Description                                                                                                      | Read-only Attribute                                  |
|--------------|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| BlockingTime | Shows the total time during which the object was blocked ( time ).                                               | StatBlockingTime [SimTalk]                           |
| B_Mu         | Shows the mean duration of the time spans during which the object was blocked ( time ).                          | StatBlockingMu [SimTalk]                             |
| B_Delta      | Shows the standard deviation of the time spans during which the object was blocked from the mean value ( time ). | StatBlockingDelta [SimTalk]                          |
| %age_Stp     | Shows the ratio of the time during which the object was Stopped to the statistics collection period.             | StatStoppedPortion [SimTalk] - material flow objects |
| Stops        | Shows how often the object was stopped ( integer ).                                                              | StatStoppedCount [SimTalk] - material flow objects   |
| StoppedTime  | Shows the total time during which the object was stopped ( time ).                                               | StatStoppedTime [SimTalk]                            |
| Stp_Mu       | Shows the mean duration of a stopped time of the object ( time ).                                                | StatStoppedMu [SimTalk] - material flow objects      |
| Stp_Delta    | Shows the standard deviation of the stopped time from the mean value ( time ).                                   | StatStoppedDelta [SimTalk] - material flow objects   |
| %age_F       | Shows the ratio of the time during which the object was Failed to the statistics collection period.              | StatFailPortion [SimTalk]                            |
| Failures     | Shows how often the object was failed ( integer ).                                                               | StatFailCount [SimTalk]                              |
| FailTime     | Shows the total time during which the object was failed ( time ).                                                | StatFailTime [SimTalk]                               |
| F_Mu         | Shows the mean duration of a failure of the object ( time ).                                                     | StatFailMu [SimTalk]                                 |
| F_Delta      | Shows the standard deviation of the failure time from the mean value ( time ).                                   | StatFailDelta [SimTalk]                              |

| Item       | Description                                                                                                                              | Read-only Attribute                  |
|------------|------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
| %age_P     | Shows the ratio of the time during which the object was Paused to the statistics collection period.                                      | StatPausingPortion [SimTalk]         |
| Pauses     | Shows how often the object was paused ( integer ).                                                                                       | StatPausingCount [SimTalk]           |
| PauseTime  | Shows the total time during which the object was paused ( time ).                                                                        | StatPausingTime [SimTalk]            |
| P_Mu       | Shows the mean duration of a pause ( time ).                                                                                             | StatPausingMu [SimTalk]              |
| P_Delta    | Shows the standard deviation of the length of pauses from the mean value ( time ).                                                       | StatPausingDelta [SimTalk]           |
| %age_E     | Shows the ratio of the time during which the object was Empty to the statistics collection period.                                       | StatEmptyPortion [SimTalk]           |
| Empty      | Shows how often the object was empty ( integer ).                                                                                        | StatEmptyCount [SimTalk]             |
| EmptyTime  | Shows the total time during which the object was empty ( time ).                                                                         | StatEmptyTime [SimTalk]              |
| E_Mu       | Shows the mean duration of a time span during which the object was empty ( time ).                                                       | StatEmptyMu [SimTalk]                |
| E_Delta    | Shows the standard deviation of the time spans during which the object was empty to the mean value ( time ).                             | StatEmptyDelta [SimTalk]             |
| %age_WaSU  | Shows the ratio of the time the object was setting-up and for which Exporters were missing to the statistics collection period ( real ). | StatWaitingSetUpExpPortion [SimTalk] |
| WaSetUpExp | Shows how often the object was setting-up, while Exporters were missing ( integer ).                                                     | StatWaitingSetUpExpCount [SimTalk]   |

| Item               | Description                                                                                                                                        | Read-only Attribute                |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| WaSetUpExpTime     | Shows the total time during which the object was setting-up and for which Exporters were missing ( time ).                                         | StatWaitingSetUpExpTime [SimTalk]  |
| WaSUExp_Mu         | Shows the mean duration of a setting-up process for which Exporters were missing ( time ).                                                         | StatWaitingSetUpExpMu [SimTalk]    |
| WaSUExp_Delta      | Shows the standard deviation of a setting-up process for which Exporters were missing ( time ).                                                    | StatWaitingSetUpExpDelta [SimTalk] |
| WaSetUpExpTime(Wa) | Shows the total time during which the object was set-up and waiting and for which Exporters were missing ( time ).                                 | -                                  |
| WaSetUpExpTime(Wo) | Shows the total time during which the object was set-up and processing and for which Exporters were missing ( time ).                              | -                                  |
| WaSetUpExpTime(B)  | Shows the total time during which the object was set-up and blocked and for which Exporters were missing ( time ).                                 | -                                  |
| %_WaExp            | Shows the ratio of the time during which the object was waiting and for which Exporters were missing to the statistics collection period ( real ). | -                                  |
| WaitingExp         | Shows how often the object was waiting, while Exporters were missing ( integer ).                                                                  | -                                  |
| WaitingTimeExp     | Shows the total number of times during which the object was waiting and for which Exporters were missing ( time ).                                 | -                                  |
| WaExp_Mu           | Shows the mean duration of a time span during which the object was waiting and for which Exporters were missing ( time ).                          | -                                  |
| WaExp_Delta        | Shows the standard deviation from the mean value of the                                                                                            | -                                  |

| Item            | Description                                                                                                                                       | Read-only Attribute                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
|                 | waiting times for which Exporters were missing ( time ).                                                                                          |                                                       |
| %age_BExp       | Shows the ratio of the blocking time during which Exporters were missing to the statistics collection period ( real ).                            | -                                                     |
| BlocksExp       | Shows how often the object was blocked, while Exporters were missing ( integer ).                                                                 | -                                                     |
| BlockingTimeExp | Shows the total time during which the object was blocked and for which Exporters were missing ( time ).                                           | -                                                     |
| BExp_Mu         | Shows the mean duration of a blockage of the object for which Exporters were missing ( time ).                                                    | -                                                     |
| BExp_Delta      | Shows the standard deviation of the time spans during which the object was blocked from the mean value for which Exporters were missing ( time ). | -                                                     |
| %age_WaRes      | Shows the time during which the object was waiting for MUs and for Exporters/Services in relation to the statistics collection period ( real ).   | StatWaitingResPortion                                 |
| WaitingRes      | Shows how often the object was blocked and waiting for MUs and for Exporters/Services ( integer ).                                                | StatWaitingResCount [SimTalk] - material flow objects |
| WaitingTimeRes  | Shows the total time during which the object was blocked and was waiting for MUs and for Exporters/Services ( time ).                             | StatWaitingResTime [SimTalk] - material flow objects  |
| WaRes_Mu        | Shows the mean duration of a period of time during which the object was blocked and was waiting for MUs and for Exporters/Services ( time ).      | StatWaitingResMu [SimTalk] - material flow objects    |
| WaRes_Delta     | Shows the mean deviation of the times during which the object was blocked and was waiting for                                                     | StatWaitingResDelta [SimTalk] - material flow objects |

| Item             | Description                                                                                                       | Read-only Attribute             |
|------------------|-------------------------------------------------------------------------------------------------------------------|---------------------------------|
|                  | MUs and for Exporters/Services ( time ).                                                                          |                                 |
| %age_WaParts     | Shows the total time during which the object was waiting for MUs to the statistics collection period ( real ).    | -                               |
| WaitingParts     | how often the object was blocked and was waiting for MUs ( integer ).                                             | StatWaitingPartsCount [SimTalk] |
| WaitingTimeParts | Shows the total time during which the AssemblyStation was blocked and was waiting for MUs ( time ).               | StatWaitingPartsTime [SimTalk]  |
| WaParts_Mu       | Shows the mean duration of a period of time during which the object was blocked and was waiting for MUs ( time ). | StatWaitingPartsMu [SimTalk]    |
| WaParts_Delta    | Shows the mean deviation of the times during which the object was blocked and was waiting for MUs ( time ).       | Animate Every x-th Pixel        |

For the MUs the following restrictions apply:

| Item     | Note                                                                                                                                                                                                  |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Working  | The entries in the columns %age_Wo, Working, WorkingTime, Wo:Mu, and Wo_Delta are always 0 as you cannot set a processing time for MUs that can transport other MUs and these are thus never working. |
| Failures | The entries in the columns %age_F, Failures, FailTime, F_Mu, and F_Delta are always 0 as you cannot fail the receptivity of MUs . Failures of the Transporter only refer to the driving behavior.     |
| Pauses   | The entries in the columns %age_P, Pauses, PauseTime, P_Mu, and P_Delta are always 0 as you cannot pause the receptivity of MUs . Pauses of the Transporter only refer to the driving behavior.       |
| Set-up   | The entries in the columns %age_SU, SetUp, SetUpTime, SU_Mu, SU_Delta, SetupTime(Wa),                                                                                                                 |

| Item   | Note                                                                  |
|--------|-----------------------------------------------------------------------|
|        | SetupTime(Wo), and SetupTime(B) are always 0 as the MU cannot set-up. |

The product statistics table of the MUs shows the following values.

- If you query statistics of a MU class , the values refer to the entire statistics collection period.
- If you query statistics of a individual MU , the values refer to the lifetime of that MU .

| Item      | Description                                                                                                                                                                                                                                                                                                                                                                        | Read-only Attribute                    |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| Name      | Shows the name of the MU the statistical data is interpreted for (data type string ).                                                                                                                                                                                                                                                                                              | -                                      |
| Time      | Shows the current simulation time ( time ).                                                                                                                                                                                                                                                                                                                                        | -                                      |
| Start (P) | Shows the time at which the product statistics collection of the object started ( time ).                                                                                                                                                                                                                                                                                          | -                                      |
| %age_P_IP | Shows the time portion during which the MU was located on a material flow object of type Production and was processed. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period. | StatProdWorkingPortion [SimTalk] - MUs |
| %age_P_SU | Shows the time portion during which a resource of type Production was setting-up for this MU ( real ).                                                                                                                                                                                                                                                                             | StatProdSetupPortion [SimTalk] - MUs   |
| %age_P_Wa | Shows the time portion during which the MU was located on a material flow object of type Production and was waiting. The sum of the columns %age_P_Wa , %age_P_IP ,                                                                                                                                                                                                                | StatProdWaitingPortion [SimTalk] - MUs |

| Item       | Description                                                                                                                                                                                                                                                                                                                                                                                | Read-only Attribute                    |
|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
|            | %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period.                                                                                                                                                                               |                                        |
| %age_P_Stp | Shows the time portion during which the MU was located on a material flow object of type Production and was stopped. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period.           | StatProdStoppedPortion [SimTalk] - MUs |
| %age_P_F   | Shows the time portion during which the MU was located on a material flow object of type Production and was in a failed state. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period. | StatProdFailPortion [SimTalk] - MUs    |
| %age_P_P   | Shows the time portion during which the MU was located on a material flow object of type Productio n and was in a paused state. The sum of the columns %age_P_Wa , %age_P_IP , %age_P_Stp , %age_P_F , and                                                                                                                                                                                 | StatProdPausingPortion [SimTalk] - MUs |

| Item       | Description                                                                                                                                                                                                                                                                                                                                                         | Read-only Attribute                      |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|
|            | %age_P_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Production to the entire statistics collection period.                                                                                                                                                                                    |                                          |
| %age_T_IP  | Shows the time portion during which the MU was located on a material flow object of type Transport and was processed. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period. | StatTranspPausingPortion [SimTalk] - MUs |
| %age_T_SU  | Shows the time portion during which a resource of type Transport was setting-up for this MU ( real ).                                                                                                                                                                                                                                                               | StatTranspSetupPortion [SimTalk] - MUs   |
| %age_T_Wa  | Shows the time portion during which the MU was located on a material flow object of type Transport and was waiting. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period.   | StatTranspWaitingPortion [SimTalk] - MUs |
| %age_T_Stp | Shows the time portion during which the MU was located on a material flow object of type Transport and was stopped. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the                                                                                                                                                                   | StatTranspStoppedPortion [SimTalk] - MUs |

| Item      | Description                                                                                                                                                                                                                                                                                                                                                                          | Read-only Attribute                      |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|
|           | Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period.                                                                                                                                                                                                                      |                                          |
| %age_T_F  | Shows the time portion during which the MU was located on a material flow object of type Transport and was in a failed state. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period ( real ). | StatTranspFailPortion [SimTalk] - MUs    |
| %age_T_P  | Shows the time portion during which the MU was located on a material flow object of type Transport and was in a paused state. The sum of the columns %age_T_Wa , %age_T_IP , %age_T_F , and %age_T_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Transport to the entire statistics collection period ( real ). | StatTranspPausingPortion [SimTalk] - MUs |
| %age_S_IP | Shows the time portion during which the MU was located on a material flow object of type Storage and was processed. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object                                                                                  | StatStoreWorkingPortion [SimTalk] - MUs  |

| Item       | Description                                                                                                                                                                                                                                                                                                                                                             | Read-only Attribute                     |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|
|            | of type Storage to the entire statistics collection period.                                                                                                                                                                                                                                                                                                             |                                         |
| %age_S_SU  | Shows the time portion during which a resource of type Storage was setting-up for this MU ( real ).                                                                                                                                                                                                                                                                     | StatStoreSetupPortion [SimTalk] - MUs   |
| %age_S_Wa  | Shows the time portion during which the MU was located on a material flow object of type Storage and was waiting. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.           | StatStoreWaitingPortion [SimTalk] - MUs |
| %age_S_Stp | Shows the time portion during which the MU was located on a material flow object of type Storage and was stopped. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period.           | StatStoreStoppedPortion [SimTalk] - MUs |
| %age_S_F   | Shows the time portion during which the MU was located on a material flow object of type Storage and was in a failed state. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period. | StatStoreFailPortion [SimTalk] - MUs    |

| Item                   | Description                                                                                                                                                                                                                                                                                                                                                                      | Read-only Attribute                     |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------|
| %age_S_P               | Shows the time portion during which the MU was located on a material flow object of type Storage and was in a paused state. The sum of the columns %age_S_Wa , %age_S_IP , %age_S_F , and %age_S_P of the Product Statistics Table shows the ratio of the time the MU was located on a material flow object of type Storage to the entire statistics collection period ( real ). | StatStorePausingPortion [SimTalk] - MUs |
| Count                  | Shows the number of existing MU instances of this class with product statistics on. The MUs may be located in different Frame hierarchies ( integer ).                                                                                                                                                                                                                           | StatCount [SimTalk]                     |
| Deleted                | Shows the number of MUs , which were removed from the installation during statistics collection of the class. Plant Simulation only counts MUs for which you selected the check box Product statistics .                                                                                                                                                                         | StatDeleted [SimTalk] - MUs             |
| avgLT/Average Lifespan | Shows the average life-span of MUs , which were created and removed from the installation during the statistics collection period. Plant Simulation only counts MUs for which you selected the check box Product statistics .                                                                                                                                                    | StatAvgLifeSpan [SimTalk] - MUs         |

The driving statistics table of the Transporter shows these values:

| Item   | Description                                                                                      | Read-only Attribute   |
|--------|--------------------------------------------------------------------------------------------------|-----------------------|
|        | Shows the name of the object for which the statistical data of the row are evaluated ( string ). | Name -                |
| Time   | Shows the current simulation time ( time ).                                                      | -                     |

| Item        | Description                                                                                                     | Read-only Attribute                                            |
|-------------|-----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| OrderOcc    | Shows the ratio of the time during which the Transporter had an order and was loaded to the life-span ( real ). | StatOrderOccTime [SimTalk] StatOrderOccPortion [SimTalk]       |
| OrderEmpty  | Shows the ratio of time during which the Transporter had an order and was not loaded to the life-span ( real ). | StatOrderEmptyTime [SimTalk] StatOrderEmptyPortion [SimTalk]   |
| Home        | the ratio of the time during which the Transporter was returning to its base to the life- span ( real ).        | StatHomeDrivingTime [SimTalk] StatHomeDrivingPortion [SimTalk] |
| Charges     | Shows how often the battery was charged ( integer ).                                                            | StatBatChargeCount [SimTalk]                                   |
| %age_C      | the ratio of the time during which the battery of the Transporter was charging to the life-span.                | StatBatChargePortion [SimTalk]                                 |
| Tsp%age_F   | Shows the ratio of the time during which the Transporter was in a failed state to the life-span ( real ).       | ShiftCalendarObject [SimTalk] - Frame                          |
| TspFailures | Shows the number of failures during the total life-span ( integer ).                                            | StatTspFailCount [SimTalk]                                     |
| TspFailTime | Shows the sum of all failure times during the total life-span of the Transporter ( time ).                      | StatTspFailTime [SimTalk]                                      |
| TspF_Mu     | Shows the mean duration of a failure ( time ).                                                                  | StatTspFailMu [SimTalk]                                        |
| TspF_Delta  | Shows the standard deviation from the mean value ( time ).                                                      | StatTspFailDelta [SimTalk]                                     |
| Tsp%ageP    | Shows the ratio of the time during which the Transporter was paused to the total life-span ( real ).            | StatTspPausingPortion [SimTalk]                                |

| Item         | Description                                                        | Read-only Attribute            |
|--------------|--------------------------------------------------------------------|--------------------------------|
| TspPauses    | Shows the number of pauses during the total life-span ( integer ). | StatTspPausingCount            |
| TspPauseTime | Shows the sum of all pause-times of the Transporter ( time ).      | StatTspPausingTime             |
| TspP_Mu      | Shows the mean duration of a pause ( time ).                       | StatTspPausingMu [SimTalk]     |
|              | the standard deviation from the mean value ( time ).               | TspP_Delta StatTspPausingDelta |

**Methods of the Importer**

##### \_Methods of the Importer

The Importer of some of the material flow and fluid objects provides the methods listed in the table of contents.

**Remarks**

At the moment only these objects can import services. You can define them on the subtabs of the Tab Importer .

- The material flow objects Source , Drain , Station , ParallelStation , AssemblyStation , DismantleStation , PickAndPlace Robot , Store , Buffer , PlaceBuffer , Sorter and Conveyor .
- The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

Imp , SetupImp , FailImp , and TransportImp are boolean read-only attributes.

If an object does not have any Importer at all, the object does not provide the attributes Imp , SetupImp , FailImp , and TransportImp .

If the object has at least one Importer , the object provides all four attributes. The attribute returns true if the object has that type of Importer , otherwise false.

**Note**

The attribute returns true even if the Importer is not active.

Use Imp.Active to check if the respective Importer is active or not.

**Imp [SimTalk]**

Plant Simulation addresses processing-importer methods as sub-methods of Imp .

**Note**

In a control the number 2 designates the processing-importer .

**Example**

ParallelStation.Imp.releaseExporters

**SetupImp [SimTalk]**

Plant Simulation addresses setup-importer methods as sub-methods of SetupImp .

The setup-importer shares all attributes and methods with the processing-importer . The only exception are the set-up services.

**Note**

In a control the number 1 designates the set-up-importer .

**Example**

MyAssembly.SetupImp.getServices

**FailImp [SimTalk]**

Plant Simulation addresses failure-importer methods as sub-methods of FailImp .

**Note**

In a control the number 0 designates the failure-importer .

**Example**

MyStation.FailImp.releaseExporters

**TransportImp [SimTalk]**

Plant Simulation addresses transport-importer methods as sub-methods of TransportImp .

<!-- image -->

**Example**

MyRemovalStation.TransportImp.setServices(TransportServices)

The window Show Attributes and Methods only shows the identifiers Imp , SetupImp , FailImp , and TransportImp for the Importer , but not the actual methods for these importer types .

<!-- image -->

**See also**

**Tab Importer**

Attributes of the Importer

###### getAlternativeServices [SimTalk]

getAlternativeServices [SimTalk]

Returns the different alternatives for the services of the Importer of the object designated by &lt;Path&gt; and writes them into a table.

Remarks

At the moment only these objects can import services.

The Material Flow Objects AssemblyStation , the Conveyor , the DismantleStation , the Drain , the ParallelStation , the Source , and the Station .

The Fluid Objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.getAlternativeServices(Services:table) < Path >.SetupImp.getAlternativeServices(Services:table) < Path >.FailImp.getAlternativeServices(Services:table)
```

**Parameter**

The parameter Services of data type table designates the name of an unformatted table (a table in a Frame or a local table).

- The main table contains the name of the alternatives.
- The subtable has two columns.
- Column 1 contains the name of the Service ( string ).
- Column 2 contains the amount of services to be provided ( integer ).

**Example**

Station11.Imp.getAlternativeServices(myImpAltServicesList) ParallelStation.SetupImp.getAlternativeServices(mySetupImpAltServicesList)

**See also**

Services for Processing Services for Setting-up Services for Repairing setAlternativeServices [SimTalk]

**getExporters [SimTalk]**

###### getExporters [SimTalk]

Returns all Exporters providing services for the Importer of the object designated by &lt;Path&gt;.

Remarks

At the moment only these objects can import services.

The Material Flow Objects AssemblyStation , the Conveyor , the DismantleStation , the Drain , the ParallelStation , the Source , and the Station .

The Fluid Objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.getExporters([Exporters:table])
-> void/array < Path >.FailImp.getExporters([Exporters:table])
-> void/array < Path >.SetupImp.getExporters([Exporters:table])
-> void/array < Path >.TransportImp.getExporters([Exporters:table])
-> void/array
```

**Parameter**

The optional parameter Exporters of data type table designates the name of the table into which the Exporters will be written.

Return Value

Specify the optional parameter Exporters to write them to this table.

Do not specify the parameter to write the Exporters to an array of data type object .

Example

```simtalk
-- writes the Exporters into the specified table MyStation.FailImp.getExporters(myExporterListFailImp) ParallelStation.Imp.getExporters(myExporterListImp) MyStation.SetupImp.getExporters(myExporterListSetupImp) MyStation1.TransportImp.getExporters(myExporterListTranspImp) -- writes the Exporters to an array
```

MyStation.FailImp.getExporters ParallelStation.Imp.getExporters MyStation.SetupImp.getExporters MyStation1.TransportImp.getExporters

**See also**

**Exporters [on View menu]**

**getImportedServices [SimTalk]**

###### getImportedServices [SimTalk]

Returns all services provided for the Importer of the object designated by &lt;Path&gt;, and writes them into a table.

**Remarks**

At the moment only these objects can import services.

The Material Flow Objects AssemblyStation , the Conveyor , the DismantleStation , the Drain , the ParallelStation , the Source , and the Station .

The Fluid Objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.getImportedServices(Services:table) < Path >.SetupImp.getImportedServices(Services:table) < Path >.FailImp.getImportedServices(Services:table) < Path >.TransportImp.getImportedServices(Services:table)
```

**Parameter**

The parameter Services of data type table designates the name of the table.

The name of the service is identical with the name of the subtable.

The subtable has two columns.

- Column 1 contains the name of the Exporter ( string ).
- Column 2 contains the number of the services provided ( integer ).

**Example**

MyStation.FailImp.getImportedServices(myImportedServicesListFailImp) ParallelStation.SetupImp.getImportedServices(myImportedServicesListImp)

**See also**

**Services [on View menu]**

###### getServices [SimTalk] - importer

getServices [SimTalk] - importer

Returns all services of the Importer of the object designated by &lt;Path&gt;, and writes them into a table.

**Remarks**

For the transport importer you can only request one service with the Amount 1 at a time. For this reason the returned table only has one column. If the table contains more than one row, each of them is an Alternative of its own.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.getServices(Services:table) < Path >.SetupImp.getServices(Services:table) < Path >.FailImp.getServices(Services:table) < Path >.TransportImp.getServices(Services:table)
```

**Parameter**

The parameter Services of data type table designates the name of an unformatted table (a table in a Frame or a local table) with three columns:

- Column 1 contains the name of the service ( string ).
- Column 2 contains the number of the required services ( integer ).
- Column 3 contains the name of the alternative service ( string ).

**Examples**

```simtalk
var servicesTable: table[string,integer,string]
Station.Imp.getServices(servicesTable)
```

servicesTable.delete switch @.Name case "PartA" servicesTable.writeRow(1,1, "ServiceA",2) case "PartB" servicesTable.writeRow(1,1, "ServiceB",1) case "PartC" servicesTable.writeRow(1,1, "ServiceA",1) servicesTable.writeRow(1,2, "ServiceB",1) end Station.Imp.setServices(servicesTable) end

Station13.FailImp.getServices(myServicesListFailImp) ParallelStation.SetupImp.getServices(myServicesListSetupImp)

**SimTalk**

setServices [SimTalk] - importer

See also

Services for Processing

Services for Setting-up

Services for Repairing

Services for Carrying Parts Away [transport importer]

**getUnavailableServices [SimTalk]**

###### getUnavailableServices [SimTalk]

Returns all services which the Importer of the object designated by &lt;Path&gt; requested and which are unavailable at the moment, and writes them into a table.

**Remarks**

At the moment only these objects can import services.

The Material Flow Objects AssemblyStation , the Conveyor , the DismantleStation , the Drain , the ParallelStation , the Source , and the Station .

The Fluid Objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.getUnavailableServices(Services:table) < Path >.SetupImp.getUnavailableServices(Services:table) < Path >.FailImp.getUnavailableServices(Services:table) < Path >.TransportImp.getUnavailableServices(Services:table)
```

**Parameter**

The parameter Services of data type table designates the name of the table.

The name of the service is identical with the name of the subtable.

The subtable has four columns and shows the Name of the Exporter , the Amount of services defined, the Amount of unavailable services, and the Name of the associated Alternative .

The table shows the name of the unavailable service white on a red background in the respective cell.

**Example**

MyStation.FailImp.getUnavailableServices(myUnavailableFailServices) ParallelStation.SetupImp.getUnavailableServices(myUnavailableSetupServices)

**See also**

**Unavailable Services [on View menu]**

###### import [SimTalk] - importer

import [SimTalk] - importer

Starts a query with the Broker you specified as the Broker for the Importer of the object designated by &lt;Path&gt;.

Remarks

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

**Note**

If you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for fixing the failure, you have to use the method &lt;name of the station&gt;.FailImp.import .

If you requested the service for removing the failure with the method &lt;name of the station&gt;.FailImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.FailImp. releaseExporters .

If the Importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

Type

Method

Syntax

```simtalk
< Path >.Imp.import([MU:object[ ,Exporters:any]) → boolean < Path >.FailImp.import([MU:object[, Exporters:any]) → boolean < Path >.SetupImp.import([MU:object[, Exporters:any]) → boolean < Path >.SetupImp.import([SetupType:string[, Exporters:any]) → boolean < Path >.TransportImp.import([MU:object[, Exporters:any]) → boolean
```

**Parameters**

- The optional parameter MU of data type object designates the MU for which the Workers/Exporters are requested.

As a rule only the import for setting-up requires the MU .

For setting-up we offer the optional parameter SetupType of data type string . This is, for example, required when you work with the method setupFor .

- The optional parameter Exporters of data type table designates a table. If the request was successful (return value true), the table will contain all Workers/Exporters assigned to the Importer .

Return Value

The return value has the data type boolean .

true if Workers/Exporters were successfully assigned to the Importer .

false if Workers/Exporters were not assigned to the Importer .

**Example**

MyStation.FailImp.import ParallelStation.Imp.import(Part, ExpTable)

**SimTalk**

releaseExporters [SimTalk]

startProcessing [SimTalk] - importer

See also

Broker [failure importer]

**importExporter [SimTalk]**

###### importExporter [SimTalk]

Returns if the Importer of the object designated by &lt;Path&gt; successfully brokered the Workers/Exporters (true) or not (false).

Remarks

Use the method importExporter in the Request Control of the Importer .

**Note**

The Broker does not save a failed mediation. You thus have to check beforehand if the Workers/Exporters can be brokered and you yourself have to start another attempt to broker the Workers/Exporters .

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.importExporter(Worker:object/Workers:array[, MU:object]) → boolean < Path >.SetupImp.importExporter(Worker:object/Workers:array[, MU:object]) → boolean
```

**Parameters**

- The parameter Worker of data type object designates a single specific Worker/Exporter .

The parameter Workers of data type array designates several Workers/Exporters .

**Note**

Plant Simulation brokers the Workers/Exporters specified in the array from back to front, meaning the last Worker/Exporter first. This is important if the Workers/Exporters offer different services.

- The optional parameter MU of data type object designates the MU for which the Worker/Exporter was requested.

Return Value

The return value has the data type boolean .

true if the Workers/Exporters were successfully brokered.

false if the Workers/Exporters were not brokered.

**Example**

MyStation.Imp.importExporter(MyWorker:1) ParallelStation.SetupImp.importExporter([MyWorker:1, MyWorker:2])

**releaseExporters [SimTalk]**

###### releaseExporters [SimTalk]

Releases the Exporters assigned to the Importer of the object designated by &lt;Path&gt;.

Remarks

The station will finish processing the MUs it is Working on at the moment.

The call does not affect events of type SetupEnd and Out .

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

**Note**

If you requested the service for removing the failure with the method &lt;name of the station&gt;.FailImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.FailImp.releaseExporters .

Type

Method

Syntax

< Path >.Imp.releaseExporters < Path >.FailImp.releaseExporters < Path >.SetupImp.releaseExporters < Path >.TransportImp.releaseExporters

**Example**

MyStation.FailImp.releaseExporters ParallelStation.setUpImp.releaseExporters

MyAssembly.Imp.releaseExporters

SimTalk import [SimTalk] - importer stopProcessing [SimTalk] releaseExporters [SimTalk] See also

Working [state, material flow objects]

**setAlternativeServices [SimTalk]**

###### setAlternativeServices [SimTalk]

Sets the alternative services which the Importer of the object designated by &lt;Path&gt; requests.

**Remarks**

**Note**

The method setServices accomplishes the same.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.setAlternativeServices(Services:table) < Path >.SetupImp.setAlternativeServices(Services:table) < Path >.FailImp.setAlternativeServices(Services:table)
```

Parameter

The parameter Services of data type table designates the name of the table of the alternative services.

The subtable has two columns.

- Column 1 contains the name of the Service ( string ).
- Column 2 contains the Amount of services to be provided ( integer ). The Importer requires all services of a single alternative at the same time.

**Example**

Station11.Imp.setAlternativeServices(MyServicesTable) ParallelStation.SetupImp.setAlternativeServices(MySetupServices) MyAssembly.FailImp.setAlternativeServices(MyFailureServices)

**SimTalk**

getAlternativeServices [SimTalk]

setServices [SimTalk] - importer

See also

Data Held in Tabular Form in Attributes [material flow objects]

Services for Processing

Services for Setting-up

Services for Repairing

###### setServices [SimTalk] - importer

Sets the services which the Importer of the object designated by &lt;Path&gt; requests.

**Remarks**

**Note**

The method setAlternativeServices accomplishes the same.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.setServices(Services:table) < Path >.SetupImp.setServices(Services:table) < Path >.FailImp.setServices(Services:table) < Path >.TransportImp.setServices(Services:table)
```

**Parameter**

The parameter Services of data type table designates the name of the table in which you defined the services.

The table has three columns.

- Column 1 contains the name of the Service ( string ).
- Column 2 contains the Amount of services to be provided ( integer ).
- Column 3 contains the name of the Alternative service ( string ). The Importer requires that all services of a single alternative are present at the same time.

To execute the setting-up , processing , or repairing jobs, the Importer always requires all services of an Alternative . If, for example, the Importer does not have all services of Alternative1 , he attempts to get all services of Alternative2 , etc. For successive services in the table, which all belong to the same alternative, the name of the alternative is only shown after the first service on the table.

<!-- image -->

For the transport importer you can only request one service with the Amount 1 at a time. For this reason you can only assign a table with one column. If you enter more than one service, each of these services is an Alternative of its own.

<!-- image -->

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Examples**

Station1.Imp.setServices(MyServicesTable) ParallelStation.SetupImp.setServices(MySetupServices) dismantle.FailImp.setServices(MyFailureServices) MyStation1.TransportImp.setServices(MyTransportServices)

```simtalk
var servicesTable: table[string,integer,string]
Station.Imp.getServices(servicesTable)
servicesTable.delete
switch
	@.Name
case "PartA"
	servicesTable.writeRow(1,1, "ServiceA",2)
case "PartB"
	servicesTable.writeRow(1,1, "ServiceB",1)
case "PartC"
	servicesTable.writeRow(1,1, "ServiceA",1)
	servicesTable.writeRow(1,2, "ServiceB",1)
end
Station.Imp.setServices(servicesTable)
end
var servTab:table --[string,integer,string]
servTab.create
M.imp.getServices(servtab)
servtab.delete
switch
	@.name
case "A"
	servTab.writeRow(1,1, "ServA",2)
case "B"
	servTab.writeRow(1,1, "ServB",1)
case "C"
	servTab.writeRow(1,1, "ServA",1)
	servTab.writeRow(1,2, "ServB",1)
end
M.imp.setServices(servtab)
```

**SimTalk**

```simtalk
getServices [SimTalk] - importer setAlternativeServices [SimTalk] See also Data Held in Tabular Form in Attributes [material flow objects] Services for Processing
```

Services for Setting-up Services for Repairing Services for Carrying Parts Away [transport importer]

startProcessing [SimTalk] - importer

Starts processing the MU for which the Importer of the object designated by &lt;Path&gt; requested Exporters .

Remarks

After processing has started the appropriate Out event is registered.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.startProcessing
-> boolean < Path >.FailImp.startProcessing
-> boolean < Path >.TransportImp.startProcessing
-> boolean
```

**Parameter**

The parameter of data type boolean starts processing anew from the start after an interruption ( true ) or not ( false ).

Return Value

The return value has the data type boolean .

false if processing cannot be started, because not all of the required services are available.

**Example**

MyStation.FailImp.startProcessing ParallelStation.Imp.startProcessing(true) MyAssembly.FailImp.startProcessing

DismantleStation.Imp.startProcessing(true) Station.TransportImp.startProcessing DePortioner.TransportImp.startProcessing(true)

SimTalk getServices [SimTalk] - importer stopProcessing [SimTalk] startSetup [SimTalk] See also Data Held in Tabular Form in Attributes [material flow objects] Services for Processing Services for Setting-up Services for Repairing

**startSetup [SimTalk]**

###### startSetup [SimTalk]

Makes the setup importer start setting the object designated by &lt;Path&gt; up for the MU for which the Exporter was requested.

Remarks

After starting setting-up the appropriate SetupEnd event is registered.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.SetupImp.startSetup([StartAnewContinue:boolean]) → boolean
```

**Parameter**

The optional parameter StartAnewContinue of data type boolean sets if setting-up starts anew after an interruption ( true ) or if setting-up continues where it stopped before the interruption ( false ).

Return Value

The return value has the data type boolean .

false if set-up cannot be started, because not all the required services are available.

**Example**

ParallelStation.SetupImp.startSetup dismantle.SetupImp.startSetup(true)

**SimTalk**

startProcessing [SimTalk] - importer

stopProcessing [SimTalk]

See also

Services for Setting-up

**stopProcessing [SimTalk]**

###### stopProcessing [SimTalk]

Makes the Importer stop processing the MU that is located on the object designated by &lt;Path&gt;.

**Remarks**

After processing was stopped stopProcessing returns the material flow object to the state waiting for an Importer . At the same time, the service is returned to the Exporter and the Broker can broker this service anew.

Use stopProcessing to release the service that is Working at the moment, and provide it for the Importer of an object, with a higher Priority and which requires the same service. If no other Importer has a higher Priority , than the active one, the service is reassigned to this object again.

**Note**

At the moment only these objects can import services.

The material flow objects AssemblyStation , Conveyor , DismantleStation , Drain , ParallelStation , Source , and Station .

The fl uid objects DePortioner , Mixer , ContinuousMixer , Portioner , and Tank .

You can define them on the Tab Importer .

Type

Method

Syntax

```simtalk
< Path >.Imp.stopProcessing < Path >.FailImp.stopProcessing < Path >.TransportImp.stopProcessing
```

**Example**

```simtalk
Station1.Imp.stopProcessing
```

SimTalk

startProcessing [SimTalk] - importer

startSetup [SimTalk]

**See also**

**Working [state, material flow objects]**

**Priority [processing importer]**

##### Methods of Sensors

###### \_Methods of Sensors

The length-oriented objects Conveyor , Track , TwoLaneTrack , Turntable , and Transporter provide the methods listed in the table of contents to the left for creating and manipulating Sensors .

**Note**

For the loading space of the Transporter , the window Show Attributes and Methods , which you can open by pressing the F8 key, only shows the attributes and methods pertaining to the selected Type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

**\_Methods of Sensors**

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

See also

Attributes of the Sensors

Read-Only Attributes of the Sensors

###### createSensor [SimTalk] - material flow objects

Creates a new sensor on the object designated by &lt;Path&gt;.

**Remarks**

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Method

Syntax

```simtalk
< Path >.createSensor([Position:real, PositionType:string, Control:method, Front:boolean, Rear:boolean, Destination:Path, BothLanes:boolean, LightBarrierMode:boolean]) → integer
```

**Parameters**

The sensor is defined by these parameters:

- The optional parameter Position of data type real designates the position. The values you can specify depend on the parameter PositionType you specify.
- The optional parameter PositionType of data type string designates the type of position: "Relative" , "Length" , "Relative from end" , or "Length from end" .
- The optional parameter Control of data type method designates the name of the Method object that the Sensor triggers.

You can specify the name of the method as a string, i.e., "myMethod" or you can specify &amp;myMethod .

- The optional parameter Front of data type boolean sets if the front of the MU is going to activate the sensor ( true ) or not ( false ).

**Note**

If you want to create a sensor, which is going to be triggered by the Booking Point of the MU , you first have to create the sensor with the optional parameter Front . After that, you can set that the created sensor is triggered by the Booking Point with the attribute BookPosition of the created sensor.

- The optional parameter Rear of data type boolean sets if the rear of the MU is going to activate the sensor ( true ) or not ( false ).

**Note**

If you want to create a sensor, which is going to be triggered by the Booking Point of the MU , you first have to create the sensor with the optional parameter Front . After that, you can set that the created sensor is triggered by the Booking Point with the attribute BookPosition of the created sensor.

- The optional parameter Destination of data type path sets sensor activation to Only when Destination and specifys the object, which you specify, as the Destination . When VOID is passed, the setting will be Always .
- The optional parameter BothLanes of data type boolean sets if the sensor will also be created on the other lane of the TwoLaneTrack , i.e., if the object creates a sensor on both lanes.
- The optional parameter LightBarrierMode of data type boolean designates that a light-barrier is going to activate the sensor ( true ) or not ( false ).

If you do not specify any parameters, Plant Simulation creates the sensor with these default settings:

(0,"Length",VOID,true,false,VOID,false) , i.e., the position is 0, does not trigger a method and is activated by the Front of the MU .

**Return Value**

The return value has the data type integer .

It is the unique number of the sensor. You can use this number to access the sensor.

**Examples**

MyTwoLaneTrack.B.createSensor(1,"Length","MyCtrl",true,false,VOID,false)

MyConveyor.createSensor(1,"Length from end","MyCtrl",true,false,VOID,false)

```simtalk
.MUs.Transporter:1.LoadBayType := "Track" .MUs.Transporter:1.createSensor(0.5,"Length","MyControl",true,false,VOID,fal se,false)
var ID1,ID2: integer
ID1 := MyTrack.createSensor(0.5,"Relative","SensCtrl",true,false)
ID2 := MyTrack.createSensor(0.7,"Relative",&myMethod,false,true)
MyTrack.sensorID(ID2).BookPosition := true // booking point triggers the sensor
```

SimTalk deleteSensor [SimTalk] - material flow objects BookPosition [SimTalk] See also Sensors [general description] New [sensor]

Type [loading space]

deleteSensor [SimTalk] - material flow objects

Deletes the specified sensor from the object designated by &lt;Path&gt;.

Remarks

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Method

Syntax

```simtalk
< Path >.deleteSensor(SensorID:integer)
```

Parameter

The parameter SensorID of data type integer designates the sensors.id .

Examples

MyTrack.deleteSensor(2)

```simtalk
.MUs.Transporter:1.deleteSensor(1)
var oClass,iObj:object
oClass := ~.Conveyor
for var n := oClass.numSensors downto 1
	oClass.deleteSensor(oClass.sensorNo(n).ID)
next
```

SimTalk

createSensor [SimTalk] - material flow objects

sensors.id [SimTalk] - material flow objects

See also

Delete [sensor]

**Sensors [general description]**

existsSensorID [SimTalk] - material flow objects

Returns if the specified sensor of the object designated by &lt;Path&gt; exists ( true ) or does not exist ( false ).

Remarks

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Method

Syntax

&lt; Path &gt;.existsSensorID(SensorID:integer) → boolean

Parameter

The parameter SensorID of data type integer designates the Sensors.ID .

Return Value

The return value has the data type boolean .

Examples

print MyConveyor.existsSensorID(1)

```simtalk
print .MUs.Transporter:1.existsSensorID(2)
```

SimTalk

sensors.id [SimTalk] - material flow objects

###### sensorID [SimTalk] - material flow objects

Returns the specified sensor of the object designated by &lt;Path&gt;.

Remarks

**Note**

The methods sensorNo(SensorID:integer) and sensorID(SensorID:integer) can reference different sensors.

**Note**

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading space types &gt; Track or Line !

Type

Method

Syntax

```simtalk
< Path >.sensorID(SensorID:integer) → any
```

Parameter

The parameter SensorID of data type integer designates the unique Sensor-ID which Plant Simulation assigns when you create the sensor.

Return Value

The return value has the data type any .

Examples

```simtalk
MyTrack.sensorID(3).Front := true
MyTwoLaneTrack.A.sensorID(1).Front := true
.MUs.Transporter:1.sensorID(2).Rear := true
```

SimTalk sensors.id [SimTalk] - material flow objects existsSensorID [SimTalk] - material flow objects sensorNo [SimTalk] - material flow objects See also Sensors [general description]

**New [sensor]**

###### sensorNo [SimTalk] - material flow objects

Returns a sensor of the object designated by &lt;Path&gt; whose unique identifier ( sensors.id ) you do not know.

Remarks

**Note**

The methods sensorNo(SensorNumber:integer) and sensors.id can reference different sensors.

**Note**

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Method

Syntax

```simtalk
< Path >.sensorNo(SensorNumber:integer) → object
```

Parameter

The parameter SensorNumber of data type integer can be a value between 1 and the number of sensors.

Which sensor Plant Simulation returns may change during the simulation, i.e., if existing sensors are deleted. Thus, only use the method sensorNo if a method call iterates through all sensors of the object.

Return Value

The return value has the data type object .

Examples

```simtalk
var i: integer
for var i := 1 to Track.NumSensors
	Track.sensorNo(i).Front := true
next
.MUs.Transporter:1.Sensors.id1.Rear := true
```

SimTalk sensors.id [SimTalk] - material flow objects See also Sensors [general description]

###### sensors.id [SimTalk] - material flow objects

Returns the specified sensor of the object designated by &lt;Path&gt;.

Remarks

Creating and manipulating sensors via SimTalk for the loading space of the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Method

Syntax

< Path >.sensors.id<Number> → any

Parameter

The parameter number after the id designates the unique identifier which Plant Simulation assigns when you create the sensor.

Return Value

The return value has the data type any .

Examples

```simtalk
MyTrack.sensors.id3.Front := true
var sensor := MyTrack.sensors.id2
sensor.Front := true
```

SimTalk

deleteSensor [SimTalk] - material flow objects

existsSensorID [SimTalk] - material flow objects

See also

Sensors [general description]

**Methods of Curved Objects in 2D**

##### \_Methods of Curved Objects in 2D

The curved objects provide the methods listed in the table of contents to the left for modifying the settings for curved and straight segments.

The curved objects AngularConverter , Conveyor , Track , TwoLaneTrack , Turntable , FootPath , and Pipe provide the methods listed in the table of contents to the left for modifying the settings for curved and straight segments, when you activated Curve mode.

You define the properties of the curved and straight segments of the objects on the tab Curve .

<!-- image -->

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**See also**

**\_Attributes of the Curved Objects in 2D**

**Tab Curve**

getCurveSegments [SimTalk]

Gets the segments table of the curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.getCurveSegments(Table:table)

Parameter

The parameter Table of data type table designates the table into which Plant Simulation writes the settings of the segment table.

**Note**

The definition of the segments table always shows the original orientation of the segments without a possible rotation or mirroring.

The rotation is stored in the attribute ObjectAngle and mirroring is stored in the attribute ObjectMirrored . This enables retaining inheritance of the definition of the segments even if one or more segments are rotated or mirrored.

**Example**

MyConveyor.getCurveSegments(MyCurveSegmentsTable)

SimTalk

setCurveSegments [SimTalk]

\_3D.getExtSegments [SimTalk]

ObjectAngle [SimTalk] - material flow objects

ObjectMirrored [SimTalk] - material flow objects See also Segments [curve] - 2D, described Reuse the Segments of a Length-oriented Object Tab Curve [general description] Segments [tab Appearance] - 3D

mirrorX [SimTalk] - material flow objects

Flips the curved object designated by &lt;Path&gt; on the X-axis.

Remarks

Note

A 3D Only model does not provide this method.

Plant Simulation mirrors the curved object vertically and thus reverses top and bottom.

Type

Method

Syntax

&lt; Path &gt;.mirrorX

Example

MyTurntable.mirrorX

See also

Mirror Vertically

mirrorY [SimTalk] - material flow objects

Flips the curved object designated by &lt;Path&gt; on the Y-axis.

Remarks

Note

A 3D Only model does not provide this method.

Plant Simulation mirrors the curved object horizontally and thus reverses left and right.

Type

Method

Syntax

&lt; Path &gt;.mirrorY

Example

MyTurntable.mirrorY

See also

Mirror Horizontally

reverse [SimTalk]

Reverses the direction of motion of the curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this method.

Syntax

&lt; Path &gt;.reverse

Type

Method

Example

Conveyor.reverse

See also

Reverse [segment, 2D]

Reverse [segment, 3D]

rotate [SimTalk] - curved object

Rotates the curved object designated by &lt;Path&gt; clockwise.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.rotate(Angle:real)

Parameter

The parameter Angle of data type real designates the number of degrees around which a single rotation step rotates the object.

Example

MyTrack.rotate(45)

SimTalk

getCurveSegments [SimTalk]

setCurveSegments [SimTalk]

See also

Rotate Icon setCurveSegments [SimTalk]

Sets the segments table of the curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.setCurveSegments(Table:table)

Parameter

The parameter Table of data type table designates the table from which Plant Simulation imports the settings of the segment table.

**Note**

The definition of the segments table always shows the original orientation of the segments without a possible rotation or mirroring.

The rotation is stored in the attribute ObjectAngle and mirroring is stored in the attribute ObjectMirrored . This enables retaining inheritance of the definition of the segments even if one or more segments are rotated or mirrored.

**Example**

MyConveyor.setCurveSegments(MyCurveSegmentsTable)

SimTalk

getCurveSegments [SimTalk]

\_3D.setExtSegments [SimTalk]

ObjectAngle [SimTalk] - material flow objects

ObjectMirrored [SimTalk] - material flow objects See also Segments [curve] - 2D, described Reuse the Segments of a Length-oriented Object Tab Curve [general description]

Segments [tab Appearance] - 3D

Methods for the Workplace

Methods of the Workplace

The material flow objects that support an importer , i.e., the Station , the ParallelStation , the AssemblyStation , the DismantleStation , the Mixer , the Portioner , the DePortioner , and the Tank provide the method assignedWorkplaces for the Workplace which you can assign to them.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

###### Methods of the Workplace

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### assignedWorkplaces [SimTalk]

Returns the Workplaces assigned to the object designated by &lt;Path&gt; and writes them to a table (an object or a local variable).

Type

Method

Syntax

```simtalk
< Path >.assignedWorkplaces([Workplaces:table])
-> any
```

Parameter

The optional parameter Workplaces of data type table designates the name of the table.

Return Value

The return value has the data type any .

Is an array containing the assigned Workplaces if you do not specify the optional parameter.

Examples

```simtalk
Station13.assignedWorkplaces(myAssignedWorkplaces) -- writes the Workplaces to the table
print Station.assignedWorkplaces -- might
return [*.Models.Model.Workplace, *.Models.Model.Workplace1] in an array
```

See also

Associated Workplaces [on View menu]

