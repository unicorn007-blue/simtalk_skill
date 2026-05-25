### Accessing Objects in 3D

#### \_\_Accessing Objects in 3D

SimTalk provides the attributes and methods listed in the table of contents to the left for accessing objects 3D .

You can view and access the attributes and methods for accessing objects in 3D by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

<!-- image -->

**See also**

**Auto Complete**

#### \_3D.addLengthOrientation [SimTalk]

Makes a length-oriented object out of the object designated by &lt;Path&gt;.

Remarks

This does not apply to existing length-oriented objects, moving objects ( MUs ), Connectors , and Interfaces .

Type

Method

Syntax

&lt; Path &gt;.\_3D.addLengthOrientation

Example

MyStation.\_3D.addLengthOrientation

See also

\_3D.removeLengthOrientation [SimTalk]

\_3D.InternalClassType [SimTalk]

TransferLengthToObject [SimTalk] in 2D

#### \_3D.addObject [SimTalk]

Creates an animatable object for the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.addObject(Name:string[, LengthOriented:boolean]) → any
```

**Parameters**

- The parameter Name of data type string designates the name of the animatable object.

Specify a name, which corresponds to the name of an animatable object in the origin of the object, in which the new animatable object is going to be created to create an object that inherits from the animatable object in the origin of the respective object. This way you can restore a deleted animatable object, which inherits from another object, in a way that it inherits again from the original object.

- The parameter LengthOriented of data type boolean sets if the animatable object is to be lengthoriented ( true ) or not ( false ).

If you specify this parameter and the object would be created with an origin, the newly created object will only have an origin if this origin is length-oriented as well if you set it to true .

This is not the case if you specify false .

Specify this parameter to make the new object length-oriented if it has an origin and if this origin is length-oriented as well.

**Return Value**

The return value has the data type any .

The return value is the newly created object.

**Examples**

```simtalk
// adds an animatable object to the Station
var MyAnimatableObject := Station._3D.addObject("MyAnimatableObject") // deletes the animatable object from the Station
```

**\_3D.addObject [SimTalk]**

```simtalk
MeinAnimierbaresObjekt.delete
Station._3D.getObject("MyAnimatableObject").delete
// adds an animatable object to the Conveyor // and makes it length-oriented
var MyAnimatableObject := Conveyor._3D.addObject("MyAnimatableObject", true)
```

**See also**

```simtalk
Make Animatable Object makeAnimatableObject [SimTalk] Add Animatable Object
_3D.getObject [SimTalk] delete [SimTalk] - animatable object
```

#### \_3D.Exists [SimTalk]

Checks if the object designated by &lt;Path&gt; exists in 3D (true) or not (false).

Remarks

If the object exists or not matters if the existence of a 3D object depends on its context. A Connector in 3D only exists if its predecessor as well as its successor exist in 3D.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.Exists → boolean
```

Return Value

The return value has the data type boolean .

**Example**

if obj._3D.Exists ... end

**See also**

\_3D.existsObject [SimTalk]

#### \_3D.existsObject [SimTalk]

