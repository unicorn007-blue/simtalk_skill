### \_\_Accessing the Fill Level of the Buffer

SimTalk provides the attributes listed in the table of contents to the left for accessing the fill level of the Buffer .

See also

Show Contents As

#### \_3D.FillLevelDimensions [SimTalk]

Sets the dimensions of the fill level display of the Buffer designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >._3D.FillLevelDimensions:length[2]

Assignment Value

You can assign an array of data type length with two values.

The first value designates the X-Dimension , the second designates the Y-Dimension .

Example

```simtalk
.Models.MyModel.MyBuffer._3D.FillLevelDimensions := [2, 2]
```

See also

Settings for the Dimensions

#### \_3D.FillLevelPosition [SimTalk]

Sets the position of the fill level display of the Buffer designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >._3D.FillLevelPosition:length[3]

Assignment Value

You can assign an array with three values of data type length

The first value designates the X-axis , the second the Y-axis , and the third the Z-axis .

Example

```simtalk
.Models.MyModel.MyBuffer._3D.FillLevelPosition := [0, 0, 0.5]
```

See also

Settings for the Position [Buffer]

#### \_3D.FillLevelRotation [SimTalk]

Sets the rotation of the fill level display of the Buffer designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.FillLevelRotation:real/real[4]
```

Assignment Value

You can specify:

- A number which defines the rotation around the negative z-axis at the position at which you specified the fill level.
- An array with four values. The first value designates the rotation angle. The remaining three values designate the components of the rotation axis at the position at which you specified the fill level.

**Example**

```simtalk
.Models.MyModel.MyBuffer._3D.FillLevelRotation := [0.5, 1, 0, 0]
```

See also

Settings for the Rotation [Buffer]

#### \_3D.ShowContentsAs [SimTalk]

Sets how the Buffer designated by &lt;Path&gt; shows its contents .

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowContentsAs:string
```

Assignment Value

You can assign a value of data type string .

You can specify "MUs" , "Fill level" , or "Both" .

Example

```simtalk
.Models.MyModel.MyBuffer._3D.ShowContentsAs := "Both"
```

See also

Show Contents As

