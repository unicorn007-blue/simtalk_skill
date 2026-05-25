### Accessing Properties of Graphic Shapes

#### Accessing Properties of Graphic Shapes

SimTalk provides the attributes listed in the table of contents to the left for setting properties of graphic shapes in 3D .

See also

Insert Shape

\_Accessing Methods of Graphic Shapes

\_Accessing Attributes of Graphic Shapes

#### Board Material Attributes

\_Board Material Attributes

The Board Material of the Rack provides the attributes listed in the table of contents to the left.

See also

Rack

Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

##### BoardMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the boards of the rack designated by &lt;Path&gt;.

Remarks

You cannot assign BoardMaterialActive when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).BoardMaterialActive := true
```

**See also**

| Rack > Rack Settings                | BoardMaterialEmissiveColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| createRack [SimTalk]                | BoardMaterialShininess [SimTalk]       |
| _Rack Attributes                    | BoardMaterialSpecularColor [SimTalk]   |
| BoardMaterialAmbientColor [SimTalk] | BoardMaterialTransparency [SimTalk]    |
| BoardMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### BoardMaterialAmbientColor [SimTalk]

Sets the ambient color of the board material of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |

| _Rack Attributes                    | BoardMaterialSpecularColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| BoardMaterialAmbientColor [SimTalk] | BoardMaterialTransparency [SimTalk]    |
| BoardMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### BoardMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the board material of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |

| _Rack Attributes                    | BoardMaterialSpecularColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| BoardMaterialAmbientColor [SimTalk] | BoardMaterialTransparency [SimTalk]    |
| BoardMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### BoardMaterialEmissiveColor [SimTalk]

Sets the emissive color of the board material of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialEmissiveColor := makeRGBValue(255,0,0)
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |

| _Rack Attributes                    | BoardMaterialSpecularColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| BoardMaterialAmbientColor [SimTalk] | BoardMaterialTransparency [SimTalk]    |
| BoardMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### BoardMaterialShininess [SimTalk]

Sets the shininess of the board material of the rack designated by &lt;Path&gt;.

**Remarks**

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialShininess := 0.5
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |
| _Rack Attributes       | BoardMaterialSpecularColor [SimTalk]   |

| BoardMaterialAmbientColor [SimTalk]   | BoardMaterialTransparency [SimTalk]   |
|---------------------------------------|---------------------------------------|
| BoardMaterialDiffuseColor [SimTalk]   | _3D.getGraphic [SimTalk]              |

##### BoardMaterialSpecularColor [SimTalk]

Sets the specular color of the board material of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |

| _Rack Attributes                    | BoardMaterialSpecularColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| BoardMaterialAmbientColor [SimTalk] | BoardMaterialTransparency [SimTalk]    |
| BoardMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### BoardMaterialTransparency [SimTalk]

Sets the transparency of the board material of the rack designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BoardMaterialTransparency:real

**Assignment Value**

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BoardMaterialTransparency := 0.6
```

**See also**

| Rack > Rack Settings   | BoardMaterialEmissiveColor [SimTalk]   |
|------------------------|----------------------------------------|
| createRack [SimTalk]   | BoardMaterialShininess [SimTalk]       |
| _Rack Attributes       | BoardMaterialSpecularColor [SimTalk]   |

| BoardMaterialAmbientColor [SimTalk]   | BoardMaterialTransparency [SimTalk]   |
|---------------------------------------|---------------------------------------|
| BoardMaterialDiffuseColor [SimTalk]   | _3D.getGraphic [SimTalk]              |

#### Border Line Material Attributes

\_Border Line Material Attributes

You can set the Border Line Material around the platform of the Mezzanine with the attributes listed in the table of contents to the left.

See also

Mezzanine

createMezzanine [SimTalk]

##### BorderLineMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialActive := true
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialAmbientColor [SimTalk]

BorderLineMaterialDiffuseColor [SimTalk]

BorderLineMaterialEmissiveColor [SimTalk]

BorderLineMaterialShininess [SimTalk] BorderLineMaterialSpecularColor [SimTalk] BorderLineMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### BorderLineMaterialAmbientColor [SimTalk]

Sets the ambient color of the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialActive [SimTalk] BorderLineMaterialDiffuseColor [SimTalk] BorderLineMaterialEmissiveColor [SimTalk] BorderLineMaterialShininess [SimTalk] BorderLineMaterialSpecularColor [SimTalk] BorderLineMaterialTransparency [SimTalk]

##### BorderLineMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the borderline material around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings createMezzanine [SimTalk] BorderLineMaterialActive [SimTalk] BorderLineMaterialAmbientColor [SimTalk] BorderLineMaterialEmissiveColor [SimTalk] BorderLineMaterialShininess [SimTalk] BorderLineMaterialSpecularColor [SimTalk] BorderLineMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### BorderLineMaterialEmissiveColor [SimTalk]

Sets the emissive color of the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialEmissiveColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialActive [SimTalk] BorderLineMaterialAmbientColor [SimTalk] BorderLineMaterialDiffuseColor [SimTalk] BorderLineMaterialShininess [SimTalk] BorderLineMaterialSpecularColor [SimTalk] BorderLineMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### BorderLineMaterialShininess [SimTalk]

Sets the shininess of the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialShininess := 0.7
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialActive [SimTalk]

BorderLineMaterialAmbientColor [SimTalk]

BorderLineMaterialDiffuseColor [SimTalk] BorderLineMaterialShininess [SimTalk] BorderLineMaterialSpecularColor [SimTalk] BorderLineMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### BorderLineMaterialSpecularColor [SimTalk]

Sets the specular color of the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialSpecularColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialActive [SimTalk] BorderLineMaterialAmbientColor [SimTalk] BorderLineMaterialDiffuseColor [SimTalk] BorderLineMaterialEmissiveColor [SimTalk] BorderLineMaterialShininess [SimTalk] BorderLineMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### BorderLineMaterialTransparency [SimTalk]

Sets the transparency of the borderline material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).BorderLineMaterialTransparency := 0.4
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

BorderLineMaterialActive [SimTalk]

**Dimensioning Attributes**

BorderLineMaterialAmbientColor [SimTalk]

BorderLineMaterialDiffuseColor [SimTalk]

BorderLineMaterialEmissiveColor [SimTalk]

BorderLineMaterialShininess [SimTalk]

BorderLineMaterialSpecularColor [SimTalk]

\_3D.getGraphic [SimTalk]

#### Dimensioning Attributes

\_Dimensioning Attributes

Dimensionings provide the attributes listed in the table of contents to the left.

See also createDimensioning [SimTalk] Dimensioning

##### DimensioningSpace [SimTalk]

