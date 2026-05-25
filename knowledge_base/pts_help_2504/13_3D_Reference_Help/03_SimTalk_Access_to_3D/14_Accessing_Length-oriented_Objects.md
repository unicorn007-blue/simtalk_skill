### Accessing Length-oriented Objects

#### \_\_Accessing Length-oriented Objects

SimTalk provides the attributes and methods listed in the table of contents to the left for defining lengthoriented objects in 3D .

You can view and access the attributes and methods for defining length-oriented objects by clicking Auto Complete on the Edit ribbon tab of the Method Editor .

<!-- image -->

**See also**

Auto Complete

#### \_3D.AniGravityMode [SimTalk]

Activates Gravity Mode of the length-oriented object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

This setting only applies to the length-oriented objects . It is especially helpful for suspension tracks, etc.

Gravity Mode only affects automatic animations, that is animations for which you did not specify an animation path.

On a suspension track the part is always placed perpendicular to the floor in Gravity Mode , either hanging from a rail on the ceiling or standing up on a rail on the floor.

Type

Attribute

Syntax

```simtalk
< Path >._3D.AniGravityMode:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyConveyor._3D.AniGravityMode := true
```

See also

Gravity Mode

#### \_3D.AnimationOffset [SimTalk]

Sets the Animation Offset of the length-oriented object designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >._3D.AnimationOffset:length[3]

Assignment Value

You can assign an array of data type length with three values.

They set the offset of the animation path to the surface of the object along the X direction, the Y direction, and the Z direction.

Example

```simtalk
MyConveyor._3D.AnimationOffset := [0m, 0m, 1m]
```

See also

Animation Offset

#### \_3D.AniSmoothRotation [SimTalk]

Activates Smooth Rotation of the length-oriented object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

This setting only applies to the length-oriented objects . It is especially helpful for suspension tracks, etc.

Smooth Rotation only affects automatic animations, that is animations for which you did not specify an animation path.

If the object currently animates its MUs using a user-defined Animation Path Type &gt; Lines , Smooth Rotation specifies whether the part slowly changes its rotation around the anchor points (like this is the case on a Station ( true ) for example) or if it abruptly changes its orientation (like at a corner on a Conveyor with the standard MU animation) ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.AniSmoothRotation:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.\_3D.AniSmoothRotation := true

See also

Smooth Rotation

#### \_3D.BaseHeight [SimTalk] - 3D

Sets the Base Height of the length-oriented object designated by &lt;Path&gt;.

Remarks

The Base Height sets the distance between the insertion height (z-coordinate) of the length-oriented object and the height of a segment whose ΔZ equals 0.

<!-- image -->

The base height can be inherited, meaning that you can define it once in the class of the object instead of having to define it for each instance individually. The z-coordinate defines the floor of the installation and the base height defines the distance of the legs from the floor. By changing the setting ΔZ in the Segments table, you can add an additional offset. The setting ΔZ also affects the simulation time in Plant Simulation 2D.

**Note**

Normally, the Base Heights in 2D and in 3D are identical. They might differ if you clear Connect 2D and 3D Positions under Edit 3D Properties &gt; Tab Transformation &gt; Position in a 2D and 3D model .

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.BaseHeight:length

Assignment Value

You can assign a value of data type length .

**Example**

```simtalk
MyConveyor._3D.BaseHeight := 3
print MyConveyor._3D.BaseHeight
```

**See also**

Base Height [curve] in 2D

BaseHeight [SimTalk] - material flow objects

Base Height [tab Appearance]

Insert Curved and Straight Segments &gt; Anchor Point Height

#### \_3D.ExtConfiguration [SimTalk]

Sets the extrusion configuration of the length-oriented object designated by &lt;Path&gt;.

Remarks

An example of an extrusion configuration might look like this:

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.ExtConfiguration:table

Parameters of the Extrusion Configuration

The parameters of the extrusion configuration designate the following settings:

- Index Name : Is the name of the extrusion group, it is only entered once for each group in the first column of the group, i.e., in column 0.
- Extrusion Profile : The subtable [2 x number of points], which you can open by double-clicking in the cell Extrusion Profile , specifies the profile that will be extruded according to the settings below. Define the values in a way so that they match a width of 1 meter.
- Configuration Type : You can set the following values:

