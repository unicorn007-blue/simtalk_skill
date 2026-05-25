### TwoLaneTrack

Use the TwoLaneTrack for modeling a transport line with two lanes on which, with or without automatic routing , on which the Transporter moves parts in opposite directions.

Icon

<!-- image -->

**Description**

You might, for example, use the TwoLaneTrack and the Transporter to model an AGV (automated guided vehicle) system. The distance, which the Transporter has to travel on the TwoLaneTrack is defined by the Length of lane A and the Length of lane B of the TwoLaneTrack , the Transporter's MU Length , and its Speed . They determine the time, which the Transporter remains on the TwoLaneTrack . As opposed to the point-oriented material flow objects, Plant Simulation uses the actual length, which you type in, during your simulation run. A Transporter may not pass another one moving in front of it. The Transporters thus retain their order of moving onto and of leaving the TwoLaneTrack . Each lane of the TwoLaneTrack may have its own length to realistically model the length of the lanes, when the TwoLaneTrack turns the corner. In that case the outside lane is longer than the inside lane.

If several Transporters travel along a lane of the TwoLaneTrack at a different speed, the faster one collides with the slower one. Plant Simulation then activates the Collision Control of the faster Transporter and automatically reduces its speed to the speed of the slower Transporter .

The Transporter can drive forward and Backwards on the TwoLaneTrack , i.e., it drives onto the TwoLaneTrack at its exit and exits it at its entrance . Driving forward and backward are not properties of the TwoLaneTrack , but of the Transporters , which drive on it.

The maximum capacity of the TwoLaneTrack is defined by its length and the lengths of the individual Transporters moving on it, i.e., a TwoLaneTrack that is three yards long accepts three Transporters of one yard each at the most. With the Capacity you can further restrict the number of Transporters located on the TwoLaneTrack .

You can insert the TwoLaneTrack into a Frame as follows:

**· In a 3D Only Model**

As a curved object, which is the default setting.

By inserting any sequence of curved segments and straight segments, you can realistically model curved conveyor systems on which the Transporters move.

You can select different configurations for the TwoLaneTrack on the tab Appearance .

<!-- image -->

**· In a 2D Only Model**

As a curved object, which is the default setting.

With its icon, if you deactivate Curve mode on the Tab Curve by clearing the check box . Then,

<!-- image -->

.

To change the Width/height of the icon, open the dialog of the object and type in the Curve width on the tab Curve .

You can control how often the part is shown on the TwoLaneTrack with the setting Animate every x-th

<!-- image -->

pixel . If you insert the TwoLaneTrack with its icon , the Number of Animation Events controls these steps.

The TwoLaneTrack supports bidirectional traffic. You can thus select if Right-hand Traffic or Left-hand Traffic applies.

It looks like this in 2D:

<!-- image -->

**It looks like this in 3D:**

<!-- image -->

To show a tooltip with information about the TwoLaneTrack , hover with the mouse over it.

<!-- image -->

Show Manipulators

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

The manipulator at the start and at the end of the length-oriented object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Model a Transport System with Passive Objects

Work with Length-oriented Objects in 2D and 3D

#### TwoLaneTrack

**Work with Length-oriented Objects in 3D Routing [TwoLaneTrack]**

#### Routing [TwoLaneTrack]

To facilitate a branching TwoLaneTrack , use any of these controls to move a Transporter on to the succeeding object.

Plant Simulation uses:

- The Exit Control of the TwoLaneTrack .
- Automatic Routing of the Transporter .
- The Driving Control of the Transporter .
- The built-in properties of the TwoLaneTrack described below.

The Exit Control has the highest priority. If you did not define an Exit Control for the TwoLaneTrack and if you typed in a destination list for the Transporter , Automatic Routing moves the Transporter on to the proper successor, using the destination list of the successors.

You can also assign a Destination to the Transporter . The TwoLaneTrack has a Forward destination list and Backward destination list for each of its lanes, into which you type all destinations that the Transporter can reach, when it moves on the respective lane of the TwoLaneTrack . If you assigned a destination list to a lane of the Transporter that is ready to be moved on, the TwoLaneTrack searches the Forward destination list and the Backward destination list of all successors for the Destination you typed in, and, as soon as it finds it, moves the Transporter on to that successor. If the TwoLaneTrack does not find the destination, it moves the Transporter to the next successor in turn. Plant Simulation terminates the search after it finds the first instance of the Destination . Automatic routing is inactive if you did not type in a Destination for the Transporter or if you typed in an Exit Control for the TwoLaneTrack .

If you did not type in an Exit Control nor any Destination Lists for the successors, the TwoLaneTrack uses the Driving Control of the Transporter to move it. If you do not type in any controls at all, the TwoLaneTrack moves the Transporters to each of the successors, to which it is connected, in turn.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Model a Transport System with Passive Objects

#### Dialog Box of the TwoLaneTrack

Dialog Box of the TwoLaneTrack

Double-click the icon of the TwoLaneTrack to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Tab Controls A/B

Entrance Locked [lane A]

Exit Locked [lane A]

Entrance Locked [lane B]

Exit locked [lane B]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Lane A

Lane A

You can select these settings for Lane A :

Length , Entrance Locked , and Exit Locked .

<!-- image -->

See also

asAny [SimTalk]

IsLaneA [SimTalk]

**Length [text box] - lane A**

**Length [text box] - lane A**

Type in the Length of Lane A of the TwoLaneTrack .

After you inserted it, Plant Simulation shows its length here. The length of the lanes of the TwoLaneTrack and the sum of the lengths of all Transporters located on it determine how many Transporters it can accommodate at any one time.

