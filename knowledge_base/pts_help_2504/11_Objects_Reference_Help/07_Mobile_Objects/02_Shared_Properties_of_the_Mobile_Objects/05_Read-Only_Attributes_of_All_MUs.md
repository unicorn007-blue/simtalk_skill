#### Read-Only Attributes of All MUs

Read-Only Attributes of All MUs

The mobile objects provide:

- \_Read-Only Attributes for the Location
- \_Read-Only Attributes for the State of the MUs
- \_Read-Only Attributes for Accessing the Load
- \_Read-Only Attributes for Accessing Statistics of the MUs

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

**Read-Only Attributes for the Location**

##### \_Read-Only Attributes for the Location

The MUs provide the read-only attributes listed in the table of contents to the left for querying their location.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print @.FrontPos

###### BookPos [SimTalk]

Returns the position of the booking point of the MU designated by &lt;MU-Path&gt; according to the current Conveying Direction on the object on which it is located.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.BookPos → real
```

Return Value

The return value has the data type real .

**Note**

BookPos only returns the position if the active MU is located on a length-oriented object!

For point-oriented objects the return value always is 0.

**Examples**

```simtalk
print @.BookPos
print .MUs.Board:1.BookPos // might
return 1.57983600312685m
```

SimTalk

ConveyingDirection [SimTalk]

setLength [SimTalk] - MUs

See also

New [sensor]

ConveyingDirection [SimTalk]

###### Coordinate3D [SimTalk] - MUs

Coordinate3D [SimTalk] - MUs

Returns the 3D coordinate of the moving object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation 2D computes these coordinates of data type real using the pixel coordinates in 2D, the Scaling Factor you entered, and the 3D origin .

**Note**

You cannot set the 3D coordinate of the MU , you can only get it!

You cannot query the value of Coordinate3D for MU instances in a 3D Only model.

Type

Read-only attribute

Syntax

<MUPath >.Coordinate3D:array

Return Value

The return value is an array of data type length with three values.

Examples

```simtalk
var a: length[3]
a := .MUs.Transporter:3.Coordinate3D
print a
print .MUs.Transporter:3.Coordinate3D
```

**SimTalk**

XPos [SimTalk] - MUs

YPos [SimTalk] - MUs _3D.getPositionOfObject [SimTalk] _3D.getWorldCoordinate [SimTalk]

**Coordinate3D [SimTalk] - MUs**

**FrontLocation [SimTalk]**

###### FrontLocation [SimTalk]

Returns the object on which the front end of the MU designated by &lt;MU-Path&gt; is located.

**Remarks**

If the MU is spread over several length-oriented objects with different insertion directions, the insertion direction of the MU is determined by the Front or the Rear of the object on which the MU is booked. This is, for example, the case if a part of the MU is located on a Converter or on an active Loading Space of the Transporter .

**Compare the example below:**

The Source produces a part named Board and moves it forward onto the Conveyor .

<!-- image -->

It moves it on to the cross-sliding car , more exactly onto the CSC\_Car . The CSC\_Car has the Loading Space Type &gt; Line and Backwards is activated because the insertion direction of the CSC\_Car is from up to down here. As long as Board is booked on the Conveyor , the front location is the CSC\_Car and the rear location is the Conveyor .

<!-- image -->

As soon as Board is booked on the CSC\_Car , the front location is the Conveyor and the CSC\_Car is the rear location.

The cross-sliding car then moves on to Conveyor1 . While Board moves off the CSC\_Car , but is still booked on it, the front location is the CSC\_Car and the rear location is Conveyor1 .

<!-- image -->

As soon as Board is booked on Conveyor1 , the front location is Conveyor1 and the rear location is the CSC\_Car .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.FrontLocation → object
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

<!-- image -->

**FrontLocation [SimTalk]**

**Examples**

```simtalk
print @.FrontLocation.NumMu
print "FrontLocation: ", .MUs.Board:1.FrontLocation
print "RearLocation: ",  .MUs.Board:1.RearLocation
```

**SimTalk**

RearLocation [SimTalk]

FrontLocation [SimTalk]

FrontLocationInMovingDirection [SimTalk]

###### FrontLocationInMovingDirection [SimTalk]

Returns the object on which the front end of the MU in the direction of motion and designated by &lt;MU-Path&gt; is located.

Remarks

As opposed to the read-only attribute FrontLocation it does not matter where the MU is booked and in which direction the location is inserted into the Frame .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.FrontLocationInMovingDirection → object

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

Example

print @.FrontLocationInMovingDirection

SimTalk

FrontLocation [SimTalk]

RearLocation [SimTalk]

RearLocationInMovingDirection [SimTalk]

**FrontMU [SimTalk]**

###### FrontMU [SimTalk]

Returns the MU which is located on the same object in front of the MU designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.FrontMU → object
```