| Name/Value for Assignment              | Description                                                                                                                                                              |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Path, z max, Move abs / 0              | Extrude once along the path with z as defined in the anchors, the distance from the edge remains fixed when changing the width.                                          |
| Path, z max, Move rel / 1              | Extrude once along the path with z as defined in the anchors and pin the profile base point to its relative position when changing the width.                            |
| Path, z max, Scale x / 2               | Extrude once along the path with z as defined in the anchors and scale in the x-direction when changing the width.                                                       |
| Path, z max, Scale xy / 3              | Extrude once along the path with z as defined in the anchors and scale in the x-direction and the y-direction when changing the width.                                   |
| Path, Floor, Move abs / 4              | Extrude once along the path with z = 0.0, the distance from the edge remains fixed when changing the width.                                                              |
| Path, Floor, Move rel / 5              | Extrude once along the path with z = 0.0 and pin the profile base point to its relative position when changing the width.                                                |
| Path, Floor, Scale x / 6               | Extrude once along the path with z = 0.0 and scale in the x-direction when changing the width.                                                                           |
| Path, Floor, Scale xy / 7              | Extrude once along the path with z = 0.0 and scale in the x-direction and the y-direction when changing the width.                                                       |
| Horizontal, Anchors, z max, Move / 8   | Extrude horizontally for every anchor point with z as defined in the anchors and pin to the borders when changing the width. The graphic tilts according to the incline. |
| Horizontal, Anchors, z max, Scale / 9  | Extrude horizontally for every anchor point with z as defined in the anchors and pin to the center when changing the width. The graphic tilts according to the incline.  |
| Horizontal, Anchors, z 1/5, Move / 10  | Extrude horizontally for every anchor point with z = 1/5 of the anchor point height and pin to the borders when changing the width.                                      |
| Horizontal, Anchors, z 1/5, Scale / 11 | Extrude horizontally for every anchor point with z = 1/5 of the anchor point height and pin to the center when changing the width.                                       |

| Name/Value for Assignment               | Description                                                                                                                                                             |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Horizontal, Anchors, Floor, Move / 12   | Extrude horizontally for every anchor point with z = 0.0 and pin to the borders when changing the width.                                                                |
| Horizontal, Anchors, Floor, Scale / 13  | Extrude horizontally for every anchor point with z = 0.0 and pin to the center when changing the width.                                                                 |
| Horizontal, Interval, z max, Move / 14  | Extrude horizontally with a fixed interval with z as defined in the anchors and pin to the borders when changing the width. The graphic tilts according to the incline. |
| Horizontal, Interval, z max, Scale / 15 | Extrude horizontally with a fixed interval with z as defined in the anchors and pin to the center when changing the width. The graphic tilts according to the incline.  |
| Horizontal, Interval, z 1/5, Move / 16  | Extrude horizontally with a fixed interval with z = 1/5 of the anchor point height and pin to the borders when changing the width.                                      |
| Horizontal, Interval, z 1/5, Scale / 17 | Extrude horizontally with a fixed interval with z = 1/5 of the anchor point height and pin to the center when changing the width.                                       |
| Horizontal, Interval, Floor, Move / 18  | Extrude horizontally with a fixed interval with z = 0.0 and pin to the borders when changing the width.                                                                 |
| Horizontal, Interval, Floor, Scale / 19 | Extrude horizontally with a fixed interval with z = 0.0 and pin to the center when changing the width.                                                                  |
| Vertical, Floor, Anchors, Move / 20     | Extrude vertically for every anchor point from the path anchor to the floor and pin to the borders when changing the width.                                             |
| Vertical, Floor, Anchors, Fix / 21      | Extrude vertically for every anchor point from the path anchor to the floor and pin to the center when changing the width.                                              |
| Vertical, Interval, Move / 22           | Extrude vertically with a fixed interval from the path anchor to the floor and pin to the borders when changing the width.                                              |
| Vertical, Interval, Fix / 23            | Extrude vertically with a fixed interval from the path anchor to the floor and pin to the center when changing the width.                                               |

