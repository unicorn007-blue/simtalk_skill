### \_Accessing Functions of the Extrusion Profile

SimTalk provides the functions listed in the table of contents to the left for accessing an extrusion profile.

#### F3DgenerateEllipse [SimTalk]

Creates a two-dimensional ellipse profile which you can use in your user-defined extrusion configuration.

Type

Method

Syntax

F3DgenerateEllipse(BasePoint:length[2], Width:length, Height:length, CurvePrecision:length)

**Parameters**

- The parameter BasePoint is an array of data type length with two values which set the base point of the ellipse profile.
- The parameter Width of data type length sets its width.
- The parameter Height of data type length sets its height.
- The parameter CurvePrecision of data type length sets the sampling accuracy for the generate ellipse.

**Example**

```simtalk
var profile : any := F3DgenerateEllipse([2.6,4.5], 4, 4, 0.1) //  returns a two-dimensional array containing the values defining a profile; to be used for an extrusion profile
```

**See also**

\_3D.ExtConfiguration [SimTalk]

\_3D.InheritGraphics [SimTalk]

createExtrusionGraphic [SimTalk]

F3DgenerateHollowEllipse [SimTalk]

F3DgenerateHollowRectangle [SimTalk]

F3DgenerateRectangle [SimTalk]

#### F3DgenerateHollowEllipse [SimTalk]

Creates a two-dimensional hollow ellipse profile which you can use in your user-defined extrusion configuration.

Type

Method

Syntax

F3DgenerateHollowEllipse(BasePoint:length[2], Width:length, Height:length, BarThickness:length, CurvePrecision:length)

**Parameters**

- The parameter BasePoint is an array of data type length with two values which set the base point of the hollow ellipse profile.
- The parameter Width of data type length sets its width.
- The parameter Height of data type length sets its height.
- The parameter BarThickness of data type length sets the thickness of the bar.
- The parameter CurvePrecision of data type length sets the sampling accuracy for the generate ellipse.

<!-- image -->

**F3DgenerateHollowEllipse [SimTalk]**

**Example**

```simtalk
// The following code visualizes the generated profile using cubes
var points := F3DgenerateHollowEllipse([0,0], 4, 2, 0.1, 0.1)
for var i := 1 to points.ydim
	var Cube := _3D.getGraphic("deco").createCuboid([0.03, 0.03, 0.01])
	Cube.Position := [points[1,i], points[2,i], 0.0]
	Cube.MaterialActive := true
	Cube.MaterialDiffuseColor :=  makeRGBValue(0,255,0)
next
```

**See also**

_3D.InheritGraphics [SimTalk] _3D.ExtConfiguration [SimTalk] createExtrusionGraphic [SimTalk] F3DgenerateEllipse [SimTalk] F3DgenerateHollowRectangle [SimTalk] F3DgenerateRectangle [SimTalk]

#### F3DgenerateHollowRectangle [SimTalk]

Creates a two-dimensional hollow rectangular profile which you can use in your user-defined extrusion configuration.

Type

Method

Syntax

F3DgenerateHollowRectangle(BasePoint:length[2], Width:length, Height:length, BarThickness:length)

**Parameters**

- The parameter BasePoint is an array of data type length with two values which set the base point of the hollow rectangular profile.
- The parameter Width of data type length sets its width.
- The parameter Height of data type length sets its height.
- The parameter BarThickness of data type length sets the thickness of the bar.

**Example**

```simtalk
var profile : any := F3DgenerateHollowRectangle([2.6,4.5], 4, 2, 3, 0.1) //  returns a two-dimensional array containing the values defining a profile; to be used for an extrusion profile
```

**See also**

\_3D.ExtConfiguration [SimTalk]

\_3D.InheritGraphics [SimTalk]

createExtrusionGraphic [SimTalk]

F3DgenerateEllipse [SimTalk]

F3DgenerateHollowEllipse [SimTalk]

F3DgenerateRectangle [SimTalk]

#### F3DgenerateRectangle [SimTalk]

Creates a two-dimensional rectangular profile which you can use in your user-defined extrusion configuration.

Type

Method

Syntax

F3DgenerateRectangle(BasePoint:length[2], Width:length, Height:length)

**Parameters**

- The parameter BasePoint is an array of data type length with two values which set the base point of the rectangular profile.
- The parameter Width of data type length sets its width.
- The parameter Height of data type length sets its height.

**Example**

```simtalk
var profile : any := F3DgenerateRectangle([2.6,4.5],4, 2)
```

// returns a two-dimensional array containing the values defining a profile // to be used for an extrusion profile

See also _3D.InheritGraphics [SimTalk] F3DgenerateHollowRectangle [SimTalk]

createExtrusionGraphic [SimTalk] F3DgenerateEllipse [SimTalk] F3DgenerateHollowEllipse [SimTalk] _3D.ExtConfiguration [SimTalk]

