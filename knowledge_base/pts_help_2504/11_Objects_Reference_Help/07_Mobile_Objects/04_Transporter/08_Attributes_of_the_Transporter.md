#### Attributes of the Transporter

\_Attributes of the Transporter

The Transporter provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of All MUs .
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

**Note**

The window Show Attributes and Methods , which you can open by pressing the F8 key, only shows the attributes and methods pertaining to the selected type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space Track , not those pertaining to the loading space Store or Line .

**Note**

If the Transporter has derived objects or transports other parts, you cannot change any of the attributes pertaining to the loading space in its class with SimTalk commands.

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
.MUs.Transporter.BatBasicCons := 0.25
print .MUs.MyTransporter.BatBasicCons
posit := Station.Cont.XPos
```

<!-- image -->

##### Acceleration [SimTalk] - Transporter

Sets the Acceleration with which the Transporter designated by &lt;MU-Path&gt; increases its speed on the Track/TwoLaneTrack.

Type

Attribute

Syntax

&lt;MUPath &gt;.Acceleration:acceleration

Assignment Value

You can assign a value of data type acceleration .

You can specify any real number greater than or equal to 0 .

**Note**

In SimTalk 2.0 you can specify the acceleration units mps² , cm² , fps² , and LU/s² .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

To create the ² symbol, activate the Num Lock key on the numeric keypad, hold down Alt and type in 0178 on the numeric keypad.

To create the ² symbol on the German keyboard layout , hold down Alt Gr and press the key with the number 2 . If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

**Example**

.MUs.MyTransporter.Acceleration := 3.1mps2

**See also**

Acceleration [text box] - Transporter AccelerationEnabled [SimTalk] - Transporter Activates ( true ) or deactivates ( false ) acceleration for the Transporter designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.AccelerationEnabled:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.MyTransporter.AccelerationEnabled := true
```

See also

Acceleration [check box] - Transporter

##### Accumulating [SimTalk] - Transporter

Sets if succeeding MUs may move up on the loading space of type Line of the Transporter designated by &lt;MU-Path&gt;&gt; if the first MU cannot exit true .

Remarks

In that case the front of the succeeding MU touches the rear of the preceding MU . Assign false so that the MUs retain their distance to each other.

Type

Attribute

Syntax

```simtalk
<MUPath >.Accumulating:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.Accumulating := true
```

See also

Accumulating [check box] - Transporter

##### AutomaticRouting [SimTalk] - Transporter

Activates ( true ) or deactivates ( false ) Automatic Routing of the Transporter designated by &lt;MU-Path&gt;.

Remarks

When searching for the shortest route, Plant Simulation uses all Connectors between the current location of the Transporter and its destination object.

- For Transporters driving on Tracks/TwoLaneTracks connected with Connectors to other simulation objects this applies:

Except for the destination object, the route consists of objects of type Track/TwoLaneTrack , which are connected with Connectors . The route can also cover Sub-Frames or surrounding Frames , as long as the Tracks/TwoLaneTracks are connected with Connectors via objects of type Interface .

- For Transporters which drive freely within the simulation model this applies:

Except for the destination object, the route consists of objects of type Track/TwoLaneTrack or Marker , which are connected with Connectors . The route can also cover Sub-Frames or surrounding Frames , as long as the Tracks/TwoLaneTracks/Markers are connected with Connectors via objects of type Interface .

**Note**

For tugger trains automatic routing only works when you type the Destination into the tractor .

Type

Attribute

Syntax

```simtalk
<MUPath >.AutomaticRouting:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.MyTransporter.AutomaticRouting := true
```

SimTalk

RouteWeightingAttr [SimTalk] - Transporter

**See also**

**Automatic Routing [Transporter]**

**Backwards [SimTalk] - Transporter**

##### Backwards [SimTalk] - Transporter

Makes the Transporter designated by &lt;MU-Path&gt; and the MUs on it drive in reverse on the Track/ TwoLaneTrack ( true ) or not ( false ).

Remarks

When the Transporter drives in reverse from a Track/TwoLaneTrack onto a Track/TwoLaneTrack , it enters the Track/TwoLaneTrack at its exit and leaves it at its entrance.

**Note**

This only applies when the Transporter drives from a Track/TwoLaneTrack to a Track/TwoLaneTrack , but not from a point-oriented object onto a Track/TwoLaneTrack .

Driving forward or in reverse are properties of the Transporter , not of the Track/TwoLaneTrack !

If you cleared Acceleration of the Transporter , it reverses the direction into which it drives immediately without decelerating and accelerating.

If you selected Acceleration , the Transporter slows down until its speed is 0 m/s. Then it reverses the direction into which it drives and accelerates until it reaches its final speed.

Type

Attribute

Syntax

```simtalk
<MUPath >.Backwards:boolean
```

Assignment Value

You can assign a value of data type boolean .

**Examples**

```simtalk
if @.empty
	@.backwards := true
else
waituntil SP2.empty prio 1
@.Cont.move(SP2)
@.backwards := true
end
.MUs.MyTransporter.Backwards := true
```

**SimTalk**

AccelerationEnabled [SimTalk] - Transporter

See also

Backwards [Transporter]

Backwards [check box] - loading space

Acceleration [check box] - Transporter

##### BatBasicCons [SimTalk]

BatBasicCons [SimTalk]

Sets the Basic Consumption that comes off the battery of the Transporter designated by &lt;MU-Path&gt;.

Remarks

This applies as long as the Transporter is running on battery power.

The battery charge is independent of failures and/or pauses . The Basic Consumption also applies while charging the battery!

Type

Attribute

Syntax

&lt;MUPath &gt;.BatBasicCons:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.MyTransporter.BatBasicCons :=0.25 // consumption = 250ma
```

See also

Statistics report , Battery [statistics]

Basic Consumption

##### BatCapacity [SimTalk]

Sets the maximum charge Capacity of the battery of the Transporter designated by &lt;MU-Path&gt;.

Remarks

The charge cannot exceed this value.

Type

Attribute

Syntax

&lt;MUPath &gt;.BatCapacity:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.MyTransporter.BatCapacity := 10 // 10ah
```

See also

Statistics report , Battery [statistics]

Capacity [text box] - battery

##### BatCharge [SimTalk]

BatCharge [SimTalk]

Sets the active Battery Charge of the Transporter designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.BatCharge:real
```

Assignment Value

You can assign a value of data type real .

Specify a value between 0 (empty) and the capacity of the battery .

The unit is ampere hours (Ah).

Example

```simtalk
// This method controls the battery charge of a Transporter.
if @.BatteryUsed and (@.BatCharge = @.BatReserve)
	print "Attention: Charge on reserve"
	print "Driving to charge bay."
	@.Destination := .building3.charge_bay
end
```

SimTalk

BatCapacity [SimTalk]

See also

Charge

##### BatChargeCtrl [SimTalk]

Designates an object of type Method of the object designated by &lt;MU-Path&gt;, when the specified battery charge of the Transporter dropped to the reserve charge.

Remarks

Plant Simulation also runs the control if the charge drops to 0 or reaches the capacity of the battery.

Type

Attribute

Syntax

```simtalk
<MUPath >.BatChargeCtrl:object
```

**Assignment Value**

You can assign a value of data type object .

**Examples**

```simtalk
// A sample charge control for a Transporter could look like this:
var charge: real charge := ?.BatCharge
if round(charge - ?.BatCapacity) = 0
	?.BatCharging := false // stops charging
elseif charge= ?.BatReserve
	?.BatCharging := true // starts charging
end
.MUs.MyTransporter.BatChargeCtrl := &myBatteryChargeCtrl
```

SimTalk

BatCharge [SimTalk]

BatReserve [SimTalk]

BatCapacity [SimTalk]

See also

Charge Control

**BatChargeCtrl [SimTalk]**

##### BatChargeCurrent [SimTalk]

Sets the Charge Current of the battery of the Transporter designated by &lt;MU-Path&gt; that is activated or deactivated by the attribute BatCharging .

Remarks

The battery charge is independent of failures and/or pauses . The Basic Consumption also applies while charging the battery!

Type

Attribute

Syntax

&lt;MUPath &gt;.BatChargeCurrent:real

Assignment Value

You can assign a value of data type real .

Example

.MUs.MyTransporter.BatChargeCurrent := 1.0 // Ampere

SimTalk

BatCharging [SimTalk]

See also

Statistics report , Battery [statistics]

Charge Current

##### BatCharging [SimTalk]

BatCharging [SimTalk]

Sets if the battery of the Transporter designated by &lt;MU-Path&gt; will be recharged ( true ) or not ( false ).

Remarks

Failures or pauses do not affect charging the battery.

Type

Attribute

Syntax

&lt;MUPath &gt;.BatCharging:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Station.Cont.BatCharging :=true // starts charging
```

