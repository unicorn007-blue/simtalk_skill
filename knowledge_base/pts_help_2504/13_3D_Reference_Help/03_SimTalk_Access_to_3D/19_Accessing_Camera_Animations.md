### Accessing Camera Animations

#### \_\_Accessing Camera Animations

Plant Simulation provides a set of functions for Camera Animations .

Only the Frame provides Camera Animations .

You can buffer the entirety or all animations of a type in a value of data type any , for example:

```simtalk
var a : any := .Models.Model._3D.CameraAnimations
```

SimTalk provides the attributes and methods listed in the table of contents to the left for camera animations in 3D .

See also

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.delete [SimTalk]

Deletes the specified Camera Animation of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.delete → boolean < Path >._3D.CameraAnimations. getAnimation (<...>).delete → boolean
```

Return Value

The return value has the data type boolean .

true if the animation was deleted successfully.

false if the animation was not deleted.

Example

_3D.CameraAnimations.Default.delete

**See also**

\_3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.getTable [SimTalk]

Returns the animation data of all saved animations of the specified Camera Animation of the object designated by &lt;Path&gt; and writes it into the specified table.

Remarks

Plant Simulation automatically formats the passed table.

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.getTable(Target:table) < Path >._3D.CameraAnimations. getAnimation (<...>).getTable(Target:table)
```

**Parameter**

The parameter Target of data type table contains the data of each saved animation.

Example

```simtalk
// cama stands for camera animation
var cama:= _3D.CameraAnimations
var created : boolean := cama.createAnimationLine("Animation2")
if created // The animation line was created.
	var t: table // Copy the 'Default' line values to the table. cama.Default.getTable(t) cama.Animation2.setTable(t)
end
```

**See also**

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

_3D.CameraAnimations.<AnimationPathName>.setTable [SimTalk] _3D.CameraAnimations.getTable [SimTalk] _3D.CameraAnimations.setTable [SimTalk] _3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.IsCurve [SimTalk]

Returns if the specified Camera Animation of the object designated by &lt;Path&gt; is of type Polycurve or not.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.IsCurve → boolean < Path >._3D.CameraAnimations. getAnimation (<...>).IsCurve → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
var b : boolean := _3D.MUAnimations.Default.IsCurve
```

See also

\_3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.IsLine [SimTalk]

Returns if the specified Camera Animation of the object designated by &lt;Path&gt; is of type Lines or not.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.IsLine → boolean < Path >._3D.CameraAnimations. getAnimation (<...>).IsLine → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
var b : boolean := _3D.MUAnimations.Default.IsLine
```

See also

\_3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.IsSpline [SimTalk]

Returns if the specified Camera Animation of the object designated by &lt;Path&gt; is of type Spline or not.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.IsSpline → boolean < Path >._3D.CameraAnimations. getAnimation (<...>).IsSpline → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
var b : boolean := _3D.CameraAnimations.Default.IsSpline
```

See also

\_3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.play [SimTalk]

Schedules the saved Camera Animation of the Frame designated by &lt;Path&gt; and then plays the scheduled animations.

Remarks

Before executing the method an implicit call of the method CameraAnimations.reset takes place.

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.play([Backwards:boolean:=fal se, Factor:real:=1]) → time < Path >._3D.CameraAnimations. getAnimation (<...>).play([Backwards:boolean:=fal se]) → time
```

**Parameters**

- The optional parameter Backwards of data type boolean sets if the animation on the path is to be played backward ( true ) or forward ( false ).

Do not specify the parameter to play the animation on the path forward.

**Default Value of the Parameter**

The default value is false.

- The optional parameter Factor of data type real sets a positive factor, which Plant Simulation multiplies onto the animation speed.

Do not specify the parameter to make the animation run as-is, meaning with the factor 1.

Specify a factor of 0.5 to make the animation run slower.

Specify a factor of 2 to make the animation run twice as fast, meaning that it takes only half the time.

**Return Value**

The return value has the data type time .

It is the time that the specified animation takes.

**Example**

