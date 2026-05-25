#### Attributes of the Material Flow Objects

Attributes of the Material Flow Objects

All material flow objects have predefined attributes controlling their behavior or representing their state. You can set the value of an attribute , and you can get its value, either using the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the corresponding attributes. To view all of the methods , read-only attributes and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**Note**

Also compare the topic Data Held in Tabular Form in Attributes .

See also

Attributes of All Objects

Attributes for Animating MUs in 2D

- \_Attributes for the State
- \_Attributes for Setting Times
- \_Attributes for Setting-Up

Attributes for Defining Failures

##### Attributes for Statistics

- \_Attributes of the Controls
- \_Attributes for Setting the Exit Strategy
- \_Attributes for Simulating Costs
- \_Attributes of the Importer
- \_Attributes of Sensors
- \_Attributes of the Curved Objects in 2D

Attributes for Animating MUs in 2D

Attributes for Animating MUs in 2D

The objects provide the attribute RotateMUs for the rotation of the icon of a MU on a material flow object.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

###### RotateMUs [SimTalk] - material flow objects

Rotates the icons of the MUs on the point-oriented material flow object designated by &lt;Path&gt;, if the parts transfer onto a rotated object as they move across any of the material flow objects.

**Remarks**

**Note**

A 3D Only model does not provide the attribute RotateMUs .

**Note**

The attribute RotateMUs is only important for models created in previous versions of Plant Simulation which used this no-longer supported setting that you want to change. RotateMUs still works but we advise against using it in new models.

Specify true to rotate the part to match the rotation of the material flow object.

Specify false to make the part keep its previous rotation/direction.

**Note**

A rotation triggered by the setting Same as the Object ( RotateMUs ) on a point-oriented object only has an effect as long as the part is located on this object. When leaving the object the part again assumes the rotation it had before. When entering a new object, the part considers the rotation of this new object if Same as the Object is active.

<!-- image -->

**Note**

If Plant Simulation shows a length-oriented object in curve mode, Plant Simulation evaluates the setting Rotate Movables / RotateMovables .

<!-- image -->

**Note**

We advise to not deactivate Rotate Movables as this setting does not affect the behavior in 3D .

**Note**

For Transporter and Container this applies: If Same as the Object is active, loaded parts are rotated in the same direction as the Transporter or Container .

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.RotateMUs:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation.RotateMUs := false
```

See also

RotateMUs [SimTalk] - Frame

RotateMovables [SimTalk]

##### Attributes for the State

**\_Attributes for the State**

The material flow objects provide the attributes listed in the table of contents to the left for setting the state in which they are.

You can also select these settings in the dialogs of the objects.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

###### EntranceLocked [SimTalk] - material flow objects

Locks the entrance of the material flow object designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

As long as EntranceLocked is set to true , Plant Simulation cannot move a MU to the object.

The object will finish processing the MUs already located on it, but does not accept any other MUs .

MUs which cannot enter the object, are entered into the Blocking List :

- If the MU wants to enter the object at its entrance, the MU is entered into the Forward Blocking List .
- If the MU is moving backward and want to enter a length-oriented object at its exit, the MU is entered into the Exit Blocking List .

As soon as you unlock the entrance, the MUs in the Blocking List move up.

Type

Attribute

Syntax

&lt; Path &gt;.EntranceLocked:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if pp.NumMU > 10
	pp.EntranceLocked := true
	waituntil pp.numMu  10
	pp.EntranceLocked := false
end
```

See also Entrance Locked [material flow objects] EntranceFree [SimTalk] InheritEntranceExitLockedOnReset [SimTalk] Forward Blocking List Exit Blocking List

###### ExitLocked [SimTalk] - material flow objects

Closes the exit of the material flow object designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

Plant Simulation enters the MUs that cannot exit the object into the Exit Blocking List of this object.

**Note**

The MU does not trigger the Exit Control , if you selected the check box Exit Locked .

When the exit is unlocked again, the object moves the first MU in the Exit Blocking List to a successor.

**Note**

This does not apply to the objects Store and Drain .

Type

Attribute

Syntax

&lt; Path &gt;.ExitLocked:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation.ExitLocked := true
```

SimTalk

InheritEntranceExitLockedOnReset [SimTalk]

See also Exit Locked [material flow objects] Exit Blocking List

###### Failed [SimTalk] - material flow objects

Fails the object designated by &lt;Path&gt; ( true ) or does not fail it ( false ).

Remarks

You can also fail the object or remove the failure with the check box Failed .

If you manually fail a station, it remains failed while any of the failure profiles you defined is active. It will change to not failed once the last failure ( DisruptionEnd event) of the last failure profile ends or when you assign false to this attribute.

**Note**

During the reset phase of the simulation Plant Simulation resets all failures.

**Note**

When you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method &lt;name of the station&gt;.failImp.import .

When you requested the service for removing the failure with the method &lt;name of the station&gt;.failImp.import , you have to release the imported service, after the failure has been removed, with the method &lt;name of the station&gt;.failImp.releaseExporters .

**Note**

When a Worker/Exporter is brokered to the failed station, it remains brokered to the station while it is failed. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

Plant Simulation resets the attribute Failed during the reset phase of the simulation.

If a failure occurs during the simulation run, Plant Simulation also resets the attribute Failed .

Type

Attribute

Syntax

&lt; Path &gt;.Failed:boolean Watchable The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

**Example**

```simtalk
if MyStation.Failed
	MyStation.Failed := false
end
```

SimTalk

import [SimTalk] - importer

releaseExporters [SimTalk]

See also

Failed [check box] - material flow objects

###### InheritEntranceExitLockedOnReset [SimTalk]

Reactivates inheritance of the settings Entrance Locked and Exit Locked for the object designated by &lt;Path&gt; when resetting the model ( true ) or not ( false ).

Remarks

The attribute is only available for the material flow objects and the fl uid objects , which provide the check boxes Entrance Locked and/or Exit Locked .

Type

Attribute

Syntax

&lt; Path &gt;.InheritEntranceExitLockedOnReset:boolean

Assignment Value

You can assign a value of data type boolean .

Example

AssemblyStation.InheritEntranceExitLockedOnReset := true

SimTalk

inheritAttribute [SimTalk] - object

ExitLocked [SimTalk] - material flow objects

EntranceLocked [SimTalk] - material flow objects

See also

Inherit 'Entrance/Exit Locked' On Reset

Entrance Locked [material flow objects]

Entrance Locked [fluid objects]

Pause [SimTalk] - material flow objects

Pauses the object designated by &lt;Path&gt; ( true ) or does not pause it ( false ).

Remarks

Plant Simulation resets the pause when you reset the EventController .

You can also pause the object or remove the pause with the drop-down list Paused/Planned/Unplanned .

**Note**

To check if the object is only paused and not paused and unplanned, you can query the state of the attribute Unplanned . If Unplanned returns false, the object is only paused.

**Note**

When a Worker/Exporter is brokered to the paused station, it remains brokered to the station while it is paused. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

During the reset phase of the simulation Plant Simulation resets the attribute Pause .

Syntax

&lt; Path &gt;.Pause:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if not ParallelStation.Pause
	ParallelStation.Pause := true
end
```

**SimTalk**

Paused/Planned/Unplanned [material flow objects]

**Unplanned [SimTalk] - material flow objects**

**ReservedFor [SimTalk]**

###### ReservedFor [SimTalk]

Reserves a place for a MU on the object designated by &lt;Path&gt;.

**Remarks**

- You can, for example, use ReservedFor to reserve the entrance of a Conveyor for a MU .
- For objects, for which only a single place can be reserved, for example for the Station , specify the MU . For objects, for which several parts can be reserved, for example for the Buffer , specify a array of MUs .
- Plant Simulation automatically reserves a place at the destination when you use a transport importer and activate Wait for Free Target .
- Plant Simulation automatically reserves a place at the destination when you use a PickAndPlace robot and activate Wait for Free Target .
- Specify VOID to delete all reservations.

**Note**

If you set the attribute SequentialDelivery of the AssemblyStation to true , the attribute ReservedFor returns the object for which the place is currently reserved.

If you set it to false , ReservedFor returns an array of objects for which places are reserved.

Type

Attribute

Syntax

&lt; Path &gt;.ReservedFor:any

Assignment Value

You can assign a value of data type any .

Querying the MU for Which a Place is Reserved

You can also query the MU for which a place is reserved. Depending on the object, the attribute returns the MU or an array of MUs .

By assigning a MU or an array of MUs the current reservation gets replaced by the assigned MU or array of MUs !

The return value is VOID if the place is not reserved.

**Examples**

```simtalk
Station.ReservedFor := .MUs.Part:23 ParallelStation[2,1].ReservedFor := .MUs.Part:23
Station.ReservedFor := VOID                        // deletes reservation
print Station.ReservedFor                          // returns void
Buffer.ReservedFor := [.MUs.Part:1, .MUs.Part:2]
print Buffer.ReservedFor                           // returns the assigned array of MUs
MyAssemblyStation.SequentialDelivery := true
print MyAssemblyStation.ReservedFor               // returns the object for which a place is reserved
MyAssemblyStation.SequentialDelivery := false
print MyAssemblyStation.ReservedFor               // returns an array of objects for which places are reserved
```

**SimTalk**

contentsAndReservedList [SimTalk]

ReservedPlace [SimTalk] of the MUs

WaitForFreeTarget [SimTalk] - transport importer

WaitForFreeTarget [SimTalk] -PickAndPlace

SequentialDelivery [SimTalk]

See also

Contents and Reserved Places

Model a Worker Who Waits for a Free Target Stopped [SimTalk] - material flow objects Stops the object designated by &lt;Path&gt; ( true ) or does not pause it ( false ).

Remarks

Stopped means that all of its processing operations come to a halt. The LockoutZone can also set this attribute.

**Note**

When a Worker/Exporter is brokered to the stopped station, it remains brokered to the station while it is stopped. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

During the reset phase of the simulation Plant Simulation resets the attribute Stopped .

**Note**

A Conveyor with activated Acceleration stops instantaneous without deceleration when you set the attribute to true .

It also returns to the Target Speed instantaneous without acceleration when you set the attribute to false . For this reason the Speed Control is not called either.

Type

Attribute

Syntax

&lt; Path &gt;.Stopped:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

**Example**

MyStation.Stopped := true

SimTalk

Stopped [state, material flow objects]

See also

LockoutZone

###### Unplanned [SimTalk] - material flow objects

Sets if the object designated by &lt;Path&gt; is not planned to be working for the time you entered into ShiftCalendar the ( true ) or if it is planned to work ( false ).

Remarks

You can also set the object to planned or unplanned with the drop-down list Paused/Planned/Unplanned .

**Note**

To check if the object is only paused and not paused and unplanned, you can query the state of the attribute Unplanned . If Unplanned returns false, the object is only paused.

**Note**

When a Worker/Exporter is brokered to the paused/unplanned station, it remains brokered to the station while it is unplanned. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

During the reset phase of the simulation Plant Simulation resets the attribute Unplanned .

Type

Attribute

Syntax

&lt; Path &gt;.Unplanned:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

ParallelStation.Unplanned := false SimTalk Paused/Planned/Unplanned [material flow objects]

See also

Working [state, material flow objects]

ShiftCalendar [object]

Attributes for Setting Times

\_Attributes for Setting Times

Normally, the Processing Time ( ProcTime ) of the object determines how long a MU remains on it. After the processing time has elapsed, the object moves the MU on to the next object in the flow of materials. When set-up processes are required to process the MU , the processing time may be increased by the Setup Time . The same is true when failures or pauses take place. Recovery Time and Cycle Time control if an object may receive MUs . During recovery and between cycle times no MUs may enter the object. You can set the times to be constants or define them as probability distributions. You have to set the distribution type and the data of the distribution accordingly (see Probability Distributions ).

The material flow objects provide the attributes listed in the table of contents to the left for setting times.

You can also select these settings in the dialogs of the objects on the Tab Times .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

###### AutomaticProcessing [SimTalk]

Automatically starts processing parts on the object designated by &lt;Path&gt; immediately after they enter the object ( true ) or does not start automatically processing parts ( false ).

Remarks

If you deactivate Automatic Processing , you have to start processing entering parts with the method startProcessing . Only then the station requests Workers .

If you deactivate Automatic Processing , the part is not ready to exit without being processed, compare Finished .

**Note**

This only applies for the objects Station , ParallelStation , AssemblyStation , DismantleStation , and Drain .

**Note**

For the ParallelStation you can only deactivate Automatic Processing when Start Processing When Full / StartProcessingWhenFull is selected/true.

Type

Attribute

Syntax

&lt; Path &gt;.AutomaticProcessing:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

MyStation.AutomaticProcessing := true SimTalk startProcessing [SimTalk] - material flow objects StartProcessingWhenFull [SimTalk] Finished [SimTalk] See also Automatic Processing Start Processing When Full [check box]

CycleTime [SimTalk]

Sets the cycle time , i.e., the times at which MUs may enter the object designated by &lt;Path&gt;.

Remarks

The Cycle Time is the time that passes between the points in time where parts can enter the object. The cycle time is, for example, useful to model chain conveyors with a fixed chain interval that only transport materials when a free hook is available.

The value 34 , for example, means that MUs can enter at the simulation times 0, 34, 68, 102, …

Plant Simulation only opens the entrance of the object for a moment. When a MU is waiting to enter at that time, it may enter, if not, another cycle has to pass before it can enter.

Use the attribute EntranceOpen to query if the entrance is open at the moment.

The attribute TimeUntilEntranceOpen returns the time at which the entrance is open again.

**Note**

When you select a distributed time, then Plant Simulation computes the value for the cycle time interval only once to arrive at equidistant intervals.

Type

Attribute

Syntax

&lt; Path &gt;.CycleTime:time

Assignment Value

You can assign a value of data type time .

Specify 0 to make MUs move onto the object at any time.

Examples

```simtalk
MyStation.CycleTime := 120 // 2 minutes
```

MyStation.CycleTime.setTypeAndAttr("Formula","Variable2/20")

CycleTime [SimTalk]

SimTalk Parameters of the Distributions &gt; Type [SimTalk] - distribution parameter EntranceOpen [SimTalk] - material flow objects TimeUntilEntranceOpen [SimTalk] - material flow objects See also Waiting [state, material flow objects] Cycle Time [general description] Times and Distributions Methods of the Distributions

###### EnforceProcessing [SimTalk]

Starts processing parts on the object designated by &lt;Path&gt;, although no MU is located on it or continues processing if the MU has already exited the object ( true ).

Remarks

Use EnforceProcessing to make a station work for statistics purposes, although no part is being processed. You might, for example, use it make a rotation or opening or closing of a door count as working .

Specify false to terminate processing if the MU has already exited the object.

**Note**

This only applies to the objects Station , ParallelStation , AssemblyStation , and DismantleStation .

As EnforceProcessing changes the Processing Time of the object, it thus affects failures related to the processing time .

Type

Attribute

Syntax

&lt; Path &gt;.EnforceProcessing:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyStation.EnforceProcessing := true

SimTalk

Failures.&lt;NameOfFailureProfile&gt;. Mode [SimTalk] - failures

See also

Working [state, material flow objects]

Failure Relates To

**EnforceProcessing [SimTalk]**

###### ProcTime [SimTalk] - material flow objects

Sets the duration of the Processing Time of the object designated by &lt;Path&gt;.

Remarks

The Processing Time is the time during which the MU is located on the object to be processed. It designates the interval between setting-up and the time at which the material flow object moves the part on to its successor.

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the simulation model.

