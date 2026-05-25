### Turntable

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

See also

Width [text box] - Converter

Curve Width

**Turntable**

#### Turntable [object]

Use the Turntable for modeling a rotating platform, which moves the part onto one of several connected material flow objects and/or turns it around.

Icon

<!-- image -->

Description

The Turntable has a capacity of one, i.e. only one part can be located on it at any one time. The length of the MU must not be longer than the Length of the Turntable itself.

The Turntable moves the part on to its successors within the flow of materials like this:

- The MU arrives at the exit of the predecessor. It notifies the turntable that it wants to be rotated.
- The turntable then determines if it accepts the MU for rotating it or not.
- Without a Pull Control , the turntable will be notified that a MU wants to be rotated, and it accepts it.
- If you entered a Pull Control , the turntable executes it, and when the MU is selected, it will be rotated.
- The turntable rotates to the respective predecessor, and the MU moves onto the turntable and drives onto it.
- Once one of the conditions below is met, the turntable looks for the target station and starts rotating toward it:
- If the MU has completely entered the turntable.

- If the MU has reached the rotation point on the table.
- If the part is located in the center of the turntable, i.e., when both ends of the part have the same distance from the ends of the turntable.
- If you want the turntable to not rotate automatically, but only if the MU has reached a user-defined sensor, select User-defined with Sensor . In the Sensor Control , you have to tell the turntable to call the method setDestination .
- For determining the target station, the turntable either uses its default exit strategies or the Target Control . Within this Method you set the target station with the method setDestination .

**Note**

Do not use an Exit Control for determining the target of the MU , as an Exit Control will be called only when the MU is ready to exit the Turntable . This point in time is too late though, as the target has to be determined earlier in time.

- Then the turntable rotates to the target and MU moves on, once the turntable has reached the final position of the rotation. Only then a new MU can move onto the Turntable . The Turntable has a Capacity of 1.

**Note**

If an object, from which/onto which the MU is to be moved, does not exist in the respective angle table, the Turntable checks the Exit Angle Table for an entering MU or the Entry Angle Table for a leaving MU , if the object exists there and uses that angle. If the object is not contained in the respective table, the Turntable uses the angle from the layout in the Frame .

You can control the rotation animation steps, with which the Turntable rotates in 2D, with the setting

<!-- image -->

Animate Every x-th Pixel . If you insert the Turntable with its icon Events controls these steps.

, the Number of Animation

In 3D, you can select different configurations for the Turntable on the tab Appearance of the Lengthoriented Objects .

<!-- image -->

In 3D an animatable object with the Velocity of 0 does not rotate with the Turntable when the Turntable rotates. This applies if the insertion position of the animatable object is located on the animation rotation axis of the Turntable . This is the case if the insertion point is exactly located on the animation rotation center or is reachable from there along the animation rotation axis without a sideways deviation.

This resembles a real Turntable with a fixed base and a rotary table.

<!-- image -->

To show a tooltip with information about the Turntable , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Turntable , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

<!-- image -->

To add the Turntable to your simulation model, click MaterialFlow &gt; Turntable on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Move Parts On with the Turntable

Video on YouTube

