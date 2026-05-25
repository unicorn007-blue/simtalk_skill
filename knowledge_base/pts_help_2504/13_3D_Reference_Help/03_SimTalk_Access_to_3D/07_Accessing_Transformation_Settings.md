### Accessing Transformation Settings

#### \_\_Accessing Transformation Settings

SimTalk provides the attributes and methods listed in the table of contents to the left for accessing the transformation of objects in 3D .

To access the attributes in 3D you can type in:

&lt; Path &gt;.\_3D.NameOfTheAttribute designates the path to the attribute of the 3D object.

To set an attribute, you will type &lt; Path &gt;.\_3D.NameOfTheAttribute := "MyString"

You can view and access the attributes and methods for setting the transformation by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

**See also**

**Auto Complete**

#### \_3D.CornerPoints [SimTalk]

Sets the intermediate anchor points of the Connector designated by &lt;Path&gt; in the 3D window .

Type

Attribute

Syntax

< Path >._3D.CornerPoints:length[3,*]

Assignment Value

You can assign a two-dimensional array of data type length with sequences of three values.

Examples

```simtalk
var cornerPoints := .Models.Model.Connector1._3D.CornerPoints
cornerPoints[3,1] := 4 .Models.Model.Connector1._3D.CornerPoints := cornerPoints
.Models.Model.Connector1._3D.CornerPoints[3,1] := 4
```

See also

CornerPointsArray [SimTalk]

make2DimArray [SimTalk]

#### \_3D.Dimensions [SimTalk] - simulation object

Sets the dimensions of the scaled graphic of the simulation object and the non-length-oriented animatable object designated by &lt;Path&gt;.

Remarks

You cannot set any dimensions for an object without graphics.

**Note**

The following objects do not provide the attribute \_3D.Dimensions :

- Part , Container , Transporter , and Worker
- Connector , Interface , and Marker
- Length-oriented objects
- Store
- Variable , Comment , Button , DropDownList , Checkbox , and Display

Type

Attribute

Syntax

< Path >._3D.Dimensions:length[3]

Assignment Value

You can assign an array of data type length with three positive values.

Example

```simtalk
MyStation._3D.Dimensions := [3m, 2m, 2m]
```

See also

Edit 3D Properties [dialog] &gt; Transformation [3D object] &gt; Settings for the Scale [transformation] &gt; Set Dimensions

\_3D.Dimensions [SimTalk] - Store X [SimTalk] - array Y [SimTalk] - array Z [SimTalk] - array

#### \_3D.getWorldCoordinate [SimTalk]

Returns the position of the object designated by &lt;Path&gt; in the topmost Frame .

Type

Method

Syntax

< Path >._3D.getWorldCoordinate([Offset:length[3]]) → length[3]

**Parameter**

The optional parameter Offset is an array of data type length with three values. You can use it to query the world coordinate of the designated coordinate within the object coordinate system.

Return Value

The return value is an array of data type length with three values.

**Example**

```simtalk
print Store._3D.getWorldCoordinate(Store.getAnimationPoint(1, 1))
```

**See also**

- \_3D.getWorldRotation [SimTalk]
- \_3D.getPositionOfObject [SimTalk]
- \_3D.getRotationOfObject [SimTalk]
- \_3D.Position [SimTalk]

#### \_3D.getWorldRotation [SimTalk]

Returns the rotation of the object designated by &lt;Path&gt; in the topmost Frame .

Type

Method

Syntax

```simtalk
< Path >._3D.getWorldRotation → real[4]
```

**Return Value**

The return value is an array of data type real with four values.

The first value designates the angle, the remaining three values designate the components of the rotation axis.

**Example**

```simtalk
print Store._3D.getWorldRotation // might
return [0, 0, 0, -1]
```

**See also**

- \_3D.getPositionOfObject [SimTalk]
- \_3D.getWorldRotation [SimTalk]
- \_3D.getWorldCoordinate [SimTalk]
- \_3D.Rotation [SimTalk]

#### \_3D.Mirror [SimTalk]

Sets mirroring of the object designated by &lt;Path&gt; on one or three planes.

Remarks

This does not apply to existing length-oriented objects , moving objects ( MUs ), and to Connectors .

Type

Attribute

Syntax

```simtalk
< Path >._3D.Mirror:boolean/boolean[3]
```

**Assignment Value**

- You can assign a single value of data type boolean to only mirror the object on the YZ-Plane .
- You can assign a value of data type array containing three values of data type boolean to set mirroring around the designated planes. The values of data type boolean designate the YZ-Plane , the XZ-Plane , and the XY-Plane in this order.

**Examples**

```simtalk
MyFrame._3D.Mirror := true
MyFrame._3D.Mirror := [true,false,true]
```

See also

**Settings for Mirroring**

#### \_3D.Position [SimTalk]

Sets the current position of the object designated by &lt;Path&gt;.

Remarks

This does not apply to MU instances and to Connector instances .

\_3D.Position shows the current position.

For MU instances this position is computed by the animation.

Type

Attribute

Syntax

< Path >._3D.Position:length[3]

**Assignment Value**

You can assign an array with three values of data type length .

**Example**

```simtalk
MyFrame._3D.Position := [5,3,0]
```

See also

###### Settings for the Position [transformation]

\_3D.getGraphic [SimTalk] . Position [SimTalk] - graphic

X [SimTalk] - array

Y [SimTalk] - array

Z [SimTalk] - array