For a Processing Time of 0 , Plant Simulation does not request a Worker . For this reason the Processing Time will be computed when the MU enters the station or when set-up is done.

To request a Worker in spite of a Processing Time of 0 , enter a Processing Time that is slightly greater than 0, for example 0.001 .

If an empty Workpiece Carrier enters the Station , it exits it again immediately without being processed.

**Note**

For the PlaceBuffer you can only enter a constant Processing Time .

If Sequentially Indexing is cleared, you can only assign the Processing Time for the PlaceBuffer as a whole. The Processing Time is equally distributed across all places.

If Sequentially Indexing is checked, the entire Processing Time passes for moving the part onto the next place.

**Note**

For the Buffer you can only enter a constant Processing Time . As the Processing Time of the Buffer really is a Dwell Time , is not prolonged by failures or pauses .

Each MU remains in the Buffer for at least for the time, which you entered as the Dwell Time . For the Buffer Type &gt; Stack a MU can only exit the Buffer , when all parts which entered the Buffer after the current part, have already exited the Buffer , i.e., when the MU is located at the very top of the stack.

Type

Attribute

**Syntax**

< Path >.ProcTime:time

Assignment Value

You can assign a value of data type time .

**Examples**

```simtalk
-> time partType    : string Station     : object workplan : table
partType := @.partType
Station  := ?
workplan := root.workplan["processingSteps", partType]
result   := workplan["ProcTime",Station]
switch
	@.Name
case "PartA"
	?.ProcTime := str_to_time("10:0") // PartA will be processed for 10 minutes case "PartB" then
	?.ProcTime := str_to_time("2:0")  // PartB will be processed for 2 minutes
end
MyStation.ProcTime := 180 // 3 minutes
MyStation.ProcTime := 3:  // 3 minutes as well
@.ProcTime.setTypeAndAttr("List(Type)", "self.ProcTimeList")
```

SimTalk

Parameters of the Distributions &gt; Type [SimTalk] - distribution parameter

See also

Workpiece Carrier [check box]

Processing Time [general description]

Times and Distributions

###### Methods of the Distributions

###### RandomSeed [SimTalk] - material flow objects

Sets the seed values which are required for creating the random numbers of the object designated by &lt;Path&gt;, together with the Random Numbers Variant of the EventController .

Remarks

When you insert an object into your model, Plant Simulation automatically assigns a random number seed value to this object. You can query the next assigned random seed value with the function setRandomSeedCounter(0) . After the object is created, Plant Simulation increases this counter by 1, so that the next object gets a different random seed value.

If you assign the same random number seed value to two objects, these two objects will generate the same sequence of random numbers, for example for Processing Times which use a distribution, etc.

**Note**

The seed value affects the random number stream of the material flow object which is used for the Processing Time , the Setup Time , the Recovery Time , and the Cycle Time . It also affects the random number streams of the failure profiles, and the random number streams of user-defined attributes of data type RandTime . Plant Simulation makes sure that all of these random number streams are initialized differently. This means that changing the attribute RandomSeed causes the random number stream of the material flow object and also the random number streams of all failure profiles and user-defined attributes to generate a new sequence of random numbers, and all of these streams will generate different sequences of numbers.

Type

Attribute

Syntax

&lt; Path &gt;.RandomSeed:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyStation.RandomSeed := 40
```

SimTalk

IncrementRandomNumbersVariantOnReset [SimTalk] of the EventController

**setRandomSeedCounter [SimTalk]**

See also

Data Types [SimTalk]

Simulating Random Processes

Random Seed Value

Random Number Seed Values

Increment Variant on Reset of the EventController

Random Numbers Variant of the EventController RecoveryTime [SimTalk] - material flow objects Sets the duration of the Recovery Time of the object designated by &lt;Path&gt;.

Remarks

The Recovery Time is the time which is required to put a station into a defined state before it can start processing the next part. The recovery time is, for example, useful to model materials handling equipment, such as a robot, which requires a certain time to insert work pieces into or remove them from processing places.

Use the attribute EntranceOpen to query if the entrance is open at the moment.

The attribute TimeUntilEntranceOpen returns the time at which the entrance is open again.

Type

Attribute

Syntax

&lt; Path &gt;.RecoveryTime:time

Assignment Value

You can assign a value of data type time .

Specify 0 so that MUs can enter continually.

Examples

MyStation.RecoveryTime := 300 // seconds

MyStation.RecoveryTime.setTypeAndAttr("cEmp", cEmpTable)

SimTalk

Parameters of the Distributions &gt; Type [SimTalk] - distribution parameter

RecoveryTime [SimTalk] - material flow objects

RecoveryTime.LowerBound

RecoveryTime.Type RecoveryTime.UpperBound EntranceLocked [SimTalk] - material flow objects EntranceOpen [SimTalk] - material flow objects EntranceFree [SimTalk] putAttributeNamesIntoTable [SimTalk] - distributions See also Recovery Time [general description] Times and Distributions Methods of the Distributions

###### RecoveryTimeMode [SimTalk]

Sets when the Recovery Time of the AssemblyStation , DismantleStation , PickAndPlaceRobot , and Station designated by &lt;Path&gt; starts.

<!-- image -->

**Remarks**

RecoveryTimeMode also applies to the ParallelStation with activated setting Start Processing When Full .

Type

Attribute

Syntax

&lt; Path &gt;.RecoveryTimeMode:string

**Assignment Value**

You can assign a value of data type string .

**You can specify: .**

- "When part enters" the station.
- "When processing is finished" . The recovery time elapses after the part is processed, no matter if the part is still located on the station or has left it.
- "When part exits" the station. The recovery time elapses after the part is processed and has left the station.

**Example**

```simtalk
MyStation.RecoveryTimeMode := "When part exits"
```

**See also**

Recovery Time [general description]

Recovery Time Starts

Times and Distributions SetupTime [SimTalk] - material flow objects Sets the duration of the Set-up Time of the object designated by &lt;Path&gt;.

Remarks

A material flow object has to set up, whenever the name of the MU differs from the name of the MU that the object processed before.

The Set-up Time is the time it takes to set the object up for processing a different type of MU . An identical name designates that MUs are of the same type.

You can also arrange if the object sets-up automatically or if set-up will be started explicitly from within a Method . Setting-up is described under the tab Set-Up .

If an empty Workpiece Carrier enters the Station , it exits it again immediately without the Station being set up for it.

When a set-up time of 0 results, for example from a distribution or from a formula , Plant Simulation sets the station up without using up any time at all and does not request any Workers . Plant Simulation counts this as a setup process for statistical purposes and the part type , for which the station is being set up, is set to this new part type immediately. If you typed in a constant set-up time , the object never sets up.

Type

Attribute

Syntax

< Path >.SetupTime:time

Assignment Value

You can assign a value of data type time .

Examples

```simtalk
MyStation.SetupTime := 120 // 2 minutes
MyStation.SetupTime.Type := "Matrix(Type)"
MyStation.SetupTime.DataTable := DataTable
```

// MyStation.SetupTime.setTypeAndAttr("Matrix(Type)", DataTable)

SimTalk

Parameters of the Distributions &gt; Type [SimTalk] - distribution parameter

RemainingSetUpTime [SimTalk]

See also

Tab Set-Up [general description]

Workpiece Carrier [check box]

Set-up Time [general description]

Times and Distributions

Methods of the Distributions

Attributes for Setting-Up

\_Attributes for Setting-Up

The Station , ParallelStation , AssemblyStation , DismantleStation , and Drain provide the attributes listed in the table of contents to the left for setting them up.

You can also select these settings in the dialogs of the objects on the Tab Set-Up .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

###### AutomaticSetup [SimTalk]

Automatically sets the object designated by &lt;Path&gt; up whenever it is necessary ( true ) or does not set it up automatically ( false ).

Remarks

Specify true for AutomaticSetup to trigger the set-up process of the object as soon as the respective differing MU class intends to move onto the object.

Specify false for AutomaticSetup and define the set-up process yourself, for example with the method setUpFor .

**Note**

If the object cannot be set up at the current point in time, for example because it is failed, Plant Simulation does not attempt to set the object up anew.

Type

Attribute

Syntax

&lt; Path &gt;.AutomaticSetup:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

ParallelStation.AutomaticSetup := true

SimTalk

setupFor [SimTalk]

**See also**

**Automatic Set-up , check box**

###### SetupAfterNPartsMode [SimTalk]

Sets the object designated by &lt;Path&gt; up immediately after the n-th part was processed ( Before Next Part ) or after the n-plus-first part wants to move onto the station ( After Last Part ).

Type

Attribute

Syntax

```simtalk
< Path >.SetupAfterNPartsMode:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Before Next Part" or "After Last Part" .

Example

```simtalk
MyStation.SetupAfterNumParts := 250
MyStation.SetupAfterNPartsMode := "After Last Part"
```

See also

Set-up After n Parts

**SetupAfterNumParts [SimTalk]**

###### SetupAfterNumParts [SimTalk]

Sets after how many parts the object designated by &lt;Path&gt; sets up.

Remarks

Specifying 0 deactivates setting-up after the number of parts.

The object also sets-up and starts counting starting with 0 if the part type changes before the number of parts, which you entered, is reached. For this reason it might happen that the object never reaches the number of parts of a certain type, for which it is to set up.

When the value 0 was determined when setting the Set-up Time , for example resulting from a distribution or from a formula , Plant Simulation treats this as if a setup process has taken place. This means that the counter also is reset for a setup process of time 0.

If you do not want this, select the setting Off for Setup Depends On or set the attribute SetupForType to false . Then the station only sets up after the selected number of parts.

**Note**

The number of parts is the number of parts that enter the station. These parts do not necessarily have to be processed. Statistics also counts parts which were removed from a station before they were processed, for example during a set-up process or while the station was waiting for a service to be executed.

Type

Attribute

Syntax

```simtalk
< Path >.SetupAfterNumParts:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyStation.SetupAfterNumParts := 250
MyStation.SetupAfterNPartsMode := "After Last Part"
```

SimTalk SetupForType [SimTalk] See also Set-up Time [general description] Set-up Depends On Set-up After n Parts

**SetupAttrName [SimTalk]**

###### SetupAttrName [SimTalk]

Sets the object designated by &lt;Path&gt; up depending on a MU name or depending on a user-defined attribute .

Remarks

To set the MU up according to its Name , specify an empty string "" .

Setting SetupAttrName to a non-empty string "" will set the attribute SetupForType to true.

To set the MU up according to a user-defined attribute of the MU , specify the name of that user-defined attribute .

This user-defined attribute has to be of data type string , integer , boolean , or object .

Plant Simulation converts values of data type integer and boolean to strings .

For values of data type object Plant Simulation always sets up for the object name.

For .Models.Model.Conveyor5.Packstation2 Plant Simulation sets up for the object Packstation2.

Type

Attribute

Syntax

```simtalk
< Path >.SetupAttrName:string < Path >.SetupAttrName:integer < Path >.SetupAttrName:boolean < Path >.SetupAttrName:object
```

**Assignment Value**

You can assign a value of data type string .

**Example**

```simtalk
ParallelStation.SetupAttrName := "" -- sets the attribute SetupForType to true
MyStation.SetupAttrName := "MySetupAttribute"
```

**See also**

**Set-up Depends On**

**SetupForType [SimTalk]**

SetupCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation executes the set-up control whenever a set-up process of the object designated by &lt;Path&gt; starts or ends. If you did not enter the name of a method , the attribute SetupCtrl returns VOID.

Use the read-only attribute ResSetUp to query if the set-up process starts or ends. When ?.ResSetUp returns true , the set-up process just started.

The standard set-up control as a user-defined attribute looks like this:

<!-- image -->

Type

Attribute

Syntax

```simtalk
< Path >.SetupCtrl:object
```

Assignment Value

You can assign a value of data type object .

Example

```simtalk
MyStation.SetupCtrl := &mySetupControl
```

SimTalk

ResSetup [SimTalk] - material flow objects

ResSetup [SimTalk] - material flow objects

**See also**

**Set-up Control**

###### SetupForType [SimTalk]

SetupForType [SimTalk]

Sets the object designated by &lt;Path&gt; up when the type of the MU changes ( true ) or does not set it up when the type changes ( false ).

Remarks

Specify false to only set the object up after the number of parts that you specified has been reached.

Setting the attribute SetupAttrName to a non-empty string "" will set the attribute SetupForType to true.

Type

Attribute

Syntax

```simtalk
< Path >.SetupForType:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation.SetupForType := true  // sets up when the MU type changes
MyStation.SetupForType := false // does not set up when the MU type changes
```

See also

Set-up Depends On

Set-up After n Parts

SetupAttrName [SimTalk]

SetUpOnlyWhenEmpty [SimTalk]

Enables MUs to remain on the object designated by &lt;Path&gt; during the set-up process ( true ) or not ( false ).

Remarks

The set-up time starts when all set-up processes which you specified are finished. MUs located on the object will be processed with the settings for the MU class for which the object was set up before.

Type

Attribute

Syntax

&lt; Path &gt;.SetUpOnlyWhenEmpty:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

ParallelStation.SetUpOnlyWhenEmpty := true

See also

Set-up Only When Empty

Attributes for Defining Failures

Attributes for Defining Failures

The stationary material flow objects have a failure generator which creates failures during the interval you set on the tab Failures . You can define the start and the end of the failure, the interval between two failures, and their duration.

The stationary material flow objects provide the attributes listed in the table of contents to the left for defining failures.

The window Show Attributes and Methods shows the identifier Failures but not the methods proper of the failures.

<!-- image -->

The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**See also**

Tab Failures [general description]

- \_Methods for Defining Failures
- \_Attributes of the Failure Profiles
- \_Attributes for Failures in the Simplified Notation

###### Failed [SimTalk] - material flow objects

Failed [SimTalk] - material flow objects

Fails the object designated by &lt;Path&gt; ( true ) or does not fail it ( false ).

Remarks

You can also fail the object or remove the failure with the check box Failed . When you manually fail a station, it remains failed while any of the failure profiles you defined is active. It will change to not failed once the last failure ( List &gt; DisruptionEnd event) of the last failure profile ends or when you assign false to this attribute.

**Note**

During the reset phase of the simulation Plant Simulation resets the attribute Failed .

When a failure occurs during the simulation run, Plant Simulation resets the attribute Failed as well.

**Note**

When you set the failed state of a material flow object with the attribute Failed , and you would like to import a Service for removing the failure, you have to use the method name of station.failImp.import .

When you requested the service for removing the failure with the method name of station.failImp.import , you have to release the imported service, after the failure has been removed, with the method name of station.failImp.releaseExporters .

Type

Attribute

Syntax

