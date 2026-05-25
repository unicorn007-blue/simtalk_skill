#### Read-Only Attributes of the Material Flow Objects

Read-Only Attributes of the Material Flow Objects

All material flow objects share the read-only attributes described below. You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to a unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- formula-not-decoded -->

See also

- \_Methods for the State
- \_Read-Only Attributes for the State
- \_Methods for Accessing the Contents

Methods for Setting-Up

- \_Methods for Defining Failures

##### Miscellaneous Read-Only Attributes of the Material Flow Objects

**\_Miscellaneous Read-Only Attributes**

All material flow objects share the read-only attributes described below. You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the Tab Statistics .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print Source.Empty
```

**See also**

Full [SimTalk] - material flow objects

###### AssignedLockoutzones [SimTalk]

AssignedLockoutzones [SimTalk]

Returns the LockoutZones that are assigned to the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.AssignedLockoutzones → array

Return Value

The return value has the data type array .

Examples

// the station SP3 is assigned to one lockout zone

```simtalk
print SP3.AssignedLockoutzones // returns [*.Models.Test5.LockoutZone1]
// the station SP5 is assigned to two lockout zones
print SP5.AssignedLockoutzones // returns [*.Models.Test5.LockoutZone1, *.Models.Test5.LockoutZone2]
```

See also

LockoutZone

Associated Lockout Zones

Check the Contents List of the Stations

###### Cont [SimTalk] - material flow objects

Returns the MU that is located on the object designated by &lt;Path&gt;.

Remarks

If the Worker , who is carrying a part, puts that part down, the read-only attribute Worker.Cont returns the part that he put down.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Cont → object
```

**Watchable**

The read-only attribute is watchable .

Return Value

The return value has the data type object .

- Returns the MU that is located on the object if the object has a capacity of 1.
- Returns the MU that can exit next if the object has a capacity greater than 1.
- Returns VOID if no MU is located on the object.
- Returns the Main Part if the object is an AssemblyStation or a DismantleStation .

**Example**

```simtalk
if MyStation.Cont /= VOID
	print MyStation.Cont.name
end
ParallelStation.Cont.CurrIconNo := 1
```

**SimTalk**

mu [SimTalk] - material flow objects

**See also Contents [material flow objects]**

Exit Locked [material flow objects]

###### EntranceFree [SimTalk]

Returns if the entrance of the object designated by &lt;Path&gt; is free (true) or if it is blocked (false).

Remarks

The entrance might be blocked because a MU is located there or because the capacity of the object is exhausted. The object may only receive a MU if the entrance is open and free.

The entrance of the PickAndPlace robot is free/open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

Type

Read-only attribute

Syntax

```simtalk
< Path >.EntranceFree → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

true if the object is not failed, not paused, not unplanned, and not stopped.

false for the Workplace if its capacity is exhausted by the assigned Workers , who are still en route.

false for the ParallelStation with activated setting Start Processing When Full if not all processed parts have exited the object yet.

Example

```simtalk
if MyStation.EntranceFree AND MyStation.EntranceOpen AND Not MyStation.EntranceLocked
	@.move(Station)
end
```

**EntranceFree [SimTalk]**

See also Entrance Locked [material flow objects] EntranceLocked [SimTalk] - material flow objects RecoveryTime [SimTalk] - material flow objects Loading Time [PickAndPlace] LoadingTime [SimTalk] - PickAndPlace Unloading Time [PickAndPlace] UnloadingTime [SimTalk] - PickAndPlace Loading Time [Workplace] LoadingTime [SimTalk] - Workplace Unloading Time [Workplace] UnloadingTime [SimTalk] - Workplace Start Processing When Full [check box]

EntranceOpen [SimTalk] - material flow objects

Returns if the entrance of the material flow object designated by &lt;Path&gt; is open (true) or not (false).

Remarks

If the entrance is open, a MU can move onto the material flow object.

The entrance of the PickAndPlace robot is open while its Loading Time is running. The entrance is closed once the part is actually moved on. The PickAndPlace robot opens the entrance again after the Unloading Time has passed.

The entrance of a material flow object is not open, if its Entrance is Locked or if the material flow object is waiting for its Recovery Time to be completed.

Type

Read-only attribute

Syntax

```simtalk
< Path >.EntranceOpen → boolean
```

Return Value

The return value has the data type boolean .

Example

print MyStation.EntranceOpen

SimTalk

EntranceLocked [SimTalk] - material flow objects

EntranceFree [SimTalk]

RecoveryTime [SimTalk] - material flow objects

See also

Entrance Locked [material flow objects]

Recovery Time [general description]

**Start Processing When Full [check box]**

###### ExitFree [SimTalk]

Returns if the exit of the object designated by &lt;Path&gt; is not Blocked by a MU / Transporter (true), or blocked (false) or if the maximum number of MUs is located on the object, i.e., its capacity is exhausted (true) or not (false).

Remarks

Only the Track , the TwoLaneTrack and the Conveyor provide this read-only attribute.

Type

Read-only attribute

Syntax

```simtalk
< Path >.ExitFree → boolean
```

Return Value

The return value has the data type boolean .

true if the object is not failed, not paused, not unplanned, and not stopped

Example

```simtalk
print MyConveyor.ExitFree
print MyTrack.ExitFree
```

See also

Exit Locked [material flow objects]

Blocked [state, material flow objects]

###### IsInterrupted [SimTalk]

IsInterrupted [SimTalk]

Returns if the object designated by &lt;Path&gt; is interrupted (true), meaning that it is paused, failed, or stopped or if is not interrupted (false).

Type

Read-only attribute

Remarks

IsInterrupted is only available for objects that support interruptions, meaning pauses or failures .

Syntax

&lt; Path &gt;.IsInterrupted → boolean

Return Value

The return value has the data type boolean .

Example

print Station.IsInterrupted IsSetupFor [SimTalk]

Returns the name of the MU for which the object designated by &lt;Path&gt; is currently set up or is setting-up for.

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsSetupFor → string
```

Return Value

The return value has the data type string .

Is an empty string "" if the object is not set up for a MU .

Example

```simtalk
if machine.IsSetupFor = @.name AND NOT machine.setUp
	@.move(machine)
else
	machine.setUpFor(@)
end
```

SimTalk

ResSetup [SimTalk] - material flow objects

setupFor [SimTalk]

See also

Set-up For NumMU [SimTalk] - material flow objects Returns the number of MUs booked on the object designated by &lt;Path&gt;.

Remarks

**Note**

On length-oriented objects MUs may only be located on a part of the object. In this case they will only be counted if their booking point is actually located on the object.

**Note**

When the object is not booked on another object either, Plant Simulation counts the MU as being part of the length-oriented object on which a part of the MU is located. This might, for example, occur, if a MU is moved from a Station onto a Conveyor .

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumMU → integer

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

print ParallelStation.NumMU

SimTalk

NumMUParts [SimTalk] - material flow objects

See also

