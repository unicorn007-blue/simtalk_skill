### \_Detailed Access To Graphics

SimTalk provides the attributes and methods listed in the table of contents to the left for accessing the object graphics in 3D .

#### addGraphicTransformation [SimTalk]

Adds an additional transformation to an existing transformation of the designated graphic of the object designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Let's suppose that a graphic is translated by the coordinates (3, 0, 0) from its origin and its basic orientation, and rotated by 30° around its y-axis.

Applying the method addGraphicTransformation to this graphic with a translation of (2, 0, 0) and a uniform scaling factor of 2 results in a graphic translation which first translates it by the coordinates (3, 0, 0), then rotates it by 30° around the y-axis, then translates it by (2, 0, 0), and finally scales the resulting translation by a factor of 2 in all directions. Note the sequence is important. It is, for example, not possible to combine the translations into one.

Type

Method

Syntax

&lt; Path &gt;.addGraphicTransformation(Position:length[3], RotationAngle:real, RotationAxis:real[3], Scale:real/real[3])

**Parameters**

- The parameter Position is an array of data type length with three values. They designate the position of the graphic.
- The parameter RotationAngle of data type real sets its rotation angle.
- The parameter RotationAxis is an array of data type real with three values. They designate the rotation axis of the graphic.
- The parameter Scale sets the scale of the graphic.

You can either specify a single parameter of data type real , which sets a uniform scaling.

Or you can specify an array of data type real with three values. They designate the scaling factors along the X-axis, the Y-axis, and the Z-axis.

**Examples**

MyStation.getGraphic("default", [1,4]).addGraphicTransformation([3,2,1], 30, [0,0,-1], 2)

MyStation.getGraphic("deco", [1,4]).addGraphicTransformation([3,2,1], 30, [0,0,-1], 2)

**See also**

##### Transformation [3D object]

\_3D.getGraphic [SimTalk]

#### deleteGraphic [SimTalk]

Deletes the specified graphic of the object designated by &lt;Path&gt;.

Remarks

Note

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

&lt; Path &gt;.deleteGraphic

Example

MyStation.\_3D.getGraphic("default", [2,2]).deleteGraphic

See also

\_3D.InheritGraphics [SimTalk]

**graphic [SimTalk]**

#### graphic [SimTalk]

Returns the designated inner graphic or graphic group of graphic or graphic group designated by &lt;Path&gt;.

Remarks

The method graphic is available for composite graphics, compare InternalGraphicType &gt; Composite Graphics .

Type

Method

Syntax

```simtalk
< Path >.graphic(Name:string) < Path >.graphic(Index:string)
```

**Parameter**

The parameter Name of data type string designates the name of the inner graphic.

Or

The parameter Index of data type integer designates the n-th inner graphic.

**Example**

```simtalk
var outerGraphic := machine._3D.getGraphic("default", [1]) // returns the first graphic in the graphic group named 'default'
var innerGraphic := outerGraphic.Graphic(2) // returns the second graphic in the first graphic in the graphic group named 'default'
innerGraphic.Position := [1,2,3]
```

**See also**

InternalGraphicType [SimTalk] _3D.getGraphic [SimTalk] _Detailed Access To Graphics

#### groupGraphics [SimTalk]

Transforms the designated graphics in the graphic designated by &lt;Path&gt; into a group.

Remarks

**Note**

groupGraphics is available for composite graphics, compare InternalGraphicType &gt; Composite Graphics .

You can specify the graphics to be grouped either by their numeric indexes or by their names.

Assigning the method deactivates graphic inheritance.

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

< Path >.groupGraphics(Children:any[]) → any

Parameters

The parameter Children is an array of data type any . It sets the numeric indexes or the names of the graphics which are to be added to the grouped graphic.

Return Value

The return value has the data type any .

It designates the created graphic, compare the method \_3D.getGraphic .

**Examples**