```simtalk
< Path >.Failed:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

if MyStation.Failed

```simtalk
MyStation.Failed := false
end
```

SimTalk import [SimTalk] - importer releaseExporters [SimTalk] See also Failed [check box] - material flow objects List of Events \_Attributes of the Failure Profiles \_Attributes for Failures in the Simplified Notation FailureActive [SimTalk] - material flow objects Activates failures for the object designated by &lt;Path&gt; ( true ) or does not activate them ( false ).

Remarks

**Note**

The failure of the object is only active, when you activate this attribute and the attribute Active of the respective failure profile !

Type

Attribute

Syntax

&lt; Path &gt;.FailureActive:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

ParallelStation.FailureActive := false

See also

Active [check box] - failures

- \_Attributes of the Failure Profiles
- \_Attributes for Failures in the Simplified Notation

**Attributes of the Failure Profiles**

##### \_Attributes of the Failure Profiles

The stationary material flow objects provide the attributes listed in the table of contents to the left for defining failure profiles .

The objects address failure profile attributes as sub-attributes of Failures .

The window Show Attributes and Methods shows the identifier Failures for failures, but not the actual attributes of the failure profile.

<!-- image -->

**Example**

<!-- image -->

The figure below illustrates the information using the example of the object Station .

<!-- image -->

**See also**

Tab Failures [general description]

\_Attributes for Failures in the Simplified Notation

###### \_Attributes of the Failure Profiles

###### Active [SimTalk] - failure profile

Activates the failure profile designated by &lt;NameOfFailureProfile&gt; of the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

**Note**

The failure of the object is only active, when you activate this attribute, i.e., the failure profile itself, and the attribute FailureActive of the object as such!

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyStation.Failures.MyFailureProfile1.Active := true

SimTalk

FailureActive [SimTalk] - material flow objects

See also

Active [check box] - failure profile Availability [SimTalk] - failure profile Sets the Availability of the designated failure profile of the object designated by &lt;Path&gt;.

Remarks

Availability is the proportion of time during which a machine is in an operable state. The availability is based on a combination of MTBF and MTTR .

Type

Attribute

Syntax

```simtalk
< Path >.Failures.<NameOfFailureProfile>.Availability:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyStation.Failures.MyFailureProfile1.Availability := 90  // 90 percent
```

**Note**

You can only query the Availability , when the representation Availability % and MTTR is active, otherwise the Debugger opens!

If you selected the representation Interval and Duration , and you assign a value to the Availability % , either in SimTalk , with the AttributeExplorer , etc., Plant Simulation changes the representation to Availability % and MTTR . It then uses the percentage value you entered for the Availability % and enters a default value of 1 hour for the MTTR .

When you set these two values via information flow with these attributes, the following assignments result in an MTTR of 0, i.e., the Station will not fail during the simulation.

```simtalk
MyStation.Failures.MyFailureProfile1.MTTR := 60
MyStation.Failures.MyFailureProfile1.Availability := 100
```

The following sequence of assignments result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

```simtalk
MyStation.Failures.MyFailureProfile1.Availability := 100
MyStation.Failures.MyFailureProfile1.MTTR := 60
```

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after changing the duration of the failure. This causes a new failure event to be computed.

**Note**

When you set an availability of 100 percent, meaning that the station will never fail, and subsequently change the availability to a more realistic value, say 50 percent, Plant Simulation will only apply this new setting when you first assign the value false to the attribute Active , and then reassign the value true to the attribute Active again after setting the attribute Availability .

**Example**

```simtalk
// Reduces the availability and the MTTR during the simulation run. // This method is called by the init method via a method call after 12 hours.
print EventController.SimTime," Simulated availability in the morning: ",round(100 * (1 - MyStation.StatFailPortion),2)," %" MyStation.InitStat // reduce the availability
MyStation.Availability := 80
MyStation.MTTR := str_to_time("10:00")
MyStation.FailureActive := false
MyStation.FailureActive := true // activate failures
```

**SimTalk**

Active [SimTalk] - failure profile

See also

Availability [failure, text box]

MTTR [SimTalk] - failure profile

###### AvailabilityOn [SimTalk]

AvailabilityOn [SimTalk]

Returns, if the object designated by &lt;Path&gt; uses the representation Availability and MTTR or the representation Interval and Duration for failures.

Type

Read-only attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.AvailabilityOn → boolean

Return Value

The return value has the data type boolean .

Example

print MyStation.Failures.MyFailureProfile1.AvailabilityOn

See also

Availability [failure, check box]

###### Duration [SimTalk] - failure profile

Sets the Duration of the specified failure of the designated failure profile of the object designated by &lt;Path&gt;.

Remarks

**Note**

When you change failure settings, this does not affect the already computed DisruptionEnd event.

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused.

Statistics counts the times during which these two states overlap as pause time.

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Duration:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.Failures.MyFailureProfile1.Duration.setTypeAndAttr("Normal",30,10)

See also

Duration [failure]

###### Failed [SimTalk] - failure profile

Failed [SimTalk] - failure profile

Fails the specified failure profile of the object designated by &lt;Path&gt; ( true ) or does not fail it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Failed

Watchable

The attribute Failed of the failure profile is not watchable and Plant Simulation calls a control, for example a Fail Control .

The attribute Failed of the material flow object proper is watchable though.

Assignment Value

You can assign a value of data type boolean .

Example

print MyStation.Failures.MyFailureProfile1.Failed

See also

Failed [check box] - failure profile

Failed [SimTalk] - material flow objects

Fail Control [material flow objects]

Interval [SimTalk] - failure profile

Sets the Interval between two failures of the specified failure profile of the object designated by &lt;Path&gt;.

Remarks

Failures only occur when Interval or Duration have a value greater than 0.

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true to the attribute Active again after changing the interval of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Interval:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.Failures.MyFailureProfile1.Interval.setTypeAndAttr("Normal",1,60,1 0)

SimTalk

Active [SimTalk] - failure profile

See also

Interval [failure]

Duration [failure]

Mode [SimTalk] - failure profile

Mode [SimTalk] - failure profile

Sets to which time failures of the designated failure profile of the object designated by &lt;Path&gt; relate.

Remarks

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the Availability becomes. This then prevents the Availability you entered into the dialog from being reached.

**Note**

When a station fails, and a pause takes place during the failure, the failure time of the station will still be used up, although the station is paused. The DisruptionEnd event will not be changed.

When a station, which fails based on the processing time or the operating time, and which is interrupted by a pause or failure, the processing time or the operating time of the station for simulating the MTBF will not be used up. The points in time for the DisruptionBegin event will be moved forward into the future. Statistics counts the times during which these two states overlap as pause time.

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Mode:string

Assignment Value

You can assign a value of data type string .

You can specify "SimulationTime" , "ProcessingTime" , or "OperatingTime" .

Example

MyStation.Failures.MyFailureProfile1.Mode := "OperatingTime"

See also

DisruptionBegin

DisruptionEnd

Failure Relates To Failure Relates To > Simulation time Failure Relates To > Operating time Failure Relates To > Processing time

###### MTTR.getBounds

The sub-method MTTR.getBounds gets the bounds of the mean time to repair ( MTTR ) of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

< >.Failures.<NameOfFailureProfile>.MTTR.getBounds(byref

```simtalk
Path LowerBound:time, byref UpperBound:time)
```

**Parameters**

The parameters LowerBound and UpperBound of data type time designate the local variables to which Plant Simulation writes the lower and the upper bound.

**Example**

```simtalk
var lower,upper: time
MyStation.Failures.MyFailureProfile1.MTTR.getBounds(lower, upper)
print lower, " ", upper
```

**SimTalk**

MTTR [SimTalk] - failure profile

MTTR.setBounds

See also

MTTR [material flow objects]

###### MTTR.setBounds

The sub-method MTTR.setBounds sets the bounds of the mean time to repair ( MTTR ) of the object designated by &lt;Path&gt;.

Remarks

Specify MTTR.setBounds(0,0) to delete the bounds of the MTTR , .

If you use bounds, both bounds have to have positive values and the mean time to repair has to be located between the bounds. For given bounds the mean time to repair might not be realizable, although both conditions are met.

**Note**

The Availability and the MTTR are internally converted into the parameters of the statistical distributions of the failure interval and of the Failure Duration . During the conversion inexact calculations may happen, which might slightly influence the simulated value of the MTTR . If you change the bounds of the MTTR , we recommend to also set the value of the MTTR .

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.MTTR.setBounds(LowerBound:time, UpperBound:time)

**Parameters**

- The parameter LowerBound of data type time designates the lower bound.
- The parameter UpperBound of data type time designates the upper bound.

**Example**

MyStation.Failures.MyFailureProfile1.MTTR.setBounds(60, 300)

SimTalk

MTTR [SimTalk] - failure profile

MTTR.getBounds

**See also**

**MTTR [material flow objects]**

MTTR [SimTalk] - failure profile

MTTR [SimTalk] - failure profile

Sets the mean time to repair ( MTTR ) of the specified failure profile of the object designated by &lt;Path&gt;.

Syntax

< Path >.Failures.<NameOfFailureProfile>.MTTR:time

Type

Attribute

Assignment Value

You can assign a value of data type time .

Examples

MyStation.Failures.MyFailureProfile1.MTTR.setBounds(60, 300)

```simtalk
MyStation.Failures.MyFailureProfile1.MTTR := 3600  // 1 hour
```

**Note**

You can only query the MTTR , when the representation Availability % and MTTR is active, otherwise the Debugger opens!

When you selected the representation Interval and Duration , and you assign a value to the MTTR , either in SimTalk , or with the AttributeExplorer , etc., Plant Simulation changes the representation to Availability % and MTTR . It then uses the value you entered for the MTTR and enters a default value of 95 percent for the Availability % .

When you set these two values via information flow with these attributes, the following assignments result in an MTTR of 0, i.e., the Station will not fail during the simulation.

```simtalk
MyStation.Failures.MyFailureProfile1.MTTR := 60
MyStation.Failures.MyFailureProfile1.Availability := 100
```

The following sequence of assignments result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

```simtalk
MyStation.Failures.MyFailureProfile1.Availability := 100
MyStation.Failures.MyFailureProfile1.MTTR := 60
```

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after changing the MTTR. This causes a new failure event to be computed.

**Note**

When you set the MTTR to 0, meaning that the station will never fail, and subsequently change the MTTR to a more realistic value, say 60 seconds, Plant Simulation will only apply this new setting when you first assign the value false to the attribute Active , and then reassign the value true to the attribute Active again.

```simtalk
print EventController.Time," Simulated availability in the morning: ",round(100 * (1 - MyStation.StatFailPortion),2)," %" MyStation.initStat // reduces the availability:
MyStation.Availability := 80
MyStation.MTTR := str_to_time("10:00")
MyStation.FailureActive := false
MyStation.FailureActive := true // activates failures
```

**SimTalk**

Active [SimTalk] - failure profile

MTTR.getBounds [SimTalk]

MTTR.setBounds [SimTalk]

See also

MTTR [material flow objects]

Name [SimTalk] - failure profile

Name [SimTalk] - failure profile

Sets the name of the failure profile of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Name:string

Assignment Value

You can assign a value of data type string .

Example

MyStation.Failures.MyFailureProfile1.Name := "MyFailure2"

See also

Name [failure]

Start [SimTalk] - failure profile

Sets the Start Time of the first failure of the specified failure profile of the object designated by &lt;Path&gt;.

Remarks

**Note**

When you specify 0 , Plant Simulation uses the failure Interval to set the point in time of the first failure.

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after setting the start time of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

< Path >.Failures.<NameOfFailureProfile>.Start:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.Failures.MyFailureProfile1.Start.setTypeAndAttr("Const",

str_to_time("45:00"))

SimTalk

Active [SimTalk] - failure profile

See also

Start [failure]

Interval [failure]

###### Stop [SimTalk] - failure profile

Stop [SimTalk] - failure profile

Sets the Stop Time of the last failure of the specified failure profile of the object designated by &lt;Path&gt;.

Remarks

**Note**

When you specify 0 , Plant Simulation creates new failures infinitely.

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute after setting the stop time of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

&lt; Path &gt;.Failures.&lt;NameOfFailureProfile&gt;.Stop:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.Failures.MyFailureProfile1.Stop.setTypeAndAttr("Const",

str_to_time("2:30:00"))

SimTalk

Active [SimTalk] - failure profile

See also

Stop [failure]

**Attributes for Failures in the Simplified Notation**

##### \_Attributes for Failures in the Simplified Notation

When a material flow object only has a single failure profile , we recommend to use the simplified notation without specifying the profile. Plant Simulation then always addresses the first failure profile . If you did not define a failure profile , the objects do not provide the attributes below.

The stationary material flow objects provide these attributes listed in the table of contents to the left for simplified access to failures.

You can also select these settings in the dialogs of the objects on the tab Failures .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

See also Tab Failures [general description] \_Methods for Defining Failures \_Attributes of the Failure Profiles Availability [SimTalk] - material flow objects Sets the Availability in percent of the object designated by &lt;Path&gt;.

Remarks

Availability is the proportion of the time during which a machine is in an operable state.

**Note**

You can only query the Availability , when the representation Availability % and MTTR is active, otherwise the Debugger opens!

When you selected the representation Interval and Duration , and you assign a value to the MTTR , either in SimTalk , or with the AttributeExplorer , etc., Plant Simulation changes the representation to Availability % and MTTR . It then uses the value you entered for the MTTR and enters a default value of 95 percent for the Availability % .

Type

Attribute

Syntax

```simtalk
< Path >.Availability:real
```

Assignment Value

You can assign a value of data type real .

When you set these two values via information flow with these attributes, the following assignments result in an MTTR of 0, i.e., the Station will not fail during the simulation.

```simtalk
MyStation.MTTR := 60
MyStation.Availability := 100
```

The following sequence of assignments result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

```simtalk
MyStation.Availability := 100
MyStation.MTTR := 60
```

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute after changing the Duration of the failure. This causes a new failure event to be computed.

**Note**

When you set an availability of 100 percent, meaning that the station will never fail, and subsequently change the availability to a more realistic value, say 50 percent, Plant Simulation will only apply this new setting when you first assign the value false to the attribute Active , and then reassign the value true to the attribute Active again after setting the attribute Availability .

SimTalk

Active [SimTalk] - failure profile

See also

Availability [failure, text box]

###### FailDuration [SimTalk]

Sets the Duration of a failure of the object designated by &lt;Path&gt;.

Remarks

**Note**

The attribute affects the failure profile with the number 1.

**Note**

When you change failure settings, this does not affect the already computed EndFailure event.

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be used up, although the station is paused.

Statistics counts the times during which these two states overlap as pause time.

Type

Attribute

Syntax

&lt; Path &gt;.FailDuration:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.FailDuration := 6.85 // 6.85 seconds

See also

Duration [failure]

###### FailInterval [SimTalk]

FailInterval [SimTalk]

Sets the Interval between two failures for the object designated by &lt;Path&gt;.

Remarks

Failures only occur when FailInterval or FailDuration have a value greater than 0.

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true to the attribute Active again after changing the interval of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

< Path >.FailInterval:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
// failures are to take place equally distributed between 5 and 8 minutes.
MyStation.FailInterval.Type := "uniform"
MyStation.FailInterval.Start := 5*60 // 5 minutes
MyStation.FailInterval.Stop := 8*60  // 8 minutes
```

SimTalk

Active [SimTalk] - failure profile

FailDuration [SimTalk]

See also

Interval [failure]

###### FailStart [SimTalk]

Sets the Start Time of the first failure of the object designated by &lt;Path&gt;.

Remarks

When you specify 0 (zero), the failure occurs immediately when the simulation starts if the attribute FailDuration has a value greater than 0. Changes of the attribute are also considered while processing events after resetting the model.

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after setting the start time of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

&lt; Path &gt;.FailStart:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyStation.FailStart := 3600.00 // first failure after 1 hour
```

SimTalk

Active [SimTalk] - failure profile

FailDuration [SimTalk]

See also

Start [failure]

###### FailStop [SimTalk]

FailStop [SimTalk]

Sets the Stop Time of the last failure of the object designated by &lt;Path&gt;.

Remarks

Note

Specify 0 to create new failures infinitely.

**Note**

If you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after setting the stop time of the failure. This causes a new failure event to be computed.

Type

Attribute

Syntax

&lt; Path &gt;.FailStop:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.FailStop := 0.0 // no time limit

SimTalk

Active [SimTalk] - failure profile

See also

Stop [failure]

Mode [SimTalk] - failures

Sets to which time the failures of the object designated by &lt;Path&gt; relate to.

Type

Attribute

Syntax

&lt; Path &gt;.Mode:string

Assignment Value

You can assign a value of data type string .

You can specify "SimulationTime" , "ProcessingTime" , or "OperatingTime" .

Example

MyStation.Failures.MyFailureProfile1.Mode := "OperatingTime"

See also

Failure Relates To

###### MTTR [SimTalk] - material flow objects

MTTR [SimTalk] - material flow objects

Sets the mean time to repair ( MTTR ) of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.MTTR:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyStation.MTTR := 3600  // 1 hour
```

