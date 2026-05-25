### Conveyor

#### Conveyor [object]

Use the object Conveyor for modeling a conveyor system or a part thereof.

Icon

<!-- image -->

Description

As opposed to the point-oriented material flow objects, Plant Simulation uses the actual Length , which you type into the dialog of the Conveyor , during your simulation run.

The Conveyor transports a MU along its entire length with a constant speed. A MU cannot pass another MU moving along in front of it. If you do not enter an Exit Control , the Conveyor distributes the MUs equally among the successors it is connected to.

If the preceding MU cannot exit the Conveyor , the check box Accumulating sets if succeeding MUs may move up, so that they are located front to back to each other, or if they will retain their distance to each other.

Plant Simulation moves MUs on as follows:

**· Moving from point-oriented object to length-oriented object**

When moving from a point-oriented object, such as a Source or a Station , to a Conveyor , the front of the MU moves to the start of the Conveyor . If Station and Conveyor are not placed directly side by side, the MU seems to hang in thin air, compare Position of the MU .

<!-- image -->

If the objects are placed directly side by side you will not notice that as the MU still seems to be located on the predecessor.

<!-- image -->

**· Moving from length-oriented object to length-oriented object**

When moving from Conveyor to Conveyor , the MU moves continually on, i.e., only its front moves on to the successor, while the remainder follows with the Speed you specified. If the transport speeds differ, Plant Simulation uses the speed of the Conveyor , on which the Booking Point Length of the MU is located.

<!-- image -->

**· Moving from length-oriented object to point-oriented object**

When moving onto a point-oriented object, such as a Station , the MU always moves completely and instantaneously, i.e., it is then located on that object as a whole, not only its front section.

<!-- image -->

You can also enter the MU Distance between MUs on the Conveyor . This is the distance between the end of the MU that is located on the Conveyor and the beginning of the next MU that wants to enter. If no further MUs arrive, the Conveyor stops when this distance has been reached. As soon as the next MU arrives, it starts to transport MUs again. The default value -1 means that the Conveyor does not use a MU Distance .

**Note**

If the preceding Conveyor transports MUs faster than the Conveyor which uses a gap, the MU Distance can become smaller. This happens because the entering MU will be transported with a greater speed until its booking point is located on the conveyor which uses a gap.

You can insert the Conveyor into a Frame as follows:

**· In a 3D Only Model**

As a curved object, which is the default setting.

By inserting any sequence of curved segments and straight segments, you can realistically model curved conveyor systems on which the MUs move.

<!-- image -->

You can select different configurations for the Conveyor on the tab Appearance .

<!-- image -->

- In a 2D Only Model

As a curved object, which is the default setting.

With its icon, if you deactivate Curve mode on the Tab Curve by clearing the check box . Then, it looks like this .

<!-- image -->

To change the Width/Height of the icon, open the dialog of the object and type in the Curve Width on the tab Curve . Then, it looks like this .

You can control how often the MU is shown on the Conveyor with the setting Animate Every x-th Pixel .

If you insert the Conveyor with its icon , the Number of Animation Events controls these steps.

To show a tooltip with information about the Conveyor , hover with the mouse over it.

<!-- image -->

**Show Manipulators**

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

The manipulator at the start and at the end of the length-oriented object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

**Add the Object to the Simulation Model**

<!-- image -->

To add the Conveyor to your simulation model, click MaterialFlow &gt; Conveyor on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Work with Length-oriented Objects in 3D

Work with Length-oriented Objects in 2D and 3D

Model a Transport System with Active Objects

Video on YouTube