| Name/Value for Assignment               | Description                                                                                                                                                             |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Forward, z max, Anchors, Move abs / 24  | Repeatedly extrude a small segment in the path direction for each anchor point, the distance from the borders remains fixed when changing the width.                    |
| Forward, z max, Anchors, Move rel / 25  | Repeatedly extrude a small segment in the path direction for each anchor point, and pin the base point of the profile to its relative position when changing the width. |
| Forward, z max, Anchors, Fix / 26       | Repeatedly extrude a small segment in the path direction for each anchor point, the distance from the center remains fixed when changing the width.                     |
| Forward, z max, Interval, Move abs / 27 | Repeatedly extrude a small segment in the path direction with a fixed interval, the distance from the borders remains fixed when changing the width.                    |
| Forward, z max, Interval, Move rel / 28 | Repeatedly extrude a small segment in the path direction with a fixed interval, and pin the base point of the profile to its relative position when changing the width. |
| Forward, z max, Interval, Fix / 29      | Repeatedly extrude a small segment in the path direction with a fixed interval, the distance from the center remains fixed when changing the width.                     |
| Vertical, z max, Anchors, Move / 30     | Extrude vertically for each anchor point at the height of the path anchor point and pin to the borders when changing the width.                                         |
| Vertical, z max, Anchors, Fix / 31      | Extrude vertically for each anchor point at the height of the path anchor point and pin to the center when changing the width.                                          |
| Vertical, z max, Interval, Move / 32    | Extrude vertically with a fixed interval at the height of the path anchor point and pin to the borders when changing the width.                                         |
| Vertical, z max, Interval, Fix / 33     | Extrude vertically with a fixed interval at the height of the path anchor point and pin to the center when changing the width.                                          |
| Forward, Floor, Anchors, Move abs / 34  | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, the distance from the borders remains fixed when changing the width.       |

| Name/Value for Assignment                 | Description                                                                                                                                                                          |
|-------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Forward, Floor, Anchors, Move rel / 35    | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, and pin the base point of the profile to its relative position when changing the width. |
| Forward, Floor, Anchors, Fix / 36         | Repeatedly extrude a small segment in the path direction for each anchor point with z = 0.0, the distance from the center remains fixed when changing the width.                     |
| Forward, Floor, Interval, Move abs / 37   | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, the distance from the borders remains fixed when changing the width.                    |
| Forward, Floor, Interval, Move rel / 38   | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, and pin the base point of the profile to its relative position when changing the width. |
| Forward, Floor, Interval, Fix / 39        | Repeatedly extrude a small segment in the path direction with a fixed interval with z = 0.0, the distance from the center remains fixed when changing the width.                     |
| Vertical, Ceiling, Anchors, Move / 40     | Extrude vertically for each anchor point from the path anchor point to the ceiling and pin to the borders when changing the width. The end offset denotes the ceiling height.        |
| Vertical, Ceiling, Anchors, Fix / 41      | Extrude vertically for each anchor point from the path anchor point to the ceiling and pin to the center when changing the width. The end offset denotes the ceiling height.         |
| Vertical, Ceiling, Interval, Move / 42    | Extrude vertically with a fixed interval from the path anchor point to the ceiling and pin to the borders when changing the width. The end offset denotes the ceiling height.        |
| Vertical, Ceiling, Interval, Fix / 43     | Extrude vertically with a fixed interval from the path anchor point to the ceiling and pin to the center when changing the width. The end offset denotes the ceiling height.         |
| Horizontal, Anchors, z max Gr, Scale / 45 | Extrude horizontally for each anchor point with z as defined in the anchor points and pin to the center when changing the width.                                                     |

| Name/Value for Assignment                  | Description                                                                                                                        |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| Horizontal, Interval, z max Gr, Move / 46  | Extrude horizontally with a fixed interval with z, as defined in the anchor points and pin to the borders when changing the width. |
| Horizontal, Interval, z max Gr, Scale / 47 | Extrude horizontally with a fixed interval with z, as defined in the anchor points and pin to the center when changing the width.  |

- Start Offset : Is the offset of the start reference in the extrusion direction.
- End Offset : Is the offset of the end reference in the extrusion direction.
- Repetition Interval : For the configuration types 14, 15, 16, 17, 18, 19, 22, and 23 the value 0 means that the extrusion is being generated once at the start point of the object. A value greater than 0 means that the extrusion is generated every number of meters that you enter. If you specify 0.5 , the extrusion will be generated every 50 cm along the &lt;Path&gt;. For the other values, this value is meaningless, and Plant Simulation only accepts 0.
- Graphic Group ID : By default this value is 0. A value between 0 and 10 generates additional graphic groups into which the program places these thus marked extrusions. The Fluid object Pipe for example uses this feature.
- Material : In the subtable Material , which you can open by double-clicking in the cell Material , you can set the following:

The Diffuse Color [MUs] , compare makeRGBValue [SimTalk] . The Ambient Color [MUs] , compare makeRGBValue [SimTalk] . The Specular Color [MUs] , compare makeRGBValue [SimTalk] . The Emissive Color [MUs] , compare makeRGBValue [SimTalk] . The Transparency [MUs] . The Shininess [MUs] .

**Assignment Value**

You can a value of data type table containing the extrusion configuration.