```simtalk
self.~._3D.CameraAnimations.VerticalAni.play self.~._3D.CameraAnimations.MyAnimationPath.play
```

**See also**

- \_3D.CameraAnimations.pause [SimTalk]
- \_3D.CameraAnimations.resetAnimation [SimTalk]
- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.schedule [SimTalk]
- \_3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.schedule [SimTalk]

Schedules a saved camera animation of the Frame designated by &lt;Path&gt;.

Remarks

To run the animation, call the function \_3D.CameraAnimations.play .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.schedule([Backwards:boolean: =false, Factor:real:=1]]) < Path >._3D.CameraAnimations. getAnimation (<...>).schedule([Backwards:boolean: =false])
```

**Parameters**

- The optional parameter Backwards of data type boolean sets if the animation on the path is to be played backward ( true ) or forward ( false ).

Do not specify the parameter to play the animation on the path forward.

**Default Value of the Parameter**

The default value is false.

- The optional parameter Factor of data type real sets a positive factor which Plant Simulation multiplies onto the animation speed.

Do not specify the parameter to make the animation run as-is, meaning with the factor 1.

Specify a factor of 0.5 to make the animation run slower.

Specify a factor of 2 to make the animation run twice as fast, meaning that it takes only half the time.

**Example**

```simtalk
self.~._3D.CameraAnimations.VerticalAni.schedule self.~._3D.CameraAnimations.playAnimation
```

**See also**

**\_3D.CameraAnimations.pause [SimTalk]**

- \_3D.CameraAnimations.resetAnimation [SimTalk]

- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.play [SimTalk]
- \_3D.CameraAnimations.getAnimation [SimTalk]
- \_3D.CameraAnimations.play [SimTalk]

#### \_3D.CameraAnimations.&lt;AnimationPathName&gt;.setTable [SimTalk]

Overwrites the saved animations of the designated Camera Animation data of the Frame designated by &lt;Path&gt; with the data of the passed table.

Remarks

The table has to be formatted correctly, otherwise 3D cancels your changes.

You can query the format of the table with the method \_3D.CameraAnimations.&lt;AnimationPathName&gt;.getTable .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.<AnimationPathName>.setTable(Source:table) < Path >._3D.CameraAnimations. getAnimation (<...>).setTable(Source:table)
```

**Parameter**

The parameter Source of data type table contains the new saved animation.

**Example**

```simtalk
var cama := _3D.CameraAnimations
var created : boolean := cama.createAnimationLine("Animation2")
if created // The animation line was created.
	var t: table // Copy the 'Default' line values to the table. cama.Default.getTable(t) cama.Animation2.setTable(t)
end
```

**See also**

Edit 3D Properties [dialog] > MU Animation [3D] _3D.CameraAnimations.<AnimationPathName>.getTable [SimTalk] _3D.CameraAnimations.getTable [SimTalk] _3D.CameraAnimations.getAnimation [SimTalk]

#### \_3D.CameraAnimations.AnimationTimeBlock [SimTalk]

Returns the time which the Camera Animation of the next block for the Frame designated by &lt;Path&gt; will most likely require. The time measurement relates to the simulation time.

Remarks

For Camera Animations a block generally only consists of a single animation, overlapping as with Self Animations is not possible. The time measurement relates to the simulation time.

Type

Read-only attribute

Syntax

< Path >._3D.CameraAnimations.AnimationTimeBlock -> time

Return Value

The return value has the data type time .

Example

```simtalk
var t : time := self.~._3D.CameraAnimations.AnimationTimeBlock
```

See also

**\_3D.CameraAnimations.AnimationTimeTotal [SimTalk]**

#### \_3D.CameraAnimations.AnimationTimeTotal [SimTalk]

Returns the time which the Camera Animation of all blocks for the Frame designated by &lt;Path&gt; will most likely require.

Remarks

The time measurement relates to the simulation time.

Type

Read-only attribute

Syntax

< Path >._3D.CameraAnimations.AnimationTimeTotal -> time

Return Value

The return value has the data type time .

Example

