### Turnplate

#### Turnplate [object]

Use the Turnplate for modeling a rotating platform, which rotates the loaded parts and ensures the uniform orientation of the leaving parts.

Icon

<!-- image -->

Description

A typical example is in the package shipping industry where all packages have to be rotated to a uniform direction so that a scanner can automatically read the bar code holding the address information. The Turnplate has a capacity of one, i.e., only one MU can be located on it at any one time. The MU moves onto the Turnplate and the Turnplate starts rotating when the booking point of the MU has reached the center of rotation of the Turnplate . When the rotation is finished, the MU exits the Turnplate . The conveying direction on the Turnplate is unidirectional, i.e., the MU cannot be conveyed forward and then backward.

The length of the MU must not be longer than the Length of the Turnplate itself.

The center of rotation is by default located in the center of the Turnplate . The rotation takes up a certain amount of time. You can type in the rotation time per rotation steps of 90 degrees. If you type in a rotation time of 0, the MU is rotated instantaneous without using up any time at all.

The rotation angle that you type in should be a multiple of 90 degrees. If you type in an angle other than that, Plant Simulation rounds this angle to the next angle that is divisible by 90. You can also type in a value greater than 360 degrees as long as it is divisible by 90. This way the Turnplate can rotate the MU several times to simulate packing machines, such as shrink wrappers, etc. By default, the Turnplate rotates 90 degrees clockwise.

After the turnplate has rotated the MU and it has left it, the Turnplate returns to its starting position.

You can control the rotation animation steps in 2D, with which the Turnplate rotates, with the setting

Animate Every x-th Pixel . If you insert the Turnplate with its icon , the Number of Animation Events

controls these steps.

In 3D, you can select different configurations for the Turnplate on the tab Appearance of the Lengthoriented Objects .

<!-- image -->

To show a tooltip with information about the Turnplate , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Turnplate , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the Turnplate to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; Turnplate on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Align and Shrink-Wrap Parts with the Turnplate

Configure the Turnplate to Rotate the Part According to an Attribute

Video on YouTube

[https://youtu.be/hOvdrDnvXXo?si=Cs5gOF4JB5PBlVma&amp;t=532](https://youtu.be/hOvdrDnvXXo?si=Cs5gOF4JB5PBlVma&t=532)

#### Dialog Box of the Turnplate

Dialog Box of the Turnplate

Double-click the icon of the Turnplate to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

##### Tab Attributes

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Length [text box] - Turnplate

<!-- image -->

<!-- image -->

Type in the Length of the Turnplate .

After you inserted it, Plant Simulation shows its length here. The Turnplate only rotates MUs , which it can accommodate in their entirety, meaning that they are shorter or as long as the value you enter here.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic of the Turnplate if you change the length .

In 3D, you can change the length of the graphic and the anchor points of the Turnplate by clicking Show

Manipulators

on the Edit ribbon tab or by pressing M on the keyboard.

SimTalk

Length [Turnplate] ]

###### Width [text box] - Turnplate

Width [text box] - Turnplate

Type in the Width of the Turnplate .

<!-- image -->

**Note**

You can only type in the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the width in meters.

**SimTalk**

Width [SimTalk] - Turnplate

###### Speed [text box] - Turnplate

Type in the Speed with which the Turnplate conveys the MU while it is located on the plate.

You can also type in -1 for an infinite speed.

SimTalk

Speed [SimTalk] - Turnplate

###### Rotation Time per 90° [text box] - Turnplate

Rotation Time per 90° [text box] - Turnplate

Type in the Time it takes the Turnplate to rotate by 90 degrees.

<!-- image -->

To rotate the MU immediately, without using up any time at all, type in a rotation time of 0 .

SimTalk

RotationTimePer90Degrees [text box] - Turnplate

###### Strategy [drop-down list] - Turnplate

Select the Strategy according to which the Turnplate rotates the part:

- Angle rotates the MU according to the rotation Angle , which you type in.
- MU Attribute rotates the MU according to a built-in or a user-defined attribute of the MU . Click Open List and type in the name of the Attribute of the MU , the Value of the attribute, and the rotation Angle .
- MU Name rotates the MU according to its name. Click Open List and type in the Name of the MU and the rotation Angle .
- Method rotates the MU according to the strategy method . Within this method you have to call the method rotatePart with the rotation angle as parameter. Type the name of the method into the text box Strategy Method .

<!-- image -->

<!-- image -->