Contents [material flow objects]

Tab Statistics [material flow objects] Tab Statistics [Container]

Statistics Values [Transporter]

NumMUParts [SimTalk] - material flow objects

Returns the number of MUs located on the object designated by &lt;Path&gt; as a whole or in part.

Remarks

For length-oriented objects a MU may have exited the object with its front part while the rear is still located on the object. In this case NumMUParts counts both occupied lengths separately, although they are part of a single MU .

NumMU returns the number of MUs whose booking point is located on the object.

On point-oriented objects NumMUParts and NumMU always return the same value.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumMUParts → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
if conveyor.NumMUParts < 3
@.move(conveyor)
end
```

SimTalk

NumMU [SimTalk] - material flow objects

See also

Contents [material flow objects]

###### NumPartsSinceSetup [SimTalk]

Returns the number of MUs , which the object designated by &lt;Path&gt; has processed since the last set-up process.

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumPartsSinceSetup → integer

Return Value

The return value has the data type integer .

Example

print MyStation.NumPartsSinceSetup

See also

Set-up After n Parts

NumPred [SimTalk] - general description

NumPred [SimTalk] - general description

Returns the number of predecessors of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumPred → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
for var i := 1 to MyStation.NumPred
	print MyStation.pred(i) // prints all predecessors
next
```

SimTalk

NumPred [SimTalk] - lane A or B

See also

Show Predecessors [View ribbon] - 2D

NumSucc [SimTalk] - general description

Returns the number of successors of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumSucc → integer
```

Return Value

The return value has the data type integer .

Example

if ParallelStation.NumSucc > 1 ....  // more than one successor end

SimTalk

NumSucc [SimTalk] - lane A or B

See also

Show Successors [View ribbon] - 2D

RemainingSetUpTime [SimTalk]

Returns the remaining setup time of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.RemainingSetUpTime → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Note

The value -1 tells that the object has finished setting up.

Example

print MyStation.RemainingSetUpTime

SimTalk

SetupTime [SimTalk] - material flow objects

See also

Set-up Time [general description]

Read-Only Attributes for the State

\_Read-Only Attributes for the State

The material flow objects provide the read-only attributes listed in the table of contents to the left for returning the state in which they are.

All material flow objects share the read-only attributes described below. You can query the values of the read-only attribute , but you cannot set them as Plant Simulation calculates the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print Source.Empty
```

BwBlockListEntry1 [SimTalk]

Returns the first entry of the Backward Blocking List of the object designated by &lt;Path&gt; if the Backward Blocking List contains entries.

Remarks

BwBlockListEntry1 applies to the Conveyor , the Track , and the lanes of the TwoLaneTrack .

**Note**

Accessing the Backward Blocking List with the read-only-attribute BwBlockListEntry1 is much faster than with the method bwBlockList if you only need the first entry of the Backward Blocking List .

Type

Read-only attribute

Syntax

&lt; Path &gt;.BwBlockListEntry1 → object

Return Value

The return value has the data type object .

VOID if the Backward Blocking List is empty.

Example

print MyTrack.BwBlockListEntry1

SimTalk

bwBlockList [SimTalk] - material flow objects

See also

Backward Blocking List

###### Empty [SimTalk] - material flow objects

Returns if the material flow object designated by &lt;Path&gt; is empty, meaning that no MU is located on it in part or as a whole (true) or not (false).

Remarks

For objects with more than one place, such as the ParallelStation or the Store , you can use the read-only attribute Empty to find out if MUs are located on a specific place (false) or the place is empty (true).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Empty → boolean < Path >[X:integer, Y:integer].Empty → boolean
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the place.
- The parameter Y of data type integer designates the y-coordinate.

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// no MUs are located on the object
if MyStation.Empty .MUs.Part.create(MyStation)
end
if buffer[1].Empty .MUs.Part.create(buffer[1])
end // only one station is Empty if ParallelStation[2,3].Empty .MUs.Part.create(ParallelStation[2,3]) end
```

SimTalk Full [SimTalk] - material flow objects Occupied [SimTalk] - material flow objects See also

Empty [state, material flow objects]

Full [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; is full (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Full → boolean < Path >[X:integer, Y:integer].Full → boolean
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the processing place.
- The parameter Y of data type integer designates the y-coordinate.

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

true for point-oriented objects if all processing places are occupied. If more than one processing place exists, each one of them might be asked if it is ready to receive a MU . As a place may process a single MU , Full is identical with Occupied .

true for length-oriented objects if the number of MUs on the object corresponds to its capacity or the length occupied takes the value of its length.

**Example**

```simtalk
// queries the entire object if NOT storeNorth.Full
@.move(storeNorth)
elseif NOT storeEast.Full
	@.move(storeEast)
else // if all are all Full, use spare
	@.move(spareStore)
end // queries each single station if ParallelStation[3,4].Full ParallelStation[3,4].Cont.delete
end
```

SimTalk Empty [state, material flow objects]

Occupied [SimTalk] - material flow objects

###### FwBlockListEntry1 [SimTalk]

Returns the first entry of the Forward Blocking List of the object designated by &lt;Path&gt; if the Forward Blocking List contains entries.

Remarks

Accessing the Forward Blocking List with the read-only-attribute FwBlockListEntry1 is much faster than with the method fwBlockList if you only need the first entry of the Forward Blocking List .

**Note**

If the predecessor is a FlowControl or a Sorter , the Forward Blocking List contains this FlowControl or Sorter instead of the MU .

Type

Read-only attribute

Syntax

&lt; Path &gt;.FwBlockListEntry1 → object

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

VOID if the Forward Blocking List is empty.

Example

print MyStation.FwBlockListEntry1

SimTalk

fwBlockList [SimTalk] - material flow objects

See also

Forward Blocking List

**FwBlockListEntry1 [SimTalk]**

**Video on YouTube**

[https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&amp;t=269](https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&t=269)

###### GetDisruptionBeginTime [SimTalk]

Returns the point in time at which the next start of a failure of the object designated by &lt;Path&gt; is scheduled to take place.

Remarks

GetDisruptionBeginTime only considers automatically created events. It does not consider a failure event which you manually inserted with the methods startFailure or startFailureIn .

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetDisruptionBeginTime → time

Return Value

The return value has the data type time .

Is -1 if no event exists.

Example

print mystation.GetDisruptionBeginTime

SimTalk

startFailure [SimTalk] - material flow objects

startFailureIn [SimTalk] - material flow objects

See also

GetDisruptionEndTime [SimTalk]

Event List &gt; DisruptionBegin

###### GetDisruptionEndTime [SimTalk]

Returns the point in time at which the next end of a failure of the object designated by&lt;Path&gt; is scheduled to take place.

Remarks

GetDisruptionEndTime only considers automatically created events. It does not consider a failure event which you manually inserted with the methods startFailure or startFailureIn .

**Note**

If several overlapping failures are active for the object, GetDisruptionEndTime returns the end of the first/next failure instead of the time when the object will no longer be failed. In this case this is not the time at which the object can resume processing the part again.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetDisruptionEndTime → time

Return Value

The return value has the data type time .

Is -1 if no event exists.

Example

print mystation.GetDisruptionEndTime

SimTalk

GetDisruptionBeginTime [SimTalk]

startFailure [SimTalk] - material flow objects

startFailureIn [SimTalk] - material flow objects

**See also**

**Event List &gt; DisruptionEnd**

Occupied [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; contains at least one MU in whole or in part (true) or not (false).

Remarks

For objects with more than one place, such as the ParallelStation or the Store , you can use the read-only attribute Occupied to find out if a specific place contains MUs (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Occupied → boolean < Path >[X:integer, Y:integer].Occupied → boolean
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the place.
- The parameter Y of data type integer designates the y-coordinate.

Watchable

The attribute is watchable .

Return Value

The return value has the data type boolean .

Examples

```simtalk
-- called by: init and itself via ref().methCall(0); -- wait until all parts are available and the assembly station is free Waituntil A.occupied and B.occupied and C.occupied and D.occupied and Assembly.empty prio 3 -- create a new main part on the assembly station ~.MUs.plate.create(Assembly) -- assemble all parts to the main part A.cont.move(Assembly.cont)
B.cont.move(Assembly.cont)
C.cont.move(Assembly.cont)
D.cont.move(Assembly.cont) -- starts method execution again
self.executeIn(0)
if not MyStation.Occupied then @.move(Station)
end
// search for an unOccupied station on the ParallelStation and place the MU
for var x := 1 to ParallelStation.xDim
	for var y := 1 to ParallelStation.yDim
		if not ParallelStation[x,y].Occupied
			@.move(ParallelStation[x,y])
			exitloop 2 // terminate both loops
		end
	next
