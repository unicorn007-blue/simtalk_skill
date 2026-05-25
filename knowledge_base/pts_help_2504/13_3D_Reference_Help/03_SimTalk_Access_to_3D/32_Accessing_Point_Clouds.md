### Accessing Point Clouds

#### \_\_Accessing Point Clouds

SimTalk provides the attributes listed in the table of contents to the left for point clouds of the Frame in 3D .

**See also**

**Edit 3D Properties [dialog] &gt; Point Cloud**

#### \_3D.PointCloudPath [SimTalk]

Sets the file path to the point cloud you want to use in the Frame designated by &lt;Path&gt;.

Remarks

Provided the path is relative, it refers to the folder in which your simulation model is located.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.PointCloudPath:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
.Models.MyFrame._3D.PointCloudPath := "C:\Program Files\Siemens\Plant Simulation 2504\3D\Siemens_Stand_Layers rotate 180degree.pod"
```

See also

Edit 3D Properties [dialog] &gt; Point Cloud &gt; File Path

#### \_3D.PointCloudPosition [SimTalk]

Sets the position of the point cloud in the Frame designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >._3D.PointCloudPosition:array

Assignment Value

You can assign a value of data type array .

The values designate the x-position, the y-position, and the z-position of the point cloud in the simulation model.

Example

```simtalk
.Models.MyFrame._3D.PointCloudPosition := [2, 3, 0]
var a := .Models.MyFrame._3D.PointCloudPosition
```

See also

Edit 3D Properties [dialog] &gt; Point Cloud &gt; Position [point cloud]

#### \_3D.PointCloudRotation [SimTalk]

Sets the rotation, i.e., the rotation angle and the rotation axis of the point cloud in the Frame designated by &lt;Path&gt;.

Remarks

3D interprets the rotation angle as a rotation around the negative z-axis. This corresponds to the rotation angles in 2D.

Type

Attribute

Syntax

< Path >._3D.PointCloudRotation:any

Assignment Value

You can specify:

- A number which defines the rotation around the negative z-axis at the position at which you inserted the object. This is the axis that causes a rotation that matches the rotation in 2D.
- An array with four values.
- The first value designates the angle, the remaining three values designate the components of the rotation axis.

Return Value

When querying the attribute, 3D returns an array with four items

Example

```simtalk
.Models.MyFrame._3D.PointCloudRotation := 30             // rotation by 30 degrees .Models.MyFrame._3D.PointCloudRotation := [45, 0, 1, 0]  // rotates by 45 degrees // around the y axis
```

See also

Edit 3D Properties [dialog] &gt; Point Cloud &gt; Rotation [point cloud]

**Accessing Video Recording Settings**

