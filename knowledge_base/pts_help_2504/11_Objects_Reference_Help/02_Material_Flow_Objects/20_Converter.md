### Converter

#### Converter [object]

Use the Converter for conveying a part either straight through or for lifting it onto a laterally moving transport level and then conveying it to the left or right-hand side.

Icon

<!-- image -->

Description

Use the Converter to model materials handling equipment. If the MU moves onto the Converter it either passes straight through in the conveying direction or it is, for example, lifted onto a laterally moving transport level by a lifting mechanism and then conveyed laterally to the left or laterally to the right.

If the part enters on side 1 or 3, straight means that the part keeps its conveying direction and exits on the opposite side. The insertion direction for this lateral movement is from side 3 to side 1 when the insertion direction of the Converter is from left to right, i.e., up to down.

The Converter can only be connected to a single object per side. The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

<!-- image -->

As long as MUs are only conveyed in one direction, the Converter can accommodate any number of MUs . If the MU is to change its conveying direction, the Converter can only lift and transport a single MU . MUs can arrive from all sides and be conveyed to all sides.

You can determine the side to which the Converter conveys the MU in the Strategy Method . The destination objects can be switched to the respective conveying direction at the same time. You can also select the conveying Strategy according to which the Converter conveys the MUs . The preferred direction is the direction in which you inserted the Converter . It then conveys the MUs without any time delay in this direction. If a MU leaves the preferred direction, it has to move onto the Converter , is then lifted, while the Moving Time elapses, and can then exit on either side.

After it conveyed a MU to the side, the Converter has to be lowered back into its default position, before it can convey the next part. You can specify the lifting time and the lowering time of the Converter , i.e., the Moving Time .

When you connect the Converter with its predecessor or successor, you can determine with the mouse at which side of the Converter the Connector docks. To do so, click the left side, the bottom side, the top, or the right side of the Converter . You can also set the side with the method connect of the Connector .

<!-- image -->

The Converter is a length-oriented object. In 2D you can control how often the MU is shown on the

<!-- image -->

Converter with the setting Animate Every x-th Pixel . If you insert the Converter with its icon Number of Animation Events controls these steps.

You can also enter the Relative Converting Point For Length and/or the Relative Converting Point For Width .

<!-- image -->

**Note**

If the MU is converted at the converting point, meaning that the MU is located on the converting point of the Converter , the Converter has to provide enough space to accommodate the MU :

- The distance of the Booking Point Length from the rear of the MU can be at most as great as the distance of the distance of the converting point for the length from the left side of the Converter .
- The distance of the Booking Point Length from the front of the MU can be at most as great as the distance of the converting point for the length from the right side of the Converter .
- The distance of the Booking Point Width from the left side of the MU can be at most as great as the distance of the converting point for the width from side 3 of the Converter .
- The distance of the Booking Point Width from the right side of the MU can be at most as great as the distance of the converting point for the width from side 1 of the Converter .

In 3D, you can select different configurations for the Converter on the tab Appearance .

<!-- image -->

To show a tooltip with information about the Converter , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Converter , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

<!-- image -->

To add the Converter to your simulation model, click MaterialFlow &gt; Converter on the Home ribbon tab.

See also

Convey Parts Laterally with the Converter Manage Class Library &gt; Basic Objects &gt;

Video on YouTube

