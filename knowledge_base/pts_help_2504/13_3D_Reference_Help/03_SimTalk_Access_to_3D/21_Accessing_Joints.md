### Accessing Joints

#### \_\_Accessing Joints

SimTalk provides the functions listed in the table of contents to the left for accessing joints in 3D.

See also

Joint

Poses

\_\_Accessing Poses

#### \_3D.JointUseShortestRotationDirection [SimTalk]

Sets if the rotational joint of the object designated by &lt;Path&gt; uses the spatially shortest direction toward its target orientations ( true ) or not ( false ).

Remarks

If the joint uses the spatially shortest direction, you cannot specify joint limits.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.JointUseShortestRotationDirection:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCrane._3D.getObject(1).JointUseShortestRotationDirection := true
```

See also

Type of Joint &gt; Revolute Joint

Use Shortest Rotation Direction

JointLowerLimitActive [SimTalk]

JointLowerLimit [SimTalk]

JointUpperLimitActive [SimTalk]

JointUpperLimit [SimTalk]

#### JointAcceleration [SimTalk]

Sets the acceleration of the joint of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.JointAcceleration:acceleration

**Assignment Value**

- For a Prismatic Joint the value designates the acceleration in meters per second squared.

For a Prismatic Joint you assign a value of data type acceleration .

- For a Revolute Joint the value designates the acceleration in degrees per second squared.

For a Revolute Joint you assign a value of data type real .

**Example**

```simtalk
MyStation._3D.getObject(1).JointAcceleration := 0.3
```

See also

\_3D.getObject [SimTalk]

Acceleration [text box] - joint

JointDeceleration [SimTalk]

#### JointCurrentValue [SimTalk]

Returns the current joint value of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.JointCurrentValue -&gt; length

**Return Value**

- For a Prismatic Joint this is a value in meters.

For a Prismatic Joint the return value has the data type length .

- For a Revolute Joint this is a value in ° (degrees).

For a Revolute Joint the return value has the data type real .

**Example**

print MyStation.\_3D.getObject(1).JointCurrentValue

**See also**

\_3D.getObject [SimTalk]

JointVelocity [SimTalk]

JointLowerLimit [SimTalk]

JointUpperLimit [SimTalk]

#### JointDeceleration [SimTalk]

Sets the deceleration of the joint of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.JointDeceleration:acceleration

**Assignment Value**

- For a Prismatic Joint the value designates the deceleration in meters per second squared.

For a Prismatic Joint you can assign a value of data type acceleration .

- For a Revolute Joint the value designates the deceleration in degrees per second squared. For a Revolute Joint you assign a value of data type real .

**Example**

```simtalk
MyStation._3D.getObject(1).JointDeceleration := 0.3
```

See also

Acceleration [text box] - joint

\_3D.getObject [SimTalk]

Acceleration [text box] - joint

JointAcceleration [SimTalk]

#### JointLowerLimit [SimTalk]

Sets the lower limit of the joint of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.JointLowerLimit:length

**Remarks**

Plant Simulation exclusively uses limits while defining poses . It does not use them to influence any other behavior, such as \_3D.Poses.moveToCoordinate [SimTalk] , \_3D.Poses.moveToMU [SimTalk] , etc.

**Assignment Value**

- For a Translation the value is in meters.

For a Translation you assign a value of data type length .

- For a Rotation the value is in degrees. \_3D.getObject eanbles you to access animatable objects. For a rotation you assign a value of data type real .

**Example**

```simtalk
MyStation._3D.getObject(1).JointLowerLimit := 43
```

**See also**

\_3D.getObject [SimTalk]

Lower Limit

#### JointLowerLimitActive [SimTalk]

Sets if the lower limit of the joint of the object designated by &lt;Path&gt; is active ( true ) or not ( false ).

Remarks

\_3D.getObject enables you to access animatable objects.

Type

Attribute

Syntax

```simtalk
< Path >.JointLowerLimitActive:boolean
```

Assignment Value

You can assign a value of data type boolean .

Specify true to activate the limit if it has not been activated before. It will be activated with the other active limit if the other limit (upper/lower) has a value. It will be activated with 0 if no value was assigned.

**Examples**

MyStation._3D.getObject(1).JointLowerLimitActive

```simtalk
// Let's suppose: The value of the lower limit is 3 (_3D.getObject(1).JointLowerLimit = 3) // the lower limit is activated (_3D.getObject(1).JointLowerLimitActive = true) // the lower limit is not activated (_3D.getObject(1).JointUpperLimitActive = false)
_3D.getObject(1).JointUpperLimitActive := true // activates the upper limit and sets it to 3
// Let's suppose: The lower limit is not activated (_3D.getObject(1).JointLowerLimitActive = false) // the upper limit is activate (_3D.getObject(1).JointUpperLimitActive = false)
_3D.getObject(1).JointLowerLimitActive := true // activates the upper limit and sets it to 0
```

See also \_3D.getObject [SimTalk] Lower Limit

\_3D.JointUseShortestRotationDirection [SimTalk]

#### JointType [SimTalk]

Sets the type of joint of the object designated by &lt;Path&gt;.

Remarks

\_3D.getObject enables you to access animatable objects.

Type

Attribute

Syntax

```simtalk
< Path >.JointType:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Prismatic joint" or "Revolute joint" .

