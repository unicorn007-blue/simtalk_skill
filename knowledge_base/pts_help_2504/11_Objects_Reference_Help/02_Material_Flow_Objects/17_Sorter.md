### Sorter

#### Sorter [object]

Use the Sorter for sorting parts according to different sort criteria.

Icon

<!-- image -->

Description

The MUs exit the Sorter according to the priorities you set. The Sorter moves the part with the highest priority first, regardless of the time at which it entered. You can define the priority of the part with the Sort Criterion and the Sort Order . The data type of the sort criterion must be real or convertible to real .

The sort criterion can be:

- Occupation time
- MU-Property
- Method

If you select a Descending sort order, the Sorter moves the part with the highest value, with respect to the sort criterion, first.

If you select an Ascending sort order, the Sorter moves the part with the lowest value first.

The Sorter sorts the MUs again when:

- Another MU enters.
- Its contents changes because you access it.

If you want to sort the MUs located on the Sorter only when a MU enters, Plant Simulation assumes that the sort criterion does not change during the time the MUs stay on the Sorter . In this case, Plant Simulation adds new MUs to the existing order of MUs located on it.

If the value of the sort criterion depends on the time, for example the battery charge of a Transporter , Plant Simulation sorts the MUs every time the contents changes, especially before a MU moves.

If a MU does not have a sort criterion, or its data type cannot be converted to real , the MU sequence on the object is undefined, and Plant Simulation shows an error message in the Console . If there are several MUs with the same value for the sort criterion, the order of these MUs with respect to each other is not defined.

We offer alternative graphics for the Sorter in 3D . Click Exchange Graphics in the 3D window of the Sorter and select an alternative graphic.

<!-- image -->

Plant Simulation shows the parts in the Sorter in 3D stacked, even if it only has a single animation point.

To show a tooltip with information about the Sorter , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Sorter , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Sorter to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MaterialFlow &gt; Sorter on the Home ribbon tab.

Video on YouTube

