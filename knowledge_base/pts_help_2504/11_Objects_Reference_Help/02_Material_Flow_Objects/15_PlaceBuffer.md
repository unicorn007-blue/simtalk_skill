### PlaceBuffer

```simtalk
print place.MU(i)
next // Returns the topmost MU of the stack: Store[1,1].Cont // Returns the second MU from the top on the place 1,2: Store[1,2].MU(2)
```

**SimTalk**

XDim [SimTalk] - Store

YDim [SimTalk] - Store

getStackHeight [SimTalk]

See also

Z-Dimension [Store]

Stack Parts in the Store

Unload Stacked Parts

mu [SimTalk] - pe, Store

**PlaceBuffer**

#### PlaceBuffer

Use the PlaceBuffer to process parts on a number of buffer places, which are arranged in a row, one behind the other. It is not part of the built-in objects that the Toolbox provides by default.

Icon

<!-- image -->

**Description**

The MUs , which the PlaceBuffer processes have to advance from place to place and can only leave the PlaceBuffer after they passed the last place. This way, you can call and access each and every place individually.

**Note**

We do not show the PlaceBuffer in new models by default. You have to add it yourself to your model.

- If Sequentially Indexing is cleared, you can only set the Processing Time for the PlaceBuffer as a whole, not for the individual places. The Processing Time is equally distributed across all places. For a Processing Time of one minute and a Capacity of three places each place has a processing time of 20 seconds.

A part can move directly to an idle place in the PlaceBuffer if Sequentially Indexing is cleared. After the part has passed this and all succeeding places, it can exit the PlaceBuffer . If you create a part on an idle place, it does not have to pass this place, but may move on to the next place or to the next object.

- If Sequentially Indexing is checked, the Processing Time for moving the part on to the next place is used up. For a capacity of four the threefold processing time passes at least before the part can leave the PlaceBuffer , as three move processes have to take place. The time can be extended through waiting times.

The PlaceBuffer moves the part cyclically on to its successors. In case the first part cannot leave the PlaceBuffer , you can set how it moves on:

- To make the MUs accumulate on the PlaceBuffer , select the check box Accumulating . This enables the MUs to move front to end to each other, when the exit of the PlaceBuffer is Blocked .
- To make the MUs retain their distance to each other, i.e., make all succeeding MUs stop moving when the preceding MU cannot exit the PlaceBuffer , clear Accumulating .

The default graphic of the PlaceBuffer in 3D is a table with a size of 2 by 1 by 1 meter on whose surface up to four parts are moved on in the X-Direction . When scaling the PlaceBuffer , typically only in the X-Direction , the pre-defined animation area is scaled as well so that you only have to adjust the Capacity .

We offer two 3D-graphics for the PlaceBuffer :

- The graphic Table2x1x1modular.jt in the folder jt-graphics which you can import into any object.
- The alternative graphic PlacebufferModular.s3d in the folder s3d-graphics\BuffersAndSorters , allowing you to adapt the size of the table to your needs by changing the individually transformable graphics parts without changing the thickness of the elements of the table.

In 3D, you can also set the Animation Area on which the PlaceBuffer animates the parts .

Note the following:

1. If the Animation Area is active, the PlaceBuffer uses it. In this case the index of the MU is the index of the area in the X-Direction . The capacity in the Y-Direction is always 1.
2. If a MU animation path named Default with more than one anchor points exists, the index of the MU is converted into a relative position. The MUs are then equally distributed on this line.
3. In all other cases the PlaceBuffer uses the first path for the first MU , the second path for the second MU , etc. If no suitable path exists, but a path named Default exists, that consists of a single point only, the PlaceBuffer uses that path.

<!-- image -->

If you want to model a buffer with a large capacity that has to be fast, we recommend to use the object Buffer .

To show a tooltip with information about the PlaceBuffer , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the PlaceBuffer , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the PlaceBuffer to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; PlaceBuffer on the Home ribbon tab.

#### Dialog Box of the PlaceBuffer

Dialog Box of the PlaceBuffer

Double-click the icon of the PlaceBuffer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Capacity [text box] - PlaceBuffer

Capacity [text box] - PlaceBuffer

Type in the Capacity , i.e., the number of places of the PlaceBuffer .

<!-- image -->

<!-- image -->

Type in -1 for an unlimited number of places if Sequentially Indexing is active. You can access the individual places of the PlaceBuffer by their index. You can only reduce the Capacity , if enough places are empty.

You can only change the Capacity if no parts are located in the PlaceBuffer , i.e., if it is empty.

SimTalk

