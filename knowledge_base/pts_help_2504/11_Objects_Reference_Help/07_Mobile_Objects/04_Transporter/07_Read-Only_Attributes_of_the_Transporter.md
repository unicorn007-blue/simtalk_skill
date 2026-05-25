#### Read-Only Attributes of the Transporter

\_Read-Only Attributes of the Transporter

The Transporter provides:

- The read-only attributes listed in the table of contents to the left.
- The Read-Only Attributes of All MUs .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print @.FrontPos

**AGVPool [SimTalk]**

##### AGVPool [SimTalk]

Returns the AGVPool to which the Transporter designated by &lt;MU-Path&gt; is assigned.

Type

Read-only attribute

Syntax

<MUPath >.AGVPool → path

Return Value

The return value has the data type path .

Void for Transporters driving on Tracks/TwoLaneTracks .

Is the associated AGVPool for Transporters driving freely within the area.

Example

```simtalk
print .MUs.Transporter:3.AGVPool   // void, as the Transporter drives on a Track print .MUs.Transporter:1.AGVPool   // .Models.Model.AGVPool as the Transporter drives freely
```

**See also**

AGV [text box] of the AGVPool

##### Collided [SimTalk]

Returns if the Transporter designated by &lt;MU-Path&gt; collided with another one (true) or not (false).

Remarks

When a MU with the same Speed and the same Acceleration drives behind another MU , it is not collided.

This means, for example, when a MU collides with a stationary MU and when both MU then drive on together, the rear MU does not count as collided. Or when a faster MU collides with another MU and when both MUs have the same Acceleration and the same Speed , the rear MU does not count as collided after moving on.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.Collided → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print@.Collided

See also

Collision Control [Transporter]

CurrentAcceleration [SimTalk] - Transporter

Returns the actual acceleration or deceleration of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.CurrentAcceleration → acceleration

Watchable

The read-only attribute is watchable for special values. By observing this value, you might, for example detect the event when the Transporter has reached its Final Speed .

Return Value

The return value has the data type acceleration .

Example

```simtalk
print .MUs.Transporter:5.CurrentAcceleration
```

See also

Acceleration [check box] - Transporter

##### DistanceObjectBelowLimit [SimTalk]

Returns the MU for which the Distance of the Transporter designated by &lt;MU-Path&gt; is smaller than the value you set.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.DistanceObjectBelowLimit → object
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type object .

If the Distance is not smaller than the defined value for any MU , DistanceObjectBelowLimit returns void.

Examples

```simtalk
var o : object := .MUs.Transporter:1.DistanceObjectBelowLimit
print .UserObjects.MyTransporter1:10.DistanceObjectBelowLimit // might, for example
return .UserObjects.MyTransporter1:9
```

See also

Distance [text box] - distance control

Distance Control

##### GetFrontWagon [SimTalk]

Returns the Transporter which is hitched to the front of the active Transporter designated by &lt;MU-Path&gt;.

Remarks

The object can either be a trailer or the tractor.

<!-- image -->

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.GetFrontWagon → object
```

Return Value

The return value has the data type object .

Example

```simtalk
print .MUs.Transporter:2.GetFrontWagon // returns .MUs.Transporter:1
```

**See also**

**GetRearWagon [SimTalk]**

##### GetRearWagon [SimTalk]

Returns the Transporter which is hitched to the rear of the active Transporter designated by &lt;MU-Path&gt;.

Remarks

The object can either be a trailer or the tractor.

<!-- image -->

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.GetRearWagon → object
```

Return Value

The return value has the data type object .

Example

```simtalk
print .MUs.Transporter:2.GetRearWagon // returns .MUs.Transporter:3
```

**See also**

**GetFrontWagon [SimTalk]**

##### GetTractor [SimTalk]

GetTractor [SimTalk]

Returns the tractor which pulls or pushes the trailer designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.GetTractor → object
```

Return Value

The return value has the data type object .

Example

```simtalk
var MyTractor: object
MyTractor := MyTrailer:1.GetTractor
MyTractor.Stopped := true
```

SimTalk

Is Tractor [check box]

GetFrontWagon [SimTalk]

GetRearWagon [SimTalk]

See also

IsTractor [SimTalk]

HasRouteToDestination [SimTalk] - Transporter

Returns if the Transporter designated by &lt;MU-Path&gt; did find a route to its destination (true) or if it did not find one (false).

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
print .MUs.Transporter:1.HasRouteToDestination
```

SimTalk

getRoute [SimTalk] - Transporter

See also

Route to Destination [Transporter]