Return Value

The return value has the data type object .

**Example**

```simtalk
// We use a collision control to find out if the predecessor failed or not.
if @.FrontMU /= VOID
	if @.FrontMU.failed
		print "Jammed because of failure."
	end
end
```

**SimTalk**

**RearMU [SimTalk]**

###### FrontPos [SimTalk]

Returns the exact position of the front of the MU designated by &lt;MU-Path&gt; on the material flow object.

Remarks

If the MU is spread over several length-oriented objects with different insertion directions, the insertion direction of the MU is determined by the Front or the Rear of the object on which the MU is booked. This is, for example, the case if a part of the MU is located on a Converter or on an active Loading Space of the Transporter .

For length-oriented objects the entrance has the position 0 and the exit has the position Length of the object. On point-oriented objects ( Station , ParallelStation , etc.) the return value always is 0.

Type

Read-only attribute

Syntax

<MUPath >.FrontPos → length

Return Value

The return value has the data type length .

Example

print @.FrontPos

SimTalk

RearPos [SimTalk]

FrontPos [SimTalk]

FrontPosInMovingDirection [SimTalk]

###### FrontPosInMovingDirection [SimTalk]

Returns the exact position of the front of the MU in the direction of motion and designated by &lt;MU-Path&gt;.

Remarks

As opposed to the read-only attribute FrontPos it does not matter where the MU is booked and in which direction the location is inserted into the Frame .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.FrontPosInMovingDirection → length

Return Value

The return value has the data type length .

Example

print @.FrontPosInMovingDirection

SimTalk

FrontPos [SimTalk]

RearPos [SimTalk]

RearPosInMovingDirection [SimTalk]

###### GetNo [SimTalk]

Returns the unique number of the MU designated by &lt;MU-Path&gt; in the sequence in which the instances were inserted into the model.

Remarks

In the dialog the number is displayed next to the name, separated by a colon.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.GetNo → integer
```

**Return Value**

The return value has the data type integer and is greater than 0.

The return value can access each instance.

Example

```simtalk
print .MUs.Transporter:1.GetNo = 1 // always returns true
print @.GetNo > 10
```

**SimTalk**

num [SimTalk] - MUs

See also

Number [of the MU]

HasRouteToDestination [SimTalk] - MUs

Returns if the Container/Part designated by &lt;MU-Path&gt; did find a route to its destination (true) or if it did not find it (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.HasRouteToDestination → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

```simtalk
print .MUs.Part:1.HasRouteToDestination
```

SimTalk

getRoute [SimTalk] - Part, Container

See also

Route to Destination [Part, Container]

Destination [Part, Container]

###### LocationInFrame [SimTalk]

Returns the station or the length-oriented object on which the MU designated by &lt;MU-Path&gt; is located.

**Remarks**

The LocationInFrame is important when a part is loaded onto another part. Otherwise LocationInFrame returns the same object as the read-only attribute Location does.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.LocationInFrame → object
```

**Return Value**

The return value has the data type object .

void if the Transporter or the Worker are driving or walking freely within the area.

**Example**

```simtalk
print .MUs.Part:1.LocationInFrame  // might, for example,
return .Models.Model.Station
print .MUs.Part:2.LocationInFrame  // might, for example,
return .Models.Model.Conveyor
```

**SimTalk**

Location [SimTalk] - material flow objects

**PreviousLocation [SimTalk]**

###### PreviousLocation [SimTalk]

Returns the previous location of the MU designated by &lt;MU-Path&gt;.

Remarks

