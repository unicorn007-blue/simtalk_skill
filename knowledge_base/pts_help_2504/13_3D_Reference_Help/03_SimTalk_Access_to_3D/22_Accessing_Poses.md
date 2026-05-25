### Accessing Poses

#### \_\_Accessing Poses

SimTalk provides the attributes and methods listed in the table of contents to the left for poses for objects, which you can insert into a Frame , and for MUs .

In general a pose designates a combination of position and orientation of an object. In our context a pose designates a number of translation or rotation positions for animatable objects which belong to a simulation object. This also takes the degrees of freedom into account which you set in the joint definitions of these animatable objects.

A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

SimTalk

- \_3D.Poses.moveTo [SimTalk]

\_3D.Poses.moveToCoordinate [SimTalk]

See also

- \_\_Accessing Joints

Joint

Poses

Model Joints and Poses

#### \_3D.MovementInterruptible [SimTalk]

Sets if failures and pauses will interrupt pose runs of the object designated by &lt;Path&gt; ( true ) or not ( false ).

**Remarks**

If you start a pose run while a failure or pause is active at the moment, the pose run will start regardless of the setting MovementInterruptible .

A pose run designates all movements that were started by any version of the methods \_3D.Poses.moveTo and \_3D.Poses.moveToCoordinate , both for the object itself and for any of its animatable objects.

\_3D.MovementInterruptible applies to the objects FluidSource , FluidDrain , Tank , Mixer , Transporter , Frame , Exporter , and Worker . It also applies to all objects which can transport MUs or Workers , except for the Workplace .

Type

Attribute

Syntax

```simtalk
< Path >._3D.MovementInterruptible:boolean
```

Assignment Value

You can assign a value of data type boolean .

**Example**

```simtalk
Station._3D.MovementInterruptible := true
```

See also

**Movement Interruptible**

- \_3D.Poses.cancelMovement [SimTalk]
- \_3D.Poses.continueMovement [SimTalk]
- \_3D.Poses.isMovingTo [SimTalk]
- \_3D.Poses.moveTo [SimTalk]
- \_3D.Poses.moveToCoordinate [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]

\_3D.Poses.stopMovement [SimTalk]

\_3D.Poses.EndPoseWasReached [SimTalk]

#### \_3D.Poses.cancelMovement [SimTalk]

Cancels the movement toward the designated pose of the object designated by &lt;Path&gt;.

Remarks

If you do not specify the optional parameter, all movements will be canceled.

\_3D.Poses.cancelMovement affects the designated pose, however always together with the other poses to which the object moved together with this pose in a common call of the method \_3D.Poses.moveTo .

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.cancelMovement([Pose:string])
```

Parameter

The optional parameter Pose of data type string sets the name of the pose toward which the object moves.

Example

Station._3D.Poses.moveTo(["Pose1", "Pose2"]) Station._3D.Poses.cancelMovement("Pose1") // instead, you can also enter: Station._3D.Poses.cancelMovement("Pose2")

**See also**

- \_3D.Poses.moveTo [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]
- \_3D.Poses.stopMovement [SimTalk]
- \_3D.MovementInterruptible [SimTalk]
- \_3D.Poses.EndPoseWasReached [SimTalk]

#### \_3D.Poses.continueMovement [SimTalk]

Continues the movement the designated pose of the object designated by &lt;Path&gt;.

Remarks

If you do not specify the optional parameter, all paused movements will be continued.

\_3D.Poses.continueMovement affects the designated pose, however always together with the other poses to which the object moved together with this pose in a common call of the method \_3D.Poses.moveTo .

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.continueMovement([Pose:string])
```

Parameter

The optional parameter Pose of data type string sets the name of the pose which the object moves.

If you do not specify the optional parameter, all paused movements will be continued.

Example

```simtalk
Station._3D.Poses.moveTo(["Pose1", "Pose2"])
Station._3D.Poses.continueMovement("Pose1") // instead, you can also enter: Station._3D.Poses.continueMovement("Pose2")
```

**See also**

_3D.Poses.moveTo [SimTalk] _3D.Poses.pauseMovement [SimTalk] _3D.MovementInterruptible [SimTalk] _3D.Poses.EndPoseWasReached [SimTalk]