[https://youtu.be/hOvdrDnvXXo?si=Cs5gOF4JB5PBlVma&amp;t=532](https://youtu.be/hOvdrDnvXXo?si=Cs5gOF4JB5PBlVma&t=532)

#### Dialog Box of the Turntable

Dialog Box of the Turntable

Double-click the icon of the Turntable to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Length [text box] - Turntable

Length [text box] - Turntable

Type in the Length of the Turntable .

<!-- image -->

After you inserted it, Plant Simulation shows its length here. The Turntable only rotates parts, which are shorter or as long as the value, which you enter here.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the length of a Turntable which only consists of a single straight segment.

In 3D, you can change the length of the graphic and the anchor points of the Turntable by clicking Show

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

SimTalk

Length [SimTalk] - Turntable

See also

OccupiedLength [SimTalk] - Conveyor

###### Width [text box] - Turntable

Type in the Width of the Turntable .

<!-- image -->

**Note**

You can only type in the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

In 3D, you can change the width of the graphic and the anchor points of the Turntable by clicking Show

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

SimTalk

Width [SimTalk] - Turntable

**Rotation Point [text box]**

###### Rotation Point [text box]

Type in the Rotation Point , i.e., the position of the fulcrum around which the Turntable rotates.

<!-- image -->

You can enter a type in between 0 and the length of the Turntable . 0 designates the point at which you start inserting the Turntable .

The center of rotation is the fulcrum around which the table rotates.

The start point is the point which you click, when you start inserting the Turntable .

The end point is the point which you click, when you finish inserting the Turntable . The circle in the screenshot below shows all points which the turntable can reach with its end point, when it rotates around the fulcrum.

<!-- image -->

**SimTalk**

RotationPoint [SimTalk]

###### Conveyor Speed [text box]

Type in the Speed with which the Turntable transports the MU , while it is located on the table.

SimTalk

Speed [SimTalk] - Turntable

See also

Velocity [joint]

###### Rotation Time per 90° [text box] - Turntable

Rotation Time per 90° [text box] - Turntable

Type in the Time which it takes the Turntable to rotate by 90 degrees.

SimTalk

RotationTimePer90Degrees [SimTalk] - Turntable

###### Rotate When [drop-down list] - Turntable

Select, when the Turntable rotates toward its target object:

<!-- image -->

- When the MU has completely entered the Turntable .
- When the MU has reached the rotation point/the fulcrum on the table.
- When the MU is located in the center of the Turntable , i.e., when both ends of the MU have the same distance from the edges of the turntable.
- If you want the Turntable to not rotate automatically, but only when the MU has reached a user-defined sensor, select User-defined with Sensor . In the Sensor Control , you have to tell the Turntable to call the method setDestination .

**SimTalk**

RotateWhen [SimTalk]

###### Go to Default Position [check box] - Turntable

To rotate the Turntable back to its Default Position , when the MU has left the Turntable and when no new MU is ready to be rotated, select this check box.

<!-- image -->

Default Angle [text box] - Turntable

Type in the Angle in degrees to which the Turntable rotates, when you selected Go to Default Position .

The default position is located at this angle. If you would like the Turntable to rotate to the side on which the start point is located, add 180 degrees to this angle.

SimTalk

DefaultAngle [SimTalk] - Turntable

See also

Go to Default Position [check box] - Turntable

GoToDefaultPosition [SimTalk] - Turntable

###### MU Leaves Backwards Depends On

Type in the name of the user-defined attribute of the MU , which triggers its rotation, so that it exits the table driving backward.

<!-- image -->

This user-defined attribute can be an attribute of data type boolean or a Method which returns a value of data type boolean .

MU leaves Backwards Depends On will only be evaluated, when you select Any as the side in the Exit Angle Table .

<!-- image -->

SimTalk

##### MURotationAttribute [SimTalk]

See also

Exit Angle Table

###### Entry Angle Table

To open the table of the Entry Angles at which the MUs move onto the Turntable , click this button.

<!-- image -->

You can view or fine-tune these settings:

- The number of the Predecessor .
- The name of the Predecessor .
- The Angle at which the Connector from this predecessor connects to the Turntable .
- At Which Side it turns toward the predecessor.
- If you select Start Point , the Turntable turns with the side, at which you started inserting the Turntable , toward this predecessor.
- If you select End Point , the Turntable turns with the side, at which you finished inserting the Turntable , toward this predecessor.
- If you select Any , the Turntable computes the smallest angle and turns with this computed side toward this predecessor.

<!-- image -->

The figure illustrates the position of the Entry Angle depending on the insertion direction of the Turntable .

<!-- image -->

If you want the Turntable to compute the angles at which you connected it to its predecessors, click it with the right mouse button and select Calculate Angles .

<!-- image -->

**SimTalk**

setEntryAngles [SimTalk]

getEntryAngles [SimTalk]

calculateAngles [SimTalk] - Turntable

###### Exit Angle Table

To open the table of the Exit Angles at which the MUs leave the Turntable , click this button.

<!-- image -->

You can view or fine-tune these settings:

<!-- image -->

- The number of the Successor .
- The name of the Successor .
- The Angle at which the Connector from the Turntable connects toward this successor.
- At Which Side it turns toward the successor.
- If you select Start Point , the Turntable turns with the side, at which you started inserting the Turntable toward this successor.
- If you select End Point , the Turntable turns with the side, at which you finished inserting the Turntable toward this successor.
- If you select Any , the Turntable computes the smallest angle and turns with this computed side toward this successor. With this setting the MU can leave backward or forward, depending on the side which can be reached with the smallest angle.
- If you select MU keeps Direction , the Turntable turns this side of the Turntable toward this successor which makes the MU keep its direction.
- If you select MU leaves backward , the Turntable turns this side of the Turntable toward this successor so that the Turntable turns the MU around, and it leaves moving backward. Compare MU Leaves Backwards Depends On .

<!-- image -->

The figure illustrates the position of the Exit Angle depending on the insertion direction of the Turntable .

<!-- image -->

If you want the Turntable to compute the angles at which you connected it to its successors, click it with the right mouse button and select Calculate Angles .

<!-- image -->

SimTalk setExitAngles [SimTalk] getExitAngles [SimTalk] calculateAngles [SimTalk] - Turntable

**Automatic Stop [check box] - Turntable**

###### Automatic Stop [check box] - Turntable

To set the current speed of the Turntable to 0 if it does not transport a part, select this check box.

<!-- image -->

This might, for example, be the case if it is empty or if it is blocked when a part cannot leave it.

If the speed of the Turntable is 0, the Energy State changes to Operational .

SimTalk

AutomaticStop [SimTalk] - Turntable

##### Tab Times [Turntable]

Define Times as described under the Tab Times .

Note

The Turntable does not provide the Cycle Time .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Recovery Time Starts

**Tab Failures**

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

###### Tab Controls [Turntable]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Set-up Control .

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

**Note**

Do not use an Exit Control for determining the target of the MU , as an Exit Control will be called only when the MU is ready to exit the Turntable . This point in time is too late though, as the target has to be determined earlier in time.

In addition, you can also select the Shift Calendar .

See also

Entrance Control [general description]

Exit Control [general description]

Pull Control [general description]

Target Control [Turntable]

**Target Control [Turntable]**

###### Target Control [Turntable]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Target Control ,which is called as soon as the MU has completely moved onto the Turntable or has reached the center of rotation. As opposed to the Exit Control , the MU is not ready to exit the object yet. .

<!-- image -->

You have to set the target object with the method setDestination .

**Note**

Do not use an Exit Control for determining the target of the MU , as an Exit Control will be called only when the MU is ready to exit the Turntable . This point in time is too late though, as the target has to be determined earlier in time.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

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

The standard target control looks like this:

<!-- image -->

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics [Turntable]

Statistics is described under the Tab Statistics .

In addition, the Turntable collects these statistical values:

| Item English    | Description                                                                                                                     | Read-only attribute                              | Item German    |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|----------------|
| Rotation Empty  | Shows the portion of the statistics collection period during which the object was rotating Empty , i.e., without moving a part. | StatRotationEmptyPort ion [SimTalk] - Turntable  | Drehung leer   |
| Rotation Loaded | Shows the portion of the statistics collection period during which the object was rotating while moving a part.                 | StatRotationLoadedPor tion [SimTalk] - Turntable | Drehung belegt |

<!-- image -->

To view Rotation Time in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

**Tab Statistics [Turntable]**

**See also**

Resource Statistics [check box]

Resource Type

<!-- image -->

##### Tab Curve [Turntable]

As opposed to the regular length-oriented objects, the Turntable consists of a single straight segment formed by two points, not of a sequence of straight and curved segments. You can apply all of the settings described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Tab Curve [Turntable]**

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Turntable during a simulation run.

- Click the icon of the Turntable with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Tab Costs

Select costs settings for the object on the Tab Costs .

While the Turntable transports MUs costs accrue which result from the sum of the total investment costs and the total operating costs.

Note

The total investment costs only accrue during the Depreciation Period .

If the Turntable is empty, the costs remain with the Turntable as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Backward Blocking List    |
|--------------------------------------------|---------------------------|
| Show Statistics Report [on View menu]      | Exit Blocking List        |
| Show Attributes and Methods [on View menu] | Associated Lockout Zones  |
| Contents [material flow objects]           | Associated Shift Calendar |
| Forward Blocking List                      |                           |

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

**Methods of the Turntable**

#### \_Methods of the Turntable

The Turntable provides:

- The methods listed in the table of contents to the left.
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

##### calculateAngles [SimTalk] - Turntable

Computes the angles at which you connected the Turntable designated by &lt;Path&gt; with its predecessor and with its successor in the Frame .

Remarks

The Turntable then enters the Entry Angles into the Entry Angles Table and the Exit Angles into the Exit Angles Table .

Type

Method

Syntax

&lt; Path &gt;.calculateAngles

**Example**

MyTurntable.calculateAngles SimTalk getEntryAngles [SimTalk] getExitAngles [SimTalk] setEntryAngles [SimTalk] setExitAngles [SimTalk] See also Calculate Angles Entry Angle Table Exit Angle Table getDestination [SimTalk] - Turntable Returns the target object to which the Turntable designated by &lt;Path&gt; moves the MU .

Remarks

You will usually use getDestination in the Target Control / TargetCtrl .

Type

Method

Syntax

&lt; Path &gt;.getDestination → object

Return Value

The return value has the data type object .

Example

MyTurntable := ?.getDestination

SimTalk

setDestination [SimTalk] - Turntable

TargetCtrl [SimTalk] - Turntable

See also

Target Control [Turntable]

##### getEntryAngles [SimTalk]

getEntryAngles [SimTalk]

Returns the Entry Angle Table of the Turntable designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

&lt; Path &gt;.getEntryAngles(EntryAnglesTable:table)

**Parameter**

The parameter EntryAnglesTable of data type table designates the name of the table into which the Method writes the entry angles.

The table contains the number of the Predecessor , its Name , at which Angle the Connector from this predecessor connects to the Turntable , and Which Side turns toward the predecessor.

<!-- image -->

**Example**

MyTurntable.getEntryAngles(myEntryAngleTable)

**SimTalk**

setEntryAngles [SimTalk]

calculateAngles [SimTalk] - Turntable

**See also**

**Entry Angle Table**

##### getExitAngles [SimTalk]

getExitAngles [SimTalk]

Returns the Exit Angle Table of the Turntable designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

&lt; Path &gt;.getExitAngles(ExitAnglesTable:table)

Parameter

The parameter ExitAnglesTable of data type table designates the name of the table.

The table contains the number of the Successor , its Name , at which Angle the Connector from the Turntable connects to this successor, and Which Side turns toward the successor.

<!-- image -->

**Example**

MyTurntable.getExitAngles(myExitAngleTable)

SimTalk

setExitAngles [SimTalk]

calculateAngles [SimTalk] - Turntable

**See also**

**Exit Angle Table**

goToAngle [SimTalk]

Sets the angle to which the side of the end point of the Turntable designated by &lt;Path&gt; rotates.

Remarks

Only applies, if no MU is located on it and if no MU is waiting for it.

Type

Method

Syntax

&lt; Path &gt;.goToAngle(Angle:real)

Parameter

The parameter Angle of data type real designates the angle.

Example

?.goToAngle(45)

##### goToAngle [SimTalk]

setDestination [SimTalk] - Turntable

```simtalk
Sets the target object to which the Turntable designated by <Path> moves the MU . Remarks You will usually use setDestination in the Target Control / TargetCtrl . Type Method Syntax
< Path >.setDestination(Destination:object)
```

Parameter

The parameter Destination of data type object designates the target object.

Example

```simtalk
if @.Name = "PartA" // the identifier "@" points to the MU, the part in our case, // which triggers the call of the current method in a control
	?.setDestination(ConveyorPartA) // the identifier "?" points to the object which // calls the method, the turntable in our case
else
	?.setDestination(ConveyorPartB)
end
```

SimTalk

getDestination [SimTalk] - Turntable

TargetCtrl [SimTalk] - Turntable

See also

Target Control [Turntable]

##### setEntryAngles [SimTalk]

setEntryAngles [SimTalk]

Sets the name of the Entry Angle Table that is going to be assigned to the Turntable designated by &lt;Path&gt;.

Type

Method

Syntax

<!-- image -->

Parameter

The parameter EntryAnglesTable of data type table designates the name of the table.

It contains the number of the Predecessor , the Name of the Predecessor , the Angle at which the Connector from this predecessor connects to the Turntable , and at Which Side it turns toward the predecessor.

<!-- image -->

The figure illustrates the position of the Entry Angle depending on the insertion direction of the Turntable .

<!-- image -->

**Example**

MyTurntable.setEntryAngles(myEntryAngleTable)

SimTalk

getEntryAngles [SimTalk]

calculateAngles [SimTalk] - Turntable

See also

Entry Angle Table

##### setExitAngles [SimTalk]

setExitAngles [SimTalk]

Sets the name of the Exit Angle Table that is going to be assigned to the Turntable designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setExitAngles(ExitAnglesTable:table)

Parameter

The parameter ExitAnglesTable of data type table designates the name of the table.

It contains the number of the Successor , the Name of the Successor , the Angle the Connector from the Turntable connects to this successor, and at Which Side it turns toward the successor:

<!-- image -->

The figure illustrates the position of the Exit Angle depending on the insertion direction of the Turntable .

<!-- image -->

**Example**

MyTurntable.setExitAngles(myExitAngleTable)

SimTalk

getExitAngles [SimTalk]

calculateAngles [SimTalk] - Turntable

See also

Exit Angle Table

stopMU [SimTalk]

Stops the MU while the Turntable designated by &lt;Path&gt; is still rotating.

Remarks

When the rotation is finished, the MU automatically moves again.

Use stopMU to stop the MU before it reaches the end of the table to prevent collisions for example. You will mostly use stopMU in a sensor control.

Type

Method

Syntax

&lt; Path &gt;.stopMU

Example

MyTurntable.stopMU

##### stopMU [SimTalk]

#### Read-Only Attributes of the Turntable

\_Read-Only Attributes of the Turntable

The Turntable provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Turntable.StatRotationEmptyPortion

##### CurrentDestinationAngle [SimTalk]

Returns the destination angle to which the Turntable designated by &lt;Path&gt; rotates at the moment.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentDestinationAngle → real

Return Value

The return value has the data type real .

Example

print MyTurntable.CurrentDestinationAngle // might return 74.36 for example StatRotationEmptyPortion [SimTalk] - Turntable Returns the portion of the statistics collection period during which the Turntable designated by &lt;Path&gt; was rotating empty without a MU being located on the table.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRotationEmptyPortion → real

Return Value

The return value has the data type real .

Example

print MyTurntable.StatRotationEmptyPortion

See also

Tab Statistics [Turnplate]

Statistics report , Rotation Time

Empty [state, material flow objects]

StatRotationEmptyTime [SimTalk] - Turntable

Returns the total time during which the Turntable designated by &lt;Path&gt; was rotating empty , i.e., without a MU being located on the table.

Type

Read-only Attribute

Syntax

< Path >.StatRotationEmptyTime → time

Return Value

The return value has the data type time .

Example

print MyTurntable.StatRotationEmptyTime

See also

Statistics report , Rotation Time

Empty [state, material flow objects]

##### StatRotationLoadedPortion [SimTalk] - Turntable

Returns the portion of the statistics collection period during which the Turntable designated by &lt;Path&gt; was rotating with a MU being located on the table.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRotationEmptyPortion → real

Return Value

The return value has the data type real .

Example

print MyTurntable.StatRotationEmptyPortion

See also

Tab Statistics [Turnplate]

Statistics report , Rotation Time StatRotationLoadedTime [SimTalk] - Turntable Returns the total time during which the Turntable designated by &lt;Path&gt; was rotating with a MU being located on the table.

Type

Read-only attribute

Syntax

< Path >.StatRotationLoadedTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyTurntable.StatRotationLoadedTime
```

See also

Statistics report , Rotation Time

##### Attributes of the Turntable

\_Attributes of the Turntable

The Turntable provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Curved Objects in 2D .
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTurntable.GoToDefaultPosition := false
print MyTurntable.GoToDefaultPosition
posit := MyStation.Cont.XPos
```

##### AutomaticStop [SimTalk] - Turntable

Automatically stops the Turntable designated by&lt;Path&gt;. This means that it sets the current speed to 0 if it does not transport a MU . This might, for example, be the case if it is empty or if it is blocked because a MU cannot leave it.

Remarks

If the speed of the Turntable is 0, the Energy State changes to operational .

Type

Attribute

Syntax

```simtalk
< Path >.AutomaticStop:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTurntable.AutomaticStop := true
```

See also

Automatic Stop [check box] - Turntable

Operational [energy]

##### DefaultAngle [SimTalk] - Turntable

Sets the rotation angle in degrees to which the side of the end point of the Turntable designated by &lt;Path&gt; rotates.

Remarks

DefaultAngle applies when you set Go to Default Position / GoToDefaultPosition to true .

To rotate the Turntable to the side on which the start point is located, add 180° to this angle.

Type

Attribute

Syntax

&lt; Path &gt;.DefaultAngle:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyTurntable.DefaultAngle := 5
```

SimTalk

GoToDefaultPosition [SimTalk] - PickAndPlace

See also

Default Angle [text box] - Turntable

Go to Default Position [check box] - Turntable GoToDefaultPosition [SimTalk] - Turntable Returns the Turntable designated by &lt;Path&gt; to its default position ( true ) or not ( false ).

Remarks

GoToDefaultPosition applies when the part has left the Turntable and if no new part is ready to be rotated.

**Note**

If you set the attribute to true , the Turntable uses the attribute DefaultAngle , when you reset the model.

The attribute DefaultAngle sets the actual angle.

Type

Attribute

Syntax

&lt; Path &gt;.GoToDefaultPosition:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTurntable.GoToDefaultPosition := true

SimTalk

DefaultAngle [SimTalk] - Turntable

See also

Go to Default Position [check box] - Turntable

Default Angle [text box] - Turntable Length [SimTalk] - Turntable Sets the Length of the Turntable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Length:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

MyTurntable.Length := 10.0m

See also

Length [text box] - Turntable MURotationAttribute [SimTalk]

Sets name of the user-defined attribute of the MU which triggers its rotation on the Turntable designated by &lt;Path&gt;.

Remarks

MURotationAttribute can be an attribute of data type boolean or a Method , which returns a value of data type boolean . MURotationAttribute will only be evaluated, when you select Any as the Side in the Exit Angle Table .

Type

Attribute

Syntax

&lt; Path &gt;.MURotationAttribute:string

Assignment Value

You can assign a value of data type string .

Example

MyTurntable.MURotationAttribute := "MyRotationAttribute"

See also

Exit Angle Table

MU Leaves Backwards Depends On

##### RotateWhen [SimTalk]

Sets, when the Turntable designated by &lt;Path&gt; rotates toward it target station.

Type

Attribute

Syntax

&lt; Path &gt;.RotateWhen:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Completely entered" , i.e., if the MU has completely entered the Turntable .
- "Rotation point reached" , i.e., if the MU has reached the center of rotation on the table.
- "Centered" , i.e., if both ends of the MU have the same distance from the ends of the turntable.
- "User-defined with Sensor" . Here the Turntable does not rotate automatically, but only when the MU has reached a user-defined sensor. In the Sensor Control , you have to tell the Turntable to call the method setDestination

**Example**

MyTurntable.RotateWhen := "completely entered"

SimTalk

setDestination [SimTalk] - Turntable

See also

Strategy [drop-down list] - Turnplate

Rotation Point [text box]

##### RotationPoint [SimTalk]

RotationPoint [SimTalk]

Sets the position of the point around which the Turntable designated by &lt;Path&gt; rotates.

Type

Attribute

Syntax

< Path >.RotationPoint:length

Assignment Value

You can assign a value of data type length .

You can specify a value between 0 and the length of the Turntable . 0 designates the point at which you start inserting the Turntable .

Example

```simtalk
MyTurntable.RotationPoint := 4
```

See also

Rotation Point [text box]

##### RotationTimePer90Degrees [SimTalk] - Turntable

Sets the time it takes the Turntable designated by &lt;Path&gt; to rotate by 90 degrees.

Type

Attribute

Syntax

&lt; Path &gt;.RotationTimePer90Degrees:time

Assignment Value

You can assign a value of data type time .

Example

MyTurntable.RotationTimePer90Degrees := 2

See also

Rotation Time per 90° [text box] - Turntable

##### Speed [SimTalk] - Turntable

Speed [SimTalk] - Turntable

Sets the speed, with which the Turntable designated by &lt;Path&gt; rotates.

Type

Attribute

Syntax

**&lt; Path &gt;.Speed:speed**

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

Specify -1 for an infinite speed.

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the number, without a separating blank space, for example 10mps or 10.5kmps .

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**Note**

In SimTalk 2.0 you can enter the unit s for seconds . Enter the unit s directly after the number, without a separating blank space. Entering the unit sometimes is necessary to make sure that the computed expression has the correct data type.

```simtalk
var x : length := 10m
var s : speed := x / 2s   // Beware: x/2 would have the wrong unit, m instead of m/s
```

**Example**

```simtalk
MyTurntable.Speed := 1.5
```

**See also**

Conveyor Speed [text box]

##### TargetCtrl [SimTalk] - Turntable

TargetCtrl [SimTalk] - Turntable

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

In the Target Control you determine the successor to which the Turntable designated by &lt;Path&gt; moves the MU .

As opposed to the Exit Control , the MU is not ready to exit the object yet. You have to set the target object in the method setDestination .

Plant Simulation runs the Method as soon as the MU has completely moved onto the Turntable or has reached the center of rotation.

Type

Attribute

Syntax

< Path >.TargetCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
if @.Name = "PartA" // the identifier "@" points to the MU, the part in our case, // which triggers the call of the current method in a control
	?.setDestination(ConveyorPartA) // the identifier "?" points to the object which // calls the method, the turntable in our case
else
	?.setDestination(ConveyorPartB)
end
MyTurntable.TargetCtrl := &myTargetControl
```

SimTalk

setDestination [SimTalk] - Turntable

**See also**

**Target Control [Turntable]**

##### Width [SimTalk] - Turntable

Width [SimTalk] - Turntable

Sets the width of the Turntable designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject , the Width does not affect how the Turntable is shown in the Frame in 2D.

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

Type in the unit directly after the values, without a separating blank space, for example 5m or 5.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyTurntable.Width := 2 // meters
```

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

See also

Width [text box] - Turntable

Curve Width