Example

```simtalk
MyStation._3D.getObject(1).JointType := "Revolute joint"
```

See also

\_3D.getObject [SimTalk]

Type of Joint

#### JointUpperLimit [SimTalk]

Sets the upper limit of the joint of the object designated by &lt;Path&gt;.

Type

Attribute

Remarks

Plant Simulation exclusively uses limits while defining poses . It does not use them to influence any other behavior, such as \_3D.Poses.moveToCoordinate [SimTalk] , \_3D.Poses.moveToMU [SimTalk] , etc.

Syntax

&lt; Path &gt;.JointUpperLimit:length

**Assignment Value**

- For a Translation the value is in meters.

For a Translation you assign a value of data type length .

- For a Rotation the value is in degrees. \_3D.getObject enables you to access animatable objects.

For a Rotation you assign a value of data type real .

**Example**

```simtalk
MyStation._3D.getObject(1).JointUpperLimit := 25
```

See also

\_3D.getObject [SimTalk]

Upper Limit

#### JointUpperLimitActive [SimTalk]

Sets if the upper limit of the joint of the object designated by &lt;Path&gt; is active ( true ) or not ( false ).

Remarks

\_3D.getObject enables you to access animatable objects.

Type

Attribute

Syntax

&lt; Path &gt;.JointUpperLimitActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyStation.\_3D.getObject(1).JointUpperLimitActive := true

See also

\_3D.getObject [SimTalk]

Upper Limit

\_3D.JointUseShortestRotationDirection [SimTalk]

#### JointVelocity [SimTalk]

Sets the speed of the joint of the object designated by &lt;Path&gt;.

**Remarks**

An animatable object with the Velocity of 0 does not rotate with the Turntable when the Turntable rotates. This applies when the insertion position of the animatable object is located on the animation rotation axis of the Turntable . This is the case if the insertion point is exactly located on the animation rotation center or is reachable from there along the animation rotation axis without a sideways deviation.

<!-- image -->

This behavior resembles a real Turntable with a fixed base and a rotating table.

\_3D.getObject enables you to access animatable objects.

Type

Attribute

Syntax

&lt; Path &gt;.JointVelocity:speed

**Assignment Value**

- For a Prismatic Joint the value designates the velocity in meters per second.
- For a Prismatic Joint you assign a value of data type speed .
- For a Revolute Joint the value designates the angular velocity in degrees per second.

For a Revolute Joint you assign a value of data type real .

**Example**

```simtalk
MyStation._3D.getObject(1).JointVelocity := 25
```

See also

Velocity [joint]

JointAcceleration [SimTalk]

JointDeceleration [SimTalk]

\_3D.getObject [SimTalk]

Turntable [object]

#### moveTo [SimTalk]

Moves to one or several positions or rotations of the joint of the object designated by &lt;Path&gt;.

Remarks

A moveTo call of an animatable object aborts a previous moveTo run of the same animatable object. For active movements to poses or movements, which the method \_3D.Poses.moveToCoordinate started, a conflict arises if this animatable object is part of the other active movement.

**Note**

Whenever you change Limits , Velocity , Acceleration , or the Joint Type of the animatable object, the initial position for the next pose run that affects this object returns to 0.

**Note**

Plant Simulation does not use joint limits in this method. This means, that you can move to a position beyond the limits you specified.

Type

Method

Syntax

```simtalk
< Path >.moveTo(PositionOrRotationAngle:real[, TimeSpan:time]) → time < Path >.moveTo(PositionsOrRotationAngles:array[real][, TimeSpan:time]) → time < Path >.moveTo(PositionsOrRotationAngles:array[real][, TimeSpans:array[time]]) → time
```

**Parameters**

- The parameter PositionOrRotationAngle of data type real sets the position or the rotation angle of the joint toward which the object moves.