#### \_3D.Poses.EndPoseWasReached [SimTalk]

Returns if all pose runs for the object designated by &lt;Path&gt; came to an end (true) or not (false).

Remarks

It does not matter if the pose runs came to a regular end or if they were canceled with the methods \_3D.Poses.cancelMovement or \_3D.Poses.stopMovement .

Pose runs that are only paused by \_3D.Poses.pauseMovement or by failures or pauses, will not set \_3D.Poses.EndPoseWasReached to true.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.Poses.EndPoseWasReached → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
Station._3D.Poses.moveTo("Pose1")
waituntil Station._3D.Poses.EndPoseWasReached
```

**See also**

- \_3D.Poses.cancelMovement [SimTalk]
- \_3D.Poses.continueMovement [SimTalk]
- \_3D.Poses.isMovingTo [SimTalk]
- \_3D.Poses.moveTo [SimTalk]
- \_3D.Poses.moveToCoordinate [SimTalk]

\_3D.Poses.pauseMovement [SimTalk] \_3D.Poses.stopMovement [SimTalk]

#### \_3D.Poses.getAnimationTime [SimTalk]

Returns how long the movement toward the designated pose of the object designated by &lt;Path&gt; takes.

Remarks

If you do not specify the optional parameter, the method returns the simulation time which remains until all pose movements and movements caused by the methods \_3D.Poses.moveToCoordinate or moveTo respectively, are processed, provided that \_3D.Poses.pauseMovement does not cause a delay.

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.getAnimationTime([Pose:string])
```

Parameter

The optional parameter Pose of data type string sets the name of the pose toward which the object moves.

Example

```simtalk
print Station._3D.Poses.getAnimationTime
print Station._3D.Poses.getAnimationTime("Pose1")
```

SimTalk

- \_3D.Poses.moveToCoordinate [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]

moveTo [SimTalk]

_3D.Poses.getTable [SimTalk]

#### \_3D.Poses.getTable [SimTalk]

Returns the poses of the object designated by &lt;Path&gt; and writes them into the specified table.

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.getTable(Poses:table)
```

Parameter

The parameter Poses of data type table designates the table in which the data of the poses are going to be written.

Example

```simtalk
var t : table
MyStation._3D.Poses.getTable(t)
MyStation._3D.Poses.setTable(t)
```

See also

\_3D.Poses.setTable [SimTalk]

#### \_3D.Poses.isMovingTo [SimTalk]

Returns if the object designated by &lt;Path&gt; moves toward the designated pose.

Remarks

\_3D.Poses.isMovingTo affects the designated pose, however always together with the other poses to which the object moved together with this pose in a common call of the method \_3D.Poses.moveTo .

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.isMovingTo(Pose:string) → boolean
```

**Parameter**

The parameter Pose of data type string sets the name of the pose toward which the object moves.

Return Value

The return value has the data type boolean .

true if the object moves toward the pose.

false if the object does not move toward the pose.

If the pose name is either empty or does not match any existing pose, the method returns an error.

**Example**

```simtalk
print Station._3D.Poses.isMovingTo("Pose1")
```

See also

- \_3D.Poses.moveTo [SimTalk]
- \_3D.MovementInterruptible [SimTalk]
- \_3D.Poses.EndPoseWasReached [SimTalk]

#### \_3D.Poses.moveTo [SimTalk]

Moves to one or several poses of the object designated by &lt;Path&gt;.

Remarks

**Note**

Whenever you change the Lower Limit / upper Limit , the Velocity , the Acceleration , or the Joint Type of an animatable object, the initial position for the next pose run that affects this object returns to 0.