##### BatDriveCons [SimTalk]

Sets the Driving Consumption of the Transporter designated by &lt;MU-Path&gt; when it is moving under battery power.

Type

Attribute

Syntax

&lt;MUPath &gt;.BatDriveCons:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.MyTransporter.batDriveCons := 1.75 // 1.75 Ah
```

See also

Statistics report , Battery [statistics]

Driving Consumption

##### BatReserve [SimTalk]

BatReserve [SimTalk]

Sets the Reserve Charge of the battery of the Transporter designated by &lt;MU-Path&gt;.

Remarks

When the battery charge drops below the value you enter for the reserve charge, the Transporter calls the battery charge control that may initiate recharging the battery.

Type

Attribute

Syntax

```simtalk
<MUPath >.BatReserve:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
// set reserve to 20 % of capacity
@.BatReserve := 0.2 * @.BatCapacity
```

SimTalk

BatChargeCtrl [SimTalk]

Charge Control

See also

Reserve , text box

##### BatteryUsed [SimTalk]

Makes the Transporter designated by &lt;MU-Path&gt; drive under Battery Power ( true ) or not ( false ).

Remarks

Operating under battery power is deactivated by default.

Type

Attribute

Syntax

&lt;MUPath &gt;.BatteryUsed:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.BatteryUsed := true
```

See also

Battery [check box]

BwEntranceCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation runs the Method as soon as a MU enters the loading space of type Line/Track of the Transporter designated by &lt;MU-Path&gt; via its exit and/or if the part moves toward its entrance after entering.

Type

Attribute

Syntax

<MUPath >.BwEntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
.MUs.Transporter:3.LoadBayType := "Track" .MUs.Transporter:3.BwEntranceCtrl := &myBackwardEntranceCtrl
```

See also

Backward Entrance Control

Controls [loading space]

##### BwEntranceCtrlFront [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; activates the Backward Entrance Control when the front of the MU enters the loading space of type Line/Track via its exit and/or if the part moves toward the entrance of the loading space after entering ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.BwEntranceCtrlFront:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.MUs.Transporter:3.LoadBayType := "Track" .MUs.Transporter:3.BwEntranceCtrlFront := false
```

See also

**Controls [loading space]**

Backward Entrance Control BwEntranceCtrlRear [SimTalk] - Transporter Sets if the Transporter designated by &lt;MU-Path&gt; activates the Backward Entrance Control when the rear of the MU enters the loading space of type Line/Track via its exit and/or if the part moves toward the entrance of the loading space after entering ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.BwEntranceCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:3.LoadBayType := "Track" .MUs.Transporter:3.BwEntranceCtrlFront := false
```

See also

Controls [loading space]

Backward Entrance Control

##### BwExitCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;, which is called as soon as a MU exits the loading space of type Line/Track of the Transporter via its entrance and/or if the MU moves toward the entrance of the loading space when exiting.

Type

Attribute

Syntax

<MUPath >.BwExitCtrl

Assignment Value

You can assign a value of data type method .

**Example**

```simtalk
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrl := &myBackwardExitCtrl
```

See also

Controls [loading space]

Backward Exit Control

##### BwExitCtrlFront [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; activates the exit control when the front of the MU exits the loading space of type Line/Track via its entrance.

Remarks

BwExitCtrlFront also applies if the part moves toward the entrance of the loading space when exiting ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.BwExitCtrlFront:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrlFront := false
```

See also

Controls [loading space]

Backward Exit Control

##### BwExitCtrlRear [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; activates the Exit Control when the rear of the MU exits the loading space of type Line/Track via its entrance.

Remarks

BwExitCtrlRear also applies if the part moves toward the entrance of the loading space when exiting ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
<MUPath >.BwExitCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:4.LoadBayType := "Line" .MUs.Transporter:4.BwExitCtrlRear := false
```

See also

Controls [loading space]

Backward Exit Control Capacity [SimTalk] - Transporter Sets the Capacity , i.e., the number of MUs or MU parts that may be located on the loading space of type Line/Track of the Transporter designated by &lt;MU-Path&gt; as a whole or in part at any one time.

Remarks

When the number you specified as the Capacity is reached, the Conveyor does not accept any additional MUs , even if its full length is not exhausted.

Type

Attribute

Syntax

```simtalk
<MUPath >.Capacity:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite capacity.

Example

```simtalk
.MUs.Transporter:3.LoadBayType := "Line" .MUs.Transporter:3.Capacity := 15
```

See also

Capacity [text box] - Transporter

##### CollisionCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;, which is called when the Transporter collides with a slower one, i.e., the following Transporter drives faster than the one driving ahead of it and the distance between them is 0.

Remarks

The Collision Control only applies to Transporters that drive on Tracks or TwoLaneTracks .

Type

Attribute

Syntax

<MUPath >.CollisionCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
if .MUs.MyTransporter.CollisionCtrl = VOID .MUs.MyTransporter.CollisionCtrl := &myCollisionCtrl
end
// @ is the transporter which Collided //
@.frontmu references the transporter in front // hitch the current transporter to the transporter driving in front of it var rear, front: object
var TractorSpeed : real rear := @
front := @.FrontMU
if front.IstZugmaschine
	TractorSpeed := front.Speed
	rear.hitchFront(front)
	front.Speed  := TractorSpeed
else
	rear.hitchFront(front)
