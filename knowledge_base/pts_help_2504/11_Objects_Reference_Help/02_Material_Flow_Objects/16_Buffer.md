### Buffer

#### Buffer [object]

Use the Buffer for temporarily holding a large number of parts and then pass them on.

**Icon**

<!-- image -->

**Description**

Insert a Buffer between two components of your plant:

- To temporarily hold parts , if one of the components following it in the sequence of stations fails, preventing the preceding machines to stop producing parts.
- To move parts on , if the preceding components stop working, preventing the production process from grinding to a halt.

Dimensioning a Buffer with a large enough capacity for covering all failures leads to a complete decoupling of the respective components of your plant. The Buffer not only tides over failure times but also serves as a compensating station for fluctuating transport and operating times, which lead to queues forming in front of a machine or a component. But even then it cannot always prevent the material flow from being interrupted or grinding to a halt.

As the Buffer does not have individual places, it does not have to divide the processing time, i.e., the time during which the part remains in it, into small individual steps. Instead, you can select the sequence in which the parts exit the Buffer .

**Select the Buffer Type**

- Queue to make the parts exit the Buffer in the same order in which they entered it ( F irst I n F irst O ut).
- Stack to make the part , which entered last, leave the Buffer first ( L ast I n F irst O ut).

**Note**

Each MU remains for at least the time in the Buffer , which you entered as the Dwell Time . For the Buffer Type &gt; Stack a MU can only exit the Buffer , when all parts, which entered the Buffer after the current part, have already exited the Buffer , i.e., when the MU is located at the very top of the stack.

To show a tooltip with information about the Buffer , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Buffer , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

<!-- image -->

<!-- image -->

The Buffer is ideally suited for modeling a buffer with a great Capacity requiring high performance. If you need more advanced functions, you can use the PlaceBuffer .

We offer alternative graphics for the Buffer in 3D . Click Exchange Graphics in the 3D window of the Buffer and select an alternative graphic.

<!-- image -->

Plant Simulation shows the MUs in the Buffer in 3D stacked if it only has a single animation point.

Add the Object to the Simulation Model

To add the Buffer to your simulation model, click MaterialFlow &gt; Buffer on the Home ribbon tab.

See also

Buffer Parts within the Production Line

Use a Buffer between Processing Stations

Properties of the DataQueue

Properties of the DataStack Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

Video on YouTube