When all pose runs of an object reached their destination, Plant Simulation enters an EndOfTime event into the Event List .

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.moveTo(Pose:string[, TimeSpan:time]) → time < Path >._3D.Poses.moveTo(Poses:array[string][, TimeSpan:time]]) → time < Path >._3D.Poses.moveTo(Poses:array[string][, TimeSpans:array[time]]) → time
```

**Parameters**

- The parameter Pose of data type string sets the name of the pose toward which the object moves.

The parameter Poses designates an array of data type string containing the names of several consecutive poses. The object moves to the designated poses sequentially one after the other.

If you specify invalid parameters or if you specify a pose that contains an animatable object that is part of a movement that is still active, the method opens the Method Debugger with an error. In this context a pose movement always consists of all poses that are specified together with the method \_3D.Poses.moveTo . It stays active until the last pose is reached.

If the object is to move to a pose named "init" and no pose with that name exists, the object moves to an implicit pose which sets all animatable objects of the object designated by &lt;Path&gt; to 0.

- The optional parameter TimeSpan of data type time sets the duration of the movement.

The optional parameter TimeSpans designates an array of data type time , which sets the durations of the movement.

If you do not specify the parameter, the pose movement is run with the time which results from the speeds from the joint definitions of the involved animatable objects.

If you specify the parameter, it means the following:

- If you specify a single time , the entire pose movement has to take place within the specified time. The time relations of the joints and the individual pose movements among each other are retained. If the instruction Station.\_3D.Poses.moveTo(["Pose1", "Pose2"]) takes 3 seconds, of which 1 second is allotted to Pose1 and 2 seconds are allotted to Pose2, then the instruction Station.\_3D.Poses.moveTo(["Pose1", "Pose2"], 7.5) takes 7.5 seconds of which 2.5 seconds are allotted to Pose1 and 5 seconds are allotted to Pose2.
- If you specify a sequence of times in an array , the first pose is to be reached within the first time span, the second pose in the second time span, etc. You have to specify as many time spans as you defined poses.

The instruction Station.\_3D.Poses.moveTo(["Pose1", "Pose2"], 7.5) from the example above and the instruction Station.\_3D.Poses.moveTo(["Pose1", "Pose2"], [2.5, 5]) thus are equivalent. You can only specify an array of times if you also specified an array of poses .

The instruction Station.\_3D.Poses.moveTo("Pose1", [7.5]) results in an error although the same number of poses is specified as the number of time spans. The instruction Station.\_3D.Poses.moveTo(["Pose1"], [7.5]) does not result in an error, but is unnecessarily complicated because the instruction Station.\_3D.Poses.moveTo("Pose1", 7.5)) yields the same result without specifying an array at all.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated pose movement will probably take, provided it will not be interrupted.

**Example**

Station._3D.Poses.moveTo(["Pose1", "Pose2"]) Station._3D.Poses.moveTo(["Pose1", "Pose2"], 7.5) Station._3D.Poses.moveTo("Pose1", 7.5)

**SimTalk**

moveTo [SimTalk] _3D.Poses.moveToCoordinate [SimTalk] _3D.Poses.moveToMU [SimTalk] _3D.Poses.moveToMUAnimationPosition [SimTalk] moveToCoordinate [SimTalk] moveToMU [SimTalk]

moveToMUAnimationPosition [SimTalk]

- \_3D.Poses.isMovingTo [SimTalk]
- \_3D.Poses.cancelMovement [SimTalk]
- \_3D.Poses.continueMovement [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]
- \_3D.Poses.EndPoseWasReached [SimTalk]
- \_3D.MovementInterruptible [SimTalk]
- \_3D.AniRotationAxis [SimTalk]
- \_3D.AniRotationCenter [SimTalk]
- \_3D.AniTranslationDirection [SimTalk]

See also

Joint Settings for the Animation

Open and Close the Gate with Poses

Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=pGkDwvoDw3LOD4Wo&amp;t=1130](https://youtu.be/rQi5oRyZckQ?si=pGkDwvoDw3LOD4Wo&t=1130)

[https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&amp;t=269](https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&t=269)

#### \_3D.Poses.moveToCoordinate [SimTalk]

Moves the object designated by &lt;Path&gt; to the specified coordinate with its first animation point to the designated coordinate and to the designated rotation as long as the identified robot configuration supports this. This works without you having to define a pose.

Remarks

\_3D.Poses.moveToCoordinate does not support the four axis robot with ball joint gripper. The object corresponds to one of the supported robot configurations.

Plant Simulation checks the attribute \_3D.AnimationObject to identify the robot configuration. The objects, which are located between the simulation object, which is excluded, and \_3D.AnimationObject , which is included, are checked for the appropriate robot configuration with which the pose movement is executed.

Plant Simulation checks if a part of the axes configuration matches a supported robot type from the simulation object level to the gripper object. A robot type with more axes takes precedence over a robot type with fewer axes.

**Note**

If Plant Simulation cannot identify the robot configuration, this is considered an error and the Method Debugger will open.

**Note**

Not reaching the destination coordinate/rotation is not considered an error and does not open the Method Debugger . An unsuitable, but recognizable axes configuration will not be recognized, if eight axes exist, for example, but only the last three axes are recognized as part of a simpler robot type.

**Note**

Plant Simulation does not use joint limits in this method. This means, that you can move to a position beyond the limits you specified.

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.moveToCoordinate(Coordinate:length[3], Rotation:real/ real[4][, TimeSpan:time])
-> time
```