The parameter PositionsOrRotationAngles designates an array of data type real that sets a sequence of positions or rotation angles of the joint to which the object moves. The designated positions or rotations are then approached sequentially one after the other.

The movement stays active until the last position or rotation is reached.

- The optional parameter TimeSpan of data type time sets the duration of the movement.

The optional parameter TimeSpans designates an array of data type time , which sets the durations of the movement.

**moveTo [SimTalk]**

Do not specify the parameter to run the pose movement with the time which results from the speeds from the joint definitions of the involved animatable object.

If you specify the parameter, it means the following:

- If you specify a single time , the entire movement has to take place within the specified time.
- If you specify a sequence of times in an array , the first position or rotation is to be reached within the first time span, the second pose in the second time span, etc. You have to specify as many time spans as you defined positions or rotations.

You can only specify an array of times if you also specified an array of positions or rotations .

The instruction Station.\_3D.getObject(1).moveTo(3, [7.5]) results in an error although the same number of positions is specified as the number of time spans. The instruction Station.\_3D.getObject(1).moveTo([3], [7.5]) does not result in an error, but is unnecessarily complicated because the instruction Station.\_3D.getObject(1).moveTo(3, 7.5)) yields the same result without specifying an array at all.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated pose movement will probably take, provided it will not be interrupted.

**Example**

Station._3D.getObject(1).moveTo(3, -1) Station._3D.getObject(1).moveTo([3, -1], 7.5) Station._3D.getObject(1).moveTo(3, 7.5)

**SimTalk**

- \_3D.Poses.moveTo [SimTalk]

moveToMU [SimTalk] moveToCoordinate [SimTalk] moveToMUAnimationPosition [SimTalk] _3D.Poses.moveToMU [SimTalk] _3D.Poses.moveToMUAnimationPosition [SimTalk] _3D.Poses.moveToCoordinate [SimTalk] _3D.Poses.cancelMovement [SimTalk]

- \_3D.Poses.continueMovement [SimTalk]
- \_3D.Poses.pauseMovement [SimTalk]
- \_3D.Poses.EndPoseWasReached [SimTalk]
- \_3D.MovementInterruptible [SimTalk]
- \_3D.AniRotationAxis [SimTalk]
- \_3D.AniRotationCenter [SimTalk]
- \_3D.AniTranslationDirection [SimTalk]

See also

**Joint**

Open and Close the Gate without Poses

Move the Gate Up to the Height of the Part

#### moveToCoordinate [SimTalk]

Moves the joint designated by &lt;Path&gt; to the specified coordinate.

Remarks

When moving a joint to a coordinate, Plant Simulation computes the target joint state based upon a relaxed state at which the origin of the joint is located at the position [0,0,0]. The joint points toward the direction specified in the attribute \_3D.AniTranslationDirection in its reset coordinate system.

**Note**

Plant Simulation does not use joint limits in this method. This means, that you can move to a position beyond the limits you specified.

Type

Method

Syntax

&lt; Path &gt;.moveToCoordinate(Coordinate:length[3][, TimeSpan:time]) -&gt; time

**Parameters**

- The parameter Coordinate is an array of data type length which specifies the coordinate to which the joint is to move in the joint's coordinate system.

**Note**

The joint's coordinate system includes its animation state. This also means that if you first compute the coordinate to move to, then move the joint, and then call moveToCoordinate , you will end up at another coordinate as the coordinate which you might have intended to.

- The optional parameter TimeSpan of data type time sets the duration of the movement.

If you do not specify the parameter, Plant Simulation runs the movement run with the time which results from the speed from the joint definition of this animatable object.

Return Value

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Example**

```simtalk
var destObj = ?.succ
var arm = self.~._3D.getObject("Arm")
var destPos = destObj._3D.getMUAnimationPosition
destPos.z += @.MUHeight
wait arm.moveToCoordinate(arm.getPositionOfObject(destObj, destPos))
```

**SimTalk**

```simtalk
_3D.Poses.moveToCoordinate [SimTalk] moveTo [SimTalk] moveToMU [SimTalk] moveToMUAnimationPosition [SimTalk]
_3D.Poses.moveTo [SimTalk]
_3D.Poses.moveToMU [SimTalk]
_3D.Poses.moveToMUAnimationPosition [SimTalk]
_3D.Poses.cancelMovement [SimTalk]
_3D.Poses.continueMovement [SimTalk]
_3D.Poses.pauseMovement [SimTalk]
_3D.Poses.EndPoseWasReached [SimTalk]
_3D.MovementInterruptible [SimTalk] See also Joint Video on YouTube https://youtu.be/wfVN-mcWNsc?si=Un-c8tYPrM135pgG&t=479
```