Each lane of the TwoLaneTrack may have its own length to realistically model the length of the lanes, when the TwoLaneTrack turns a corner. In that case the outside lane is longer than the inside lane.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the Length of Lane A of a TwoLaneTrack which only consists of a single straight segment.

<!-- image -->

<!-- image -->

In 3D, you can change the length of the graphic and the anchor points of the TwoLaneTrack by clicking

<!-- image -->

Show Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

SimTalk

A. Length [SimTalk] - lane A or B

A. OccupiedLength [SimTalk] - lane A or B

**Entrance Locked [lane A]**

To prevent that Transporters enter lane A of the TwoLaneTrack , select this check box.

The TwoLaneTrack will finish transporting the Transporters that are already located on it.

<!-- image -->

It does not accept any additional Transporters and enters those into the Blocking List of Lane A .

- If the Transporter wants to enter the TwoLaneTrack at its entrance, it is entered into the Forward Blocking List of Lane A .
- If the Transporter is moving backward and wants to enter a length-oriented object at its exit, it is entered into the Exit Blocking List of Lane A .

Transporting starts again once you clear the check box. The first Transporter in the Forward Blocking List of Lane A is going to be moved on first.

SimTalk

A. EntranceLocked [SimTalk] - lane A or B

See also

Forward Blocking List

Exit Blocking List

**Exit Locked [lane A]**

**Exit Locked [lane A]**

To prevent that Transporters exit Lane A of the TwoLaneTrack , select this check box.

The TwoLaneTrack does not transport the Transporters to the successor in the material flow, but enters them into the Exit Blocking List of Lane A of the TwoLaneTrack .

<!-- image -->

Once the exit is unlocked again, the TwoLaneTrack moves the first Transporter in the Exit Blocking List of Lane A on to its successor.

Note

The Transporter does not trigger the Exit Control if you selected the check box Exit Locked .

SimTalk

A. ExitLocked [SimTalk] - lane A or B

Lane B

Lane B

You can select these settings for Lane B :

Length , Entrance Locked , and Exit Locked .

<!-- image -->

See also

asAny [SimTalk]

IsLaneB [SimTalk]

**Length [text box] - lane B**

Length [text box] - lane B

Type in the Length of Lane B of the TwoLaneTrack .

After you inserted it, Plant Simulation shows its length here. The length of the lanes of the TwoLaneTrack and the sum of the lengths of all Transporters located on it determine how many Transporters it can accommodate at any one time.

Each lane of the TwoLaneTrack may have its own length to realistically model the length of the lanes, when the TwoLaneTrack turns a corner. In that case the outside lane is longer than the inside lane.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the Length of Lane B of a TwoLaneTrack which only consists of a single straight segment.

<!-- image -->

<!-- image -->

In 3D, you can change the length of the graphic and the anchor points of the TwoLaneTrack by clicking

<!-- image -->

Show Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

SimTalk

B. Length [SimTalk] - lane A or B

B. OccupiedLength [SimTalk] - lane A or B

**Entrance Locked [lane B]**

To prevent that Transporters enter Lane B of the TwoLaneTrack , select this check box.

The TwoLaneTrack will finish transporting the Transporters already located on it.

<!-- image -->

It does not accept any additional Transporters and enters those into the Blocking List of Lane B .

- If the Transporter wants to enter the TwoLaneTrack at its entrance, it is entered into the Forward Blocking List of lane B .
- If the Transporter is moving backward and want to enter a length-oriented object at its exit, it is entered into the Exit Blocking List of Lane B .

Transporting starts again once you clear the check box. The first Transporter in the Forward Blocking List of Lane B is going to be moved on first.

SimTalk

B. EntranceLocked [SimTalk] - lane A or B

See also

Forward Blocking List

Exit Blocking List

**Exit locked [lane B]**

**Exit locked [lane B]**

To prevent that Transporters exit Lane B of the TwoLaneTrack , select this check box.

The TwoLaneTrack does not transport the Transporters to the successor in the material flow, but enters them into the Exit Blocking List of Lane B of the TwoLaneTrack .

<!-- image -->

Once the exit is unlocked again, the TwoLaneTrack moves the first Transporter in the Exit Blocking List of Lane B on to its successor.

**Note**

The Transporter does not trigger the Exit Control if you selected the check box Exit locked .

SimTalk

B. ExitLocked [SimTalk] - lane A or B

See also

Exit Blocking List

###### Width [text box] - TwoLaneTrack

Type in the Width of both lanes of the TwoLaneTrack in meters.

**Note**

You can only type on the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

SimTalk

Width [SimTalk] - TwoLaneTrack

<!-- image -->

**Track Pitch [text box]**

###### Track Pitch [text box]

Type in the Track Pitch between Lane A and Lane B .

<!-- image -->

The Track Pitch is the distance between the center lines of the two lanes of the two-lane track.

<!-- image -->

**Compare this example:**

<!-- image -->

**SimTalk**

TrackPitch [SimTalk] - TwoLaneTrack

###### Right-hand Traffic/Left-hand Traffic

Select the side of the TwoLaneTrack on which traffic moves: Right-hand Traffic or Left-hand Traffic .

<!-- image -->

It looks like this in 2D:

<!-- image -->

It looks like this in 3D:

<!-- image -->

**SimTalk**

Traffic [SimTalk] - TwoLaneTrack

###### Capacity [text box] - TwoLaneTrack

Capacity [text box] - TwoLaneTrack

Type in the Capacity of the TwoLaneTrack .

<!-- image -->

The Capacity is the maximum number of Transporters that may be located on both lanes of the TwoLaneTrack as a whole or in part at any one time.

The default value -1 stands for an infinite capacity.

SimTalk

Capacity [SimTalk] - TwoLaneTrack

###### Destination List A [text box]

Click the ellipsis button and select a List object in the dialog Select Object .