**Parameters**

You can specify the following parameters:

- The parameter Coordinate is an array of data type length with three values which designates the destination coordinate in the coordinate system of the object to be moved.
- The parameter Rotation is a value of data type real which designates a rotation around the negative z-axis.

You can also specify the parameter Rotation as an array of data type real with four values. It designates a rotation, compare \_3D.Rotation , which the animation point of the object to be moved is to take within its coordinate system after finishing the pose movement.

- The optional parameter TimeSpan of data type time sets the duration of the movement.

If you do not specify the parameter, Plant Simulation runs the movement run with the time which results from the speed from the joint definition of this animatable object.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Examples**

Station._3D.Poses.moveToCoordinate([1m, 2m, 0m], 0) Station._3D.Poses.moveToCoordinate([1m, 2m, 0m], 45, 1:00) Station._3D.Poses.moveToCoordinate([1m, 2m, 0m], [90, 0, 1, 0]) Station._3D.Poses.moveToCoordinate(Station._3D.getPositionFromObject(OtherSt ations), 0)

```simtalk
var Rotation = Station._3D.getRotationFromObject(OtherObject)
Rotation := F3DconcatenateRotations(Station._3D.getRotationFromObject(OtherObject), [180, 0, 1, 0])
Station._3D.Poses.moveToCoordinate(Station._3D.getPositionFromObject(OtherOb ject), Rotation) // grip 'OtherObject' from above
```

**SimTalk**

moveToCoordinate [SimTalk]

\_3D.Poses.moveTo [SimTalk]

\_3D.Poses.moveToMU [SimTalk] \_3D.Poses.moveToMUAnimationPosition [SimTalk] moveTo [SimTalk] moveToMU [SimTalk] moveToMUAnimationPosition [SimTalk] \_3D.Poses.cancelMovement [SimTalk] \_3D.Poses.continueMovement [SimTalk] \_3D.Poses.pauseMovement [SimTalk] \_3D.Poses.EndPoseWasReached [SimTalk] \_3D.MovementInterruptible [SimTalk] \_3D.AnimationObject [SimTalk] \_3D.Rotation [SimTalk] See also Configuring the Robot in 3D

#### \_3D.Poses.moveToMU [SimTalk]

Moves the object designated by &lt;Path&gt; with its first animation point to the specified MU instance as long as the identified robot configuration supports this. This works without you having to define a pose.

Remarks

\_3D.Poses.moveToMU does not support the four axis robot with ball joint gripper . The object corresponds to one of the supported robot configurations.

Plant Simulation checks the attribute \_3D.AnimationObject to identify the robot configuration. The objects, which are located between the simulation object, which is excluded, and \_3D.AnimationObject , which is included, are checked for the appropriate robot configuration with which the pose movement is executed.

Plant Simulation checks if a component of the axes configuration matches a supported robot type from the simulation object level to the gripper object. A robot type with more axes takes precedence over a robot type with fewer axes.

**Note**

If Plant Simulation cannot identify the robot configuration, this is considered an error and the Method Debugger will open.

**Note**

Not reaching the destination MU instance is not considered an error and does not open the Method Debugger . An unsuitable, but recognizable axes configuration will not be recognized, if eight axes exist, for example, but only the last three axes are recognized as part of a simpler robot type.

Type

Method

Syntax

```simtalk
< Path >_3D.Poses.moveToMU(MU:object[, TimeSpan:time])
-> time
```

**Parameters**

You can specify the following parameters:

- The parameter MU of data type object designates the MU instance to which the object is to move.
- The optional parameter TimeSpan of data type time sets the duration of the movement.