<!-- image -->

**Strategy [drop-down list] - Turnplate**

<!-- image -->

SimTalk

Strategy [SimTalk] - Turnplate

See also

Configure the Turnplate to Rotate the Part According to an Attribute

Angle [text box] - Turnplate

Open List [Turnplate]

Strategy Method [Turnplate]

Angle [text box] - Turnplate

Type in the Angle in degrees to which the Turnplate rotates the MU .

The rotation angle should be a multiple of 90. If you type in an angle other than that, Plant Simulation rounds this angle to the next angle that is divisible by 90. You can also type in a value greater than 360 degrees as long as it is divisible by 90. This way the turnplate can rotate the part several times around its own axis to simulate packing machines.

By default, the turnplate rotates the part 90 degrees clockwise. To rotate the part counter-clockwise, type in negative angles.

SimTalk

Angle [SimTalk] - Turnplate

###### Attribute Type [drop-down list] - Turnplate

Select the data type of the attribute that determines the rotation angle by which the Turnplate rotates the part.

<!-- image -->

**SimTalk**

AttributeType [SimTalk] - Turnplate

See also

Strategy [drop-down list] - Turnplate

###### Open List [Turnplate]

To open the rotation angles list for the MUs , click this button.

- For the Strategy &gt; MU Attribute you can type in the name of the Attribute of MU part, the Value of the attribute, and the rotation Angle .
- For the Strategy &gt; MU Name you can type in the Name of the attribute of the MU and the rotation Angle .

<!-- image -->

<!-- image -->

**SimTalk**

setAttributeList [SimTalk] - Turnplate

getAttributeList [SimTalk] - Turnplate

See also

Strategy [drop-down list] - Turnplate

Configure the Turnplate to Rotate the Part According to an Attribute

**Data Held in Tabular Form in Attributes [material flow objects]**

###### Strategy Method [Turnplate]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Strategy Method , which is called as soon as the booking point of the part is located on the center of rotation of the Turnplate for the Strategy &gt; Method .

<!-- image -->

The Strategy Method rotates the MU around the rotation angle which you specify.

Within the Strategy Method you have to call the method rotatePart with the rotation angle as parameter.

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

The default strategy method as a user-defined attribute looks like this:

?.rotatePart(90)

SimTalk

StrategyCtrl [SimTalk] - Turnplate

rotatePart [SimTalk]

See also

Select Object [for controls]

Configure the Turnplate

Strategy [drop-down list] - Turnplate

###### Automatic Stop [check box] - Turnplate

To set the current speed of the Turnplate to 0 when it does not transport a MU , select this check box.

<!-- image -->

This might, for example, be the case if it is empty or if it is blocked when a part cannot leave it.

If the speed of the Turnplate is 0, the Energy State changes to Operational .

SimTalk

AutomaticStop [SimTalk] - Turnplate

##### Tab Times

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Pull Control .

**Note**

Do not use an Exit Control for determining the target of the MU , as an Exit Control will be called only when the MU is ready to exit the Turnplate . This point in time is too late though, as the target has to be determined earlier in time.

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

In addition, you can select the Shift Calendar .

**See also**

Entrance Control [general description]

Exit Control [general description]

Pull Control [general description]

##### Tab Statistics [Turnplate]

Tab Statistics [Turnplate]

Statistics is described under the Tab Statistics .

In addition, the Turnplate collects this statistical value:

| Item English    | Description                                                                                                             | Read-only attribute                              | Item German    |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|----------------|
| Rotation Loaded | Shows the portion of the statistics collection period during which the Turnplate was rotating while transporting a MU . | StatRotationLoadedPor tion [SimTalk] - Turnplate | Drehung belegt |

<!-- image -->

To view the Rotation Time in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

**See also**

Resource Statistics [check box]

Resource Type

<!-- image -->

**Tab Statistics [Turnplate]**

**Tab Curve [Turnplate]**

##### Tab Curve [Turnplate]

As opposed to the regular length-oriented objects, the Turnplate consists of a single segment formed by two points, not of a sequence of straight and curved segments. You can apply all of the settings described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Turnplate during a simulation run.

- Click the icon of the Turnplate with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

**Tab Energy**

##### Tab Energy

Select energy settings for the object on the Tab Energy .

Tab Costs

Select costs settings for the object on the Tab Costs .

While the Turnplate transports MUs costs accrue which result from the sum of the total investment costs and the total operating costs.

Note