[https://youtu.be/PgT4wkT2Xj8?si=hMlMEbeZIVuOiJ4t&amp;t=170](https://youtu.be/PgT4wkT2Xj8?si=hMlMEbeZIVuOiJ4t&t=170)

#### Dialog Box of the Sorter

Dialog Box of the Sorter

Double-click the icon of the Sorter to open its dialog box.

<!-- image -->

<!-- image -->

###### Tab Attributes

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Video on YouTube

[https://youtu.be/PgT4wkT2Xj8?si=-sWlE9UdP0r\_cBT8&amp;t=210](https://youtu.be/PgT4wkT2Xj8?si=-sWlE9UdP0r_cBT8&t=210)

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Capacity [text box] - Sorter

Type in the Capacity of the Sorter .

<!-- image -->

Type in -1 for an infinite capacity.

The capacity is the maximum number of MUs that the Sorter can sort at any one time.

You can access a specific place in the Sorter by using its index.

SimTalk

Capacity [SimTalk] - Sorter

**Sort Order [drop-down list]**

###### Sort Order [drop-down list]

Select how the Sorter sorts the MUs located on it, in ascending or in descending order.

<!-- image -->

- A Descending sort order moves the MU with the highest value, with respect to the sort criterion, first.
- An Ascending sort order moves the MU with the lowest value first.

**SimTalk**

Order [SimTalk]

###### Time of Sort [drop-down list]

Select when the Sorter sorts the MUs that are located on it:

<!-- image -->

**· On Entry**

Plant Simulation sorts the MUs into the sequence of parts each time a new MU enters. Plant Simulation does not update the sequence of MUs , even if the values of the sort criteria change. Thus, we recommend to only select On Entry when the value of the attribute or the method you use as the sort criterion does not change while a MU is located on the Sorter .

**· On Access**

Plant Simulation dynamically sorts newly entered MUs . After a new MU enters the Sorter or before a MU leaves it, it sorts the MUs with the current values of the sort criterion for all MUs anew.

**SimTalk**

TimeOfSort [SimTalk]

###### Sort Criterion [drop-down list]

Select the Sort Criterion . Depending on the setting you select, Plant Simulation shows additional dropdown lists and/or text boxes.

**· Occupation Time**

For the setting Occupation Time Plant Simulation sorts the MUs according to the time they remained on the Sorter .

For the Sort Order &gt; Descending , the Sorter uses the FIFO rule ( F irst I n F irst O ut).

For an Ascending sort order, the Sorter uses the LIFO ( L ast I n F irst O ut) rule.

**Note**

The exit sequence of MUs that entered the Sorter at the same time is not defined as the time they spent on the Sorter is identical.

<!-- image -->

**· MU-Property**

For the setting MU-Property Plant Simulation shows two more drop-down lists to the right for selecting the sorting criteria.

<!-- image -->

Select the sorting criteria for the sorting category you selected, from the right drop-down list.

| MU-Property         | Possible Sort Criteria                                                                                           |
|---------------------|------------------------------------------------------------------------------------------------------------------|
| Attribute           | Length, Booking Point, Capacity, Speed                                                                           |
| Product Statistics  | Production Time, Transport Time, Storage Time, Waiting Time, Working Time, Failure Time, Pause Time, Set-up Time |
| Resource Statistics | Entries, Exits, Contents, Initial Contents, Max. Contents, Min. Contents, Relative Occupation                    |
| Driving Statistics  | Occupation Time, Empty Time, Home-Driving Time, Battery Charge Count, Battery Charge Time                        |

| MU-Property            | Possible Sort Criteria                                                                                                                                                   |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Battery Attribute      | Battery Charge, Battery Capacity, Battery Reserve, Battery Charge Current, Battery Basic Consumption, Battery Driving Consumption                                        |
| User-defined Attribute | Type the name of the user-defined attribute into the text box. The user-defined attribute has to have the data type integer or real . The data type sets the sort order. |

**Note**

Sorting according to statistical data applies only if statistics for MUs is activated.

**· Method**

For the setting Method you define your own sort criteria. The sort criterion is the return value of a user-defined method which Plant Simulation calls for each MU . This way, you can also sort the objects according to two or more attributes.

<!-- image -->

Or select the Method in a Frame , drag it to the text box and drop it there.

A sort method might, for example, look like this:

```simtalk
-> real // the
return value has the type "real" // the priority results from the volume, i.e., the user-defined // attributes "Width" and "Height" and the attribute "Length"
result := @.Width * @.Height * @.Length
```

**Note**

When using a Method , you may not use any actions, which interfere with the material flow, i.e., you may not transfer MUs , delete objects, etc. You may only use read-only access, you cannot change any simulation-relevant parameters of the model.

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
- The standard sort method as a user-defined attribute looks like this:

<!-- image -->

###### Start Sorting [button]

To sort the MUs according to the sort criteria you defined, click this button.

SimTalk

sort [SimTalk] - Sorter

##### Tab Times [Sorter]

Tab Times [Sorter]

Define the Recovery Time and the Cycle Time as described under the Tab Times .

The Sorter does not have a Set-up Time . The Processing Time always is zero.

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

While the Sorter sorts parts costs accrue which result from the sum of the investment costs and the operating costs.

Note

The investment costs only accrue during the Depreciation Period .

The costs are allocated to the part, proportional to the capacity, as accrued costs .

If the Sorter is empty, the costs remain with the Sorter as general costs .

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

##### Methods of the Sorter

#### Methods of the Sorter

The Sorter provides:

- The method sort [SimTalk] - Sorter .
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

sort [SimTalk] - Sorter

Sorts the MUs located on the Sorter designated by &lt;Path&gt; according to the settings which you selected.

Type

Method

Syntax

&lt; Path &gt;.sort

Example

MySorter.sort

See also

Start Sorting [button]

#### Read-Only Attributes of the Sorter

Read-Only Attributes of the Sorter

The Sorter provides:

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

**Attributes of the Sorter**

#### \_Attributes of the Sorter

The Sorter provides:

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
MySorter.Order := "ascending"
print MySorter.Order
posit := MyStation.Cont.XPos
```

##### Capacity [SimTalk] - Sorter

Capacity [SimTalk] - Sorter

Sets the number of MUs which the Sorter designated by &lt;Path&gt; can hold, i.e., its capacity .

Type

Attribute

Syntax

&lt; Path &gt;.Capacity:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
Sorter.Capacity := 10
```

See also

Capacity [text box] - Sorter

##### CustSortAttr [SimTalk]

Sets the name of a user-defined attribute which the Sorter designated by &lt;Path&gt; uses as sort criterion when you select the Sort criterion &gt; MU-Property .

**Remarks**

| MU-Property            | Possible Sort Criteria                                                                                                                                                    |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Attribute              | Length, Booking Point, Capacity, Speed                                                                                                                                    |
| Product Statistics     | Production Time, Transport Time, Storage Time, Waiting Time, Working Time, Failure Time, Pause Time, Set-up Time                                                          |
| Resource Statistics    | Entries, Exits, Contents, Initial Contents, Max. Contents, Min. Contents, Relative Occupation                                                                             |
| Driving Statistics     | Occupation Time, Empty Time, Home-Driving Time, Battery Charge Count, Battery Charge Time                                                                                 |
| Battery Attribute      | Battery Charge, Battery Capacity, Battery Reserve, Battery Charge Current, Battery Basic Consumption, Battery Driving Consumption                                         |
| User-defined Attribute | Enter the name of the user-defined attribute into the text box. The user-defined attribute has to have the data type integer or real . The data type sets the sort order. |

Type

Attribute

Syntax

```simtalk
< Path >.CustSortAttr:string
```

Assignment Value

You can assign a value of data type string .

The user-defined attribute itself has to have the data type integer or real ; it sets the sort order.

Example

```simtalk
Sorter.CustSortAttr := "MySortAttribute"
```

**See also**

**Sort Criterion [drop-down list]**

##### Order [SimTalk]

Sets the order in which the Sorter designated by &lt;Path&gt; sorts the parts.

Type

Attribute

Syntax

&lt; Path &gt;.Order:string

Assignment Value

You can assign a value of data type string .

You can specify "Ascending" or "Descending" .

Example

```simtalk
MySorter.Order := "ascending"
```

See also

Sort Order [drop-down list]

##### SortCriterion [SimTalk]

SortCriterion [SimTalk]

Sets the sort criterion which the Sorter designated by &lt;Path&gt; uses when sorting the parts.

Type

Attribute

Syntax

&lt; Path &gt;.SortCriterion:string

Assignment Value

You can assign a value of data type string .

You can specify "Occupation Time" , "MU-Property" , or "Method" .

Example

MySorter.SortCriterion := "MU-Property"

See also

Sort Criterion [drop-down list]

##### SortMethod [SimTalk]

Designates the name of the Method object of the Sorter designated by &lt;Path&gt;.

Remarks

The source code of the Method defines a user-defined sort criterion which the Sorter uses when you set the Sort Criterion &gt; Method .

Type

Attribute

Syntax

```simtalk
< Path >.SortMethod:object´
```

Assignment Value

You can assign a value of data type object .

Example

```simtalk
MySorter.SortCriterion := "myMethod"
MySorter.SortMethod := findPriority
```

See also

Sort Criterion [drop-down list] &gt; Method

##### SortProperty [SimTalk]

Sets the sort property that the Sorter designated by &lt;Path&gt; uses for sorting the parts.

Remarks

SortProperty applies for the setting Sort criterion &gt; MU-Property .

| MU-Property            | Possible Sort Criteria                                                                                                                                                    |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Attribute              | Length, Booking Point, Capacity, Speed                                                                                                                                    |
| Product Statistics     | Production Time, Transport Time, Storage Time, Waiting Time, Working Time, Failure Time, Pause Time, Set-up Time                                                          |
| Resource Statistics    | Entries, Exits, Contents, Initial Contents, Max. Contents, Min. Contents, Relative Occupation                                                                             |
| Driving Statistics     | Occupation Time, Empty Time, Home-Driving Time, Battery Charge Count, Battery Charge Time                                                                                 |
| Battery Attribute      | Battery Charge, Battery Capacity, Battery Reserve, Battery Charge Current, Battery Basic Consumption, Battery Driving Consumption                                         |
| User-defined Attribute | Enter the name of the user-defined attribute into the text box. The user-defined attribute has to have the data type integer or real . The data type sets the sort order. |

Type

Attribute

Syntax

```simtalk
< Path >.SortProperty:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MySorter.SortProperty := "Length"
```

See also

Sort Criterion [drop-down list]

##### TimeOfSort [SimTalk]

TimeOfSort [SimTalk]

Sets the property according to which the Sorter designated by &lt;Path&gt; sorts the parts.

Type

Attribute

Syntax

```simtalk
< Path >.TimeOfSort:string
```

Assignment Value

You can assign a value of data type string .

You can specify "on entry" or "on access" .

Example

```simtalk
MySorter.TimeOfSort := "on access"
```

See also

Time of Sort [drop-down list]

