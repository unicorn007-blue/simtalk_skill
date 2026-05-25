### Accessing the Bounding Box

#### \_\_Accessing the Bounding Box

SimTalk provides the read-only attributes listed in the table of contents to the left for measuring the bounding box of the visible graphics of an object.

**Note**

All data concerning the bounding box relate to the local object coordinate system.

The individual values of the bounding box relate to each other as follows:

- \_3D.BoundingBoxMin plus \_3D.BoundingBoxMax divided by 2 results in the \_3D.BoundingBoxCenter .
- \_3D.BoundingBoxMax minus \_3D.BoundingBoxMin results in the \_3D.BoundingBoxSize .

\_3D.BoundingBoxMax has to be equal to or greater than \_3D.BoundingBoxMin .

See also

getBoundingBox [SimTalk] in 2D

#### \_3D.BoundingBoxCenter [SimTalk]

Returns the center of the bounding box of the object designated by &lt;Path&gt;.

Remarks

The bounding box excludes all invisible graphics.

Type

Read-only attribute

Syntax

< Path >._3D.BoundingBoxCenter → length[3]

Return Value

The return value is an array of data type length with three values.

They designate the x-position, the y-position, and the z-position of the center point of the bounding box.

Example

```simtalk
var a :
real[3] := MyStation._3D.BoundingBoxCenter
```

#### \_3D.BoundingBoxMax [SimTalk]

Returns the upper right vertex of the bounding box of the object designated by &lt;Path&gt;.

Remarks

The bounding box excludes all invisible graphics.

The individual values of the bounding box relate to each other as follows:

\_3D.BoundingBoxMin plus \_3D.BoundingBoxMax divided by 2 results in the \_3D.BoundingBoxCenter .

\_3D.BoundingBoxMax minus \_3D.BoundingBoxMin results in the \_3D.BoundingBoxSize .

\_3D.BoundingBoxMax has to be equal to or greater than \_3D.BoundingBoxMin .

Type

Read-only attribute

Syntax

< Path >._3D.BoundingBoxMax → length[3]

Return Value

The return value is an array of data type length with three values.

They designate the x-position, the y-position, and the z-position of the upper right vertex of the bounding box.

**Example**

```simtalk
var a :
length[3] := MyStation._3D.BoundingBoxMax
```

#### \_3D.BoundingBoxMin [SimTalk]

Returns the lower left vertex of the bounding box of the object designated by &lt;Path&gt;.

Remarks

The bounding box excludes all invisible graphics.

The individual values of the bounding box relate to each other as follows:

- \_3D.BoundingBoxMin plus \_3D.BoundingBoxMax divided by 2 results in the \_3D.BoundingBoxCenter .
- \_3D.BoundingBoxMax minus \_3D.BoundingBoxMin results in the \_3D.BoundingBoxSize .

\_3D.BoundingBoxMax has to be equal to or greater than \_3D.BoundingBoxMin .

Type

Read-only attribute

Syntax

< Path >._3D.BoundingBoxMin → length[3]

Return Value

The return value is an array of data type length with three values.

They designate the x-position, the y-position, and the z-position of the lower left vertex of the bounding box.

Example

```simtalk
var a :
length[3] := MyStation._3D.BoundingBoxMin
```

#### \_3D.BoundingBoxSize [SimTalk]

Returns the size of the bounding box of the object designated by &lt;Path&gt;.

Remarks

The bounding box excludes all invisible graphics.

The bounding box of an object encloses its graphics and its animatable objects. In addition, the bounding box of a Frame encloses its static simulation objects. A MU instance does not belong to the bounding box of the object that is currently transporting it. The bounding box of a pallet does, for example, not include the parts loaded onto the pallet.

The individual values of the bounding box relate to each other as follows:

- \_3D.BoundingBoxMin plus \_3D.BoundingBoxMax divided by 2 results in the \_3D.BoundingBoxCenter .
- \_3D.BoundingBoxMax minus \_3D.BoundingBoxMin results in the \_3D.BoundingBoxSize .
- \_3D.BoundingBoxMax has to be equal to or greater than \_3D.BoundingBoxMin .

Type

Read-only attribute

Syntax

< Path >._3D.BoundingBoxSize → array

Return Value

The return value has the data type array .

The return values designate the length (x-dimension), the width (y-dimension), and the height (zdimension) of the bounding box.

Example

```simtalk
var a :
real[3] := MyStation._3D.BoundingBoxSize
```

