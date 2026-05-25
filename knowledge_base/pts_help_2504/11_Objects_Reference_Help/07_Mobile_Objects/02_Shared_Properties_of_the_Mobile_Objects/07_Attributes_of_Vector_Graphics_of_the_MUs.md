#### Attributes of Vector Graphics of the MUs

\_Attributes of Vector Graphics of the MUs

The MUs provide the attributes listed in the table of contents to the left for vector graphics.

You can also select these settings in the dialog of the objects on the Graphics [tab, MUs, 2D] .

Note

Vector graphics are only available in a 2D Only model .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
.MUs.Transporter.Length := 4.5
print .MUs.Transporter.Length
posit := Station.Cont.XPos
```

##### VectorgraphicsActive [SimTalk]

Activates ( true ) or deactivates ( false ) vector graphics mode for the MU designated by &lt;MU-Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

Once activated, Plant Simulation shows the graphics of the parts with the correct size and with the correct distance to each other.

The table below illustrates the difference between the vector graphic and the icon of the object.

<!-- image -->

| Object              | Vector Graphic Operational   | Vector Graphic Waiting   | Icon Operational   | Icon Waiting   |
|---------------------|------------------------------|--------------------------|--------------------|----------------|
| Part                |                              |                          |                    |                |
| Container           |                              |                          |                    |                |
| Transporter         |                              |                          |                    |                |
| Transporter Tractor |                              |                          |                    |                |

Type

Attribute

Syntax

&lt;MUPath &gt;.VectorgraphicsActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.MUs.MyPart.VectorgraphicsActive:=true
```

**See also**

**Vector Graphics Active**

##### VectorgraphicsAnilineDirection [SimTalk]

Sets the direction of the animation line on the vector graphic of the object Transporter designated by &lt;MU-Path&gt;.

**Remarks**

**Note**

A 3D Only model does not provide this attribute.

<!-- image -->

**Note**

This setting is only available for the Loading Space Types &gt; Track and Line .

<!-- image -->

Type

Attribute

Syntax

<!-- image -->

Assignment Value

You can assign a value of data type string .

You can specify "Lengthwise" or "Crosswise" for the direction of motion.

**Example**

MUs.MyTransporter.VectorgraphicsAnilineDirection := "Crosswise"

See also

Direction of the Animation Line

Type [loading space]

VectorgraphicsBorderColor [SimTalk]

Sets the Border Color of the vector graphic of the MU designated by &lt;MU-Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

Plant Simulation surrounds the Fill Color with the Border Color in the Border Width that you select. The Border Color also sets the color of the Direction Arrow .

Attribute

Type

Attribute

Syntax

&lt;MUPath &gt;.VectorgraphicsBorderColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.MUs.MyPart.VectorgraphicsBorderColor := 15780518 // light blue .MUs.MyPart.VectorgraphicsBorderColor := makeRGBValue(100,200,200)
```

See also

Border Color [vector graphic]

Border Width

Show Direction Arrow

VectorgraphicsBorderWidth [SimTalk]

Sets the Border Width of the vector graphic of the MU designated by &lt;MU-Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

Plant Simulation surrounds the Fill Color with the Border Width in the Border Color that you select.

Type

Attribute

Syntax

&lt;MU- Path &gt;.VectorgraphicsBorderWidth:integer

Assignment Value

You can assign a value of data type integer .

A border width of 2 looks like this , a border width of 4 looks like this .

Example

.MUs.MyPart.VectorgraphicsBorderWidth := 2

See also

Border Width

Border Color [vector graphic]

##### VectorgraphicsColor [SimTalk]

Sets the Fill Color of the vector graphic of the MU designated by &lt;MU-Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

The fill color fills the interior of the built-in vector graphic with the color that you select.

Type

Attribute

Syntax

&lt;MUPath &gt;.VectorgraphicsColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.MUs.MyPart.VectorgraphicsColor := 128 // dark red .MUs.MyPart.VectorgraphicsColor := makeRGBValue(200,200,100)
```

See also

Color [MU]

VectorgraphicsShowDirectionArrow [SimTalk]

Shows ( true ) or hides ( false ) the Direction Arrow on the vector graphic of the MU designated by &lt;MU-Path&gt; to illustrate the conveying direction.

Remarks

Note

A 3D Only model does not provide this attribute.

Border Color and Border Width also set the color and the width of the direction arrow.

<!-- image -->

<!-- image -->

The graphic looks like this with the direction arrow. It looks like this without the direction arrow.

Type

Attribute

Syntax

&lt;MUPath &gt;.VectorgraphicsShowDirectionArrow:boolean

Assignment Value

You can assign a value of data type boolean .

Example

.MUs.MyPart.VectorgraphicsShowDirectionArrow := true

See also

Show Direction Arrow

Border Color [vector graphic]

Border Width

##### VectorgraphicsShowState [SimTalk]

Part

Part

Shows ( true ) or hides ( false ) the State of the MU designated by &lt;MU-Path&gt; as a colored border around the vector graphic.

Remarks

Note

A 3D Only model does not provide this attribute.

The states are yellow for blocked , red for failed , and blue for paused . The State Color overwrites the Border Color that you select.

Type

Attribute

Syntax

&lt;MU- Path &gt;.VectorgraphicsShowState:boolean

Assignment Value

You can assign a value of data type boolean .

Example

.MUs.MyPart.VectorgraphicsShowState := true

See also

Show State

Border Color [vector graphic]

Use the Part for modeling all kinds of parts and workpieces being produced and transported.

<!-- image -->

<!-- image -->

<!-- image -->

**Icon**

<!-- image -->

Description

The Part is a moving material flow object without loading capacity that moves through a plant on the material flow objects as such. The Part represents all kinds of workpieces being produced and transported, but not transporting other workpieces.

In 3D you can set a material on the tab Appearance .

<!-- image -->

To show a tooltip with information about the Part , hover with the mouse over it.

<!-- image -->

<!-- image -->

Add the Object to the Simulation Model

To add the Part to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MUs &gt; Part on the Home ribbon tab.

See also

Shared Properties of the Mobile Objects