<!-- image -->

Type in all destination objects into this List object, which the TwoLaneTrack can reach, when the Transporter drives forward on Lane A . The forward destination list of Lane A concurrently is the backward destination list of Lane B .

Plant Simulation evaluates the destination lists when a Transporter is to be moved on to a successor. Plant Simulation searches for the destination of the Transporter in the destination lists of all succeeding TwoLaneTracks , which are directly connected with Connectors . If a succeeding TwoLaneTrack is connected via an Interface , this Interface should only have a single successor because Plant Simulation only searches for a destination list in the first successor of the Interface

SimTalk

DestListA [SimTalk] - TwoLaneTrack

See also

Select Object [for controls]

**Destination List B [text box]**

###### Destination List B [text box]

Click the ellipsis button and select a List object in the dialog Select Object .

<!-- image -->

Type in all destination objects into this List object, which the TwoLaneTrack can reach, when the Transporter drives forward on Lane B . The forward destination list of Lane B concurrently is the backward destination list of Lane A .

Plant Simulation evaluates the destination lists when a Transporter is to be moved on to a successor. Plant Simulation searches for the destination of the Transporter in the destination lists of all succeeding TwoLaneTracks , which are directly connected with Connectors . If a succeeding TwoLaneTrack is connected via an Interface , this Interface should only have a single successor because Plant Simulation only searches in the for a destination list in first successor of the Interface .

SimTalk

DestListB [SimTalk] - TwoLaneTrack

See also

Select Object [for controls]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls A/B

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Backward Entrance Control , a Backward Exit Control , and a Pull Control for Lane A and/or for Lane B of the TwoLaneTrack .

**Create a Control that is a Method of the Object**

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
- Create and insert Sensors on each lane separately or on both lanes. The TwoLaneTrack provides settings to accommodate the two lanes. The button Sensors shows how many sensors you inserted for this lane. Clicking the button shows the Sensor List , which displays all sensors you defined for the two lanes.

<!-- image -->

<!-- image -->

The TwoLaneTrack shows the sensors, which you defined, on its graphic in the Frame window. To open the dialog Sensors , hold down Alt and double-click the sensor.

See also

Define Controls for Length-Oriented Objects

Select Object [for controls]

Entrance Control [general description]

Exit Control [general description]

Backward Entrance Control

Backward Exit Control

Pull Control [general description]

**Tab Statistics**

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

##### Tab Curve [TwoLaneTrack]

Create curved TwoLaneTracks for your simulation model as described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object TwoLaneTrack during a simulation run.

- Click the icon of the TwoLaneTrack with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu of the TwoLaneTrack provides commands to access the functions for each of its two lanes.

| Refresh [on View menu]                                                    | Backward Blocking List ( bwBlockList [SimTalk] - lane A or B )   |
|---------------------------------------------------------------------------|------------------------------------------------------------------|
| Show Statistics Report [on View menu]                                     | Exit Blocking List ( exitBlockList [SimTalk] - lane A or B )     |
| Show Attributes and Methods [on View menu]                                | Associated Lockout Zones                                         |
| Contents [material flow objects] ( contentsList [SimTalk] - lane A or B ) | Associated Shift Calendar                                        |
| Forward Blocking List ( fwBlockList [SimTalk] - lane A or B )             |                                                                  |

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

**Methods of the TwoLaneTrack**

#### \_Methods of the TwoLaneTrack

The TwoLaneTrack provides:

- The methods listed in the table of contents to the left.
- The \_Methods of Curved Objects in 2D .
- The Methods of the Material Flow Objects .
- The Methods of All Objects .

**Note**

A number of methods, which the TwoLaneTrack shares with the other material flow objects, apply to a lane, instead of to the entire object.

To view all of the methods , read-only attributes , and attributes of the TwoLaneTrack , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

For the TwoLaneTrack the dialog shows A and B for the respective lane, but not the methods proper for these lanes.

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.A.exitBlockList([ExitBlockingList:table])
-> object[] < Path >.B.exitBlockList([ExitBlockingList:table])
-> object[]
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies. The expression A or B designates the lane of the TwoLaneTrack that you want to access.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter If the method has a return value, the signature shows its data type after the arrow -&gt;.

##### \_Methods of the TwoLaneTrack

bwBlockList [SimTalk] - lane A or B

Returns the blocking list in the backward direction of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

Specify the optional parameter of data type table , to make bwBlockList write the objects contained in the Backward Blocking List into this list.

Do not specify the parameter, to make bwBlockList return an array containing the objects contained in the Backward Blocking List . The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStartTime .

Type

Method

Syntax

```simtalk
< Path >.A.bwBlockList([BackwardBlockingList:table]) → any < Path >.B.bwBlockList([BackwardBlockingList:table]) → any
```

Parameter

The optional parameter BackwardBlockingList of data type table designates the name of the table, which can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns.

Column 1 has the data type object and contains all Transporters that unsuccessfully tried to move to the object.

Column 2 contains the simulation time at which the Transporters attempted to enter the object. The number of rows matches the number of Transporters in the blocking list.

Return Value

The return value has the data type any .

The return value is an array containing all MUs in the Backward Blocking List of the TwoLaneTrack on the specified lane if you do not specify the optional parameter.

**Example**

MyTwoLaneTrack.B.bwBlocklist(DataTable)

SimTalk

BlockingStarttime [SimTalk]

BwBlockListEntry1 [SimTalk]

See also

Backward Blocking List

Check the Contents List of the Stations contentsList [SimTalk] - lane A or B

Returns the entire Contents , i.e., all Transporters which are located on the specified lane of the Contents List of TwoLaneTrack designated by &lt;Path&gt;.

Remarks