**Note**

You can only query the availability, when the representation Availability % and MTTR is active, otherwise Plant Simulation opens the Debugger !

When you selected the representation Interval and Duration , and you assign a value to the Availability % , either in SimTalk , with the AttributeExplorer , etc., Plant Simulation changes the representation to Availability % and MTTR . It then uses the percentage value you entered for the Availability % and enters a default value of 1 hour for the MTTR .

When you set these two values via information flow with these attributes, the following assignments result in an MTTR of 0, i.e., the Station will not fail during the simulation.

```simtalk
MyStation.MTTR := 60
MyStation.Availability := 100
```

The following sequence of assignments result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

```simtalk
MyStation.Availability := 100
MyStation.MTTR := 60
```

**Note**

When you change failure settings, this does not affect the already computed failure events. If you would like the changed settings to take effect immediately, you first have to assign the value false to the attribute Active , and then reassign the value true again to the attribute Active after changing the MTTR. This causes a new failure event to be computed.

**Note**

When you set the MTTR to 0, meaning that the station will never fail, and subsequently change the MTTR to a more realistic value, say 60 seconds, Plant Simulation will only apply this new setting when you first assign the value false to the attribute Active , and then reassign the value true to the attribute Active again.

SimTalk

Active [SimTalk] - failure profile

See also

MTTR [material flow objects]

Attributes for the Energy Simulation

\_Attributes for the Energy Simulation

Plant Simulation provides the attributes listed in the table of contents to the left for the energy simulation of the material flow objects.

You can also select these settings in the dialogs of the material flow objects on the Tab Energy .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**See also**

\_Read-Only Attributes for Energy Statistics .

###### EnergyActive [SimTalk]

Activates the energy settings for the object designated by &lt;Path&gt; ( true ) or does not activate them ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EnergyActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Station.EnergyActive := false

See also

Active [check box] - energy

###### EnergyCurrentState [SimTalk]

EnergyCurrentState [SimTalk]

Sets the energy state of the object designated by &lt;Path&gt;.

Remarks

Note

You can only set the target energy state of the object if it is not failed .

Note

The power transition does not use up any time.

Type

Attribute

Syntax

&lt; Path &gt;.EnergyCurrentState:string

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type string .

- If the current energy state is Operational , Standby or Off , you can set the states "Operational" , "Standby" , or "Off" .
- If the current energy state is Setting-up or Working , you can set the states "Standby" , or "Off" . After you set another state, the current state is interrupted first.

Example

Station.EnergyCurrentState := "Standby"

See also

State , drop-down list EnergyPauseEndState [SimTalk]

Sets the energy end state for a pause of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EnergyPauseEndState:string

Assignment Value

You can assign a value of data type string .

You can specify "Previous state" , "Operational" , "Standby" , or "Off" .

The previous state is the state the object was in before the pause.

Example

Station.EnergyPauseEndState := "Operational"

See also

End [energy pause] , drop-down list

###### EnergyPausePowerUpEarly [SimTalk]

Powers the object designated by &lt;Path&gt; up early during a pause so that the machine has the correct energy state at the end of the pause ( true ) or not ( false ).

Remarks

Specify false to start powering up at the end of the pause.

**Note**

When you set the attribute EnergyPausePowerUpEarly to true , the machine powers up/down while the machine is paused. Therefore the powering up/down time is part of the paused time .

Type

Attribute

Syntax

&lt; Path &gt;.EnergyPausePowerUpEarly:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Station.EnergyPausePowerUpEarly := false

See also

Power Up Early [energy pause]

EnergyPauseStartState [SimTalk]

Sets the energy start state for a pause of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EnergyPauseStartState:string

Assignment Value

You can assign a value of data type string .

You can specify "No change" , "Standby" , or "Off" .

Example

Station.EnergyPauseStartState := "Standby"

See also

Start [energy pause] , drop-down list

###### EnergyTargetState [SimTalk]

EnergyTargetState [SimTalk]

Sets the target energy state of the object designated by &lt;Path&gt;.

Remarks

You can only set the target energy state of the object if it is not failed .

Type

Attribute

Syntax

&lt; Path &gt;.EnergyTargetState:string

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type string .

- If the current energy state is Operational , Standby or Off , you can set the states "Operational" , "Standby" , or "Off" .

After you set another state, the power transition uses the time which you entered under Transition Times .

- If the current energy state is Setting-up or Working , you can set the states "Standby" or "Off" . After you set another state, the current state is interrupted, resulting in the state Operational . (This process does not use up any time.) Then the power transition uses the time which you entered under Transition Times .

Example

Station.EnergyTargetState := "Standby"

See also

State , drop-down list

Transition Times EnergyUnplannedEndState [SimTalk]

Sets the energy end state for the unplanned state of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EnergyUnplannedEndState:string

Assignment Value

You can assign a value of data type string .

You can specify "Previous state" , "Operational" , "Standby" , or "No change" .

The previous state is the state the object was in before the unplanned phase.

Example

Station.EnergyUnplannedEndState := "Standby"

See also

End [energy unplanned] , drop-down list

###### EnergyUnplannedPowerUpEarly [SimTalk]

Powers the object designated by &lt;Path&gt; up early during an unplanned phase so that the machine has the correct energy state at the end of that phase ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EnergyUnplannedPowerUpEarly:boolean

Assignment Value

You can assign a value of data type boolean .

Specify false to start powering up at the end of the unplanned phase.

**Note**

When you specify true , the machine powers up/down while the machine is unplanned. Therefore the powering up/down time is part of the unplanned time .

**Example**

Station.EnergyUnplannedPowerUpEarly := true

See also

Power Up Early [energy unplanned]

EnergyUnplannedStartState [SimTalk]

Sets the energy start state for the unplanned state of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EnergyUnplannedStartState:string

Assignment Value

You can assign a value of data type string .

You can specify "No change" , "Standby" , or "Off" .

Example

Station.EnergyUnplannedStartState := "No change"

See also

Start [energy unplanned] , drop-down list PowerInputFailed [SimTalk]

Sets the power input of the state failed of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state failed , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputFailed:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputFailed := 0.5

See also

Failed [text box] - energy

###### PowerInputOff [SimTalk]

Sets the power input of the state off of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state off , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputOff:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputOff := 1

See also

Off , text box

###### PowerInputOperational [SimTalk]

PowerInputOperational [SimTalk]

Sets the power input of the state operational of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state operational , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputOperational:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputOperational := 0.5

See also

Operational [energy] , text box

###### PowerInputSettingUp [SimTalk]

Sets the power input of the state setting-up of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state setting-up , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputSettingUp:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputSettingUp := 0.001

See also

Setting-up [energy] , text box PowerInputStandby [SimTalk]

Sets the power input of the state standby of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state standby , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputStandby:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputStandby := 0.1

See also

Standby , text box

###### PowerInputWorking [SimTalk]

Sets the power input of the state working of the object designated by &lt;Path&gt;.

Remarks

If the object is in the state working , the new power input takes effect immediately.

Type

Attribute

Syntax

&lt; Path &gt;.PowerInputWorking:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.PowerInputWorking := 3

See also

Working [energy] , text box

###### TransitionTimeOffToOperational [SimTalk]

Sets the transition time which passes when the object designated by &lt;Path&gt; changes its energy state from off to operational .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeOffToOperational:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeOffToOperational := 2:30

See also

Off to Operational

###### TransitionTimeOffToStandby [SimTalk]

Sets the transition time which passes when the object designated by &lt;Path&gt; changes its energy state from off to standby .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeOffToStandby:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeOffToStandby := 2:30

See also

Off to Standby TransitionTimeOperationalToOff [SimTalk]

Sets the transition time, which passes when the object designated by &lt;Path&gt; changes its energy state from operational to off .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeOperationalToOff:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeOperationalToOff := 4:00

See also

Operational to Off

###### TransitionTimeOperationalToStandby [SimTalk]

Sets the transition time, which passes when the object designated by &lt;Path&gt; changes its energy state from operational to standby .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeOperationalToStandby:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeOperationalToStandby := 3:00

See also

Operational to Standby TransitionTimeStandbyToOff [SimTalk]

Sets the transition time which passes when the object designated by &lt;Path&gt; changes its energy state from standby to off .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeStandbyToOff:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeStandbyToOff := 1:00

See also

Standby to Off

###### TransitionTimeStandbyToOperational [SimTalk]

Sets the transition time which passes when the object designated by &lt;Path&gt; changes its energy state from standby to operational .

Type

Attribute

Syntax

&lt; Path &gt;.TransitionTimeStandbyToOperational:any

Assignment Value

You can assign a value of data type any or a formula.

Example

Station.TransitionTimeStandbyToOperational := 4:00

See also

Standby to Operational

Attributes for Simulating Costs

\_Attributes for Simulating Costs

Plant Simulation provides the attributes listed in the table of contents to the left for the cost simulation of the material flow objects.

You can also select these settings in the dialogs of the material flow objects on the Tab Costs .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**CostingActive [SimTalk] - material flow objects**

Activates the costs settings of the object designated by &lt;Path&gt; ( true ) or does not activate them ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.CostingActive:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation.CostingActive := true
```

See also

Active [check box] - costs, material flow objects DepreciationPeriod [SimTalk]

Sets the depreciation period in years over which the depreciation amount is distributed with write-offs of the object designated by &lt;Path&gt;.

Remarks

The total investment costs are the sum of the Investment Costs and the Investment Costs per Length which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period and then do not accrue anymore.

Type

Attribute

Syntax

&lt; Path &gt;.DepreciationPeriod:real

Assignment Value

You can assign a value of data type real .

Example

MyStation.DepreciationPeriod := 15

See also

Depreciation Period [text box]

Investment Costs [text box]

Investment Costs per Length [text box]

InvestmentCosts [SimTalk]

Sets the investments costs in the defined currency unit which accrue for purchasing the object designated by &lt;Path&gt;.

Remarks

The total investment costs are the sum of the Investment Costs and the Investment Costs per Length which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period and then do not accrue anymore.

Type

Attribute

Syntax

&lt; Path &gt;.InvestmentCosts:real

Assignment Value

You can assign a value of data type real .

Example

MyStation.InvestmentCosts := 100000

See also

Depreciation Period [text box]

Investment Costs [text box]

Investment Costs per Length [text box]

InvestmentCostsPerLength [SimTalk]

Sets the investments costs of the Conveyor designated by &lt;Path&gt; in the defined currency unit per meter.

Remarks

**Note**

You can only specify Investment Costs per Length for the Conveyor .

**Note**

The total investment costs are the sum of the Investment Costs and the Investment Costs per Length which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period and then do not accrue anymore.

Type

Attribute

Syntax

&lt; Path &gt;.InvestmentCostsPerLength:real

Assignment Value

You can assign a value of data type real .

Example

MyConveyor.InvestmentCostsPerLength := 1000

See also

Depreciation Period [text box]

Investment Costs [text box]

Investment Costs per Length [text box]

OperatingCosts [SimTalk]

Sets the operating costs of the object designated by &lt;Path&gt; in the defined currency unit per year. Operating costs are, among others, electricity, maintenance, building rent, etc.

Remarks

The total operating costs are the sum of the Operating Costs and the Operating Costs per Length which result from the actual length of an inserted instance of the Conveyor .

Type

Attribute

Syntax

&lt; Path &gt;.OperatingCosts:real

Assignment Value

You can assign a value of data type real .

Example

MyStation.OperatingCosts := 100

See also

Operating Costs [text box]

Operating Costs per Length [text box]

OperatingCostsPerLength [SimTalk]

Sets the operating costs of the Conveyor designated by &lt;Path&gt;.

Remarks

Operating Costs designate the operating costs in the currency unit you selected per year and meter of the conveyor. The operating costs per length are specified in Euros per year times meters.

Operating Costs are, among others, electricity, maintenance, building rent, etc.

**Note**

The total operating costs are the sum of the Operating Costs and the Operating Costs per Length which result from the actual length of an inserted instance of the Conveyor .

**Note**

You can only specify Operating Costs per Length for the Conveyor .

Type

Attribute

Syntax

&lt; Path &gt;.OperatingCostsPerLength:real

Assignment Value

You can assign a value of data type real .

Example

MyStation.OperatingCostsPerLength := 100

See also

Operating Costs per Length [text box]

Operating Costs [text box]

###### Attributes for Statistics

###### Attributes for Statistics

The material flow objects provide the attributes listed in the table of contents to the left for setting and activating resource statistics.

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**See also**

Tab Statistics [material flow objects]

**ResourceType [SimTalk]**

###### ResourceType [SimTalk]

Sets the type of resource for the object designated by &lt;Path&gt;.

Remarks

ResourceType only affects statistics collection of the MUs located on the object.

<!-- image -->

Type

Attribute

Syntax

```simtalk
< Path >.ResourceType:string
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type string .

You can specify "Production" , "Storage" , or "Transport" .

Example

```simtalk
MyTrack.ResourceType := "storage"
```

**See also**

**Resource Type**

**Additional Statistical Data of the MUs**

###### ResStatOn [SimTalk] - material flow objects

Activates statistics collection of the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

ResStatOn is inherited. If you want to activate or deactivate statistics collection for all instances of a class, assign true or false to ResStatOn .

As opposed to the method InitStat the attribute ResStatOn does not set the point in time at which statistics collection starts.

Type

Attribute

Syntax

```simtalk
< Path >.ResStatOn:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if MyStation.ResStatOn = true
	print MyStation.waitingPortion
end .ParallelStation.ResStatOn := false // also deactivates statistics collection for all instances that inherit values
```

See also

Resource Statistics [check box]

initStat [SimTalk] - material flow objects

**Attributes of the Controls**

**\_Attributes of the Controls**

The material flow objects provide the attributes listed in the table of contents to the left to trigger the methods you defined when a MU enters or exits the material flow object.

You can also select these settings in the dialogs of the objects on the Tab Controls .

To view all of the methods and attributes of the material flow object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set and get the value of the attributes, either with the check boxes, the text boxes, and the drop-down lists in the dialog windows, or by assigning a value to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

BwEntranceCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method when the MU enters the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt; via their exit and/or when it moves toward their entrance after entering.

Type

Attribute

Syntax

< Path >.BwEntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
MyTrack.BwEntranceCtrl := &myBackwardEntranceCtrl
MyTwoLaneTrack.B.BwEntranceCtrl := self.OnBwEntrance
MyConveyor.BwEntranceCtrl := &myBackwardEntranceCtrl
.MUs.Transporter:2.LoadBayType := "Track" .MUs.Transporter:2.BwEntranceCtrl := &myBackwardEntranceCtrl
```

See also

Backward Entrance Control

###### BwEntranceCtrlFront [SimTalk] - material flow objects

Sets if the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt; activate the Backward Entrance Control , when the Front of the MU enters them via their exit and/or when it moves toward their entrance after entering ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.BwEntranceCtrlFront:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
MyTrackBwEntranceCtrl := &Method1
MyTrack.BwEntranceCtrlFront := true
MyTwoLaneTrack.B.BwEntranceCtrl := &myBwEntranceCtrl
MyTwoLaneTrack.B.BwEntranceCtrlFront := true
MyConveyor.BwEntranceCtrl := Method2
MyConveyor.BwEntranceCtrlFront := false
.MUs.Transporter:2.LoadBayType := "Track" .MUs.Transporter:2.LoadBayType := &myBwEntranceCtrl .MUs.Transporter:2.BwEntranceCtrlFront := false
```

