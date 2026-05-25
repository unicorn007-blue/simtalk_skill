### Accessing State Graphics

#### \_\_Accessing State Graphics

SimTalk provides the attributes listed in the table of contents to the left for state graphics of the material flow and of the fluid objects.

See also

Edit 3D Properties [dialog] &gt; States

#### \_3D.StatesForColoring [SimTalk]

Sets which states are considered for state coloring of the object designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.StatesForColoring:string[]

**Assignment Value**

You can assign an array of data type string .

| State of the object     | Color      |
|-------------------------|------------|
| Unplanned               | light blue |
| Paused                  | blue       |
| Failed                  | red        |
| Stopped                 | pink       |
| Powering up/down        | purple     |
| Off                     | dark gray  |
| Standby                 | light gray |
| Working                 | green      |
| Blocked                 | yellow     |
| Setting-Up              | brown      |
| Entrance closed         | cyan       |
| Waiting                 | orange     |
| In execution ( Method ) | dark green |
| Suspended ( Method )    | purple     |

| State of the object          | Color     |
|------------------------------|-----------|
| Encrypted ( Method )         | gray      |
| Syntax error ( Method )      | light red |
| Program inherited ( Method ) | turquoise |

**Note**

You can only assign the states that apply to the respective object.

**Example**

```simtalk
MyParallelStation._3D.StatesForColoring := ["Failed", "Stopped", "Unplanned", "Paused", "Working", "Blocked", "Setting-up"]
```

**See also**

States &gt; Orientation [state graphic]

#### \_3D.StatesOrientation [SimTalk]

Sets the orientation and the color of the state graphics of the object designated by &lt;Path&gt;.

Remarks

When you set the attribute, Plant Simulation deletes existing state graphics or re-creates them with the orientation you set. Plant Simulation also resets the transformation (position and scaling) of the state graphic.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.StatesOrientation:string

Assignment Value

You can assign a value of data type string .

You can specify "(Off)" , "Horizontal" , "Vertical" , or "Color" .

Example

```simtalk
MyStation._3D.StatesOrientation := "Horizontal"
```

See also

States &gt; Orientation [state graphic]

#### \_3D.StatesPosition [SimTalk]

Sets the reference point of the state graphic of the object designated by &lt;Path&gt;.

Remarks

This moves all state graphics according to this value.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

< Path >._3D.StatesPosition:length[]

Assignment Value

You can assign an array of data type length .

Example

```simtalk
MyStation._3D.StatesPosition := [-1, 1, 1]
```

See also

States &gt; Position [state graphic]

\_3D.Position [SimTalk]

Position [SimTalk] - graphic

_3D.StatesScale [SimTalk]

#### \_3D.StatesScale [SimTalk]

Sets the scaling of the state graphic of the object designated by &lt;Path&gt;.

Remarks

Scaling changes the size and the position of all state graphics.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

```simtalk
< Path >._3D.StatesScale:real/real[3]
```

**Assignment Value**

- You can assign a value of data type real to use uniform scaling.
- You can assign an array of data type real with three values to use different scaling factors for the three axes.

Return Value

The return value is always an array with three values.

**Example**

```simtalk
MyStation._3D.StatesScale := 1          // uniform scaling
MyStation._3D.StatesScale := [1, 4, 9]  // different scaling factors for the x-axis, y-axis and z-axis
var a := MyStation._3D.StatesScale      // 'a' designates an array
```

**See also**

States &gt; Scale [state graphic]

_3D.Scale [SimTalk] Scale [SimTalk] - graphic

X [SimTalk] - array Y [SimTalk] - array Z [SimTalk] - array

\_3D.StatesScale [SimTalk]

#### \_3D.StatesScaleWithObject [SimTalk]

Scales the state graphic as well, when you scale the object designated by &lt;Path&gt; ( true ) or does not scale the state graphic ( false ).

Remarks

To not scale the state graphic as well, when you scale the object itself, specify false . Plant Simulation still scales the position of the state graphic though.

Note

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.StatesScaleWithObject:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyStation.\_3D.StatesScaleWithObject := true

See also

States &gt; Scale With Object [check box]