Sets the dimensioning space of the graphic designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DimensioningSpace:string
```

Assignment Value

You can assign a value of data type string .

You can specify "X Axis" , "Y Axis" , "Z Axis" , or "XY plane" .

**Example**

```simtalk
.Models.Model2._3D.getGraphic("deco", [2]).DimensioningSpace := "XY plane" .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint1 := [2,2,2] .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint2 := [3,4,5] .Models.Model2._3D.getGraphic("deco", [2]).TextPosition := [6,6,6]
print .Models.Model2._3D.getGraphic("deco", [2]).MeasuredLength // returns 2.23606797749979m
```

**See also**

| Insert Shape > Dimensioning   | MeasuringPoint2 [SimTalk]   |
|-------------------------------|-----------------------------|
| createDimensioning [SimTalk]  | TextPosition [SimTalk]      |
| MeasuredLength [SimTalk]      | getGraphic                  |
| MeasuringPoint1 [SimTalk]     |                             |

##### MeasuredLength [SimTalk]

MeasuredLength [SimTalk]

Returns the length of the graphic designated by &lt;Path&gt;.

Remarks

The measuring text shows this length.

Type

Read-only attribute

Syntax

< Path >.MeasuredLength -> length

Return Value

The return value has the data type length .

Example

```simtalk
.Models.Model2._3D.getGraphic("deco", [2]).DimensioningSpace := "XY plane" .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint1 := [2,2,2] .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint2 := [3,4,5] .Models.Model2._3D.getGraphic("deco", [2]).TextPosition := [6,6,6]
print .Models.Model2._3D.getGraphic("deco", [2]).MeasuredLength // returns 2.23606797749979m
```

**See also**

| Insert Shape > Dimensioning   | MeasuringPoint2 [SimTalk]   |
|-------------------------------|-----------------------------|
| createDimensioning [SimTalk]  | TextPosition [SimTalk]      |
| DimensioningSpace [SimTalk]   | _3D.getGraphic [SimTalk]    |
| MeasuringPoint1 [SimTalk]     |                             |

##### MeasuringPoint1 [SimTalk]

Sets the first measuring point of the graphic designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.MeasuringPoint1:length[3]

Assignment Value

You can assign an array of data type length with three values.

They designate the X-Position , the Y-Position , and the Z-Position of the measuring point.

**Example**

```simtalk
.Models.Model2._3D.getGraphic("deco", [2]).DimensioningSpace := "XY plane" .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint1 := [2,2,2] .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint2 := [3,4,5] .Models.Model2._3D.getGraphic("deco", [2]).TextPosition := [6,6,6]
print .Models.Model2._3D.getGraphic("deco", [2]).MeasuredLength // returns 2.23606797749979m
```

**See also**

| Insert Shape > Dimensioning   | MeasuringPoint2 [SimTalk]   |
|-------------------------------|-----------------------------|
| createDimensioning [SimTalk]  | TextPosition [SimTalk]      |
| DimensioningSpace [SimTalk]   | _3D.getGraphic [SimTalk]    |
| MeasuredLength [SimTalk]      |                             |

##### MeasuringPoint2 [SimTalk]

MeasuringPoint2 [SimTalk]

Sets the second measuring point of the graphic designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.MeasuringPoint2:length[3]

Assignment Value

You can assign an array of data type length with three values.

They designate the X-Position , the Y-Position , and the Z-Position of the measuring point.

**Example**

```simtalk
.Models.Model2._3D.getGraphic("deco", [2]).DimensioningSpace := "XY plane" .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint1 := [2,2,2] .Models.Model2._3D.getGraphic("deco", [2]).MeasuringPoint2 := [3,4,5] .Models.Model2._3D.getGraphic("deco", [2]).TextPosition := [6,6,6]
print .Models.Model2._3D.getGraphic("deco", [2]).MeasuredLength // returns 2.23606797749979m
```

**See also**

| Insert Shape > Dimensioning   | MeasuringPoint1 [SimTalk]   |
|-------------------------------|-----------------------------|
| createDimensioning [SimTalk]  | TextPosition [SimTalk]      |
| DimensioningSpace [SimTalk]   | _3D.getGraphic [SimTalk]    |
| MeasuredLength [SimTalk]      |                             |

TextPosition [SimTalk]

Sets the position of the caption of the dimensionings of the graphic designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.TextPosition:length[3]

Assignment Value

You can assign an array of data type length with three values.

They designate the X-Position , the Y-Position , and the Z-Position of the measuring point.

Example

```simtalk
.Models.Model2._3D.getGraphic("deco", [2]).TextPosition := [6,6,6]
```

**See also**

| Insert Shape > Dimensioning   | MeasuringPoint1 [SimTalk]   |
|-------------------------------|-----------------------------|
| createDimensioning [SimTalk]  | MeasuringPoint2 [SimTalk]   |
| MeasuredLength [SimTalk]      | _3D.getGraphic [SimTalk]    |

#### Factory Walls Attributes

\_Factory Walls Attributes

You can set the properties of the Factory Walls with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings createFactoryWalls [SimTalk]

\_Accessing Attributes of Graphic Shapes

##### WallElementWidth [SimTalk]

Sets the width of an entire individual element of the factory walls designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallElementWidth:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
MyStation.getGraphic("default").createFactoryWalls([11,40,3], 42cm).WallElementWidth := 150cm
print MyStation.getGraphic("default").createFactoryWalls([11,40,3], 42cm).WallElementWidth
```

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

\_3D.getGraphic [SimTalk]

#### Fence Attributes

\_Fence Attributes

The Fence provides the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

##### FenceElementWidth [SimTalk]

Sets the width of an entire individual element of the fence designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FenceElementWidth:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
MyStation.getGraphic("default").createFence([3,4,1], true, false).FenceElementWidth := 90cm
print MyStation.getGraphic("default").createFence([3,4,1], true, false).FenceElementWidth
```

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

\_3D.getGraphic [SimTalk]

**MeshActive [SimTalk]**

##### MeshActive [SimTalk]

Activates ( true ) or deactivates ( false ) a wire mesh between the fence posts of the fence designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshActive := true
```

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

\_3D.getGraphic [SimTalk]

##### PanesActive [SimTalk]

Activates ( true ) or deactivates ( false ) glass or acrylic glass panes between the fence posts of the fence designated by &lt;Path&gt;

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PanesActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PanesActive := true
```

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

\_3D.getGraphic [SimTalk]

#### Floor Material Attributes

\_Floor Material Attributes

You can set the Floor Material of the platform of the Mezzanine with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

**FloorMaterialActive [SimTalk]**

Activates ( true ) or deactivates ( false ) the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FloorMaterialActive := true
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

FloorMaterialAmbientColor [SimTalk]

FloorMaterialDiffuseColor [SimTalk]

**FloorMaterialActive [SimTalk]**

FloorMaterialEmissiveColor [SimTalk] FloorMaterialShininess [SimTalk] FloorMaterialSpecularColor [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialAmbientColor [SimTalk]**

Sets the ambient color of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FloorMaterialAmbientColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FloorMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] FloorMaterialActive [SimTalk] FloorMaterialDiffuseColor [SimTalk] FloorMaterialEmissiveColor [SimTalk] FloorMaterialShininess [SimTalk] FloorMaterialSpecularColor [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialDiffuseColor [SimTalk]**

Sets the diffuse color of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access FloorMaterialDiffuseColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FloorMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] FloorMaterialActive [SimTalk] FloorMaterialAmbientColor [SimTalk] FloorMaterialEmissiveColor [SimTalk] FloorMaterialShininess [SimTalk] FloorMaterialSpecularColor [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialEmissiveColor [SimTalk]**

Sets the emissive color of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).FloorMaterialEmissiveColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] FloorMaterialActive [SimTalk] FloorMaterialAmbientColor [SimTalk] FloorMaterialDiffuseColor [SimTalk] FloorMaterialShininess [SimTalk] FloorMaterialSpecularColor [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialShininess [SimTalk]**

Sets the shininess of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

Note

You can only access FloorMaterialShininess if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).FloorMaterialShininess := 0.2

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

FloorMaterialActive [SimTalk]

FloorMaterialAmbientColor [SimTalk] FloorMaterialDiffuseColor [SimTalk] FloorMaterialEmissiveColor [SimTalk] FloorMaterialSpecularColor [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialSpecularColor [SimTalk]**

Sets the specular color of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FloorMaterialSpecularColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).FloorMaterialSpecularColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] FloorMaterialActive [SimTalk] FloorMaterialAmbientColor [SimTalk] FloorMaterialDiffuseColor [SimTalk] FloorMaterialEmissiveColor [SimTalk] FloorMaterialShininess [SimTalk] FloorMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

**FloorMaterialTransparency [SimTalk]**

Sets the transparency of the floor material of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access FloorMaterialTransparency if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FloorMaterialTransparency := 0.5
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

**Frame Material Attributes**

createMezzanine [SimTalk]

FloorMaterialActive [SimTalk]

FloorMaterialAmbientColor [SimTalk]

FloorMaterialDiffuseColor [SimTalk]

FloorMaterialEmissiveColor [SimTalk]

FloorMaterialShininess [SimTalk]

FloorMaterialSpecularColor [SimTalk]

\_3D.getGraphic [SimTalk]

##### Frame Material Attributes

\_Frame Material Attributes

You can set the Frame Material of the Factory Walls with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Factory Walls

Mezzanine Settings

\_Accessing Attributes of Graphic Shapes

##### FrameMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FrameMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialActive := true
```

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