The previous location is the object on which the part was located before it moved onto the current material flow object.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.PreviousLocation → object
```

Return Value

The return value has the data type object .

Example

```simtalk
print .MUs.Part:22037.PreviousLocation
```

###### RearLocation [SimTalk]

Returns the object on which the rear end of the MU designated by &lt;MU-Path&gt; is located.

**Remarks**

If the MU is spread over several length-oriented objects with different insertion directions, the insertion direction of the MU is determined by the Front or the Rear of the object on which the MU is booked. This is, for example, the case if a part of the MU MU is located on a Converter or on an active Loading Space of the Transporter .

**Compare the example below:**

The Source produces a part named Part1 and moves it forward onto the Conveyor .

<!-- image -->

It moves it on to the cross-sliding car , more exactly onto the CSC\_Car . The CSC\_Car has the Loading Space Type &gt; Line and Backwards is activated because the insertion direction of the CSC\_Car is from up to down. As long as Part1 is booked on the Conveyor , the front location is the CSC\_Car and the rear location is the Conveyor .

<!-- image -->

As soon as Part1 is booked on the CSC\_Car , the front location is the Conveyor and the CSC\_Car is the rear location.

The cross-sliding car then moves on to Conveyor1 . While Part1 moves off the CSC\_Car , but is still booked on it, the front location is the CSC\_Car and the rear location is Conveyor1 .

<!-- image -->

As soon as Part1 is booked on Conveyor1 , the front location is Conveyor1 and the rear location is the CSC\_Car .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.RearLocation → object
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

<!-- image -->

**Examples**

```simtalk
print @.RearLocation.NumMu
print "FrontLocation: ", .MUs.Board:1.FrontLocation
print "RearLocation: ",  .MUs.Board:1.RearLocation
```

**SimTalk**

FrontLocation [SimTalk]

FrontLocationInMovingDirection [SimTalk]

RearLocationInMovingDirection [SimTalk]

RearLocationInMovingDirection [SimTalk]

Returns the object on which the rear end of the MU designated by &lt;MU-Path&gt; in the direction of motion is located.

Remarks

As opposed to the read-only attribute em RearLocation it does not matter where the MU is booked and in which direction the location is inserted into the Frame .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.RearLocationInMovingDirection → object

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

Example

print @.RearLocationInMovingDirection

SimTalk

FrontLocation [SimTalk]

FrontLocationInMovingDirection [SimTalk]

RearLocation [SimTalk]

###### RearMU [SimTalk]

Returns the MU , which is located directly behind the MU designated by &lt;MU-Path&gt; on the same material flow object.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.RearMU → object
```

Return Value

The return value has the data type object .

Example

```simtalk
@.RearMU.Stopped := true
```

if @.RearMU /= VOID end

SimTalk

FrontMU [SimTalk]

###### RearPos [SimTalk]

RearPos [SimTalk]

Returns the location of the rear of the MU designated by &lt;MU-Path&gt;.

Remarks

If the MU is spread over several length-oriented objects with different insertion directions, the insertion direction of the MU is determined by the Front or the Rear of the object on which the MU is booked. This is, for example, the case if a part of the MU is located on a Converter or on an active Loading Space of the Transporter .

For length-oriented objects the entrance has the position 0 and the exit has the position Length of the object. If the rear of the MU has not entered the length-oriented object yet, the read-only attribute returns a negative value that matches the overhang.

Type

Read-only attribute

Syntax

<MUPath >.RearPos → length

Return Value

The return value has the data type length .

On point-oriented objects ( Station , ParallelStation , etc.) the return value always is 0.

Example

```simtalk
print @.RearPos
```

SimTalk

FrontPos [SimTalk]

###### RearPosInMovingDirection [SimTalk]

Returns the location of the rear of the MU in the direction of motion and designated by &lt;MU-Path&gt;.

Remarks

As opposed to the read-only attribute RearPos it does not matter where the MU is booked and in which direction the location is inserted into the Frame .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.RearPosInMovingDirection → length

Return Value

The return value has the data type length .

Example

print @.RearPosInMovingDirection

SimTalk

FrontPos [SimTalk]

FrontPosInMovingDirection [SimTalk]

RearPos [SimTalk]

**ReservedPlace [SimTalk]**

###### ReservedPlace [SimTalk]

Returns the place which is reserved for the MU designated by &lt;MU-Path&gt; on the material flow object.

Remarks

Plant Simulation does, for example, reserve a place when you use a transport importer to carry a part to the destination and when you activated Wait for Free Target .