```simtalk
var t : time := self.~._3D.CameraAnimations.AnimationTimeTotal
```

See also

\_3D.CameraAnimations.AnimationTimeBlock [SimTalk]

#### \_3D.CameraAnimations.Count [SimTalk]

Returns the number of saved animation paths for the designated Camera Animation of the Frame designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.CameraAnimations.Count → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var cama := MyFrame._3D.CameraAnimations
```

#### \_3D.CameraAnimations.createAnimationCurve [SimTalk]

Creates a new saved animation path of type Polycurve for the Frame designated by &lt;Path&gt;.

Remarks

You can set the values of the animation path with the method \_3D.CameraAnimations.setTable .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.createAnimationCurve(Name:string) → boolean
```

Parameter

The parameter Name of data type string designates the name of the new animation path to be created.

Return Value

The return value has the data type boolean .

true if the animation path was created successfully, i.e., if the name has not been assigned yet.

Example

```simtalk
var a: boolean := self.~._3D.CameraAnimations.createAnimationCurve("curved movement")
if not a
	print "The animation curve could not be created."
end
```

See also

Edit 3D Properties [dialog] > Camera Animation [Frame] _3D.CameraAnimations.getTable [SimTalk] _3D.CameraAnimations.setTable [SimTalk] _3D.CameraAnimations.createAnimationLine [SimTalk] _3D.CameraAnimations.createAnimationSpline [SimTalk]

#### \_3D.CameraAnimations.createAnimationLine [SimTalk]

Creates a new saved animation path of type Lines for the Frame designated by &lt;Path&gt;.

Remarks