FrameMaterialAmbientColor [SimTalk]

FrameMaterialDiffuseColor [SimTalk]

FrameMaterialEmissiveColor [SimTalk]

FrameMaterialShininess [SimTalk] FrameMaterialSpecularColor [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialAmbientColor [SimTalk]

Sets the ambient color of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FrameMaterialAmbientColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FrameMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] FrameMaterialActive [SimTalk] FrameMaterialDiffuseColor [SimTalk] FrameMaterialEmissiveColor [SimTalk] FrameMaterialShininess [SimTalk] FrameMaterialSpecularColor [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FrameMaterialDiffuseColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FrameMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] FrameMaterialActive [SimTalk] FrameMaterialAmbientColor [SimTalk] FrameMaterialEmissiveColor [SimTalk] FrameMaterialShininess [SimTalk] FrameMaterialSpecularColor [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialEmissiveColor [SimTalk]

Sets the emissive color of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FrameMaterialEmissiveColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FrameMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialEmissiveColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] FrameMaterialActive [SimTalk] FrameMaterialAmbientColor [SimTalk] FrameMaterialDiffuseColor [SimTalk] FrameMaterialShininess [SimTalk] FrameMaterialSpecularColor [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialShininess [SimTalk]

Sets the shininess of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

Note

You can only access FrameMaterialShininess if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FrameMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).FrameMaterialShininess := 0.9

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

FrameMaterialActive [SimTalk]

FrameMaterialAmbientColor [SimTalk] FrameMaterialDiffuseColor [SimTalk] FrameMaterialEmissiveColor [SimTalk] FrameMaterialSpecularColor [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialSpecularColor [SimTalk]

Sets the specular color of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access FrameMaterialSpecularColor if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Title

Attribute

Syntax

&lt; Path &gt;.FrameMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type real .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialSpecularColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] FrameMaterialActive [SimTalk] FrameMaterialAmbientColor [SimTalk] FrameMaterialDiffuseColor [SimTalk] FrameMaterialEmissiveColor [SimTalk] FrameMaterialShininess [SimTalk] FrameMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### FrameMaterialTransparency [SimTalk]

Sets the transparency of the frame material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access FrameMaterialTransparency if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Title

Attribute

Syntax

&lt; Path &gt;.FrameMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).FrameMaterialTransparency := 0.7
```

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

**Mesh Material Attributes**

createFactoryWalls [SimTalk]

FrameMaterialActive [SimTalk]

FrameMaterialAmbientColor [SimTalk]

FrameMaterialDiffuseColor [SimTalk]

FrameMaterialEmissiveColor [SimTalk]

FrameMaterialShininess [SimTalk]

FrameMaterialSpecularColor [SimTalk]

\_3D.getGraphic [SimTalk]

**Mesh Material Attributes**

#### \_Mesh Material Attributes

You can set the Mesh Material with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Fence

Insert Shape &gt; Fence &gt; Fence Settings

createFence [SimTalk]

##### MeshMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the mesh material of the fence designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialActive := true
```

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

MeshMaterialAmbientColor [SimTalk]

MeshMaterialDiffuseColor [SimTalk]

MeshMaterialEmissiveColor [SimTalk]

MeshMaterialShininess [SimTalk] MeshMaterialSpecularColor [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialAmbientColor [SimTalk]

Sets the ambient color of the mesh material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] MeshMaterialActive [SimTalk] MeshMaterialDiffuseColor [SimTalk] MeshMaterialEmissiveColor [SimTalk] MeshMaterialShininess [SimTalk] MeshMaterialSpecularColor [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the mesh material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] MeshMaterialActive [SimTalk] WallMaterialAmbientColor [SimTalk] MeshMaterialEmissiveColor [SimTalk] MeshMaterialShininess [SimTalk] MeshMaterialSpecularColor [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialEmissiveColor [SimTalk]

Sets the emissive color of the mesh material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialEmissiveColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] MeshMaterialActive [SimTalk] WallMaterialAmbientColor [SimTalk] MeshMaterialDiffuseColor [SimTalk] MeshMaterialShininess [SimTalk] MeshMaterialSpecularColor [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialShininess [SimTalk]

Sets the shininess of the mesh material of the fence designated by &lt;Path&gt;.

Remarks

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).MeshMaterialShininess := 0.9

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

MeshMaterialActive [SimTalk]

WallMaterialAmbientColor [SimTalk] MeshMaterialDiffuseColor [SimTalk] MeshMaterialEmissiveColor [SimTalk] MeshMaterialSpecularColor [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialSpecularColor [SimTalk]

Sets the specular color of the mesh material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MeshMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialSpecularColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] MeshMaterialActive [SimTalk] WallMaterialAmbientColor [SimTalk] MeshMaterialDiffuseColor [SimTalk] MeshMaterialEmissiveColor [SimTalk] MeshMaterialShininess [SimTalk] MeshMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### MeshMaterialTransparency [SimTalk]

Sets the transparency of the mesh material of the fence designated by &lt;Path&gt;.

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

