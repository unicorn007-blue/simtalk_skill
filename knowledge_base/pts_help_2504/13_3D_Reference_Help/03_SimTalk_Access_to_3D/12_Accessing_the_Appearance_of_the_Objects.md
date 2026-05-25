### Accessing the Appearance of the Objects

#### \_\_Accessing the Appearance of Objects and MUs

SimTalk provides the attributes and methods listed in the table of contents to the left for the object material of objects and MUs in 3D .

Objects do not provide an object material:

- If they have object-specific appearance settings, such as the length-oriented objects and the Store .
- If they are used for connecting other objects, such as the Connector , the Interface , and the Marker .
- If they are used for displaying text or values, or for selecting a setting, such as Comment, Variable, Display, Button, DropDownList, Checkbox, Chart, Tank and Mixer .

Plant Simulation applies the attributes to all graphics of the specified object for which no material of its own is defined, for example

- The T-Shirt of the Worker .
- The body of the Transporter .
- The entire graphic of the Container and the Part .
- The blue graphics of the point-oriented objects, such as the Station , the Buffer , etc.
- The light gray plate under the icon of logical objects, such as the information flow objects Method , DataTable , etc, and of the user interface objects SankeyDiagram , CostAnalyzer , etc.

See also

Edit 3D Properties [dialog] &gt; Appearance of Objects and MUs

Appearance of the Length-oriented Objects

Appearance of the Store

#### \_3D.MaterialActive [SimTalk]

Sets if the object designated by &lt;Path&gt; has an object-wide material ( true ) or not ( false ).

Remarks

Also sets if the MU designated by &lt;MU-Path&gt; has an object-wide material ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialActive:boolean <MUPath >._3D.MaterialActive:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyStation._3D.MaterialActive := true
MyPortioner._3D.MaterialActive := false
.MUs.Part._3D.MaterialActive := true
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Material Active [check box] - MUs   | _3D.MaterialEmissiveColor [SimTalk]   |
|---------------------------------------------------------------------------------------------------|---------------------------------------|
| makeRGBValue [SimTalk]                                                                            | _3D.MaterialShininess [SimTalk]       |
| _3D.MaterialAmbientColor [SimTalk]                                                                | _3D.MaterialSpecularColor [SimTalk]   |
| _3D.MaterialDiffuseColor [SimTalk]                                                                | _3D.MaterialTransparency [SimTalk]    |

#### \_3D.MaterialAmbientColor [SimTalk]

Sets the ambient color of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the ambient color of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialAmbientColor:integer <MUPath >._3D.MaterialAmbientColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStation._3D.MaterialAmbientColor := makeRGBValue(0,0,255)
MyPortioner._3D.MaterialAmbientColor := makeRGBValue(255,0,0) .MUs.Part._3D.MaterialAmbientColor := makeRGBValue(0,0,255)
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Ambient Color [MUs]   | _3D.MaterialEmissiveColor [SimTalk]   |
|-------------------------------------------------------------------------------------|---------------------------------------|
| makeRGBValue [SimTalk]                                                              | _3D.MaterialShininess [SimTalk]       |
| _3D.MaterialActive [SimTalk]                                                        | _3D.MaterialSpecularColor [SimTalk]   |
| _3D.MaterialDiffuseColor [SimTalk]                                                  | _3D.MaterialTransparency [SimTalk]    |

#### \_3D.MaterialDiffuseColor [SimTalk]

Sets the diffuse color of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the diffuse color of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialDiffuseColor:integer <MUPath >._3D.MaterialDiffuseColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

**Example**

```simtalk
MyStation._3D.MaterialDiffuseColor := makeRGBValue(0,0,255)
MyPortioner._3D.MaterialDiffuseColor := makeRGBValue(255,0,0) .MUs.Part._3D.MaterialDiffuseColor := makeRGBValue(255,0,0)
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Diffuse Color [MUs]   | _3D.MaterialEmissiveColor [SimTalk]   |
|-------------------------------------------------------------------------------------|---------------------------------------|
| makeRGBValue [SimTalk]                                                              | _3D.MaterialShininess [SimTalk]       |
| _3D.MaterialActive [SimTalk]                                                        | _3D.MaterialSpecularColor [SimTalk]   |
| _3D.MaterialAmbientColor [SimTalk]                                                  | _3D.MaterialTransparency [SimTalk]    |

#### \_3D.MaterialEmissiveColor [SimTalk]

Sets the emissive color of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the emissive color of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialEmissiveColor:integer <MUPath >._3D.MaterialEmissiveColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.MaterialEmissiveColor := makeRGBValue(0,0,255)
MyPortioner._3D.MaterialEmissiveColor := makeRGBValue(255,0,0) .MUs.Part._3D.MaterialEmissiveColor := makeRGBValue(0,255,0)
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Emissive Color [MUs]   | _3D.MaterialDiffuseColor [SimTalk]   |
|--------------------------------------------------------------------------------------|--------------------------------------|
| makeRGBValue [SimTalk]                                                               | _3D.MaterialShininess [SimTalk]      |
| _3D.MaterialActive [SimTalk]                                                         | _3D.MaterialSpecularColor [SimTalk]  |
| _3D.MaterialAmbientColor [SimTalk]                                                   | _3D.MaterialTransparency [SimTalk]   |

#### \_3D.MaterialShininess [SimTalk]

Sets the shininess of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the shininess of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialShininess:real <MUPath >._3D.MaterialShininess:real
```

