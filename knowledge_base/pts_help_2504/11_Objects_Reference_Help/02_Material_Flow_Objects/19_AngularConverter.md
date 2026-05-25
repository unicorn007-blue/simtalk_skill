### AngularConverter

#### AngularConverter [object]

Use the AngularConverter for changing the conveying direction of the parts from lengthwise to crosswise conveyance and vice versa.

Icon

<!-- image -->

Description

The AngularConverter can accommodate a single part at any one time.

The AngularConverter moves the MU on to its successor within the flow of materials like this:

- The MU moves onto the first leg of the AngularConverter . Once the Booking Point Length has reached the entrance of the AngularConverter , the MU moves along the Entry Length with the Entry Speed until the Booking Point Length reaches the point at which the conveying direction changes. There the MU triggers the Moving Time and changes the conveying direction. At this point in time the MU has to be entirely located on the first leg of the AngularConverter . To allow the first leg to completely accommodate the entering MU , the difference between the MU Length and the Booking Point Length may not be greater than the Entry Length .

The MU Width is then used for all calculations, such as the time until it can exit the object, from here to the exit point.

The notch on the Part in 3D designates its right side.

<!-- image -->

After the MU has reached the point at which the conveying direction changes, it can continue on the AngularConverter like this:

<!-- image -->

<!-- image -->

- After the Moving Time has been used up and the MU has changed its conveying direction, it continues on the second leg of the AngularConverter . The MU drives along the Exit Length with the Exit Speed until the Booking Point Width has reached the exit of the AngularConverter . Once the MU has completely exited the AngularConverter , the Moving Time is triggered anew to return the AngularConverter to its original position. After the Moving Time has passed, the next MU can enter.

To allow the second leg to completely accommodate the leaving MU , the difference between the MU Width and the Booking Point Width may not exceed the Exit Length when the MU turns left. If the MU turns right, the value for the Booking Point Width may not exceed the Exit Length .

<!-- image -->

<!-- image -->

In 3D, you can select different configurations for the AngularConverter on the tab Appearance .

<!-- image -->

To show a tooltip with information about the AngularConverter , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the AngularConverter , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

To add the AngularConverter to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; AngularConverter on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Change the Conveying Direction with the AngularConverter

Video on YouTube