Capacity [SimTalk] - PlaceBuffer

See also

Sequentially Indexing [check box]

###### Sequentially Indexing [check box]

To only start the Processing Time on a place of the PlaceBuffer when the succeeding place is free, select this check box.

<!-- image -->

**Note**

In Sequentially Indexing mode, the Processing Time does not represent the time for which a part is processed on a place, but the time used for moving the part from its current place to the succeeding place. Suppose that we have a capacity of four, then the Processing Time passes three times before the part can leave the PlaceBuffer , because three move processes have to take place.

The total time can get longer because of waiting times. For this reason no time is used on the last place and the part can exit the PlaceBuffer immediately once it reaches the last place, provided the successor can accept the part.

If Sequentially Indexing is cleared, the default behavior of the PlaceBuffer applies.

You can only set the Processing Time for the PlaceBuffer as a whole, not for the individual places. The Processing Time is equally distributed across all places and divided by the number of places. For a Processing Time of one minute and a capacity of three places each place has a processing time of 20 seconds.

SimTalk

SequentiallyIndexing [SimTalk]

See also

Processing Time [PlaceBuffer]

Capacity [text box] - PlaceBuffer

**Accumulating [check box] - PlaceBuffer**

###### Accumulating [check box] - PlaceBuffer

To make the MUs accumulate on the PlaceBuffer , select this check box.

<!-- image -->

This enables the MUs to move front to end to each other, if the exit of the PlaceBuffer is Blocked .

To make the MUs retain their distance to each other, i.e., to make all succeeding MUs stop moving when the preceding part cannot exit the PlaceBuffer , clear Accumulating . If the preceding part cannot exit and if Accumulating is cleared, no additional MU can enter the PlaceBuffer .

<!-- image -->

**SimTalk**

Accumulating [SimTalk] - PlaceBuffer Show Fill Level [check box] - PlaceBuffer To show the relative fill level of the buffer as a colored bar at the bottom of its icon in the Frame , select this check box.

<!-- image -->

<!-- image -->

SimTalk

ShowFillLevel [SimTalk] - PlaceBuffer

Tab Times

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also select a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

**Note**

You can only type in a constant Processing Time for the parts in the PlaceBuffer , no statistical distributions, no dependencies from the part type or no formulas.

**See also**

Processing Time [PlaceBuffer]

Recovery Time [general description]

Recovery Time Starts

Cycle Time [general description]

<!-- image -->

###### Processing Time [PlaceBuffer]

Type in the Processing Time of MUs in the PlaceBuffer .

<!-- image -->

You can only specify a constant Processing Time for the parts in the PlaceBuffer . You can neither select a probability distribution, nor a dependency on the MU type, nor a formula.

For the PlaceBuffer the Processing Time is more of a Dwelling Time than a Processing Time as the parts are not really being processed, but buffered and then moved on.

If Sequentially Indexing is cleared, you can only set the Processing Time for the PlaceBuffer as a whole, not for the individual places. The Processing Time is equally distributed across all places. For a Processing Time of one minute and a Capacity of three places each place has a processing time of 20 seconds.

If Sequentially Indexing is selected, the Processing Time for moving the part on to the next place is used up. For a Capacity of four the threefold Processing Time passes at least before the part can leave the PlaceBuffer , as three move processes have to take place. The time can be extended through waiting times.

SimTalk

ProcTime [SimTalk] - material flow objects

###### Recovery Time/Cycle Time [PlaceBuffer]

Recovery Time/Cycle Time [PlaceBuffer]

The Recovery Time and the Cycle Time are described under the Tab Times .

<!-- image -->

**SimTalk**

RecoveryTime [SimTalk] - material flow objects

CycleTime [SimTalk]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Pull Control .

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

##### Tab Exit

Tab Exit

Select to which of its successors the object moves the MU on the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

##### Tab Statistics

Statistics is described under the Tab Statistics .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

Resource Type

**Tab Energy**

##### Tab Energy

Select energy settings for the object on the Tab Energy .

##### Tab Costs

Select costs settings for the object on the Tab Costs .

While the PlaceBuffer buffers parts costs accrue which result from the sum of the investment costs and the operating costs.

Note

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part, proportional to the capacity, as accrued costs .

If the PlaceBuffer is empty, the costs remain with the PlaceBuffer as general costs .

See also

Simulate the Accrued Costs of the Machines

CostAnalyzer &gt; How the CostAnalyzer Assigns Costs to Part Types

CostAnalyzer &gt; Costs Shown in the Costs Report

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Number of Animation Events [PlaceBuffer]