Specify the optional parameter of data type table to write the objects contained in the Contents List into this list.

Do not specify the parameter to return an array containing the objects contained in the Contents List .

Type

Method

Syntax

```simtalk
< Path >.A.contentsList([ContentsList:table]) → any < Path >.B.contentsList([ContentsList:table]) → any
```

**Parameter**

The optional parameter ContentsList of data type table designates the name of the table. Plant Simulation automatically generates the format of this table and deletes any existing format and contents of the table. The contents list is a table with three columns. The data type of column 1 is object , of the second and third length . Column 1 contains the path to the Transporters , column 2 the start position of the MU part, and column 3 the end position in the length unit you specified. The number of rows matches the number of Transporter parts located on the object.

Return Value

The return value has the data type any .

Is an array containing the objects in the Contents List if you do not specify the optional parameter.

**Examples**

```simtalk
MyTwoLaneTrack.A.contentsList(DataTable)
print TwoLaneTrack.A.contentsList // might, for example,
return [.MUs.Transporter:314, 34.488399, 35.988399] [.MUs.Transporter:316, 32.988399, 34.488399][.MUs.Transporter:318,
```

31.488399, 32.988399][.MUs.Transporter:320, 29.988399, 31.488399] in the Console

```simtalk
print TwoLaneTrack.A.contentsList // might, for example,
return [.MUs.Transporter:314, 34.488399, 35.988399] [.MUs.Transporter:316, 32.988399, 34.488399][.MUs.Transporter:318, 31.488399, 32.988399][.MUs.Transporter:320, 29.988399, 31.488399] in the Console
```

**SimTalk**

contentsList [SimTalk] - material flow objects

See also

Contents [material flow objects]

Check the Contents List of the Stations exitBlockList [SimTalk] - lane A or B

Returns the Exit Blocking List of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

Specify the optional parameter ExitBlockingList of data type table to write the objects contained in the Backward Blocking List into this list.

Do not specify the parameter ExitBlockingList to return an array containing the objects contained in the Backward Blocking List .

The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

Type

Method

Syntax

```simtalk
< Path >.A.exitBlockList([ExitBlockingList:table])
-> object[] < Path >.B.exitBlockList([ExitBlockingList:table])
-> object[]
```

Parameter

The optional parameter ExitBlockingList of data type table designates the name of the table, which can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns.

Column 1 has the data type object and contains the Transporters that unsuccessfully tried to exit the object.

Column 2 contains the simulation time at which the Transporters attempted to enter the object.

Return Value

The return value has the data type any .

Example

MyTwoLaneTrack.B.exitBlockList(DataTable)

SimTalk BlockingStarttime [SimTalk] See also Exit Blocking List Check the Contents List of the Stations fwBlockList [SimTalk] - lane A or B

Returns the Blocking List in the forward direction of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

Specify the optional parameter of data type table to write the objects contained in the Forward Blocking List into this list.

Do not specify the parameter to return an array containing the objects contained in the Forward Blocking List .

The array is one-dimensional and only contains the objects in the blocking list. If you need the start times of the blockages, which are contained in the blocking table, you can query them from the object with the attribute BlockingStarttime .

Type

Method

Syntax

```simtalk
< Path >.A.fwBlockList([ForwardBlockingList:table])
-> any < Path >.B.fwBlockList([ForwardBlockingList:table])
-> any
```

**Parameter**

The optional parameter ForwardBlockingList of data type table designates the name of the table, which can be a DataTable or a local variable, into which the method writes the values.

Plant Simulation automatically generates the format of this table with two columns.

Column 1 has the data type object and contains the Transporters that unsuccessfully tried to move to the object.

Column 2 contains the simulation time at which the Transporters attempted to enter the object. The number of rows matches the number of Transporters in the blocking list.

Return Value

The return value has the data type any .

**Example**

MyTwoLaneTrack.B.fwBlockList(DataTable)

SimTalk

BlockingStarttime [SimTalk]

See also

Forward Blocking List

Check the Contents List of the Stations

**getRouteLength [SimTalk] - lane A or B**

Returns the shortest route from the lane of the TwoLaneTrack designated by &lt;Path&gt; to the target and returns the length of this route.

**Remarks**

The destination can either be a material flow object, which can be reached directly via Connectors , or a destination, which you typed into a sensor.

**Note**

As the route is intended for Transporters , Plant Simulation only takes objects of type Track and TwoLaneTrack into consideration, when computing the route.

Type

Method

Syntax

```simtalk
< Path >.A.getRouteLength(Target:path[, Backwards:boolean, Position:length, ObjectsAlongRoute:table, RouteWeightingAttribute:string] → length < Path >.B.getRouteLength(Target:path[, Backwards:boolean, Position:length, ObjectsAlongRoute:table, RouteWeightingAttribute:string] → length
```

**Parameters**

- The parameter Target of data type object designates the target.
- The optional parameter Backwards of data type boolean designates the direction in which Plant Simulation looks for a route. True stands for backward, false stands for forward, which is the default setting.
- The optional parameter Position of data type length designates the position on the lane at which the search starts. If you do not specify the parameter, Plant Simulation starts searching at the end of the lane if you search forward, or it starts searching at the beginning if you search backward. This is particularly important if the Destination is a sensor, which is located on the lane of the TwoLaneTrack itself.
- The optional parameter ObjectsAlongRoute of data type table writes the objects along the route into the specified table.
- The optional parameter RouteWeightingAttribute of data type string sets the name of the attribute for the route weighting attribute for automatic routing. If the parameter is not passed, Plant Simulation does not weight the lengths of the routes.

**Return Value**

The return value has the data type length .

Is -1 if Plant Simulation did not find a route.

**Example**

print TwoLaneTrack5.B.getRouteLength(Track26)