Assignment Value

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
MyStation._3D.MaterialShininess := 0.7
MyPortioner._3D.MaterialShininess := 0.8 .MUs.Part._3D.MaterialShininess := 0.9
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Shininess [MUs]   | _3D.MaterialDiffuseColor [SimTalk]   |
|---------------------------------------------------------------------------------|--------------------------------------|
| makeRGBValue [SimTalk]                                                          | _3D.MaterialEmissiveColor [SimTalk]  |
| _3D.MaterialActive [SimTalk]                                                    | _3D.MaterialSpecularColor [SimTalk]  |
| _3D.MaterialAmbientColor [SimTalk]                                              | _3D.MaterialTransparency [SimTalk]   |

#### \_3D.MaterialSpecularColor [SimTalk]

Sets the specular color of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the specular color of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialSpecularColor:integer <MUPath >._3D.MaterialSpecularColor:integer
```

Assignment Value

You can assign a value of data type integer .

You will usually set the color with the method makeRGBValue [SimTalk] .

Example

```simtalk
MyStation._3D.MaterialSpecularColor := makeRGBValue(0,255,0)
MyPortioner._3D.MaterialSpecularColor := makeRGBValue(0,0,255)
.MUs.Part._3D.MaterialSpecularColor := makeRGBValue(0,255,0)
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Specular Color [MUs]   | _3D.MaterialDiffuseColor [SimTalk]   |
|--------------------------------------------------------------------------------------|--------------------------------------|
| makeRGBValue [SimTalk]                                                               | _3D.MaterialEmissiveColor [SimTalk]  |
| _3D.MaterialActive [SimTalk]                                                         | _3D.MaterialShininess [SimTalk]      |
| _3D.MaterialAmbientColor [SimTalk]                                                   | _3D.MaterialTransparency [SimTalk]   |

#### \_3D.MaterialTransparency [SimTalk]

Sets the transparency of the graphic of the object designated by &lt;Path&gt;.

Remarks

Also sets the transparency of the graphic of the MU designated by &lt;MU-Path&gt;.

**Note**

When assigning a value to the attribute, we automatically set the material to active ( MaterialActive := true ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.MaterialTransparency:real <MUPath >._3D.MaterialTransparency:real
```

Assignment Value

You can assign a value of data type real between 0 and 1 .

**Example**

```simtalk
MyStation._3D.MaterialTransparency := 0.75
MyPortioner._3D.MaterialTransparency := 0.75 .MUs.Part._3D.MaterialTransparency := 0.85
```

**See also**

| Edit 3D Properties [dialog] > Appearance of Objects and MUs > Transparency [MUs]   | _3D.MaterialDiffuseColor [SimTalk]   |
|------------------------------------------------------------------------------------|--------------------------------------|
| makeRGBValue [SimTalk]                                                             | _3D.MaterialEmissiveColor [SimTalk]  |
| _3D.MaterialActive [SimTalk]                                                       | _3D.MaterialShininess [SimTalk]      |
| _3D.MaterialAmbientColor [SimTalk]                                                 | _3D.MaterialSpecularColor [SimTalk]  |

#### \_3D.ShowSafetyZones [SimTalk]

Shows the defined safety zones of the Transporter designated by &lt;Path&gt; ( true ) or hides them ( false ).

Type

Attribute

Syntax

```simtalk
< Path >._3D.ShowSafetyZones:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
Station._3D.ShowSafetyZones := true
```

See also

Edit 3D Properties [dialog] &gt; Appearance of Objects and MUs &gt; Show Safety Zones

Length Zone 1

ΔWidth Zone 1

Length Zone 2

ΔWidth Zone 2

