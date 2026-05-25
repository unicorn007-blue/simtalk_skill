### Trigger

#### Trigger [object]

Use the Trigger for changing values of attributes and global variables according to a pattern you define during a simulation run. It can also activate methods , which then execute the actions you programmed.

Icon

<!-- image -->

**Description**

The Trigger maps times to the values of a variable. User-defined attributes take on values designated by the Trigger during a simulation run. You can specify the values either in a single TimeSequence object or by combining several time sequences of other Triggers . In addition, a Trigger can control how and when a Source creates MUs .

To show a tooltip with information about the Trigger , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Trigger , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Trigger to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Trigger on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Produce Parts Using a Trigger Object

#### Dialog Box of the Trigger

Dialog Box of the Trigger

Double-click the icon of the Trigger to open its dialog box.

<!-- image -->

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Period

Tab Period

The tab Period provides the settings listed in the table of contents to the left.

###### Active [check box] - Trigger

Active [check box] - Trigger

To activate the Trigger during the simulation run, select this check box.

<!-- image -->

To deactivate it, clear the check box.

Instead, you can also right-click the Trigger object in the Frame and select Activate on the context menu.

To deactivate it, select Deactivate on the context menu.

SimTalk

Active [SimTalk] - Trigger

###### Time Reference [Trigger]

Select the time reference which the Trigger uses during the simulation run.

<!-- image -->

- For a Relative time reference, type a point in time ( time ) into the text box Start Time [Trigger] .
- For an Absolute time reference, type a point in time on a certain date ( dateTime ) into the text box Start Date [Trigger] .

<!-- image -->

<!-- image -->

**SimTalk**

Absolute [SimTalk] - Trigger

**Start Time [Trigger]**

###### Start Time [Trigger]

Type in the point in time (of data type time ) at which the Trigger starts working.

<!-- image -->

###### Start Date [Trigger]

Type in the date and the point in time at which the Trigger starts working for the setting Time Reference &gt; Absolute .

<!-- image -->

**Active Interval**

###### Active Interval

Type in the time interval during which the Trigger will be active.

<!-- image -->

After this time interval has elapsed, the Trigger value will assume the default value.

Define the default value under Values &gt; Values &gt; Value Table of the TimeSequence belonging to the Trigger .

SimTalk

ActiveInterval [SimTalk]

###### Repeat Periodically

To make the Trigger repeat the values periodically instead of processing them one time only, select this check box.

Note

Only select this check box after you have set a suitable time unit on the Tab Representation ! Otherwise drawing the display on screen may be time-consuming.

SimTalk

Periodic [SimTalk]

**Period Length**

###### Period Length

Type in the duration of a Trigger's cycle during the simulation run.

When you selected Repeat Periodically , the Trigger repeats the values after a completed cycle.

SimTalk

PeriodLength [SimTalk]

Tab Values

Tab Values

The tab Values provides the settings listed in the table of contents to the left.

Trigger Type

The Trigger Types differ in the way in which they generate events.

Select the Trigger Type .

- The Input Trigger takes the values from a single TimeSequence .

Click Values , and type the values into the Value Table of the TimeSequence.

<!-- image -->

- The Combination Trigger generates a new Trigger by combining existing Triggers .

Click Combination Table and type in the names of the Triggers that are to be combined. Plant Simulation saves the result of the combination in the combination list that clicking Values opens.

<!-- image -->

<!-- image -->

**Values [Trigger]**

###### Values [Trigger]

To open the TimeSequence that contains the current sequence of values of the Trigger , click this button.

<!-- image -->

Type in the default value of the Trigger on the tab Start Values &gt; Default Value .

Instead, you can also right-click the Trigger object in the Frame and select Open Values Table on the context menu.

<!-- image -->

<!-- image -->

###### Combination Table

To open the Combination Table , click this button.

<!-- image -->

Then, type the Trigger objects which Plant Simulation combines into the combination trigger.

<!-- image -->

- Type the name of a TimeSequence into the column Time Sequence . You can access the TimeSequence in the connection Formula with this name. Click one of the entries to open the respective value list.
- Type the path to the source Trigger into the column Origin .
- Type when the Trigger starts working into the column Start Time .
- Type how often the Trigger is going to repeat into the column Count .
- Type when the Trigger stops working, independently of repeated patterns, into the column End Time . If you do not specify a value, no end time applies.

**SimTalk**

CombinationTable [SimTalk]

compute [SimTalk]

**Formula [Trigger]**

###### Formula [Trigger]

For the Combination Trigger you can type in a formula that computes the Trigger's value pattern.

<!-- image -->

The formula connects the Trigger objects, which you typed into the Combination Table . The allowed operations depend on the data type of the involved Triggers .

- For a TimeSequence of data type boolean , you can use the boolean operators AND , OR , and NOT .
- For a TimeSequence with numerical data types, you can use the operators + , -, * , and / .