[https://youtu.be/hOvdrDnvXXo?si=HtapSi48BgDSePJA&amp;t=377](https://youtu.be/hOvdrDnvXXo?si=HtapSi48BgDSePJA&t=377)

#### Dialog Box of the AngularConverter

Dialog Box of the AngularConverter

Double-click the icon of the AngularConverter to open its dialog box.

###### Tab Attributes

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Entry Length [text box]

Type in the length of the first leg of the AngularConverter .

<!-- image -->

It covers the distance from the entry point to the point at which the AngularConverter switches the conveying direction.

**Note**

If Transfer Length on the Tab Curve in 2D is active, Plant Simulation adjusts the graphic of the AngularConverter , when you change the Entry Length . If the length cannot be exactly displayed in pixels, Plant Simulation adjusts the length of the graphic. If you need to use the exact length, clear Transfer Length .

<!-- image -->

<!-- image -->

SimTalk

EntryLength [SimTalk]

**Exit Length [text box]**

###### Exit Length [text box]

Type in the length of the second leg of the AngularConverter .

<!-- image -->

It covers the distance from the point at which the AngularConverter switches the conveying direction to the point at which the MU exits the object.

**Note**

If Transfer Length on the Tab Curve in 2D is active, Plant Simulation adjusts the graphic of the AngularConverter , when you change the Exit Length . If the length cannot be exactly displayed in pixels, Plant Simulation adjusts the length of the graphic. If you need to use the exact length, clear Transfer Length .

<!-- image -->

SimTalk

ExitLength [SimTalk]

###### Width [text box] - AngularConverter

Type in the Width of the AngularConverter .

<!-- image -->

**Note**

You can only specify the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

SimTalk

Width [SimTalk] - AngularConverter

**Entry Speed [text box]**

###### Entry Speed [text box]

Type in the speed with which the MUs moves on the AngularConverter from the entry point to the point at which the AngularConverter switches the conveying direction.

<!-- image -->

###### Exit Speed [text box]

Type in the speed with which the MUs moves on the AngularConverter from the point at which the AngularConverter switches the conveying direction to the point at which it exits the object.

<!-- image -->

Automatic Stop [check box] - AngularConverter

To automatically stop the AngularConverter , i.e., to set its current speed to 0 if it does not transport a part, select this check box.

<!-- image -->

This might, for example, be the case if it is empty or if it is blocked because a MU cannot leave it.

When the speed of the AngularConverter is 0, the Energy State changes to Operational .

SimTalk

AutomaticStop [SimTalk] - AngularConverter

Tab Times

Tab Times [AngularConverter]

Define Times as described under the Tab Times .

In addition, the AngularConverter provides the Moving Time .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

Moving Time [text box] - AngularConverter

###### Moving Time [text box] - AngularConverter

Select a distribution for the Moving Time from the drop-down list, and type the values, which that distribution requires, into the text box.

<!-- image -->

Plant Simulation shows these values along the upper border of the tab. You can also select a constant time ( Const ).

The Moving Time is the time it takes the AngularConverter to switch from lengthwise to crosswise conveyance and vice versa.

The Moving Time is used up, when the MU arrives at the corner at which the AngularConverter switches conveyance and again, when it has completely left the AngularConverter to return the AngularConverter to its original position. Only then can another MU move onto the AngularConverter , as it can only accommodate a single MU at any one time.

If you use the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the moving time applies.

<!-- image -->

**SimTalk**

MovingTime [SimTalk] - AngularConverter

MovingTime . Type [SimTalk] - distribution parameter

**Tab Failures**

**Tab Failures**

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can select or enter an Entrance Control , an Exit Control , and a Pull Control .

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

See also

Select Object [for controls]

Entrance Control [general description]

Exit Control [general description]

**Pull Control [general description]**

**Shift Calendar [tab Controls]**

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

**Tab Statistics**

**Tab Statistics**

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

###### Tab Curve [AngularConverter]

As opposed to the regular length-oriented objects, the AngularConverter consists of two straight segments formed by three points, not of a sequence of straight and curved segments. You can apply all of the settings described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object AngularConverter during a simulation run.

- Click the icon of the AngularConverter with the left mouse button and click Edit Icons on the Home ribbon tab.
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

While the AngularConverter transports parts costs accrue which result from the sum of the total investment costs and the total operating costs.

**Note**

The total investment costs only accrue during the Depreciation Period .

If the AngularConverter is empty, the costs remain with the AngularConverter as general costs .

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

#### Methods of the AngularConverter

Methods of the AngularConverter

The AngularConverter provides:

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

#### Read-Only Attributes of the AngularConverter

Read-Only Attributes of the AngularConverter

The AngularConverter provides:

- The read-only attribute IsUp [SimTalk] - AngularConverter .
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Source.Empty

##### IsUp [SimTalk] - AngularConverter

Returns if a MU is located on the exit leg of the AngularConverter designated by &lt;Path&gt; after the Moving Time has elapsed and after the MU has exited while the Moving Time is still running (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsUp → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyAngularConverter.IsUp

#### Attributes of the AngularConverter

\_Attributes of the AngularConverter

The AngularConverter provides:

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
MyAngularConverter.AutomaticStop := false
print MyAngularConverter.Pause
posit := MyStation.Cont.XPos
```

##### AutomaticStop [SimTalk] - AngularConverter

Automatically stops the AngularConverter designated by&lt;Path&gt;. This means that it sets its current speed to 0 if it does not transport a part.

Remarks

This might, for example, be the case if it is empty or if it is blocked because a MU cannot leave it.

If the speed of the AngularConverter is 0, the Energy State changes to operational .

Type

Attribute

Syntax

&lt; Path &gt;.AutomaticStop:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyAngularConverter.AutomaticStop := true

See also

Automatic Stop [check box] - AngularConverter

Operational [energy]

**EntryLength [SimTalk]**

##### EntryLength [SimTalk]

Sets the length of the first leg of the AngularConverter designated by &lt;Path&gt;.

Remarks

The EntryLength covers the distance from the entry point to the point at which the AngularConverter switches the conveying direction.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.EntryLength:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

Example

MyAngularConverter.EntryLength := 2

SimTalk

ExitLength [SimTalk]

**See also**

**Entry Length [text box]**

**EntrySpeed [SimTalk]**

##### EntrySpeed [SimTalk]

Sets the speed with which the MU moves on the AngularConverter designated by &lt;Path&gt; from the entry point to the point at which the AngularConverter switches the conveying direction.

Type

Attribute

Syntax

&lt; Path &gt;.EntrySpeed:speed

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

Example

MyAngularConverter.EntrySpeed := 2

SimTalk

ExitSpeed [SimTalk]

See also

Entry Speed [text box]

##### ExitLength [SimTalk]

Sets the length of the second leg of the AngularConverter designated by &lt;Path&gt;.

Remarks

The ExitLength covers the distance from the point at which the AngularConverter switches the conveying direction to the point at which the MU exits the object.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.ExitLength:length

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type length .

Example

MyAngularConverter.ExitLength := 2

SimTalk

EntryLength [SimTalk]

See also

Exit Length [text box]

**ExitLength [SimTalk]**

##### ExitSpeed [SimTalk]

Sets the speed with which the MU moves on the AngularConverter designated by &lt;Path&gt; from the point at which the AngularConverter switches the conveying direction to the point at which it exits the object.

Type

Attribute

Syntax

&lt; Path &gt;.ExitSpeed:speed

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

Example

MyAngularConverter.ExitSpeed := 2

SimTalk

EntrySpeed [SimTalk]

See also

Exit Speed [text box]

##### MovingTime [SimTalk] - AngularConverter

Sets the time it takes the AngularConverter designated by &lt;Path&gt; to switch from lengthwise to crosswise conveyance and vice versa.

Remarks

The Moving Time is triggered, when the MU arrives at the corner at which the AngularConverter switches conveyance. It is triggered again, when it has exited the AngularConverter altogether to set it back to its original position.

If you use the formula distribution , you can enter a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the moving time applies.

Type

Attribute

Syntax

&lt; Path &gt;.MovingTime:time

Assignment Value

You can assign a value of data type time .

Example

MyAngularConverter.MovingTime := 20

See also

Moving Time [text box] - AngularConverter

Formula [distribution]

Width [SimTalk] - AngularConverter

Sets the Width of the AngularConverter designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject the Width does not affect how the AngularConverter is shown in the Frame in 2D.

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

MyAngularConverter.Width := 4

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

See also

Width [text box] - AngularConverter

Curve Width