MyFrame._3D.getGraphic("default", [1,2]).groupGraphics([2,3]) // groups the graphics at the indexes [1,2,2] and [1,2,3] MyFrame._3D.getGraphic("deco").groupGraphics(["Plate","Tool"]) // groups the graphics named "Plate" and "Tool"

See also InternalGraphicType [SimTalk] Group Graphics ungroupGraphic [SimTalk] \_3D.InheritGraphics [SimTalk] \_3D.getGraphic [SimTalk]

#### Index [SimTalk] - graphic in 3D

Returns the numeric index of the specified graphic of the object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Index → integer
```

Return Value

The return value has the data type integer .

Examples

```simtalk
var index : integer := MyStation._3D.getGraphic("default", ["Wheels"].Index // the Variable contains the numeric index of the graphic
var index : integer := Graphicgroup.Graphic("Wheels").Index // the Variable contains the numeric index of the graphic
var Graphicgroup := MyStation._3D.getGraphic("default")
```

See also

Name [SimTalk] - graphic

#### InternalGraphicType [SimTalk]

Returns the type of the graphic or graphic group designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.InternalGraphicType → string

Return Value

The return value has the data type string .

Plant Simulation returns one of the following types:

**Composite graphics**

- FactoryWalls are Factory Walls . After optimizing a parent graphic this graphic might possibly not be recognized as factory walls but as a Shape or a GroupNode.
- Fence is a Fence . After optimizing a parent graphic this graphic might possibly not be recognized as a fence but as a GroupNode.
- GraphicGroup is a graphic group. This is the case for all graphics whose access arose with an empty array in the second parameter of \_3D.getGraphic or if you only specified a single parameter.
- GroupNode is a normal group node that is formed by groupGraphics for example.
- Instance is a special group node which can only contain a single child graphic.
- Rack is a Rack . After optimizing a parent graphic this graphic might possibly not be recognized as a rack but as a Shape or a GroupNode.
- Stairs is a Staircase . After optimizing a parent graphic this graphic might possibly not be recognized as a set of stairs but as a Shape or a GroupNode.
- Switch is a special group node that always shows one if its children only.

**Simple graphics**

- BarredArea is a Barred Area . After optimizing a parent graphic this graphic might possibly not be recognized as a barred area but as a Shape.
- Box is a Box . After optimizing a parent graphic this graphic might possibly not be recognized as a box but as a Shape.

- Dimensionings are Measurements within your model. After optimizing a parent graphic this graphic might possibly not be recognized as dimensionings but as a Shape.
- Shape is a graphic that is not subdivided any more, which contains its graphics data itself, as opposed to GroupNode.

**Example**

```simtalk
var graphic := MyStation._3D.getGraphic("default", [1])
if graphic.InternalGraphicType = "Fence"
	graphic.restoreCutouts
end
```

**See also**

\_3D.getGraphic [SimTalk]

#### makeAnimatableObject [SimTalk]

Creates an animatable object for the object designated by &lt;Path&gt;.

Remarks

makeAnimatableObject takes the designated graphic, extracts it from the original object, and uses this graphic for the animatable object to be created.

If the graphic, from which the animatable object is created, is not part of the default graphics group, the method creates a graphics group with the name of the graphics group where the graphic to be extracted is located. In previous versions Plant Simulation created the graphics group within the default graphics group.

**Note**

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

```simtalk
< Path >.makeAnimatableObject(ObjectName:string, ExtractAtBoundingBoxBase:boolean[, ExtractionOffset:length[3], SwapXAndZAxis:boolean]) → any
```

**Parameters**

- The parameter ObjectName of data type string sets the name of the animatable object.
- The parameter ExtractAtBoundingBoxBase of data type real sets if the insertion position of the new object is determined based on the bounding box of the graphic ( true ) or not ( false ).
- The optional parameter ExtractionOffset is an array of data type length with three values which sets the offset of the insertion position. If you do not specify the value, the method uses the values [0,0,0].
- The optional parameter SwapXAndZAxis of data type boolean sets if the graphics of the animatable object will be rotated by 90° around the y-axis, thus swapping the x-axis and the z-axis, while looking the same from the outside ( true ). If you do not specify the value, the method uses the value false.

**Return Value**

The return value of data type any designates the newly created animatable object.

**Examples**

```simtalk
var tool := MyStation._3D.getGraphic("default", ["tool"]).makeAnimatableObject("toolHead",true, [0,0,0])
tool.JointType := "Revolute Joint"
MyStation._3D.getGraphic("default", ["tool"]).makeAnimatableObject("toolHead",true, [0,0,0])
MyStation._3D.getObject("toolHead").JointType := "Revolute Joint" // This line of code accomplishes the same as the second line of code in the first example.
```

**See also**

**Make Animatable Object**

delete [SimTalk] - animatable object

\_3D.getObject [SimTalk]

\_3D.addObject [SimTalk]

#### MaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the graphic designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialActive := true
```

See also

Set the Material of a Graphic

MaterialAmbientColor [SimTalk]

MaterialDiffuseColor [SimTalk]

MaterialEmissiveColor [SimTalk]

MaterialShininess [SimTalk]

MaterialSpecularColor [SimTalk]

**MaterialTransparency [SimTalk]**

#### MaterialAmbientColor [SimTalk]

Sets the ambient color of the material of the specified graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialAmbientColor := makeRGBValue(0,0,255)
```

See also

Edit 3D Properties [dialog] &gt; Material [tab] &gt; Ambient Color [material]

MaterialActive [SimTalk]

MaterialDiffuseColor [SimTalk]

MaterialEmissiveColor [SimTalk] MaterialShininess [SimTalk] MaterialSpecularColor [SimTalk] MaterialTransparency [SimTalk]

#### MaterialDiffuseColor [SimTalk]

Sets the diffuse color of the graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog] &gt; Material [tab] &gt; Diffuse Color [material]

MaterialActive [SimTalk]

MaterialAmbientColor [SimTalk]

MaterialEmissiveColor [SimTalk] MaterialShininess [SimTalk] MaterialSpecularColor [SimTalk] MaterialTransparency [SimTalk]

#### MaterialEmissiveColor [SimTalk]

Sets the emissive color of the graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialEmissiveColor := makeRGBValue(0,255,0)
```

See also

Edit 3D Properties [dialog] &gt; Material [tab] &gt; Emissive Color [material]

MaterialActive [SimTalk]

MaterialAmbientColor [SimTalk]

MaterialDiffuseColor [SimTalk] MaterialShininess [SimTalk] MaterialSpecularColor [SimTalk] MaterialTransparency [SimTalk]

#### MaterialShininess [SimTalk]

Sets the material shininess of the graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialShininess := 0.9
```

See also

Edit 3D Properties [dialog] &gt; Material [tab] &gt; Shininess [material]

MaterialActive [SimTalk]

MaterialAmbientColor [SimTalk]

MaterialDiffuseColor [SimTalk]

**MaterialSpecularColor [SimTalk] MaterialTransparency [SimTalk]**

#### MaterialSpecularColor [SimTalk]

Sets the specular color of the graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access the attribute if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialSpecularColor := makeRGBValue(0,255,0)
```

See also

Edit 3D Properties [dialog] &gt; Material [tab] &gt; Specular Color [material]

MaterialActive [SimTalk] MaterialAmbientColor [SimTalk] MaterialDiffuseColor [SimTalk] MaterialShininess [SimTalk] MaterialTransparency [SimTalk]

#### MaterialTransparency [SimTalk]

Sets the transparency of the material of the graphic designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

If your model contains several partially or fully transparent graphics behind each other from your current view point, it can happen that some or all of these graphics look wrong or seem to be missing.

This is due to heuristics without which the rendering performance would drastically decrease.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
MyStation._3D.getGraphic("default", [3,3]).MaterialTransparency := 0.9
```

See also Edit 3D Properties [dialog] &gt; Material [tab] &gt; Transparency [material] MaterialActive [SimTalk] MaterialAmbientColor [SimTalk] MaterialDiffuseColor [SimTalk] MaterialSpecularColor [SimTalk] MaterialShininess [SimTalk]

#### Name [SimTalk] - graphic

Sets the name of the graphic or graphic group designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot change the name of the graphic group named default .

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.Name:string

Assignment Value

You can assign a value of data type string .

Examples

```simtalk
Station._3D.getGraphic("default", [1]).Name := "MyGraphic"
var n:string := Station._3D.getGraphic("default", [1]).Name
```

See also

\_3D.InheritGraphics [SimTalk]

\_3D.getGraphic [SimTalk]

**Index [SimTalk] - graphic in 3D**

#### NumGraphics [SimTalk]

Returns the number of the direct child graphics index of the graphic or graphic group designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.NumGraphics → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var count : integer := MyStation._3D.getGraphic("default", [1,2,4]).NumGraphics
var count : integer := MyStation._3D.getGraphic("deco", [1,2,4]).NumGraphics
```

See also

\_3D.getGraphic [SimTalk]

#### ObstacleForWorker [SimTalk]

Sets the settings for the obstacle for the Worker of the graphic designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The attribute is not available for those object which you cannot insert directly into a Frame , for example MUs or folders . Graphics of type BarredArea do not provide the attribute as well.

**Note**

When you view the Obstacles for the Worker , you will notice that there is a gap of 40 cm between the obstacles and the objects/graphics. This is because we supposed the width which a Worker needs to pass through to be 80 cm. As our Workers do not have width as such, you see this distance between the obstacles instead.

Type

Attribute

Syntax

&lt; Path &gt;.ObstacleForWorker:string

Assignment Value

You can assign a value of data type string .

You can enter one of the following settings for graphics of type Stairs :

<!-- image -->

- "(None)"

The staircase is no obstacle for the Worker who can walk through it.

- "Bounding box"

The bounding box of the staircase is an obstacle for the Worker around which he has to walk.

- "Sides"

This setting computes the obstacle for the Worker in a way that:

- An accessible entrance toward which the staircase lead or an exit from which the staircase leads away is not obscured by the obstacle.
- The obstacle is limited to the applicable range for the respective simulation-relevant height.

You can specify one of these settings for the graphics types FactoryWalls , Fence , GroupNode , Instance , Mezzanine , Rack , and Switch , compare InternalGraphicType :

- "(None)"

The graphic is no obstacle for the Worker who can walk through it or across it.

- "Bounding box"

The bounding box of the graphic is an obstacle for the Worker around which he has to walk.

- "Graphics"

The graphics of the graphics are an obstacle for the Worker around which he has to walk.

You can specify one of these settings for graphics of type Box and Shape :

- "(None)"

The box is no obstacle for the Worker who can walk through it or across it.

- "Bounding box"

The bounding box of the box is an obstacle for the Worker around which he has to walk.

**Example**

```simtalk
Station._3D.ObstacleForWorker := "Graphics"
Station._3D.getGraphic("default", [2]).ObstacleForWorker := "(None)"
```

**See also**

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Obstacle for the Worker [drop-down list]

InternalGraphicType [SimTalk]

- \_3D.getGraphic [SimTalk]
- \_3D.ObstacleForWorker [SimTalk] for objects

Worker [object]

#### optimizeByPruningTinyGraphics [SimTalk]

Optimizes the graphic designated by &lt;Path&gt; by pruning its tiny graphics, i.e., it removes all component graphics which individually fit within the cube designated by the parameter BoundingCubeSideLength .

Remarks

Note

Assigning the method deactivates graphic inheritance.

Note

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

&lt; Path &gt;.optimizeByPruningTinyGraphics(BoundingCubeSideLength:length)

Parameter

The parameter BoundingCubeSizeLength is an array with a single value of data type real . It designates the size of the bounding box.

Example

.Models.Model.\_3D.getGraphic("deco",[1]).optimizeByPruningTinyGraphics([1], 0.001)

See also

Optimize Selected Graphic

Step 1: Prune Tiny Graphics

\_3D.getGraphic [SimTalk]

#### optimizeByStructureFlattening [SimTalk]

Optimizes the graphic designated by &lt;Path&gt;.

**Remarks**

Note

Assigning the method deactivates graphic inheritance.

**Note**

The method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

&lt; Path &gt;.optimizeByStructureFlattening(KeepGrouping:boolean, PreserveObstacles:boolean, RemovePolylinesAndPointSets:boolean[, PreserveReferences:boolean:=false])

**Parameters**

- The parameter KeepGrouping of data type boolean sets if the structure of the object will be flattened while preserving its contents ( true ) or not ( false ).
- The parameter PreserveObstacles of data type boolean sets if obstacles are preserved ( true ) or not ( false ).
- The parameter RemovePolylinesAndPointSets of data type boolean sets if polylines and point sets are deleted ( true ) or not ( false ).
- The parameter PreserveReferences of data type boolean sets if multiple references to sub-graphics are going to be preserved and thus the model size is to be kept as small as possible ( true ) or not and thus allow the model size to grow by the optimization ( false ). If the parameter KeepGrouping is true as well, the parameter PreserveReferences has no effect.

**Default Value of the Parameter**

The default value is false.

**Example**

.Models.Model._3D.getGraphic("deco", [1]).optimizeByStructureFlattening(true, true, false)

**See also**

Optimize Selected Graphic

Step 2: Flatten Structure

\_3D.getGraphic [SimTalk]

#### optimizeByVisibilityFilter [SimTalk]

Optimizes the graphic designated by &lt;Path&gt; i.e., it removes graphic components which are not visible from the outside.

Remarks

**Note**

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

&lt; Path &gt;.optimizeByVisibilityFilter(CullGranularity:integer, ReductionLevel:integer)

**Parameters**

- The parameter CullGranularity of data type integer sets the granularity for deleting graphics. 0 is very fine granular, 3 is very coarse granular.
- The parameter ReductionLevel of data type integer sets how close the procedure looks at the graphic. 0 stands for a rather coarse look which causes a lot of graphics to be deleted very quickly, 3 stands for a very close look which takes a lot longer.

**Examples**

.Models.Model.\_3D.getGraphic("default", [1]).optimizeByVisibilityFilter(0, 1)

.Models.Model.\_3D.getGraphic("deco", [2]).optimizeByVisibilityFilter(2, 1)

See also

Optimize Selected Graphic

##### Step 3: Visibility Filter

#### Position [SimTalk] - graphic

Sets the position of the graphic designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.Position:length[3]

Assignment Value

You can assign an array of data type length with three values.

They designate the position of the object on the x-axis, the y-axis, and the z-axis.

Examples

```simtalk
obj._3D.getGraphic("default", [1,7]).Position := [5,-5,0]
var p :
length[3] := obj._3D.getGraphic("deco", [1,7]).Position
```

See also

\_3D.InheritGraphics [SimTalk]

\_3D.Position [SimTalk]

X [SimTalk] - array

```simtalk
Y [SimTalk] - array Z [SimTalk] - array
_3D.getGraphic [SimTalk] Edit 3D Properties [dialog] > Transformation [3D object] > Settings for the Position [transformation] Position [SimTalk] - graphic
```

#### removeTexture [SimTalk]

Deletes an existing texture from the graphic designated by &lt;Path&gt;.

Remarks

Note

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Type

Method

Syntax

&lt; Path &gt;.removeTexture

Example

MyFrame.\_3D.getGraphic("deco", [1,2]).removeTexture

See also

Remove Texture [3D graphic]

\_3D.getGraphic [SimTalk]

#### Rotation [SimTalk] - graphic

Sets the rotation of the designated graphic designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.Rotation:real/real[4]

Assignment Value

You can specify:

- A value of data type real which sets the rotation around the negative Z-axis at the position at which you inserted the object.
- An array of data type real with four values. The first value designates the angle, the remaining three values designate the components of the rotation axis at the position at which you inserted the object.

Return Value

The return value is an array of data type real with four values.

**Examples**

```simtalk
var a : any := MyStation._3D.getGraphic("default", [1]).Rotation // returns an array of size 4 MyStation._3D.getGraphic("default", [1]).Rotation := 30 // rotates the graphic by 30 degrees MyStation._3D.getGraphic("default", [1]).Rotation := [45, 0, 1, 0] // rotates the graphic by 45 degrees around the Y-axis
```

**See also**

Edit 3D Properties [dialog] &gt; Transformation [3D object] &gt; Settings for the Rotation [transformation]

\_3D.getGraphic [SimTalk]

\_3D.Rotation [SimTalk]

F3DconcatenateRotations [SimTalk]

#### Scale [SimTalk] - graphic

Sets the scaling of the graphic designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

```simtalk
< Path >.Scale:real/real[3]
```

Assignment Value

You can specify:

- A value of data type real which sets a uniform scaling.
- An array of data type real with three values. They designate the scaling factors along the X-axis, the Y-axis, and the Z-axis.

Examples

```simtalk
obj._3D.getGraphic("default", [1,7]).Scale := 1
var w :
real[3] := obj._3D.getGraphic("deco", [1,7]).Scale
```

See also

_3D.getGraphic [SimTalk] _3D.Scale [SimTalk]

X [SimTalk] - array Y [SimTalk] - array Z [SimTalk] - array

Edit 3D Properties [dialog] &gt; Transformation [3D object] &gt; Settings for the Scale [transformation]

#### TransformationMatrix [SimTalk]

Sets the transformation matrix of the designated graphic group of the graphic designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TransformationMatrix:real[4,4]/real:[16]

Assignment Value

To set the entire transformation matrix, you can:

- Specify a two-dimensional array of data type real with 4 times 4 values.

For the two-dimensional array the matrix looks like this:

| m11   | m12   | m13   |   0 |
|-------|-------|-------|-----|
| m21   | m22   | m23   |   0 |
| m31   | m32   | m33   |   0 |
| x     | y     | z     |   1 |

The sub-matrix m contains the rotation and the scaling. The values x, y, z designate the position.

- Specify a one-dimensional array of data type real with 16 values.

For the one-dimensional array the above values are arranged in the following sequence:

m11 m12 m13 0 m21 m22 m23 0 m31 m32 m33 0 x y z 1

**Return Value**

The return value is an array of data type real with four times four values.

**Examples**

```simtalk
MyStation._3D.getGraphic("default", [1]).TransformationMatrix := [1,0,0,0, 0,1,0,0, 0,0,1,0, 3,4,0,1]
var m := MyStation._3D.getGraphic("default", [1]).TransformationMatrix
m[2,4] += 3
MyStation._3D.getGraphic("default", [2]).TransformationMatrix  := m
```

**See also**

Transformation [3D object]

addGraphicTransformation [SimTalk]

\_3D.TransformationMatrix [SimTalk]

#### ungroupGraphic [SimTalk]

Ungroups the designated group of graphics of the graphic designated by &lt;Path&gt;.

Remarks

Note

Assigning the method deactivates graphic inheritance.

**Note**

You cannot assign the method if the graphic is an automatically generated graphic group or if the graphic is located in an automatically generated graphic group.

Syntax

&lt; Path &gt;.ungroupGraphic

Type

Method

Examples

MyFrame.\_3D.getGraphic("default", [1,2,3]).ungroupGraphic

MyFrame.\_3D.getGraphic("deco", [1,2,3]).ungroupGraphic

See also

Ungroup Group of Graphics

groupGraphics [SimTalk]

\_3D.getGraphic [SimTalk]