[https://youtu.be/Kznlnw5BJGc?si=PDf1XGx9A0D0HrGj](https://youtu.be/Kznlnw5BJGc?si=PDf1XGx9A0D0HrGj)

#### Dialog Box of the Conveyor

Dialog Box of the Conveyor

Double-click the icon of the Conveyor to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Tab Importer [Conveyor] &gt; Transport Importer

Video on YouTube

[https://youtu.be/Kznlnw5BJGc?si=4TUTVa8zyYFVtHfa&amp;t=359](https://youtu.be/Kznlnw5BJGc?si=4TUTVa8zyYFVtHfa&t=359)

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

In 3D, you can change the length of the graphic and the anchor points of the Conveyor by clicking Show

<!-- image -->

Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

###### Length [text box] - Conveyor

Length [text box] - Conveyor

Type the Length of the Conveyor into the text box.

<!-- image -->

After you inserted it into your simulation model, Plant Simulation shows its length in the text box.

The length of the Conveyor and the sum of the lengths of all MUs located on it determine how many MUs the Conveyor can accommodate at any one time. The length of the MUs will only be evaluated, when you type in an unlimited Capacity .

If you change the length, Plant Simulation automatically recomputes the Time .

In 3D, you can change the length of the graphic and the anchor points of the Conveyor by clicking Show

Manipulators on the Edit ribbon tab or by clicking M on the keyboard.

<!-- image -->

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the Length of a Conveyor which only consists of a single straight segment.

You can only type in the Length in pixels in 2D if you deactivate Transfer Length or if the Conveyor consists of a single straight segment.

SimTalk

Length [SimTalk] - Conveyor

See also

OccupiedLength [SimTalk] - Conveyor

Capacity [text box] - Conveyor

Time [text box] - Conveyor

###### Width [text box] - Conveyor

Type in the Width of the Conveyor .

<!-- image -->

Note

You can only type in the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the width in meters.

SimTalk

Width [SimTalk] - AngularConverter

See also

Width [tab Appearance]

Speed [text box] - Conveyor

Type in Final Speed with which the Conveyor transports the MUs located on it.

<!-- image -->

You can also type in -1 for an infinite speed.

- If you change the Speed , Plant Simulation automatically recomputes the Time , and vice versa, provided you deactivated Acceleration . The Processing Time is the Length divided by the speed .
- If you activate Acceleration , the Conveyor attempts to reach the final speed no matter if a MU is located on it or not. A MU entering the Conveyor moves with the actual speed of the Conveyor . If the Conveyor currently accelerates, the MU will accelerate as well.

**Note**

If you change the Speed Plant Simulation re-computes all events relating to the Speed for all MUs located on it. If the MU located at the exit of the object is neither blocked nor stopped , it may happen that a new Out event is scheduled. In this case the Exit Control is called again independent of the setting Exit Control Once .

SimTalk

Speed [SimTalk] - Conveyor

See also

Speed Control [Conveyor]

Time [text box] - Conveyor

Acceleration [text box] - Conveyor

Length [text box] - Conveyor

Time [text box] - Conveyor

Type in the Time which a MU takes to cover the empty Conveyor .

<!-- image -->

If you change the Time , Plant Simulation automatically recomputes the Speed .

If you type in 0 as the Time , the display of the speed is meaningless.

SimTalk

Time [SimTalk] - Conveyor

See also

Speed [text box] - Conveyor

Acceleration [check box] - Conveyor

**Accumulating [check box] - Conveyor**

###### Accumulating [check box] - Conveyor

To make the MUs accumulate on the Conveyor , select this check box. This permits the MUs to move front to end to each other, when the exit of the object is blocked.

<!-- image -->

To make the MUs retain their distance to each other, i.e., make all succeeding MUs stop moving when the preceding MU cannot exit the Conveyor , clear the check box. If the object is blocked, it stops, i.e., it reduces its speed to 0.

If a MU is stopped on a non-accumulating Conveyor , not only the succeeding MUs , but all MUs on this Conveyor are stopped and the current speed of the Conveyor is set to 0.

If a MU is to be set in motion again, no additional stopped MUs may be located on the Conveyor . If this is the case, all MUs are set in motion and the Conveyor starts moving again.

<!-- image -->

**SimTalk**

Accumulating [SimTalk] - Conveyor

See also

**Exit Blocked**

Model an Accumulating/a Non-Accumulating Transport System

###### Backwards [Conveyor]

To make the Conveyor itself and the MUs on it move in reverse, select this check box. To make them move forward, clear the check box.

<!-- image -->

<!-- image -->

When moving in reverse the MUs enter the Conveyor at its exit and leave it at its entrance.

If you cleared Acceleration of the Conveyor , it reverses the direction in which it moves immediately without decelerating and accelerating.

If you selected Acceleration , the Conveyor slows down until its speed is 0. Then it reverses the direction in which it moves and accelerates until it reaches its final speed.

SimTalk

Backwards [SimTalk] - Conveyor

See also

Speed [text box] - Conveyor

Acceleration [check box] - Conveyor

AccelerationEnabled [SimTalk] - Conveyor

###### Acceleration [check box] - Conveyor

To make the Conveyor increase its speed, select this check box.

<!-- image -->

Then, type in the Acceleration with which it speeds up and the Deceleration with which it slows down. The Conveyor also shows the actual Current Speed with which it moves.

- If you change the Speed , Plant Simulation recomputes the Time and vice versa, if you deactivate Acceleration .
- If you activate Acceleration , the Conveyor attempts to reach the final speed no matter if a MU is located on it or not. A MU entering the Conveyor moves with the actual speed of the Conveyor . If the Conveyor currently accelerates, the MU will accelerate as well.

To deactivate acceleration, clear the check box.

<!-- image -->

SimTalk

AccelerationEnabled [SimTalk] - Conveyor

See also

Acceleration [text box] - Conveyor

Deceleration [text box] - Conveyor

Speed [text box] - Conveyor

Time [text box] - Conveyor

###### Current Speed [text box] - Conveyor

Shows the Current Speed of the Conveyor at the present time here, provided you selected the check box Acceleration .

<!-- image -->

**Note**

The setting is watchable for special values. By watching this value, you might, for example detect the event when the Conveyor has reached its Final Speed .

SimTalk

CurrentSpeed [SimTalk] - Conveyor

See also

Acceleration [check box] - Conveyor

Speed Control [Conveyor]

Acceleration [text box] - Conveyor

Type in the Acceleration with which the Conveyor increases its speed.

<!-- image -->

You can type in any real number greater than or equal to 0 .

<!-- image -->

You can only type in a value for the Acceleration after you select the check box Acceleration .

SimTalk

Acceleration [SimTalk] - Conveyor

See also

Acceleration [check box] - Conveyor

###### Deceleration [text box] - Conveyor

<!-- image -->

<!-- image -->

Type in the Deceleration with which the Conveyor slows down.

You can type in any real number greater than or equal to 0 .

You can only type in a value for the Deceleration after you select the check box Acceleration .

SimTalk

Deceleration [SimTalk] - Conveyor

See also

Acceleration [check box] - Conveyor

###### Capacity [text box] - Conveyor

Capacity [text box] - Conveyor

Type in the Capacity of the Conveyor .

<!-- image -->

<!-- image -->

The Capacity is the maximum number of MUs that can be located on the Conveyor as a whole or in part at any one time.

The default value -1 designates an infinite capacity.

You can also type in another number, so that the Conveyor does not make use of the entire available Length .

SimTalk

Capacity [SimTalk] - Conveyor

See also

Length [text box] - Conveyor

###### MU Distance Type [text box]

Select the distance type for the space between the MUs . Then, type the actual distance into the text box MU Distance .

<!-- image -->

- Gap sets the distance between the rear of the preceding part and the front of the succeeding part.
- Pitch sets the distance between the front of the preceding part and the front of the succeeding part.

<!-- image -->

<!-- image -->

**Note**

The Front of the part always moves toward the end of the length-oriented object into the direction with which you inserted it along the direction of motion of the material flow.

When you insert a length-oriented object, for example a Conveyor , from left to right, the Front of the part is located on the right-hand side and moves toward the right. When you insert a length-oriented

**MU Distance Type [text box]**

<!-- image -->

- Minimum Gap sets the minimum distance between the rear of the preceding MU and the front of the succeeding MU . This setting prevents the Conveyor from stopping and from waiting for new MUs and enables the Conveyor to run dry.
- Minimum Pitch sets the minimum distance between the front of the preceding MU and the front of the succeeding MU . This setting prevents the Conveyor from stopping and from waiting for new MUs and enables the Conveyor to run dry.
- Multiple Gap sets the distance between the rear of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance .

Just as for the setting Minimum Gap , the Conveyor does not stop to wait for new MUs after the gap has been passed. The next MU can only enter the Conveyor if an integer multiple of the gap can be preserved.

- Multiple Pitch sets the distance between the front of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance .

Just as for the setting Minimum Pitch the Conveyor does not stop to wait for new MUs after the pitch has been passed. The next MU can only enter the Conveyor if an integer multiple of the pitch can be preserved.

For this setting the Conveyor behaves like a chain conveyor.

SimTalk

MUDistanceType [SimTalk]

See also

MU Distance [text box] - Conveyor

Model a Fixed Gap or a No Gap Conveyor

Model a Multiple Gap or a Multiple Pitch Conveyor

###### MU Distance [text box] - Conveyor

Select the MU Distance Type and type in the desired distance of the current MU to the preceding MU which the Conveyor enforces, when the next MU enters.

<!-- image -->

Depending on the setting for the MU Distance Type the MU Distance determines for:

<!-- image -->

- Gap the distance between the rear of the preceding MU and the front of the succeeding MU .
- Pitch the distance between the front of the preceding MU and the front of the succeeding MU .

<!-- image -->

<!-- image -->

If no further parts arrive, the Conveyor stops once the distance has been reached. As soon as the next MU arrives, it starts to transport MUs again.

The default value -1 means that the Conveyor does not use the MU Distance and that MUs can enter at any time as the predecessor provides them.

**Note**

If the preceding Conveyor transports parts faster/slower than the Conveyor , which uses a MU Distance , the distance itself can become greater/smaller. This is because the entering MU moves with a faster/ slower speed until its booking point is located on the Conveyor using a MU Distance .

If the succeeding Conveyor transports parts faster/slower than the Conveyor , which uses a MU Distance , the distance itself can become greater/smaller. This is because the booking point of the leaving MU is located on the succeeding Conveyor , which transports parts with a faster/slower speed.

**Note**

Plant Simulation only runs the distance check when a part enters. If you selected Accumulating for example the distance can be undercut when the parts accumulate.

**Note**

The Conveyor only uses the MU Distance if it transports parts in the forward direction.

SimTalk

MUDistance [SimTalk]

See also

MU Distance Type [text box]

Model a Fixed Gap or a No Gap Conveyor

Model a Multiple Gap or a Multiple Pitch Conveyor

###### Enforce MU Distance [check box]

To force the Conveyor to keep the specified MU Distance between the MUs , even if the MUs accumulate on the Conveyor , select this check box.

<!-- image -->

To allow the MUs to accumulate on the Conveyor and thus move front to end, clear the check box.

<!-- image -->

**Note**

This setting only applies when the Conveyor is Accumulating and conveys MUs in the forward direction.

**Note**

Depending on the setting MU Distance Type and the Speed of succeeding Conveyors the MU Distance might increase.

**Note**

Changing the material flow, either via information flow or manually, might temporarily decrease the MU Distance .

- If you insert MUs on the Conveyor via information flow or if you increase the length of the inserted MU , and thus violate the specified MU Distance , the respective MUs stop until the MU Distance is met again.
- If you create MUs on a Conveyor via information flow, the created MUs stop until the MU Distance is met again. The following MU keeps the distance to the previous MU instead of to the created MU , until the created MU starts moving.

**Enforce MU Distance [check box]**

- If you change the MU Distance of the Conveyor via information flow while MUs are located on it, the MUs keep their original distance at first. If the MUs are stopped later on, for example because they accumulate on the Conveyor , they only start moving again when the new distance is met.

SimTalk

EnforceMUDistance [SimTalk]

See also

Model a Fixed Gap or a No Gap Conveyor

MU Distance [text box] - Conveyor

MUDistance [SimTalk]

Automatic Stop [check box] - Conveyor

To set the Current Speed of the Conveyor to 0 when it does not transport a MU , select this check box. This might, for example, be the case if it is empty or if it is blocked if a MU cannot leave it.

<!-- image -->

If you select Automatic Stop , the Speed is immediately set to 0 without using the value you typed in for the Deceleration . Along the same lines the Speed is immediately set to the Target Speed without using the value you typed in for the Acceleration .

When the speed of the Conveyor is 0 , the Energy State changes to Operational .

SimTalk

Current Speed [text box] - Conveyor

AutomaticStop [SimTalk] - AngularConverter

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

Tab Controls [Conveyor]

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

In addition, you can:

###### Tab Controls [Conveyor]

- Select the Shift Calendar .
- Create and insert Sensors .

The Conveyor shows the sensors, which you defined, on its graphic in the Frame window. To open the dialog Sensors , hold down Alt and double-click the sensor.

**SimTalk**

BwExitCtrl [SimTalk] - material flow objects

BwExitCtrlFront [SimTalk] - material flow objects

BwExitCtrlRear [SimTalk] - material flow objects

BwEntranceCtrl [SimTalk] - material flow objects

BwEntranceCtrlFront [SimTalk] - material flow objects

BwEntranceCtrlRear [SimTalk] - material flow objects

EntranceCtrl [SimTalk] - material flow objects

EntranceCtrlFront [SimTalk] - material flow objects

EntranceCtrlRear [SimTalk] - material flow objects

ExitCtrl [SimTalk] - material flow objects

ExitCtrlFront [SimTalk] - material flow objects

ExitCtrlRear [SimTalk] - material flow objects

PullCtrl [SimTalk] - material flow objects

ShiftCalendarObject [SimTalk] - material flow objects

SpeedCtrl [SimTalk] - Conveyor

See also

Define Controls for Length-Oriented Objects

Sensors [general description]

###### Speed Control [Conveyor]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Speed Control . The Conveyor/loading space of type Line of the Transporter call the Speed Control as soon as they reach their final speed after accelerating or decelerating or when they stop after decelerating.

<!-- image -->

The Speed Control is not called if the speed changes without using up any time at all.

You can only set the Speed Control after you activate Acceleration / AccelerationEnabled .

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

SimTalk SpeedCtrl [SimTalk] - Conveyor LoadBaySpeedCtrl [SimTalk] See also Select Object [for controls]

Transporter &gt; Controls &gt; Speed control [Transporter]

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

**Tab Statistics [Conveyor]**

##### Tab Statistics [Conveyor]

In addition to the statistics values described under the Tab Statistics the accumulating Conveyor shows the value Exit blocked .

**Note**

The Conveyor is in the state Working , when its Current speed is not 0. It also is working , when the conveyor is moving and does not transport a part.

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

##### Tab Importer [Conveyor]

On the Tab Importer &gt; Sub-tab Transport you can specify how the Worker picks up conveyed parts and carries them to another station. This also enables the Worker to carry parts to the Conveyor .

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

**See also**

| Transport Importer                                    | Broker [transport importer]             |
|-------------------------------------------------------|-----------------------------------------|
| Active [check box] - transport importer               | Request Control [transport importer]    |
| Services for Carrying Parts Away [transport importer] | Receive Control [transport importer]    |
| Can Be Interrupted and Drawn Off [transport importer] | Release Control [transport importer]    |
| Wait for Free Target [transport importer]             | MUTarget                                |
| Priority [transport importer]                         | Maximum Dwell Time [transport importer] |

##### Tab Curve [Conveyor]

Create curved Conveyors for your simulation model as described under the Tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Conveyor during a simulation run.

- Click the icon of the Conveyor with the left mouse button and click Edit Icons on the Home ribbon tab.
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

##### Tab Costs

Select costs settings for the object on the Tab Costs .

| Simulate the Accrued Costs of the Machines        | Operating Costs [text box]            |
|---------------------------------------------------|---------------------------------------|
| Active [check box] - costs, material flow objects | Operating Costs per Length [text box] |
| Depreciation Period [text box]                    | _Attributes for Simulating Costs      |
| Investment Costs [text box]                       | CostAnalyzer                          |
| Investment Costs per Length [text box]            | Tab Costs [MUs] of the MUs            |

While the Conveyor transports parts costs accrue which result from the sum of the total investment costs and the total operating costs.

**Note**

The total investment costs only accrue during the Depreciation Period .

These costs are allocated to the part, proportional to the length of the part, as accrued costs . Thus a longer part is allocated higher costs as it occupies a greater part of the Conveyor .

If the Conveyor is empty, the costs remain with the Conveyor as general costs .

See also

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

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

#### Methods of the Conveyor

Methods of the Conveyor

The Conveyor provides:

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

#### Read-Only Attributes of the Conveyor

\_Read-Only Attributes of the Conveyor

The Conveyor provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Conveyor.CurrentAcceleration

##### CurrentAcceleration [SimTalk] - Conveyor

Returns the actual acceleration or deceleration of the Conveyor designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentAcceleration → acceleration

Watchable

The read-only attribute is watchable for special values.

By observing this value, you might, for example, detect the event when the Conveyor has reached its Final Speed .

Return Value

The return value has the data type acceleration .

Example

MyConveyor.CurrentAcceleration

##### OccupiedLength [SimTalk] - Conveyor

Returns the section of the entire Length of the Conveyor designated by &lt;Path&gt;, which is occupied by all MUs located on it.

Remarks

Each MU located on the Conveyor occupies part of the entire available length.

Type

Read-only attribute

Syntax

&lt; Path &gt;.OccupiedLength → length

Return Value

The return value has the data type length .

Example

print Conveyor.OccupiedLength

See also

Length [text box] - Conveyor

#### Attributes of the Conveyor

\_Attributes of the Conveyor

The Conveyor provides:

- The attributes listed in the table of contents to the left,
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
MyConveyor.AccelerationEnabled := false
print MyConveyor.AccelerationEnabled
posit := MyStation.Cont.XPos
```

##### Acceleration [SimTalk] - Conveyor

Sets the Acceleration with which the Conveyor designated by &lt;Path&gt; increases its speed in m/s 2 .

Remarks

You can only set the Acceleration after you activate Acceleration / AccelerationEnabled .

Type

Attribute

Syntax

**&lt; Path &gt;.Acceleration:acceleration**

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type acceleration .

Specify any real number greater than or equal to 0. The Conveyor accelerates until it has reached its final Speed . It accelerates no matter if a MU is located on it or not until it reaches its final speed.

**Note**

In SimTalk 2.0 you can specify the acceleration units mps² , cm² , fps² , and LU/s² .

Type in the unit directly after the values, without a separating blank space, for example 10mps2 or 10.2mps2 .

To create the ² symbol, activate the Num Lock key on the numeric keypad, hold down Alt and type in 0178 on the numeric keypad.

To create the ² symbol on the German keyboard layout , hold down Alt Gr and press the key with the number 2 . If your keyboard does not have the Alt Gr key, hold down Ctrl-right+Alt-right instead.

**Example**

MyConveyor.Acceleration := 3mps2

SimTalk AccelerationEnabled [SimTalk] - Conveyor Speed [SimTalk] - Conveyor See also Acceleration [text box] - Conveyor

Acceleration [check box] - Conveyor

##### AccelerationEnabled [SimTalk] - Conveyor

Activates ( true ) or deactivates ( false ) the Acceleration of the Conveyor designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.AccelerationEnabled:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.AccelerationEnabled := false

See also

Acceleration [check box] - Conveyor Accumulating [SimTalk] - Conveyor Sets if succeeding MUs can move up if the first MU cannot exit the Conveyor designated by &lt;Path&gt; ( true ) or if they will retain their distance to each other ( false )

Remarks

If Accumulating is active, the front of the succeeding MU touches the rear of the preceding MU .

Type

Attribute

Syntax

&lt; Path &gt;.Accumulating:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.Accumulating := true

See also

Accumulating [check box] - Conveyor

##### AutomaticStop [SimTalk] - Conveyor

Automatically stops the Conveyor designated by&lt;Path&gt;. This means that it sets the current speed to 0 when it does not transport a MU .

Remarks

Automatically stopping the Conveyor might, for example, be the case when it is empty or when it is blocked when a part cannot leave it.

The Speed it set to 0 immediately without using the value for the Deceleration . Likewise, the Speed is set to the Target Speed again immediately without using the value for the Acceleration .

If the speed of the Conveyor is 0, the Energy State changes to operational .

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
MyConveyor.AutomaticStop := true
```

See also

Automatic Stop [check box] - Conveyor

Operational [energy]

Backwards [SimTalk] - Conveyor

Sets if the Conveyor designated by &lt;Path&gt; and the MUs on it move in reverse ( true ) or forward ( false ).

Remarks

When moving in reverse the MUs enter the Conveyor at its exit and leave it at its entrance.

If you cleared Acceleration of the Conveyor , it reverses the direction in which it moves immediately without decelerating and accelerating.

If you selected Acceleration , the Conveyor slows down until its speed is 0. Then it reverses the direction in which it moves and accelerates until it reaches its final speed.

If you set a Target Distance for the Transporter , you cannot change the attribute Backwards .

Type

Attribute

Syntax

&lt; Path &gt;.Backwards:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyConveyor.Backwards := false

SimTalk

AccelerationEnabled [SimTalk] - Conveyor

TargetDistance [SimTalk]

See also

Backwards [Conveyor]

Acceleration [check box] - Conveyor

##### Capacity [SimTalk] - Conveyor

Sets the Capacity , i.e., the number of MUs or MU parts that may be located on the Conveyor designated by &lt;Path&gt; as a whole or in part at any one time.

Remarks

When this number is reached, the Conveyor does not accept any further MUs , even if its full length is not exhausted.

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
if MyConveyor.Capacity = -1
	@.move(AEstreet)
end
```

See also

Capacity [text box] - Conveyor

NumMUParts [SimTalk] - material flow objects CurrentSpeed [SimTalk] - Conveyor Sets the Current Speed of the Conveyor designated by &lt;Path&gt; in the forward direction (positive number) or in reverse (negative number).

Remarks

Specify any real number.

You can only set the Current Speed after you activate Acceleration / AccelerationEnabled .

Type

Attribute

Syntax

&lt; Path &gt;.CurrentSpeed:speed

Watchable

The attribute is watchable for special values.

By watching this value, you might, for example, detect the event when the Conveyor has reached its Final Speed .

Assignment Value

You can assign a value of data type speed .

Return Value

If you specify -1 for an infinite speed, the return value is inf .

Example

```simtalk
MyConveyor.CurrentSpeed := 2
```

SimTalk

AccelerationEnabled [SimTalk] - Conveyor

**See also Current Speed [text box] - Conveyor**

Acceleration [check box] - Conveyor Deceleration [SimTalk] - Conveyor Sets the deceleration with which the Conveyor designated by &lt;Path&gt; decreases its speed.

Remarks

Specify any real number greater than or equal to 0.

You can only set the Deceleration after you activate Acceleration / AccelerationEnabled .

Type

Attribute

Syntax

&lt; Path &gt;.Deceleration:acceleration

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type acceleration .

Example

```simtalk
MyConveyor.Deceleration := 1
```

SimTalk

AccelerationEnabled [SimTalk] - Conveyor

See also

Deceleration [text box] - Conveyor

Acceleration [check box] - Conveyor

##### EnforceMUDistance [SimTalk]

Makes the Conveyor designated by &lt;Path&gt; keep the specified MU Distance between the MUs , even if the MUs accumulate on the Conveyor ( true ) or not ( false ).

**Remarks**

**Note**

This setting only applies if the Conveyor is Accumulating and conveys parts in the forward direction.

**Note**

Depending on the setting MU Distance Type and the Speed of succeeding Conveyors the MU distance might increase,

**Note**

Changing the material flow, either via information flow or manually, might temporarily decrease the MU Distance .

- If you insert MUs on the Conveyor via information flow or if you increase the length of the inserted MU , and thus violate the specified MU Distance , the respective MUs stop until the MU Distance is met again.
- If you create MUs on a Conveyor via information flow, the created MUs stop until the MU Distance is met again. The following MU keeps the distance to the previous MU instead of to the created MU , until the created MU starts moving.
- If you change the MU Distance of the Conveyor via information flow while MUs are located on it, the MUs keep their original distance at first. If the MUs are stopped later on, for example because they accumulate on the Conveyor , they only start moving again when the new distance is met.

Type

Attribute

Syntax

&lt; Path &gt;.EnforceMUDistance:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Example**

MyConveyor.EnforceMUDistance := true

SimTalk

MUDistance [SimTalk]

See also

MU Distance Type [text box]

Enforce MU Distance [check box]

MU Distance [text box] - Conveyor

Accumulating [check box] - Conveyor Length [SimTalk] - Conveyor Sets the Length of the Conveyor designated by &lt;Path&gt;.

Remarks

Length and Speed form the processing time on the object.

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

MyConveyor.Length := 10.0m

SimTalk

Speed [SimTalk] - Conveyor

See also

Length [text box] - Conveyor

##### MUDistance [SimTalk]

Sets the desired distance of the current MU to the succeeding MU which the Conveyor designated by &lt;Path&gt; enforces, when the next MU enters.

**Remarks**

Depending on the setting for the MU Distance Type , the MU Distance determines for:

- Gap the distance between the rear of the preceding MU and the front of the succeeding MU .
- Pitch the distance between the front of the preceding MU and the front of the succeeding MU .

<!-- image -->

<!-- image -->

If no further parts arrive, the Conveyor stops once the distance has been reached. As soon as the next MU arrives, it starts to transport MUs again.

The default value -1 means that the Conveyor does not use the MU Distance and that MUs can enter at any time as the predecessor provides them.

**Note**

If the preceding Conveyor transports parts faster/slower than the Conveyor , which uses a MU Distance , the distance itself can become greater/smaller. This is because the entering part moves with a faster/ slower speed until its Conveyor point is located on the conveyor using a MU Distance .

If the succeeding Conveyor transports parts faster/slower than the Conveyor , which uses a MU Distance , the distance itself can become greater/smaller. This is because the booking point of the leaving MU is located on the succeeding Conveyor , which transports MUs with a faster/slower speed.

**Note**

Plant Simulation only runs the distance check when a MU enters. If you selected Accumulating for example the distance can be undercut when the MUs accumulate.

**Note**

The Conveyor only uses the MU Distance if it transports parts in the forward direction.

Type

Attribute

Syntax

&lt; Path &gt;.MUDistance:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyConveyor.MUDistance := 1
```

See also

MU Distance Type [text box]

MU Distance [text box] - Conveyor

Model a Fixed Gap or a No Gap Conveyor

Accumulating [check box] - Conveyor

##### MUDistanceType [SimTalk]

Sets the MU Distance Type of the MU Distance of the Conveyor designated by &lt;Path&gt;.

**Remarks**

**Note**

Plant Simulation only runs the distance check when a MU enters. If you selected Accumulating for example, the distance can fall below the value once the MUs accumulate.

- Gap sets the distance between the rear of the succeeding MU and the front of the preceding MU .
- Pitch sets the distance between the front of the succeeding MU and the front of the preceding MU .
- Minimum Gap sets the minimum distance between the rear of the preceding MU and the front of the succeeding MU . This setting prevents the Conveyor from stopping and from waiting for new MUs and enables it to run dry.

<!-- image -->

<!-- image -->

<!-- image -->

**MUDistanceType [SimTalk]**

- Minimum Pitch sets the minimum distance between the front of the preceding MU and the front of the succeeding MU . This setting prevents the Conveyor from stopping and from waiting for new MUs and enables it to run dry
- Multiple Gap sets the distance between the rear of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance .

Just as for the setting Minimum Gap , the Conveyor does not stop to wait for new MUs after the gap has passed, but the next MU can only enter the Conveyor if an integer multiple of the gap can be preserved.

- Multiple Pitch sets the distance between the front of the preceding MU and the front of the succeeding MU . The distance can be an integer multiple of the defined MU Distance .

Just as for the setting Minimum Pitch the Conveyor does not stop to wait for new MUs after the pitch has passed, but the next MU can only enter the Conveyor if an integer multiple of the pitch can be preserved.

For this setting the Conveyor behaves like a chain conveyor.

Type

Attribute

Syntax

```simtalk
< Path >.MUDistanceType:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Gap" , "Pitch" , "Minimum Gap" , "Minimum Pitch" , "Multiple Gap" , or "Multiple Pitch" .

**Example**

```simtalk
MyConveyor.MUDistanceType := "Pitch"
```

See also

MU Distance Type [text box]

MU Distance [text box] - Conveyor

Model a Fixed Gap or a No Gap Conveyor

Accumulating [check box] - Conveyor Speed [SimTalk] - Conveyor Sets the Speed with which the Conveyor designated by &lt;Path&gt; transports the MUs .

Remarks

Speed and Length form the Processing Time on the object.

The Processing Time is the Length divided by the Speed . You can also enter -1 for an infinite speed.

**Note**

When you change the Speed Plant Simulation re-computes all events relating to the Speed for all MUs located on the object. If the MU located at the exit of the object is neither blocked nor stopped , it may happen that a new Out event is scheduled. In this case the Exit Control is called again independent of the attribute ExitControlOnce .

Type

Attribute

Syntax

< Path >.SpeedCtrl:speed

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type speed .

Example

```simtalk
MyConveyor.Speed := 0.5 // meters per second
```

SimTalk

Length [SimTalk] - Conveyor

ExitCtrlOnce [SimTalk]

**See also Speed [text box] - Conveyor**

**Out event**

SpeedCtrl [SimTalk] - Conveyor

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

The Conveyor/loading space of type Line of the Transporter designated by &lt;Path&gt; run the Method as soon as they reach their final speed after accelerating or decelerating or when they stop after decelerating.

The Speed Control is not called if the speed changes without using up any time at all.

If you did not enter a Method , the attribute is VOID.

You can only set the Speed Control after you activate Acceleration AccelerationEnabled .

Type

Attribute

Syntax

&lt; Path &gt;.SpeedCtrl:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyConveyor.SpeedCtrl := &mySpeedControl
```

SimTalk

AccelerationEnabled [SimTalk] - Conveyor

See also

Speed Control [Conveyor]

Acceleration [check box] - Conveyor Time [SimTalk] - Conveyor Sets the Time which the MU spends moving on the Conveyor designated by &lt;Path&gt;.

Remarks

Time divided by Length yield the Speed of the object.

Type

Attribute

Syntax

< Path >.Time:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyConveyor.Time := 60
```

SimTalk

Length [SimTalk] - Conveyor

See also

Time [text box] - Conveyor

##### Width [SimTalk] - Conveyor

Width [SimTalk] - Conveyor

Sets the Width of the Conveyor designated by &lt;Path&gt;.

Remarks

**Note**

If you deactivate TransferLengthToObject , the Width does not affect how the Conveyor is shown in the Frame in 2D.

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

MyConveyor.Width := 4 -- meters

SimTalk

TransferLengthToObject [SimTalk]

**CurveWidth [SimTalk]**

See also

Curve Width

Width [text box] - AngularConverter

