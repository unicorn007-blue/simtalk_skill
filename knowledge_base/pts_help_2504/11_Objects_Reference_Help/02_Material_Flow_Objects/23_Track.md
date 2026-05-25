### Track

See also

Width [text box] - Turnplate

Curve Width

**Track**

#### Track [object]

Use the Track for modeling way to model a part of a transport line, with or without automatic routing , on which the Transporter drives and moves parts.

Icon

<!-- image -->

Description

You might, for example, use the Track and the Transporter to model an AGV (automated guided vehicle) system. The distance, which the Transporter has to travel on the Track -defined by the Track's Length , the Transporter's MU Length , and its Speed -determines the time, which the Transporter remains on the Track . As opposed to the point-oriented material flow objects, Plant Simulation uses the actual Length , which you type in, during your simulation run. A Transporter cannot pass another Transporter moving in front of it. Transporters thus retain their order of moving onto and of moving off the Track (FIFO)

If several Transporters travel along the Track at a different speed, and a faster one collides with a slower one, Plant Simulation activates the Collision Control of the faster Transporter and automatically reduces its speed to the speed of the slower Transporter .

The maximum capacity of the Track is defined by its length and the lengths of the individual Transporters moving on it, i.e., a Track that is three yards long accepts three Transporters of one yard each at the most. You can use the Capacity to further restrict the number of Transporters located on the Track .

The Transporter can drive forward and Backwards on the Track , i.e., it drives onto the Track at its Exit and exits it at its Entrance . Driving forward and backward are not properties of the Track , but of the Transporters , which drive on it.

You can insert the Track into a Frame as follows:

**· In a 3D Only Model**

As a curved object, which is the default setting.

By inserting any sequence of curved segments and straight segments, you can realistically model curved conveyor systems on which the Transporters move.

You can select different configurations for the Track on the tab Appearance .

<!-- image -->

**· In a 2D Only Model**

As a curved object, which is the default setting.

With its icon, if you deactivate Curve mode on the Tab Curve by clearing the check box . Then, it looks like this .

To change the Width/height of the icon, open the dialog of the object and type in the Curve Width on the tab Curve .

You can control how often the part is shown on the Track with the setting Animate Every x-th Pixel . If you insert the Track with its icon , the Number of Animation Events controls these steps.

To show a tooltip with information about the Track , hover with the mouse over it.

<!-- image -->

Show Manipulators

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

The manipulator at the start and at the end of the length-oriented object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Model a Transport System with Passive Objects Work with Length-oriented Objects in 2D and 3D Work with Length-oriented Objects in 3D Routing [TwoLaneTrack]

#### Routing [Track]

To facilitate a branching Track , can use any of these controls to move a Transporter on to the succeeding object.

**Plant Simulation uses:**

- The Exit Control of the Track .
- Automatic Routing of the Transporter .
- The Driving Control of the Transporter .
- The built-in properties of the Track described below.

The Exit Control of the Track has the highest priority. If you did not define an Exit Control and if you typed in a destination list for the Transporter , Automatic Routing moves the Transporter on to the proper successor, using the destination lists of the successors.

You can also assign a Destination to the Transporter . The Track has a Forward Destination List and a Backward Destination List , into which you type all destinations that the Transporter can reach when it drives on the Track . If you assigned a destination list to the Transporter that is ready to be moved on, the Track searches the Forward Destination List and the Backward Destination List of all successors for the Destination that you typed in, and, as soon as it finds it, moves the Transporter on to that successor. If the Track does not find the destination, it moves the Transporter to the next successor in turn. Plant Simulation terminates the search after it finds the first instance of the Destination . Automatic routing is inactive if you did not type in a Destination for the Transporter or if you typed in an Exit Control for the Track .

If you neither typed in an Exit Control nor any Destination Lists for the successors, the Track uses the Driving Control of the Transporter to move it. If you do not type in any controls at all, the built-in properties of Track move the Transporters to each of the successors, to which it is connected, in turn.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Model a Transport System with Passive Objects

#### Dialog Box of the Track

Dialog Box of the Track

Double-click the icon of the Track to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

##### Tab Attributes

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Length [text box] - Track