**Example**

TRIGGER AND TRIGGER2 AND TRIGGER3 weeklyPlan AND dailyPlan employeenum - 2

**SimTalk**

Formula [SimTalk]

Tab Actions

Tab Actions

The tab Actions provides the settings listed in the table of contents to the left.

###### Attributes [Trigger]

Click Attributes below Trigger and type in the names of the objects and the attributes, which the Trigger controls into the list.

<!-- image -->

- First, click the check box to turn Inheritance off. Only then you can type data into the list.
- Type the name of the object that the Trigger controls into the column Object .
- Type the name of the attribute of this object as a string into the column Attribute .

For a Variable object, you do not have to type in an attribute. The Trigger then passes the current value to the attributes of the respective objects.

- When an error occurs in the value assignment during the simulation run, Plant Simulation inserts the respective error message in the column Error Message .

**SimTalk**

insertTriggeredAttr [SimTalk]

deleteTriggeredAttr [SimTalk]

See also

Context Menu of Embedded Lists

**Methods [Trigger]**

###### Methods [Trigger]

Click Methods below Trigger to open a list.

<!-- image -->

Click the check box to turn Inheritance off.

Type in the names of the methods that the Trigger controls. This way, Plant Simulation can call a different Method whenever a value of the Trigger changes. Plant Simulation passes the previous and current trigger values as parameters when the methods are called.

SimTalk

insertTriggeredMeth [SimTalk]

deleteTriggeredMeth [SimTalk]

See also

Context Menu of Embedded Lists

###### Objects [Trigger]

To open a list containing the Source that creates the parts, click this button.

<!-- image -->

The list shows the name of and the path to the Source object which Plant Simulation inserted when you selected Time of creation &gt; Trigger in the dialog of the Source , clicked on Trigger , typed in the name of the Trigger and clicked OK or Apply .

You cannot edit this table.

###### Tab Representation

##### Tab Representation

Define the Value Pattern and the Time Unit which the Trigger uses to show the values over time on the tab Representation .

<!-- image -->

**See also**

**Value Pattern**

Time Unit

<!-- image -->

###### Value Pattern

Shows the value pattern over time in an x-y diagram. The background color is white.

You can also select the Time unit .

<!-- image -->

###### Time Unit

Select a Time Unit from the drop-down list that scales the time axis of the Trigger .

<!-- image -->

- Second
- Minute
- Hour
- Day

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

##### Tools Menu

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the Trigger

\_Methods of the Trigger

The Trigger provides:

- The methods listed in the table of contents to the left.
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

##### compute [SimTalk]

Generates a new value list for the Trigger designated by &lt;Path&gt; for the trigger type Combination .

Remarks

We advise to always call compute when the combination formula changed.

Type

Method

Syntax

< Path >.compute

**Example**

```simtalk
MyTrigger.Formula := "K1 + K2 + K3"
MyTrigger.compute
```

See also

Trigger Type

**deleteTriggeredAttr [SimTalk]**

##### deleteTriggeredAttr [SimTalk]

Deletes the specified methods and attributes from the table Triggered Attributes of the Trigger designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteTriggeredAttr(Object:object, Attribute:string) -&gt; boolean

**Parameters**

- The parameter Object of data type object designates the object.
- The parameter Attribute of data type string designates the attribute to be controlled.

Return Value

The return value has the data type boolean .

Example

MyTrigger.deleteTriggeredAttr(MyTrack,"pause")

SimTalk

insertTriggeredAttr [SimTalk]

See also

Attributes [Trigger]

##### deleteTriggeredMeth [SimTalk]

Deletes the specified Method from the list Triggered Methods of the Trigger designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteTriggeredMeth(Method:object) -&gt; boolean

Parameter

The parameter Method of data type object designates the Method that is to be deleted.

Return Value

The return value has the data type boolean .

Example

MyTrigger.deleteTriggeredMeth(&amp;shift1)

SimTalk

insertTriggeredMeth [SimTalk]

See also

Methods [Trigger]

**insertTriggeredAttr [SimTalk]**

##### insertTriggeredAttr [SimTalk]