Plant Simulation does also reserve a place when a PickAndPlace robot transports a part to the target and when you activated Wait for Free Target .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.ReservedPlace:object
```

Return Value

The return value has the data type object .

void if no place is reserved.

Examples

```simtalk
// @ refers to a MU which is located on a Station:
print @.ReservedPlace // for example .Models.Model.Station.pe
// @ refers to a MU which is located on a ParallelStation:
print @.ReservedPlace // for example .Models.Model.ParallelStation.pe[2,1]
```

SimTalk

contentsAndReservedList [SimTalk]

ReservedFor [SimTalk]

WaitForFreeTarget [SimTalk] - transport importer

WaitForFreeTarget [SimTalk] -PickAndPlace See also Contents and Reserved Places Wait for Free Target [transport importer]

Wait for Free Target [PickAndPlace]

Model a Worker Who Waits for a Free Target

Read-Only Attributes for the State of the MUs

\_Read-Only Attributes for the State of the MUs

The MUs provide the read-only attributes listed in the table of contents to the left for querying their state.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print .MUs.Transporter:123.Occupied
```

###### BlockingStarttime [SimTalk]

Returns the point in time at which the blocking time of the MU designated by &lt;MU-Path&gt; started.

Remarks

The BlockingStarttime also applies to the Sorter and to the FlowControl , i.e., to the objects that can appear in a Blocking List .

Type

Read-only attribute

Syntax

<MUPath >.BlockingStarttime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Part:872564.BlockingStarttime
```

See also

Forward Blocking List

Exit Blocking List

Backward Blocking List

removeFromBlocklists [SimTalk]

**CreationTime [SimTalk]**

###### CreationTime [SimTalk]

Returns the time at which the MU designated by &lt;MU-Path&gt; was created during the simulation run.

Type

Read-only attribute

Syntax

<MUPath >.CreationTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print Part:1.CreationTime
```

###### CurrentSpeed [SimTalk] - MUs

Returns the actual speed with which the MU designated by &lt;MU-Path&gt; moves.

Remarks

If the MU is located on a Conveyor , it always has the sign (+ or -) that corresponds to the direction of motion of the Conveyor .

Type

Read-only attribute

Syntax

<MUPath >.CurrentSpeed → speed

**Watchable**

The read-only attribute is watchable .

**Note**

Although this value can continually change because the object is accelerating, CurrentSpeed is watchable for certain values. By observing this value you might, for example, recognize when the speed of a MU changes, because it collided with the MU in front of it, because it stops at the end of a Conveyor , or caused by other outside influences.

**Return Value**

The return value has the data type speed .

Example

```simtalk
var MyPart: object
MyPart := MyConveyor.MU(1)
waituntil MyPart.CurrentSpeed = 0 prio 1
print "Stopped at this time:", EventController.simTime
```

See also