Click the icon of the PlaceBuffer with the left mouse button and click Edit Icons on the Home ribbon tab.

**Note**

If Sequentially indexing is checked, parts in the PlaceBuffer do not move on triggered by animation events. Sequentially Indexing does not affect the animation.

Go to the Animation ribbon tab of the Icon Editor and select Set Animation Events . Type a number into the text box that determines how often Plant Simulation draws the contents of the PlaceBuffer while a part is located on it.

Plant Simulation only uses the setting Number of Animation Events in special cases for the animation.

Plant Simulation normally computes the Number of Animation Events based on the Processing Time and the capacity of the PlaceBuffer . To speed up the simulation when the PlaceBuffer has a great Capacity , you can type in 0. Then Plant Simulation does not schedule any animation events for the PlaceBuffer and thus does not animate any parts on the PlaceBuffer .

<!-- image -->

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Forward Blocking List     |
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

#### Methods of the PlaceBuffer

Methods of the PlaceBuffer

The PlaceBuffer provides:

- The method pe, [X Y] .
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

##### pe(1) / [ 1] [SimTalk] - PlaceBuffer

pe(1) / [ 1] [SimTalk] - PlaceBuffer

Sets the designated place of the PlaceBuffer designated by &lt;Path&gt;.

Remarks

The PlaceBuffer has several storage places which are arranged in a row one after the other.

Note

If Sequentially Indexing is active, we do not support the method pe .

Type

Method

Syntax

```simtalk
< Path >.pe([Index:integer:=1]) → any < Path >[Index:integer] → any
```

Parameter

The optional parameter Index of data type integer designates the place.

**Default Value of the Parameter**

The default value is 1.

Return Value

The return value has the data type any .

Example

```simtalk
@.move(MyPlaceBuffer[2])
@.move(MyPlaceBuffer.pe(2))
```

See also

Sequentially Indexing [check box]

#### Read-Only Attributes of the PlaceBuffer

Read-Only Attributes of the PlaceBuffer

The PlaceBuffer provides:

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyPlaceBuffer.UUID

#### Attributes of the PlaceBuffer

\_Attributes of the PlaceBuffer

The PlaceBuffer provides:

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
MyPlaceBuffer.Accumulating := true
print MyPlaceBuffer.Accumulating
posit := MyStation.Cont.XPos
```

##### Accumulating [SimTalk] - PlaceBuffer

Sets if the following MUs may move up ( true ) or will have to wait ( false ) if the preceding MU cannot exit the PlaceBuffer designated by &lt;Path&gt;.

Remarks

If the preceding part cannot exit and Accumulating is false , no further MU can enter the PlaceBuffer .

Type

Attribute

Syntax

&lt; Path &gt;.Accumulating:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

MyPlaceBuffer.Accumulating := true

See also

Accumulating [check box] - PlaceBuffer Capacity [SimTalk] - PlaceBuffer Sets the Capacity , i.e., the number of stations of the PlaceBuffer designated by &lt;Path&gt;.

Remarks

The value -1 designates an infinite capacity if SequentiallyIndexing is set to false . You can access the individual locations by their index. You can only reduce the Capacity when enough places are free.

If parts are located in the PlaceBuffer you cannot change its Capacity . You can only change it when it is empty.

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
MyPlaceBuffer.Capacity := 12
```

SimTalk

SequentiallyIndexing [SimTalk]

See also

Sequentially Indexing [check box]

##### SequentiallyIndexing [SimTalk]

Sets if the Processing Time on a place of the PlaceBuffer designated by &lt;Path&gt; only starts when the succeeding place is free ( true ) or not ( false ).

Remarks

In Sequentially Indexing mode, the Processing Time does not represent the time for which a part is processed on a place, but the time used for moving the part from its current place to the succeeding place. Suppose that we have a Capacity of four, then the Processing Time passes three times before the part can leave the PlaceBuffer , because three move processes have to take place.

The total time can get longer because of waiting times. For this reason no time is used on the last place and the part can exit the PlaceBuffer immediately once it reaches the last place, provided the successor can accept the part.

Type

Attribute

Syntax

&lt; Path &gt;.SequentiallyIndexing:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPlaceBuffer.SequentiallyIndexing := true

See also

Sequentially Indexing [check box]

##### ShowFillLevel [SimTalk] - PlaceBuffer

Sets if the PlaceBuffer designated by &lt;Path&gt; shows its fill level below its icon in the Frame in 2D ( true ) or not ( false ).

Remarks

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

MyPlaceBuffer.ShowFillLevel := true

See also

Show Fill Level [check box] - PlaceBuffer