The total investment costs only accrue during the Depreciation Period .

If the Turnplate is empty, the costs remain with the Turnplate as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

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

**Methods of the Turnplate**

#### \_Methods of the Turnplate

The Turnplate provides:

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

##### getAttributeList [SimTalk] - Turnplate

Returns the attribute list of the Turnplate designated by &lt;Path&gt;.

**Remarks**

Contains the name of the Attribute of the MU , the Value of the attribute, and the rotation Angle for the Strategy &gt; MU Attribute .

<!-- image -->

Contains the Name of the attribute of the part and the rotation Angle for the Strategy &gt; MU Name .

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getAttributeList(Attributes:table)

Parameter

The parameter Attributes of data type table designates the name of the list.

Example

MyTurnplate.getAttributeList(MyAttributesList)

SimTalk

setAttributeList [SimTalk] - Turnplate

See also

Strategy [drop-down list] - Turnplate

Open List [Turnplate]

Data Held in Tabular Form in Attributes [material flow objects]

rotatePart [SimTalk]

Rotates the MU on the Turnplate designed by &lt;Path&gt; by the specified angle.

Type

Method

Syntax

&lt; Path &gt;.rotatePart(Angle:integer)

Parameter

The parameter Angle of data type integer designates the angle.

This angle has to be a positive or a negative multiple of 90.

Example

?.rotatePart(180)

See also

Strategy Method [Turnplate]

setAttributeList [SimTalk] - Turnplate

Sets the attribute list of the Turnplate designated by &lt;Path&gt;.

The attribute list sets the MU that leaves the Turnplate .

**Remarks**

For the Strategy &gt; MU Attribute you can specify the name of the Attribute of the MU , its Value and the rotation Angle .

<!-- image -->

For the Strategy &gt; MU Name you can specify the Name of the MU and the rotation Angle .

<!-- image -->

Type

Method

**Syntax**

&lt; Path &gt;.setAttributeList(Attributes:table)

Parameter

The parameter Attributes of data type table designates the path to a list or a variable of the same data type.

Plant Simulation then copies the contents of the passed list to the attribute list of the Turnplate.

Example

MyTurnplate.setAttributeList(MyAttributes)

SimTalk

getAttributeList [SimTalk] - Turnplate

See also

Strategy [drop-down list] - Turnplate

Open List [Turnplate]

Data Held in Tabular Form in Attributes [material flow objects]

#### Read-Only Attributes of the Turnplate

\_Read-Only Attributes of the Turnplate

The Turnplate provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Turnplate.StatRotationLoadedPortion

##### StatRotationLoadedPortion [SimTalk] - Turnplate

Returns the portion of the statistics collection period during which the Turnplate designated by &lt;Path&gt; was rotating while a MU was located on the plate.

Syntax

&lt; Path &gt;.StatRotationLoadedPortion → real

Return Value

The return value has the data type real .

Example

print MyTurnplate.StatRotationLoadedPortion

See also

Tab Statistics [Turnplate]

Statistics report , Rotation Time

##### StatRotationLoadedTime [SimTalk] - Turnplate

Returns the total time during which the Turnplate designated by &lt;Path&gt; was rotating while a MU was located on the plate.

Syntax

< Path >.StatRotationLoadedTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyTurnplate.StatRotationLoadedTime
```

See also

Statistics report , Rotation Time

#### Attributes of the Turnplate

\_Attributes of the Turnplate

The Turnplate provides:

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
MyTurnplate.angle := 180
print MyTurnplate.angle
posit := MyStation.Cont.XPos
```

##### Angle [SimTalk] - Turnplate

Angle [SimTalk] - Turnplate

Sets the rotation angle in degrees to which the Turnplate designated by &lt;Path&gt; rotates the MU .

Remarks

The rotation angle should be a multiple of 90 degrees. If you specify an angle other than that, Plant Simulation rounds this angle to the next angle that is divisible by 90.

You can also specify a value greater than 360 degrees as long as it is divisible by 90. This way the Turnplate can rotate the MU several times to simulate packing machines.

By default the Turnplate rotates 90 degrees clockwise. To rotate counter-clockwise, specify negative angles.

Type

Attribute

Syntax

```simtalk
< Path >.Angle:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyTurnplate.Angle := 90
```

See also

Angle [text box] - Turnplate AttributeType [SimTalk] - Turnplate Sets the Attribute Type of the Turnplate designated by &lt;Path&gt;.

Remarks

