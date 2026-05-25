### Connector

Use the Connector for establishing material flow connections between objects along which the parts move.

Icon

<!-- image -->

**Description**

The Connector also connects an object with an exit or entrance-modeled with the Interface -of a Frame when you modeled hierarchically, i.e., when you nest Frames within Frames . The Connector shows the direction of the connection with an arrowhead in the middle of the connecting line.

To show the predecessors and the successors of an object in a Tooltip , you drag the mouse over the respective Connector .

<!-- image -->

To show the source and the target of the Connector in the Frame as a tooltip , drag the mouse over the Connector .

<!-- image -->

**Note**

You can only establish a single connection between two objects!

To reorder the sequence of the successors of the selected object, right-click the object in the Frame and select Reorder Successors on the context menu.

<!-- image -->

**Show Manipulators**

In 3D you can also reorder the connections by clicking Show Manipulators on the Edit ribbon tab.

With the manipulators of the start and end anchor points you can change the predecessor or the successor respectively of the Connector and attach it to another object. Drag the start or end anchor point from the current object to another object of your choice.

<!-- image -->

If you did not select anything in the scene, the command also shows the position manipulators of the Connectors in the scene if Connectors are shown in the scene.

You can edit the anchor points with the position manipulator, including the start and the end anchor point.

Plant Simulation shows the start and end anchor point of the Connectors cut in half. This clearly separates Connectors without a length of their own and allows to easily select each of the Connectors .

<!-- image -->

<!-- image -->

Add the Object to the Simulation Model

To add the Connector to your simulation model, click MaterialFlow &gt; Connector on the Home ribbon tab.

See also

Dialog Box of the Connector

Connect Objects with the Connector

#### Dialog Box of the Connector

Dialog Box of the Connector

Double-click the Connector , which you inserted into a Frame , to open its dialog box.

Tab Attributes

Tab Attributes

The tab Attributes provides these settings:

Width [text box] - Connector

Color [Connector]

<!-- image -->

Manage Class Library &gt; Basic Objects &gt;

###### Width [text box] - Connector

Type in the line Width of the Connector .

<!-- image -->

This can be a real number between -1 and 100 .

- The value 1 stands for a line weight of 1 pixel in a Frame window with a zoom factor of 100 %.
- The value 0 stands for a Connector width of 1 pixel no matter if the Frame window is zoomed or not.
- The value -1 makes the Connector invisible.

The Connectors in 3D use the line Width you define here as well.

<!-- image -->

The Width is a value of data type real . For 3D Only models you can reduce the default width, which corresponds to 0 or 1, with values between 0 and 1, to a fraction of that.

SimTalk

Width [SimTalk] - Connector

**Color [Connector]**

###### Color [Connector]

To set the color of the Connector , click the field next to Color .

<!-- image -->

You can select one of the predefined colors or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

Color [SimTalk] - Connector

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Connector**

#### \_Methods of the Connector

The Connector provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### connect [SimTalk]

Connects the specified objects within a Frame with the Connector designated by &lt;Connector-Path&gt;.

**Remarks**

The method connect also connects any end of a TwoLaneTrack with any end of another TwoLaneTrack . To do so, you have to pass two lanes to the method connect . The exit of the first lane, which you specify, will then be connected with the entrance of the second lane. The method still connects the TwoLaneTracks and not the individual lanes.

Type

Method

**Syntax**

```simtalk
<ConnectorPath >.connect(StartOfConnection:any, EndOfConnectionY:any) → object <ConnectorPath >.connect(StartOfConnection:any, EndOfConnectionY:any[, SideOfConverterStart:integer, SideOfConverterEnd:integer]) → object
```

**Parameters**

- The parameter StartOfConnection of data type any designates the starting point of the Connector designated by &lt;Connector-Path&gt;.
- The parameter EndOfConnection of data type any designates the end point of the connection.

You can also set an Interface object as first or as second parameter. The return value is the Connector that was just created. If Plant Simulation cannot create the Connector , it opens the Method Debugger .

- The optional parameter SideOfConverterStart of data type integer sets at which side of the Converter the Connector is to dock: 0 designates right , 1 designates bottom , 2 designates left , and 3 designates top .