**See also**

Backward Entrance Control

**BwEntranceCtrlRear [SimTalk] - material flow objects**

Activates the Backward Entrance Control of the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt;, when the Rear of the MU enters them via their exit and/or when it moves toward their entrance after entering ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.BwEntranceCtrlRear:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
MyTrack.BwEntranceCtrl := &Method1
MyTrack.BwEntranceCtrlRear := true
MyTwoLaneTrack.B.BwEntranceCtrl := &myBwEntranceCtrl
MyTwoLaneTrack.B.BwEntranceCtrlRear := true
MyConveyor.BwEntranceCtrl := &Method2
MyConveyor.BwEntranceCtrlRear := false
.MUs.Transporter:2.LoadBayType := "Track" .MUs.Transporter:2.BwEntranceCtrl := &myBwEntranceCtrl .MUs.Transporter:2.BwEntranceCtrlRear := false
```

**See also**

Backward Entrance Control

**BwExitCtrl [SimTalk] - material flow objects**

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Method when the MU exits the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt; via their entrance and/or when it moves toward their entrance when exiting.

Type

Attribute

Syntax

< Path >.BwExitCtrl:method

Assignment Value

You can assign a value of data type method .

**Examples**

```simtalk
MyTrack.BwExitCtrl := &myBackwardExitCtrl
MyTwoLaneTrack.A.BwExitCtrl := &myBackwardExitCtrl
MyConveyor.BwExitCtrl := &myBackwardExitCtrl
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrl := &myBackwardExitCtrl
waituntil Station1.Occupied und
Station1.Cont.Ready prio 1
Station1.Cont.move(@) // load the part
@.Destination := ConveyorA
ConveyorD.Backwards := false
```

See also

**Backward Exit Control**

###### BwExitCtrlFront [SimTalk] - material flow objects

Activates the Backward Exit Control of the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt;, when the Front of the MU exits them via their entrance and/or when it moves toward their entrance when exiting ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.BwExitCtrlFront:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

Examples

```simtalk
MyTrack.BwExitCtrlFront := false
MyTwoLaneTrack.A.BwExitCtrlFront := true
MyConveyor.BwExitCtrlFront := true
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrlFront := false
```

See also

**Backward Exit Control**

###### BwExitCtrlRear [SimTalk] - material flow objects

Activates the Backward Exit Control of the length-oriented objects Conveyor , Track , or TwoLaneTrack designated by &lt;Path&gt;, when the Rear of the MU exits via their entrance and/or when it moves toward their entrance when exiting ( true ) or not ( false ).

Remarks

Specify true for BwExitCtrlRear , to make the object activate the Backward Exit Control when the rear of the part exits the object moving in reverse.

Type

Attribute

Syntax

```simtalk
< Path >.BwExitCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

**Examples**

```simtalk
MyTrackBwEntranceCtrl := &Method1
MyTrack.BwEntranceCtrlRear := true
MyTwoLaneTrack.B.BwEntranceCtrl := &myBwEntranceCtrl
MyTwoLaneTrack.B.BwEntranceCtrlRear := true
MyConveyor.BwEntranceCtrl := Method2
MyConveyor.BwEntranceCtrlRear := false
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrlRear := false
```

**See also**

**Backward Exit Control**

###### EntranceCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as a MU enters the object designated by &lt;Path&gt;. If you did not specify a method , the attribute EntranceCtrl returns the value VOID.

**Note**

As the MU is already located on the object when the Entrance Control is called, set-up and processing times for this MU cannot be changed any more.

Use the attribute EntranceCtrlBeforeActions to still set the times in the Entrance Control .

Type

Attribute

Syntax

&lt; Path &gt;.EntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
// is an entrance control entered?
if MyStation.EntranceCtrl = VOID
	MyStation.EntranceCtrl := &myEntranceCtrl // control exists
end
// entrance control of the object 'MyStore'
var NextRow: integer // find free row in the 'InventoryTable' of 'MyStore'
NextRow := Inventory.ydim + 1 // enter the ID of the new part and the path // to the part in the 'InventoryTable' InventoryTable[0,NextRow] :=
@.id
InventoryTable[1,NextRow] := @ AttemptToRemoveNextPart
// increase the capacity of 'MyStore' if needed
if MyStore.full
	MyStore.xDim := MyStore.xDim + 4
end
```

SimTalk

EntranceCtrlBeforeActions [SimTalk]

See also

Entrance Control [general description]

Create Entrance and Exit Controls

Change the Processing Time in the Entrance Control

Change the Importer Services in the Entrance Control

Change the Assembly Table in the Entrance Control

###### EntranceCtrlBeforeActions [SimTalk]

Activates the Entrance Control of the object designated by &lt;Path&gt; before the standard actions are executed ( true ) or after they are executed ( false ).

Remarks

Actions encompass starting the Processing Time or the Set-up Time , requesting services through the importer , or changing the Assembly Table of the AssemblyStation .

**Note**

You cannot change the Assembly Table if the Main MU is already located on the AssemblyStation . To change the Assembly Table in the Entrance Control of the Station , select the check box Before Actions of the Entrance Control .

Type

Attribute

Syntax

&lt; Path &gt;.EntranceCtrlBeforeActions:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyAssemblyStation.EntranceCtrlBeforeActions := true

See also

Entrance Control [general description] &gt; Before actions

Create Entrance and Exit Controls

Change the Processing Time in the Entrance Control

Change the Importer Services in the Entrance Control

Change the Assembly Table in the Entrance Control

###### EntranceCtrlFront [SimTalk] - material flow objects

Activates the Entrance Control of the object designated by &lt;Path&gt; as soon as the Front of the MU enters the object ( true ) or does not activate it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EntranceCtrlFront:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if MyTrack.EntranceCtrlFront = false
	MyTrack.EntranceCtrlFront := true
end
```

See also

Entrance Control [general description] &gt; Front EntranceCtrlRear [SimTalk] - material flow objects Activates the Entrance Control of the object designated by &lt;Path&gt; as soon as the Rear of the MU enters the object ( true ) or does not activate it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.EntranceCtrlRear:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.EntranceCtrlRear := true

See also

Entrance Control [general description] &gt; Rear

###### ExitCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Method as soon as a MU exits the object designated by &lt;Path&gt;. If you did not specify the name of a method , the attribute ExitCtrl returns VOID.

**Note**

If the MU is a Transporter with a Destination Control , the Destination Control will not be called.

**Note**

The Exit Control can have an optional parameter of data type object . If the method has this parameter, then the successor object, which pulls the MU because the MU was contained in the blocking list of the object, will be assigned to this parameter. The MU will be pulled, for example, when the successor becomes available again or when its entrance is opened.

**Note**

A Front -triggered Exit Control is only called for the last station of the cycle defined by the object Cycle as the Destination for all other stations of the cycle is already set. Use a Rear -triggered Exit Control instead.

**Note**

The event CheckMUPosition (compare the List of Events ) is scheduled when the Exit Control is called and checks, after processing the Exit Control , if the MU has to be stopped. This is the case when neither the position of the front of the MU in the direction of motion nor its Direction changed. This prevents that the MU is stopped before calling the Exit Control .

The standard exit control as a user-defined attribute looks like this:

<!-- image -->

Type

Attribute

**Syntax**

< Path >.ExitCtrl:method

**Assignment Value**

You can assign a value of data type object/method .

**Examples**

```simtalk
// This is the exit control for all stations and for the source. // This control can be called several times until the move command is successful.
var WorkPlan : table,
var NextStation : object WorkPlan := root.MyWorkPlan["Operations",@.PartType]
if @.PositionInWorkPlan = WorkPlan.ydim
	@.Move(root.Shipping) // end of production
else
	NextStation := WorkPlan["Operation", @.PositionInWorkPlan + 1]
	if @.Move(NextStation)
		@.PositionInWorkPlan := @.PositionInWorkPlan + 1
	end
end
var n: integer
n := Station.StatNumIn
if n = 100 then @.move(Station1)
elseif n = 300
	@.move(Station2)
else
	@.move(Station3)
end
```

// rear-triggered exit control of the station 'RetrieveFromStore' // catches the event after a part has been successfully // removed from the Store and left the station 'RetrieveFromStore' AttemptToRemoveNextPart

```simtalk
MyStation.ExitCtrl := &Method  // enter control
MyStation.ExitCtrl := VOID     // and delete it again
// Exit control of the station Arrival
var WorkerTab:object := AssignedWorkers
if NOT WP_Arrival.empty
var Worker1 := WP_Arrival.cont
WorkerTab.setCursor(1,1)
WorkerTab.find({1,1}..{1,*}, worker1)
WorkerTab[2,WorkerTab.cursorY] := true
Arrival.cont.move(Worker1)
waituntil Arrival.succ.~.WP_buffer.entranceFree
Worker1.goto(Arrival.succ.~.WP_buffer)
return
end
WorkerTab.setCursor(2,1)
if WorkerTab.find({2,1}..{2,*}, false)
	var row:integer := WorkerTab.cursorY
	WorkerTab[2,row] := true;
	Arrival.WorkerWasOrdered := true // assigned
	var Worker := WorkerTab[1,row]
	waituntil WP_Arrival.entranceFree
	Worker.goto(WP_Arrival)
	waituntil Worker.~ = WP_Arrival
	Arrival.cont.move(Worker);
	Arrival.WorkerWasOrdered := false
	waituntil Arrival.succ.~.WP_buffer.entranceFree
	Worker.goto(Arrival.succ.~.WP_buffer)
end
-- exit control of the working station var currPart,nextPart,StreetObj,LocObj,destObj:object
currPart := @
TransportOrders.push(currPart)
StreetObj := Vehicle.~
if NOT Vehicle.hasOrder
	nextPart := TransportOrders.pop
	if StreetObj.A.numSensors > 0
		if Vehicle.getLaneNo = 1
			LocObj := StreetObj.A.sensorID(1).destination
		else
			LocObj := StreetObj.B.sensorID(2).destination
		end
		if nextPart.~ = LocObj  -- a stopped vehicle at the right place
			currPart.move(Vehicle)
			repeat -- find a free processing station
				destObj := to_str("S", ceil(z_uniform(1,1,8)))
			until destObj.empty
			Vehicle.destination := destObj
		else
			Vehicle.destination := currPart.~
		end
	else
		Vehicle.destination := currPart.~
end
Vehicle.hasOrder := true
Vehicle.stopped := false
```

end

**See also**

Exit Control [general description]

List of Events

Create Entrance and Exit Controls

Distribute Parts with an Exit Control

###### ExitCtrlFront [SimTalk] - material flow objects

Activates the Exit Control of the object designated by &lt;Path&gt; as soon as the Front of the MU exits ( true ) the object or does not activate it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ExitCtrlFront:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.ExitCtrlFront := false

See also

Exit Control [general description] &gt; Front

**ExitCtrlOnce [SimTalk]**

###### ExitCtrlOnce [SimTalk]

Activates the exit control of the object designated by &lt;Path&gt; only once when the part intends to exit the object ( true ) or if the exit control is triggered again when the part is unblocked ( false ).

Remarks

If the target station cannot receive the part, the part is entered into the Entrance Blocking List of the target station. As soon as the target station becomes available again, the part is unblocked. To call the Exit Control again now, specify false .

**Note**

If the station is failed or paused , all transfer processes are canceled, and the parts are removed from the Entrance Blocking Lists of the succeeding stations. Once the station becomes operational again, the fully processed parts get a new Out event and the Exit Control is called again independent of this setting.

Type

Attribute

Syntax

```simtalk
< Path >.ExitCtrlOnce:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrack.ExitCtrlOnce := true
```

To detect if the Exit Control is called because the part is unblocked , and by which object the part is unblocked, you can declare the Exit Control with a parameter of type object :

Example

```simtalk
param unblockObject:object
if unblockObject /= void
	@.move(unblockObject)
else
	@.move // trigger the standard exit behavior
end
```

If the Exit Control is called for the first time, the parameter is void. If the part was entered into the Forward Blocking list of an object, which unblocked the part, the parameter references the object for which the part was waiting.

See also

Exit Control [general description] &gt; Exit Control Once ExitCtrlRear [SimTalk] - material flow objects Activates the Exit Control of the object designated by &lt;Path&gt; as soon as the Rear of the MU exits ( true ) or does not activate it ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.ExitCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrack.ExitCtrlRear := true
```

See also

Exit Control [general description] &gt; Front and Rear [exit control]

###### PullCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Method whenever the object designated by &lt;Path&gt; is ready to receive a new MU or when it is ready, when a new MU is waiting at its entrance.

In the Pull Control you can determine which of the parts, which intends to move onto the object, the object will accept. For this you have to get the Forward Blocking List with the method fwBlockList and unblock a MU in the list with the method unblock .

**Note**

If you only need the first entry of the Forward Blocking List , use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

Let us assume that red parts are especially important and thus have a priority for being processed. Then you can always pull red parts first from the predecessors and only then pull parts in other colors.

**Note**

The Pull Control does not determine if a MU is to be moved to this or to another successor. Instead, it selects one of the parts which have already determined to move on to this successor.

**Note**

A Pull Control will not be called for the stations of the object Cycle .

**Note**

For the objects Conveyor , Track , and TwoLaneTrack the Pull Control only applies to MUs moving in the forward direction, i.e., to objects, which move onto them at their entrance and exit them at their exit . It does not apply to MUs moving onto them backward at their exit and not to MUs that have been moved to a certain position.

**Note**

For the Converter the Pull Control also applies for parts that enter the object at the exit moving in reverse.

Type

Attribute

**Syntax**

< Path >.PullCtrl:method

**Assignment Value**

You can assign a value of data type object/method .

**Examples**

```simtalk
MyStation.PullCtrl := &myPullControl
var blockList:table // @,?: the object for which a pull control was called // implements the method myPullControl
?.fwBlockList(blockList)
var n:integer := 1
?.unblock(blockList[1,n]) // n sets the row in the blockList, i.e., // the MU to be unblocked
// ?: the object for which the control was called // @: the MU for which the object was called, //    during unblocking the identifier @ has the value void //var
blockList := ?.fwBlocklist
?.unblock(?.fwBlockListEntry1)
-- The Station pools the MUs -- according to the last color.
var BlockTable    :table BlockTable.create -- creates the structure for the local variable -- BlockTable, which is of the type table
Station.fwBlockList(BlockTable) -- copies the forward blocking list in -- the local table BlockTable
var type:string := Station.IsSetupFor -- copies the type of MU which the parallel station -- has been set up for to the variable "type"
if BlockTable.findAttr("color", type) -- checks, if a part with the same color type -- exists in the table BlockTable
	?.unblock(BlockTable[1,BlockTable.cursorY]) -- unblock the part with the same color -- BlockTable.cursorY returns the row number -- where the part was found in the "findAttr" -- command above else    -- of
	if BlockTable.findAttr("color", type)
if BlockTable.yDim>0 -- checks, if at least one part is in the table
	?.unblock(BlockTable[1,1]) -- unblock the first part