&lt; Path &gt;.MeshMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).MeshMaterialTransparency := 0.9
```

See also

Insert Shape &gt; Fence

Fence Settings

#### Mezzanine Attributes

createFence [SimTalk]

MeshMaterialActive [SimTalk]

MeshMaterialAmbientColor [SimTalk]

MeshMaterialDiffuseColor [SimTalk]

MeshMaterialEmissiveColor [SimTalk]

MeshMaterialShininess [SimTalk]

MeshMaterialSpecularColor [SimTalk]

\_3D.getGraphic [SimTalk]

**Mezzanine Attributes**

**\_Mezzanine Attributes**

You can set the properties of the Mezzanine with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

\_Accessing Attributes of Graphic Shapes

**BorderLineActive [SimTalk]**

Activates ( true ) or deactivates ( false ) the border line around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BorderLineActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).BorderLineActive := true

See also

Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

\_3D.getGraphic [SimTalk]

##### FloorThickness [SimTalk]

FloorThickness [SimTalk]

Sets the floor thickness of the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.FloorThickness:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [7]).FloorThickness := 0.05
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

\_3D.getGraphic [SimTalk]

##### PostDiameter [SimTalk] - mezzanine

Sets the diameter of the posts on which the platform of the mezzanine designated by &lt;Path&gt; rests.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostDiameter:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [7]).PostDiameter := 0.25
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

\_3D.getGraphic [SimTalk]

**RailingsActive [SimTalk]**

##### RailingsActive [SimTalk]

Activates ( true ) or deactivates ( false ) railings around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.RailingsActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).RailingsActive := true

See also

Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

\_3D.getGraphic [SimTalk]

##### RailingSegmentWidth [SimTalk]

Sets the width of the individual segments of the railing of the mezzanine designated by &lt;Path&gt;. The segment width is the distance between the individual posts that hold the railing.

Remarks

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

You can only access the attribute if the railing is active.

Note

Assigning the attribute deactivates graphic inheritance.

Type

Attribute

Syntax

&lt; Path &gt;.RailingSegmentWidth:length

Assignment Value

You can assign an array of data type length .

Example

MyFrame.\_3D.getGraphic("deco", [2]).RailingSegmentWidth := 1.2

See also

Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

\_Mezzanine Attributes

\_3D.getGraphic [SimTalk]

#### Pane Material Attributes

\_Pane Material Attributes

You can set the Pane Material of the Factory Walls and the Fence with the attributes listed in the table of contents to the left.

See also

Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

\_Factory Walls Attributes

Fence

Fence Settings

createFence [SimTalk]

\_Factory Walls Attributes

\_3D.getGraphic [SimTalk]

InternalGraphicType [SimTalk]

##### PaneMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).PaneMaterialActive := true
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialAmbientColor [SimTalk]   |
|------------------------------------------|--------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialDiffuseColor [SimTalk]   |
| _Factory Walls Attributes                | PaneMaterialEmissiveColor [SimTalk]  |
| Fence > Fence Settings                   | PaneMaterialShininess [SimTalk]      |
| createFence [SimTalk]                    | PaneMaterialSpecularColor [SimTalk]  |

| _Factory Walls Attributes   | PaneMaterialTransparency [SimTalk]   |
|-----------------------------|--------------------------------------|
| _3D.getGraphic [SimTalk]    |                                      |

##### PaneMaterialAmbientColor [SimTalk]

Sets the ambient color of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Syntax**

&lt; Path &gt;.PaneMaterialAmbientColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PaneMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

| Factory Walls > Factory Walls Settings   | RailingMaterialActive [SimTalk]     |
|------------------------------------------|-------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialDiffuseColor [SimTalk]  |
| _Factory Walls Attributes                | PaneMaterialEmissiveColor [SimTalk] |

| Fence > Fence Settings    | PaneMaterialShininess [SimTalk]     |
|---------------------------|-------------------------------------|
| createFence [SimTalk]     | PaneMaterialSpecularColor [SimTalk] |
| _Factory Walls Attributes | PaneMaterialTransparency [SimTalk]  |
| _3D.getGraphic [SimTalk]  |                                     |

##### PaneMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialDiffuseColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PaneMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialActive [SimTalk]        |
|------------------------------------------|-------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialAmbientColor [SimTalk]  |
| _Factory Walls Attributes                | PaneMaterialEmissiveColor [SimTalk] |
| Fence > Fence Settings                   | PaneMaterialShininess [SimTalk]     |
| createFence [SimTalk]                    | PaneMaterialSpecularColor [SimTalk] |
| _Factory Walls Attributes                | PaneMaterialTransparency [SimTalk]  |
| _3D.getGraphic [SimTalk]                 |                                     |

##### PaneMaterialEmissiveColor [SimTalk]

Sets the emissive color of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialEmissiveColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.Mode1._3D.getGraphic("deco", [5]).PaneMaterialEmissiveColor := makeRGBValue(0,255,0)
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialActive [SimTalk]        |
|------------------------------------------|-------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialAmbientColor [SimTalk]  |
| _Factory Walls Attributes                | PaneMaterialDiffuseColor [SimTalk]  |
| Fence > Fence Settings                   | PaneMaterialShininess [SimTalk]     |
| createFence [SimTalk]                    | PaneMaterialSpecularColor [SimTalk] |
| _Factory Walls Attributes                | PaneMaterialTransparency [SimTalk]  |
| _3D.getGraphic [SimTalk]                 |                                     |

##### PaneMaterialShininess [SimTalk]

Sets the shininess of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

**Remarks**

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialShininess:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PaneMaterialShininess := 0.8
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialActive [SimTalk]        |
|------------------------------------------|-------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialAmbientColor [SimTalk]  |
| _Factory Walls Attributes                | PaneMaterialDiffuseColor [SimTalk]  |
| Fence > Fence Settings                   | PaneMaterialEmissiveColor [SimTalk] |

| createFence [SimTalk]     | PaneMaterialSpecularColor [SimTalk]   |
|---------------------------|---------------------------------------|
| _Factory Walls Attributes | PaneMaterialTransparency [SimTalk]    |
| _3D.getGraphic [SimTalk]  |                                       |

##### PaneMaterialSpecularColor [SimTalk]

Sets the specular color of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialSpecularColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PaneMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialActive [SimTalk]        |
|------------------------------------------|-------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialAmbientColor [SimTalk]  |
| _Factory Walls Attributes                | PaneMaterialDiffuseColor [SimTalk]  |
| Fence > Fence Settings                   | PaneMaterialEmissiveColor [SimTalk] |
| createFence [SimTalk]                    | PaneMaterialShininess [SimTalk]     |
| _Factory Walls Attributes                | PaneMaterialTransparency [SimTalk]  |
| _3D.getGraphic [SimTalk]                 |                                     |

##### PaneMaterialTransparency [SimTalk]

Sets the transparency of the material of the glass or acrylic glass panes of the Factory Walls or the Fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PaneMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PaneMaterialTransparency := 0.5
```

**See also**

| Factory Walls > Factory Walls Settings   | PaneMaterialActive [SimTalk]       |
|------------------------------------------|------------------------------------|
| createFactoryWalls [SimTalk]             | PaneMaterialAmbientColor [SimTalk] |

| _Factory Walls Attributes   | PaneMaterialDiffuseColor [SimTalk]   |
|-----------------------------|--------------------------------------|
| Fence > Fence Settings      | PaneMaterialEmissiveColor [SimTalk]  |
| createFence [SimTalk]       | PaneMaterialShininess [SimTalk]      |
| _Factory Walls Attributes   | PaneMaterialSpecularColor [SimTalk]  |
| _3D.getGraphic [SimTalk]    |                                      |

**Post Material Attributes**

**\_Post Material Attributes**

You can set the Post Material of the Fence , the Mezzanine , and the Rack with the attributes listed in the table of contents to the left.

**Note**

The attributes are available for graphics of type Fence , Mezzanine , and Rack , compare InternalGraphicType .

SimTalk

**InternalGraphicType [SimTalk]**

See also

| Fence > Fence Settings         | _Mezzanine Attributes    |
|--------------------------------|--------------------------|
| createFence [SimTalk]          | Rack > Rack Settings     |
| _Factory Walls Attributes      | createRack [SimTalk]     |
| Mezzanine > Mezzanine Settings | _Rack Attributes         |
| createMezzanine [SimTalk]      | _3D.getGraphic [SimTalk] |

##### PostMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the posts of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).PostMaterialActive := true
```

**See also**

| Fence > Fence Settings         | _Rack Attributes                    |
|--------------------------------|-------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]            |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]  |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]  |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk] |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]     |

| Rack > Rack Settings   | PostMaterialSpecularColor [SimTalk]   |
|------------------------|---------------------------------------|
| createRack [SimTalk]   | PostMaterialTransparency [SimTalk]    |

##### PostMaterialAmbientColor [SimTalk]

Sets the ambient color of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialAmbientColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PostMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

| Fence > Fence Settings         | _Rack Attributes                    |
|--------------------------------|-------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]            |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]  |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]  |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk] |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]     |
| Rack > Rack Settings           | PostMaterialSpecularColor [SimTalk] |
| createRack [SimTalk]           | PostMaterialTransparency [SimTalk]  |

##### PostMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).PostMaterialDiffuseColor := makeRGBValue(255,0,0)

**See also**

| Fence > Fence Settings         | _Rack Attributes                    |
|--------------------------------|-------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]            |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]  |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]  |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk] |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]     |
| Rack > Rack Settings           | PostMaterialSpecularColor [SimTalk] |
| createRack [SimTalk]           | PostMaterialTransparency [SimTalk]  |

##### PostMaterialEmissiveColor [SimTalk]

Sets the emissive color of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialEmissiveColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PostMaterialEmissiveColor := makeRGBValue(255,0,0)
```

**See also**

| Fence > Fence Settings         | _Rack Attributes                    |
|--------------------------------|-------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]            |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]  |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]  |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk] |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]     |
| Rack > Rack Settings           | PostMaterialSpecularColor [SimTalk] |
| createRack [SimTalk]           | PostMaterialTransparency [SimTalk]  |

##### PostMaterialShininess [SimTalk]

Sets the shininess of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

**Remarks**

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PostMaterialShininess := 0.6
```

**See also**

| Fence > Fence Settings         | _Rack Attributes                   |
|--------------------------------|------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]           |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk] |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk] |

| createMezzanine [SimTalk]   | PostMaterialEmissiveColor [SimTalk]   |
|-----------------------------|---------------------------------------|
| _Mezzanine Attributes       | PostMaterialShininess [SimTalk]       |
| Rack > Rack Settings        | PostMaterialSpecularColor [SimTalk]   |
| createRack [SimTalk]        | PostMaterialTransparency [SimTalk]    |

##### PostMaterialSpecularColor [SimTalk]

Sets the specular color of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

**Remarks**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialSpecularColor:integer

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PostMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

| Fence > Fence Settings         | _Rack Attributes                    |
|--------------------------------|-------------------------------------|
| createFence [SimTalk]          | _3D.getGraphic [SimTalk]            |
| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]  |
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]  |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk] |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]     |
| Rack > Rack Settings           | PostMaterialSpecularColor [SimTalk] |
| createRack [SimTalk]           | PostMaterialTransparency [SimTalk]  |

##### PostMaterialTransparency [SimTalk]

Sets the transparency of the post material of the fence, the mezzanine, or of the rack designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostMaterialTransparency:real

**Assignment Value**

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).PostMaterialTransparency := 0.6
```

**See also**

| Fence > Fence Settings   | _Rack Attributes         |
|--------------------------|--------------------------|
| createFence [SimTalk]    | _3D.getGraphic [SimTalk] |

#### Profile Material Attributes

| _Factory Walls Attributes      | PostMaterialAmbientColor [SimTalk]   |
|--------------------------------|--------------------------------------|
| Mezzanine > Mezzanine Settings | PostMaterialDiffuseColor [SimTalk]   |
| createMezzanine [SimTalk]      | PostMaterialEmissiveColor [SimTalk]  |
| _Mezzanine Attributes          | PostMaterialShininess [SimTalk]      |
| Rack > Rack Settings           | PostMaterialSpecularColor [SimTalk]  |
| createRack [SimTalk]           | PostMaterialTransparency [SimTalk]   |

#### Profile Material Attributes

\_Profile Material Attributes

You can set the Profile Material of the Fence with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Fence

createFence [SimTalk]

##### ProfileMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the profile material of the fence designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).ProfileMaterialActive := true
```

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

ProfileMaterialAmbientColor [SimTalk]

ProfileMaterialDiffuseColor [SimTalk]

ProfileMaterialEmissiveColor [SimTalk]

ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialAmbientColor [SimTalk]

Sets the ambient color of the profile material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).ProfileMaterialAmbientColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] ProfileMaterialActive [SimTalk] ProfileMaterialDiffuseColor [SimTalk] ProfileMaterialEmissiveColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the profile material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).ProfileMaterialDiffuseColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] ProfileMaterialActive [SimTalk] ProfileMaterialAmbientColor [SimTalk] ProfileMaterialEmissiveColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialEmissiveColor [SimTalk]

Sets the emissive color of the profile material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).ProfileMaterialEmissiveColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] ProfileMaterialActive [SimTalk] ProfileMaterialAmbientColor [SimTalk] ProfileMaterialDiffuseColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialShininess [SimTalk]

Sets the shininess of the profile material of the fence designated by &lt;Path&gt;.

Remarks

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).ProfileMaterialShininess := 0.7

See also

Insert Shape &gt; Fence

Fence Settings

createFence [SimTalk]

ProfileMaterialActive [SimTalk]

ProfileMaterialAmbientColor [SimTalk] ProfileMaterialDiffuseColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialSpecularColor [SimTalk]

Sets the specular color of the profile material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).ProfileMaterialSpecularColor := makeRGBValue(255,0,0)

See also

Insert Shape &gt; Fence Fence Settings createFence [SimTalk] ProfileMaterialActive [SimTalk] ProfileMaterialAmbientColor [SimTalk] ProfileMaterialDiffuseColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### ProfileMaterialTransparency [SimTalk]

Sets the transparency of the profile material of the fence designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.ProfileMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).ProfileMaterialTransparency := 0.9
```

See also

Insert Shape &gt; Fence

Fence Settings

**Rack Attributes**

createFence [SimTalk] ProfileMaterialActive [SimTalk] ProfileMaterialAmbientColor [SimTalk] ProfileMaterialDiffuseColor [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialShininess [SimTalk] ProfileMaterialSpecularColor [SimTalk] \_3D.getGraphic [SimTalk]

#### Rack Attributes

\_Rack Attributes

You can set the properties of the Rack with the attributes listed in the table of contents to the left.

See also

Rack

Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

BayDepth [SimTalk]

Sets the depth of a single storage bay of the rack designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

Note

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

The attribute BayDepth indirectly also sets the depth of the entire rack.

Type

Attribute

Syntax

&lt; Path &gt;.BayDepth:length

Assignment Value

You can assign a value of data type length .

Example

MyFrame.\_3D.getGraphic("deco", [8]).BayDepth := 1.5

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

##### BaySize [SimTalk]

Sets the size of a single storage bay of the rack designated by &lt;Path&gt; in the XZ-dimension .

Remarks

The value for X or [0] returns the first value and the value for Y or [1] returns the second value although the orientation in the X/Z-direction is defined from the point of view of the rack.

When you assign values to the attribute, the existing capacity does not change and the overall dimensions of the storage bay, i.e., the values of the attribute Dimensions are changed as well.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

< Path >.BaySize:length[2]

Assignment Value

You can assign an array of data type length with two values.

Example

```simtalk
MyFrame._3D.getGraphic("deco", [8]).BaySize := [2, 2.5]
```

See also

Dimensions [SimTalk] - graphic

Rack &gt; Rack Settings

createRack [SimTalk]

##### \_Rack Attributes

\_3D.getGraphic [SimTalk]

##### BoardDepth [SimTalk]

Sets the depth of a board of the rack designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BoardDepth:length

Assignment Value

You can assign an array of data type length .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [8]).BoardDepth := 1.5
```

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

**BoardThickness [SimTalk]**

##### BoardThickness [SimTalk]

Sets the thickness of a board of the rack designated by &lt;Path&gt;.

Remarks

Note

The BoardThickness is not part of the height of the rack.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.BoardThickness:length

Assignment Value

You can assign a value of data type length .

Example

.Models.MyModel.\_3D.getGraphic("deco", [8]).BoardThickness := 0.025

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

##### Capacity [SimTalk] - rack

Sets the number of storage bays per board and the number of boards of the rack designated by &lt;Path&gt; in the XZ-Dimension .

Remarks

You can specify the storage bays per board in the X-direction (.X/[0]) and the number of boards in the Y-direction (.Y/[1]).

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.Capacity:integer[2]

Watchable

The attribute is watchable .

Assignment Value

You can assign an array of data type integer with two values.

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [8]).Capacity := [4, 4]
```