You can set the values of the animation path with the method \_3D.CameraAnimations.setTable .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.createAnimationLine(Name:string) → boolean
```

Parameter

The parameter Name of data type string designates the name of the new animation path to be created.

Return Value

The return value has the data type boolean .

true if the animation path was created successfully, i.e., if the name has not been assigned yet.

**Example**

```simtalk
var a: boolean := self.~._3D.CameraAnimations.createAnimationLine("straight
movement") if not a print "The animation line could not be created."
end
```

See also

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

_3D.CameraAnimations.getTable [SimTalk] _3D.CameraAnimations.setTable [SimTalk] _3D.CameraAnimations.createAnimationCurve [SimTalk] _3D.CameraAnimations.createAnimationSpline [SimTalk]

#### \_3D.CameraAnimations.createAnimationSpline [SimTalk]

Creates a new saved animation path of type Spline for the Frame designated by &lt;Path&gt;.

Remarks

You can set the values of the animation path with the method \_3D.CameraAnimations.setTable .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.createAnimationSpline(Name:string) → boolean
```

Parameter

The parameter Name of data type string designates the name of the new animation path to be created.

Return Value

The return value has the data type boolean .

true if the animation path was created successfully, i.e., if the name has not been assigned yet.

**Example**

```simtalk
var a: boolean := self.~._3D.CameraAnimations.createAnimationSpline("spline
movement") if not a print "The animation spline could not be created."
end
```

See also

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

_3D.CameraAnimations.getTable [SimTalk] _3D.CameraAnimations.setTable [SimTalk] _3D.CameraAnimations.createAnimationCurve [SimTalk] _3D.CameraAnimations.createAnimationLine [SimTalk]

#### \_3D.CameraAnimations.getAnimation [SimTalk]

Returns the specified Camera Animation of the Frame designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.getAnimation(AnimationPathName:string) < Path >._3D.CameraAnimations.getAnimation(Index:integer)
```

**Parameters**

The parameters designate a possibility each to query the designated animation.

- The parameter AnimationPathName of data type string designates a saved animation, whose name is an illegal SimTalk identifier, "#0#0" in the example below.
- The parameter Index of data type integer designates the n-th animation of the animations.

Return Value

If a string is passed and if the animation with the specified name or the specified index pair does not exist, the method returns void instead of opening the Debugger .

This does not apply to all other error cases, for example if you only specify a single integer value, the direct path extension, or specifying unsuited data types.

**Example**

```simtalk
var t: table self.~._3D.CameraAnimations.getAnimation("#0#0").getTable(t)
var t: table self.~._3D.CameraAnimations.getAnimation(7).getTable(t)
```

**See also**

\_3D.CameraAnimations.getTable [SimTalk]

- \_3D.CameraAnimations.setTable [SimTalk]

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

**Accessing an Animation via the Path Extension**

If a saved animation has a name that is a legal SimTalk identifier, you can access this animation via the path extension. This applies, for example, to the Path Name &gt; Default of the MU Animation . Here you could, for example, type in Assembly.\_3D.CameraAnimations.D . The path extension then suggests

<!-- image -->

#### \_3D.CameraAnimations.getTable [SimTalk]

Returns the animation data of all saved animations of the designated Camera Animation of the Frame designated by &lt;Path&gt; and writes it into the designated table.

Remarks

Plant Simulation automatically formats the passed table .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.getTable(Target:table)
```

**Parameter**

The parameter Target of data type table contains all available saved animations of the designated animation type.

Example

```simtalk
var t : table self.~._3D.CameraAnimations.getTable(t) debug self.~._3D.CameraAnimations.setTable(t)
```

**See also**

- \_3D.CameraAnimations.setTable [SimTalk]
- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.getTable [SimTalk]
- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.setTable [SimTalk]

#### \_3D.CameraAnimations.pause [SimTalk]

Pauses animations of the Frame designated by &lt;Path&gt; which are playing at the moment.

Type

Method

Syntax

< Path >._3D.CameraAnimations.pause

**Example**

```simtalk
self.~._3D.CameraAnimations.pause
```

**See also**

- \_3D.CameraAnimations.play [SimTalk]
- \_3D.CameraAnimations.resetAnimation [SimTalk]

#### \_3D.CameraAnimations.play [SimTalk]

Plays all scheduled animations of the Frame designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >._3D.CameraAnimations.play

**Examples**

```simtalk
var animations : any := self.~._3D.getObject("Arm").CameraAnimations
animations.reset
animations.rotateDown.schedule
animations.startNextAnimationBlock
animations.downFinished.schedule
animations.scheduleRotation(0, 360, 90)
@.austrittIn(animations.AnimationTimeTotal)
animations.play
self.~._3D.CameraAnimations.scheduleRotation(0, 90, 15)
self.~._3D.CameraAnimations.play
```

**See also**

- \_3D.CameraAnimations.pause [SimTalk]
- \_3D.CameraAnimations.resetAnimation [SimTalk]

#### \_3D.CameraAnimations.resetAnimation [SimTalk]

Resets all scheduled Camera Animations of the Frame designated by &lt;Path&gt;.

Remarks

This stops all playing animations and cancels all scheduled animations.

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.resetAnimation
```

**Example**

```simtalk
var animations : any := self.~.Models.MyFrame._3D.CameraAnimations
animations.resetAnimation
animations.Roundtrip.schedule
animations.play self.~._3D.CameraAnimations.resetAnimation
```

**See also**

- \_3D.CameraAnimations.play [SimTalk]
- \_3D.CameraAnimations.pause [SimTalk]

#### \_3D.CameraAnimations.setTable [SimTalk]

Overwrites the saved animations of the designated Camera Animation of the Frame designated by &lt;Path&gt; with the data of the passed table.

Remarks

The table has to be formatted correctly, otherwise 3D cancels your changes.

You can get the format of the table with the method \_3D.CameraAnimations.getTable .

Type

Method

Syntax

```simtalk
< Path >._3D.CameraAnimations.setTable(Source:table)
```

Parameter

The parameter Source of data type table contains the new animations.

Example

```simtalk
var t: table self.~._3D.CameraAnimations.getTable(t) debug self.~._3D.CameraAnimations.setTable(t)
```

See also

Edit 3D Properties [dialog] &gt; Camera Animation [Frame]

- \_3D.CameraAnimations.getTable [SimTalk]
- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.getTable [SimTalk]
- \_3D.CameraAnimations.&lt;AnimationPathName&gt;.setTable [SimTalk]