end
-- collision control for all trailers
var rear:object  := @
var front:object := @.frontMU
```

if front.isTractor rear.hitchfront else rear.hitchfront end

**SimTalk**

**Collided [SimTalk]**

See also

Collision Control [Transporter]

##### CurrentSpeed [SimTalk] - Transporter

Sets the Current Speed with which the Transporter designated by &lt;MU-Path&gt; drives on the Track/ TwoLaneTrack forward (positive number) or in reverse (negative number).

Remarks

Setting the Current Speed only works if Acceleration is active.

Type

Attribute

Syntax

&lt;MUPath &gt;.CurrentSpeed:speed

Watchable

The attribute is watchable .

**Note**

Although this value can continually change because the Transporter is accelerating, CurrentSpeed is watchable for certain values. By observing this value you might, for example, recognize when the speed of the Transporter changes, because it collided with the Transporter in front of it, because it stops at the end of a Track/TwoLaneTrack , or because of other outside influences.

An observer of the attribute CurrentSpeed does not wake up if a Transporter driving without acceleration collides with a decelerating/accelerating Transporter and the CurrentSpeed does not change immediately during this action, but the collided Transporter is forced to a continuous speed change by the preceding Transporter . The observer only wakes up, when the final speed of the preceding Transporter is reached.

**Note**

When an AGV with active Acceleration completes a rotation on the spot, it just starts accelerating, and the value of CurrentSpeed is still 0 at that time. After that, the CurrentSpeed increases continuously. An observer of CurrentSpeed like waituntil will not be triggered until the AGV reaches its Final Speed .

Use an observer of CurrentAcceleration to be notified about the end of the rotation, when the AGV starts accelerating again:

```simtalk
waituntil (@.CurrentAcceleration > 0) prio 1
```

if @.CurrentSpeed = 0 end

**Assignment Value**

You can assign a value of data type speed .

You can specify any real number.

**Examples**

```simtalk
.MUs.MyTransporter.CurrentSpeed := 3.6
var vehicle: object
vehicle := MyTrack.MU(1)
waituntil vehicle.CurrentSpeed = 0 prio 1
print "Stopped at this time:", EventController.simTime
```

**See also**

**Current Speed [text box] - Transporter**

##### CurveSpeed [SimTalk]

Sets the speed with which the Transporter designated by &lt;MU-Path&gt; drives through curves on the route to its destination.

Remarks

Specify a real number greater than 0.

The default value -1 designates that the curve speed is not active. The Transporter drives through curves on the route with its normal Speed . This also applies if the Curve Speed is higher than the normal Speed .

The Transporter decelerates in time so that it reaches the specified Curve Speed at the start of the curve and then accelerates again after it has passed the curve.

**Note**

This applies to Transporters driving freely within the area of the model as well as to Transporters driving on Tracks .

**Note**

The Transporter does not maintain the Curve Speed on a lane of a TwoLaneTrack .

Only the tractor of a tugger train maintains the Curve Speed , not the trailers.

**Note**

A Transporter driving on Tracks can only slow down in time to meet the Curve Speed if it either has a route to a destination or if each Track only has a single successor.

If the route network contains intersections, the Transporter can only start slowing down to the Curve Speed if it drove onto the succeeding Track at an intersection.

Type

Attribute

Syntax

&lt;MUPath &gt;.CurveSpeed:speed

**Assignment Value**

You can assign a value of data type speed .

**CurveSpeed [SimTalk]**

You can specify any real number.

**Example**

```simtalk
.MUs.MyTransporter.CurveSpeed := 0.5
```

See also

Curve Speed [text box]

setRoute [SimTalk] - Transporter Deceleration [SimTalk] - Transporter Sets the Deceleration of the Transporter designated by &lt;MU-Path&gt; on the Track .

Type

Attribute

Syntax

<MUPath >.Deceleration:acceleration

Assignment Value

You can assign a value of data type acceleration . You can enter any real number greater than or equal to 0.

Example

```simtalk
.MUs.Transporter.Deceleration := 2
```

SimTalk

calcBrakingDistance [SimTalk] - general description

See also

Deceleration [text box] - Transporter

##### DefaultCurveRadius [SimTalk]

Sets the Default Curve Radius with which the freely driving Transporter designated by &lt;MU-Path&gt; approaches the Markers .

Remarks

Plant Simulation uses this value for computing the route of the AGV that drives freely within the area. The Default Curve Radius sets the size of the curvature/fillet at the Markers .

The AGV passes the Marker on a curve segment with the specified Default Curve Radius . The AGV calls the Arrival Control of the Marker at the point of the curve segment at which it is closest to the Marker .

The distance of the Marker should be at least twice the Default Curve Radius at coordinates where the AGV needs to change its direction.

**Note**

You cannot change the DefaultCurveRadius if the Transporter is already driving on a route.

If a stationary Transporter cannot drive to the first Marker using the specified DefaultCurveRadius , the Transporter rotates on the spot, if possible, and then drives in a straight line toward the next Marker .

Once the AGV arrives at the waypoint of the route, it decelerates to 0, rotates on the spot with the specified Rotation Speed , and accelerates again afterwards.

To make the AGV rotate on the spot with the Rotation Speed you set, enter 0 as the Default Curve Radius .

**Note**

In previous versions the AGV did not use the Rotation Speed when rotating on the spot with a Default Curve Radius of 0.

To use the behavior of previous versions, enter -1 as the Rotation Speed for the respective AGVs .

**Note**

To rotate on the spot the AGV needs to decelerate to the Speed 0. When you assign a new route to an AGV with activated Acceleration while the AGV is currently driving, this might in some cases cause the AGV to first decelerate to 0, then turn, and finally drive back to the start of the new route.

Type

Attribute

**Syntax**

<MUPath >.DefaultCurveRadius:length

Assignment Value

You can assign a value of data type length .

**Examples**

```simtalk
.MUs.Transporter.DefaultCurveRadius := 1.1 .MUs.Transporter.RotationSpeed := 2 -- Transporter drives in a curve, does not use rotation speed
.MUs.Transporter.DefaultCurveRadius := 0 .MUs.Transporter.RotationSpeed := 2 -- Transporter rotates on the spot, uses rotation speed
```

**SimTalk**

setRoute [SimTalk] - Transporter

See also

Default Curve Radius [text box]

Speed [Transporter]

Rotation Speed [text box]

Marker

**DestCtrl [SimTalk]**

##### DestCtrl [SimTalk]

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation runs the Method after the Transporter has moved onto and covered the object, which you specified as the Destination Object and arrives at the Exit of the Destination .

When you specify an Exit Control for the Destination , the Transporter does not activate the Destination Control .

When you specifeded a front-triggered Exit Control into the Destination Object , this does not activate the Destination Control .

After setting the destination in the Destination Control , you have to make the Transporter drive on by moving it with the method move .

Plant Simulation also runs the Destination Control if you used TargetDistance or TargetPosition , and the Transporter has covered the distance.

If you are working with automated guided transport systems , the Destination Control is called when the Transporter has reached the end of the route, which you set with the method setRoute , rotate , drive , or setRouteSegments .

Type

Attribute

Syntax

<MUPath >.DestCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
@.DestCtrl := &myDestinationCtrl  // enter
@.DestCtrl := VOID                // and delete again
```

SimTalk

DestinationWasReached [SimTalk]

setRoute [SimTalk] - Transporter setRouteSegments [SimTalk] move [SimTalk] - MUs rotate [SimTalk] - Transporter drive [SimTalk] TargetDistance [SimTalk] TargetPosition [SimTalk] See also Destination Control Destination [SimTalk] - Transporter

Marker , object Destination [SimTalk] - Transporter Sets the Destination Object to which the Transporter designated by &lt;MU-Path&gt; drives.

Remarks

The destination applies:

- For a Transporter that drives on Tracks if you did not specify in an Exit Control or a Driving Control .

Plant Simulation checks the DestLists of the successors and moves the Transporters to the object whose list contains the Destination . If automatic routing is active, you do not have to define destination lists.

If the destination is a TwoLaneTrack , you can also select the Destination Lane , A or B .

**Note**

For tugger trains automatic routing only works when you specify the Destination in the tractor .

- the freely driving Transporter designated by &lt;MU-Path&gt; drives.

You can also specify a table or a list as the Destination . This list or table can be a DataList , a DataQueue , a DataStack , or a DataTable which you inserted into a Frame . It can also be a user-defined attribute or a Variable of data type table , list , queue , or stack . The list or table has to have the column type object . The Transporter then covers all destination objects in the list or table one after the other.

- DataTable ( table ): Plant Simulation cyclically processes the first column of the DataTable . The Transporter always heads for the destination object which is located on the table row to which the attribute DestinationListRow of the Transporter points.

**Note**

In most cases the DataTable will only have a single column. You can type any data into additional columns though.

- DataList ( list ): Plant Simulation treats the DataList as a DataTable with one column.
- DataQueue or DataStack ( queue or stack ): The Transporter always drives to the first object in the DataQueue or the DataStack . As soon as the destination is reached, Plant Simulation removes the first object from the list. The Transporter then drives to the new first object in the list.

**Note**

Once the Transporter has reached its destination, it immediately picks the next destination from the list or table.

If the destination was a sensor, Plant Simulation already determines the next destination before the Sensor Control is called. To set the immediate next destination in the control, it does not suffice to change the list or table respectively, but you also have to reassign the attribute Destination of the Transporter afterwards.

Type

Attribute

Syntax

<MUPath >.Destination:path

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type path .

Example

```simtalk
@.Destination := .building13.buffer4 // enter
@.Destination := VOID                // and delete again
@.Destination := TwoLaneTrack.A
```

SimTalk

DestinationListRow [SimTalk]

Control [SimTalk] - sensors

StopAtDestination [SimTalk]

See also

Destination [text box] - Transporter

Control [SimTalk] - sensors

**Distance [SimTalk]**

##### Distance [SimTalk]

Sets the Distance from which on the Transporter designated by &lt;MU-Path&gt; calls the Distance Control .

Remarks

The distance prevents the MUs from getting too close to each other or from moving away too far from each other. You can specify a value greater than 0.

Type

Attribute

Syntax