See also

Rack &gt; Rack Settings

createRack [SimTalk]

**\_Rack Attributes**

\_3D.getGraphic [SimTalk]

##### GroundClearance [SimTalk]

Sets the Ground Clearance of the rack designated by &lt;Path&gt;.

Remarks

The Ground Clearance is the distance between the lower edge of the lowest shelf and the floor on which the rack stands.

Specify 0 so that the lowest shelf rests flat on the floor.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

<!-- image -->

<!-- image -->

Type

Attribute

Syntax

**&lt; Path &gt;.GroundClearance:length**

Assignment Value

You can assign a value of data type length which sets the ground clearance.

Specify void to use the default ground clearance.

Example

```simtalk
Store3._3D.StoreType := "Rack with round posts (dynamic)"
Store3._3D.Gap := 0.1
Store3._3D.FloorThickness := 0.15
Store3._3D.GroundClearance := 0.3
```

See also

Appearance of the Store &gt; Ground Clearance

**MinimalStructure [SimTalk]**

##### MinimalStructure [SimTalk]

Sets if the rack designated by &lt;Path&gt; will be optimized for performance ( true ) or for post-processing capability ( false ).

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.MinimalStructure:boolean

Assignment Value

You can assign an array of data type boolean .

Example

.Models.MyModel.\_3D.getGraphic("deco", [8]).MinimalStructure := true

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_Rack Attributes

\_3D.getGraphic [SimTalk]

PostDiameter [SimTalk] - rack

Sets the diameter of the posts the rack designated by &lt;Path&gt;.

Remarks

Note

You can only access the attribute when the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

Note

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.PostDiameter:length

Assignment Value

You can assign a value of data type length .

Example

MyFrame.\_3D.getGraphic("deco", [8]).PostDiameter := 0.25

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_3D.getGraphic [SimTalk]

##### SquarePosts [SimTalk]

SquarePosts [SimTalk]

Sets if the posts the rack designated by &lt;Path&gt; are square ( true ) or round ( false ).

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.SquarePosts:boolean

Assignment Value

You can assign an array of data type boolean .

Example

```simtalk
MyFrame._3D.getGraphic("deco", [8]).SquarePosts := true
```

See also

Rack &gt; Rack Settings

createRack [SimTalk]

\_3D.getGraphic [SimTalk]

#### Railing Material Attributes

\_Railing Material Attributes

You can set the material of the railing around the platform of the Mezzanine with the attributes listed in the table of contents to the left.

Note

The railing material does not affect the handrails of the mezzanine .

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

##### RailingMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialActive := true
```

See also

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

RailingMaterialAmbientColor [SimTalk] RailingMaterialDiffuseColor [SimTalk] RailingMaterialEmissiveColor [SimTalk] RailingMaterialShininess [SimTalk] RailingMaterialSpecularColor [SimTalk] RailingMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### RailingMaterialAmbientColor [SimTalk]

Sets the ambient color of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

RailingMaterialActive [SimTalk]

RailingMaterialDiffuseColor [SimTalk]

RailingMaterialEmissiveColor [SimTalk]

RailingMaterialShininess [SimTalk]

RailingMaterialSpecularColor [SimTalk]

RailingMaterialTransparency [SimTalk]

\_3D.getGraphic [SimTalk]

##### RailingMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

RailingMaterialActive [SimTalk]

RailingMaterialAmbientColor [SimTalk]

RailingMaterialEmissiveColor [SimTalk]

RailingMaterialShininess [SimTalk]

RailingMaterialSpecularColor [SimTalk]

RailingMaterialTransparency [SimTalk]

\_3D.getGraphic [SimTalk]

##### RailingMaterialEmissiveColor [SimTalk]

Sets the emissive color of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialEmissiveColor := makeRGBValue(255,0,0)
```

**See also**

Insert Shape &gt; Mezzanine

Mezzanine Settings

createMezzanine [SimTalk]

RailingMaterialActive [SimTalk]

RailingMaterialAmbientColor [SimTalk]

RailingMaterialDiffuseColor [SimTalk]

RailingMaterialShininess [SimTalk]

RailingMaterialSpecularColor [SimTalk]

RailingMaterialTransparency [SimTalk]

\_3D.getGraphic [SimTalk]

##### RailingMaterialShininess [SimTalk]

Sets the shininess of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialShininess := 0.9
```

See also

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] RailingMaterialActive [SimTalk] RailingMaterialAmbientColor [SimTalk] RailingMaterialDiffuseColor [SimTalk] RailingMaterialEmissiveColor [SimTalk] RailingMaterialSpecularColor [SimTalk] RailingMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### RailingMaterialSpecularColor [SimTalk]

Sets the specular color of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

```simtalk
< Path >.RailingMaterialSpecularColor:integer
```

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

Insert Shape &gt; Mezzanine Mezzanine Settings createMezzanine [SimTalk] RailingMaterialActive [SimTalk] RailingMaterialAmbientColor [SimTalk] RailingMaterialDiffuseColor [SimTalk] RailingMaterialEmissiveColor [SimTalk] RailingMaterialShininess [SimTalk] RailingMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### RailingMaterialTransparency [SimTalk]

Sets the transparency of the material of the railing around the platform of the mezzanine designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The railing material does not affect the handrails of the mezzanine .

Type

Attribute

Syntax

&lt; Path &gt;.RailingMaterialTransparency:real

**Assignment Value**

You can assign a value of data type integer .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).RailingMaterialTransparency := 0.9
```

| See also                               |
|----------------------------------------|
| Insert Shape > Mezzanine               |
| Mezzanine Settings                     |
| createMezzanine [SimTalk]              |
| RailingMaterialActive [SimTalk]        |
| RailingMaterialAmbientColor [SimTalk]  |
| RailingMaterialDiffuseColor [SimTalk]  |
| RailingMaterialEmissiveColor [SimTalk] |
| RailingMaterialShininess [SimTalk]     |
| RailingMaterialSpecularColor [SimTalk] |
| _3D.getGraphic [SimTalk]               |

#### Stairs Attributes

\_Stairs Attributes

You can set the properties of the Stairs with the attributes listed in the table of contents to the left.

See also

Stairs &gt; Stairs Settings

createRack [SimTalk]

\_Stairs Attributes

\_3D.getGraphic [SimTalk]

Rise [SimTalk]

Rise [SimTalk]

Sets the height of the staircase designated by &lt;Path&gt;.

Remarks

Note