#### moveToMU [SimTalk]

Moves the joint designated by &lt;Path&gt; to the specified MU instance.

Remarks

When moving a joint to an MU instance, Plant Simulation computes the target joint state based upon a relaxed state at which the origin of the joint is located at the position [0,0,0]. The joint points toward the direction specified in the attribute \_3D.AniTranslationDirection in its reset coordinate system.

**Note**

Plant Simulation does not use joint limits in this method. That means you can move to a position beyond the limits you specified.

Type

Method

Syntax

```simtalk
< Path >.moveToMU(MU:object[, TimeSpan:time])
-> time
```

**Parameters**

- The parameter MU of data type object designates the MU instance to which the joint moves to.
- The optional parameter TimeSpan of data type time sets the duration of the movement.

If you do not specify the parameter, Plant Simulation executes the movement run with the time which results from the speed from the joint definition of this animatable object.

Return Value

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Example**

```simtalk
var mu = otherObject.cont
var arm = self.~._3D.getObject("Arm")
wait arm.moveToMU(mu)
```

SimTalk

\_3D.Poses.moveToMU [SimTalk] moveTo [SimTalk] moveToCoordinate [SimTalk] moveToMUAnimationPosition [SimTalk] \_3D.Poses.moveTo [SimTalk] \_3D.Poses.moveToMUAnimationPosition [SimTalk] \_3D.Poses.moveToCoordinate [SimTalk] \_3D.Poses.cancelMovement [SimTalk] \_3D.Poses.continueMovement [SimTalk] \_3D.Poses.pauseMovement [SimTalk] \_3D.Poses.EndPoseWasReached [SimTalk] \_3D.MovementInterruptible [SimTalk] See also Joint

#### moveToMUAnimationPosition [SimTalk]

Moves the joint designated by &lt;Path&gt; to the position and rotation in space where the specified MU instance would be located when being moved to the specified place.

**Remarks**

When moving a joint to a MU instance, Plant Simulation computes the target joint state based upon a relaxed state at which the origin of the joint is located at the position [0,0,0]. The joint points toward the direction specified in the attribute \_3D.AniTranslationDirection in its reset coordinate system.

**Note**

Plant Simulation does not use joint limits in this method. This means, that you can move to a position beyond the limits you specified.

Type

Method

Syntax

```simtalk
< Path >.moveToMUAnimationPosition(MU:object, TargetPE:object/PE[, RelPos/ AbsPos:real/length, TimeSpan:time])
-> time
```

**Parameters**

- The parameter MU of data type object designates the MU instance to measure when moving to the target place.
- The parameter TargetPE of data type object designates the place to which the item is to move. This can be a specific PE or an object if the object only has one PE.
- The optional parameter RelPos/AbsPos designates a value of data type real or length .

If the value has the data type real , it designates the relative position on the object. The relative position can be a value between 0 and 1. 0 designates the start of the animation and 1 the end of the animation, i.e., the value 100 %.

If the value has the data type length , it designates the absolute position on the object as the distance starting at the beginning of the object.

This parameter will only be used if TargetPE specifies a length-oriented place, e.g. a Conveyor or a Transporter with a length-oriented loadbay.

If you do not specify the parameter, it takes the value 0.0.

- The optional parameter TimeSpan of data type time designates the duration of the movement.

If you do not specify the parameter, Plant Simulation runs the movement run with the time which results from the speed from the joint definition of this animatable object.

**Return Value**

The return value has the data type time .

It designates the time span of the simulation time which the designated movement will probably take, provided it will not be interrupted.

**Example**

```simtalk
var mu = otherObject.cont
var arm = self.~._3D.getObject("Arm")
wait arm.moveToMUAnimationPosition(mu)
```

**SimTalk**

- \_3D.Poses.moveToMUAnimationPosition [SimTalk]

```simtalk
moveTo [SimTalk] moveToCoordinate [SimTalk] moveToMU [SimTalk]
_3D.Poses.moveTo [SimTalk]
_3D.Poses.moveToMU [SimTalk]
_3D.Poses.moveToCoordinate [SimTalk]
_3D.Poses.cancelMovement [SimTalk]
_3D.Poses.continueMovement [SimTalk]
_3D.Poses.pauseMovement [SimTalk]
_3D.Poses.EndPoseWasReached [SimTalk]
_3D.MovementInterruptible [SimTalk]
_3D.getMUAnimationPosition [SimTalk]
_3D.getMUAnimationRotation [SimTalk]
```

**Accessing Poses**

See also

Joint