<MUPath >.Distance:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
.MUs.MyTransporter.Distance := 1.5
```

SimTalk

Distance Control

See also

Distance [text box] - distance control

##### DistanceCtrl [SimTalk]

Designates a Method object of the object designated by &lt;MU-Path&gt;.

**Remarks**

Plant Simulation executes the Distance Control :

- If the Transporter , for which you entered the Distance Control , is not an AGV , Plant Simulation executes the control when it gets closes any other part than the Distance which you entered. Plant Simulation calls the control when the distance becomes either too small or too great.
- If the Transporter is an AGV , it executes the control you entered when another AGV enters or exits one of its safety zones.

The standard distance control as a user-defined attribute looks like this:

<!-- image -->

**DistanceCtrl [SimTalk]**

Type

Attribute

Syntax

<MUPath >.DistanceCtrl:method

**Parameters**

If the Transporter is not an AGV , the parameter DistanceObjectBelowLimit is true when the distance becomes too small. It is false when the distance becomes too great.

If the Transporter is an AGV , use the alternative parameter set.

- The parameter IsInZone of data type boolean is true when another AGV enters one of the safety zones. It is false when the AGV exits the safety zone again.
- The parameter ZoneNumber of data type integer has the value 1 for safety zone 1 and the value 2 for safety zone 2.

It has the value 0 if the Transporter is not an AGV .

The anonymous identifier ? designates the part ( MU ) for which you entered the Distance Control and the Distance or the safety zones. The anonymous identifier @ designates the part ( MU ) for which the distance became too great or too small or which entered or exited a safety zone. At the point in time at which the Distance Control is called @ is located in front of ? in the direction of motion of ? or it is located in one of the safety zone of ? in the direction of motion of ? .

For tugger trains you have to enter the control into the tractor. If a tugger train falls below the Distance you entered, the Distance Control of the tractor will be triggered. Within the control method the anonymous identifier @ is the MU to which the distance is too small, while the anonymous identifier ? designates the tractor of the train.

**Assignment Value**

You can assign a value of data type method .

**Examples**

```simtalk
if .MUs.MyTransporter.DistanceCtrl = VOID .MUs.MyTransporter.DistanceCtrl := &myDistanceCtrl
end
```

// ? designates the transporter with the control // @ designates the calling transporter, which falls short of

```simtalk
// or exceeds the distance
param distanceIsBelowLimit: boolean
if distanceIsBelowLimit
	?.Speed := @.Speed        // adapt speed of transporter in front
else
	?.speed := ?.Origin.Speed // switch back to original speed
end
-- ? transporter with the control -- @ the inducing transporters, which are below or above the distance
param distanceIsBelowLimit : boolean
var behindVeh:object := ?
var aheadVeh:object  := @
if distanceIsBelowLimit
	behindVeh.speed := aheadVeh.speed * 0.7
	behindVeh.distance := 10
	print "decelerate"
else
	print "accelerate"
	behindVeh.speed := aheadVeh.speed * 1.2
	behindVeh.distance := 5
end
```

**See also**

Distance [text box] - distance control

AGV [text box]

Distance Control

Work with a Distance Control without AGVPool

**DriveCtrl [SimTalk]**

##### DriveCtrl [SimTalk]

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

In the Method you set to which successor the Transporter moves, when a Track has no Exit Controls , but more than one successor.

Note An Exit control overrides the DriveCtrl .

Type

Attribute

Syntax

<MUPath >.DriveCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
// At an intersection two Tracks of different length are available. // If the shorter Track is failed, the Transporter selects the // alternative route. var loc, shortTrack, longTrack, Destination : object
loc := @.location // which successor has shortest the track?
if loc.succ(1).Length = loc.succ(2).Length
	shortTrack := loc.succ(1)  // shorter track
	longTrack := loc.succ(2)   // longer track
else // exchange
	shortTrack := loc.succ(2)  // shorter track
	longTrack := loc.succ(1)   // longer track
end
if shortTrack.failed
	@.move(longTrack)
else
	@.move(shortTrack)
end
.MUs.MyTransporter.DriveCtrl := &myDriveCtrl
```

**See also**

**Driving Control**

**DrivingHome [SimTalk]**

##### DrivingHome [SimTalk]

Sets if the Transporter designated by &lt;MU-Path&gt; drives back to its home base ( true ) or not ( false ).

Remarks

The attributes DrivingHome and HasOrder change the state of the Transporter . Both attributes are important for statistics collection only.

**Note**

Plant Simulation does not automatically set the attribute DrivingHome to true when a Transporter reaches its destination, the Transporter remains in the current state! You have to explicitly set the state.

As soon as DrivingHome is set to true , the Transporter sets HasOrder to false and vice versa.

Type

Attribute

Syntax

```simtalk
<MUPath >.DrivingHome:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTransporter.DrivingHome
MyTransporter.DrivingHome := true
```

SimTalk

HasOrder [SimTalk] - Transporter

##### EntranceCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;.

**Remarks**

Plant Simulation runs the Method as soon as a MU enters the loading space of the Transporter .

If you did not enter a method , the attribute EntranceCtrl returns the value VOID.

All types of the loading space provide the Entrance Control .

<!-- image -->

**Assignment Value**

You can assign a value of data type method .

**Note**

As the MU is already located on the object when the entrance control is called, set-up and processing times for this MU cannot be changed any more. You can set the set-up and processing time with a formula.

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Store" .MUs.Transporter:1.EntranceCtrl := &MyEntranceControl
```

**See also**

Controls [loading space] &gt; Entrance Control [general description]

##### EntranceCtrlFront [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; triggers the Entrance Control as soon as the front of the MU enters the loading space of type Track or Line ( true ) or not ( false ).

**Remarks**

<!-- image -->

Type

Attribute

Syntax

&lt;MUPath &gt;.EntranceCtrlFront:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Track" .MUs.Transporter:1.EntranceCtrlFront := true
```

**See also**

Controls [loading space]&gt; Entrance Control &gt; Front

##### EntranceCtrlRear [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; triggers the Entrance Control as soon as the rear of the MU enters the loading space of type Track or Line ( true ) or not ( false ).

**Remarks**

<!-- image -->

Type

Attribute

Syntax

&lt;MUPath &gt;.EntranceCtrlRear:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Track" .MUs.Transporter:1.EntranceCtrlRear := true
```

**See also**

Controls [loading space]&gt; Entrance Control &gt; Rear

##### ExitCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;.

**Remarks**

Plant Simulation runs the Method as soon as a MU exits the loading space of the Transporter . If you did not enter the name of a method , the attribute ExitCtrl returns VOID.

**Note**

The exit control can have an optional parameter of data type object . When the method has this parameter, then the successor object, which pulls the MU because the MU was contained in the Blocking List of the object, will be assigned to this parameter. The MU will be pulled, for example, when the successor becomes available again or when its entrance is opened.

All types of the loading space provide the Exit Control .

<!-- image -->

Type

Attribute

**Syntax**

```simtalk
<MUPath >.ExitCtrl:boolean
```

Assignment Value

You can assign a value of data type method .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Store" .MUs.Transporter:1.ExitCtrl := &MyExitControl
```

See also

Controls [loading space]

Exit Control [general description]

##### ExitCtrlFront [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; triggers the Exit Control as soon as the front of the MU exits the loading space of type Line/Track ( true ) or not ( false ).

**Remarks**

<!-- image -->

Type

Attribute

Syntax

&lt;MUPath &gt;.ExitCtrlFront:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Track" .MUs.Transporter:1.ExitCtrlFront := false
```

**See also**

Controls [loading space]&gt; Exit Control &gt; Front

Exit Control [general description]

##### ExitCtrlRear [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; triggers the Exit Control as soon as the rear of the MU exits the loading space of type Line/Track ( true ) or not ( false ).

**Remarks**

<!-- image -->

Type

Attribute

Syntax

&lt;MUPath &gt;.ExitCtrlRear:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.ExitCtrlRear := false
```

**See also**

Controls [loading space]&gt; Exit Control &gt; Rear

Exit Control [general description]

##### Failed [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; is failed and stops while driving on a Track/TwoLaneTrack ( true ) or not ( false ).

Remarks

After the value has been changed, Plant Simulation executes the Fail Control .

If you manually fail the Transporter , it remains failed while any of the failure profiles you defined is active. It will change to not failed once the last failure ( DisruptionEnd event ) of the last failure profile ends or when you assign false to the attribute.

**Note**

Plant Simulation resets all failures during the reset phase of the simulation run.

Type

Attribute

Syntax