<!-- image -->

<!-- image -->

| Left   | Bottom   | Top   | Right   |
|--------|----------|-------|---------|

- The optional parameter SideOfConverterEnd of data type integer is only required when you insert a Connector between two Converters .
- SideOfConverterStart then designates the side of the source Converter . The parameter SideOfConverterEnd of data type integer designates the side of the target Converter at which the Connector ends.

**Return Value**

The return value has the data type object .

The return value is the Connector that has been created.

**Examples**

.Materialflow.Connector.connect(Station, Store) .Materialflow.Connector.connect(Station, Interface3)

- .Materialflow.Connector.connect(T1, T2)
- // connects the exit of T1 with the entrance of T2
- .Materialflow.Connector.connect(T1.A, T2.A)
- // connects the exit of T1 with the entrance of T2
- .Materialflow.Connector.connect(T1.A, T2.B)
- // connects the exit of T1 with the exit of T2
- .Materialflow.Connector.connect(T1.B, T2.A)
- // connects the entrance of T1 with the entrance of T2
- .MaterialFlow.Connector.connect("TwoLaneTrack1.B", "TwoLaneTrack2.A")
- // connects lanes of two-laned tracks

##### getEndPoint [SimTalk]

Returns the coordinates of the end point of the Connector designated by &lt;Connector-Path&gt;.

Remarks

Plant Simulation then assigns the coordinates to the local variables, whose names you specify.

Type

Method

Syntax

&lt;ConnectorPath &gt;.getEndPoint(byRef XResult:integer, byRef YResult:integer)

**Parameters**

- The local variable XResult of data type integer , to which the value is assigned, designates the xcoordinate of the end point of the Connector .
- The local variable YResult of data type integer , to which the value is assigned, designates its ycoordinate.

**Example**

```simtalk
var x,y: integer
connector.getEndPoint(x,y)
```

**SimTalk**

getStartPoint [SimTalk]

**getStartPoint [SimTalk]**

##### getStartPoint [SimTalk]

Returns the coordinates of the starting point of the Connector designated by &lt;Connector-Path&gt;.

Remarks

Plant Simulation then assigns the coordinates to the local variables, whose names you specify.

Type

Method

Syntax

```simtalk
<ConnectorPath >.getStartPoint(byRef XResult:integer, byRef YResult:integer)
```

**Parameters**

- The local variable XResult of data type integer , to which the value is assigned, designates the xcoordinate of the starting point of the Connector .
- The local variable YResult of data type integer , to which the value is assigned, designates its ycoordinate.

**Example**

```simtalk
var x,y: integer
connector.getStartPoint(x,y)
```

SimTalk

getEndPoint [SimTalk]

#### Read-Only Attributes of the Connector

\_Read-Only Attributes of the Connector

The Connector provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Connector.SuccInterface

**PredInterface [SimTalk]**

##### PredInterface [SimTalk]

Returns the direct predecessor object of the Connector designated by &lt;Connector-Path&gt;.

Remarks

If the preceding object is a Frame , PredInterface returns the Interface object, as opposed to the method pred , which returns the Frame .

Type

Read-only attribute

Syntax

&lt;ConnectorPath &gt;.PredInterface → object

Return Value

The return value has the data type object .

Example

print Connector2.predinterface

SimTalk

SuccInterface [SimTalk]

pred [SimTalk] - general description

See also

Show Predecessors [model settings]

##### PredLane [SimTalk] - Connector

Returns the lane of a TwoLaneTrack , whose end point is connected with the Connector designated by &lt;Connector-Path&gt;.

Remarks

The predecessor lane is the lane which leads to the Connector in the forward direction.

If the predecessor is not a TwoLaneTrack , PredLane returns the predecessor object.

Type

Read-only attribute

Syntax

&lt;ConnectorPath &gt;.PredLane → any

Return Value

The return value has the data type any .

Example

print Connector2.PredLane

SimTalk

SuccLane [SimTalk] - Connector

**SuccInterface [SimTalk]**

##### SuccInterface [SimTalk]