\_3D.getWorldCoordinate [SimTalk]

#### \_3D.PositionsConnected [SimTalk]

Matches the position of the object designated by &lt;Path&gt; in the 2D part of the simulation model with the position of the respective object in the 3D part of the model ( true ) or not ( false ).

**Remarks**

\_3D.PositionsConnected also applies to the anchor points of length-oriented objects .

Type

Attribute

Syntax

```simtalk
< Path >._3D.PositionsConnected:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Examples**

```simtalk
MyConveyor._3D.PositionsConnected := true
```

MyStation.\_3D.PositionsConnected := false

**See also**

\_3D.RotationsConnected [SimTalk]

Connect 2D and 3D Positions

#### \_3D.Rotation [SimTalk]

Sets the current rotation of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.Rotation:real/real[4]
```

Assignment Value

You can specify:

- A number which defines the rotation around the negative z-axis at the position at which you inserted the object. This is the axis that causes a rotation that matches the rotation in 2D.
- An array of data type real with four items, which defines the rotation around the specified axis (values 2 to 4) at the position at which you inserted the object.

If you get the attribute, 3D returns an array with four items.

Examples

```simtalk
var a : any := MyStation._3D.Rotation // returns an array of 4 values
MyStation._3D.Rotation := 30 // rotates the object by 30 degrees
MyStation._3D.Rotation := [45, 0, 1, 0] // rotates the object by 45 degrees around the Y axis
```

See also

Settings for the Rotation [transformation]

\_3D.getGraphic [SimTalk] . Rotation [SimTalk] - graphic

F3DconcatenateRotations [SimTalk]

ObjectAngle [SimTalk] - object icons in 2D

**ObjectMirrored [SimTalk] - object icons in 2D**

#### \_3D.RotationsConnected [SimTalk]

Matches the rotation of the object designated by &lt;Path&gt; in the 2D part of the simulation model with the rotation of the respective object in the 3D part of the model ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.RotationsConnected:boolean
```

Assignment Value

You can assign a value of data type boolean .

**Examples**

```simtalk
MyConveyor._3D.RotationsConnected := false
MyStation._3D.RotationsConnected := true
```

See also

**\_3D.RotationsConnected [SimTalk]**

Connect 2D and 3D Positions

#### \_3D.Scale [SimTalk]

Sets the current scale of the object designated by &lt;Path&gt;.

Remarks

This does not apply to Connectors .

Type

Attribute

Syntax

```simtalk
< Path >._3D.Scale:real/real[3]
```

**Assignment Value**

- You can assign a value of data type real to achieve uniform scaling.
- You can assign an array with three values of data type real to use different scaling factors for the three axes.

**Examples**

```simtalk
MyStation._3D.Scale := 1           // uniform scaling
MyStation._3D.Scale := [1, 4, 9]   // different scaling factors for the xaxis, y-axis and z-axis
```

**See also**

Settings for the Scale [transformation] Scale [SimTalk] - graphic X [SimTalk] - array Y [SimTalk] - array Z [SimTalk] - array

#### \_3D.ScaleAutomatically [SimTalk]

Automatically scales the graphics of the MU designated by &lt;MU-Path&gt; ( true ) or not ( false ).

Remarks

3D then adjusts the size and positioning of the graphic of the MU to the measurements and the booking point of the MU in 2D.

Type

Attribute

Syntax

```simtalk
<MUPath >._3D.ScaleAutomatically:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

Example

```simtalk
.MUs.Part:1._3D.ScaleAutomatically := true
```

See also

Scale Automatically

\_3D.exchangeGraphic [SimTalk]

#### \_3D.TransformationMatrix [SimTalk]

Sets the entire transformation of the object designated by &lt;Path&gt;.

Remarks

- \_3D.TransformationMaxtrix can either designate a one-dimensional array of data type real with 16 values or a two-dimensional array of data type real with four times four values.
- \_3D.TransformationMaxtrix is available for all fully transformable objects ( stations , Frames , lengthoriented objects , Interfaces , and for the classes of the Connector , the MUs , and the Worker ).

Note

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.TransformationMatrix → array

Return Value

The return value is always an array with four times four values.

See also

Transformation [3D object]

addGraphicTransformation [SimTalk]

#### F3DconcatenateRotations [SimTalk]

Concatenates two rotations into one and returns the computed value.

Type

Method

Syntax

```simtalk
F3DconcatenateRotations(Rotation1:real[4], Rotation2:real[4]) → real[4]
```

**Parameters**

- The parameter Rotation1 is an array of data type real with four values, which sets the first rotation of the graphic. The elements of the array denote the rotation angle, and the x-component, the y-component, and the z-component of the rotation axis.
- The parameter Rotation2 is an array of data type real with four values, which sets the second rotation of the graphic. The elements of the array denote the rotation angle, and the x-component, the y-component, and the z-component of the rotation axis.

**Return Value**

The return value is an array with four values of data type real .

Corresponds to the sequence of the input rotations which are executed one after the other in the sequence in which they were passed to the method.

**Examples**

```simtalk
Station._3D.Rotation := F3DconcatenateRotations(Station._3D.Rotation, [45, 0, 1, 0])
Station._3D.Rotation := F3DconcatenateRotations([90, 0, 1, 0], [45, 0, 1, 0])
```

**See also**

\_3D.Rotation [SimTalk]

Rotation [SimTalk] - graphic

\_3D.NameLabelRotation [SimTalk]