Destination [text box] - Transporter

##### SafetyZonesEmpty [SimTalk]

SafetyZonesEmpty [SimTalk]

Returns if other AGVs are located in one of the safety zones of the AGV designated by &lt;MU-Path&gt; (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.SafetyZonesEmpty
-> boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

```simtalk
var agv: object := AGVPool.getAssignedAGV(1)
if agv.SafetyZonesEmpty
	agv.Speed := agv.Origin.Speed
end
```

SimTalk

Distance [SimTalk]

getSafetyZoneContent [SimTalk]

SafetyZones [SimTalk]

See also

Distance Control

Distance [text box] - distance control

##### StatBatChargeCount [SimTalk]

Returns how often the battery of the Transporter designated by &lt;MU-Path&gt; was charged.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatBatChargeCount → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatBatChargeCount
```

See also

Statistics report , Battery [statistics]

##### StatBatChargePortion [SimTalk]

StatBatChargePortion [SimTalk]

Returns the portion of its lifetime during which the battery of the Transporter designated by &lt;MU-Path&gt; was charged.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatBatChargePortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatBatChargePortion
```

See also

Statistics report , Battery [statistics]

StatHomeDrivingPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; was returning to its base.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatHomeDrivingPortion → real

Return Value

The return value has the data type real .

Example

print MyTrack.Transporter:1.StatHomeDrivingPortion

SimTalk

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

See also

Home Driving

Statistics Values [Transporter] of the Transporter

Statistics report , Usage of the Transporters

##### StatHomeDrivingTime [SimTalk]

StatHomeDrivingTime [SimTalk]

Returns the time the Transporter designated by &lt;MU-Path&gt; took for returning to its base.

Type

Read-only attribute

Syntax

<MUPath >.StatHomeDrivingTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyTrack.Transporter:1.StatHomeDrivingTime
```

SimTalk

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

##### StatOrderEmptyPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; had an order and was not loaded with parts.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatOrderEmptyPortion → real

Return Value

The return value has the data type real .

Example

print MyTrack.Transporter:1.StatOrderEmptyPortion

SimTalk

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

See also

Statistics Values [Transporter] of the Transporter

Statistics report , Usage of the Transporters

Order Empty

##### StatOrderEmptyTime [SimTalk]

StatOrderEmptyTime [SimTalk]

Returns the time during which the Transporter designated by &lt;MU-Path&gt; had an order and was not occupied.

Type

Read-only attribute

Syntax

<MUPath >.StatOrderEmptyTime → time

Return Value

The return value has the data type time .

Example

print MyTrack.Transporter:1.StatOrderEmptyTime

SimTalk

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

##### StatOrderOccPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; had an order and was loaded with parts.

Type

Read-only attribute

Syntax

&lt;MUPath &gt;.StatOrderOccPortion → real

Return Value

The return value has the data type real .

Example

print .MUs.Transporter:1.StatOrderOccPortion

SimTalk

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

See also

Statistics Values [Transporter] of the Transporter

Statistics report , Usage of the Transporters

Order Occupied

##### StatOrderOccTime [SimTalk]

StatOrderOccTime [SimTalk]

Returns the time during which the Transporter designated by &lt;MU-Path&gt; had an order and was occupied.

Type

Read-only attribute

Syntax

<MUPath >.StatOrderOccTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatOrderOccTime
```

See also

DrivingHome [SimTalk]

HasOrder [SimTalk] - Transporter

##### StatTraveledDistance [SimTalk] - Transporter

Returns the distance which the instance of the Transporter designated by &lt;MU-Path&gt; covered while driving on a Track/TwoLaneTrack or freely within the area of the model in meters.

Type

Read-only attribute

Syntax

<MUPath >.StatTraveledDistance → length

Return Value

The return value has the data type length .

Example

print MyTrack.MUs.Transporter:1.StatTraveledDistance

See also

Tab Statistics [Transporter]

Statistics report , Traveled Distance

##### StatTspFailCount [SimTalk]

StatTspFailCount [SimTalk]

Returns the number of failures of the Transporter designated by &lt;MU-Path&gt; during the total life-span.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspFailCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatTspFailCount
```

See also

Statistics report , Failures [Transporter]

##### StatTspFailDelta [SimTalk]

Returns the standard deviation from the mean value of a failure of the Transporter designated by &lt;MUPath&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspFailDelta → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspFailDelta
```

See also

Statistics report , Failures [Transporter]

##### StatTspFailMu [SimTalk]

StatTspFailMu [SimTalk]

Returns the mean duration of a failure of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspFailMu → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTspFailMu
```

See also

Statistics report , Failures [Transporter]

##### StatTspFailPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; was failed.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspFailPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTspFailPortion
```

See also

Statistics Values of the Transporter

Statistics report , Usage of the Transporters

Statistics report , Failures [Transporter]

Failed [driving statistics]

##### StatTspFailTime [SimTalk]

StatTspFailTime [SimTalk]

Returns the sum of all failure times during the total life-span of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspFailTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspFailTime
```

See also

Statistics report , Failures [Transporter]

##### StatTspPausingCount [SimTalk]

Returns the number of pauses during the total life-span of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspPausingCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatTspPausingCount
```

See also

Statistics report , Pauses [Transporter]

##### StatTspPausingDelta [SimTalk]

StatTspPausingDelta [SimTalk]

Returns the standard deviation from the mean value of a pause of the Transporter designated by &lt;MUPath&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspPausingDelta → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspPausingDelta
```

See also

Statistics report , Pauses [Transporter]

##### StatTspPausingMu [SimTalk]

Returns the mean duration of a pause of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspPausingMu → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspPausingMu
```

**See also**

Statistics report , Pauses [Transporter]

StatTspPausingPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; was paused.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspPausingPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTspPausingPortion
```

See also

Statistics Values [Transporter] of the Transporter

Statistics report , Usage of the Transporters

Statistics report , Pauses [Transporter]

Paused [Transporter]

##### StatTspPausingTime [SimTalk]

Returns the sum of all pause-times of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspPausingTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspPausingTime
```

See also

Statistics report , Pauses [Transporter]

##### StatTspReadyCount [SimTalk]

StatTspReadyCount [SimTalk]

Returns the number of ready-times during the total life-span of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspReadyCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatTspReadyCount
```

See also

Statistics report , Ready-Times

##### StatTspReadyDelta [SimTalk]

Returns the standard deviation from the mean value of a ready-time of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspReadyDelta → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspReadyDelta
```

See also

Statistics report , Ready-Times

##### StatTspReadyMu [SimTalk]

StatTspReadyMu [SimTalk]

Returns the mean duration of a ready-time of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspReadyMu → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspReadyMu
```

See also

Statistics report , Ready-Times

##### StatTspReadyPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; was ready.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspReadyPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTspReadyPortion
```

See also

Statistics Values [Transporter] of the Transporter

Statistics report , Usage of the Transporters

Statistics report , Ready-Times

Ready

##### StatTspReadyTime [SimTalk]

StatTspReadyTime [SimTalk]

Returns the sum of all ready-times of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspReadyTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspReadyTime
```

See also

Statistics report , Ready-Times

##### StatTspUnplannedCount [SimTalk]

Returns how often the Transporter designated by &lt;MU-Path&gt; was unplanned during its lifetime.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspUnplannedCount → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print .MUs.Transporter:1.StatTspUnplannedCount
```

See also

Tab Statistics [Transporter] of the Transporter

Unplanned [Transporter]

StatTspUnplannedDelta [SimTalk]

Returns the standard deviation from the mean value of the mean duration of an unplanned time of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.staStatTspUnplannedDelta → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspUnplannedDelta
```

See also

Tab Statistics [Transporter] of the Transporter

Unplanned [Transporter]

##### StatTspUnplannedMu [SimTalk]

Returns the mean duration of an unplanned time of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspUnplannedMu → time

Return Value

The return value has the data type time .

Example

```simtalk
print .MUs.Transporter:1.StatTspUnplannedMu
```

See also

Tab Statistics [Transporter] of the Transporter

Unplanned [Transporter]

StatTspUnplannedPortion [SimTalk]

Returns the portion of its lifetime during which the Transporter designated by &lt;MU-Path&gt; was unplanned.

Type

Read-only attribute

Syntax

```simtalk
<MUPath >.StatTspUnplannedPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
print .MUs.Transporter:1.StatTspUnplannedPortion
```

See also

Statistics Values [Transporter]

Statistics report , Usage of the Transporters

Unplanned [Transporter]

##### StatTspUnplannedTime [SimTalk]

Returns the sum of all unplanned times of the Transporter designated by &lt;MU-Path&gt;.

Type

Read-only attribute

Syntax

<MUPath >.StatTspUnplannedTime → time

Return Value

The return value has the data type time .

**Example**

```simtalk
print .MUs.Transporter:1.StatTspUnplannedTime
```

See also

Tab Statistics [Transporter]

Unplanned [Transporter] , drop-down list