If you do not specify the parameter, Plant Simulation executes the movement run with the time which results from the speed from the joint definition of the involved animatable objects.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Examples**

```simtalk
var mu = otherObject.cont
var arm = self.~._3D.getObject("Arm")
wait arm.moveToMU(mu)
-- control MyRob action to pick parts at the store -- and drop them on the station
var nextPart : object
for var i := 1 to 12 nextPart = Store.cont
	waituntil station.empty -- move to part and load it wait MyRob._3D.Poses.MoveToMU(nextPart)
	nextPart.move(MyRob) wait 1 -- move to target station and drop part there wait MyRob._3D.Poses.MoveToMUAnimationPosition(nextPart, Station)
	nextPart.move(Station) wait 1 -- move robot to home position wait MyRob._3D.Poses.moveTo("home") next
```

**SimTalk**

**moveToMU [SimTalk]**

- \_3D.Poses.moveTo [SimTalk]
- \_3D.Poses.moveToCoordinate [SimTalk]
- \_3D.Poses.moveToMUAnimationPosition [SimTalk]

moveTo [SimTalk]

- moveToCoordinate [SimTalk]

moveToMUAnimationPosition [SimTalk]

- \_3D.Poses.cancelMovement [SimTalk]
- \_3D.Poses.continueMovement [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]
- \_3D.Poses.EndPoseWasReached [SimTalk]
- \_3D.MovementInterruptible [SimTalk]
- \_3D.AnimationObject [SimTalk]

**See also**

**Joint**

#### \_3D.Poses.moveToMUAnimationPosition [SimTalk]

Moves the object designated by &lt;Path&gt; with its first animation point to the position and rotation in space where the specified MU instance would be located when being moved to the specified place as long as the identified robot configuration supports this. This works without you having to define a pose.

Remarks

\_3D.Poses.moveToMUAnimationPosition does not support the four axis robot with ball joint gripper . The object corresponds to one of the supported robot configurations.

Plant Simulation checks the attribute \_3D.AnimationObject to identify the robot configuration. The objects, which are located between the simulation object, which is excluded, and \_3D.AnimationObject , which is included, are checked for the appropriate robot configuration with which the pose movement is executed.

Plant Simulation checks if a part of the axes configuration matches a supported robot type from the simulation object level to the gripper object. A robot type with more axes takes precedence over a robot type with fewer axes.

**Note**

If Plant Simulation cannot identify the robot configuration, this is considered an error and the Method Debugger will open.

**Note**

Not reaching the destination place is not considered an error and does not open the Method Debugger . An unsuitable, but recognizable axes configuration will not be recognized, if eight axes exist, for example, but only the last three axes are recognized as part of a simpler robot type.

**Note**

Plant Simulation does not use joint limits in this method. This means, that you can move to a position beyond the limits you specified.

Type

Method

Syntax

&lt; Path &gt;.\_3D.Poses.moveToMUAnimationPosition(MU:object, TargetPE:object/PE[, RelPos/AbsPos:real/length, TimeSpan:time]) -&gt; time

**Parameters**

- The parameter MU of data type object designates the MU instance to measure when moving to the target place.
- The parameter TargetPE of data type object designates the place to which the item is to move. This can be a specific PE , or an object if the object only has one PE.
- The optional parameter RelPos/AbsPos designates a value of data type real or length .

If the value has the data type real , it designates the relative position on the object. The relative position can be a value between 0 and 1. 0 designates the start of the animation and 1 the end of the animation, i.e., the value 100 %.

If the value has the data type length , it designates the absolute position on the object as the distance starting at the beginning of the object.

This parameter will only be used if TargetPE specifies a length-oriented place, e.g. a Conveyor or a Transporter with a length-oriented loadbay.

If you do not specify the parameter, it takes the value 0.0.

- The optional parameter TimeSpan of data type time designates the duration of the movement.

If you do not specify the parameter, the movement is run with the time which results from the speeds from the joint definitions of the involved animatable objects.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Examples**

```simtalk
var mu = otherObject.cont
wait self.~._3D.moveToMUAnimationPosition(mu) -- control MyRob action to pick parts at the store -- and drop them on the station
var nextPart : object
for var i := 1 to 12 nextPart = Store.cont
	waituntil station.empty -- move to part and load it wait MyRob._3D.Poses.MoveToMU(nextPart)
	nextPart.move(MyRob) wait 1
-- move to target station and drop part there wait MyRob._3D.Poses.MoveToMUAnimationPosition(nextPart, Station)
nextPart.move(Station)
wait 1 -- move robot to home position wait MyRob._3D.Poses.moveTo("home") next
```

