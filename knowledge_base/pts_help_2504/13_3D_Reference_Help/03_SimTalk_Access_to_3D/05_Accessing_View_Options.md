### Accessing View Options

#### \_\_Accessing View Options

SimTalk provides the attributes listed in the table of contents to the left for setting view options of the Frame in 3D .

See also

View Ribbon Tab [3D only]

#### \_3D.PlanningView [SimTalk]

Activates ( true ) or deactivates ( false ) the Planning View in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.PlanningView:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.PlanningView := true
```

See also

View Ribbon Tab [3D only] &gt; Use Planning View

#### \_3D.ShowBasePlate [SimTalk]

Shows ( true ) or hides the base plate ( false ) below the grid in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowBasePlate:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowBasePlate := false
```

See also

View Ribbon Tab [3D only] &gt; Show Base Plate

#### \_3D.ShowConnections [SimTalk]

Shows Connectors/Interfaces/Markers in the active 3D window of the Frame designated by &lt;Path&gt; ( true ) or hides them ( false ).

Remarks

Also shows or hides material flow directions of the length-oriented objects for which you set \_3D.ShowMaterialFlowDirection to true .

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowConnections:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowConnections := false
```

See also

View Ribbon Tab [3D only] &gt; Show Connections [View ribbon] - 3D

Show Material Flow Direction

\_3D.ShowMaterialFlowDirection [SimTalk]

#### \_3D.ShowExternalGraphics [SimTalk]

Shows ( true ) or hides ( false ) external graphics in the Frame designated by &lt;Path&gt; .

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowExternalGraphics:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowExternalGraphics := false
```

See also

View Ribbon Tab [3D only] &gt; Show External Graphic Groups

#### \_3D.ShowGrid [SimTalk]

Shows ( true ) or hides ( false ) the grid in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowGrid:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowGrid := false
```

See also

View Ribbon Tab [3D only] &gt; Show Grid [View ribbon] - 3D

#### \_3D.ShowLabels [SimTalk]

Shows ( true ) or hides ( false ) the labels of the objects in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowLabels:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowLabels := false
```

See also

View Ribbon Tab [3D only] &gt; Show Object Names [View ribbon] - 3D

#### \_3D.ShowNames [SimTalk]

Shows ( true ) or hides ( false ) the names of the objects in the Frame designated by &lt;Path&gt; .

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowNames:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowNames := false
```

See also

View Ribbon Tab [3D only] &gt; Show Object Names [View ribbon] - 3D

#### \_3D.ShowPointClouds [SimTalk]

Shows ( true ) or hides ( false ) point clouds in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowPointClouds:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowPointClouds := false
```

See also

View Ribbon Tab [3D only] &gt; Show Point Clouds

#### \_3D.ShowShadows [SimTalk]

Shows ( true ) or hides ( false ) shadows in the Frame designated by &lt;Path&gt; .

Remarks

Plant Simulation only shows the shadows of the objects in a Frame .

Captions, manipulators, path visualizations, and some display objects, for example Variable , Comment , etc. do not throw a shadow most of the time.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowShadows:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowShadows := false
```

See also

View Ribbon Tab [3D only] &gt; Show Shadows

#### \_3D.ShowSky [SimTalk]

Shows ( true ) or hides ( false ) the sky in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowSky:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame._3D.ShowSky := true
```

See also

View Ribbon Tab [3D only] &gt; Show Sky

#### \_3D.ShowUserDefinedAttributes [SimTalk]

Shows ( true ) or hides ( false ) the user-defined attributes of the objects in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowUserDefinedAttributes:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

MyFrame.\_3D.ShowUserDefinedAttributes := false

See also

View Ribbon Tab [3D only] &gt; Show User-defined Attributes [View ribbon] - 3D