The attribute is available for graphics of type Stairs , compare InternalGraphicType .

Note

Assigning the attribute deactivates graphic inheritance.

Note

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.Rise:length

Assignment Value

You can assign an array of data type length .

Example

.Models.MyModel.\_3D.getGraphic("deco", [3]).Rise := 3.5

See also

InternalGraphicType [SimTalk]

Stairs &gt; Stairs Settings

createRack [SimTalk]

\_Stairs Attributes

**\_3D.getGraphic [SimTalk]**

Run [SimTalk]

Run [SimTalk]

Returns the depth the staircase designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.Run → length

Return Value

The return value has the data type length .

Example

```simtalk
print .Models.MyModel._3D.getGraphic("deco", [3]).Run
```

See also

Stairs &gt; Stairs Settings

\_3D.getGraphic [SimTalk]

\_Stairs Attributes

createRack [SimTalk]

##### TreadWidth [SimTalk]

Sets the width of the treads of the staircase designated by &lt;Path&gt;.

Remarks

Note

TreadWidth is available for graphics of type Stairs , compare InternalGraphicType .

Note

Assigning the attribute deactivates graphic inheritance.

Note

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadWidth:length

Assignment Value

You can assign an array of data type length .

Example

.Models.MyModel.\_3D.getGraphic("deco", [3]).TreadWidth := 4

See also

InternalGraphicType [SimTalk]

Stairs &gt; Stairs Settings

createRack [SimTalk]

\_Stairs Attributes

**\_3D.getGraphic [SimTalk]**

#### Stringer Material Attributes

\_Stringer Material Attributes

You can set the Stringer Material of the Stairs with the attributes listed in the table of contents to the left.

Remarks

Note

The attributes are available for graphics of type Stairs , compare InternalGraphicType .

Note

The stringer material does not affect the handrails of the staircase .

SimTalk

InternalGraphicType [SimTalk]

createStairs [SimTalk]

\_3D.getGraphic [SimTalk]

See also

Stairs &gt; Stairs Settings

\_Stairs Attributes

##### StringerMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).StringerMaterialActive := true
```

**See also**

| Stairs > Stairs Settings   | StringerMaterialEmissiveColor [SimTalk]   |
|----------------------------|-------------------------------------------|
| createRack [SimTalk]       | StringerMaterialShininess [SimTalk]       |
| _Stairs Attributes         | StringerMaterialSpecularColor [SimTalk]   |

| StringerMaterialAmbientColor [SimTalk]   | StringerMaterialTransparency [SimTalk]   |
|------------------------------------------|------------------------------------------|
| StringerMaterialDiffuseColor [SimTalk]   | _3D.getGraphic [SimTalk]                 |

##### StringerMaterialAmbientColor [SimTalk]

Sets the ambient color of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings               | StringerMaterialEmissiveColor [SimTalk]   |
|----------------------------------------|-------------------------------------------|
| createRack [SimTalk]                   | StringerMaterialShininess [SimTalk]       |
| _Stairs Attributes                     | StringerMaterialSpecularColor [SimTalk]   |
| StringerMaterialAmbientColor [SimTalk] | StringerMaterialTransparency [SimTalk]    |
| StringerMaterialDiffuseColor [SimTalk] | 3D.getGraphic                             |

##### StringerMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings               | StringerMaterialEmissiveColor [SimTalk]   |
|----------------------------------------|-------------------------------------------|
| createRack [SimTalk]                   | StringerMaterialShininess [SimTalk]       |
| _Stairs Attributes                     | StringerMaterialSpecularColor [SimTalk]   |
| StringerMaterialAmbientColor [SimTalk] | StringerMaterialTransparency [SimTalk]    |
| StringerMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]                  |

##### StringerMaterialEmissiveColor [SimTalk]

Sets the emissive color of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialEmissiveColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings               | StringerMaterialDiffuseColor            |
|----------------------------------------|-----------------------------------------|
| createRack [SimTalk]                   | StringerMaterialShininess [SimTalk]     |
| _Stairs Attributes                     | StringerMaterialSpecularColor [SimTalk] |
| StringerMaterialActive [SimTalk]       | StringerMaterialTransparency [SimTalk]  |
| StringerMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]                |

##### StringerMaterialShininess [SimTalk]

Sets the shininess of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

Note

You can only access the attribute if the material is active.

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialShininess := 0.5
```

See also

| Stairs > Stairs Settings   | StringerMaterialDiffuseColor [SimTalk]   |
|----------------------------|------------------------------------------|
| createRack [SimTalk]       | StringerMaterialEmissiveColor [SimTalk]  |

| _Stairs Attributes                     | StringerMaterialSpecularColor [SimTalk]   |
|----------------------------------------|-------------------------------------------|
| StringerMaterialActive [SimTalk]       | StringerMaterialTransparency [SimTalk]    |
| StringerMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]                  |

##### StringerMaterialSpecularColor [SimTalk]

Sets the specular color of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

**Note**

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings               | StringerMaterialDiffuseColor [SimTalk]   |
|----------------------------------------|------------------------------------------|
| createRack [SimTalk]                   | StringerMaterialEmissiveColor [SimTalk]  |
| _Stairs Attributes                     | StringerMaterialShininess [SimTalk]      |
| StringerMaterialActive [SimTalk]       | StringerMaterialTransparency [SimTalk]   |
| StringerMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]                 |

##### StringerMaterialTransparency [SimTalk]

Sets the transparency of the material of the stringers of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Note

The stringer material does not affect the handrails of the staircase .

Type

Attribute

Syntax

&lt; Path &gt;.StringerMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).StringerMaterialTransparency := 0.5
```

**Tread Material Attributes**

**See also**

| Stairs > Stairs Settings               | StringerMaterialDiffuseColor [SimTalk]   |
|----------------------------------------|------------------------------------------|
| createRack [SimTalk]                   | StringerMaterialEmissiveColor [SimTalk]  |
| _Stairs Attributes                     | StringerMaterialShininess [SimTalk]      |
| StringerMaterialActive [SimTalk]       | StringerMaterialSpecularColor [SimTalk]  |
| StringerMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]                 |

**Tread Material Attributes**

#### \_Tread Material Attributes

You can set the Tread Material of the Stairs with the attributes listed in the table of contents to the left.

**Note**

The attributes are available for graphics of type Stairs , compare InternalGraphicType [SimTalk] .

See also

Stairs &gt; Stairs Settings

createRack [SimTalk]

\_Stairs Attributes

\_3D.getGraphic [SimTalk]

##### TreadMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the treads of the staircase designated by &lt;Path&gt;.

Remarks

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [4]).TreadMaterialActive := true
```

**See also**

| Stairs > Stairs Settings            | TreadMaterialEmissiveColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| createRack [SimTalk]                | TreadMaterialShininess [SimTalk]       |
| _Stairs Attributes                  | TreadMaterialSpecularColor [SimTalk]   |
| TreadMaterialAmbientColor [SimTalk] | TreadMaterialTransparency [SimTalk]    |
| TreadMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### TreadMaterialAmbientColor [SimTalk]

Sets the ambient color of the material of the treads of the staircase designated by &lt;Path&gt;.

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

&lt; Path &gt;.TreadMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).TreadMaterialAmbientColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings   | TreadMaterialEmissiveColor [SimTalk]   |
|----------------------------|----------------------------------------|
| createRack [SimTalk]       | TreadMaterialShininess [SimTalk]       |