**SimTalk**

Destination [SimTalk] - sensors

RouteWeightingAttr [SimTalk] - Transporter pred [SimTalk] - lane A or B

Returns the direct predecessor of the designated lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.A.pred([PredecessorNumber:integer:=1]) → object < Path >.B.pred([PredecessorNumber:integer:=1]) → object
```

Parameter

The optional parameter PredecessorNumber of data type integer designates the n-th predecessor of the specified lane of the TwoLaneTrack . The objects have to be connected for this to work.

**Default Value of the Parameter**

The default value is 1.

Return Value

The return value has the data type object .

Example

if MyTwoLaneTrack.A.pred(3) = TwoLaneTrack1

... end

See also

succ [SimTalk] - lane A or B

##### predConnector [SimTalk] - lane A or B

predConnector [SimTalk] - lane A or B

Returns the incoming Connector connected directly with the specified lane of the TwoLaneTrack designated by &lt;Path&gt;. Adding and deleting connections may change the index number of a connection.

Type

Method

Syntax

```simtalk
< Path >.A.predConnector([PredecessorNumber:integer:=1]) → object < Path >.B.predConnector([PredecessorNumber:integer:=1]) → object
```

Parameter

The optional parameter PredecessorNumber of data type integer designates the n-th preceding Connector of the specified lane of the TwoLaneTrack .

**Default Value of the Parameter**

The default value is 1.

Return Value

The return value has the data type object .

VOID if the connection does not exist.

Example

```simtalk
for var i := MyTwoLaneTrack.B.NumPred downto 1 // deletes connections MyTwoLaneTrack.B.predConnector(i).deleteObject
next
```

**SimTalk**

succConnector [SimTalk] - lane A or B

predLane [SimTalk] - lane A or B

Returns the direct predecessor of the designated lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.A.predLane([Predecessor:integer]) → any < Path >.B.predLane([Predecessor:integer]) → any
```

Parameter

The optional parameter Predecessor of data type integer designates the lane of the n-th predecessor of the TwoLaneTrack . The objects have to be connected for this to work.

Return Value

The return value has the data type any .

Example

if MyTwoLaneTrack.A.predLane(3) = TwoLaneTrack1.B ... end

SimTalk

succLane [SimTalk] - lane A or B

##### predLaneNo [SimTalk] - lane A or B

predLaneNo [SimTalk] - lane A or B Returns the number of the preceding lane of the specified lane of the TwoLaneTrack designated by <Path>. Remarks Only works if the objects are connected. Type Method Syntax

```simtalk
< Path >.A.predLaneNo([Predecessor:integer]) → integer < Path >.B.predLaneNo([Predecessor:integer]) → integer
```

**Parameter**

The optional parameter Predecessor of data type integer designates the number of the lane of the n-th predecessor of the TwoLaneTrack . The objects have to be connected for this to work.

Return Value

The return value has the data type integer .

Example

```simtalk
if MyTwoLaneTrack.A.predLaneNo(3) = 2
	print "third preceeding lane is lane B"
end
```

**SimTalk**

succLaneNo [SimTalk] - lane A or B

##### succ [SimTalk] - lane A or B

Returns the direct successor of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.A.succ([SuccessorNumber:integer:=1]) → object < Path >.B.succ([SuccessorNumber:integer:=1]) → object
```

Parameter

The optional parameter SuccessorNumber of data type integer designates the number of the successor on the specified lane of the TwoLaneTrack . The objects have to be connected for this to work.

**Default Value of the Parameter**

The default value is 1, meaning the first successor on the lane.

Return Value

The return value has the data type object .

**Note**

If the n-th successor of the object is an Interface , Plant Simulation does not return the Interface itself, but the successor of the Interface . If this again is an Interface , it will be tracked until Plant Simulation reaches a material flow object which can accept MUs .

If the n-th successor of the object is a Frame , Plant Simulation does not return the Frame itself, but the successor of the Interface inserted into this Frame .

If an Interface only has a single successor, this successor is uniquely identified and will be used, independent of the exit strategy of the Interface .

If an Interface has several successors, the successor is identified according to its exit strategy. If you selected a blocking exit strategy, the strategy determines the successor no matter if it can accept a MU at the moment or not.

If you selected a non-blocking exit strategy, Plant Simulation searches for the next successor that can accept a MU according to the selected exit strategy.

If none of the successors can accept a MU , the method returns VOID. The successor that can accept a MU next cannot be determined at that point in time. This does not apply if there is only a single successor.

**Example**

if MyTwoLaneTrack.B.succ = TwoLaneTrack1 ... end

**SimTalk**

pred [SimTalk] - lane A or B

##### succConnector [SimTalk] - lane A or B

Returns the outgoing Connector connected directly with the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

Adding and deleting connections may change the index number of a connection.

Type

Method

Syntax

```simtalk
< Path >.A.succConnector([SuccessorNumber:integer:=1]) → object < Path >.B.succConnector([SuccessorNumber:integer:=1]) → object
```

**Parameter**

The optional parameter SuccessorNumber of data type integer designates the successor on the specified lane of the TwoLaneTrack . The objects have to be connected for this to work.

**Default Value of the Parameter**

The default value is 1, meaning the first succeeding connector on the lane.

Return Value

The return value has the data type object .

VOID if the connection does not exist.

Example

myTwoLaneTrack.B.succConnector.deleteObject

**SimTalk**

predConnector [SimTalk] - lane A or B

##### succLane [SimTalk] - lane A or B

succLane [SimTalk] - lane A or B

Returns the direct successor of the designated lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.A.succLane([Successor:integer]) → any < Path >.B.succLane([Successor:integer]) → any
```

Parameter