```simtalk
<MUPath >.Failed:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

if MyTrack.Cont.Failed

```simtalk
MyTrack.Cont.Failed := false
end
```

SimTalk

FailCtrl [SimTalk]

**See also Failed [check box] - Transporter DisruptionEnd event**

##### HasOrder [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; has a transport order ( true ) or not ( false ).

Remarks

The attributes DrivingHome and HasOrder change the state of the Transporter . Both attributes are important for statistics collection only.

**Note**

Plant Simulation does not automatically set the attribute HasOrder to true when you assign a destination to the Transporter , the Transporter remains in the current state! You have to explicitly set the state.

As soon as HasOrder is set to true , the Transporter sets DrivingHome to false and vice versa.

Type

Attribute

Syntax

```simtalk
<MUPath >.HasOrder:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
@.HasOrder
Station.Cont.HasOrder := true
```

See also

DrivingHome [SimTalk]

##### InitCtrl [SimTalk] - Transporter

InitCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation runs the Method during the Init phase of the simulation.

In the Init Control you can, for example, initialize the Transporter with suitable values and assign userdefined attributes.

Type

Attribute

Syntax

<MUPath >.InitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
if .MUs.Transporter:1.InitCtrl = VOID .MUs.Transporter:1.InitCtrl := &myTransporterInitCtrl // enter end                                                      // and .MUs.Transporter:1.InitCtrl := VOID                      // delete
```

SimTalk

init [SimTalk] - predefined name

See also

Init Control [Transporter]