Inserts the specified attribute of the specified object into the table Triggered Attributes of the Trigger designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.insertTriggeredAttr(Object:object, Attribute:string)
```

**Parameters**

- The parameter Object of data type object designates the object.
- The parameter Attribute of data type string designates the attribute.

Example

MyTrigger.insertTriggeredAttr(MyTrack,"pause") MyTrigger.insertTriggeredAttr(MyTrack,"length") MyTrigger.insertTriggeredAttr(&MyVariable,"")

SimTalk

deleteTriggeredAttr [SimTalk]

See also

Attributes [Trigger]

##### insertTriggeredMeth [SimTalk]

Inserts the specified Method into the list Triggered Methods of the Trigger designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.insertTriggeredMeth(Method:object)

Parameter

The parameter Method of data type object designates the Method that is to be inserted.

Example

MyTrigger.insertTriggeredMeth(&amp;Shift3)

SimTalk

deleteTriggeredMeth [SimTalk]

See also

Methods [Trigger]

#### Read-Only Attributes of the Trigger

Read-Only Attributes of the Trigger

The Trigger provides:

- The read-only attribute CurrentValue [SimTalk] .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyTrigger.CurrentValue

##### CurrentValue [SimTalk]

Returns the Current Value of the Trigger's designated by &lt;Path&gt;.

Remarks

The data type of the value matches the data type of the Trigger .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentValue → any

Return Value

The return value has the data type any .

Example

print MyTrigger.CurrentValue

See also

Tab Representation

#### Attributes of the Trigger

\_Attributes of the Trigger

The Trigger provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTrigger.Combination := true
MyTrigger.CombinationTable.delete({0,1}..{*,*})
MyTrigger.CombinationTable.writeRow(1,1,Trig5,0,10,3600)
MyTrigger.CombinationTable.createNestedList(0,1) MyTrigger.CombinationTable[0,1].setname("K1")
print MyTrigger.Combination
posit := Station.Cont.XPos
```

Absolute [SimTalk] - Trigger

Sets the Time Reference of the Trigger designated by &lt;Path&gt; to Absolute ( true ) or Relative ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Absolute:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrigger.Absolute := true
```

See also

Time Reference [Trigger]

##### Active [SimTalk] - Trigger

Active [SimTalk] - Trigger

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

Only active Triggers trigger the attributes and methods which you entered. We recommend to not activate Triggers that only hold data.

Type

Attribute

Syntax

```simtalk
< Path >.Active:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrigger.Active := true
```

See also

Active [check box] - Trigger

##### ActiveInterval [SimTalk]

Sets the time span during which the Trigger designated by &lt;Path&gt; will be active.

Remarks

After this time interval has elapsed, the Trigger value will take the default value. Define the default value under Values &gt; Values &gt; Value Table .

Type

Attribute

Syntax

&lt; Path &gt;.ActiveInterval:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyTrigger.ActiveInterval := str_to_time("1:00.00")
```

See also

Active Interval

Values [Trigger]

##### Combination [SimTalk]

Combination [SimTalk]

Sets the Trigger Type of the Trigger designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Combination:boolean

Assignment Value

You can assign a value of data type boolean .

Specify true for Combination , false for Input .

Example

MyTrigger.Combination := false

See also

Trigger Type

##### CombinationTable [SimTalk]

Sets the Combination Table , which the Trigger designated by &lt;Path&gt; uses.

Type

Attribute

Syntax

```simtalk
< Path >.CombinationTable:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
MyTrigger.Combination := true
MyTrigger.CombinationTable.delete({0,1}..{*,*})
MyTrigger.CombinationTable.writeRow(1,1,Trig5,0,10,3600)
MyTrigger.CombinationTable.createNestedList(0,1) MyTrigger.CombinationTable[0,1].setname("K1")
```

**See also**

Combination Table

##### Formula [SimTalk]

Formula [SimTalk]

Sets the Formula that the Trigger designated by &lt;Path&gt; uses to compute its value pattern.

Type

Attribute

Syntax

```simtalk
< Path >.Formula:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyTrigger.Formula := "K1 + K2 / K3"
```

See also

Formula [Trigger]

##### Periodic [SimTalk]

Sets if the Trigger designated by &lt;Path&gt; will be executed periodically ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Periodic:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTrigger.Periodic := true
```

See also

Repeat Periodically

##### PeriodLength [SimTalk]

PeriodLength [SimTalk]

Sets the Period Length of the Trigger designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.PeriodLength:time

Assignment Value

You can assign a value of data type time .

Example

MyTrigger.PeriodLength := 3600

See also

Period Length ReferenceDate [SimTalk] - Trigger Sets the Start Date of the Trigger designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.ReferenceDate:dateTime

Assignment Value

You can assign a value of data type dateTime .

Example

MyTrigger.ReferenceDate := sysDate

See also

Start Date [Trigger]

ReferenceTime [SimTalk] - Trigger

ReferenceTime [SimTalk] - Trigger

Sets the Start Time of the Trigger designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.ReferenceTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyTrigger.ReferenceTime := str_to_time("1:00:00:00.00")
```

See also

Start Time [Trigger]

##### ValueTable [SimTalk]

Sets the Values Table that the Trigger designated by &lt;Path&gt; uses to enter the value pattern over time.

Type

Attribute

Syntax

```simtalk
< Path >.ValueTable:table
```

Assignment Value

You can assign a value of data type table .

Example

MyTrigger.ValueTable.delete MyTrigger.ValueTable.include(TS703)

See also

Values [Trigger]

#### Generator