| _Stairs Attributes                  | TreadMaterialSpecularColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| TreadMaterialActive [SimTalk]       | TreadMaterialTransparency [SimTalk]    |
| TreadMaterialDiffuseColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### TreadMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the material of the treads of the staircase designated by &lt;Path&gt;.

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

&lt; Path &gt;.TreadMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).TreadMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

| Stairs > Stairs Settings            | TreadMaterialEmissiveColor [SimTalk]   |
|-------------------------------------|----------------------------------------|
| createRack [SimTalk]                | TreadMaterialShininess [SimTalk]       |
| _Stairs Attributes                  | TreadMaterialSpecularColor [SimTalk]   |
| TreadMaterialActive [SimTalk]       | TreadMaterialTransparency [SimTalk]    |
| TreadMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]               |

##### TreadMaterialEmissiveColor [SimTalk]

Sets the emissive color of the material of the treads of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).TreadMaterialEmissiveColor := makeRGBValue(255,0,0)

**See also**

| Stairs > Stairs Settings            | TreadMaterialDiffuseColor [SimTalk]   |
|-------------------------------------|---------------------------------------|
| createRack [SimTalk]                | TreadMaterialShininess [SimTalk]      |
| _Stairs Attributes                  | TreadMaterialSpecularColor [SimTalk]  |
| TreadMaterialActive [SimTalk]       | TreadMaterialTransparency [SimTalk]   |
| TreadMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]              |

##### TreadMaterialShininess [SimTalk]

Sets the shininess of the material of the treads of the staircase designated by &lt;Path&gt;.

**Remarks**

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).TreadMaterialShininess := 0.5
```

**See also**

| Stairs > Stairs Settings   | TreadMaterialDiffuseColor [SimTalk]   |
|----------------------------|---------------------------------------|
| createRack [SimTalk]       | TreadMaterialEmissiveColor [SimTalk]  |
| _Stairs Attributes         | TreadMaterialSpecularColor [SimTalk]  |

| TreadMaterialActive [SimTalk]       | TreadMaterialTransparency [SimTalk]   |
|-------------------------------------|---------------------------------------|
| TreadMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]              |

##### TreadMaterialSpecularColor [SimTalk]

Sets the specular color of the material of the treads of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).TreadMaterialSpecularColor := makeRGBValue(255,0,0)

**See also**

| Stairs > Stairs Settings            | TreadMaterialDiffuseColor [SimTalk]   |
|-------------------------------------|---------------------------------------|
| createRack [SimTalk]                | TreadMaterialEmissiveColor [SimTalk]  |
| _Stairs Attributes                  | TreadMaterialShininess [SimTalk]      |
| TreadMaterialActive [SimTalk]       | TreadMaterialTransparency [SimTalk]   |
| TreadMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]              |

##### TreadMaterialTransparency [SimTalk]

Sets the transparency of the material of the treads of the staircase designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.TreadMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).TreadMaterialTransparency := 0.5
```

See also

| Stairs > Stairs Settings   | TreadMaterialDiffuseColor [SimTalk]   |
|----------------------------|---------------------------------------|
| createRack [SimTalk]       | TreadMaterialEmissiveColor [SimTalk]  |

| _Stairs Attributes                  | TreadMaterialShininess [SimTalk]     |
|-------------------------------------|--------------------------------------|
| TreadMaterialActive [SimTalk]       | TreadMaterialSpecularColor [SimTalk] |
| TreadMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]             |

**Wall Material Attributes**

#### \_Wall Material Attributes

You can set the Wall Material of the Factory Walls with the attributes listed in the table of contents to the left.

See also

Insert Shape &gt; Factory Walls &gt; Factory Walls Settings

createFactoryWalls [SimTalk]

WallMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

Note

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).WallMaterialActive := true
```

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

WallMaterialAmbientColor [SimTalk]

WallMaterialDiffuseColor [SimTalk]

WallMaterialEmissiveColor [SimTalk]

WallMaterialShininess [SimTalk] WallMaterialSpecularColor [SimTalk] WallMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

WallMaterialAmbientColor [SimTalk]

Sets the ambient color of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).WallMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] WallMaterialActive [SimTalk] WallMaterialDiffuseColor [SimTalk] WallMaterialEmissiveColor [SimTalk] WallMaterialShininess [SimTalk] WallMaterialSpecularColor [SimTalk] WallMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

WallMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialDiffuseColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).WallMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] WallMaterialActive [SimTalk] WallMaterialAmbientColor [SimTalk] WallMaterialEmissiveColor [SimTalk] WallMaterialShininess [SimTalk] WallMaterialSpecularColor [SimTalk] WallMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### WallMaterialEmissiveColor [SimTalk]

Sets the emissive color of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).WallMaterialEmissiveColor := makeRGBValue(255,0,0)
```

See also

Insert Shape &gt; Factory Walls Factory Walls Settings createFactoryWalls [SimTalk] WallMaterialActive [SimTalk] WallMaterialAmbientColor [SimTalk] WallMaterialDiffuseColor [SimTalk] WallMaterialShininess [SimTalk] WallMaterialSpecularColor [SimTalk] WallMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

WallMaterialShininess [SimTalk]

Sets the shininess of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

Note

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialShininess:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).WallMaterialShininess := 0.9

See also

Insert Shape &gt; Factory Walls

Factory Walls Settings

createFactoryWalls [SimTalk]

WallMaterialActive [SimTalk]

WallMaterialAmbientColor [SimTalk] WallMaterialDiffuseColor [SimTalk] WallMaterialEmissiveColor [SimTalk] WallMaterialSpecularColor [SimTalk] WallMaterialTransparency [SimTalk] \_3D.getGraphic [SimTalk]

##### WallMaterialSpecularColor [SimTalk]

Sets the specular color of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialSpecularColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

.Models.MyModel.\_3D.getGraphic("deco", [5]).WallMaterialSpecularColor := makeRGBValue(255,0,0)

**See also**

| Insert Shape > Factory Walls > Factory Walls Settings   | WallMaterialEmissiveColor [SimTalk]   |
|---------------------------------------------------------|---------------------------------------|
| createFactoryWalls [SimTalk]                            | WallMaterialShininess [SimTalk]       |
| WallMaterialActive [SimTalk]                            | WallMaterialTransparency [SimTalk]    |
| WallMaterialAmbientColor [SimTalk]                      | _3D.getGraphic [SimTalk]              |
| WallMaterialDiffuseColor [SimTalk]                      |                                       |

##### WallMaterialTransparency [SimTalk]

Sets the transparency of the wall material of the factory walls designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

**Note**

Assigning the attribute deactivates graphic inheritance.

**Note**

You cannot assign the attribute when the graphic is an automatically generated graphic group or when the graphic is located in an automatically generated graphic group.

Type

Attribute

Syntax

&lt; Path &gt;.WallMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
.Models.MyModel._3D.getGraphic("deco", [5]).WallMaterialTransparency := 0.9
```

**See also**

| Insert Shape > Factory Walls > Factory Walls Settings   | WallMaterialEmissiveColor [SimTalk]   |
|---------------------------------------------------------|---------------------------------------|
| createFactoryWalls [SimTalk]                            | WallMaterialShininess [SimTalk]       |

<!-- image -->

| WallMaterialActive [SimTalk]       | WallMaterialSpecularColor [SimTalk]   |
|------------------------------------|---------------------------------------|
| WallMaterialAmbientColor [SimTalk] | _3D.getGraphic [SimTalk]              |
| WallMaterialDiffuseColor [SimTalk] |                                       |