end
end    -- of
if BlockTable.findAttr("color", type),
else
-- A typical pull control -- using the forward blocking list
var BlockTable:table BlockTable.create -- creates the structure for the local variable -- BlockTable, which is of the type table
Drain.fwBlockList(BlockTable) -- copies the forward blocking list in -- the local table BlockTable
Drain.unblock(BlockTable[1,1]) -- unblocks the first part from the local table -- BlockTable
```

**SimTalk**

FwBlockListEntry1 [SimTalk]

fwBlockList [SimTalk] - material flow objects

unblock [SimTalk]

See also

Pull Control [general description]

SetupCtrl [SimTalk] - material flow objects

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever a set-up process of the object designated by &lt;Path&gt; starts or ends. If you did not enter the name of a method , the attribute SetupCtrl returns VOID.

Use the read-only attribute ResSetup to find out if the set-up process starts or ends.

When ?.setup returns true , the set-up process just started.

The standard set-up control as a user-defined attribute looks like this:

<!-- image -->

Type

Attribute

Syntax

< Path >.SetupCtrl:method

Assignment Value

You can assign a value of data type object/method .

Example

```simtalk
MyStation.SetupCtrl := &mySetUpControl
```

SimTalk

ResSetup [SimTalk] - material flow objects

See also

Set-up Control

**ShiftCalendarObject [SimTalk] - material flow objects**

Sets the ShiftCalendar which the material flow object designated by &lt;Path&gt; uses when it is working in shifts.

Type

Attribute

Syntax

&lt; Path &gt;.ShiftCalendarObject:path

Assignment Value

You can assign a value of data type path .

Example

MyStation.ShiftCalendarObject := MyShiftcalendar

See also

Shift Calendar [tab Controls]

Attributes for Setting the Exit Strategy

\_Attributes for Setting the Exit Strategy

The Source , the Station , the ParallelStation , the PlaceBuffer , the Buffer , the Sorter , the Conveyor , the Track , and the TwoLaneTrack provide the attributes listed in the table of contents to the left for setting and getting their exit strategy.

You can also select these settings in the dialogs of the objects on the Tab Exit .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

###### AttributeType [SimTalk] - material flow objects

Sets the data type of the attributes that determine how the object designated by &lt;Path&gt; moves the MUs on to its successors when you set the attribute ExitStrategy to "MU Attribute" .

Type

Attribute

Syntax

```simtalk
< Path >.AttributeType:string
```

Assignment Value

You can assign a value of data type string .

You can assign one of these Data Types .

| Acceleration   | Method   |
|----------------|----------|
| Any            | Object   |
| Array          | Queue    |
| Boolean        | Real     |
| Date           | Speed    |
| DateTime       | Stack    |
| Integer        | String   |
| JSON           | Table    |
| Length         | Time     |
| List           | Weight   |

**Example**

```simtalk
ParallelStation.AttributeType := "integer"
```

SimTalk

ExitStrategy [SimTalk] - material flow objects

**See also MU Attribute [described]**

**Data Types [SimTalk]**

DefaultSuccessor [SimTalk] - material flow objects

Sets the number of the Default Successor to which the object designated by &lt;Path&gt; moves the part when you set the attribute ExitStrategy to "MU Attribute" .

Remarks

The default successor is the successor to which the material flow object moves the MU , when this MU does not have an attribute with the Value you specified in the DataTable .

Type

Attribute

Syntax

&lt; Path &gt;.DefaultSuccessor:integer

Assignment Value

You can assign a value of data type integer .

To show a message, when a part is to be moved which does not meet any of the conditions in the DataTable , specify 0 .

Example

```simtalk
ParallelStation.DefaultSuccessor := 1
```

SimTalk

ExitStrategy [SimTalk] - material flow objects

See also

MU Attribute [described]

DefaultSuccessor [SimTalk] - material flow objects

###### ExitStrategy [SimTalk] - material flow objects

Sets the Exit Strategy for MUs which leave the material flow object designated by &lt;Path&gt;.

Remarks

**Note**

For length-oriented objects Plant Simulation only takes the Exit Strategy into account, when the part moves in the forward direction.

Type

Attribute

Syntax

&lt; Path &gt;.ExitStrategy:string

Assignment Value

You can assign a value of data type string .

You can specify " Cyclic ", " Start at successor 1 ", " Random ", " Percentage ", " Cyclic sequence ", " Linear sequence ", " Least recent demand ", " Most recent demand ", " Max. contents "," Min. contents ", " Max. proc. time ", " Min. proc. time ", " Max. set-up time ", " Min. set-up time ", " Max. num. in ", " Min. num. in ", " Max. rel. occu. ", " Min. rel. occu. ", or " MU Attribute ".

**Example**

```simtalk
ParallelStation.ExitStrategy := "random"
```

See also

Tab Exit [general description]

###### ExitStrategyBlocking [SimTalk]

Sets whether the material flow object designated by &lt;Path&gt; uses the blocking behavior when a MU exits ( true ) or not ( false ).

**Remarks**

- Specify true for ExitStrategyBlocking to always move the part to the designated successor. If that successor is not ready to receive it, the part will be blocked.

When moving the part fails, Plant Simulation enters the part into the Forward Blocking List of the designated successor.

- Specify false for ExitStrategyBlocking to move the part to any of its successors, which can receive it. The part will only be blocked, if none of the successors can receive it.

When none of the successors can receive the part , Plant Simulation enters it into the Forward Blocking List of all successors.

**Note**

The non-blocking Exit Strategy &gt; MU Attribute moves the part on when any of the objects, which meet one of the criteria, can receive the part.

In both cases Plant Simulation schedules an Out event for the part , when a successor, whose Forward Blocking List contains the part , can receive it.

Type

Attribute

Syntax

&lt; Path &gt;.ExitStrategyBlocking:boolean

Assignment Value

You can assign a value of data type boolean .

Example

ParallelStation.ExitStrategyBlocking := true

See also

Blocking [exit strategy] , check box

**Forward Blocking List**

**MU Attribute [described]**

Out event

**ExitStrategyMUAttributeList [SimTalk]**

###### ExitStrategyMUAttributeList [SimTalk]

Sets the contents of the attribute list of the material flow object designated by &lt;Path&gt; for the Exit Strategy &gt; MU Attribute .

Remarks

You can enter several numbers of the desired successors into the Attribute List for the Attribute Value .

In the non-blocking case Plant Simulation checks which of the desired successors can receive the MU . If none of the desired successors can receive the MU , Plant Simulation inserts the MU into the Blocking List of these successors.

Type

Attribute

Syntax

< Path >.ExitStrategyMUAttributeList

Assignment Value

You can assign a value of data type table .

Example

<!-- image -->

```simtalk
var t:table[string,string,integer]
t.create
t.writeRow(1, 1, "Name", "A", 1)
t.writeRow(1, 2, "Name", "B", 2)
MyStation.ExitStrategyMUAttributeList := t
```

See also

**MU Attribute [described]**

Data Held in Tabular Form in Attributes [material flow objects]

ExitStrategyPercentageValues [SimTalk] - material flow objects

Sets the contents of the internal exit list of the material flow object designated by &lt;Path&gt; for the Exit Strategies &gt; Percentage and Random .

Type

Attribute

Syntax

< Path >.ExitStrategyPercentageValues:array

Assignment Value

You can assign a value of data type array .

Examples

```simtalk
MyStation.ExitStrategy := "Percentage"
MyStation.ExitStrategyPercentageValues := [1,2,3]
MyStation.ExitStrategy := "Random"
MyStation.ExitStrategyPercentageValues := [2,1,3]
```

See also

Percentage [described] , drop-down list

Random [described] , drop-down list

Data Held in Tabular Form in Attributes [material flow objects]

###### ExitStrategySequence [SimTalk]

Sets the contents of the internal exit list of the material flow object designated by &lt;Path&gt; for the Exit Strategies &gt; Cyclic sequence and Linear sequence .

Type

Attribute

Syntax

< Path >.ExitStrategySequence:array

Assignment Value

You can assign a value of data type array .

Examples

```simtalk
MyStation.ExitStrategy := "Cyclic sequence"
MyStation.ExitStrategySequence := [2,1,3]
MyStation.ExitStrategy := "Linear sequence"
MyStation.ExitStrategySequence := [3,2,1]
```

See also

Cyclic Sequence [described]

Linear Sequence [described]

**MaxDwellTime [SimTalk]**

###### MaxDwellTime [SimTalk]

Sets the time during which the Worker waits for the parts at the object designated by &lt;Path&gt;, which he is to carry to the target station ( MU Target ).

Remarks

Once the Maximum Dwelling Time has passed, the Worker walks to the target station, no matter if his carrying capacity is met or not. You can use the anonymous identifier @ to access the Worker for whom the Maximum Dwell Time applies. The Worker picks up the parts which the station finished processing within the Maximum Dwelling Time .

**Note**

If you want the Worker to wait until he can pick up all parts up to his carrying capacity, specify a very long time.

**Note**

The maximum dwell time only applies to the objects, which provide a transport-importer , i.e., for the Station , the ParallelStation , the AssemblyStation , the DismantleStation , the Sorter , the Buffer and the PlaceBuffer .

Type

Attribute

Syntax

&lt; Path &gt;.MaxDwellTime:time

Assignment Value

You can assign a value of data type time .

Example

MyStation.MaxDwellTime := 3.000

See also

Maximum Dwell Time [transport importer]

MU Target

###### MUTarget [SimTalk]

MUTarget [SimTalk]

Sets the MU Target for the transport importer of the object designated by &lt;Path&gt;.

Remarks

The MU Target is the Workplace attached to the work station, which processes the part next and to which the Worker carries the part, or the work station itself.

**Note**

If you specify a MU Target , the Worker carries all parts to this target.

If you do not specify a MU Target , the Dismantle Table or the setting Main MU to Successor with Number determine it.

Type

Attribute

Syntax

&lt; Path &gt;.MUTarget:object

Assignment Value

You can assign a value of data type object .

Example

MyStation.MUTarget := MyWorkplace3

See also

MU Target

Dismantle Table [button] - DismantleStation

Main MU to Successor with Number [text box] - DismantleStation

**Attributes of the Importer**

##### \_Attributes of the Importer

The Importer of some of the material flow and of the fluid object provides the attributes listed in the table of contents.

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

Imp

Plant Simulation addresses the importer attributes, except for Active , as sub-attributes of Imp in attributes.

**Note**

In a control the number 2 designates the processing-importer .

**Example**

ParallelStation.Imp.Priority := 10

**SetupImp**

Plant Simulation addresses the setup-importer attributes, except for Active , as sub-attributes of SetupImp in attributes.

**Note**

In a control the number 1 designates the set-up-importer .

**Example**

```simtalk
MyStation.SetupImp.Priority := 40
```

**FailImp**

Plant Simulation addresses the failure-importer attributes, except for Active , as sub-attributes of FailImp in attributes.

**Note**

In a control the number 0 designates the failure-importer .

**Example**

```simtalk
MyStation.FailImp.Priority := 60
```

**TransportImp**

Plant Simulation addresses the transport-importer attributes, except for Active , as sub-attributes of TransportImp in attributes.

**Note**

In a control the number 3 designates the transport-importer .

**Example**

```simtalk
MyStation.TransportImp.Priority := 20
```

The window Show Attributes and Methods shows the identifiers Imp , SetUpImp , Faillmp , and TransportImp for the Importer , but not the actual attributes of these importer types.

<!-- image -->

**See also**

###### Tab Importer [general description]

\_Methods of the Importer

###### Active [SimTalk] - importer

Active [SimTalk] - importer

Activates ( true ) or deactivates ( false ) the importer of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Imp.Active:boolean < Path >.FailImp.Active:boolean < Path >.SetupImp.Active:boolean < Path >.TransportImp.Active:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
ParallelStation.Imp.Active := true
MyStation.FailImp.Active := false
MyStation.SetupImp.Active := true
MyStation.TransportImp.Active := true
```

**See also**

Processing Importer &gt; Active [check box] - processing importer

Set-up Importer &gt; Active [check box] - set-up importer

Failure Importer &gt; Active [check box] - failure importer

Failure Importer &gt; Active [check box] - transport importer

###### BrokerPath [SimTalk] - importer

Designates the Broker of the importer of the object designated by &lt;Path&gt;. The Exporter uses this Broker to provide its services.

Remarks

For Broker hierarchies Plant Simulation only calls the control of this Broker , not the controls of any existing sub-Brokers .

Type

Attribute

Syntax

```simtalk
< Path >.FailImp.BrokerPath:object < Path >.Imp.BrokerPath:object < Path >.SetupImp.BrokerPath:object < Path >.TransportImp.BrokerPath:object
```

Assignment Value

You can assign a value of data type object .

Example

```simtalk
ParallelStation.Imp.BrokerPath := Broker3
MyStation.FailImp.BrokerPath := myBroker2
```

See also

Broker [processing importer]

Broker [failure importer]

Broker [set-up importer]

Broker [transport importer]

**Common [SimTalk]**

###### Common [SimTalk]

Activates common resources ( true ) of the importer of the object designated by &lt;Path&gt; or deactivates them ( false ).

Remarks

Activating Common Resources deactivates the set-up-importer . The processing-importer requests Exporters/Workers when set-up starts and releases them when processing is finished.

When you deactivate Common Resources , the processing-importer will only request Exporters/Workers when processing starts. At the beginning of setting-up, the set-up-importer requests Exporters/Workers and releases them when setting-up is finished.

Type

Attribute

Syntax

```simtalk
< Path >.Imp.Common:boolean < Path >.SetupImp.Common:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyStation.Imp.Common := true
```

See also

Common Resources [set-up importer]

###### Interruptible [SimTalk]

Enables importers with a higher priority to withdraw resources, i.e., Workers or Exporters , from this importer from the object designated by &lt;Path&gt; ( true ) or not ( false ).

**Remarks**

When an importer with higher priority requests services, which the freely available resources cannot fulfill, and when sufficient interruptible importers with lower priority are available, to which the required services are brokered at the moment, then as many interruptible importers are interrupted as required to satisfy the importer with higher priority. The tasks ( processing / setting-up / repair / transport ), which the interrupted importer performs, will then be interrupted, and the resources are brokered to the importer with higher priority.

Type

Attribute

Syntax

```simtalk
< Path >.Imp.Interruptible:boolean < Path >.FailImp.Interruptible:boolean < Path >.SetupImp.Interruptible:boolean < Path >.TransportImp.Interruptible:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
ParallelStation.Imp.Interruptible := false
MyStation.FailImp.Interruptible := true
MyStation.SetupImp.Interruptible := true
MyStation.TransportImp.Interruptible := true
```

**See also**

Can Be Interrupted and Drawn Off [set-up importer]

Can Be Interrupted and Drawn Off [failure importer]

Can Be Interrupted and Drawn Off [set-up importer]

Can Be Interrupted and Drawn Off [transport importer]

###### MU [SimTalk] - importer