Checks if the animatable object designated by &lt;Path&gt; exists in 3D (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >._3D.existsObject(Name:string) → boolean < Path >._3D.existsObject(Index:integer) → boolean
```

**Parameter**

The parameter Name of data type string designates the name of the object.

Or

The parameter Index of data type integer designates the n-th internal animatable object.

Return Value

The return value has the data type boolean .

Example

```simtalk
print basis._3D.existsObject("MyObject")
```

See also

\_3D.Exists [SimTalk]

existsObject [SimTalk]

#### \_3D.ExistsWithAnimation [SimTalk]

Returns if the object designated by &lt;Path&gt; exists in 3D or not and if the respective animation function is activated (true) or not (false).

Remarks

For MUs the animation function is the MU Animation , for all other objects it is the States Animation .

The attribute applies to all MUs and simulation objects. It does not apply to the folder , Connectors , and Interfaces .

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.ExistsWithAnimation → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyStation._3D.ExistsWithAnimation
```

See also

\_3D.Exists [SimTalk]

\_3D.existsObject [SimTalk]

MUs and States [Home ribbon]

#### \_3D.getAttribute [SimTalk]

Returns the value of the specified attribute of the object designated by &lt;Path&gt;.

Remarks

**Note**

\_3D.getAttribute also applies to animatable objects.

Type

Method

Syntax

```simtalk
< Path >._3D.getAttribute(AttributeName:string[, byRef Inherited:boolean, byRef CanInherit:boolean]) → any
```

**Parameters**

- The parameter AttributeName of data type string designates the value of the attribute.
- If a local variable of data type boolean is passed to the optional parameter Inherited , Plant Simulation assigns true to this variable if the attribute designated by string inherits its value, false if it does not inherit the value.

In case an attribute cannot be inherited, the optional parameter Inherited always returns false.

- If a local variable of data type boolean is passed to the optional parameter CanInherit , Plant Simulation assigns true to this variable if the value of the attribute designated by string can be inherited, false if it cannot be inherited.

Return Value

The return value has the data type any .

Examples

```simtalk
var inherited, canInherit : boolean
var pos := MyRobot._3D.getAttribute("Position", inherited, canInherit)
```

**\_3D.getAttribute [SimTalk]**

// inherited returns if the position can be inherited and canInherit if the attribute supports inheritance

```simtalk
var inherited : boolean
var pos := MyRobot._3D.getObject("Z").getAttribute("Position", inherited) // inherited returns if the position is inherited
var AttrName : string := "ShowContent"
var zi := MyFrame._3D.getAttribute(AttrName)
```

**See also**

**\_Methods of User-defined Attributes**

getAttribute [SimTalk] - object in 2D

#### \_3D.getMUAnimationPosition [SimTalk]

Returns the position on which a MU would be animated under certain marginal conditions.

Remarks

You can call \_3D.getMUAnimationPosition for length-oriented objects and for point-oriented objects .

getMUAnimationPosition for Length-oriented Objects

Returns the anticipated position of a MU on the length-oriented object designated by &lt;Path&gt;.

If you call the method for a simulation object , the method evaluates the attribute \_3D.AnimationObject and, if need be, returns a position on an animated object within the coordinate system of the simulation object.

If you call the method for the animatable object itself, the method only considers this object. Plant Simulation assumes that the animation will take place on this animatable object and returns the position within the coordinate system of the animatable object.

Type

Method

Syntax

```simtalk
< Path >._3D.getMUAnimationPosition(RelPos/AbsPos:real/length[, Lane/ Direction:integer:=1])
-> length[3]
```

**Parameters**

- The parameter RelPos/AbsPos is a value of data type real or length .

If the value has the data type real , it designates the relative position on the object. The relative position can be a value between 0 and 1. 0 designates the start of the animation and 1 the end of the animation, i.e., the value 100 %.

If the value has the data type length , it designates the absolute position on the object as the distance starting at the beginning of the object.

- The optional parameter Lane/Direction of data type integer designates the lane or the direction on the object respectively.

For a TwoLaneTrack the value 1 designates lane A and the value 2 designates lane B .

For a Converter the value 1 designates the default direction and the value 2 cross-wise conveying.

For all other objects 1 is the only valid value. If you do not specify the value, Plant Simulation automatically uses the value 1.

**Default Value of the Parameter**

The default value is 1.

Return Value

The return value is an array of data type length with three values.

Example

```simtalk
var p := Converter._3D.getMUAnimationPosition(0.5, 2)
var p := Conveyor._3D.getMUAnimationPosition(1m)
```

getMUAnimationPosition for Point-oriented Objects

Returns the anticipated position of a MU on the point-oriented object designated by &lt;Path&gt;.

If you call the method for a simulation object , the method evaluates the attribute \_3D.AnimationObject and, if need be, returns a position on an animated object within the coordinate system of the simulation object.

If you call the method for the animatable object itself, the method only considers this object. Plant Simulation assumes that the animation will take place on this animatable object and returns the position within the coordinate system of the animatable object.

Type

Method

Syntax

```simtalk
< Path >._3D.getMUAnimationPosition([X:integer:=1, Y:integer:=1])
-> length[3]
```

**Parameters**

- The optional parameter X of data type integer designates the processing place in the X-direction.

You have to enter the parameter for objects with a matrix loading space.

For other objects the parameter is optional. If you do not specify the value, Plant Simulation automatically uses the value 1.

For objects, which only have a single processing place, 1 is the only valid value.

**Default Value of the Parameter**

The default value is 1.

- The optional parameter Y of data type integer designates the processing place in the Y-direction.

You have to enter the parameter for objects with a matrix loading space.

For other objects the parameter is optional. If you do not specify the value, Plant Simulation automatically uses the value 1.

For objects, which only have a single processing place, 1 is the only valid value.

**Default Value of the Parameter**

The default value is 1.

**Return Value**

The return value is an array of data type length with three values.

**Examples**

```simtalk
var p := Station._3D.getMUAnimationPosition()
var p := PlaceBuffer._3D.getMUAnimationPosition(4)
var p := ParallelStation._3D.getMUAnimationPosition(3,4) // Let's assume we have a container on the object Station. // Then we can compute the position of the MU on place (1,1) // in the current frame as follows:
var container := Station.Cont
var animPos   := Station.Cont._3D.getMUAnimationPosition(1,1)
print current._3D.getPositionOfObject(container, animPos)
```

**See also**

```simtalk
_3D.MUAnimations.<AnimationPathName>.getMUAnimationPosition [SimTalk]
_3D.AnimationObject [SimTalk]
_3D.getPositionOfObject [SimTalk]
_3D.getMUAnimationRotation [SimTalk]
_3D.Poses.moveToMUAnimationPosition [SimTalk] Video on YouTube https://youtu.be/wfVN-mcWNsc?si=X80zVeMID2L2nf-m&t=902
```

**\_3D.getMUAnimationPosition [SimTalk]**

#### \_3D.getMUAnimationRotation [SimTalk]

Returns the rotation with which a MU would be animated under certain marginal conditions.

Remarks

You can call \_3D.getMUAnimationRotation for length-oriented objects and for point-oriented objects .

getMUAnimationRotation for Length-oriented Objects

Returns the anticipated rotation of a MU on the length-oriented object designated by &lt;Path&gt;.

If you call the method for a simulation object , the method evaluates the attribute \_3D.AnimationObject and, if need be, makes the rotation of the animated object part of the computation.

If you call the method for the animatable object itself, the method only considers this object. Plant Simulation assumes that the animation will take place on this animatable object and returns the rotation within the coordinate system of the animatable object.

Type

Method

Syntax

```simtalk
< Path >._3D.getMUAnimationRotation(RelPos/AbsPos:real/length[, Lane/ Direction:integer:=1])
-> real[4]
```

**Parameters**

- The parameter RelPos/AbsPos is a value of data type real or length .

If the value has the data type real , it designates the rotation at the relative position on the object. The relative position can be a value between 0 and 1. 0 designates the start of the animation and 1 the end of the animation, i.e., the value 100 %.

If the value has the data type length , it designates the rotation at the absolute position on the object.

- The optional parameter Lane/Direction of data type integer designates the lane or the direction on the object respectively.

For a TwoLaneTrack the value 1 designates lane A and the value 2 designates lane B .

For a Converter the value 1 designates the default direction and the value 2 cross-wise conveying.

For all other objects 1 is the only valid value. If you do not specify the value, Plant Simulation automatically uses the value 1.

Default Value of the Parameter

The default value is 1.

**Return Value**

The return value is an array of data type real with four values.

Example

```simtalk
var p := Converter._3D.getMUAnimationRotation(0.5, 2)
var p := Conveyor._3D.getMUAnimationRotation(1m)
```

getMUAnimationRotation for Point-oriented Objects

Returns the anticipated rotation of a MU on the point-oriented object designated by &lt;Path&gt;.

If you call the method for a simulation object , the method evaluates the attribute \_3D.AnimationObject and, if need be, makes the rotation of the animated object part of the computation.

If you call the method for the animatable object itself, the method only considers this object. Plant Simulation assumes that the animation will take place on this animatable object and returns the rotation within the coordinate system of the animatable object.

Type

Method

Syntax

```simtalk
< Path >._3D.getMUAnimationRotation([X:integer:=1, Y:integer:=1])
-> real[4]
```

**Parameters**

- The optional parameter X of data type integer designates the processing place in the X-direction.

You have to enter the parameter for objects with a matrix loading space.

For other objects the parameter is optional. If you do not specify the value, Plant Simulation automatically uses the value 1.

For objects, which only have a single processing place, 1 is the only valid value.

**Default Value of the Parameter**

The default value is 1.

- The optional parameter Y of data type integer designates the processing place in the Y-direction.

You have to enter the parameter for objects with a matrix loading space.

For other objects the parameter is optional. If you do not specify the value, Plant Simulation automatically uses the value 1.

For objects, which only have a single processing place, 1 is the only valid value.

**Default Value of the Parameter**

The default value is 1.

**Return Value**

The return value is an array of data type real with four values.

**Examples**

```simtalk
var p := Station._3D.getMUAnimationRotation()
var p := PlaceBuffer._3D.getMUAnimationRotation(4)
var p := ParallelStation._3D.getMUAnimationRotation(3,4)
// Let's assume we have a container on the object Station. // Then we can compute the rotation of the MU on place (1,1) // in the current frame as follows:
var container := Station.Cont
var animRot   := Station.Cont._3D.getMUAnimationRotation(1,1)
print current._3D.getrotationOfObject(container, animPos)
```

**See also**

```simtalk
_3D.MUAnimations.<AnimationPathName>.getMUAnimationPosition [SimTalk]
_3D.AnimationObject [SimTalk]
_3D.getPositionOfObject [SimTalk]
_3D.getMUAnimationPosition [SimTalk]
_3D.Poses.moveToMUAnimationPosition [SimTalk]
```

#### \_3D.getObject [SimTalk]

Returns the designated inner object of the object designated by &lt;Path&gt;.

Remarks

\_3D.getObject excludes objects with a counterpart in 2D, such as objects within a Frame or MUs on an object.

Type

Method

Syntax

```simtalk
< Path >._3D.getObject(ObjectName:string) < Path >._3D.getObject(ObjectIndex:integer)
```

**Parameter**

The parameter ObjectName of data type string designates the name of the object.

Or

The parameter ObjectIndex of data type integer designates the specified inner object.

Example

```simtalk
var o := Machine._3D.getObject("Arm") // if ObjectName is a valid identifier, you can also type: //
var
o := Machine._3D.Arm
```

Abbreviated Notation if ObjectName is a Valid Identifier

If the parameter ObjectName is a valid identifier, you can also type:

```simtalk
var o := Machine._3D.Arm
```

See also

delete [SimTalk] - animatable object

**\_3D.getObject [SimTalk]**

\_3D.addObject [SimTalk] \_3D.getGraphic [SimTalk] \_3D.getObject [SimTalk]

#### \_3D.getPositionOfObject [SimTalk]

Returns the position of the designated object in the coordinate system of the object designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >._3D.getPositionOfObject(Object:any[, Offset:length[3]]) → length[3]

**Parameters**

- The parameter Object of data type any designates the object whose position you would like to know.
- The optional parameter Offset is an array of data type length with three values. You can use it to convert the designated coordinate within the coordinate system of the passed object into the corresponding coordinate within the coordinate system of the calling object.

**Return Value**

The return value is an array of data type length with three values.

Designates the position of the object.

**Example**

```simtalk
// the part Part:1 is located on Transporter:2. The Transporter drives on .Models.Model.Track ... Track._3D.getPositionOfObject(.MUs.Part:1) // returns the position of the Part relative to the object position of the Track
_3D.getPositionOfObject(.MUs.Part:1)       // returns the position of the Part relative to the Frame, .MUs.Transporter:2._3D.getPositionOfObject(Station)    // returns the position  .Models.Model.Station relative to .Transporter // You can also specify simulation and 3D simulation objects and animatable objects. .MUs.Transporter:2._3D.getPositionOfObject(Station._3D) // same as above .MUs.Transporter:2._3D.getPositionOfObject(PickAndPlace._3D.getObject(1).get Object(1).getObject(1)) // returns the position of the ball joint of a four-axis robot relative to the Transporter
```

**\_3D.getPositionOfObject [SimTalk]**

See also \_3D.getRotationOfObject [SimTalk] \_3D.getWorldRotation [SimTalk] \_3D.getWorldCoordinate [SimTalk] \_3D.Position [SimTalk] \_3D.getMUAnimationPosition [SimTalk] Video on YouTube

[https://youtu.be/wfVN-mcWNsc?si=CuqfSgfwl7syzKQc&amp;t=565](https://youtu.be/wfVN-mcWNsc?si=CuqfSgfwl7syzKQc&t=565)

#### \_3D.getRotationOfObject [SimTalk]

Returns the rotation of the designated object in the coordinate system of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.getRotationOfObject(Object:any) → real[4]
```

Parameter

The parameter Object of data type any designates the object whose rotation you would like to know.

Return Value

The return value is an array of data type real with four values.

The first value designates the angle, the remaining three values designate the components of the rotation axis.

**Example**

```simtalk
print _3D.getRotationOfObject(Store)
```

See also

- \_3D.getPositionOfObject [SimTalk]
- \_3D.getWorldRotation [SimTalk] n
- \_3D.getWorldCoordinate [SimTalk]
- \_3D.Rotation [SimTalk]

Video on YouTube

[https://youtu.be/wfVN-mcWNsc?si=g56eH65auboJbJYV&amp;t=782](https://youtu.be/wfVN-mcWNsc?si=g56eH65auboJbJYV&t=782)

#### \_3D.hasAttribute [SimTalk]

Returns if the simulation object designated by &lt;Path&gt; has the attribute with the designated name (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >._3D.hasAttribute(AttributeName:string) → boolean
```

Parameter

The parameter AttributeName of data type string designates the name of the attribute of which you want to know if the object has it or not.

Return Value

The return value has the data type boolean .

true if the object has the attribute that can be read.

false for the parameter Imp , SetupImp , and FailImp if this attribute does not exist for the specified object.

**Examples**

```simtalk
print Store._3D.hasAttribute("StorageAreaMaterialShininess")
print Station._3D.getObject(1).hasAttribute("AnimationOffset")
print Conveyor._3D.hasAttribute("Imp")        -- returns false
print Conveyor._3D.hasAttribute("SetupImp")   -- returns false
print Conveyor._3D.hasAttribute("FailImp")    -- returns false
```

See also

hasAttribute [SimTalk] - 2D

#### \_3D.inheritAttribute [SimTalk]

Turns inheritance of the attribute designated by AttributeName of the object designated by &lt;Path&gt; on if it was turned off.

Remarks

If several attributes are inherited together, all attributes will be inherited, when you turn inheritance of a single attribute on.

Type

Method

Syntax

&lt; Path &gt;.\_3D.inheritAttribute(AttributeName:string)

Parameter

The parameter AttributeName of data type string designates the name of the attribute.

**Examples**

Conveyor.\_3D.inheritAttribute("VisibleGraphicGroups")

Frame._3D.inheritAttribute("PlanningView") // You can call the method for any of the view options. // This turns inheritance of all view options on or off.

**See also**

View tab &gt; Use Planning View , Inherit View Options [3D only]

inheritAttribute [SimTalk] - object in 2D

#### \_3D.InternalClassType [SimTalk]

Returns the built-in English name of the length-oriented object designated by &lt;Path&gt;.

Remarks

The internal class name is not the localized object name that some of the localized versions of Plant Simulation show, but the English object name that the Class Library shows.

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.InternalClassType
-> string
```

Return Value

The return value has the data type string .

- The return values AnimatableExtrusionObject and SimulationExtrusionObject designate a lengthoriented object in 3D.
- The return values AnimatableObject and SimulationObject designate a point-oriented object in 3D.

Exceptions are the following objects with the internal class types Button , Chart , Checkbox , Comment , Connector , Container , Display , DropDownList , Folder , Frame , Interface , Mixer , Part , PickAndPlace , Store , Tank , Toolbar , Transporter , Variable , and Worker .

**Example**

```simtalk
var animObject : any := obj._3D.getObject(1)
if animObject.InternalClassType = "AnimatableExtrusionObject" then
	animObject.BaseHeight := 2
end
```

See also

InternalClassType [SimTalk]

typeOf [SimTalk]

- \_3D.addLengthOrientation [SimTalk]
- \_3D.removeLengthOrientation [SimTalk]

**\_3D.InternalClassType [SimTalk]**

#### \_3D.memUsage [SimTalk]

Computes how much memory the 3D part of object designated by &lt;Path&gt; uses.

Type

Method

Syntax

```simtalk
< Path >._3D.memUsage → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
print MyStation._3D.memUsage -- might
return 2665, i.e.
2.6 KB
print MyStation.memUsage -- might
return 4975, i.e.
4.9 KB
```

See also

Show Structure [class library]

memUsage [SimTalk]

#### \_3D.NumObjects [SimTalk]

Returns the number of animatable objects that are part of the object designated by &lt;Path&gt;.

Remarks

You can then access these objects with the function \_3D.getObject .

Type

Read-only attribute

Syntax

```simtalk
< Path >._3D.NumObjects → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var obj := .Models.Model.MyStation._3D
for var i := 1 to obj.NumObjects
	print obj.getObject(i).Name
next
```

See also

\_3D.getObject [SimTalk]

#### \_3D.openDialog [SimTalk]

Opens the dialog Edit 3D Properties of the object designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >._3D.openDialog

Example

Buffer._3D.openDialog

See also

openDialog [SimTalk] - all objects in 2D

Edit 3D Properties [dialog]

#### \_3D.openWindow [SimTalk]

Opens the object designated by &lt;Path&gt; in a new window in 3D .

Type

Method

Syntax

< Path >._3D.openWindow

Example

MyFrame._3D.openWindow

See also

Open [object class]

Open in New 3D Window [simulation object]

closeAllWindows [SimTalk]

#### \_3D.removeLengthOrientation [SimTalk]

Makes an object out of the length-oriented object designated by &lt;Path&gt; which will not be length-oriented in 3D.

Remarks

\_3D.removeLengthOrientation only applies to classes which do not inherit settings from another class.

Type

Method

Syntax

&lt; Path &gt;.\_3D.removeLengthOrientation

**Example**

MyStationLengthOriented.\_3D.removeLengthOrientation

See also

\_3D.addLengthOrientation [SimTalk]

\_3D.InternalClassType [SimTalk]

TransferLengthToObject [SimTalk] in 2D

#### \_3D.Selected [SimTalk]

Selects the object designated by &lt;Path&gt; in 3D ( true ) or deselects it ( false ).

Remarks

\_3D.Selected selects all simulation and animatable objects in all 3D windows. The global selection remains active until you close the model or select something else, even if no window is still open.

\_3D.Selected selects graphics and tools, such as animation path nodes and manipulators, in a single 3D window only, not globally in all 3D windows.

**Note**

The Select Control of the material flow objects does not react when you select an object in 3D.

Type

Attribute

Syntax

```simtalk
< Path >._3D.Selected:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyStation._3D.Selected := true
MyPickAndPlace._3D.getObject(1).Selected := true
```

See also

Selected [SimTalk] - 2D

Select Control

#### delete [SimTalk] - animatable object

Deletes the animatable object designated by &lt;PathToObjectToBeDeleted&gt;.

Remarks

Deleting an animatable object can make variables invalid which reference neighboring animatable objects!

It always makes those variables invalid which reference objects which are located within the deleted object.

Type

Method

Syntax

&lt; Path &gt;ToObjectToBeDeleted&gt;.delete

**Example**

```simtalk
// adds an animatable object to the Station
var MyAnimatableObject := Station._3D.addObject("MyAnimatableObject") // deletes the animatable object from the Station MyAnimatableObject.delete Station._3D.getObject("MyAnimatableObject").delete
```

See also

\_3D.addObject [SimTalk]

_3D.getObject [SimTalk]

#### Length [SimTalk] - animatable object

Sets the length of the animatable object designated by &lt;Path&gt;.

Remarks

You can set and get this value if the object has a single straight-lined segment.

Otherwise, you can only get this value.

Type

Attribute

Syntax

< Path >.Length:length

**Assignment Value**

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyStation._3D.getObject(1).Length := 2m
```

**See also**

\_3D.getExtSegments [SimTalk]

_3D.setExtSegments [SimTalk]

#### Name [SimTalk] - animatable object

Sets the name of the animatable object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Name:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
PickAndPlace._3D.getObject(1).Name := "MyObject"
var n:string := PickAndPlace._3D.getObject(1).Name
```

See also

\_3D.getObject [SimTalk]

Name [text box] - 3D