next
```

**See also**

**Working [state, material flow objects]**

###### Operational [SimTalk]

Operational [SimTalk]

Returns if the object designated by &lt;Path&gt; is in the state operational (true) or not operational (false).

Remarks

Operational is true, when Paused , Failed , and Stopped are false.

Type

Read-only attribute

Syntax

&lt; Path &gt;.Operational → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyStation.Operational

See also

Working [state, material flow objects]

###### Ready [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; is occupied and a MU is ready to exit (true) or not (false).

Remarks

For the ParallelStation Ready returns if at least one processing place is occupied and at least one MU is ready to exit (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Ready → boolean
```

Return Value

The return value has the data type boolean .

**Examples**

```simtalk
print MyStation.Ready
// The read-only attribute Ready is not watchable, but if you want to wait for // Ready == true for the object Station you can use this statement:
waituntil Station.Cont /= void and Station.Cont.Finished
```

See also

Working [state, material flow objects]

ResBlocked [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; is blocked (true) or not (false).

Remarks

An object is blocked if it is fully occupied, it is neither failed nor paused, and all of its processing places are not processing.

Type

Read-only attribute

Syntax

```simtalk
< Path >.ResBlocked → boolean
```

Watchable

The read-only attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record the read-only attribute in watch mode.

Return Value

The return value has the data type boolean .

Examples

```simtalk
waituntil ParallelStation.ResBlocked prio 1 deleteMovables // empties all occupied stations
print MyStation.ResBlocked
```

See also

Blocked [state, material flow objects]

SimTalk

ResCurrentState [SimTalk] - material flow objects ResCurrentState [SimTalk] - material flow objects Returns the current state of the object designated by &lt;Path&gt;.

Remarks

During a simulation run a material flow resource can be in one of these states: Working , Setting-Up , Waiting , Blocked , Powering up/down , Failed , Stopped , Paused , or Unplanned

**Note**

If two states occur at the same time, for example Paused and Failed , the read-only attribute returns the state that also has precedence for statistics collection. Paused for example for Paused and Failed .

Type

Read-only attribute

Syntax

&lt; Path &gt;.ResCurrentState → string

Watchable

The read-only attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record the read-only attribute in watch mode.

Return Value

The return value has the data type string .

Example

```simtalk
print MyStation.ResCurrentState
```

See also

Resource Statistics [material flow objects]

ResSetup [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; is setting up and not failed, not paused, or not stopped (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.ResSetup → boolean
```

Watchable

The read-only attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record the read-only attribute in watch mode.

Return Value

The return value has the data type boolean .

Example

```simtalk
if machA.ResSetup
	@.move(machineB)
end
```

SimTalk

ResCurrentState [SimTalk] - material flow objects

IsSetupFor [SimTalk]

setupFor [SimTalk]

See also

Setting-Up [state, material flow objects]

Methods for Setting-Up ResWaiting [SimTalk] - material flow objects Returns if the object designated by &lt;Path&gt; is Waiting (true) or not (false).

Remarks

A resource is if it is not paused, it is not failed, has free capacity left, and occupied processing places are not processing parts.

Type

Read-only attribute

Syntax

&lt; Path &gt;.ResWaiting → boolean

Watchable

The attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record the read-only attribute in watch mode.

Return Value

The return value has the data type boolean .

Examples

print MyStation.ResWaiting

```simtalk
waituntil ParallelStation.ResWaiting prio 1 deleteMovables // empties all occupied stations
```

SimTalk

ResCurrentState [SimTalk] - material flow objects

See also

Waiting [state, material flow objects]

Waiting Time in the Statistics Report

###### ResWorking [SimTalk] - material flow objects

Returns if the object designated by &lt;Path&gt; is working (true) or not (false).

**Remarks**

The definition of working depends on the object that is processing the part:

| Object                                                                               | Description                                                                                                                                                                                                                            |
|--------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Station , ParallelStation , AssemblyStation , DismantleStation , PlaceBuffer , Drain | Is working if it processes at least one MU                                                                                                                                                                                             |
| Track , TwoLaneTrack                                                                 | Is working if at least one MU is moving on it                                                                                                                                                                                          |
| Conveyor                                                                             | Is working if its current speed is not 0. It can also be working if it is moving and if it does not transport any part                                                                                                                 |
| Turnplate , Turntable                                                                | Is working if it has a speed or if it is rotating, no matter if it moves a part or not                                                                                                                                                 |
| Converter , AngularConverter                                                         | Is working if it has a speed or if the moving time is running                                                                                                                                                                          |
| PickAndPlace Robot                                                                   | Is working if it is rotating, no matter if it moves a part or not or if it picks a part up or deposits a part                                                                                                                          |
| Source , Store , Buffer , Transporter , Container , Tank                             | -                                                                                                                                                                                                                                      |
| Sorter                                                                               | - The processing time is identical with the sorting time, i.e., it is always zero. This means that sorting takes place instantaneously. Even though the processing time is zero, each sorting action counts as a processing procedure. |
| FluidDrain , FluidSource                                                             | Is working if material flows                                                                                                                                                                                                           |
| Mixer                                                                                | Is working if materials are mixed                                                                                                                                                                                                      |
| Portioner                                                                            | Is working if the material is transformed into a MU                                                                                                                                                                                    |
| DePortioner                                                                          | Is working if the MU is transformed into a material                                                                                                                                                                                    |

Type

Read-only attribute

**Syntax**

```simtalk
< Path >.ResWorking → boolean
```

Watchable

The attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record the read-only attribute in watch mode.

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyStation.ResWorking
```

See also

Failure Relates To &gt; The processing time

ResCurrentState [SimTalk] - material flow objects

Working [state, material flow objects]

Working Time in the Statistics Report TimeUntilEntranceOpen [SimTalk] - material flow objects Returns the time until the entrance of the object designated by &lt;Path&gt; opens again after the recovery time has elapsed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.TimeUntilEntranceOpen → real

Return Value

The return value has the data type real .

Example

print ParallelStation.TimeUntilEntranceOpen

See also

Recovery Time [general description]

Read-Only Attributes of Sensors

\_Read-Only Attributes of Sensors

Plant Simulation provides the read-only attributes listed in the table of contents to the left for sensors of the material flow objects.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

**Note**

For the loading space of the Transporter , the window Show Attributes and Methods , which you can open by pressing the F8 key, only shows the attributes and methods pertaining to the selected Type of Loading Space . If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyTrack.NumSensors

**See also**

\_Attributes of Sensors

\_Methods of Sensors

###### IsTriggered [SimTalk]

Returns if the part has reached the sensor of the length-oriented object designated by &lt;Path&gt; (true) or not (false). This applies when the Front of the part has reached the sensor until the point in time at which the Rear of the part has reached the sensor.

**Remarks**

**Note**

Add the number of the sensor to the expression id , for example ID1 , ID2 , etc.

**Note**

If you want to observe IsTriggered , the sensor has to be triggered by the Front and by the Rear of the part.

IsTriggered only returns the correct value if the sensor is triggered by the Front as well as by the Rear of the part.

If you did not specify Always and if the Destination of the part and of the sensor do not match, the observer for IsTriggered is not triggered.

**Note**

IsTriggered never returns true if you only specify a Rear -triggered sensor.

Type

Read-only attribute

Syntax

&lt; Path &gt;.Sensors.id&lt;Number&gt;.IsTriggered → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

**Example**

waituntil MyConveyor.Sensors.id1.IsTriggered

SimTalk

sensors.id [SimTalk] - material flow objects

See also

Sensors [general description]

###### NumSensors [SimTalk] - material flow objects

Returns the number of sensors defined for the length-oriented object designated by &lt;Path&gt;.

Remarks

Creating and manipulating sensors via SimTalk for the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumSensors → integer

Return Value

The return value has the data type integer .

Examples

print MyTrack.NumSensors

print .MUs.Transporter:1.NumSensors

SimTalk

sensorNo [SimTalk] - material flow objects

See also

Sensors [general description]

Type [loading space]

###### Origin [SimTalk] - sensor

Origin [SimTalk] - sensor

Returns the origin of the sensor of the length-oriented object designated by &lt;Path&gt;.

Remarks

Creating and manipulating sensors via SimTalk for the Transporter only works if you select the Loading Space Types &gt; Track or Line !

Type

Read-only attribute

Syntax

```simtalk
< Path >.Sensors.id<number>.Origin → integer < Path >.sensorNo(<number>).Origin → integer
```

Return Value

The return value has the data type integer .

VOID if the sensor does not have an origin.

Examples

```simtalk
for var n := MyConveyor.NumSensors downto 1
	if MyConveyor.sensorNo(n).Origin = VOID
		MyConveyor.deleteSensor(MyConveyor.sensorNo(n).ID)
	end
next
```

print MyConveyor.Sensors.id1.origin

SimTalk

sensors.id [SimTalk] - material flow objects

sensorNo [SimTalk] - material flow objects

See also

Sensors [general description]

###### PositionAbs [SimTalk]

Returns the distance of the sensor from the starting point of the length-oriented object designated by &lt;Path&gt; no matter how the sensor was defined.

Type

Read-only attribute

Syntax

< Path >.Sensors.id<Number>.PositionAbs → length

Return Value

The return value has the data type length .

Example

```simtalk
print conveyor.sensors.ID1.PositionAbs
// might, for example,
return 13.08m
```

See also

Sensors [general description]

Read-Only Attributes for Statistics

\_Read-Only Attributes for Querying Statistics

The material flow objects provide the read-only attributes listed in the table of contents to the left for accessing the statistics values they collected.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyStation.StatBlockingCount StatAverageDwellTime [SimTalk] - material flow objects Returns the average time of all parts which stayed on the object designated by &lt;Path&gt;.

Remarks

Plant Simulation only counts times during which the object was not paused and not unplanned.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatAverageDwellTime → time

Return Value

The return value has the data type time .

Example

print MyBuffer.StatAverageDwellTime

See also

Tab Statistics [material flow objects]

###### StatAverageWorkingTime [SimTalk]

StatAverageWorkingTime [SimTalk]

Returns the mean time of all parts that were processed by the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatAverageWorkingTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatAverageWorkingTime

###### StatBlockingCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was blocked .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatBlockingCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatBlockingCount

See also

Blocked [state, material flow objects]

Statistics report , Blocked Time StatBlockingDelta [SimTalk]

Returns the standard deviation of the time spans during which the object designated by &lt;Path&gt; was blocked from the mean.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatBlockingDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatBlockingDelta

See also

Blocked [state, material flow objects]

Statistics report , Blocked Time

###### StatBlockingMu [SimTalk]

Returns the mean duration of the time spans during which the object designated by &lt;Path&gt; was blocked .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatBlockingMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatBlockingMu

See also

Blocked [state, material flow objects]

Statistics report , Blocked Time StatBlockingPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was blocked .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatBlockingPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatBlockingPortion

See also

Blocked [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Blocked Time StatBlockingTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was blocked .

Type

Read-only attribute

Syntax

< Path >.StatBlockingTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatBlockingTime

See also

Blocked [state, material flow objects]

Statistics report , Blocked Time

**StatEmptyCount [SimTalk]**

StatEmptyCount [SimTalk]

Returns the number of time spans during which the object designated by &lt;Path&gt; was empty , i.e., not failed , not paused , or not stopped .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatEmptyCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print MyStation.StatEmptyCount
```

See also

Statistics report , Empty Time [material flow objects]

Statistics report , Empty Time [MUs]

Empty [state, material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects]

###### StatEmptyDelta [SimTalk]

Returns the standard deviation of the time spans from the mean value during which the object designated by &lt;Path&gt; was empty , i.e., not failed , not paused , or not stopped .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatEmptyDelta → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print MyAssembly.StatEmptyDelta
```

See also

Statistics report , Empty Time [material flow objects]

Statistics report , Empty Time [MUs]

Empty [state, material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects]

**StatEmptyMu [SimTalk]**

StatEmptyMu [SimTalk]

Returns the mean duration of the time span during which the object designated by &lt;Path&gt; was empty , i.e., not failed , not paused , or not stopped .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatEmptyMu → real
```

Return Value

The return value has the data type real .

Example

print ParallelStation.StatEmptyMu

See also

Statistics report , Empty Time [material flow objects]

Statistics report , Empty Time [MUs]

Empty [state, material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects]

StatEmptyPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was empty , i.e., not failed , not paused , or not stopped .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatEmptyPortion → real
```

Return Value

The return value has the data type real .

Example

print ParallelStation.StatEmptyPortion

See also

Tab Statistics [material flow objects]

Tab Statistics [Container]

Statistics Values [Transporter]

Statistics report , Empty Time [material flow objects]

Statistics report , Empty Time [MUs]

Statistics report , Material Flow Properties [MUs]

Empty [state, material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects]

**StatEmptyTime [SimTalk]**

StatEmptyTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was empty , i.e., not failed , not paused , or not stopped .

Type

Read-only attribute

Syntax

< Path >.StatEmptyTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatEmptyTime

See also

Statistics report , Empty Time [material flow objects]

Statistics report , Empty Time [MUs]

Empty [state, material flow objects]

Failed [state - material flow objects]

Paused [state, material flow objects]

Stopped [state, material flow objects] state

###### StatEntranceBlockedPortion [SimTalk]

Returns the portion of the time during which the entrance of the material flow object designated by &lt;Path&gt; was blocked because it could not receive a MU from any of its predecessors.

Remarks

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- That left a Conveyor at a sensor.
- That could not leave the predecessor because its exit was locked .

Plant Simulation also does not record times for which the entrance of the material flow object was locked .

The entrance blocked portion does not refer to the entire simulation time, but only to the time during which the material flow object was available , i.e, it was not paused , failed , or stopped .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEntranceBlockedPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEntranceBlockedPortion

SimTalk

StatEntranceBlockedTime [SimTalk]

**See also**

**Entrance Blocked**

###### StatEntranceBlockedTime [SimTalk]

Returns the time during which the entrance of the material flow object designated by &lt;Path&gt; was blocked because it could not receive a MU from any of its predecessors.

Remarks

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- That left a Conveyor at a sensor.
- That could not leave the predecessor because its exit was locked .

Plant Simulation also does not record times for which the entrance of the material flow object was locked .

The entrance blocked time does not refer to the entire simulation time, but only to the time during which the material flow object was available , i.e, it was not paused , failed , or stopped .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEntranceBlockedTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEntranceBlockedTime

SimTalk

StatEntranceBlockedPortion [SimTalk]

**See also**

**Entrance Blocked**

###### StatExitBlockedPortion [SimTalk]

Returns the portion of the time during which the exit of the material flow object designated by &lt;Path&gt; was blocked because no part could leave it as all of the successors could not take the part.

Remarks

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- Which left a Conveyor at a sensor.
- For which the Dwell Time of a Buffer has not passed yet.

Plant Simulation also does not record times for which the exit of the material flow object was locked.

The StatExitBlockedPortion does not refer to the entire simulation time, but only to the time during which the material flow object was available, i.e, it was not paused , failed , or stopped .

**Note**

Plant Simulation considers a Buffer/PlaceBuffer as starved if it cannot provide parts to a successor, no matter if a successor could currently take the part or not. The starved condition is the opposite of the Exit Blocked condition, i.e., a Buffer/PlaceBuffer is either in the state Exit Blocked or starved .

Therefore the exit blocked portion plus the starved portion always add up to 100 %. We do not provide the starved portion as a separate statistics value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExitBlockedPortion → real

Return Value

The return value has the data type real .

**Example**

```simtalk
print MyConveyor.StatExitBlockedPortion
print MyBuffer.StatExitBlockedPortion
print MyPlaceBuffer.StatExitBlockedPortion
```

**SimTalk**

**StatExitBlockedTime [SimTalk]**

See also

Exit Blocked

###### StatExitBlockedTime [SimTalk]

Returns the time during which the exit of the material flow object designated by &lt;Path&gt; was blocked because no part could leave it as all the successors could not take the part.

Remarks

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- Which left a Conveyor at a sensor.
- For which the Dwell Time of a Buffer has not passed yet.

Plant Simulation also does not record times for which the exit of the material flow object was locked.

The StatExitBlockedTime does not refer to the entire simulation time, but to the time during which the material flow object was available, i.e, was not paused , failed , or stopped .

**Note**

Plant Simulation considers a Buffer/PlaceBuffer as starved if it cannot provide parts to a successor, no matter if a successor could currently take the part or not. The starved condition is the opposite of the Exit Blocked condition, i.e., a Buffer/PlaceBuffer is either in the state Exit Blocked or starved .

Therefore the exit blocked portion plus the starved portion always add up to 100 %. We do not provide the starved portion as a separate statistics value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExitBlockedTime → time

Return Value

The return value has the data type time .

**Example**

```simtalk
print MyConveyor.StatExitBlockedTime
print MyBuffer.StatExitBlockedTime
print MyPlaceBuffer.StatExitBlockedTime
```

**SimTalk**

###### StatExitBlockedPortion [SimTalk]

See also

Exit Blocked

###### StatFailCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was failed .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatFailCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatFailCount

See also

Failed [state - material flow objects]

Statistics report , Failed Time

###### StatFailDelta [SimTalk]

StatFailDelta [SimTalk]

Returns the standard deviation of the failed time of the object designated by &lt;Path&gt; from the mean value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatFailDelta → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatFailDelta

See also

Failed [state - material flow objects]

Statistics report , Failed Time

###### StatFailMu [SimTalk]

Returns the mean duration of a failure of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatFailMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatFailMu

See also

Failed [state - material flow objects]

Statistics report , Failed Time

###### StatFailPortion [SimTalk]

StatFailPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was failed .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatFailPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatFailPortion

See also

Failed [state - material flow objects]

Statistics report , Failed Time

Tab Statistics [material flow objects]

Tab Type Statistics of the Drain

###### StatFailTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was failed .

Type

Read-only attribute

Syntax

< Path >.StatFailTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyStation.StatFailTime
```

See also

Failed [state - material flow objects]

Statistics report , Failed Time

**StatisticsStartRes [SimTalk]**

###### StatisticsStartRes [SimTalk]

Returns the point in time at which the object designated by &lt;Path&gt; started collecting statistical data.

Remarks

StatisticsStartRes applies to the material flow objects and to the classes of the MUs .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatisticsStartRes → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Examples

MyStation.StatisticsStartRes

.MUs.Part.StatisticsStartRes

SimTalk

initStat [SimTalk] - material flow objects

initStat [SimTalk] - MUs

###### StatMaxNumMU [SimTalk] - material flow objects

Returns the maximum number of places of the object designated by &lt;Path&gt; which were occupied up until the time of the query.

Remarks

Plant Simulation only counts the number of actually occupied places at the same time, not the cargo which the MUs transport.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatMaxNumMU → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
var use: real
use := MyStore.StatMaxNumMU/MyStore.capacity
print "MyStore", use*100, " % ","used."
```

See also

Tab Statistics [material flow objects]

Statistics Values [Transporter]

Tab Statistics [Container]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

StatMinNumMU [SimTalk] - material flow objects

Returns the minimum number of places of the object designated by &lt;Path&gt; which were occupied up until the time of the query.

Remarks

Plant Simulation only counts the number of actually occupied places at the same time, not the cargo which the MUs transport.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMinNumMU → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatMinNumMU

See also

Tab Statistics [material flow objects]

Statistics Values [Transporter]

Tab Statistics [Container]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

StatNumIn [SimTalk] - material flow objects

Returns the number of MUs that entered the object designated by &lt;Path&gt;.

Remarks

Plant Simulation only counts the MU itself, not its contents, i.e., the parts that it transports.

Let's say a Container loaded with several Parts enters an object, then the StatNumIn is increased by one, not by the number of Parts on the Container .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatNumIn → integer

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

print MyStation.StatNumIn

See also

Tab Statistics [material flow objects]

Tab Statistics [Container]

Statistics Values [Transporter]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

StatNumOut [SimTalk] - material flow objects

Returns the number of MUs that exited the object designated by &lt;Path&gt;.

Remarks

Plant Simulation only counts the MU itself, not its contents, i.e., the parts that it transports.

Let's say a Container loaded with several Parts leaves an object, then the StatNumOut is increased by one, not by the number of Parts on the Container .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatNumOut → integer

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

print MyStation.StatNumOut

See also

Tab Statistics [material flow objects]

Tab Statistics [Container]

Statistics Values [Transporter]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

StatPausingCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was paused .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPausingCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatPausingCount

See also

Paused [state, material flow objects]

Statistics report , Paused Time

###### StatPausingDelta [SimTalk]

StatPausingDelta [SimTalk]

Returns the standard deviation from the mean value of the length of the pauses of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPausingDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatPausingDelta

See also

Paused [state, material flow objects]

Statistics report , Paused Time StatPausingMu [SimTalk]

Returns the mean duration of a pause of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPausingMu → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatPausingMu

See also

Paused [state, material flow objects]

Statistics report , Paused Time StatPausingPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was paused .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPausingPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatPausingPortion

See also

Paused [state, material flow objects]

Tab Statistics [material flow objects]

Tab Type Statistics

Statistics report , Paused Time StatPausingTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was paused .

Type

Read-only attribute

Syntax

< Path >.StatPausingTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatPausingTime

See also

Paused [state, material flow objects]

Statistics report , Paused Time StatPoweringUpDownCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was powering up/down .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

**Note**

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPoweringUpDownCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatPoweringUpDownCount

See also

Powering up/down [state, material flow objects]

Statistics report , Powering up/down Time StatPoweringUpDownDelta [SimTalk]

Returns the standard deviation from the mean value of the powering up time or the powering down time of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPoweringUpDownDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatPoweringUpDownDelta

See also

Powering up/down [state, material flow objects]

Statistics report , Powering up/down Time StatPoweringUpDownMu [SimTalk]

Returns the mean duration of the powering up time or the powering down time of the object designated by &lt;Path&gt;.

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

**Note**

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPoweringUpDownMu → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatPoweringUpDownMu

See also

Powering up/down [state, material flow objects]

Statistics report , Powering up/down Time StatPoweringUpDownPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was powering up/down .

Remarks

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPoweringUpDownPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatPoweringUpDownPortion

See also

Powering up/down [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Powering up/down Time StatPoweringUpDownTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was powering up/down .

Remarks

Plant Simulation only records this value if the station is not failed , not paused , not stopped , or not unplanned .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPoweringUpDownTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatPoweringUpDownTime

See also

Powering up/down [state, material flow objects]

Statistics report , Powering up/down Time StatPredeposition [SimTalk]

Returns the number of MUs that were located on the object designated by &lt;Path&gt; at the beginning of the statistics collection.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatPredeposition → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatPredeposition

StatRelativeEmptyPortion [SimTalk]

Returns the relative portion of the statistics collection period during which the object designated by &lt;Path&gt; was empty in relation to the time during which the object was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRelativeEmptyPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatRelativeEmptyPortion

See also

Empty [state, material flow objects]

Tab Statistics [material flow objects]

Tab Statistics [Container]

Statistics Values [Transporter]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

###### StatRelativeFullPortion [SimTalk]

Returns the relative portion of the statistics collection period during which all temporary storage places of the Buffer , the PlaceBuffer , and of the Sorter designated by &lt;Path&gt; were occupied in relation to the time during which the object was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRelativeFullPortion → real

Return Value

The return value has the data type real .

Example

print MyBuffer.StatRelativeFullPortion

See also

Tab Statistics [material flow objects] of Buffer , PlaceBuffer , and Sorter

Statistics report , Material Flow Properties [material flow objects]

StatRelativeOccupation [SimTalk] - material flow objects

Returns the relative, i.e., capacity-based, occupancy of the object designated by &lt;Path&gt;.

Remarks

The relative occupancy is determined by the sum of the dwelling times, that are located within the statistics collection period, of all MUs on an object during which the object was not paused , unplanned , or failed , divided by the capacity and the entire statistics collection period without counting pauses, unplanned times, or failures. The return value 0 stands for 0 percent, the return value 1 stands for 100 percent.

Take a ParallelStation for example with four processing stations that processes a single MU during the entire statistics collection period. It has a relative occupancy of 25 percent.

A Conveyor , which is fully occupied during the entire statistics collection period, has a relative occupancy of 100 % for example. If the distance of the MUs on the Conveyor is exactly as great as the length of the MU, the relative occupancy is 50%. The Speed of the connected Conveyors affects the relative occupancy or when the MU moves from the Conveyor onto a point-oriented object respectively. Relative occupancy plus relative empty time do not add up to 100% because it does not matter how much of the Conveyor is occupied during the time that it is not empty.

Use StatRelativeOccupation to compute the average waiting time of a MU (excluding paused , unplanned , and failed times):

```simtalk
(EventController.SimTime - EventController.StartStat) * Buffer.StatRelativeOccupation * Buffer.capacity / (Buffer.StatNumOut + Buffer.NumMU)
```

In addition, you can compute the average number of MUs on the object designated by &lt;Path&gt;:

Buffer.StatRelativeOccupation * Buffer.Capacity

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatRelativeOccupation → real
```

Return Value

The return value has the data type real .

**Example**

```simtalk
if drill.StatRelativeOccupation < 0.2
	print drill.name, " utilization is too low."
end
```

SimTalk

StatRelativeOccupationIR [SimTalk] - material flow objects

See also

Relative Occupation

Tab Statistics [material flow objects]

Tab Statistics [Container]

Statistics Values [Transporter]

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

StatRelativeOccupationIR [SimTalk] - material flow objects

Returns the relative, i.e., capacity-based, occupancy with interruptions, i.e., with pauses , unplanned times and failures , of the object designated by &lt;Path&gt;.

Remarks

The relative occupancy with interruptions is computed from the relation of the sum of the dwelling times of the MUs and the product of statistics collection period and capacity. The return value 0 stands for 0 percent, the return value 1 stands for 100 percent.

Use StatRelativeOccupationIR to compute the average waiting time of a MU (including paused , unplanned , and failed times):

```simtalk
(EventController.SimTime - EventController.startstat) * Buffer.StatRelativeOccupationIR * Buffer.capacity / (Buffer.StatNumOut + Buffer.NumMU)
```

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatRelativeOccupationIR → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print MyStation.StatRelativeOccupationIR
```

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

StatRelativeOccupation [SimTalk] - material flow objects

**See also**

Statistics report , Material Flow Properties [material flow objects]

Statistics report , Material Flow Properties [MUs]

###### StatSetUpCount [SimTalk]

StatSetUpCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was setting-up .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSetUpCount → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatSetUpCount

See also

Setting-Up [state, material flow objects]

Statistics report , Set-up Time [statistics report]

###### StatSetUpDelta [SimTalk]

Returns the standard deviation from the mean value of the set-up time of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSetUpDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatSetUpDelta

See also

Setting-Up [state, material flow objects]

Statistics report , Set-up Time [statistics report]

###### StatSetUpMu [SimTalk]

StatSetUpMu [SimTalk]

Returns the mean duration of a set-up process of the object designated by &lt;Path&gt;.

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSetUpMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatSetUpMu

See also

Setting-Up [state, material flow objects]

Statistics report , Set-up Time [statistics report]

###### StatSetUpPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was setting-up to process a different type of part.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSetUpPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatSetUpPortion

See also

Setting-Up [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Set-up Time [statistics report]

Tab Type Statistics of the Drain

###### StatSetupTime [SimTalk]

StatSetupTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was setting-up .

Type

Read-only attribute

Syntax

< Path >.StatSetupTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatSetupTime

See also

Setting-Up [state, material flow objects]

Statistics report , Set-up Time [statistics report]

StatStoppedCount [SimTalk] - material flow objects

Returns how often the LockoutZone stopped the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatStoppedCount

See also

Stopped [state, material flow objects]

Statistics report , Stopped Time

LockoutZone StatStoppedDelta [SimTalk] - material flow objects Returns the standard deviation from the mean value during which the object designated by &lt;Path&gt; was stopped by the LockoutZone .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatStoppedDelta

See also

Stopped [state, material flow objects]

Statistics report , Stopped Time

LockoutZone StatStoppedMu [SimTalk] - material flow objects Returns the mean duration of the time during which the object designated by &lt;Path&gt; was stopped by the LockoutZone .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatStoppedMu → real
```

Return Value

The return value has the data type real .

Example

print MyStation.StatStoppedMu

See also

Stopped [state, material flow objects]

Statistics report , Stopped Time

LockoutZone StatStoppedPortion [SimTalk] - material flow objects Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was stopped by the LockoutZone .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoppedPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatStoppedPortion

See also

Stopped [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Stopped Time

LockoutZone StatStoppedTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was stopped by the LockoutZone .

Type

Read-only attribute

Syntax

< Path >.StatStoppedTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatStoppedTime

See also

Stopped [state, material flow objects]

Statistics report , Stopped Time

LockoutZone StatUnplannedCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatUnplannedCount → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatUnplannedCount

See also

Unplanned [state, material flow objects]

###### StatUnplannedDelta [SimTalk]

Returns the standard deviation from the mean value during which the object designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatUnplannedDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatUnplannedDelta

See also

Unplanned [state, material flow objects]

###### StatUnplannedMu [SimTalk]

StatUnplannedMu [SimTalk]

Returns the mean duration of the time during which the object designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatUnplannedMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatUnplannedMu

See also

Unplanned [state, material flow objects]

###### StatUnplannedPortion [SimTalk]

Returns the ratio of the time during which the object designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatUnplannedPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatUnplannedPortion

See also

Unplanned [state, material flow objects]

Tab Statistics [material flow objects]

StatUnplannedTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatUnplannedTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatUnplannedTime

See also

Unplanned [state, material flow objects]

###### StatWaitingCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was waiting .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingCount → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatWaitingCount

See also

Waiting [state, material flow objects]

Statistics report , Waiting Time

###### StatWaitingDelta [SimTalk]

StatWaitingDelta [SimTalk]

Returns the standard deviation of the waiting times from the mean value of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingDelta → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingDelta

See also

Waiting [state, material flow objects]

Statistics report , Waiting Time

###### StatWaitingMu [SimTalk]

Returns the mean duration of the time during which the object designated by &lt;Path&gt; was waiting .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWaitingMu

See also

Waiting [state, material flow objects]

Statistics report , Waiting Time StatWaitingPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was waiting .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingPortion → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingPortion

See also

Waiting [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Waiting Time of the stationary objects StatWaitingResCount [SimTalk] - material flow objects Returns how often the object designated by &lt;Path&gt; was waiting for processing-Exporters/processingservices .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResCount → integer

Return Value

The return value has the data type integer .

Example

print MyStation.StatWaitingResCount

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts StatWaitingResDelta [SimTalk] - material flow objects Returns the mean deviation of a time span during which the object designated by &lt;Path&gt; was waiting for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResDelta → integer

Return Value

The return value has the data type integer .

Example

print ParallelStation.StatWaitingResDelta

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts

###### StatWaitingResMu [SimTalk] - material flow objects

Returns the mean duration of a time span during which the object designated by &lt;Path&gt; was waiting for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWaitingResMu

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts StatWaitingResPortion [SimTalk] - material flow objects Returns the portion of the statistics collection period the object designated by &lt;Path&gt; was waiting for processing-Exporters/processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResPortion → real

Return Value

The return value has the data type real .

Example

print Station.StatWaitingResPortion

See also

Waiting [state, material flow objects]

Statistics report , Importers Waiting for Services and Parts

Statistics report , Waiting Times for Services and Parts StatWaitingResTime [SimTalk] - material flow objects Returns the total time during which the object designated by &lt;Path&gt; was waiting for processing-Exporters/ processing-services .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingResTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatWaitingResTime

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Services and Parts StatWaitingSetUpExpBlockingPortion [SimTalk]

Returns the portion of the time during which the object designated by &lt;Path&gt; was waiting for Exporters/ services for setting-up while being blocked .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpBlockingPortion → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingSetUpExpBlockingPortion

See also

Waiting [state, material flow objects]

Blocked [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters

###### StatWaitingSetUpExpCount [SimTalk]

Returns number of time spans during which the object designated by &lt;Path&gt; was waiting for Exporters/ services for setting-up .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpCount → integer

Return Value

The return value has the data type integer .

Example

print MyAssembly.StatWaitingSetUpExpCount

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters

Statistics report , Importers Waiting for Services and Parts StatWaitingSetUpExpDelta [SimTalk]

Returns the standard deviation from the mean value during which the object designated by &lt;Path&gt; was waiting for Exporters/services for setting-up .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpDelta → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingSetUpExpDelta

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters StatWaitingSetUpExpMu [SimTalk]

Returns the mean duration while the object designated by &lt;Path&gt; was waiting for Exporters/services for setting-up .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpMu → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingSetUpExpMu

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters StatWaitingSetUpExpPortion [SimTalk]

Returns the portion of the statistics collection period during which the object designated by &lt;Path&gt; was waiting for Exporters/services for setting-up .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWaitingSetUpExpPortion

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters

Statistics report , Importers Waiting for Services and Parts StatWaitingSetUpExpTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was waiting for Exporters/services for setting-up .

Type

Read-only attribute

Syntax

< Path >.StatWaitingSetUpExpTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatWaitingSetUpExpTime

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters StatWaitingSetUpExpWaitingPortion [SimTalk]

<!-- image -->

Returns the total time portion during which the object designated by &lt;Path&gt; was waiting for Exporters/ services for setting-up .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpWaitingPortion → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingSetUpExpWaitingPortion

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters StatWaitingSetUpExpWorkingPortion [SimTalk]

Returns the total portion the object designated by &lt;Path&gt; was waiting for Exporters/services for setting-up while the object was waiting .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWaitingSetUpExpWorkingPortion → real

Return Value

The return value has the data type real .

Example

print ParallelStation.StatWaitingSetUpExpWorkingPortion

See also

Waiting [state, material flow objects]

Statistics report , Waiting Times for Set-up Exporters

###### StatWaitingTime [SimTalk]

StatWaitingTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was waiting .

Type

Read-only attribute

Syntax

< Path >.StatWaitingTime → time

Return Value

The return value has the data type time .

Example

print ParallelStation.StatWaitingTime

See also

Waiting [state, material flow objects]

Statistics report , Waiting Time

###### StatWorkingCount [SimTalk]

Returns how often the object designated by &lt;Path&gt; was working .

Remarks

The state working will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWorkingCount → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWorkingCount

See also

Working [state, material flow objects]

Tab Statistics [material flow objects]

Statistics report , Working Time StatWorkingDelta [SimTalk]

Returns the standard deviation of the time spans during which the object designated by &lt;Path&gt; was working from the mean value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWorkingDelta → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWorkingDelta

See also

Working [state, material flow objects]

Statistics report , Working Time

###### StatWorkingMu [SimTalk]

Returns the mean duration of the time spans during which the object designated by &lt;Path&gt; was working .

Remarks

The state will not be terminated by failures , pauses , or shift changes , but it will only be interrupted.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWorkingMu → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWorkingMu

See also

Working [state, material flow objects]

Statistics report , Working Time StatWorkingPortion [SimTalk]

Returns the portion of the statistics collection period during which the object was working .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatWorkingPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatWorkingPortion

See also

Working [state, material flow objects]

Tab Statistics [material flow objects]

Tab Type Statistics of the Drain

Statistics report , Working Time

###### StatWorkingTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was working

Type

Read-only attribute

Syntax

< Path >.StatWorkingTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyStation.StatWorkingTime
```

See also

Working [state, material flow objects]

Statistics report , Working Time

Read-Only Attributes for Energy Statistics

\_Read-Only Attributes for Energy Statistics

Plant Simulation provides the read-only attributes listed in the table of contents to the left for querying the energy consumption statistics of the material flow objects.

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyStation.StatEnergyFailConsumption

See also

Tab Statistics [material flow objects] &gt; Energy Statistics [button]

\_Attributes for the Energy Simulation

###### PowerInput [SimTalk]

Returns the current power input of the object designated by &lt;Path&gt; depending on the current energy state in kilowatts.

Type

Read-only attribute

Syntax

```simtalk
< Path >.PowerInput → real
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

print Station.PowerInput

See also

Active [check box] - energy StatEnergyFailConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was failed .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyFailConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyFailConsumption StatEnergyFailConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was failed .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyFailConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyFailConsumptionPortion

See also

Energy Statistics [button]

Statistics report , Energy Statistics - Energy Statistics

###### StatEnergyFailTime [SimTalk]

StatEnergyFailTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was failed .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyFailTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergyFailTime

###### StatEnergyOffConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was off .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOffConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyOffConsumption StatEnergyOffConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was off .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOffConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyOffConsumptionPortion

See also

Energy Statistics [button]

Statistics report , Energy Statistics - Energy Statistics

###### StatEnergyOffTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was off .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOffTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergyOffTime StatEnergyOperationalConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was operational .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOperationalConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyOperationalConsumption

###### StatEnergyOperationalConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was operational .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOperationalConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyOperationalConsumptionPortion

See also

Energy Statistics

Statistics report , Energy Statistics - Energy Statistics StatEnergyOperationalTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was operational .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyOperationalTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergyOperationalTime

###### StatEnergySetupConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was setting-up .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergySetupConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergySetupConsumption StatEnergySetupConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was setting-up .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergySetupConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergySetupConsumptionPortion

See also

Energy Statistics

###### StatEnergySetupTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was setting-up .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

< Path >.StatEnergySetupTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergySetupTime

###### StatEnergyStandbyConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was on standby .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyStandbyConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyStandbyConsumption

###### StatEnergyStandbyConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was on standby .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyStandbyConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyStandbyConsumptionPortion

See also

Energy Statistics

Statistics report , Energy Statistics - Energy Statistics StatEnergyStandbyTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was on standby .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyStandbyTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergyStandbyTime

###### StatEnergyTotalConsumption [SimTalk]

Returns the total energy consumption of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyTotalConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyTotalConsumption

See also

Energy Statistics [button]

Statistics report , Energy Statistics - Energy Statistics

###### StatEnergyWorkingConsumption [SimTalk]

Returns the total energy consumption during which the object designated by &lt;Path&gt; was working .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyWorkingConsumption → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyWorkingConsumption StatEnergyWorkingConsumptionPortion [SimTalk]

Returns the portion of the total energy consumption during which the object designated by &lt;Path&gt; was working .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatEnergyWorkingConsumptionPortion → real

Return Value

The return value has the data type real .

Example

print MyStation.StatEnergyWorkingConsumptionPortion

See also

Energy Statistics [button]

Statistics report , Energy Statistics - Energy Statistics

###### StatEnergyWorkingTime [SimTalk]

Returns the total time during which the object designated by &lt;Path&gt; was working .

Remarks

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

Type

Read-only attribute

Syntax

< Path >.StatEnergyWorkingTime → time

Return Value

The return value has the data type time .

Example

print MyStation.StatEnergyWorkingTime

