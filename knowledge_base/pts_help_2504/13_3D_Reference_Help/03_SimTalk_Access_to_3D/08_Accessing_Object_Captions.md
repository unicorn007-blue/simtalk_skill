### Accessing Object Captions

#### \_\_Accessing Object Captions

SimTalk provides the attributes listed in the table of contents to the left for accessing the captions of objects in 3D .

See also

Edit 3D Properties [dialog] &gt; Captions

#### \_3D.NameLabelEnabled [SimTalk]

Shows ( true ) or hides ( false ) the Name and the Label of the object designated by &lt;Path&gt;.

Remarks

Assigning the attribute deactivates graphic inheritance.

Plant Simulation automatically converts underscores \_ in object names to spaces.

Plant Simulation shows underscores \_ in object labels as underscores.

Type

Attribute

Syntax

```simtalk
< Path >._3D.NameLabelEnabled:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

Example

```simtalk
MyStation._3D.NameLabelEnabled := true
```

See also

Edit 3D Properties [dialog] &gt; Captions &gt; Name/Label Activated

#### \_3D.NameLabelPosition [SimTalk]

Sets the reference point of the Name and the Label of the object designated by &lt;Path&gt;.

Remarks

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

< Path >._3D.NameLabelPosition:length/length[3]

**Assignment Value**

- You can assign an array of data type length .
- You can assign a value of data type array containing three values of data type length .

**Example**

```simtalk
MyStation._3D.NameLabelPosition := [-1, 1, 1]
```

**See also**

Edit 3D Properties [dialog] &gt; Captions &gt; Settings for the Position [captions]

#### \_3D.NameLabelRotation [SimTalk]

Sets the rotation of the Name and the Label of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.NameLabelRotation:real/real[4]
```

**Assignment Value**

- You can assign a value of data type real that sets the rotation angle in degrees.
- You can assign a value of data type array containing four values of data type real .

**Examples**

```simtalk
MyStation._3D.NameLabelRotation := 45 // degrees
MyStation._3D.NameLabelRotation := [45, 0, 1, 0] // angle, components of the rotation axis
```

**See also**

Edit 3D Properties [dialog] &gt; Captions &gt; \_3D.NameLabelRotation [SimTalk]

#### \_3D.NameLabelScale [SimTalk]

Sets the scaling of the Name and the Label of the object designated by &lt;Path&gt;.

Remarks

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

```simtalk
< Path >._3D.NameLabelScale:real/real[3]
```

**Assignment Value**

- You can assign a value of data type real , which sets uniform scaling with the factor you specify.
- You can assign a value of data type array containing three values of data type real , which specify the scaling factor on the X-axis , the Y-axis , and the Z-axis .

**Example**

```simtalk
MyStation._3D.NameLabelScale := [1, 0.7, 0.4]
```

See also

Edit 3D Properties [dialog] &gt; Captions &gt; Settings for the Scale [captions]

**Accessing the Background Color of Frame and Folder**