Queries the MU for which a resource was ordered by the specified importer type of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Imp.MU < Path >.FailImp.MU < Path >.SetupImp.MU < Path >.TransportImp.MU
```

**Example**

```simtalk
MyStation.Imp.MU
MyStation.FailImp.MU
MyStation.SetupImp.MU
MyStation.TransportImp.MU
```

###### Priority [SimTalk] - importer

Priority [SimTalk] - importer

Sets the priority with which the importer of the object designated by &lt;Path&gt; fulfills a request.

Remarks

The Priority of an importer is a criterion for the urgency of a request.

If the importer is not assigned an Exporter immediately after a request, the importer will be entered in the list of unsatisfied requests of the Broker that is arranged according to priority.

Type

Attribute

Syntax

```simtalk
< Path >.FailImp.Priority:integer < Path >.Imp.Priority:integer < Path >.SetupImp.Priority:integer < Path >.TransportImp.Priority:integer
```

Assignment Value

You can assign a value of data type integer .

The higher the value that you enter, the higher is the priority. Plant Simulation provides a service with Priority 10 before providing a service with Priority 1 .

Example

```simtalk
ParallelStation.Imp.Priority := 4
MyStation.FailImp.Priority := 15
```

See also

Priority [processing importer]

Priority [failure importer]

Priority [set-up importer]

Priority [transport importer]

###### ReceiveCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever Exporters/Workers were assigned to the importer of the object designated by &lt;Path&gt;.

The Exporter/Worker is already located at the station and provides the service.

The Receive Control is called after the Entrance Control of the Workplace and after the Order Control of the Exporter/Worker .

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation.

Type

Attribute

Syntax

< Path >.FailImp.ReceiveCtrl:method < Path >.Imp.ReceiveCtrl:method < Path >.SetupImp.ReceiveCtrl:method < Path >.TransportImp.ReceiveCtrl:method

Parameters

The Receive Control you specify has to define two parameters:

- The parameter Type of data type integer designates the type of the importer : 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transportimporter .
- The parameter Exporters is an array of data type object that contains all brokered Exporters/Workers .

If Exporters/Workers were requested for a part, you have to start carrying away the part with the method startProcessing . You can also model travel times with a wait-instruction before calling the method startProcessing .

**Example**

```simtalk
// importer type (0 is the failure, 1 the setup, 2 the process, 3 the transport importer)
param type: integer, exporters: object[MyExporter]
if type = 1
```

machine.SetupImp.startSetup

else machine.Imp.startProcessing end

Assignment Value

You can assign a value of data type method .

Reformatting the Method

When you manually enter a Receive Control and click Apply or OK , Plant Simulation automatically checks if the method expects the correct parameters. If this is not the case, it shows a message asking to reformat the method or not. Plant Simulation automatically re-formats empty methods. You cannot suppress checking of the format of the Method .

Example

```simtalk
MyStation.FailImp.ReceiveCtrl := &myReceiveCtrl
```

SimTalk

startProcessing [SimTalk] - importer

See also

Receive Control [processing importer]

Receive Control [set-up importer]

Receive Control [failure importer]

Receive Control [transport importer]

Entrance Control [Workplace]

Order Control [Worker]

Request Control [processing importer]

Release Control [processing importer]

Reset Simulation [EventController]

###### ReleaseAllServices [SimTalk]

Sets if the importer of the object designated by &lt;Path&gt; releases all services when one or more of these services are failed or paused ( true ) or if it only releases the failed services ( false ). This also applies if a service was interrupted because it was requested by an importer with higher priority.

Remarks

Release All Services only works, when you also select the check box Fail Services of the Exporter or set the attribute FailServices to true . For the Worker Fail Services is always activated implicitly.

Type

Attribute

Syntax

```simtalk
< Path >.Imp.ReleaseAllServices:boolean < Path >.SetupImp.ReleaseAllServices:boolean < Path >.FailImp.ReleaseAllServices:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation.Imp.ReleaseAllServices := true
```

SimTalk

FailServices [SimTalk]

See also

Fail Services [text box]

Release All Services When One Of Them Is Failed [set-up importer]

Release All Services When One Of Them Is Failed [failure importer]

Release All Services, When One Of Them Is Failed [processing importer]

**ReleaseCtrl [SimTalk] - importer**

###### ReleaseCtrl [SimTalk] - importer

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Method as soon as the importer of the object designated by &lt;Path&gt; releases the Exporters by default. When Exporters were requested for a MU , you have to start processing of the MU with the method startProcessing . By calling startProcessing later you can also display times the part spent moving between objects.

You have to release the Exporters with the method releaseExporters . By calling startProcessing later on you can model traveling times.

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation.

Type

Attribute

Syntax

< Path >.FailImp.ReleaseCtrl:method < Path >.Imp.ReleaseCtrl:method < Path >.SetupImp.ReleaseCtrl:method < Path >.TransportImp.ReleaseCtrl:method

**Parameter**

The Release Control you enter has to define a parameter of data type integer characterizing the type of the importer : 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processingimporter , and 3 the transport-importer .

Assignment Value

You can assign a value of data type method .

Reformatting the Method

When you manually enter a Release Control and click Apply or OK , Plant Simulation automatically checks if the method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking to reformat the method or not. Plant Simulation automatically re-formats empty methods. You cannot suppress checking of the format of the Method .

**Examples**

```simtalk
-- Release the worker after the last step of production. -- called by: Release control of the importer
param type : integer -- Importertyp (0=repair, 1=setup, 2=processing) var part,allWorker:object;var j:integer
part := @;
allWorker := WorkerPartAssignment
if part /= void
	j := allWorker.getRowNo(part)
	if j /= -1
		allWorker[0,j] := void
	end
end
switch type
case 1
	?.setupImp.releaseExporters
case 2
	?.imp.releaseExporters-- calls Broker controls end
param type: integer
if type = 1
	machine.SetupImp.releaseExporters
else
	machine.Imp.releaseExporters
end
MyStation.FailImp.ReleaseCtrl := &myReleaseCtrl
MyStation.SetupImp.ReceiveCtrl := &myReceiveCtrl
```

**SimTalk**

startProcessing [SimTalk] - importer releaseExporters [SimTalk] See also Release Control [processing importer] Release Control [set-up importer] Release Control [failure importer] Release Control [transport importer]

Receive Control [processing importer] Receive Control [set-up importer] Receive Control [failure importer] Receive Control [transport importer] Reset Simulation [EventController]

###### RequestCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever the importer of the object designated by &lt;Path&gt; sends a request to the Broker .

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation.

Type

Attribute

Syntax

< Path >.FailImp.RequestCtrl:method < Path >.Imp.RequestCtrl:method < Path >.SetupImp.RequestCtrl:method < Path >.TransportImp.RequestCtrl:method

**Parameter**

The Request Control you specify has to define a parameter of data type integer characterizing the type of the importer : 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processingimporter , and 3 the transport-importer .

You have to make sure that Exporters are assigned to the importer ! You can, for example, accomplish this in the method import . You also have to make sure that the MUs are processed using the method startProcessing .

Assignment Value

You can assign a value of data type method .

Reformatting the Method

When you manually enter a Request Control and click Apply or OK , Plant Simulation automatically checks if the method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking to reformat the method or not. Plant Simulation automatically re-formats empty methods. You cannot suppress checking of the format of the Method .

**RequestCtrl [SimTalk]**

**Examples**

```simtalk
// importer type (0 is the failure, 1 the setup, 2 the process, 3 the transport importer)
param type: integer
switch type
case 2
	machine.Imp.setAlternativeServices(process_services[1,@.type])
	machine.Imp.import(@)
case 1
	machine.SetupImp.setAlternativeServices(setup_services[1,@.type])
	machine.SetupImp.import(@)
end
MyStation.FailImp.RequestCtrl := &myFailureRequestCtrl
ParallelStation.Imp.RequestCtrl := &myRequestCtrl
```

**SimTalk**

import [SimTalk] - importer

startProcessing [SimTalk] - importer

See also

Request Control [processing importer]

Request Control [set-up importer]

Request Control [failure importer]

Request Control [transport importer]

Receive Control [processing importer]

Release Control [processing importer]

Release Control [transport importer]

Reset Simulation [EventController]

###### WaitForFreeTarget [SimTalk] - transport importer

Sets if the transport importer of the object designated by &lt;Path&gt; only requests a Worker if the destination object is ready to accept the part that wants to exit ( true ).

Remarks

Plant Simulation enters the part that cannot be transported into the Forward Blocking List of the destination object.

Type

Attribute

Syntax

&lt; Path &gt;.TransportImp.WaitForFreeTarget:boolean

Assignment Value

You can assign a value of data type boolean .

Specify false to request a Worker immediately.

Example

MyStation.TransportImp.WaitForFreeTarget := true

SimTalk

ReservedFor [SimTalk]

ReservedPlace [SimTalk] of the MUs

contentsAndReservedList [SimTalk]

See also

Wait for Free Target [transport importer]

Model a Worker Who Waits for a Free Target

**Attributes of Sensors**

**Attributes of Sensors**

##### \_Attributes of Sensors

The length-oriented objects Conveyor , Track , TwoLaneTrack , Turntable , and Transporter provide the attributes listed in the table of contents to the left for modifying the settings of sensors .

The path to the attributes has to reference a sensor, which you defined for the object designated by &lt;Path&gt;, i.e., it has to have this notation:

```simtalk
< Path >. sensors.id <number> < Path >. sensorNo (sensorID:integer)
```

**Note**

For the loading space of the Transporter , the window Show Attributes and Methods , which you can open by pressing the F8 key, only shows the attributes and methods pertaining to the selected type of loading space.

If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

**SimTalk**

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

\_Methods of Sensors

\_Read-Only Attributes of Sensors

###### Activate [SimTalk] - sensors

Sets when the Transporter triggers the sensor of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.sensors.id<Number>.Activate:string < Path >.sensorNo(<Number>).Activate:string
```

**Assignment Value**

You can assign a value of data type string .

- "Always" , independent of the destination of the Transporter .
- "Only when" the Transporter has the same Destination as the one, which you typed into the sensor.

**Example**

```simtalk
MyTrack.Sensors.ID2.Activate := "Only when destination"
```

**SimTalk**

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Activate [sensor] , check box

Sensors [general description]

###### BookPosition [SimTalk]

BookPosition [SimTalk]

Sets if the Booking Position triggers the sensor of the object designated by &lt;Path&gt; ( true ) or does not trigger it ( false ).

Remarks

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

Syntax

```simtalk
< Path >.sensors.id<Number>.BookPosition:boolean < Path >.sensorNo(<Number>).BookPosition:boolean
```

Assignment Value

You can assign a value of data type boolean .

Examples

```simtalk
MyTrack.Sensors.ID2.BookPosition := true
MyTwolaneTrack.A.Sensors.ID2.BookPosition := false
var ID1,ID2: integer
ID1 := MyTrack.createSensor(0.5,"Relative","SensCtrl",true,false)
ID2 := MyTrack.createSensor(0.7,"Relative",&myMethod,false,true)
MyTrack.sensorID(ID2).BookPosition := true // booking point triggers the sensor
.MUs.Transporter:1.Sensors.ID2.BookPosition := true
```

SimTalk

createSensor [SimTalk] - material flow objects

```simtalk
sensors.id [SimTalk] - material flow objects sensorNo [SimTalk] - material flow objects
```

See also New [sensor] &gt; Booking point Sensors [general description]

Type [loading space]

**Control [SimTalk] - sensors**

###### Control [SimTalk] - sensors

Designates a Method object, which the sensor of the object designated by &lt;Path&gt; activates.

**Remarks**

A value, which you assign, has to be the reference to a Method ( object ) or the name of the Method .

**Note**

You can only create and edit sensor for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

The standard sensor control as a user-defined attribute looks like this.

<!-- image -->

**Parameters**

- As soon as the sensor calls the attribute Control , it passes the Sensor-ID as optional parameter. If the Method expects an integer parameter, the sensor passes the Sensor ID to the Method ; if you do not specify an integer parameter, the Method will be called without a parameter.
- The optional parameter Front of data type boolean shows the user if the Front or the Rear of the part triggered the control.
- The optional parameter BookPos of data type boolean shows the user if the Booking Position of the part triggered the control or not.

**Assignment Value**

You can assign a value of data type method .

**Examples**

```simtalk
param triggeredSensorID: integer, Front: boolean, BookPosition: boolean
if Front /*¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯ the sensor was triggered by the front of the MU _________________________________________________________________________*/
else / *¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯¯ the sensor was triggered by the rear of the MU _________________________________________________________________________*/
end
MyTrack.Sensors.ID2.Control := &mySensorControl
MyTrack.Sensors.ID2.Control := "mySensorControl" .MUs.Transporter:1.LoadBayType := "Track" .MUs.Transporter:1.createSensor(1,"Length","self.OnSensor",true,false)
// Apply the destination selected in the drop-down list // named 'SelectDestination'.
var l: list
SelectDestination.getItems(l)
if DestinationActive.Value // destination is active // set new destination of the part
	@.Destination := l[SelectDestination.Value]
end
-- Unload the transporter (empty container)
param SensorID: integer, Bug: boolean, BuchPos: boolean
var Transp:object := @
Transp.stopped := true
for var j := Transp.numMU downto 1
	var Container:object := Transp.MU(j)
	if Container.empty
		Container.move(Robot_Unload)
		waituntil Container.~ = Conveyor prio 1
	end
next
Transp.stopped := false
Transp.setRoute([Load])
param Container:object
var PartType:string := Container.name -- assigned part type
var color:integer
switch PartType
case "A"
	color := makeRGBValue(192, 0, 0) -- red case "B"
	color := makeRGBValue(0, 255, 0)
case "C"
	color := makeRGBValue(255, 255, 0) -- yellow
end
while NOT Container.full
	var MU := ~.Part.create(Container)
	MU._3d.MaterialDiffuseColor := color
end
-- Load full transporter
param SensorID: integer
var Transp:object := ?.cont
Transp.stopped := NOT Transp.full -- A full transporter is not stopped. while NOT Transp.full
waituntil Store.occupied -- We recommend using initial stock.
var Container := Store.cont
Container.move(Robot_Load)
waituntil Container.~ = Transp
end
Transp.stopped := false
Transp.setRoute([M2, M3, Unit_A.Track])
var currPart,destObj:object
if Vehicle.occupied  -- unload
	currPart := Vehicle.cont
	currPart.move(Vehicle.destination)
	Vehicle.hasOrder := false
	Vehicle.stopped := true
	if TransportOrders.dim>0
		currPart := TransportOrders.pop
		Vehicle.destination := currPart.~
		Vehicle.hasOrder := true
		wait 30
		Vehicle.stopped := false
	end
else -- load
	currPart := Vehicle.destination.cont
	currPart.move(Vehicle)
Vehicle.stopped := true
repeat -- find a free processing station
	destObj := to_str("S", ceil(z_uniform(1,1,8)))
until destObj.empty
Vehicle.destination := destObj
wait 30
Vehicle.stopped := false
end
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Control [sensor]

New [sensor]

Sensors [general description]

###### Destination [SimTalk] - sensors

Destination [SimTalk] - sensors

Designates the object designated by &lt;Path&gt; to which the MU is to move.

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Destination:object < Path >.sensorNo(<Number>).Destination:object
```

Assignment Value

You can assign a value of data type object .

Example

```simtalk
MyTrack.Sensors.ID2.Destination := Station
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Destination [sensor] , text box

Sensors [general description]

###### Front [SimTalk]

Sets if the object designated by &lt;Path&gt; calls the Sensor Control , when the Front of the MU passes the sensor ( true ) or not ( false ).

**Remarks**

**Note**

The Front of the part always moves toward the end of the length-oriented object into the direction with which you inserted it along the direction of motion of the material flow. When you insert a length-oriented object, for example a Conveyor , from left to right, the Front of the part is located on the right-hand side and moves toward the right. When you insert a length-oriented object from right to left, the Front of the part is located on the left-hand side and moves toward the left.

<!-- image -->

This also applies to parts which move backward when you select the check box Backwards of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the lengthoriented object into the direction with which you inserted it along the direction of motion of the material flow.

**Note**

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

**Syntax**

&lt; Path &gt;.Sensors.ID&lt;Number&gt;.Front:boolean

&lt; Path &gt;.sensorNo(&lt;number&gt;).Front:boolean

**Front [SimTalk]**

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
MyTrack.Sensors.ID2.front := true
MyTwoLaneTrack.A.Sensors.ID2.front := false .MUs.Transporter:1.Sensors.ID2.Front := false .MUs.Transporter:1.Sensors.ID2.Rear := true
```

