### Accessing the Appearance of the Store

#### \_\_Accessing the Appearance of the Store

SimTalk provides the attributes listed in the table of contents to the left for setting the appearance of the Store in 3D.

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store

#### \_3D.Dimensions [SimTalk] - Store

Sets the dimensions of the storage area of the Store designated by &lt;Path&gt;.

Remarks

For the dynamic types these dimensions designate the slot dimensions.

For the non-dynamic types these dimensions designate the overall dimensions of the Store .

Type

Attribute

Syntax

< Path >._3D.Dimensions:length[3]

**Assignment Value**

You can assign an array of data type length with three values.

They designate the X-dimension /width, the Y-dimension /depth, and the Z-dimension /height of the storage area.

**Example**

```simtalk
MyStore._3D.Dimensions := [2, 2, 0.01]
```

**See also**

Edit 3D Properties [dialog] &gt; Store &gt; X [text box] - Store, 3D , Y [text box] - Store, 3D , Z [text box] Store, 3D

\_3D.Dimensions [SimTalk] - simulation object

X [SimTalk] - array

Y [SimTalk] - array

Z [SimTalk] - array

#### \_3D.FloorThickness [SimTalk]

Sets the Thickness of the base plate below the floor space of the Store designated by &lt;Path&gt; for the Store Type &gt; Floorspace (dynamic) .

Remarks

Also sets the Thickness of the individual shelves of the Store designated by &lt;Path&gt; for the Store Type &gt; Rack with round/square posts (dynamic) .

Type

Attribute

Syntax

< Path >._3D.FloorThickness:any

Assignment Value

You can assign a value of data type any .

Specify void to use the default thickness.

Example

```simtalk
MyStore._3D.FloorThickness := 0.24
```

See also

\_3D.StoreType [SimTalk]

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Floor Thickness

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Board Thickness

#### \_3D.Gap [SimTalk]

Sets the Gap , i.e., the distance between the individual rack bays for the dynamic store types of the Store designated by &lt;Path&gt;.

Remarks

**Note**

The attribute only applies to the dynamic store types .

For a dynamic rack, Plant Simulation implicitly uses a gap of 3 cm.

For a dynamic floor space, Plant Simulation uses an effective gap of 0 cm which also includes the borderline.

Type

Attribute

Syntax

< Path >._3D.Gap:any

Assignment Value

You can assign a value of data type any .

You can only assign a value greater than or equal to 0.

If you do not want to use a gap, specify void .

**Examples**

```simtalk
.Models.MyStore._3D.Gap := void -- no gap
Store3._3D.StoreType := "Rack with round posts (dynamic)"
Store3._3D.Gap := 0.1
Store3._3D.FloorThickness := 0.15
Store3._3D.GroundClearance := 0.3
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Gap [rack]

\_3D.Gap [SimTalk]

**Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Type [drop-down list] - Store**

#### \_3D.GroundClearance [SimTalk]

Sets the distance between the lower edge of the lowest shelf and the floor on which the rack of the Store designated by &lt;Path&gt; stands for the Store Type &gt; Rack with round/square posts (dynamic) .

Type

Attribute

Syntax

< Path >._3D.GroundClearance:any

Assignment Value

You can assign a value of data type any .

Specify void to use the default ground clearance.

Specify 0 to make the lowest shelf rest flat on the floor.

Example

```simtalk
Store3._3D.StoreType := "Rack with round posts (dynamic)"
Store3._3D.Gap := 0.1
Store3._3D.FloorThickness := 0.15
Store3._3D.GroundClearance := 0.3
```

See also

\_3D.StoreType [SimTalk]

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Board Thickness

#### \_3D.OriginX [SimTalk]

Sets the origin of the automatically created graphic and of the MU animation of the Store designated by &lt;Path&gt; in the X-Direction .

**Remarks**

<!-- image -->

| Origin X               | Origin Y               | Capacity 3 times 3   | Capacity 4 times 3   |
|------------------------|------------------------|----------------------|----------------------|
| Center                 | Bottom                 |                      |                      |
| Center                 | Top                    |                      |                      |
| Center default setting | Center default setting |                      |                      |
| Left                   | Bottom                 |                      |                      |

<!-- image -->

| Origin X   | Origin Y   | Capacity 3 times 3   | Capacity 4 times 3   |
|------------|------------|----------------------|----------------------|
| Left       | Top        |                      |                      |
| Left       | Center     |                      |                      |
| Right      | Bottom     |                      |                      |
| Right      | Top        |                      |                      |
| Right      | Center     |                      |                      |

Type

Attribute

**\_3D.OriginX [SimTalk]**

**Syntax**

```simtalk
< Path >._3D.OriginX:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Left" , "Center" , or "Right" .

**Example**

```simtalk
Store3._3D.OriginX := "Left"
```

**See also**

\_3D.OriginY [SimTalk]

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Origin [graphic]

#### \_3D.OriginY [SimTalk]