**SimTalk**

**moveToMUAnimationPosition [SimTalk]**

```simtalk
_3D.Poses.moveTo [SimTalk]
_3D.Poses.moveToMU [SimTalk]
_3D.Poses.moveToCoordinate [SimTalk] moveTo [SimTalk] moveToCoordinate [SimTalk] moveToMU [SimTalk]
_3D.Poses.cancelMovement [SimTalk]
_3D.Poses.continueMovement [SimTalk]
_3D.Poses.pauseMovement [SimTalk]
_3D.Poses.EndPoseWasReached [SimTalk]
_3D.MovementInterruptible [SimTalk]
_3D.getMUAnimationPosition [SimTalk]
_3D.getMUAnimationRotation [SimTalk]
_3D.AnimationObject [SimTalk] See also Configuring the Robot in 3D
```

#### \_3D.Poses.pauseMovement [SimTalk]

Pauses the movement toward the designated pose of the object designated by &lt;Path&gt;.

Remarks

If you do not specify the optional parameter, all movements will be paused.

\_3D.Poses.pauseMovement affects the designated pose, however always together with the other poses to which the object moved together with this pose in a common call of the method \_3D.Poses.moveTo .

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.pauseMovement([Pose:string])
```

Parameter

The optional parameter Pose of data type string sets the name of the pose toward which the object moves.

Example

Station._3D.Poses.moveTo(["Pose1", "Pose2"]) Station._3D.Poses.pauseMovement("Pose1") // instead, you can also enter: Station._3D.Poses.pauseMovement("Pose2")

**See also**

```simtalk
_3D.Poses.moveTo [SimTalk]
_3D.Poses.continueMovement [SimTalk]
_3D.MovementInterruptible [SimTalk]
_3D.Poses.EndPoseWasReached [SimTalk]
```

#### \_3D.Poses.setTable [SimTalk]

Sets the poses of the object designated by &lt;Path&gt; from the specified table.

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.setTable(Poses:table)
```

Parameter

The parameter Poses of data type table designates the table which contains the data of the poses.

Example

```simtalk
var t : table
MyStation._3D.Poses.getTable(t)
MyStation._3D.Poses.setTable(t)
```

See also

_3D.Poses.getTable [SimTalk]

#### \_3D.Poses.stopMovement [SimTalk]

Stops the movement toward the designated pose of the object designated by &lt;Path&gt; and, if you entered a deceleration for the joints, decelerates toward a halt.

Remarks

Do not specify the optional parameter to stop all movements.

\_3D.Poses.stopMovement affects the designated pose, however always together with the other poses to which the object moved together with this pose in a common call of the method \_3D.Poses.moveTo .

Remarks

**\_3D.Poses.stopMovement [SimTalk]**

Type

Method

Syntax

```simtalk
< Path >._3D.Poses.stopMovement([Pose:string])
-> time
```

Parameter

The optional parameter Pose of data type string sets the name of the pose toward which the object moves.

Return Value

The return value has the data type time .

Example

```simtalk
Station._3D.Poses.moveTo(["Pose1", "Pose2"])
wait Station._3D.Poses.stopMovement("Pose1") // instead, you can also enter: wait Station._3D.Poses.stopMovement("Pose2")
```

**See also**

_3D.Poses.cancelMovement [SimTalk] _3D.Poses.moveTo [SimTalk] _3D.Poses.pauseMovement [SimTalk] _3D.MovementInterruptible [SimTalk] _3D.Poses.EndPoseWasReached [SimTalk]

#### \_3D.SynchronizedJoints [SimTalk]

Sets if moving toward a pose will synchronize the joints, so that all joints, that are part of the movement, reach the target state at the same time ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.SynchronizedJoints:boolean

Assignment Value

You can assign a value of data type boolean .

Example

.MaterialFlow.Station.\_3D.SynchronizedJoints := true

SimTalk

**\_\_Accessing Poses**

See also

Poses

Synchronized Joints