IsIdle [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; is idle ( true ) or not ( false ).

Remarks

IsIdle works together with the read-only attribute NumIdleAGVs of the AGVPool . NumIdleAGVs returns the number of Transporters for which the attribute IsIdle returned true.

Newly created Transporters always have the state IsIdle=true .

Type

Attribute

Syntax

```simtalk
<MUPath >.IsIdle:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.IsIdle := true
```

SimTalk

NumIdleAGVs [SimTalk]

getIdleAGV [SimTalk]

See also

Fine-position an AGV

**IsTractor [SimTalk]**

##### IsTractor [SimTalk]

Sets the Transporter designated by &lt;MU-Path&gt; as the tractor of the tugger train which pulls or pushes the trailers ( true ) or not ( false ).

Remarks

The Transporter shows the icon tractor in 2D instead of the icon Operational .

<!-- image -->

<!-- image -->

As a vector graphic the icon of the tractor looks like this .

Note

To prevent the tractor from loading parts, enter 0 as the XDim and the YDim for the Loading Space Type &gt; Store . For the Loading Space Types &gt; Line/Track , enter 0 as the Capacity .

Type

Attribute

Syntax

```simtalk
<MUPath >.IsTractor:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.IsTractor := true
```

SimTalk

GetTractor [SimTalk]

XDim [SimTalk] - Transporter

YDim [SimTalk] - Transporter

See also

Is Tractor [check box]

##### Capacity [SimTalk] - Transporter

**LoadBayAcceleration [SimTalk]**

##### LoadBayAcceleration [SimTalk]

Sets the speed with which the loading space of type Line of the Transporter designated by &lt;MU-Path&gt; accelerates.

Type

Attribute

Syntax

<MUPath >.LoadBayAcceleration:acceleration

Assignment Value

You can assign a value of data type acceleration .

Example

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBayAcceleration := 10
```

See also

Acceleration [text box] - loading space

##### LoadBayAccelerationEnabled [SimTalk]

Activates ( true ) or deactivates ( false ) the acceleration of the loading space of type Line of the Transporter designated by &lt;MU-Path&gt;.

Type

Attribute

Syntax

```simtalk
<MUPath >.LoadBayAccelerationEnabled:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBayAccelerationEnabled := true
```

See also

Acceleration [check box] - loading space

**LoadBayBackwards [SimTalk]**

##### LoadBayBackwards [SimTalk]

Sets if the loading space of type Line of the Transporter designated by &lt;MU-Path&gt; and the MUs on it move in reverse ( true ) or forward ( false ).

Remarks

**Note**

Here moving forward or in reverse are not properties of the Transporter , but of the loading space moving on it!

If you cleared Acceleration of the loading space, it reverses the direction into which it moves immediately without decelerating and accelerating.

If you selected Acceleration , the loading space slows down until its speed is 0. Then it reverses the direction into which it moves and accelerates until it reaches its final speed.

Type

Attribute

Syntax

```simtalk
<MUPath >.LoadBayBackwards:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBayBackwards := true
```

SimTalk

LoadBayAccelerationEnabled [SimTalk]

See also

Backwards [check box] - loading space

Acceleration [check box] - loading space

##### LoadBayCurrentSpeed [SimTalk]

LoadBayCurrentSpeed [SimTalk]

Sets the Current Speed with which the loading space of type Line of the Transporter designated by &lt;MU-Path&gt; drives forward (positive number) or in reverse (negative number).

Remarks

This only works if LoadBayAccelerationEnabled is active.

Type

Attribute

Syntax

<MUPath >.LoadBayCurrentSpeed:speed

Assignment Value

You can assign a value of data type speed . You can enter any real number.

Example

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBayCurrentSpeed := 12
```

SimTalk

LoadBayAccelerationEnabled [SimTalk]

See also

Current Speed [text box] - loading space

##### LoadBayDeceleration [SimTalk]

Sets the deceleration with which the loading space of type Line of the Transporter designated by &lt;MUPath&gt; reduces its speed.

Type

Attribute

Syntax

<MUPath >.LoadBayDeceleration:acceleration

Assignment Value

You can assign a value of data type acceleration .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBayDeceleration := 10
```

See also

Deceleration [text box] - loading space LoadBayLength [SimTalk] - Transporter Sets the Length of the loading space of type Line/Track of the Transporter designated by &lt;MU-Path&gt; in meters.

Type

Attribute

Syntax

<MUPath >.LoadBayLength:length

Assignment Value

You can assign a value of data type length .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadbayLength := 10
```

See also

Length [text box] - loading space

##### LoadBaySpeed [SimTalk] - Transporter

Sets the speed with which the loading space of type Line of the Transporter designated by &lt;MU-Path&gt; moves.

Remarks

When you activate Acceleration , the speed is the same as its final speed.

Type

Attribute

Syntax

<MUPath >.LoadBaySpeed:speed

Assignment Value

You can assign a value of data type speed .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBaySpeed := 10
```

See also

Speed [text box] - Transporter

Acceleration [check box] - Transporter

**LoadBaySpeedCtrl [SimTalk]**

##### LoadBaySpeedCtrl [SimTalk]

Designates a Method object of the object designated by &lt;MU-Path&gt;.

**Remarks**

Plant Simulation runs the Method as soon as the loading space of type Line of the Transporter designated by &lt;MU-Path&gt; reaches its final speed after speeding up or slowing down or when it stops after accelerating or decelerating, i.e., when it has the speed 0. If you did not enter the name of a Method , the attribute is VOID.

**Note**

This only applies when you selected the check box Acceleration .

**Note**

The Speed Control of the loading space of the Transporter provides the same functions as the Speed Control of the object Conveyor .

**Note**

Do not confuse the Speed Control of the loading space of type Line of the Transporter with the Speed Control of the Transporter as such.

Type

Attribute

Syntax

&lt;MU- Path &gt;.LoadBaySpeedCtrl:method

<!-- image -->

**LoadBaySpeedCtrl [SimTalk]**

Assignment Value

You can assign a value of data type method .

**Example**

```simtalk
.MUs.Transporter:1.LoadBayType := "Line" .MUs.Transporter:1.LoadBaySpeedCtrl := &myLoadBaySpeedCtrl
```

**See also**

Controls [loading space]&gt; Speed Control

Speed Control [Conveyor]

Acceleration [check box] - Transporter

##### LoadBayType [SimTalk]

Sets the type of loading space of the Transporter designated by &lt;MU-Path&gt;.

Remarks

The loading space of type

- Store designates a Loading Space consisting of loading places along the X-Dimension , the YDimension , and the Z-Dimension onto which the Transporter places the parts it loads.

The orientation of the MUs depends on the orientation of the animation line in 2D and in 3D.

- Track designates a passive length-oriented loading space on to which the Transporter loads and unloads parts. This is especially handy for modeling a cross-sliding car and other types of materials handling equipment. You can also enter Controls and define sensors .
- In addition, you can select the direction of the animation line . The orientation of the MU depends on the orientation of the animation line in 2D and in 3D.

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

<!-- image -->

- Line designates an active length-oriented loading space similar to a Conveyor being part of the loading space, which transports the loaded parts forward or backward. The CrossSlidingCar makes

extensive use of this type of loading space. In addition, you can select the direction of the animation line . The orientation of the MU depends on the orientation of the animation line in 2D and in 3D.

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

<!-- image -->

**Note**

The window Show Attributes and Methods , which you can open by pressing the F8 key, only shows the attributes and methods pertaining to the selected Type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

**Note**

If the Transporter has derived objects or transports other parts, you cannot change any of the attributes pertaining to the loading space in its class with SimTalk commands.

Type

Attribute

**Syntax**

```simtalk
<MUPath >.LoadBaytype:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Line" , "Track" , or "Store" .

**Example**

```simtalk
.MUs.Transporter:1.LoadBaytype := "Track"
```

SimTalk

getStackHeight [SimTalk] - MUs

See also

Type [loading space]

X-Dimension [Transporter]

Y-Dimension [Transporter]

Y-Dimension [Transporter]

Controls [loading space]

Sensors [Transporter]

Direction of the Animation Line

MU Length [Transporter]

##### Pause [SimTalk] - Transporter

Pause [SimTalk] - Transporter

Sets if the Transporter designated by &lt;MU-Path&gt; is paused or stopped ( true ) or not ( false ).

Remarks

After the value is changed, the Transporter activates the Pause Control .

**Note**

Plant Simulation does not modify the attribute Pause in any way during reset and init phases.

**Note**

Pauses do not affect the Target Position of the Transporter .

Type

Attribute

Syntax

```simtalk
<MUPath >.Pause:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
if not MyTrack.Cont.pause
	MyTrack.Cont.pause := true
end
```

SimTalk

PauseCtrl [SimTalk]

**See also**

**Paused/Planned/Unplanned [Transporter]**

##### ResetDestinationWhenAtDestination [SimTalk] - Transporter

Makes the Transporter class designated by &lt;MU-Path&gt; reset the Destination and the route to the destination when the Transporter arrived at the destination ( true ) or not ( false ).

Remarks

The Destination is reset at the same point in time as the attribute DestinationWasReached , namely when leaving the Destination .

If the Transporter arrived at the destination and if no new destination is set or if the destination is not reset, the Transporter again tries to find a route to the same destination. This can be useful in certain exceptional cases, but will probably be not useful in most cases.

If the destination is a DataTable or a list object , the destination will only be reset when the last object in the DataTable or list object has been reached.

If the attribute is true , the DataTable will be processed once only.

If the attribute is false , the DataTable will be processed cyclically.

Type

Attribute

Syntax

&lt;MUPath &gt;.ResetDestinationWhenAtDestination:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter.ResetDestinationWhenAtDestination := true
```

SimTalk

setRoute [SimTalk] - Transporter

**DestinationWasReached [SimTalk]**

See also

Destination [SimTalk] - Transporter

Reset Destination When at Destination [Transporter]

**RotationSpeed [SimTalk]**

##### RotationSpeed [SimTalk]

Sets the speed with which the AGV designated by &lt;MU-Path&gt; rotates on the spot if you called the method rotate .

Remarks

Specify a real number greater than 0 . The Rotation Speed is measured in degrees per second.

Specify -1 to make the AGV rotate on the spot instantaneous, without using any time.

Specify 0 as the Default Curve Radius to make the AGV rotate on the spot with the Rotation Speed .

When the AGV arrives at the waypoint of the route, it decelerates to 0, rotates on the spot with the specified Rotation Speed , and accelerates again afterwards.

**Note**

In previous versions the AGV did not use the Rotation Speed when rotating on the spot with a Default Curve Radius of 0.

To use the behavior of previous versions, enter -1 as the Rotation Speed for the respective AGVs .

Type

Attribute

Syntax

<MUPath >.RotationSpeed:speed

Assignment Value

You can assign a value of data type speed .

**Examples**

```simtalk
.MUs.Transporter.DefaultCurveRadius := 1.1 .MUs.Transporter.RotationSpeed := 2 -- Transporter drives a curve, does not use rotation speed
.MUs.Transporter.DefaultCurveRadius := 0 .MUs.Transporter.RotationSpeed := 2 -- Transporter rotates on the spot, uses rotation speed
```

SimTalk rotate [SimTalk] - Transporter setRoute [SimTalk] - Transporter See also Rotation Speed [text box] Default Curve Radius [text box] Curve Speed [text box]

Marker , object

##### RouteWeightingAttr [SimTalk] - Transporter

Is used for controlling the Route Weighting Attribute when you activate Automatic Routing for the Transporter designated by &lt;MU-Path&gt;.

**Remarks**

**Note**

If you assign a value to the attribute RouteWeightingAttr , Plant Simulation automatically re-computes the destination.

**Note this:**

- For Transporters driving on Tracks/TwoLaneTracks connected with Connectors to other simulation objects this applies:

The value of the route weighting attribute determines the name of a user-defined attribute of a Track/ TwoLaneTrack . The user-defined attribute has to have the data type real .

The lengths of the Track/TwoLaneTracks will be multiplied with the value you assigned to the userdefined attribute . If you assign a negative value to the user-defined attribute , this Track/TwoLaneTrack will not be used for automatic routing. Tracks/TwoLaneTracks , which do not have a user-defined attribute with the name designated by the route weighting attribute, use the factor 1.0.

**Note**

If you assign a value to the attribute RouteWeightingAttr , Plant Simulation automatically re-computes the destination.

- For Transporters , which drive freely within the area, this applies:

The value of the route weighting attribute determines the name of a user-defined attribute of the objects Marker/Track/TwoLaneTrack or Connector . The user-defined attribute has to have the data type real or be a Method that returns a value of data type real .

The lengths of the Track will be multiplied with the value you assigned to the user-defined attribute .

For Connectors between two Markers/Track/TwoLaneTrack the distance between these objects will be multiplied with the value you assigned to the user-defined attribute .

Connectors/Markers/Track/TwoLaneTracks , which do not have a user-defined attribute with the name designated by the route weighting attribute, use the factor 1.0.

Type

Attribute

**Syntax**

```simtalk
<MUPath >.RouteWeightingAttr:string
```

**Assignment Value**

You can assign a value of data type string .

**Examples**

```simtalk
.MUs.Transporter.RouteWeightingAttr :="MyWeightFactor"
Track5.MyWeightFactor := 0.7  // preferably use this main route
Track7.MyWeightFactor := 1.5  // try to avoid this branch route
Track8.MyWeightFactor := -1   // do not use this route
param sensorID : integer -- calculate weighing factor x length for every track -- to show which way gets the best value
WeightBlue := Highway.A.length * Highway.CurrentTraffic + CityRoad5.A.length * CityRoad5.CurrentTraffic + CityRoad7.A.length * CityRoad7.CurrentTraffic + CityRoad9.A.length * CityRoad9.CurrentTraffic
WeightGreen := CountryRoad.A.length * CountryRoad.CurrentTraffic + CityRoad4.A.length * CityRoad4.CurrentTraffic
WeightGray := CityRoad1.A.length * CityRoad1.CurrentTraffic + CityRoad2.A.length * CityRoad2.CurrentTraffic + CityRoad3.A.length * CityRoad3.CurrentTraffic + CityRoad6.A.length * CityRoad6.CurrentTraffic -- set destination of the transporter
@.destination := "CityRoad10"
```

**See also**

Route Weighting Attribute - Transporter

Automatic Routing [Transporter]

Destination [SimTalk] - Transporter

**RoutingCtrl [SimTalk]**

##### RoutingCtrl [SimTalk]

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation runs the Method when it automatically predicted a route to the destination.

Within this control you might, for example, read out the newly predicted route using the method getRoute .

You might then manipulate this route and assign the changed route with the method setRoute .

You might also check if the entrance or the exit of one of the Tracks/TwoLaneTracks along the predicted route is locked and then circumvent this Track/TwoLaneTrack .

Type

Attribute

Syntax

<MUPath >.RoutingCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
.MUs.Transporter.RoutingCtrl := &myRoutingControl
```

SimTalk

getRoute [SimTalk] - Transporter

setRoute [SimTalk] - Transporter

See also

Routing Control

##### SafetyZones [SimTalk]

Sets the safety zones of the AGV designated by &lt;MU-Path&gt;.

**Remarks**

Note Only Automated Guided Vehicles ( AGVs ) support safety zones.

If another AGV enters or exits one of the safety zones of an automated guided vehicle, its Distance Control is going to be called.

You have to enter the values in this order:

[Length zone 1, ∆Width zone 1, Length zone 2, ∆Width zone 2]

Zone 1 designates the inner zone and Zone 2 designates the outer zone.

The zones are attached in the direction of motion to the AGV , to the front in the forward direction, to the rear in the backward direction.

<!-- image -->

**Note**

Calling the method drive with a negative value for the parameter Distance denotes that the AGV drives backward .

The zones are attached in the direction of motion and only look forward from the Front or backward from the Rear of the AGV , not sideways! This even applies when you specify a non-zero value for the parameter Angle of the method drive .

**SafetyZones [SimTalk]**

The values relate to the respective side of the AGV , Length applies to forward and backward respectively and ΔWidth toward both sides. For this reason the entire Length of a zone corresponds to its length and the entire width to the Width of the AGV plus twice the ΔWidth . All values have to be greater than or equal to 0. In addition, Zone 2 has to completely enclose Zone 1 , thus the following constraints apply:

- The Length of Zone 1 has to be smaller than or equal to the Length of Zone 2 .
- The ΔWidth of Zone 1 has to be smaller than or equal to the ΔWidth of Zone 2 .

**Note**

If you set the Length of a zone to the value 0 (more accurately to a value smaller than 1 cm), Plant Simulation deactivates this zone, and the surrounding zone respectively, and does not execute the Distance Control of the AGV for the affected zones.

**Note**

If you set the ΔWidth of a zone to a value that causes the entire width of the zone to fall below 1 cm for an AGV of width 0, this zone is deactivated as well. We advise against setting the Width of an AGV to 0.

You cannot change safety zones of an AGV when other AGVs are located in one of the safety zones.

Type

Attribute

Syntax

<MUPath >.SafetyZones:length[4]

Assignment Value

You can assign an array with four values of data type length .

Example

```simtalk
var agv: object := AGVPool.getIdleAGV
agv.SafetyZones := [1.0, 0.0, 2.0, 0.4]
```

SimTalk

drive [SimTalk]

Distance [SimTalk]

getSafetyZoneContent [SimTalk] SafetyZonesEmpty [SimTalk] calcBrakingDistance [SimTalk] - general description See also Distance Control Distance [text box] - distance control Length Zone 1 ΔWidth Zone 1 Length Zone 2 ΔWidth Zone 2 Prevent AGVs from Colliding ShiftCalendarObject [SimTalk] - Transporter Sets the ShiftCalendar which the Transporter designated by &lt;MU-Path&gt; uses.

Type

Attribute

Syntax

&lt;MUPath &gt;.ShiftCalendarObject:path

Assignment Value

You can assign a value of data type path .

Example

forklift.ShiftCalendarObject := SCEngineAssembly

See also

ShiftCalendar [object]

##### Speed [SimTalk] - Transporter

Sets the Speed of the Transporter designated by &lt;MU-Path&gt; as it drives on the Track in the forward direction.

Remarks

The value has to be equal to or greater than 0 and is interpreted in meters per second (m/s).

Type

Attribute

Syntax

<MUPath >.Speed:speed

**Assignment Value**

You can assign a value of data type speed .

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the number, without a separating blank space, for example 100kmh or 100.5kmh .

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**Note**

In SimTalk 2.0 you can enter the unit s for seconds . Enter the unit s directly after the number, without a separating blank space. Entering the unit sometimes is necessary to make sure that the computed expression has the correct data type.

```simtalk
var x : length := 10m
var s : speed := x / 2s   // Beware: x/2 would have the wrong unit, m instead of m/s
```

**Example**

```simtalk
// Speed limit 10 kilometers per hour for part moving on Track. // The Transporters may have to be slowed down. // Entrance control with speed control if@.speed2.77777 // 10km/h
@.Speed := 2.77777
end
```

**See also**

**Speed [Transporter]**

SpeedCtrl [SimTalk] - Transporter

Designates a Method object of the object designated by &lt;MU-Path&gt;.

Remarks

Plant Simulation runs the Speed Control of the Transporter :

- When the Transporter reaches its final speed after accelerating or decelerating or when it stops after decelerating.
- When the Speed of the Transporter without a Speed Control changes when a Destination is set or reached
- When a Transporter , which drives freely within the area, and for which you activated Curve Speed , reaches the curve speed the start or the end of a curve.

**Note**

This only applies, when you selected the check box Acceleration .

If you did not enter the name of a Method , the attribute is VOID.

Type

Attribute

Syntax

&lt;MU- Path &gt;.SpeedCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
.MUs.Transporter.SpeedCtrl := &mySpeedCtrl
```

See also

Speed control [Transporter]

Acceleration [check box] - Transporter Speed [Transporter] Destination [text box] - Transporter Curve Speed [text box]

##### StartDelayDuration [SimTalk]

Sets the time after which a Transporter designated by &lt;MU-Path&gt;, which collided with the one driving in front of it, starts moving after the Transporter driving in front started again.

Remarks

For the Transporter that drives freely within the space of the model the Start Delay Duration is the time after which a stopped Transporter starts moving again after you entered a Speed that is greater than 0.

Type

Attribute

Syntax

&lt;MUPath &gt;.StartDelayDuration:time

Assignment Value

You can assign a value of data type time .

Example

.MUs.Transporter.StartDelayDuration := 60

See also

Start Delay Duration [text box]

Speed [SimTalk] - Transporter

##### StopAtDestination [SimTalk]

Sets if a Transporter driving on Tracks/TwoLaneTracks stops at its Destination ( true ) or not ( false ). A Destination can be a Track/TwoLaneTrack or an object that is set as the Destination of a sensor on a Track .

Remarks

The Transporter activates the Destination Control as soon as it stopped at its Destination . To make the Transporter continue on its way, set the attribute Stopped to false .

**Note**

The Transporter only stops at the Destination if you also set the attribute ResetDestinationWhenAtDestination . This prevents you from directly using this setting to always send a Transporter to the same Destination and make it stop there on a circular course.

**Note**

StopAtDestination does not affect freely driving Transporters and Transporters that are part of a tugger train .

Type

Attribute

Syntax

```simtalk
<MUPath >.StopAtDestination:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Transporter.StopAtDestination := true
-- entrance control of a Source
@.XDim = 1
@.YDim = 1
@.StopAtDestination = true
@.AccelerationEnabled = true
@.Acceleration = 0.2
```

@.Deceleration = 0.2 @.Destination = Station1

```simtalk
-- sensor control of a Track
param SensorID: integer, Front: boolean, BookPos: boolean
var station = ?.sensorID(SensorID).Destination
waituntil station.Cont /= void and station.Cont.Finished -- Wait until the station's content is not empty and the station's content has finished processing. station.Cont.move(@)
@.Destination = Station2
@.Stopped = false
```

SimTalk

ResetDestinationWhenAtDestination [SimTalk] - Transporter

DestinationWasReached [SimTalk]

Stopped [SimTalk] - MUs

See also

Stop at Destination

Destination Control

Destination [text box] - Transporter

**StoppingCounter [SimTalk]**

##### StoppingCounter [SimTalk]

Stops the AGV designated by &lt;MU-Path&gt; once the StoppingCounter reaches a value greater than 0. It stops by using the specified Deceleration and without overwriting the attribute Speed .

Remarks

Once the AGV reaches a speed of 0, Plant Simulation sets the attribute Stopped to true. The AGV starts moving again when StoppingCounter reaches the value 0.

The attribute StoppingCounter can take a value greater than 1 if several reasons exist to stop the AGV .

Use StoppingCounter to stop the AGV with deceleration and make it drive again without cutting inheritance of its speed. You can then use StoppingCounter instead of the instructions AGV.Speed := 0.0 and AGV.Speed := AGV.Origin.Speed .

StoppingCounter is useful if an AGV stops for different reasons, for example in a Distance Control because it got too close to another AGV and in addition has to wait at a crossing until the crossing is free. It can later only continue driving if the StoppingCounter is 0.

Type

Attribute

Syntax

```simtalk
<MUPath >.StoppingCounter:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
AGV.StoppingCounter += 1
AGV.StoppingCounter -= 1
AGV.StoppingCounter := 1
AGV.StoppingCounter := 0
```

SimTalk

Stopped [SimTalk] - MUs See also AGV [text box] Deceleration [SimTalk] - Transporter Speed [SimTalk] - Transporter Video on YouTube https://youtu.be/PYXYutlaGOs?si=FNgErAj2FbcGgyhv&amp;t=409

**TargetDistance [SimTalk]**

##### TargetDistance [SimTalk]

Sets the target distance which the Transporter designated by &lt;MU-Path&gt; is to cover.

Remarks

**Note**

The attribute TargetDistance does not apply to the freely driving AGV , because the Destination of a freely driving AGV is specified by its route. The route ends at the Destination .

The Transporter automatically changes the state of the attribute Stopped to not stopped (false).

Depending if you activated Acceleration or not the Transporter behaves as follows:

- If Acceleration is deactivated, the Transporter covers the designated TargetDistance and stops there.
- If Acceleration is activated, the Transporter accelerates to the final speed, drives on with a constant speed and decelerates in time so that the Transporter stops after reaching the TargetDistance . If the TargetDistance is too small to reach the final speed and to decelerate, Plant Simulation uses the highest possible speed.

**Note**

Depending on the specified Deceleration , approaching the TargetDistance is not always possible.

As opposed to the attribute TargetPosition , for which the Transporter always has to be located on a single Track/TwoLaneTrack in its entirety, the attribute TargetDistance also works across several Tracks/ TwoLaneTracks . In addition, it also works for tugger trains .

If the Transporter has covered the TargetDistance , Plant Simulation sets the value of the attribute to -1, calls the Destination Control and sets Stopped to true.

If, for any reason, the position of the Transporter will be updated, then Plant Simulation also updates the value of the attribute TargetDistance to the current value. This is the value you set minus the value of that the Transporter already covered.

Type

Attribute

Syntax

&lt;MUPath &gt;.TargetDistance:real Watchable The attribute is watchable .

Assignment Value

You can assign a value of data type real .

The TargetDistance always is a positive value that is applied in the direction of motion.

Specify -1 to cancel approaching the TargetDistance .

**Examples**

```simtalk
.MUs.Transporter:2.TargetDistance := 3
.MUs.Transporter:2.TargetDistance := -1 // cancels approaching the target distance
```

**SimTalk**

Stopped [SimTalk] - MUs

TargetPosition [SimTalk]

See also

Acceleration [check box] - Transporter

Deceleration [text box] - Transporter

Speed [Transporter]

##### TargetPosition [SimTalk]

Sets the target position of the Transporter designated by &lt;MU-Path&gt; on a Track/TwoLaneTrack . The default value is -1.

Remarks

The Transporter drives to the TargetPosition so that its Front is located at this position.

You can only set the TargetPosition if the Transporter is located all the way on a Track/TwoLaneTrack and if it is not a part of a tugger train .

The Transporter automatically switches to Backwards when a change of direction is required to reach the target position. The Transporter automatically changes the state of the attribute Stopped to not stopped (false).

Depending if you activated Acceleration or not, the Transporter behaves as follows:

- If Acceleration is deactivated, the Transporter covers the designated TargetDistance and stops there.
- If Acceleration is activated, the Transporter accelerates to the final speed, drives on with a constant speed and decelerates in time so that the Transporter stops after reaching the TargetDistance . If the TargetDistance is too small to reach the final speed and to decelerate, Plant Simulation uses the highest possible speed.

**Note**

Depending on the specified Deceleration , approaching the TargetDistance is not always possible if the Transporter has a Speed with which the Transporter cannot come to a stop at the target position with the specified Deceleration .

**Note**

Changing the TargetPosition might affect other attributes, such as Stopped and Backwards . Inheritance of these attributes might then be deactivated.

**Note**

If you want to stop a possible approach to the target position, you can set the attribute Stopped to true . Then Plant Simulation stops the Transporter without it reaching the target position. Plant Simulation does not call the Destination Control and sets the value of the attribute TargetPosition to the default value -1.

If the Transporter has reached the TargetPosition , Plant Simulation sets the value of the attribute to -1.

Type

Attribute

**Syntax**

```simtalk
<MUPath >.TargetPosition:real
```

**Watchable**

The attribute is watchable . Once the Transporter has reached the TargetPosition , Plant Simulation sets the value to -1, calls the Destination Control , and sets Stopped to true .

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.MUs.Transporter:1.TargetPosition := 8
waituntil .MUs.Transporter:1.TargetPosition = -1
print "Destination reached"
```

SimTalk

TargetDistance [SimTalk]

See also

Acceleration [check box] - Transporter

Deceleration [text box] - Transporter

Speed [Transporter]

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=f6PmRZSDzc7Ma0I6&amp;t=762](https://youtu.be/9g6Uou-8eMc?si=f6PmRZSDzc7Ma0I6&t=762)

##### XDim [SimTalk] - Transporter

Sets the number of places along the x-axis of the loading space of the Transporter designated by &lt;MUPath&gt;.

**Remarks**

**Note**

For determining the size in pixels, compare the Scaling Factor .

The loading Capacity is the product of XDim times YDim times ZDim . The greatest allowed value is one million.

If you decrease the dimension of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Transporters for which you activated the Loading Space Type &gt; Store and then entered a dimension, Plant Simulation computes the distance between the animation points, onto which it places the loaded MUs , according to the dimension as follows:

- The distance in the X-Direction (horizontal) is the length in pixels of the loaded object divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width in pixels of the loaded object divided by the Y-Dimension .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

Type

Attribute

**Syntax**

```simtalk
<MUPath >.XDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
.MUs.Transporter.XDim := 2 .MUs.Transporter.YDim := 2 .MUs.Transporter.ZDim := 4
```

**SimTalk**

Capacity [SimTalk] - MUs

YDim [SimTalk] - Transporter

Z-Dimension [Transporter]

See also

X-Dimension [Transporter]

##### YDim [SimTalk] - Transporter

Sets the number of places along the y-axis of the loading space of the Transporter designated by &lt;MUPath&gt;.

**Remarks**

The loading Capacity is the product of XDim times YDim times ZDim . The greatest allowed value is one million.

If you decrease the dimension of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

For loaded Transporters for which you activated the Loading Space Type &gt; Store , Plant Simulation computes the distance between the animation points as follows:

- The distance in the X-Direction (horizontal) is the length in pixels of the loaded object divided by the X-Dimension .
- The distance in the Y-Direction (vertical) is the width in pixels of the loaded object divided by the Y-Dimension .

**Note**

For determining the size in pixels, compare the Scaling Factor .

If either the distance in the X-Direction or in the Y-Direction is smaller than 4 pixels, Plant Simulation does not show any MUs at all but draws a pattern in a 2D Only model to signify that the object is not empty.

As long as the loading space is half empty, Plant Simulation shows a hatch pattern. If the loading space is more than half full, Plant Simulation shows a checker pattern.

<!-- image -->

Type

Attribute

**Syntax**

```simtalk
<MUPath >.YDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
.MUs.Transporter.XDim := 2 .MUs.Transporter.YDim := 2 .MUs.Transporter.ZDim := 4
```

**SimTalk**

Capacity [SimTalk] - MUs

XDim [SimTalk] - Transporter

Z-Dimension [Transporter]

See also

Y-Dimension [Transporter]

##### ZDim [SimTalk] - Transporter

ZDim [SimTalk] - Transporter

Sets the number of storage places along the z-axis of the loading space of type Store of the Transporter designated by &lt;MU-Path&gt;.

Remarks

The Z-Dimension enables stacking parts on the loading space of type Store the Transporter .

The loading Capacity is the product of XDim times YDim times ZDim .

If you decrease the dimension of the Transporter , make sure that no MUs are located on the storage places that will be deleted by this action! Either delete these MUs or move them to another storage place on the smaller loading space.

Type

Attribute

Syntax

```simtalk
<MUPath >.ZDim:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Examples

```simtalk
.MUs.Transporter.XDim := 2 .MUs.Transporter.YDim := 2 .MUs.Transporter.ZDim := 4
// Enumerates all the MUs on place (1,1)
var place := .MUs.Transporter:1[1,1]
for var i := 1 to place.NumMU
	print place.MU(i)
// Accesses the topmost MU of the stack .MUs.Transporter:1[1,1].Cont
```

<!-- image -->

**Tools**