Sets the origin of the automatically created graphic and of the MU animation of the Store designated by &lt;Path&gt; in the Y-Direction .

**Remarks**

<!-- image -->

| Origin X               | Origin Y               | Capacity 3 times 3   | Capacity 4 times 3   |
|------------------------|------------------------|----------------------|----------------------|
| Center                 | Bottom                 |                      |                      |
| Center                 | Top                    |                      |                      |
| Center default setting | Center default setting |                      |                      |
| Left                   | Bottom                 |                      |                      |

**\_3D.OriginY [SimTalk]**

<!-- image -->

| Origin X   | Origin Y   | Capacity 3 times 3   | Capacity 4 times 3   |
|------------|------------|----------------------|----------------------|
| Left       | Top        |                      |                      |
| Left       | Center     |                      |                      |
| Right      | Bottom     |                      |                      |
| Right      | Top        |                      |                      |
| Right      | Center     |                      |                      |

Type

Attribute

**Syntax**

```simtalk
< Path >._3D.OriginY:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Top" , "Center" , or "Bottom" .

**Example**

```simtalk
Store3._3D.OriginY := "Top"
```

**See also**

\_3D.OriginX [SimTalk]

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Origin [graphic]

#### \_3D.PostMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the posts of the automatic graphics of the Store designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.PostMaterialActive:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStore._3D.PostMaterialActive := true
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

#### \_3D.PostMaterialAmbientColor [SimTalk]

Sets the ambient color of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.PostMaterialAmbientColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStore._3D.PostMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.PostMaterialDiffuseColor [SimTalk]
- \_3D.PostMaterialEmissiveColor [SimTalk]
- \_3D.PostMaterialShininess [SimTalk]
- \_3D.PostMaterialSpecularColor [SimTalk]
- \_3D.PostMaterialTransparency [SimTalk]

#### \_3D.PostMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

Type

Attribute

Syntax

```simtalk
< Path >._3D.PostMaterialDiffuseColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStore._3D.PostMaterialDiffuseColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.PostMaterialAmbientColor [SimTalk]
- \_3D.PostMaterialEmissiveColor [SimTalk]
- \_3D.PostMaterialShininess [SimTalk]
- \_3D.PostMaterialSpecularColor [SimTalk]
- \_3D.PostMaterialTransparency [SimTalk]

#### \_3D.PostMaterialEmissiveColor [SimTalk]

Sets the emissive color of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.PostMaterialEmissiveColor:integer

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStore._3D.PostMaterialEmissiveColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.PostMaterialAmbientColor [SimTalk]
- \_3D.PostMaterialDiffuseColor [SimTalk]
- \_3D.PostMaterialShininess [SimTalk]
- \_3D.PostMaterialSpecularColor [SimTalk]
- \_3D.PostMaterialTransparency [SimTalk]

#### \_3D.PostMaterialShininess [SimTalk]

Sets the shininess of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

You can only access the attribute if the material is active.

Type

Attribute

Syntax

```simtalk
< Path >._3D.PostMaterialShininess:real
```

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

```simtalk
MyStore._3D.PostMaterialShininess := 0.9
```

**See also**

| Edit 3D Properties [dialog] > Appearance of the Store > Material [tab]   | _3D.PostMaterialEmissiveColor [SimTalk]   |
|--------------------------------------------------------------------------|-------------------------------------------|
| _3D.PostMaterialAmbientColor [SimTalk]                                   | _3D.PostMaterialSpecularColor [SimTalk]   |
| _3D.PostMaterialDiffuseColor [SimTalk]                                   | _3D.PostMaterialTransparency [SimTalk]    |

#### \_3D.PostMaterialSpecularColor [SimTalk]

Sets the specular color of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

Type

Attribute

Syntax