**SimTalk**

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

Control [SimTalk] - sensors

See also

Control [SimTalk] - sensors

Backwards [Conveyor]

Sensors [general description]

New [sensor] &gt; Front

Type [loading space]

###### Lanes [SimTalk]

Sets to which lane of the TwoLaneTrack designated by &lt;Path&gt; the sensor is going to be assigned.

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Lanes:string < Path >.sensorNo(<Number>).Lanes:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Lane A" , "Lane B" or "Both Lanes" .

For a sensor on a one-lane Track , the attribute always has the value "Lane A" .

Example

```simtalk
TwoLaneTrack.A.Sensors.ID1.Lanes := "Lane B"
TwoLaneTrack.B.Sensors.ID1.Lanes := "Both Lanes"
print Track.Sensors.ID1.Lanes -- returns Lane A
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Sensors [general description]

Lanes [sensor]

**Lightbarriermode [SimTalk]**

###### Lightbarriermode [SimTalk]

Sets whether the specified sensor of the object designated by &lt;Path&gt; will be triggered as light barrier ( true ) or not ( false ).

Remarks

If Lightbarriermode is activated the following applies: When you activate Front , the front end of the part in the direction of motion triggers the sensor. When you activate Rear , the rear end of the part in the direction of motion triggers the sensor.

If Lightbarriermode is not activated the following applies: When you activate Front , the front end of the part triggers the sensor. When you activate Rear , the rear end of the part triggers the sensor. Here the direction of motion of the part is irrelevant.

**Note**

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.id<Number>.Lightbarriermode:boolean < Path >.sensorNo(<Number>).Lightbarriermode:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
MyConveyor.Sensors.ID2.Lightbarriermode := true
.MUs.Transporter:1.Sensors.ID3.Lightbarriermode := true
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also Light Barrier Mode Sensors [general description] Type [loading space] Front [SimTalk] Rear [SimTalk]

Location [SimTalk] - sensors

Location [SimTalk] - sensors

Returns the length-oriented object on which the sensor of the object designated by &lt;Path&gt; is located.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Location
-> object < Path >.sensorNo(<number>).Location
-> object < Path >.Sensors.ID<Number>.~
-> object < Path >.sensorNo(<number>).~
-> object
```

**Watchable**

The read-only attribute is watchable .

Return Value

The return value has the data type object .

Example

```simtalk
var o:any := MyPickAndPlaceRobot.getDestination
if getSimTalkTypeName(o) = "sensor"
	print o.Location
end
```

**SimTalk**

sensors.id [SimTalk] - material flow objects

```simtalk
sensorNo [SimTalk] - material flow objects See also Sensors [general description]
```

###### Position [SimTalk] - sensors

Sets the position of the sensor on the object designated by &lt;Path&gt;.

Remarks

The values you can specify depend on the PositionType :

- For length you can specify values between 0.0 and the length of the object.
- For relative you can specify values between 0.0 and 1.0 .

**Note**

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

Syntax

< Path >.Sensors.ID<Number>.Position:length < Path >.sensorNo(<Number>).Position:length

Assignment Value

You can assign a value of data type length .

**Examples**

```simtalk
MyTrack.Sensors.ID2.PositionType := "Length"
MyTrack.Sensors.ID2.Position := 5.5
MyTwoLaneTrack.A.Sensors.ID2.Position := 8.5
.MUs.Transporter:1.Sensors.ID3.Position := 0.8
```

SimTalk

**PositionType [SimTalk]**

sensors.id [SimTalk] - material flow objects sensorNo [SimTalk] - material flow objects See also Type [loading space] Position [sensor] Sensors [general description]

###### PositionType [SimTalk]

Sets the position type of the sensor of the object designated by &lt;Path&gt;.

Remarks

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.PositionType:string < Path >.sensorNo(<Number>).PositionType:string
```

Assignment Value

You can assign a value of data type string .

You can specify "relative" or "length" .

Examples

```simtalk
MyTrack.sensorNo(2).PositionType := "Length"
.MUs.Transporter:1.Sensors.ID3.PositionType := "Relative"
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Position [sensor]

Sensors [general description]

Type [loading space]

###### Rear [SimTalk]

Sets if the object designated by &lt;Path&gt; calls the sensor control , when the Rear of the MU passes the sensor ( true ) or not ( false ).

Remarks

You can only create and edit sensors for the Transporter via SimTalk for the Loading Space Types &gt; Track or Line .

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Rear:boolean < Path >.sensorNo(<number>).Rear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Examples

```simtalk
MyTrack.Sensors.ID2.Rear := true
MyTwoLaneTrack.A.Sensors.ID2.Rear := true
.MUs.Transporter:1.Sensors.ID2.Front := false .MUs.Transporter:1.Sensors.ID2.Rear := true
```

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

Control [SimTalk] - sensors

See also

New [sensor] &gt; Rear

Sensors [general description]

**Type [loading space]**

##### Attributes of Curved Objects in 2D

\_Attributes of the Curved Objects in 2D

The curved objects AngularConverter , Conveyor , Track , TwoLaneTrack , Turnplate , Turntable , FootPath , and Pipe provide the attributes listed in the table of contents to the left for modifying the settings for curved and straight segments, when you activated Curve mode in 2D.

You can also select these settings in the dialogs of the objects on the Tab Curve .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.Pause := true
print MyStation.Pause
posit := MyStation.Cont.XPos
```

**See also**

**\_Methods of Curved Objects in 2D**

Tab Curve [general description]

###### AnimateOnEveryXthPixel [SimTalk]

Sets the distance in pixels at which Plant Simulation animates the part/Transporter on the length-oriented curved object designated by &lt;Path&gt;. For the Turntable this setting in addition controls the rotation steps with which the table rotates.

Remarks

A 3D Only model does not provide this attribute.

Type

Attribute

Syntax

&lt; Path &gt;.AnimateOnEveryXthPixel:integer

Assignment Value

You can assign a value of data type integer .

Specify 1 to animate the MU on every pixel.

Specify 10 to animate it on every tenth pixel.

The higher the number you specify, the better the performance will be. When you specify 1 , performance may suffer if your model contains a large number of MUs .

Example

```simtalk
MyConveyor.AnimateOnEveryXthPixel := 6
```

See also

Animate Every x-th Pixel

Tab Curve [general description]

###### BaseHeight [SimTalk] - material flow objects

Sets the Base Height . The Base Height is the distance between the insertion height (z-coordinate) of the length-oriented object designated by &lt;Path&gt; and the height of a segment whose ΔZ equals 0.

Remarks

A 3D Only model does not provide this attribute.

The base height can be inherited, meaning that you can define it once in the class instead of having to define it individually for each instance. It is mainly used in 3D . Here the z-coordinate defines the floor of the plant and the base height defines the distance of the legs from the floor. By changing the setting ΔZ in the segments table, you can add an additional offset. The setting ΔZ also affects the simulation time in Plant Simulation 2D.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.BaseHeight:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyConveyor.BaseHeight := 3
print MyConveyor.BaseHeight
```

SimTalk \_3D.BaseHeight [SimTalk] - 3D See also Base Height [curve] Base Height [tab Appearance] Segments [curve] - 2D, described

Insert Curved and Straight Segments &gt; anchor point height

###### Color [SimTalk] - material flow objects

Sets the color of the length-oriented curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this attribute.

<!-- image -->

Set the RGB values of the color with the method makeRGBValue .

When you assign an invalid value to the attribute Color , Plant Simulation retains the current color.

Type

Attribute

Syntax

```simtalk
< Path >.Color:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyConveyor.Color := makeRGBValue(100,100,100)
MyConveyor.Color := 6579300 // same color as above
```

SimTalk

makeRGBValue [SimTalk]

**See also Color [curve]**

###### Tab Curve [general description]

###### CurveActive [SimTalk]

Activates ( true ) curve mode for the curved object designated by &lt;Path&gt; or deactivates it ( false ).

Remarks

A 3D Only model does not provide this attribute.

When activated, you can insert the length-oriented objects that contain curves into your simulation model.

The attribute AnimateOnEveryXthPixel sets how often the MUs are going to be animated on the lengthoriented objects.

**Note**

When you activate RotateMovables , Plant Simulation also activates CurveActive .

Type

Attribute

Syntax

&lt; Path &gt;.CurveActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrack.CurveActive := true
```

SimTalk

AnimateOnEveryXthPixel [SimTalk]

RotateMovables [SimTalk]

See also

Active [check box] - curve

Tab Curve [general description]

###### CurveWidth [SimTalk]

Sets the width of the curved object designated by &lt;Path&gt;.

**Remarks**

**Note**

A 3D Only model does not provide this attribute.

**Note**

You can only specify the CurveWidth in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

&lt; Path &gt;.CurveWidth:integer

<!-- image -->

**CurveWidth [SimTalk]**

Assignment Value

You can assign a value of data type integer .

You can specify a value between 1 and 500 pixels.

Example

```simtalk
MyConveyor.TransferLengthToObject := false
MyConveyor.CurveWidth := 44 // pixels
```

See also

TransferLengthToObject [SimTalk]

Curve Width

Width [SimTalk] - AngularConverter

Tab Curve [general description]

###### MidLine [SimTalk]

Sets the style for the line in the middle of the curved object designated by &lt;Path&gt;. The icons of the MUs move on this line along your Tracks , TwoLaneTracks , or Conveyors .

**Remarks**

A 3D Only model does not provide this attribute.

<!-- image -->

Type

Attribute

Syntax

**&lt; Path &gt;.MidLine:integer**

**Assignment Value**

You can assign a value of data type integer .

|   Specify | To add                |
|-----------|-----------------------|
|         1 | No line.              |
|         2 | A solid line .        |
|         3 | A dashed line .       |
|         4 | A dotted line .       |
|         5 | A dash dot line .     |
|         6 | A dash dot dot line . |

**MidLine [SimTalk]**

**Example**

```simtalk
MyTrack.MidLine := 3
```

See also

Midline Style

Tab Curve [general description]

###### ObjectAngle [SimTalk] - material flow objects

Sets the angle by which Plant Simulation rotates the curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this attribute.

Plant Simulation does not re-compute the anchor points, but retains the original curve and saves the rotation to the attribute ObjectAngle .

When you assign a value in the Segments Table , Plant Simulation changes the original anchor points.

Type

Attribute

Syntax

&lt; Path &gt;.ObjectAngle:real

Assignment Value

You can assign a value of data type real .

Example

MyConveyor.ObjectAngle := 45 print MyConveyor.ObjectAngle

SimTalk

getCurveSegments [SimTalk]

setCurveSegments [SimTalk]

ObjectMirrored [SimTalk] - material flow objects

\_3D.Rotation [SimTalk]

See also

Segments [curve] - 2D, described ObjectMirrored [SimTalk] - material flow objects Sets if the curved object designated by &lt;Path&gt; will be mirrored on the y-axis ( true ) or not ( false ).

Remarks

A 3D Only model does not provide this attribute.

When you assign a value in the Segments Table , Plant Simulation changes the original anchor points.

Plant Simulation does not re-compute the anchor points, but retains the original curve and saves the inversion to the attribute ObjectMirrored .

Type

Attribute

Syntax

&lt; Path &gt;.ObjectMirrored:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.ObjectMirrored := true print MyConveyor.ObjectMirrored

SimTalk

ObjectAngle [SimTalk] - material flow objects

\_3D.Rotation [SimTalk]

See also

Mirror Vertically

Mirror Horizontally

Segments [curve] - 2D, described

###### PenColor [SimTalk]

Sets the color of the outline around the border of the curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this attribute.

<!-- image -->

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

&lt; Path &gt;.PenColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyTrack.PenColor := makeRGBValue(15,155,100)
```

SimTalk

makeRGBValue [SimTalk]

See also

Pen Color

**Tab Curve [general description]**

###### PenWidth [SimTalk]

Sets the line width of the outline around the border of the length-oriented curved object designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this attribute.

<!-- image -->

Type

Attribute

Syntax

**&lt; Path &gt;.PenWidth:integer**

Assignment Value

You can assign a value of data type integer .

You can specify a value between -1 and 100 .

- Specify -1 to make the outline invisible.
- Specify 0 to use a pen width of 1 pixel. The width of the outline is not zoomed when you zoom the contents of the Frame .
- Specify 1 to use a pen width of 1 pixel as well. The width of the outline is also zoomed when you zoom the contents of the Frame .

**PenWidth [SimTalk]**

**Example**

```simtalk
MyTrack.PenWidth := 4
```

**See also**

**Pen Width**

Tab Curve [general description]

###### RotateMovables [SimTalk]

Rotates the MU in the direction of motion when it rounds a curve ( true ) on the curved object designated by &lt;Path&gt; or does not rotate it ( false ).

**Remarks**

**Note**

A 3D Only model does not provide this attribute.

**Note**

The attribute RotateMovables is only important for models created in previous versions of Plant Simulation which used this no-longer supported setting that you want to change.

RotateMovables still works but we advise against using it in new models.

Specify false to make the parts keep their previous direction/rotation.

<!-- image -->

**Note**

A rotation triggered by the setting RotateMovables on a length-oriented object only has an effect as long as the part is located on this object. When leaving the object the part again assumes the rotation it had before. When entering a new object, the part considers the rotation of this new object if Rotate MUs is active.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.RotateMovables:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if MyConveyor.CurveActive
	MyConveyor.RotateMovables := true
else
	MyConveyor.RotateMUs := true
end
```

SimTalk

Rotate Movables

RotateMUs [SimTalk] - material flow objects

RotateMUs [SimTalk] - Frame

**See also**

**Tab Curve [general description]**

###### TransferLengthToObject [SimTalk]

Uses the length of the curved object designated by &lt;Path&gt;, which you inserted in the layout within the Frame as the length of the object ( true ) or does not use it ( false ).

Remarks

TransferLengthToObject applies to a 2D Only and to a 3D Only model. The default setting is true for both. We provide it in the dialog Show Attributes and Methods for a 3D Only model if it was set to false in an old model to allow you to change it to true.

If the dialog is open, Plant Simulation enters this value into the text box Length .

If you select Transfer Length , Plant Simulation adapts the length of the graphic, when you change the Length if the object only consists of a single straight segment.

Type

Attribute

Syntax

&lt; Path &gt;.TransferLengthToObject:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.TransferLengthToObject := true

SimTalk

\_3D.removeLengthOrientation [SimTalk]

\_3D.addLengthOrientation [SimTalk]

See also

Transfer Length

Tab Curve [general description]

###### Transparent [SimTalk] - material flow objects

Makes the inside of the curved object designated by &lt;Path&gt; transparent, so that the background color of the Frame shines through ( true ) or does not shine through ( false ).

Remarks

The border of the objects remains as it is.

To completely hide the curved object, specify a value less than 0 for the PenWidth .

<!-- image -->

Type

Attribute

Syntax

**&lt; Path &gt;.Transparent:boolean**

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyTrack.transparent := true
MyTrack.penwidth := -2
MyConveyor.transparent := true
MyConveyor.penwidth := -1
MyFootPath.transparent := true
```

SimTalk

PenWidth [SimTalk]

See also

**Transparent [curve]**

Tab Curve [general description]