Current Speed [text box] - Transporter Empty [SimTalk] - MUs Empty [SimTalk] - MUs Returns if the Container/Transporter designated by &lt;MU-Path&gt; does contain another MU (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Empty → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
if @.Empty .MUs.Part.create(@)
end
```

See also

Empty [state, material flow objects]

Full [SimTalk] - MUs

###### EntryTime [SimTalk]

Returns the time at which the MU designated by &lt;MU-Path&gt; entered the object on which it is located at the moment.

Type

Read-only attribute

Syntax

<MUPath >.EntryTime → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Example

```simtalk
print ParallelStation.MU(1).EntryTime
print Station.MU(1).EntryTime
```

**Finished [SimTalk]**

###### Finished [SimTalk]

Returns if the processing time of the MU designated by &lt;MU-Path&gt; has completely elapsed (true) or not (false).

Remarks

This applies if the MU is located on a point-oriented object.

If the MU is located on a length-oriented object, the MU must have arrived at its exit. In addition, it must attempt to move at the moment or must have already attempted to move.

If both conditions are met, the return value is true. In addition, the point-oriented object or the lengthoriented object, on which the MU is located, must neither be failed, nor paused, nor stopped.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Finished → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

```simtalk
if MyTrack.Cont.Finished
	MyTrack.Cont.move(MyTrack.succ(2))
end
```

SimTalk

startProcessing [SimTalk] - material flow objects

See also

Automatic Processing

###### FinishedTime [SimTalk]

Returns the simulation time at which the MU designated by &lt;MU-Path&gt; could have left the object.

Type

Read-only attribute

Syntax

<MUPath >.FinishedTime → time

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type time .

Is -1 if the MU is not ready to exit the object.

Example

```simtalk
print .MUs.Part:1.FinishedTime
```

###### Full [SimTalk] - MUs

Full [SimTalk] - MUs

Returns if the capacity of the Container/Transporter designated by &lt;MU-Path&gt; is exhausted (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Full → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
if NOT @.Full .MUs.Part.create(@)
end
```

SimTalk

Empty [SimTalk] - MUs

See also

Empty [state, material flow objects]

###### Occupied [SimTalk] - MUs

Returns if the Container/Transporter designated by &lt;MU-Path&gt; does transport at least one other MU (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Occupied → boolean
```

Return Value

The return value has the data type boolean .

**Examples**

```simtalk
param SensorID: integer
var Container,part:object
Container := @
if Container.Occupied
	part := Container.Cont // contents if NOT
	part.move(Machine1)
	part.move(Machine2)
end
end
```

print .MUs.Transporter:123.Occupied

###### ProdInProcess [SimTalk]

ProdInProcess [SimTalk]

Returns if the MU designated by &lt;MU-Path&gt; is being processed or moving (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.ProdInProcess → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print "pallet is processed."
pallet := Station.Cont
if pallet.ProdInProcess
end
```

**See also**

Working [MUs]

###### ProdOnFailed [SimTalk]

Returns if the MU designated by &lt;MU-Path&gt; is located on a failed object (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.ProdOnFailed → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print Station.Cont.ProdOnFailed
```

See also

Failed [MUs] - state

###### ProdOnPaused [SimTalk]

ProdOnPaused [SimTalk]

Returns if the MU designated by &lt;MU-Path&gt; is located on a paused or unplanned object (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.ProdOnPaused → boolean
```

Return Value

The return value has the data type boolean .

Example

print Station.Cont.ProdOnPaused

See also

Paused [MUs]

###### ProdWaiting [SimTalk]

Returns if the MU designated by &lt;MU-Path&gt; is waiting (true), i.e., the MU is neither being processed nor located on a failed , paused or unplanned object, or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.ProdWaiting → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
pallet := Station.Cont
if pallet.ProdWaiting
	print "Pallet is being processed."
end
```

See also

Waiting [MUs]

**RemainingProcTime [SimTalk]**

###### RemainingProcTime [SimTalk]

Returns the time for which the MU designated by &lt;MU-Path&gt; still has to be processed.

Remarks

You can also view the remaining processing time in the window Show Attributes and Methods of the object.

<!-- image -->

Type

Read-only attribute

Syntax

<!-- image -->

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Part:872564.RemainingProcTime
```

###### TimeToOutEvent [SimTalk]

Returns the simulation time at which the Out event for the MU designated by &lt;MU-Path&gt; has been scheduled.

Type

Read-only attribute

Syntax

<MUPath >.TimeToOutEvent → time

Return Value

The return value has the data type time .

The return value is -1 if no Out event has been scheduled.

Example

```simtalk
print .MUs.Part:1.TimeToOutEvent
```

###### Waiting [SimTalk]

Waiting [SimTalk]

Returns if the MU designated by &lt;MU-Path&gt; is waiting, i.e., if the processing time of the MU has not started yet (if the object on which it is located is still being set-up) or is already finished (if the MU be moved on after being processed) (true).

Remarks

During processing Waiting returns false, even if processing is interrupted by a failure or a pause.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Waiting → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

```simtalk
var pallet : object
pallet := Station.Cont
if pallet.Waiting
	pallet.move(Station.succ(2))
end
```

Read-Only Attributes for the Load

\_Read-Only Attributes for Accessing the Load

The MUs provide the read-only attributes listed in the table of contents to the left for accessing the cargo on the loading space of Container and Transporter .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

**Note**

These read-only attributes do not apply to the Part as it does not have any loading capacity.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print @.FrontPos

###### Capacity [SimTalk] - MUs

Capacity [SimTalk] - MUs

Returns the capacity of the Container and of the loading space of type Store of the Transporter designated by &lt;MU-path&gt;.

Remarks

The Capacity is the product of XDim times XDim .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Capacity → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print @.Capacity
```

SimTalk

XDim [SimTalk] - Container

YDim [SimTalk] - Container

See also

X-Dimension [Container]

Y-Dimension [Container]

X-Dimension [Transporter]

Y-Dimension [Transporter]

###### Cont [SimTalk] - MUs

Cont [SimTalk] - MUs

Returns the MU which is located on the loading space of the MU designated by &lt;MU-Path&gt;.

Type

You can also use Cont to access any loading place on the loading space by its position in the x-direction and the y-direction.

If you activated FillWholeLayer of the Container , Cont returns the next MU from the stack containing the most parts.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Cont → object <MUPath >[X:integer, Y:integer].Cont → object
```

**Parameters**

- The parameter X of data type integer designates the x-position of the MU .
- The parameter Y of data type integer designates the y-position of the MU .

Return Value

The return value has the data type object .

Examples

```simtalk
@.Cont.move(Station) @[1,1].Cont.move(Station)
// Accesses the topmost MU of the stack .MUs.Transporter:1[1,1].Cont
```

**SimTalk**

FillWholeLayer [SimTalk]

**See also Contents [MUs] Statistics Values [Transporter]**

Fill Whole Layer [check box]

###### NumMU [SimTalk] - MUs

NumMU [SimTalk] - MUs

Returns the number of MUs located on the loading space of the MU designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.NumMU → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.NumMU
```

SimTalk

NumMUParts [SimTalk] - MUs

###### NumMUParts [SimTalk] - MUs

Returns the number of MUs located on the MU designated by &lt;MU-Path&gt; as a whole or in part.

Remarks

For length-oriented objects a MU may have exited the object with its front part while the rear is still located on the object. In this case NumMUParts counts both occupied lengths separately, although they are part of a single MU .

**Note**

NumMu returns the number of MUs whose booking point is located on the object.

On point-oriented objects the methods NumMUParts and NumMU always return the same value.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.NumMUParts → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .Models.container:2.NumMuParts
```

SimTalk

NumMU [SimTalk] - MUs

Read-Only Attributes for Statistics of the MUs

\_Read-Only Attributes for Accessing Statistics of the MUs

The MUs provide the read-only attributes listed in the table of contents to the left for querying statistics values.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print .MUs.Transporter:1.StatAvgLifeSpan StatAvgLifeSpan [SimTalk] - MUs Returns the average life-span of MU instances of the class designated by &lt;MU-Path&gt; which were created and removed from the plant during the statistics collection period.

Type

Read-only attribute

Syntax

<MUPath >.StatAvgLifeSpan → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatAvgLifeSpan
```

See also

Tab Product Statistics [MUs]

Tab Type Statistics of the Drain

Additional Statistical Data of the MUs

Statistics report , Cumulated Statistics of the Classes

**StatCount [SimTalk]**

###### StatCount [SimTalk]

Returns the number of existing MU instances of the MU class designated by &lt;MU-Path&gt; for which you activated product statistics.

Remarks

The MUs may be located in different Frame hierarchies.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatCount
```

See also

Additional Statistical Data of the MUs

Tab Product Statistics [MUs]

Statistics report , Cumulated Statistics of the Classes StatDeleted [SimTalk] - MUs Returns the number of MU instances which were removed from the installation during statistics collection of the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatDeleted → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatDeleted
```

See also

Tab Product Statistics [MUs]

Additional Statistical Data of the MUs

Statistics report , Cumulated Statistics of the Classes

**StatFailTimePortion [SimTalk]**

StatFailTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU instance of the MU class designated by &lt;MU-Path&gt; was located on failed , but not paused objects.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatFailTimePortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatFailTimePortion
```

###### StatisticsStartProd [SimTalk]

Returns the point in time at which the MU designated by &lt;MU-Path&gt; started collecting statistical data.

Type

Read-only attribute

Syntax

<MUPath >.StatisticsStartProd → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatisticsStartProd
```

###### StatMaxNumMU [SimTalk] - MUs

StatMaxNumMU [SimTalk] - MUs

Returns the maximum number of locations the MU class designated by &lt;MU-Path&gt; occupied during the simulation run until the point in time at which you query the statistics.

Remarks

Plant Simulation does not count the maximum number of MUs , but the number of locations occupied simultaneously. Also, loads are not counted.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatMaxNumMU → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Container:1.StatMaxNumMU
```

See also

Tab Statistics [Container]

###### StatMinNumMU [SimTalk] - MUs

Returns the minimum number of locations the MU class designated by &lt;MU-Path&gt; occupied during the simulation run until the point in time at which you query the statistics.

Remarks

Plant Simulation does not count the minimum number of MUs , but the number of locations occupied simultaneously. Also, loads are not counted.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatMinNumMU → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Container:1.StatMinNumMU
```

See also

Tab Statistics [Container]

###### StatNumIn [SimTalk] - MUs

StatNumIn [SimTalk] - MUs

Returns the number of MU instances that entered the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatNumIn → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Container:1.StatNumIn
```

See also

Additional Statistical Data of the MUs

###### StatNumOut [SimTalk] - MUs

Returns the number of MU instances that exited the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatNumOut → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Container:1.StatNumOut
```

See also

Additional Statistical Data of the MUs

**StatPauseTimePortion [SimTalk]**

Returns the portion of the statistics collection period during which the MU instance designated by &lt;MUPath&gt; was located on a paused or an unplanned object.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatPauseTimePortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatPauseTimePortion StatProdFailPortion [SimTalk] - MUs Returns the time portion during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdfailPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatProdfailPortion
```

SimTalk

StatProdFailTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatProdFailTime [SimTalk]

StatProdFailTime [SimTalk]

Returns the time during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdFailTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatProdFailTime
```

SimTalk

StatProdFailPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatProdPausingPortion [SimTalk] - MUs Returns the time portion during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was paused or unplanned .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdPausingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdPausingPortion

SimTalk

StatProdPausingTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatProdPausingTime [SimTalk]

Returns the time during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was paused or unplanned .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdPausingTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdPausingTime

SimTalk

StatProdPausingPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatProdSetupPortion [SimTalk] - MUs Returns the time portion of the statistics collection period during which a material flow object of type Production was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdSetupPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdSetupPortion

SimTalk

StatProdSetupTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatProdSetupTime [SimTalk]

StatProdSetupTime [SimTalk]

Returns the time of the statistics collection period during which a material flow object of type Production was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdSetupTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdSetupTime

SimTalk

StatProdSetupPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatProdStoppedPortion [SimTalk] - MUs Returns the time portion during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was stopped .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdStoppedPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdStoppedPortion

SimTalk

StatProdStoppedTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatProdStoppedTime [SimTalk]

Returns the time during which the MU instance designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was stopped .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdStoppedTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdStoppedTime

SimTalk

StatProdStoppedPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects

###### StatProductionTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Production .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProductionTimePortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProductionTimePortion

See also

Tab Product Statistics [MUs]

StatProdWaitingPortion [SimTalk] - MUs

Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was waiting .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdWaitingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdWaitingPortion

SimTalk

StatProdWaitingTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatProdWaitingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Production that was waiting .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatProdWaitingTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdWaitingTime

SimTalk

StatProdWaitingPortion [SimTalk] - MUs

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects StatProdWorkingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Production and was being processed .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdWorkingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdWorkingPortion

SimTalk

StatProdWorkingTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatProdWorkingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Production and was being processed .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatProdWorkingTime → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatProdWorkingTime

SimTalk

StatProdWorkingPortion [SimTalk] - MUs

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects StatRelativeOccupation [SimTalk] - MUs Returns the time during which the MU designated by &lt;MU-Path&gt; was occupied, in relation to its capacity, and not paused or failed divided by the statistics collection period.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatRelativeOccupation → real

Return Value

The return value has the data type real .

Example

print @.StatRelativeOccupation StatRelativeOccupationIR [SimTalk] - MUs Returns the relative, i.e., capacity-based, occupancy with interruptions, i.e., with pauses , unplanned times and failures , of the MU designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatRelativeOccupationIR → real

Return Value

The return value has the data type real .

Example

print @.StatRelativeOccupationIR

###### StatSetUpTimePortion [SimTalk]

StatSetUpTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU designated by &lt;MU-Path&gt; was set up.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatSetUpTimePortion → real
```

Return Value

The return value has the data type real .

Example

print Station.Cont.StatSetUpTimePortion

See also

Tab Product Statistics [MUs]

###### StatStorageTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU designated by &lt;MU-Path&gt; was located on an object of resource type Storage .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStorageTimePortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStorageTimePortion
```

See also

Resource Type of the material flow objects

Tab Product Statistics [MUs] of the Part StatStoreFailPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreFailPortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreFailPortion

SimTalk

StatStoreFailTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatStoreFailTime [SimTalk]

Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreFailTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStoreFailTime
```

SimTalk

StatStoreFailPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatStorePausingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was paused or unplanned .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatStorePausingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStorePausingPortion

SimTalk

StatStorePausingTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatStorePausingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was paused or unplanned .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStorePausingTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStorePausingTime
```

SimTalk

StatStorePausingPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatStoreSetupPortion [SimTalk] - MUs Returns the time portion during which a material flow object of type Storage was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatStoreSetupPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreSetupPortion

SimTalk

StatStoreSetupTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatStoreSetupTime [SimTalk]

Returns the time during which a material flow object of type Storage was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreSetupTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreSetupTime

SimTalk

StatStoreSetupPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatStoreStoppedPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was stopped .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreStoppedPortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreStoppedPortion

SimTalk

StatStoreStoppedTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatStoreStoppedTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was stopped .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreStoppedTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStoreStoppedTime
```

SimTalk

StatStoreStoppedPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatStoreWaitingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was waiting .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatStoreWaitingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreWaitingPortion

SimTalk

StatStoreStoppedTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatStoreWaitingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was waiting .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreWaitingTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStoreWaitingTime
```

SimTalk

StatStoreStoppedTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects StatStoreWorkingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was processing parts.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatStoreWorkingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatStoreWorkingPortion

SimTalk

StatStoreWaitingTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatStoreWorkingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Storage that was processing parts.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatStoreWorkingTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatStoreWorkingTime
```

SimTalk

StatStoreWaitingPortion [SimTalk] - MUs

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects StatTranspFailPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspFailPortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspFailPortion

SimTalk

StatTranspFailTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatTranspFailTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was failed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspFailTime → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTranspFailTime
```

SimTalk

StatTranspFailPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatTransportTimePortion [SimTalk]

Returns the portion of the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport of the statistics collection period.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTransportTimePortion → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTransportTimePortion

SimTalk

Resource Type of the material flow objects

See also

Tab Product Statistics [MUs]

StatTranspPausingPortion [SimTalk] - MUs

Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was paused or unplanned .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspPausingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspPausingPortion

SimTalk

StatTranspPausingTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatTranspPausingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was paused or unplanned .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspPausingTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspPausingTime

SimTalk

StatTranspPausingPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatTranspSetupPortion [SimTalk] - MUs Returns the time portion during which a resource of type Transport was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspSetupPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspSetupPortion

SimTalk

StatTranspSetupTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatTranspSetupTime [SimTalk]

StatTranspSetupTime [SimTalk]

Returns the time during which a resource of type Transport was setting-up for the MU class designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspSetupTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspSetupTime

SimTalk

StatTranspSetupPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects StatTranspStoppedPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was stopped .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspStoppedPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspStoppedPortion

SimTalk

StatTranspStoppedTime [SimTalk]

See also

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs

###### StatTranspStoppedTime [SimTalk]

StatTranspStoppedTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was stopped .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspStoppedTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspStoppedTime

SimTalk

StatTranspStoppedTime [SimTalk]

See also

Resource Type of the material flow objects StatTranspWaitingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was waiting .

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspWaitingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspWaitingPortion

SimTalk

StatTranspWaitingTime [SimTalk]

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatTranspWaitingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was waiting .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTranspWaitingTime → real
```

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspWaitingTime

SimTalk

StatTranspWaitingPortion [SimTalk] - MUs

See also

Tab Product Statistics [MUs]

Resource Type of the material flow objects StatTranspWorkingPortion [SimTalk] - MUs Returns the time portion during which the MU designated by &lt;MU-Path&gt; during which was located on a material flow object of type Transport that was processing parts.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspWorkingPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspWorkingPortion

SimTalk

StatTranspWorkingTime [SimTalk]

See also

Resource Type of the material flow objects

Tab Product Statistics [MUs]

Statistics report , Mean Time Portions of a MU Class of the Mean Life Time

Statistics report , Statistics of the Individual MUs StatTranspWorkingTime [SimTalk]

StatTranspWorkingTime [SimTalk]

Returns the time during which the MU designated by &lt;MU-Path&gt; was located on a material flow object of type Transport that was processing parts.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatTranspWorkingTime → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatTranspWorkingTime

SimTalk

StatTranspWorkingPortion [SimTalk] - MUs

See also

Resource Type of the material flow objects

Tab Product Statistics [MUs]

###### StatWaitTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU designated by &lt;MU-Path&gt; was waiting .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatWaitTimePortion → real
```

Return Value

The return value has the data type real .

Example

print ParallelStation.MU(1).StatWaitTimePortion

###### StatWorkTimePortion [SimTalk]

Returns the portion of the statistics collection period during which the MU designated by &lt;MU-Path&gt; was processed .

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatWorkTimePortion → real
```

Return Value

The return value has the data type real .

Example

print @.StatWorkTimePortion

