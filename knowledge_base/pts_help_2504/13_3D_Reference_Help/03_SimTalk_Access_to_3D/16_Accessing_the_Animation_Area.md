### Accessing the Animation Area

#### \_\_Accessing the Animation Area

SimTalk provides the attributes and methods listed in the table of contents to the left for accessing the Animation Area of objects with matrix loading space in 3D .

You can view and access the attributes and methods for setting the animation area by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

**Note**

The settings for the animation area only apply to objects with matrix loading space ( ParallelStation , Store , Transporter , and Container ), for the PlaceBuffer , and for the Worker . As a rule, you can use the pre-defined settings, unless they do not meet your requirements.

See also

Edit 3D Properties [dialog] &gt; MU Animation [3D] &gt; Animation Area [described]

Animation Area [described]

Auto Complete

#### \_3D.convertMUAnimationAreaToPaths [SimTalk]

Converts the animation area of the object designated by &lt;Path&gt; to an animation path with storage places.

Type

Method

Syntax

&lt; Path &gt;.\_3D.convertMUAnimationAreaToPaths

**Example**

Store.\_3D.convertMUAnimationAreaToPaths

#### \_3D.createMUAnimationAreaFromPaths [SimTalk]

Creates an animation area for MUs from animation paths in the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.\_3D.createMUAnimationAreaFromPaths → boolean

Return Value

The return value has the data type boolean .

true if enough data was available for the conversion.

Example

Store.\_3D.createMUAnimationAreaFromPaths

#### \_3D.MUAnimationAreaAbsoluteCenter [SimTalk]

Sets the center of the animation area of the object designated by &lt;Path&gt; in absolute values.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaAbsoluteCenter:real[3]

Assignment Value

You can assign a value of data type array containing three values of data type real .

They set the X position, the Y position, and the Z position of the Center point of the animation area.

You can specify any negative or positive value.

Example

MyParallelstation.\_3D.MUAnimationAreaAbsoluteCenter := [0.1, 0.1, 0.5]

See also

Center [animation area]

\_3D.MUAnimationAreaRelativeCenter [SimTalk]

#### \_3D.MUAnimationAreaAbsoluteSize [SimTalk]

Sets the size, i.e., the Absolute Length and the Absolute Width of the animation area of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.MUAnimationAreaAbsoluteSize:real[2]
```

Assignment Value

You can assign an array with two values of data type real . You can specify a value between 0 and any size.

They set the Absolute Length and the Absolute Width of the animation area.

Example

```simtalk
MyParallelstation._3D.MUAnimationAreaAbsoluteSize := [2m,2m]
```

See also

Length [text box] - animation area

Width [text box] - animation area

\_3D.MUAnimationAreaRelativeSize [SimTalk]

#### \_3D.MUAnimationAreaEnabled [SimTalk]

Activates ( true ) or deactivates ( false ) the animation area of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaEnabled:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyParallelstation._3D.MUAnimationAreaEnabled := true
```

See also

Animation Area [check box]

Animation Area [described]

\_3D.MUAnimationAreaShowMUsAsCuboids [SimTalk]

#### \_3D.MUAnimationAreaMURotation [SimTalk]

Sets the rotation of the MUs on the animation area of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaMURotation:real/real[3]

Assignment Value

You can assign a value of data type any .

- You can specify a real number which defines the rotation around the negative z-axis at the position at which you inserted the object. This is the axis that causes a rotation that matches the rotation in 2D.
- You can specify an array of data type real with three values. They define the components of the rotation axis around which the parts will be rotatedat the position at which you inserted the object.

**Examples**

MyParallelstation.\_3D.MUAnimationAreaMURotation := 45 // degrees

MyParallelstation.\_3D.MUAnimationAreaMURotation := [15, 1, 1, -1]

See also

MU Rotation

#### \_3D.MUAnimationAreaOrientation [SimTalk]

Sets the orientation of the animation area of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaOrientation:string

Assignment Value

You can assign a value of data type string .

You can specify "XY-plane" , "XZ-plane" , or "YZ-plane" .

Example

MyParallelstation.\_3D.MUAnimationAreaOrientation := "XY-plane"

See also

Orientation [animation area]

#### \_3D.MUAnimationAreaRelativeCenter [SimTalk]

Sets the center of the animation area of the object designated by &lt;Path&gt; in relative values.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaRelativeCenter:real[3]

Assignment Value

You can assign a value of data type array containing three values of data type real .

They set the X position, the Y position, and the Z position of the Center point of the animation area.

You can specify any negative or positive value.

Example

MyParallelstation.\_3D.MUAnimationAreaRelativeCenter := [0.1, 0.1, 0.5]

See also

Center [animation area]

\_3D.MUAnimationAreaAbsoluteCenter [SimTalk]

#### \_3D.MUAnimationAreaRelativeSize [SimTalk]

Sets the size, i.e., the Relative Length and the Relative Width of the animation area of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.MUAnimationAreaRelativeSize:real[2]
```

Assignment Value

You can assign an array with two values of data type real . You can specify a value between 0 and any size.

They set the Relative Length and the Relative Width of the animation area.

Example

```simtalk
MyParallelstation._3D.MUAnimationAreaRelativeSize := [1,1]
```

See also

Length [text box] - animation area

Width [text box] - animation area

\_3D.MUAnimationAreaAbsoluteSize [SimTalk]

#### \_3D.MUAnimationAreaShowMUsAsCuboids [SimTalk]

Sets if the MUs will be animated on the animation area of the object designated by &lt;Path&gt; with cuboids ( true ) or with the graphic of the MU as such ( false ).

Remarks

Animating the cuboids is considerably faster than animating the graphics of the MUs .

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.MUAnimationAreaShowMUsAsCuboids:boolean

**Assignment Value**

You can assign a value of data type boolean .

Example

```simtalk
MyStore._3D.MUAnimationAreaShowMUsAsCuboids := true
```

See also

Show MUs as Cuboids [check box]

\_3D.MUAnimationAreaEnabled [SimTalk]