Returns the direct successor object of the Connector designated by &lt;Connector-Path&gt;.

Remarks

If the succeeding object is a Frame , SuccInterface returns the Interface object, as opposed to the method succ , which returns the Frame .

Type

Read-only attribute

Syntax

&lt;ConnectorPath &gt;.SuccInterface → object

Return Value

The return value has the data type object .

Example

print connector2.SuccInterface

SimTalk

SuccInterface [SimTalk]

succ [SimTalk] - general description

See also

Show Successors [model settings]

##### SuccLane [SimTalk] - Connector

Returns the lane of a TwoLaneTrack , whose starting point is connected with the Connector designated by &lt;Connector-Path&gt;.

Remarks

The successor lane is the lane to which the Connector leads in the forward direction.

If the successor is not a TwoLaneTrack , SuccLane returns the successor object.

Type

Read-only attribute

Syntax

&lt;ConnectorPath &gt;.SuccLane → any

Return Value

The return value has the data type any .

Example

print Connector2.SuccLane

SimTalk

PredLane [SimTalk] - Connector

#### Attributes of the Connector

\_Attributes of the Connector

The Connector provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyStation.succConnector(3).Color := makeRGBValue(0,10,100)
print MyStation.succConnector(3).Width
posit := MyStation.Cont.XPos
```

&lt;Connector-Path&gt; designates a valid path to a Connector for which the method applies, either an absolute path to the Connector in the Class Library ( .Materialflow.Connector ) or an access by the methods predConnector or succConnector .

##### Color [SimTalk] - Connector

Sets the color of the Connector designated by &lt;Connector-Path&gt;.

Remarks

Set the RGB values of the color with the method makeRGBValue . If you assign an invalid value to the attribute Color , Plant Simulation retains the current color.

The Connectors in 3D use the color you define here as well. The default RGB color 7, 0, 0 of the Connector in Plant Simulation is interpreted as white in 3D . All other colors are applied as you define them in Plant Simulation .

Type

Attribute

Syntax

```simtalk
<ConnectorPath >.Color:integer
```

**Assignment Value**

You can assign a value of data type integer .

Example

```simtalk
MyStation.succConnector(3).Color := makeRGBValue(100,100,100)
MyStation.succConnector(3).Color := 6579300 // is the same as the color above
```

SimTalk

makeRGBValue [SimTalk]

See also

Color [Connector]

**CornerPointsArray [SimTalk]**

##### CornerPointsArray [SimTalk]

Sets the pixel coordinates of the anchor points of the Connector designated by &lt;Connector-Path&gt;.

Remarks

If the Connector does not have anchor points, the array is empty. In a 3D Only model this is always the case.

Type

Attribute

Syntax

```simtalk
<ConnectorPath >.CornerPointsArray:[integer[2,*]]
```

**Assignment Value**

You can assign a value of data type array . This is a two-dimensional array of data type integer .

**Example**

```simtalk
Connector1.CornerPointsArray := make2DimArray(2, [80, 50]) // sets an anchor point in 2D at the coordinates x=80, y=50
```

**SimTalk**

_3D.CornerPoints [SimTalk] make2DimArray [SimTalk]

##### Width [SimTalk] - Connector

Sets the width of the Connector designated by &lt;Connector-Path&gt;.

Remarks

The Width is a value of data type real .

For 3D Only models you can reduce the default width, which corresponds to 0 or 1, with values between 0 and 1, to a fraction of that.

The Connectors in 3D use the line width you define here as well.

Type

Attribute

Syntax

```simtalk
<ConnectorPath >.Width:real
```

**Assignment Value**

You can assign a value of data type real .

You can specify a number between 1 and 100 pixels.

- 1 stands for a line weight of 1 pixel in a Frame window with a zoom factor of 100 percent.
- 0 stands for a Connector width of 1 pixel no matter if the Frame window is zoomed or not.
- -1 makes the Connector invisible.

<!-- image -->

**Examples**

MyStation.succConnector(3).Width := 2

```simtalk
.Materialflow.Connector.Width := 0.5 -- 3D model
```

See also

Width [text box] - Connector