The optional parameter Successor of data type integer designates the lane of the n-th successor of the TwoLaneTrack . The objects have to be connected for this to work.

Return Value

The return value has the data type any .

Example

if MyTwoLaneTrack.B.succLane = TwoLaneTrack1.A ... end

SimTalk

predLane [SimTalk] - lane A or B

succLaneNo [SimTalk] - lane A or B

Returns the number of the succeeding lane of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.A.succLaneNo([LaneNumber:integer]) → integer < Path >.B.succLaneNo([LaneNumber:integer]) → integer
```

Parameter

The optional parameter LaneNumber of data type integer designates the number of the lane of the n-th successor lane of the TwoLaneTrack . The objects have to be connected for this to work.

Return Value

The return value has the data type integer .

Example

```simtalk
if MyTwoLaneTrack.A.succLaneNo = 1
	print "succeeding lane is lane A"
end
```

SimTalk

predLaneNo [SimTalk] - lane A or B

#### Read-Only Attributes of the TwoLaneTrack

\_Read-Only Attributes of the TwoLaneTrack

The TwoLaneTrack provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

For the TwoLaneTrack the dialog shows A and B for the respective lane, but not the read-only attributes proper for these lanes.

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print TwoLaneTrack.A.NumPred

##### IsLaneA [SimTalk]

IsLaneA [SimTalk]

Returns if the Transporter drives on lane A of the TwoLaneTrack designated by &lt;Path&gt; (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.A.IsLaneA → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print TwoLaneTrack.A.IsLaneA    // returns true if the Transporter drives
on lane A
print TwoLaneTrack.A.IsLaneA    // returns false if the Transporter does not drive on lane A
```

See also

Lane A

##### IsLaneB [SimTalk]