```simtalk
< Path >._3D.PostMaterialSpecularColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStore._3D.PostMaterialSpecularColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.PostMaterialAmbientColor [SimTalk]
- \_3D.PostMaterialDiffuseColor [SimTalk]
- \_3D.PostMaterialEmissiveColor [SimTalk]
- \_3D.PostMaterialShininess [SimTalk]
- \_3D.PostMaterialTransparency [SimTalk]

#### \_3D.PostMaterialTransparency [SimTalk]

Sets the transparency of the automatic graphics of the posts of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

**Note**

You can only access the attribute if the material is active.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.PostMaterialTransparency:real

Assignment Value

You can assign a value of data type real between 0 and 1 .

Example

MyStore.\_3D.PostMaterialTransparency := 0.9

**See also**

| Edit 3D Properties [dialog] > Appearance of the Store > Material [tab]   | _3D.PostMaterialEmissiveColor [SimTalk]   |
|--------------------------------------------------------------------------|-------------------------------------------|
| _3D.PostMaterialAmbientColor [SimTalk]                                   | _3D.PostMaterialShininess [SimTalk]       |
| _3D.PostMaterialDiffuseColor [SimTalk]                                   | _3D.PostMaterialSpecularColor [SimTalk]   |

#### \_3D.StorageAreaMaterialActive [SimTalk]

Activates ( true ) or deactivates ( false ) the material of the storage area of the automatic graphics of the Store designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialActive:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyStore._3D.StorageAreaMaterialActive := true
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

#### \_3D.StorageAreaMaterialAmbientColor [SimTalk]

Sets the ambient color of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialAmbientColor:integer
```

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialAmbientColor := makeRGBValue(255,0,0)
```

See also

Edit 3D Properties [dialog]

- \_3D.StorageAreaMaterialDiffuseColor [SimTalk]
- \_3D.StorageAreaMaterialEmissiveColor [SimTalk]
- \_3D.StorageAreaMaterialShininess [SimTalk]
- \_3D.StorageAreaMaterialSpecularColor [SimTalk]
- \_3D.StorageAreaMaterialTransparency [SimTalk]

#### \_3D.StorageAreaMaterialDiffuseColor [SimTalk]

Sets the diffuse color of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialDiffuseColor:integer
```

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.StorageAreaMaterialAmbientColor [SimTalk]
- \_3D.StorageAreaMaterialEmissiveColor [SimTalk]
- \_3D.StorageAreaMaterialShininess [SimTalk]
- \_3D.StorageAreaMaterialSpecularColor [SimTalk]
- \_3D.StorageAreaMaterialTransparency [SimTalk]

#### \_3D.StorageAreaMaterialEmissiveColor [SimTalk]

Sets the emissive color of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialEmissiveColor:integer
```

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialEmissiveColor := makeRGBValue(255,0,0)
```

**See also**

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.StorageAreaMaterialAmbientColor [SimTalk]
- \_3D.StorageAreaMaterialDiffuseColor [SimTalk]
- \_3D.StorageAreaMaterialShininess [SimTalk]
- \_3D.StorageAreaMaterialSpecularColor [SimTalk]
- \_3D.StorageAreaMaterialTransparency [SimTalk]

#### \_3D.StorageAreaMaterialShininess [SimTalk]

Sets the shininess of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialShininess:integer
```

**Assignment Value**

You can assign a value of data type integer .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialShininess := 0.9
```

**See also**

| Edit 3D Properties [dialog] > Appearance of the Store > Material [tab]   | _3D.StorageAreaMaterialEmissiveColor [SimTalk]   |
|--------------------------------------------------------------------------|--------------------------------------------------|
| _3D.StorageAreaMaterialAmbientColor [SimTalk]                            | _3D.StorageAreaMaterialSpecularColor [SimTalk]   |
| _3D.StorageAreaMaterialDiffuseColor [SimTalk]                            | _3D.StorageAreaMaterialTransparency [SimTalk]    |

#### \_3D.StorageAreaMaterialSpecularColor [SimTalk]

Sets the specular color of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialSpecularColor:integer
```

**Assignment Value**

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialSpecularColor := makeRGBValue(255,0,0)
```

**See also**

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Material [tab]

- \_3D.StorageAreaMaterialAmbientColor [SimTalk]
- \_3D.StorageAreaMaterialDiffuseColor [SimTalk]
- \_3D.StorageAreaMaterialEmissiveColor [SimTalk]
- \_3D.StorageAreaMaterialShininess [SimTalk]
- \_3D.StorageAreaMaterialTransparency [SimTalk]

#### \_3D.StorageAreaMaterialTransparency [SimTalk]

Sets the transparency of the automatic graphics of the storage area of the Store designated by &lt;Path&gt;.

Remarks

When assigning a value to the attribute, we automatically set the material to active

( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.StorageAreaMaterialTransparency:real
```

**Assignment Value**

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
MyStore._3D.StorageAreaMaterialTransparency := 0.9
```

**See also**

| Edit 3D Properties [dialog] > Appearance of the Store > Material [tab]   | _3D.StorageAreaMaterialEmissiveColor [SimTalk]   |
|--------------------------------------------------------------------------|--------------------------------------------------|
| _3D.StorageAreaMaterialAmbientColor [SimTalk]                            | _3D.StorageAreaMaterialShininess [SimTalk]       |
| _3D.StorageAreaMaterialDiffuseColor [SimTalk]                            | _3D.StorageAreaMaterialSpecularColor [SimTalk]   |

_3D.StoreType [SimTalk]

#### \_3D.StoreType [SimTalk]

Sets the type of the Store designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >._3D.StoreType:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Floorspace" , "Rack with round posts" , "Rack with square posts" , "Floorspace (dynamic)" , "Rack with round posts (dynamic)" , or "Rack with square posts (dynamic)" .

**Example**

```simtalk
Store3._3D.StoreType := "Rack with round posts (dynamic)"
Store3._3D.Gap := 0.1
Store3._3D.FloorThickness := 0.15
Store3._3D.GroundClearance := 0.3
```

See also

Edit 3D Properties [dialog] &gt; Appearance of the Store &gt; Type [drop-down list] - Store

createRack [SimTalk]