```simtalk
Note This attribute returns a copy of the values. Compare these examples:
Conveyor._3D.ExtConfiguration := MyExtrusionConfigurationTable      // assigns a new value
MyExtrusionConfigurationTable := Conveyor._3D.ExtConfiguration      // reads a value
This example seems to have the correct syntax, but does not have any effects:
Conveyor._3D.ExtConfiguration[2,1] := 2 // does not assign the subtable to the first cell of the attribute To get the desired result of the above instruction, enter this source code:
var extConfTable := Conveyor._3D.ExtConfiguration
extConfTable[2,1] := 2
Conveyor._3D.ExtConfiguration := extConfTable
```

**Example**

```simtalk
Conveyor._3D.ExtConfiguration := MyExtrusionConfigurationTable
MyExtrusionConfigurationTable := Conveyor._3D.ExtConfiguration
```

Note To copy the attribute \_3D.ExtConfiguration to a DataTable in a Frame , this does not work via a simple assignment with := but by copying format and contents of the DataTable . Compare the example below: var MyExtrusionConfigurationTable : table := Conveyor.\_3D.ExtConfiguration

MyDataTable.delete MyExtrusionConfigurationTable.copyFormatTo(MyDataTable) MyExtrusionConfigurationTable.copyRangeTo({0,0}..{*,*}, MyDataTable, 0, 0)

**See also**

Appearance of the Length-oriented Objects in the dialog Edit 3D Properties

User-defined [Conveyor type]

makeRGBValue [SimTalk]

#### \_3D.getExtSegments [SimTalk]

Gets the segments table of the length-oriented object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >._3D.getExtSegments(Table:table)
```

Parameter

The parameter Table of data type table designates the table into which Plant Simulation writes the settings of the segments table.

**Example**

MyConveyor.\_3D.getExtSegments(extSegmentsTable)

**See also**

| _3D.setExtSegments [SimTalk]   | Length [SimTalk] - animatable object           |
|--------------------------------|------------------------------------------------|
| Segments [tab Appearance] - 3D | Segments [curve] - 2D, described               |
| getCurveSegments [SimTalk]     | Tab Curve [general description]                |
| setCurveSegments [SimTalk]     | Reuse the Segments of a Length-oriented Object |

#### \_3D.setExtSegments [SimTalk]

Sets the segments table of the length-oriented object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.3D.setExtSegments(Table:table)

Parameter

The parameter Table of data type table designates the table from which Plant Simulation imports the settings of the segments table.

**Example**

MyConveyor.\_3D.setExtSegments(extSegmentsTable)

**See also**

| _3D.getExtSegments [SimTalk]   | Length [SimTalk] - animatable object           |
|--------------------------------|------------------------------------------------|
| Segments [tab Appearance] - 3D | Segments [curve] - 2D, described               |
| getCurveSegments [SimTalk]     | Tab Curve [general description]                |
| setCurveSegments [SimTalk]     | Reuse the Segments of a Length-oriented Object |

#### \_3D.ShowMaterialFlowDirection [SimTalk]

Shows the material flow direction of the length-oriented object designated by &lt;Path&gt; ( true ) along the insertion direction or hides it ( false ).

Remarks

**Note**

\_3D.ShowMaterialFlowDirection only applies to simulation objects and animatable objects which are length-oriented and which have a meaningful material flow direction.

As the FootPath does not have a meaningful material flow direction, it does not show the direction arrow despite being length-oriented.

Show Connections on the View ribbon tab shows or hides the material flow direction of all objects in a 3D window for which you set \_3D.ShowMaterialFlowDirection to true .

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.ShowMaterialFlowDirection:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.\_3D.ShowMaterialFlowDirection := false See also Show Material Flow Direction Show Connections [View ribbon] - 3D

\_3D.ShowConnections [SimTalk]

#### \_3D.ShowSensors [SimTalk]

Shows ( true ) or hides ( false ) the sensors of the length-oriented object designated by &lt;Path&gt; in 3D.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowSensors:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyConveyor._3D.ShowSensors := false
```

See also

Sensors [general description]

Show Sensors [check box]

#### \_3D.Width [SimTalk]

Sets the width of the length-oriented object designated by &lt;Path&gt;.

Remarks

The width only applies for the simulation when the setting Transfer Length in 2D is activated.

Type

Attribute

Syntax

```simtalk
< Path >._3D.Width:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
Conveyor._3D.Width := 2
```

See also

Width [tab Appearance] in the dialog Edit 3D Properties

Transfer Length

**Accessing Functions of the Extrusion Profile**