AttributeType applies to the Strategy &gt; MU Attribute .

Type

Attribute

Syntax

```simtalk
< Path >.AttributeType:string
```

**Assignment Value**

You can assign a value of data type string .

<!-- image -->

**Example**

```simtalk
MyTurnplate.AttributeType := "String"
```

See also

Attribute Type [drop-down list] - Turnplate

Strategy [drop-down list] - Turnplate

##### AutomaticStop [SimTalk] - Turnplate

Automatically stops the Turnplate designated by&lt;Path&gt;. This means that it sets the current speed to 0 when it does not transport a MU .

Remarks

This might, for example, be the case if it is empty or if it is blocked when a MU cannot leave it.

If the speed of the Turnplate is 0, its energy state changes to operational .

Type

Attribute

Syntax

&lt; Path &gt;.AutomaticStop:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTurnplate.AutomaticStop := true

See also

Automatic Stop [check box] - Turnplate

Operational [energy]

**Length [Turnplate]**

##### Length [Turnplate]

Sets the length of the Turnplate designated by &lt;Path&gt;.

Remarks

The Turnplate only rotates MUs , which it can accommodate in their entirety, meaning that they are shorter or as long as the value you enter here.

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
MyTurnplate.Length := 2.0m
```

See also

Length [text box] - Turnplate RotationTimePer90Degrees [text box] - Turnplate Sets the time it takes the Turnplate designated by &lt;Path&gt; to rotate by a rotation step of 90 degrees.

Remarks

Specify a rotation time of 0 to rotate the MU immediately, without using up any time at all.

Type

Attribute

Syntax

&lt; Path &gt;.RotationTimePer90Degrees:time

Assignment Value

You can assign a value of data type time .

Example

MyTurnplate.RotationTimePer90Degrees := 0.75

See also

Rotation Time per 90° [text box] - Turnplate

**Speed [SimTalk] - Turnplate**

##### Speed [SimTalk] - Turnplate

Sets the speed, with which the Turnplate designated by &lt;Path&gt; transports the MU , while it is located on the plate.

Remarks

Specify -1 for an infinite speed.

Type

Attribute

Syntax

< Path >.Speed:speed

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the number, without a separating blank space, for example 100km or 100.5km .

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
MyTurnplate.Speed := 1.5
```

**See also**

Speed [text box] - Turnplate

##### Strategy [SimTalk] - Turnplate

Strategy [SimTalk] - Turnplate

Sets the strategy according to which the Turnplate designated by &lt;Path&gt; rotates the MU .

Type

Attribute

Syntax

&lt; Path &gt;.Strategy:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Angle" rotates the MU according to the rotation Angle you specify.
- "MU Attribute" rotates the MU according to a built-in or a user-defined attribute of the part.
- "MU Name" rotates the MU according to its name.
- "Method" rotates the MU according to the strategy method .

Within this method you have to call the method rotatePart with the rotation angle as parameter.

**Example**

MyTurnplate.Strategy := "MU Attribute"

SimTalk

Angle [SimTalk] - Turnplate

rotatePart [SimTalk]

See also

Strategy [drop-down list] - Turnplate , drop-down list

Angle [text box] - Turnplate

##### StrategyCtrl [SimTalk] - Turnplate

Designates a Method object of the object designated by &lt;Path&gt;. Type in the source code that determines the rotation angle around which the Turnplate designated by &lt;Path&gt; rotates the MU .

Remarks

The Plant Simulation runs the Method for the Strategy Method as soon as the booking point of the MU is located on the center of rotation of the Turnplate . Within this method you have to call the method rotatePart with the rotation angle as parameter.

The default strategy method looks like this:

?.rotatePart(90)

Type

Attribute

Syntax

< Path >.StrategyCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
var rotAngle: integer
if @.typeOf(~.MyPart)           // rotates the part
	rotAngle := 90
else
	if @.typeOf(~.MyPallet)      // rotates the pallet
		rotAngle := -(4 * 360)  // minus (-) designates counterclockwise
	end
end
?.rotatePart(rotAngle)
MyTurnplate.StrategyCtrl := &myRotationStrategy
```

SimTalk

rotatePart [SimTalk]

**See also**

**Strategy Method [Turnplate]**

Width [SimTalk] - Turnplate

Sets the width of the Turnplate designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject , the Width does not affect how the Turnplate is shown in the Frame in 2D.

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

MyTurnplate.Width := 2 // meters

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