Type in the Length of the Track .

<!-- image -->

After you inserted it, Plant Simulation shows its length here. The length of the Track and the sum of the lengths of all Transporters located on it determine how many Transporters it can accommodate at any one time.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the length of a Track which only consists of a single straight segment.

In 3D, you can change the length of the graphic and the anchor points of the Track by clicking Show

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

SimTalk

Length [SimTalk] - Track

See also

OccupiedLength [SimTalk] - Track

###### Width [text box] - Track

Width [text box] - Track

Type in the Width of the Track .

<!-- image -->

**Note**

You can only type in the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

SimTalk

Width [SimTalk] - Track Capacity [text box] - Track Type in the Capacity of the Track .

<!-- image -->

The Capacity is the maximum number of Transporters that may be located on the Track as a whole or in part at any one time.

The default value -1 stands for an infinite capacity.

SimTalk

Capacity [SimTalk] - Track

**Backward Destination List [text box]**

###### Backward Destination List [text box]

Click the ellipsis button and select a List object in the dialog Select Object . Or type the path to a list into the text box.

<!-- image -->

Type all destination objects into this List object, which the Track can reach, when the Transporter moves in reverse on it.

Plant Simulation evaluates the destination lists when a Transporter is to be moved on to a successor. Plant Simulation searches for the destination of the Transporter in the destination lists of all succeeding Tracks , which are directly connected with Connectors . If a succeeding Track is connected via an Interface , this Interface should only have a single successor because Plant Simulation only searches in the first successor of the Interface for a destination list.

**Note**

The Transporter cannot only move forward but also in reverse on the Track , i.e., a Transporter can enter the Track at its exit and leave it at its entrance. Moving forward or in reverse are not properties of the object Track , but of the Transporter moving on it!

SimTalk

BwDestList [SimTalk]

See also

Select Object [for controls]

###### Forward Destination List [text box]

Click the ellipsis button and select a List object in the dialog Select Object . Or type the path to a list into the text box.

Type all destination objects into this List object, which the Track can reach, when the Transporter drives forward on it.

Plant Simulation evaluates the destination lists when a Transporter is to be moved on to a successor. Plant Simulation searches for the destination of the Transporter in the destination lists of all succeeding Tracks , which are directly connected with Connectors . If a succeeding Track is connected via an Interface , this Interface should only have a single successor because Plant Simulation only searches in the first successor of the Interface for a destination list.

SimTalk

FwDestList [SimTalk]

See also

Select Object [for controls]

##### Tab Times

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Recovery Time Starts

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Backward Entrance Control , a Backward Exit Control , and a Pull control .

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

In addition, you can:

- Select the Shift Calendar .
- Create and insert Sensors .

The Track shows the sensors, which you defined, on its graphic in the Frame window. To open the dialog Sensors , hold down Alt and double-click the sensor.

See also Define Controls for Length-Oriented Objects Entrance Control [general description] Exit Control [general description] Backward Entrance Control Backward Exit Control Pull Control [general description]

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object.

You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

**Tab Curve [Track]**

##### Tab Curve [Track]

Create curved Tracks for your simulation model as described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Track during a simulation run.

- Click the icon of the Track with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Backward Blocking List    |
|--------------------------------------------|---------------------------|
| Show Statistics Report [on View menu]      | Exit Blocking List        |
| Show Attributes and Methods [on View menu] | Associated Lockout Zones  |
| Contents [material flow objects]           | Associated Shift Calendar |
| Forward Blocking List                      |                           |

##### Tools Menu

The commands are described under the Tools Menu .

**Tabs Menu**

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Track

#### Methods of the Track

The Track provides:

- The method getRouteLength [SimTalk] - Track .
- The \_Methods of Curved Objects in 2D .
- The Methods of the Material Flow Objects .
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

##### getRouteLength [SimTalk] - Track

Returns the shortest route from the Track designated by &lt;Path&gt; to the target and returns the length of this route.

**Remarks**

The destination can either be a material flow object, which can be reached directly via Connectors , or a destination, which you typed into a sensor.

**Note**

As the route is intended for Transporters , Plant Simulation only takes objects of type Track and TwoLaneTrack into consideration when computing the route.