[https://youtu.be/PgT4wkT2Xj8?si=Udlvoq8KcAI9GxQw&amp;t=18](https://youtu.be/PgT4wkT2Xj8?si=Udlvoq8KcAI9GxQw&t=18)

#### Dialog Box of the Buffer

Dialog Box of the Buffer

Double-click the icon of the Buffer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/PgT4wkT2Xj8?si=d4Sx9mjGHp\_Pl0wB&amp;t=98](https://youtu.be/PgT4wkT2Xj8?si=d4Sx9mjGHp_Pl0wB&t=98)

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Capacity [text box] - Buffer

Capacity [text box] - Buffer

Type in the Capacity , i.e., the number of MUs , which the Buffer can hold.

<!-- image -->

Type in -1 for an infinite capacity.

As the capacity is not implemented in a matrix, you cannot access any individual place! You can only reduce the Capacity , if the new capacity you enter is greater than or equal to the actual number of MUs which are located in the Buffer .

SimTalk

Capacity [SimTalk] - Buffer

###### Buffer Type [drop-down list]

Select the Buffer Type , i.e., the exit behavior of the MUs from the Buffer :

<!-- image -->

- Queue : The parts exit the Buffer in the same order in which they entered it ( F irst I n F irst O ut).
- Stack : The part , which entered last, leaves the Buffer first ( L ast I n F irst O ut).

**SimTalk**

BufferType [SimTalk]

Show Fill Level [check box] - Buffer

To show the relative fill level of the buffer as a colored bar at the bottom of its icon in the Frame in 2D, select this check box.

<!-- image -->

<!-- image -->

To hide the fill level indicator, clear the check box.

<!-- image -->

SimTalk

ShowFillLevel [SimTalk] - Buffer

See also

Fill Level in 3D

Check the Fill Level of the Buffers in the Plant

Tab Times

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Dwell Time [Buffer]

Recovery Time [general description]

Recovery Time Starts

**Cycle Time [general description]**

**Dwell Time [Buffer]**

###### Dwell Time [Buffer]

Type in the Dwell Time for which the MUs remain in the Buffer .

For the Buffer you can only specify a constant Dwell Time . Statistics counts the Dwell Time as waiting time and not as processing time.

The Dwell Time thus is not prolonged by failures or pauses .

<!-- image -->

**Note**

Each MU remains for at least the time in the Buffer , which you entered as the Dwell Time . For the Buffer Type &gt; Stack a MU can only exit the Buffer , if all parts which entered the Buffer after the current part, have already exited the Buffer , i.e., when the MU is located at the very top of the stack.

**SimTalk**

ProcTime [SimTalk] - material flow objects

putAttributeNamesIntoTable [SimTalk] - objects

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

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics [Buffer]

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Check the Fill Level of the Buffers in the Plant

Resource Statistics [check box]

Resource Type

**Tab Energy**

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Select costs settings for the object on the Tab Costs .

While the Buffer buffers parts costs accrue which result from the sum of the investment costs and the operating costs.

Note

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part, proportional to the capacity, as accrued costs .

If the Buffer is empty, the costs remain with the Buffer as general costs .

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

| Refresh [on View menu]                     | Forward Blocking List     |
|--------------------------------------------|---------------------------|
| Show Statistics Report [on View menu]      | Exit Blocking List        |
| Show Attributes and Methods [on View menu] | Associated Lockout Zones  |
| Contents [material flow objects]           | Associated Shift Calendar |

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

#### Methods of the Buffer

Methods of the Buffer

The Buffer provides:

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

#### Read-Only Attributes of the Buffer

Read-Only Attributes of the Buffer

The Buffer provides:

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyBuffer.NumChildren

**Attributes of the Buffer**

#### \_Attributes of the Buffer

The Buffer provides:

- The attributes listed in the table of contents to the left.
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
Buffer.BufferType := "Queue"
print Buffer.BufferType
posit := MyStation.Cont.XPos
```

BufferType [SimTalk]

Sets the Buffer Type of the Buffer designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.BufferType:string

Assignment Value

You can assign a value of data type string :

- Specify "Queue" to make the parts exit the Buffer in the same order in which they entered it ( F irst I n F irst O ut).
- Specify "Stack" to make the part , which entered last, leave the Buffer first ( L ast I n F irst O ut).

Example

```simtalk
Buffer.BufferType := "Queue"
```

See also

Buffer Type [drop-down list]

##### Capacity [SimTalk] - Buffer

Capacity [SimTalk] - Buffer

Sets the Capacity , i.e., the maximum number of MUs that can be located in the Buffer designated by &lt;Path&gt;.

Remarks

As the Capacity is not implemented in a matrix, you cannot access any individual place! You can only reduce the Capacity , when the new capacity you enter is greater than or equal to the actual number of MUs located in the Buffer .

Type

Attribute

Syntax

&lt; Path &gt;.Capacity:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

The value -1 designates an infinite capacity.

Example

```simtalk
Buffer.Capacity := 12
```

See also

Capacity [text box] - Buffer

ShowFillLevel [SimTalk] - Buffer

Sets if the Buffer designated by &lt;Path&gt; shows its fill level below its icon in the Frame in 2D ( true ) or not ( false ).

Remarks

Show Fill Level is only available in a 2D Only model .

The fill level looks like this below the icon of the object.

<!-- image -->

| Fill Level On   | Fill Level Off   |
|-----------------|------------------|

Type

Attribute

Syntax

&lt; Path &gt;.ShowFillLevel:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Buffer.ShowFillLevel := true

See also

Show Fill Level [check box] - Buffer

Fill Level in 3D