[https://youtu.be/hOvdrDnvXXo?si=TgnQivMCDc9eD3nU&amp;t=13](https://youtu.be/hOvdrDnvXXo?si=TgnQivMCDc9eD3nU&t=13)

#### Dialog Box of the Converter

Dialog Box of the Converter

Double-click the icon of the Converter to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes [Converter]

The tab Attributes provides the settings listed in the table of contents to the left.

In 3D, you can change the length of the graphic and the anchor points of the Converter by clicking Show

<!-- image -->

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

###### Length [text box] - Converter

Type in the Length of the Converter .

<!-- image -->

After you inserted it, Plant Simulation shows its length here. If the MU is conveyed straight through along the direction of insertion, its length and the length of the MUs determine how many MUs it can accommodate.

**Note**

If the Converter is to convey MUs perpendicular, it has to provide enough room for the Length and the Width of the MU to completely fit on the Converter , when the booking point is located on the converting point in the center of the Converter .

In 3D, you can change the length of the graphic and the anchor points of the Converter by clicking Show

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

SimTalk

Length [SimTalk] - Converter

**Width [text box] - Converter**

###### Width [text box] - Converter

Type in the Width of the Converter . Plant Simulation inserts the Converter with the standard width of 1 meter.

**Note**

If the Converter is to convey MUs perpendicular, it has to provide enough room for the Length and the Width of the MU to completely fit on the Converter , when the booking point is located on the converting point in the center of the Converter .

**Note**

You can only type in the Width in pixels in 2D if you deactivate Transfer Length . If you activate it, Plant Simulation computes the Width in meters.

**SimTalk**

Width [SimTalk] - Converter

###### Speed [text box] - Converter

Type in the Speed with which the Converter conveys the MUs .

Type in -1 for an infinite speed.

SimTalk

Pauses [Transporter]

**Capacity [text box] - Converter**

###### Capacity [text box] - Converter

Type in the Capacity , i.e., the number of MUs , which the Converter can hold, into this text box.

<!-- image -->

<!-- image -->

The default value -1 stands for an infinite capacity.

If the Converter conveys MUs along the insertion direction, you can, for example, use the Capacity to allow the Converter to only convey this number of MUs at the same time.

This only limits the possible number of MUs . If the Converter conveys MUs it still conveys a single MU at a time though.

SimTalk

Capacity [SimTalk] - Converter

###### Relative Converting Point For Length

Type in the relative position of the converting point along the length of the Converter .

The converting point is the point at which the Converter changes the conveying direction of the MUs it conveys.

You can type in a value between 0.0 and 1.0 , denoting a position between 0 % and 100 %.

Note

The Converter does not show the location of the converting point on its graphic in the Frame .

SimTalk

RelConvertingPointL [SimTalk]

###### Relative Converting Point For Width

Type in the relative position of the converting point along the width of the Converter .

The converting point is the point at which the Converter changes the conveying direction of the MUs it conveys.

You can type in a value between 0.0 and 1.0 , denoting a position between 0 % and 100 %.

Note

The Converter does not show the location of the converting point on its graphic in the Frame .

SimTalk

RelConvertingPointW [SimTalk]

###### Automatic Stop [check box] - Converter

To set the current speed of the Converter to 0 when it does not transport a part, select this check box.

<!-- image -->

This might, for example, be the case if it is empty or if it is blocked because a MU cannot leave it.

If the speed of the Converter is 0, the Energy State changes to Operational .

SimTalk

AutomaticStop [SimTalk] - AngularConverter Go to Default Position [check box] - Converter To make the Converter return to its default position after the MU has left the Converter , select this check box.

The Converter does not return to its default position if a MU is waiting that wants to enter laterally.

SimTalk

GoToDefaultPosition [SimTalk] - Converter

###### Strategy [check box] - Converter

Select the Strategy according to which the Converter conveys the MUs to the next material flow object.

<!-- image -->

- Default Exit makes all MUs exit through the Default Exit which you select to the successor attached to that exit.
- Straight conveys the MU straight through to the next station.

<!-- image -->

If several equally fast routes exist, the route, which leads straight through the Converter will be preferred, as the parts do not have to be singularized for this. If several Converters are located within the fastest route, Plant Simulation selects the route of the equally fast routes where the part must be converted the least. A useful side effect is that Plant Simulation finds the clearly shortest route more often, meaning that the entire route to the destination is known immediately.

- MU Attribute conveys the MUs according to a built-in or a user-defined attribute of the MU . Click Open List and enter the name of the Attribute of the MU , the Value of the attribute, and select on which Side it is to exit. Type in the number of the Default Exit . Repeat this for each attribute you specify.

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

- MU Name conveys the MU according to its Name . Click Open List and type in the name of the MU and select on Which Side it is to exit.

Enter the number of the Default Exit .

<!-- image -->

- Method conveys the MUs according to the attribute ExitForMU you enter into the Strategy Method . Here you determine the side of the Converter at which the MU will exit the Converter . Select the method or enter the name of the method into the text box Strategy Method .
- Feed in enables MUs from a branch line to only enter the main line if no MU is located on the main line within the Free Space which you enter. The Free Space is the distance between two successive MUs on the main line.

<!-- image -->

<!-- image -->

**Note**

The first-come-first-served principle applies for all strategies, except for Feed In , meaning a MU , which has a matching entrance and a matching target, still cannot enter the object after the Moving Time has passed if another MU is already waiting, even if a Moving Time is required for this part as well. The main conveyor only has precedence for the strategy Feed In . Waiting MUs from a branch conveyor still have to wait unless the Moving Time has already started.

- Method at Converting Point determines the target with the attribute ExitForMU at the converting point, not already before the MU enters the Converter . This strategy is only available for a Capacity of 1.

The MU always stops at the converting point. Then, Plant Simulation calls the method for determining the target. In the method you can, for example, use ?.ExitForMU := 1 .

Select the method or type the name of the method into the text box Strategy Method .

Note

As the Strategy Method is used for determining the side of the exit, the Strategy Method will not be called if the MU has a route and Automatic Routing is activated.

SimTalk

Strategy [SimTalk] - Converter

Strategy Method [Converter]

ExitForMU [SimTalk]

See also

Convey Parts Laterally with the Converter

Convey Parts According to a Strategy Control

**Strategy Method [Converter]**

###### Strategy Method [Converter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Strategy Method , which is called as soon as the MU wants to enter the Converter for the setting Strategy &gt; Method .

<!-- image -->

The Strategy Method sets the side of the Converter at which the MU will exit the Converter . Set the side with the attribute ExitForMU .

Plant Simulation executes the Strategy Method when the MU has reached the converting point for the setting Strategy &gt; Method at Converting Point .

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

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

```simtalk
param entranceNo: integer
?.ExitForMU := 0 /* number of exit */
```

SimTalk

StrategyCtrl [SimTalk] - Converter

See also

Select Object [for controls]

Convey Parts According to a Strategy Control

**Default Exit [text box]**

###### Default Exit [text box]

Select the Default Exit at which the MU exits the Converter for the Strategies &gt; Default Exit , MU Attribute , and MU Name .

<!-- image -->

- 1 is laterally to the right in the insertion direction, 2 is against the insertion direction, 3 is laterally to the left in the insertion direction, 0 is along the insertion direction.

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

**SimTalk**

DefaultExit [SimTalk]

See also

Strategy [check box] - Converter

###### Open List [button] - Converter

To open the exit list for the MUs , click this button.

For the Strategy &gt; MU Attribute and MU Name you can open the exit list and type in the information pertaining to the respective strategy.

For the Strategy &gt; MU Attribute you can type in the name of the Attribute of the MU , its Value and select on Which Side it exits. Repeat this for each attribute you specify.

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

For the Strategy &gt; MU Name you can type in the Name of the attribute of the MU and select on Which Side it exits. Repeat this for each attribute you specify.

<!-- image -->

**SimTalk**

###### Move Down [source code]

FailDuration [SimTalk]

See also

Data Held in Tabular Form in Attributes [material flow objects]

**Convey Parts Laterally According to Their Name**

###### Attribute Type [drop-down list] - Converter

For the Strategy &gt; MU Attribute you can select the data type of the attribute that determines the material flow object to which the Converter moves the part.

<!-- image -->

**SimTalk**

AttributeType [SimTalk] - Converter

See also

Strategy [check box] - Converter

Data Types [SimTalk]

Tab Times

Tab Times [Converter]

Define Times as described under the Tab Times .

In addition, the Converter provides the Moving Time .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

###### Tab Times [Converter]

See also Recovery Time [general description] Recovery Time Starts Cycle Time [general description]

Moving Time [drop-down list] - Converter

###### Moving Time [drop-down list] - Converter

The Moving Time is the time it takes the Converter to lift the MU onto a different conveying level and to then lower itself and move back to the default position. This time always elapses when the Converter has to change the direction of the MU and when a MU enters from a side, i.e., not along the preferred insertion direction.

<!-- image -->

Plant Simulation shows these values along the upper border of the tab. You can also type in a constant time ( Const ).

Select a distribution for the Moving Time from the drop-down list, and type the values, which that distribution requires, into the text box.

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the part for which the Moving Time applies.

<!-- image -->

**SimTalk**

MovingTime [SimTalk] - Converter

MovingTime . Type [SimTalk] - distribution parameter

putAttributeNamesIntoTable [SimTalk] - distributions

**Tab Failures**

##### Tab Failures

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

##### Tab Statistics [Converter]

Statistics is described under the Tab Statistics .

In addition, the Converter collects these statistical values:

| Item English   | Description                                                                                                                              | Read-only attribute                | Item German     |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|-----------------|
| Moving Empty   | Shows the portion of the statistics collection period during which the Converter was raising or lowering itself without conveying a MU . | StatMovingEmptyPorti on [SimTalk]  | Umsetzen leer   |
| Moving Loaded  | Shows the portion of the statistics collection period during which the Converter was raising or lowering itself while conveying a MU .   | StatMovingLoadedPort ion [SimTalk] | Umsetzen belegt |

<!-- image -->

To view Moving Time in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

**Tab Statistics [Converter]**

**See also**

Resource Statistics [check box]

Resource Type

<!-- image -->

##### Tab Curve [Converter]

As opposed to the regular length-oriented objects, the Converter consists of a single straight segment, not of a sequence of straight and curved segments. You can apply most of the settings described under the Tab Curve .

As opposed to the other curved objects, you cannot enter the Width of the object here, but on the Tab Attributes .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Converter during a simulation run.

- Click the icon of the Converter with the left mouse button and click Edit Icons on the Home ribbon tab.
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

While the Converter transports parts costs accrue which result from the sum of the total investment costs and the total operating costs.

**Note**

The total investment costs only accrue during the Depreciation Period .

The costs are allocated to the part, proportional to the length of the part to the active length of the Converter , as accrued costs . Thus, a longer part is allocated higher costs as it occupies a greater part of the Converter .

If the Converter is empty, the costs remain with the Converter as general costs .

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

**Methods of the Converter**

#### \_Methods of the Converter

The Converter provides:

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

getAttributeList [SimTalk] - Converter

Returns the target list for the Strategy &gt; MU Attribute of the Converter designated by &lt;Path&gt;.

**Remarks**

The Attribute List contains the names of the Attributes of the MU , their Values , and on Which Side they exit.

<!-- image -->

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

For the Strategy &gt; MU Name it contains the names of the MUs and on which side they exit.

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getAttributeList(AttributeList:table)

Parameter

The parameter AttributeList of data type table designates the name of the list.

Example

Converter.getAttributeList(MyAttributesList)

SimTalk

setAttributeList [SimTalk] - Converter

See also

Open List [button] - Converter

Strategy [check box] - Converter

**getSideOfConnector [SimTalk]**

##### getSideOfConnector [SimTalk]

Returns the side at which the designated Connector is attached to the Converter designated by &lt;Path&gt;.

**Remarks**

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getSideOfConnector(Connector:object) → integer

**Parameter**

The parameter Connector of data type object designates the Connector .

Return Value

The return value has the data type integer .

**Example**

```simtalk
var side: integer
side := Converter.getSideOfConnector(Connector)
side := Converter.getSideOfConnector(Connector1)
```

<!-- image -->

##### getSuccessorAtExit [SimTalk]

Returns the successor object, which is connected to the Converter designated by &lt;Path&gt; at the side designated by the parameter.

Type

Method

Syntax

```simtalk
< Path >.getSuccessorAtExit(Side:integer) → object
```

**Parameter**

The parameter Side of data type integer designates the side.

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

**Return Value**

The return value has the data type object .

**Example**

MyObject := ?.getSuccessorAtExit(1)

<!-- image -->

setAttributeList [SimTalk] - Converter

Sets the target list for the Strategy &gt; MU Attribute of the Converter designated by &lt;Path&gt;.

**Remarks**

The Attribute List contains the names of the Attributes of the MU , the Values of the attributes, and on Which Side it exits.

<!-- image -->

The numbers designate the side of the Converter at which the part exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

<!-- image -->

For the Strategy &gt; MU Name you can enter the Names of the parts and on Which Side they exit.

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.setAttributeList(AttributeList:table)

Parameter

The parameter AttributeList of data type table designates the path to a list or a variable of the same data type. Plant Simulation then copies the contents of the passed list to the target list of the Converter .

Example

Converter.setAttributeList(MyAttributes)

SimTalk

getAttributeList [SimTalk] - Converter

See also

Open List [button] - Converter

Data Held in Tabular Form in Attributes [material flow objects]

Strategy [check box] - Converter

#### Read-Only Attributes of the Converter

\_Read-Only Attributes of the Converter

The Converter provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Converter.GetCurrentExit

##### GetCurrentExit [SimTalk]

Returns the number of the side at which the MU exits the Converter designated by &lt;Path&gt;.

**Remarks**

The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model. The numbers designate the side of the Converter at which the MU exits.

<!-- image -->

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetCurrentExit → integer

**Return Value**

The return value has the data type integer .

Example

No := ?.GetCurrentExit

<!-- image -->

##### GetNextEntranceNumber [SimTalk]

Returns the number of the side at which the next MU can enter the Converter designated by &lt;Path&gt;.

**Remarks**

The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model. The numbers designate the side of the Converter at which the MU exits.

<!-- image -->

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetNextEntranceNumber → integer

**Return Value**

The return value has the data type integer .

Example

No := ?.GetNextEntranceNumber

<!-- image -->

**IsUp [SimTalk] - Converter**

Returns if the Converter designated by &lt;Path&gt; is in the up position (true) or in the down position (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsUp → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
PosUpDown := MyConverter.IsUp
```

You can also use the attribute IsUp to start the lifting process.

Example

```simtalk
MyConverter.IsUp := true
```

StatMovingEmptyPortion [SimTalk]

Returns the portion of the statistics collection period during which the Converter designated by &lt;Path&gt; was raising or lowering itself and was not conveying a MU .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMovingEmptyPortion → real

Return Value

The return value has the data type real .

Example

print Converter.StatMovingEmptyPortion

See also

Tab Statistics [Converter]

Moving Time [statistics report]

##### StatMovingEmptyTime [SimTalk]

Returns the total time during which the Converter designated by &lt;Path&gt; was raising or lowering itself and was not conveying a MU .

Type

Read-only attribute

Syntax

< Path >.StatMovingEmptyTime → time

Return Value

The return value has the data type time .

Example

print Converter.StatMovingEmptyTime

See also

Moving Time [statistics report]

StatMovingLoadedPortion [SimTalk]

Returns the portion of the statistics collection period during which the Converter designated by &lt;Path&gt; was raising or lowering itself and was conveying a MU .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMovingLoadedPortion → real

Return Value

The return value has the data type real .

Example

print Converter.StatMovingLoadedPortion

See also

Tab Statistics [Converter]

Moving Time [statistics report]

##### StatMovingLoadedTime [SimTalk]

Returns the total time during which the Converter designated by &lt;Path&gt; was raising or lowering itself and was conveying a MU .

Type

Read-only attribute

Syntax

< Path >.StatMovingLoadedTime → time

Return Value

The return value has the data type time .

Example

print Converter.StatMovingLoadedTime

See also

Moving Time [statistics report]

#### Attributes of the Converter

\_Attributes of the Converter

The Converter provides:

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
Converter.Length := 11
print Converter.Length
posit := MyStation.Cont.XPos
```

##### AttributeType [SimTalk] - Converter

Sets the Attribute Type of the Strategy &gt; MU Attribute of the Converter designated by &lt;Path&gt;.

Remarks

This is the data type of the attribute that sets the material flow object to which the Converter moves the part.

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

Converter.AttributeType := "String"

**See also**

Attribute Type [drop-down list] - Converter

**Strategy [check box] - Converter**

##### AutomaticStop [SimTalk] - Converter

Automatically stops the Converter designated by&lt;Path&gt;. This means that it sets its current speed to 0 if it does not transport a MU .

Remarks

This might, for example, be the case if it is empty or if it is blocked because a MU cannot leave it.

If the speed of the Converter is 0, the Energy State changes to operational .

Type

Attribute

Syntax

&lt; Path &gt;.AutomaticStop:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Converter.AutomaticStop := true

See also

Automatic Stop [check box] - Converter

Operational [energy]

**Capacity [SimTalk] - Converter**

Capacity [SimTalk] - Converter

Sets the Capacity , i.e., the number of MUs , which the Converter designated by &lt;Path&gt; can hold.

Remarks

The default value of -1 stands for an infinite capacity.

If the Converter conveys parts along the insertion direction, you can, for example, use the Capacity to allow the Converter to only convey this number of MUs at the same time.

This only limits the possible number of MUs . If the Converter conveys parts it still conveys a single MU at a time though.

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

Example

```simtalk
Converter.Capacity := 8
```

See also

Capacity [text box] - Converter

##### DefaultExit [SimTalk]

Sets the Default Exit of the Converter designated by &lt;Path&gt;.

**Remarks**

This applies to the Strategies &gt; Default Exit , MU Attribute , and MU Name .

<!-- image -->

The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model. The numbers designate the side of the Converter at which the MU exits.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.DefaultExit:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyConverter.DefaultExit := 2
```

See also

Default Exit [text box]

<!-- image -->

**Strategy [check box] - Converter**

##### ExitForMU [SimTalk]

Sets the side at which the next entering MU or the MU positioned at the converting point wants to exit the Converter designated by &lt;Path&gt;.

Remarks

You can only set the attribute ExitForMU in the Strategy method / StrategyCtrl .

**Note**

The MU cannot exit the Converter at the side at which it entered.

The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model. The numbers designate the side of the Converter at which the MU exits.

<!-- image -->

Type

Attribute

Syntax

**&lt; Path &gt;.ExitForMU:integer**

**Assignment Value**

You can assign a value of data type integer .

**Examples**

```simtalk
param entranceNo: integer
if @.name = "C"
	?.ExitForMU := 0 /* number of the exit of the converter*/
elseif @.name = "A"
	if entranceNo = 2
		?.ExitForMU := 3
```

<!-- image -->

**ExitForMU [SimTalk]**

```simtalk
else
	?.ExitForMU := 0
end
else
	if entranceNo = 2
		?.ExitForMU := 1
	else
		?.ExitForMU := 0
	end
end
?.ExitForMU := 1
```

**SimTalk**

StrategyCtrl [SimTalk] - Converter

See also

Strategy Method [Converter]

##### GoToDefaultPosition [SimTalk] - Converter

Rotates the Converter designated by &lt;Path&gt; back to its default position after the MU has left the Converter ( true ) or not ( false ).

Remarks

The Converter does not return to its default position if a MU is waiting that wants to enter laterally.

Type

Attribute

Syntax

&lt; Path &gt;.GoToDefaultPosition:boolean

**Assignment Value**

You can assign a value of data type boolean .

Example

```simtalk
MyConverter.GoToDefaultPosition := true
```

See also

Go to Default Position [check box] - Converter

##### Length [SimTalk] - Converter

Length [SimTalk] - Converter

Sets the length of the Converter designated by &lt;Path&gt;.

Remarks

If the Converter is to convey parts perpendicular, it has to provide enough room for the length and the width of the MU to completely fit on the Converter , if the booking point is located on the converting point in the center of the Converter .

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

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyConverter.Length := 2m
```

See also

Length [text box] - Converter

##### MovingTime [SimTalk] - Converter

Sets the Moving Time which the Converter designated by &lt;Path&gt; needs to lift the MU onto a different conveying level and to then lower itself and move back to the default position.

Remarks

If you use the formula distribution , you can enter a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the moving time applies.

Type

Attribute

Syntax

< Path >.MovingTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyConverter.MovingTime := 2
```

See also

Moving Time [drop-down list] - Converter

Formula [distribution]

##### RelConvertingPointL [SimTalk]

Sets the relative position of the converting point along the length of the Converter designated by &lt;Path&gt;.

Remarks

The converting point is the point at which the Converter changes the conveying direction of the MUs it conveys.

Type

Attribute

Syntax

&lt; Path &gt;.RelConvertingPointL:real

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type real .

Specify a value between 0.0 and 1.0 , denoting a position between 0 % and 100 %.

Example

```simtalk
MyConverter.RelConvertingPointL := 0.2
```

See also

Relative Converting Point For Length

##### RelConvertingPointW [SimTalk]

Sets the relative position of the converting point along the width of the Converter designated by &lt;Path&gt;.

Remarks

The converting point is the point at which the Converter changes the conveying direction of the MUs it conveys.

Type

Attribute

Syntax

&lt; Path &gt;.RelConvertingPointW:real

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type real .

Specify a value between 0.0 and 1.0 , denoting a position between 0 % and 100 %.

Example

```simtalk
MyConverter.RelConvertingPointW := 0.8
```

See also

Relative Converting Point For Width

##### Speed [SimTalk] - Converter

Speed [SimTalk] - Converter

Sets the Speed with which the Converter designated by &lt;Path&gt; conveys the MUs .

Syntax

< Path >.Speed:speed

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

Specify -1 for an infinite speed.

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the number, without a separating blank space, for example 100kmh or 100.5kmh .

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
MyConverter.Speed := 2
```

**See also**

**Speed [text box] - Converter**

Strategy [SimTalk] - Converter

Sets the Strategy of the Converter designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Strategy:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Default exit" to make all MUs exit through the Default Exit which you select to the successor attached to that exit.
- "Straight" to convey the MU straight through to the next station.
- "Feed in" to allow MUs from a branch line to only enter the main line when no part is located on the main line within the Free Space which you enter. The Free Space is the distance between two successive MUs on the main line.
- "MU Attribute" to move the MU on according to a built-in or a user-defined attribute of the MU . You can set the attributes with the method setAttributeList . You can set the default exit with the attribute DefaultExit .

<!-- image -->

<!-- image -->

<!-- image -->

- "MU Name" to move the MU on according to its name. You can set the default exit with the attribute DefaultExit . You can set the attributes with the method setAttributeList .

The numbers designate the side of the Converter at which the MU exits. The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model.

<!-- image -->

- "Method" to convey the MU according to the attribute ExitForMU you enter into the Strategy Method in which you determine the side of the Converter at which the MU will exit the Converter . You can set the control with the attribute StrategyCtrl .
- "Method at Converting Point" to only determine the target at the converting point with the attribute ExitForMU , not already before the MU enters the Converter . This strategy is only available for a Capacity of 1.

<!-- image -->

The MU always stops at the converting point. Then, Plant Simulation calls the method for determining the target. In the method you can, for example use ?.ExitForMU := 1 . You can set the control with the attribute StrategyCtrl .

**Note**

As the Strategy Method is used for determining the side of the exit, the Strategy Method will not be called when the MU has a route and Automatic Routing is activated.

**Example**

```simtalk
MyConverter.Strategy := "Straight"
```

SimTalk StrategyCtrl [SimTalk] - Converter ExitForMU [SimTalk] setAttributeList [SimTalk] - Converter DefaultExit [SimTalk] StrategyCtrl [SimTalk] - Converter See also Strategy [check box] - Converter Strategy Method [Converter] Default Exit [text box] Capacity [text box] - Converter Automatic Routing [Part, Container]

##### StrategyCtrl [SimTalk] - Converter

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Type in the source code that determines the side of the Converter designated by &lt;Path&gt; at which the MU will exit the Converter .

The figures below illustrate the sides depending on the direction in which you inserted the Converter into your simulation model. The numbers designate the side of the Converter at which the part exits.

<!-- image -->

<!-- image -->

Plant Simulation executes the Strategy Method as soon as the MU wants to enter the Converter for the setting Strategy &gt; Method .

Plant Simulation executes the Strategy Method when the MU has reached the converting point for the setting Strategy &gt; Method at Converting Point .

You have to set the side with the attribute ExitForMU .

As the Strategy Method is used for determining the side of the exit, the Strategy Method will not be called when the MU has a route and Automatic Routing is activated.

The default strategy method looks like this:

```simtalk
param entranceNo: integer
?.ExitForMU := 0 /* number of exit */
```

Type

Attribute

Syntax

< Path >.StrategyCtrl:method

Assignment Value

You can assign a value of data type method .

**Examples**

```simtalk
param entranceNo: integer
if @.name = "C"
	?.ExitForMU := 0 /* number of the exit of the converter*/
elseif @.name = "A"
	if entranceNo = 2
		?.ExitForMU := 3
	else
		?.ExitForMU := 0
	end
else
	if entranceNo = 2
		?.ExitForMU := 1
	else
		?.ExitForMU := 0
	end
end
MyConverter.StrategyCtrl := &myStrategyCtrl
```

SimTalk

ExitForMU [SimTalk]

See also

Strategy Method [Converter]

Automatic Routing [Part, Container]

##### Width [SimTalk] - Converter

Sets the Width of the Converter designated by &lt;Path&gt;.

Remarks

**Note**

If you deactivated TransferLengthToObject the Width does not affect how the Converter is shown in the Frame in 2D.

**Note**

If the Converter is to convey MUs perpendicular, it has to provide enough room for the Length and the Width of the MU to completely fit on the Converter , if the booking point is located on the converting point in the center of the Converter .

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

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

MyConverter.Width := 2