Returns if the Transporter drives on lane B of the TwoLaneTrack designated by &lt;Path&gt; (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.B.IsLaneB → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print TwoLaneTrack.B.IsLaneB    // returns true if the Transporter drives on lane B
print TwoLaneTrack.B.IsLaneB    // returns false if the Transporter does not drive on lane B
```

See also

Lane B

##### NumPred [SimTalk] - lane A or B

NumPred [SimTalk] - lane A or B

Returns the number of predecessors of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.A.NumPred → integer < Path >.B.NumPred → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
for var i := 1 to MyTwoLaneTrack.B.NumPred
	print MyTwoLaneTrack.B.pred(i) // prints all predecessors
next
```

SimTalk

NumSucc [SimTalk] - lane A or B

##### NumSucc [SimTalk] - lane A or B

Returns the number of successors of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.A.NumSucc → integer < Path >.B.NumSucc → integer
```

Return Value

The return value has the data type integer .

**Example**

if MyTwoLaneTrack.A.NumSucc > 1 ... // more than one successor end

**SimTalk**

NumPred [SimTalk] - lane A or B

##### OccupiedLength [SimTalk] - lane A or B

Returns the part of the entire length of the specified lane of the TwoLaneTrack designated by &lt;Path&gt; which is occupied by all Transporters located on it.

Remarks

Each Transporter located on the TwoLaneTrack occupies part of the entire available length on the TwoLaneTrack .

Type

Read-only attribute

Syntax

< Path >.A.OccupiedLength → length < Path >.B.OccupiedLength → length

Return Value

The return value has the data type length .

Example

```simtalk
print myTwoLaneTrack.A.OccupiedLength
```

See also

Length [text box] - lane A

Length [text box] - lane B

#### Attributes of the TwoLaneTrack

\_Attributes of the TwoLaneTrack

The TwoLaneTrack provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Curved Objects in 2D .
- The Attributes of All Objects .

- The Attributes of the Material Flow Objects .

**Note**

A number of attributes, which the TwoLaneTrack shares with the other material flow objects, apply to a lane, instead of to the entire object.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

For the TwoLaneTrack the dialog shows A and B for the respective lane, but not the attributes proper for these lanes.

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTwoLaneTrack.B.Length:= 44
print MyTwoLaneTrack.B.Length
posit := MyStation.Cont.XPos
```

**See also**

- \_Methods of the TwoLaneTrack
- \_Read-Only Attributes of the TwoLaneTrack

**BwEntranceCtrl [SimTalk] - lane A or B**

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method when a Transporter enters the specified lane of the TwoLaneTrack designated by &lt;Path&gt; via its exit and/or when the Transporter moves toward its entrance after entering.

Type

Attribute

Syntax

< Path >.A.BwEntranceCtrl:method < Path >.B.BwEntranceCtrl:method

**Assignment Value**

You can assign a value of data type method .

Example

```simtalk
MyTwoLaneTrack.B.BwEntranceCtrl := &MyBackwardEntranceMethod
```

See also

Backward Entrance Control

##### BwEntranceCtrlFront [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; activates the Backward Entrance Control as soon as the Front of the Transporter enters the TwoLaneTrack on the designated lane via its exit and/or when it moves toward its entrance after entering ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.BwEntranceCtrlFront:boolean < Path >.B.BwEntranceCtrlFront:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.B.BwEntranceCtrl := &Method1
MyTwoLaneTrack.B.BwEntranceCtrlFront := false
```

See also

Backward Entrance Control

##### BwEntranceCtrlRear [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; activates the Backward Entrance Control as soon as the rear of the Transporter enters the TwoLaneTrack via its exit and/or when it moves toward its entrance after entering ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.BwEntranceCtrlRear:boolean < Path >.B.BwEntranceCtrlRear:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyTwoLaneTrack.A.BwEntranceCtrl := &MyMethod
MyTwoLaneTrack.A.BwEntranceCtrlRear := false
MyTwoLaneTrack.B.BwEntranceCtrl := &MyBackwardEntranceMethod
MyTwoLaneTrack.B.BwEntranceCtrlRear := true
```

See also

Backward Entrance Control

##### BwExitCtrl [SimTalk] - lane A or B

BwExitCtrl [SimTalk] - lane A or B

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method when a Transporter exits the designated lane of the TwoLaneTrack via it entrance and/or when the Transporter moves toward its entrance when exiting.

Type

Attribute

Syntax

< Path >.A.BwExitCtrl:method < Path >.B.BwExitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyTwoLaneTrack.B.BwExitCtrl := &MyBackwardExitMethod
```

See also

Backward Exit Control

##### BwExitCtrlFront [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; activates the Backward Exit Control as soon as the front of the Transporter exits the designated lane of the TwoLaneTrack via it entrance and/or when the Transporter moves toward its entrance when exiting ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.BwExitCtrlFront:boolean < Path >.B.BwExitCtrlFront:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.B.BwExitCtrl := &MyBackwardExitMethod
MyTwoLaneTrack.A.BwExitCtrlFront := false
```

See also

Backward Exit Control BwExitCtrlRear [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; activates the Backward Exit Control as soon as the Rear of the Transporter exits the designated lane of the TwoLaneTrack via it entrance and/or when the Transporter moves toward its entrance when exiting ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.BwExitCtrlRear:boolean < Path >.B.BwExitCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.B.BwExitCtrl := &MyBackwardExitMethod
MyTwoLaneTrack.B.BwExitCtrlRear := true
```

See also

Backward Exit Control

##### Capacity [SimTalk] - TwoLaneTrack

Sets the maximum number of Transporters that may be located on the TwoLaneTrack designated by &lt;Path&gt; as a whole or in part at any one time.

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

Specify -1 for an infinite Capacity .

Example

```simtalk
if MyTwoLaneTrack.Capacity = -1
	@.move(AEConveyor)
end
```

See also

Capacity [text box] - TwoLaneTrack DestListA [SimTalk] - TwoLaneTrack Sets the path to the Destination List for Transporters which drive in the forward direction on Lane A on the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

The Destination List contains all destination objects, which the Transporter can reach while driving in the forward direction on Lane A on this TwoLaneTrack .

The forward destination list of Lane A concurrently is the backward destination list of Lane B .

Type

Attribute

Syntax

&lt; Path &gt;.DestListA:object

Assignment Value

You can assign a value of data type object .

Example

MyTwoLaneTrack.DestListA := MyDataList1

See also

Destination List A [text box]

##### DestListB [SimTalk] - TwoLaneTrack

Sets the path to the Destination List for Transporters which drive in the forward direction on Lane B on the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

The Destination List contains all destinations that the Transporter can reach while driving in the forward direction on Lane B on this TwoLaneTrack .

The forward destination list of Lane B concurrently is the backward destination list of Lane A .

Type

Attribute

Syntax

&lt; Path &gt;.DestListB:object

Assignment Value

You can assign a value of data type object .

Example

MyTwoLaneTrack.DestListB := MyDataList2

See also

Destination List B [text box]

**EntranceCtrl [SimTalk] - lane A or B**

##### EntranceCtrl [SimTalk] - lane A or B

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as a Transporter enters the TwoLaneTrack designated by &lt;Path&gt; on the specified lane.

Type

Attribute

Syntax

< Path >.A.EntranceCtrl:method < Path >.B.EntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyTwoLaneTrack.A.EntranceCtrl := &MyEntranceMethod
```

See also

Entrance Control [general description]

##### EntranceCtrlFront [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; triggers the entrance control on the specified lane as soon as the front of the Transporter enters the TwoLaneTrack ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.EntranceCtrlFront:boolean < Path >.B.EntranceCtrlFront:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.A.EntranceCtrl := &MyEntranceMethod
MyTwoLaneTrack.A.EntranceCtrlFront := true
```

See also

Entrance Control [general description]

##### EntranceCtrlRear [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; triggers the entrance control on the specified lane as soon as the rear of the Transporter enters the TwoLaneTrack ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.EntranceCtrlRear:boolean < Path >.B.EntranceCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.A.EntranceCtrl := &MyEntranceMethod
MyTwoLaneTrack.A.EntranceCtrlRear := true
```

See also

Entrance Control [general description]

##### EntranceLocked [SimTalk] - lane A or B

Locks the entrance of Lane A/B of the TwoLaneTrack designated by &lt;Path&gt; ( true ) or nor ( false ). It thus prevents that Transporters can enter the object.

Remarks

The TwoLaneTrack will finish transporting the Transporters already located on it.

It does not accept any additional Transporters and enters them into the Blocking List of Lane A/B .

- If the Transporter wants to enter the TwoLaneTrack at its entrance, the Transporter is entered into the Forward Blocking List of Lane A/B .
- If the Transporter is moving backward and wants to enter a length-oriented object at its exit, the Transporter is entered into the Exit Blocking List of Lane A/B .

The TwoLaneTrack starts transporting again, when you set the attribute to false . The first Transporter in the Forward Blocking List of Lane A/B is going to be moved on first.

Type

Attribute

Syntax

```simtalk
< Path >.A.EntranceLocked:boolean < Path >.B.EntranceLocked:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.B.EntranceLocked := true
waituntil MyTwoLaneTrack.B.NumMu 10 prio 1
MyTwoLaneTrack.B.EntranceLocked := false
```

See also Entrance Locked [lane A] Entrance Locked [lane B] Forward Blocking List Exit Blocking List

##### ExitCtrl [SimTalk] - lane A or B

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as a Transporter exits the TwoLaneTrack designated by &lt;Path&gt; on the specified lane. If you did not specify a Method , the attribute is VOID.

Type

Attribute

Syntax

< Path >.A.ExitCtrl:method < Path >.B.ExitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyTwoLaneTrack.A.ExitCtrl := &MyExitMethod
```

See also

Exit Control [general description]

##### ExitCtrlFront [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; triggers the Exit Control as soon as the front of the Transporter exits on the specified lane ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.ExitCtrlFront:boolean < Path >.B.ExitCtrlFront:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.A.ExitCtrl := &MyExitMethod
MyTwoLaneTrack.A.ExitCtrlFront := false
```

See also

Exit Control [general description]

##### ExitCtrlRear [SimTalk] - lane A or B

Sets if the TwoLaneTrack designated by &lt;Path&gt; triggers the Exit Control as soon as the rear of the Transporter exits on the specified lane ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.A.ExitCtrlRear:boolean < Path >.B.ExitCtrlRear:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.A.ExitCtrl := &MyExitMethod
MyTwoLaneTrack.A.ExitCtrlRear := true
```

See also

Exit Control [general description]

##### ExitLocked [SimTalk] - lane A or B

Locks the exit of Lane A/B of the TwoLaneTrack designated by &lt;Path&gt; ( true ) or not ( false ). It thus prevents that Transporters leave the object.

Remarks

The TwoLaneTrack does not transport the Transporters to the successor in the material flow, but enters them into the Exit Blocking List of Lane A/B of the TwoLaneTrack .

Once the exit is unlocked again, the TwoLaneTrack moves the first Transporter in the Exit Blocking List of Lane A/B on to its successor.

When setting ExitLocked to false Transporters entered into the Exit Blocking List will make another attempt to exit the TwoLaneTrack .

**Note**

The Transporter does not trigger the Exit Control if you set ExitLocked to true .

Type

Attribute

Syntax

```simtalk
< Path >.A.ExitLocked:boolean < Path >.B.ExitLocked:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTwoLaneTrack.A.ExitLocked := true
```

See also

Exit Locked [lane A]

Exit locked [lane B] of lane B Exit Blocking List

ExitLocked [SimTalk] - lane A or B

##### Length [SimTalk] - lane A or B

Length [SimTalk] - lane A or B

Sets the physical length of the specified lane of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

A Transporter enters the specified lane of the TwoLaneTrack at position 0 and exits after covering the length you enter here. Speed and Length yield the dwelling time on the TwoLaneTrack .

Type

Attribute

Syntax

< Path >.A.Length:length < Path >.B.Length:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

Example

```simtalk
MyTwoLaneTrack.A.Length := 44    // meters
MyTwoLaneTrack.B.Length := 43.8  // meters
```

SimTalk

OccupiedLength [SimTalk] - lane A or B

See also

Length [text box] - lane A

Length [text box] - lane B

##### PullCtrl [SimTalk] - lane A or B

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation runs the Method when the TwoLaneTrack designated by &lt;Path&gt; is ready to accept a new Transporter on the specified lane or when it is ready, when a new Transporter is Waiting at its entrance.

In the Pull Control you can determine which Transporter , which intends to move onto the TwoLaneTrack , the TwoLaneTrack will accept. For this you have to get the Forward Blocking List of the respective lane with the method fwBlockList and unblock a Transporter in the list with the method unblock .

**Note**

If you only need the first entry of the Forward Blocking List , use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

Suppose that red parts are especially important and thus have to be processed first. You can always pull red parts from the predecessors in the Pull Control first and then parts with other colors.

**Note**

The Pull Control does not determine if a Transporter is to be moved on to this successor or to another successor, but it selects one of the Transporters which already decided to move to this successor.

**Note**

For the TwoLaneTrack the Pull Control only applies to Transporters that drive forward, meaning that they enter the TwoLaneTrack at the entrance and they exit at the exit. It does not apply to Transporters driving in reverse entering at the exit and not to Transporters that have been moved to a certain position.

Type

Attribute

Syntax

&lt; Path &gt;.A.PullCtrl:method

&lt; Path &gt;.B.PullCtrl:method

**Assignment Value**

You can assign a value of data type method .

**Example**

MyTwoLaneTrack.A.PullCtrl := &amp;MyPullMethod

SimTalk

fwBlockList [SimTalk] - lane A or B

FwBlockListEntry1 [SimTalk]

DecimalPlaces [SimTalk] - Variable

See also

Pull Control [general description]

Waiting [state, material flow objects]

##### TrackPitch [SimTalk] - TwoLaneTrack

Sets the Track Pitch , which is the distance between the center lines of the two lanes of the TwoLaneTrack designated by &lt;Path&gt;.

<!-- image -->

Type

Attribute

Syntax

< Path >.TrackPitch:length

Assignment Value

You can assign a value of data type length .

Example

```simtalk
MyTwoLaneTrack.TrackPitch := 5
```

See also

Track Pitch [text box]

Traffic [SimTalk] - TwoLaneTrack

Sets the side of the TwoLaneTrack designated by &lt;Path&gt; on which the bidirectional traffic moves:

Remarks

It looks like this in 2D:

<!-- image -->

It looks like this in 3D:

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.Traffic:string

Assignment Value

You can assign a value of data type string .

You can specify "Right-hand traffic" or "Left-hand traffic" .

Example

MyTwoLaneTrack.traffic := "left-hand traffic"

**See also**

**Right-hand Traffic/Left-hand Traffic**

##### Width [SimTalk] - TwoLaneTrack

Width [SimTalk] - TwoLaneTrack

Sets the width of the TwoLaneTrack designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject , the Width does not affect how the TwoLaneTrack is shown in the Frame in 2D.

Type

Attribute

Syntax

< Path >.Width:length

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
MyTwoLaneTrack.Width := 4
```

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

See also

Width [text box] - TwoLaneTrack

Curve Width

#### FlowControl