Type

Method

Syntax

```simtalk
< Path >.getRouteLength(Target:path[, Backwards:boolean, Position:length, ObjectsAlongRoute:table, RouteWeightingAttribute:string]) → length
```

**Parameters**

- The parameter Target of data type object designates the target.
- The optional parameter Backwards of data type boolean designates the direction in which Plant Simulation looks for a route. True stands for backward, false stands for forward, which is the default setting.
- The optional parameter Position of data type length designates the position on the Track at which the search starts. If you do not specify the parameter, Plant Simulation starts searching at the end of the Track if you search forward, or it starts searching at the beginning if you search backward. This is particularly important if the Destination is a sensor, which is located on the Track itself.
- The optional parameter ObjectsAlongRoute of data type table writes the objects along the route into the specified table.
- The optional parameter RouteWeightingAttribute of data type string sets the name of the attribute for the route weighting attribute for automatic routing. If the parameter is not passed, Plant Simulation does not weight the lengths of the routes.

**Return Value**

The return value has the data type length .

If Plant Simulation did not find a route, the return value is -1.

**Example**

print Track5.getRouteLength(Track26)

SimTalk

Destination [SimTalk] - sensors

RouteWeightingAttr [SimTalk] - Transporter

#### Read-Only Attributes of the Track

Read-Only Attributes of the Track

The Track provides:

- The read-only attribute OccupiedLength [SimTalk] - Track .
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Store.Capacity

##### OccupiedLength [SimTalk] - Track

Returns the part of the entire Length of the Track designated by &lt;Path&gt;, which is occupied by all Transporters located on it.

Remarks

Each Transporter located on the Track occupies part of the entire length available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.OccupiedLength → length

Return Value

The return value has the data type length .

Example

print MyTrack.OccupiedLength

See also

Length [text box] - Track

#### Attributes of the Track

\_Attributes of the Track

The Track provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Curved Objects in 2D .
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTrack.Length := 44
print MyTrack.Length
posit := MyStation.Cont.XPos
```

##### BwDestList [SimTalk]

BwDestList [SimTalk]

Sets the name of the destination list for a Transporter driving in reverse on the Track designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.BwDestList:object
```

Assignment Value

You can assign a value of data type object .

The destination list contains all destinations that the Transporter can reach while driving in reverse on this Track .

Example

```simtalk
MyTrack.BwDestList := myDataList
```

See also

Backward Destination List [text box]

##### Capacity [SimTalk] - Track

Sets the maximum number of Transporters that may be located on the Track designated by &lt;Path&gt; as a whole or in part at any one time.

Type

Attribute

Syntax

```simtalk
< Path >.Capacity:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite capacity.

Example

```simtalk
if MyTrack.Capacity = -1
	@.move(AEConveyor)
end
```

See also

Capacity [text box] - Track

##### FwDestList [SimTalk]

FwDestList [SimTalk]

Sets the name of the destination list for Transporters driving forward on the Track designated by &lt;Path&gt;.

Remarks

The destination list contains all destinations that the Transporter can reach, while moving in the forward direction on this Track .

Type

Attribute

Syntax

&lt; Path &gt;.FwDestList:object

Assignment Value

You can assign a value of data type object .

Example

MyTrack.FwDestList := myDataList1

See also

Forward Destination List [text box]

Length [SimTalk] - Track

Sets the Length of the Track designated by &lt;Path&gt;.

Remarks

A Transporter enters the Track at position 0, and exits it after covering the length which you enter here. Speed and Length result in the dwell time on the Track .

Type

Attribute

Syntax

< Path >.Length:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyTrack.Length := 44m
```

SimTalk

OccupiedLength [SimTalk] - Track

See also

Length [text box] - Track Width [SimTalk] - Track Sets the Width of the Track designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject , the Width does not affect how the Track is shown in the Frame in 2D.

Type

Attribute

Syntax

&lt; Path &gt;.Width:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyTrack.Width := 2 // meters
```

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

**TwoLaneTrack**

See also

Width [text box] - AngularConverter

Curve Width

**TwoLaneTrack**

