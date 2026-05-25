### PLCSIM\_Advanced

The Plant Simulation object PLCSIM\_Advanced provides the interface to PLCSIM Advanced of version 5.0 or higher. The Siemens program PLCSIM Advanced simulates functions of virtual PLCs (Programmable Logic Controllers). The object PLCSIM\_Advanced enables to exchange data between Plant Simulation simulation models and virtual PLCs which are executed in PLCSIM Advanced .

Icon

<!-- image -->

**Description**

PLC Out signals are copied to Plant Simulation variables and attributes of the objects in Plant Simulation . Plant Simulation sends PLC In signals to the PLC program running in PLCSIM Advanced , which are then used there.

The progression of time is synchronized between PLCSIM Advanced and Plant Simulation . The object PLCSIM\_Advanced supports real time mode as well as time scaling with factors between 0.01 and 100.

To show a tooltip with information about the PLCSIM\_Advanced Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the PLCSIM\_Advanced Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the object PLCSIM\_Advanced to the Class Library , click Manage Class Library &gt; Basic Objects &gt; PLCSIM\_Advanced on the Home ribbon tab.

<!-- image -->

<!-- image -->

**See also**

What is S7-PLCSIM Advanced?

Accessing PLCSIM Elements

<!-- image -->

#### What is S7-PLCSIM Advanced?

"Using PLCSIM Advanced, you can simulate your CPU programs on a virtual controller. You do not need any real controllers for this. You can configure your CPU with STEP 7 in the TIA Portal, program your application logic and then load the hardware configuration and the program into the virtual controller.

From there you can run your program logic, observe the effects of simulated inputs and outputs and adapt your programs.

In addition to communicating via Softbus, PLCSIM Advanced provides a full Ethernet connection and can thus also communicate distributed.

PLCSIM Advanced enables interaction with native C++/C# programs or simulation software over the user interface (API)." S7-PLCSIM Advanced Online Help

**Application Areas**

- Verification of the user program (TIA Portal)
- Automatic testing of the STEP 7 program
- Software in the loop simulation for the virtual commissioning of machine tools/production machines, production cells and production lines in a plant

**Note**

If PLCSIM Advanced communicates across several computers within your computer network, the PLCSIM Advanced Runtime Manager has to be installed on all participating computers.

**Advantages**

Using PLCSIM Advanced offers numerous advantages:

- Improve quality of automation projects by early error detection
- Avoid costs for hardware in simulation environments
- Reduced response times
- Reduce risk for commissioning
- Earlier training of operator is possible
- Increase production efficiency by optimizing program components
- Increase efficiency during replacement of machine components

#### Dialog Box of PLCSIM\_Advanced

Dialog Box of the PLCSIM\_Advanced Interface

Double-click the icon of the PLCSIM\_Advanced Interface to open its dialog box.

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Active [check box] - PLCSIM\_Advanced

To activate PLCSIM\_Advanced , select this check box.

<!-- image -->

To deactivate it, clear the check box.

Instead, you can also right-click the object PLCSIM\_Advanced in the Frame and select Activate on the context menu.

To deactivate it, select Deactivate on the context menu.

Remarks

When you select the check box Active , Plant Simulation asks if it should set the Real-time factor of the EventController to 1 and clear the setting Skip Long Event Intervals . To prevent this question in the future, select Never ask again in the message dialog. Then Plant Simulation will only ask again, when you delete the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences\VCRealTime1 .

SimTalk

Active [SimTalk] - PLCSIM\_Advanced

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Instance Name [text box]

Instance Name [text box]

Type in the name of the virtual PLC with which the object PLCSIM\_Advanced is to communicate.

SimTalk

InstanceName [SimTalk]

###### Remote Runtime Manager [text box]

Type in the IP address of the computer on which the Remote Runtime Manager runs.

<!-- image -->

Leave the text box empty if you want to use the Runtime Manager on your local computer.

The default setting for the Runtime Manager Port in PLCSIM Advanced is 50000 .

<!-- image -->

The Runtime Manager establishes a connection to PLCSIM Advanced .

SimTalk

RemoteRuntimeManager [SimTalk]

###### Simulation Mode

Select the Simulation Mode from the drop-down list.

<!-- image -->

- For the setting Real-time the simulation is executed in real-time in Plant Simulation as well as in the virtual PLC. The data exchange with the virtual PLC is executed in the interval that you set as the Data Exchange Interval without stopping the clock.
- We recommend to use this mode when the simulation model communicates via other interfaces in addition to the PLCSIM\_Advanced Interface , for example via the OPCUA Interface or via Sockets .
- For the setting Step-by-step Plant Simulation sets the operating mode SingleStep in the virtual PLC and exchanges data after each cycle of the virtual PLC. At the same time it sets the Data Exchange Interval to 0.

**SimTalk**

DataExchangeInterval [SimTalk]

**Data Exchange Interval [text box]**

###### Data Exchange Interval [text box]

Type in the value of the Data Exchange Interval . This is the time span in milliseconds in which PLCSIM\_Advanced exchanges data with the virtual PLC while the simulation model runs in real time.

<!-- image -->

If you type in 0 , Plant Simulation sets the operating mode SingleStep in the virtual PLC and exchanges data after each cycle of the virtual PLC. During data exchange the virtual PLC is in Freeze mode . This ensures that all data is completely transmitted before the next cycle starts. This also causes the virtual time to stand still during data exchange. Thus the virtual time progresses slower than real time. Plant Simulation synchronizes the simulation time with the virtual PLC and thus the simulation model runs slower than real time.

SimTalk

DataExchangeInterval [SimTalk]

See also

OfflineCycleCtrl [SimTalk]

###### Items [PLCSIM\_Advanced]

To open the table into which you enter the PLCSIM items, click this button.

<!-- image -->

You can either fill in the table manually or you can import items .

Each row in the table represents a group.

- Type the names of the groups into the cells below Group Name .
- Select the type of signal, which the group is to contain, in the cells below Signal Type .
- PLC In are input signals of the PLC. You can assign a value in a SimTalk Method to such an item.
- PLC Out are output signals of the PLC. You can query the value of such an item in a SimTalk Method , but you cannot assign a value.
- Plant Simulation exchanges data after the data exchange interval has elapsed. You can prolong this time for a group by typing a value into the cells below Interval that is greater than the data exchange interval. Specify 0 or a value smaller than the data exchange interval, Plant Simulation again exchanges signals and data after each data exchange interval.
- Click Apply .
- Double-click in the cell below Group Name or click in the cell and press F2 to open the items list proper for this group. Then, define the items of that group in the subtable. The items, which you can specify, depend on the respective program running in the PLC control you are using.

<!-- image -->

An example might look like this:

<!-- image -->

- Specify these settings:
- Type the name of the item in the virtual PLC into the cells below Identifier .
- Type an alias for the item into the cells below Alias . Within SimTalk Methods elements are addressed with this Alias . The Alias has to meet the naming conventions for user-defined names .
- Type the name of the attribute with which the value in the virtual PLC is to be synchronized into the cells below Simulation Model Attribute .

For a PLC In signal Plant Simulation will transmit the value of the attribute to the input signal of the virtual PLC. For a PLC Out signal Plant Simulation will assign the value of the output signal of the virtual PLC to the attribute.

The attribute can be one of the following: A built-in or user-defined attribute of a Plant Simulation object, or an object of type Variable , or an object of type Checkbox . If you specify a Variable or Checkbox , Plant Simulation will map the built-in attribute Value of the respective object.

You can also specify a SimTalk method into the column Simulation Model Attribute . Plant Simulation will run the callback method each time a new data value arrives. The new value is passed as a parameter to the method.

```simtalk
param  value : any // switch Belt 2 on or off if value
Belt2.speed := 2
else
	Belt2.speed := 0
end
```

If you do not specify the Simulation Model Attribute , you can still set or get the item value in a SimTalk method .

```simtalk
var OldActive : boolean := PLCSIM.BeltActive  -- read the item with the Alias BeltActive from the PLC
PLCSIM.BeltActive := true                     -- set the item  with the Alias BeltActive in the PLC
```

When you import PLC tags from PLCSIM Advanced to the object PLCSIM\_Advanced , Plant Simulation adds four groups to the items table.

The group names designate the following:

- I : Data and signals that are sent from Plant Simulation attributes to the virtual PLC.
- O : Data and signals that are sent from the virtual PLC to Plant Simulation object attributes or callback methods.
- M : Marker variables in the virtual PLC. Plant Simulation can read and write these signals.
- DB : Data in PLC data blocks. Plant Simulation can read and write these signals.

Plant Simulation exchanges data after the data exchange interval has elapsed. You can prolong this time for a group by typing a value into the cells below Interval that is greater than the data exchange interval. Specify 0 or a value smaller than the data exchange interval to again exchange signals and data after each data exchange interval.

You can also allocate signals in the Input/Output/Marker area via their address. This is useful if you want to access memory in the virtual PLC for which no identifiers were assigned in the PLC program.

Open an existing group by double-clicking it. Or create a new group, click Apply , and then double-click the new group. Specify a percentage sign followed by a character that sets the area, and the address as the identifier. Compare these examples:

- %I100 for an Input signal at address 100
- %Q40.7 or %O40.7 for an Output signal at bit 7 of address 40
- %M5 for a Marker signal at address 5

**Note**

When you delete items, Plant Simulation adds these items to the list of ignored items, so they will not be added when you import items later. If you want to import some of them again later on, remove those from the list of ignored items before you import items.

SimTalk

getItems [SimTalk] - PLCSIM\_Advanced

setItems [SimTalk] - PLCSIM\_Advanced

See also

Data Exchange Interval [text box]

###### Show Item Values [PLCSIM\_Advanced]

To open a table that shows the values of the Items that you defined, click this button.

<!-- image -->

Double-click a group name in the table that opens, so that Plant Simulation shows the values of the items of this group.

SimTalk

getItems [SimTalk] - PLCSIM\_Advanced

setItems [SimTalk] - PLCSIM\_Advanced

See also

Items [OPCClassic]

###### Import Items [PLCSIM\_Advanced]

To import all items that the program of the virtual PLC provides, click this button.

<!-- image -->

To do so, you first have to activate the connection. Plant Simulation then creates groups for these items.

<!-- image -->

You can also create new groups and copy items between the groups to achieve a more convenient signal grouping than the provided by the PLC. The table of the configured items shows the current data item values when a connection to a running virtual PLC is active

SimTalk getItems [SimTalk] - PLCSIM_Advanced setItems [SimTalk] - PLCSIM_Advanced

Tab Filter

Tab Filter

On the tab Filter you can define settings that control how many and which signals the API of the PLCSIM\_Advanced interface provides for Plant Simulation .

If you do not set any limitations, the PLCSIM-Advanced-API provides all signals. Keep in mind that the PLCSIM-Advanced-API can only manage 500,000 variables at the moment. If the virtual PLC has more than 500,000 signals, the PLCSIM-Advanced-API will return an error when Plant Simulation establishes the connection and retrieves the signals. To prevent this, you can filter the signals. If you limit the number of signals, Plant Simulation can also establish the connection with PLCSIM Advanced faster.

When you retrieve all signals from the PLCSIM-Advanced-API , by clicking the button Import Items on the tab Attributes , the items table can be extensive and confusing. Here it also might be helpful to filter the signals to be retrieved. Plant Simulation only writes those signals to the table that pass the filter.

The tab Filter provides the settings listed in the table of contents to the left.

###### HMI-Visible Signals Only [check box]

To make the PLCSIM-Advanced-API only provide signals for Plant Simulation which are marked as HMI visible in the virtual PCS, select this check box. To provide all signals, clear the check box.

<!-- image -->

HMI stands for H uman M achine I nterface.

**SimTalk**

HMIVisibleSignalsOnly [SimTalk]

**Datablock Filter [PLCSIM\_Advanced]**

###### Datablock Filter [PLCSIM\_Advanced]

The list Datablock Filter shows the names of the datablocks which the PLCSIM-Advanced-API provides.

<!-- image -->

If the list is empty, all datablocks are available.

If the list is not empty, only those datablocks are available whose names are contained in the list.

**SimTalk**

DatablockFilter [SimTalk]

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] Edit Ignored Items Clear Ignored Items SimTalk updateDialog [SimTalk] See also View Menu [general description]

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of PLCSIM\_Advanced

##### \_Methods of PLCSIM\_Advanced

The PLCSIM\_Advanced Interface provides:

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

getItems [SimTalk] - PLCSIM\_Advanced

Returns the items which you defined in the items table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getItems(Table:table)
```

Parameter

The parameter Table of data type table designates the name of the table to which the method writes the values.

Example

```simtalk
var MyItemsTable: table
MyPLCSIM.getItems(MyItemsTable)
```

See also

Items [PLCSIM\_Advanced]

setItems [SimTalk] - PLCSIM\_Advanced getItemValue [SimTalk] - PLCSIM\_Advanced Returns the current value of an item of the object designated by &lt;Path&gt; which you defined for the virtual PLC.

Type

Method

Syntax

```simtalk
< Path >.getItemValue(ItemName:string[, GroupName:string]) → any
```

**Parameters**

- The parameter ItemName of data type string designates the element in the PLC.

Normally you access an item in the PLC with PLCSIM\_Advanced.ItemName or with PLCSIM\_Advanced.GroupName.ItemName .

If the name of the item is only known at runtime, for example, when it is read from a user-defined attribute of data type string of a MU , then this notation is impractical. For this case we introduced the methods getItemValue and setItemValue .

```simtalk
PLCSIM_Advanced.setItemValue("MyItem", 123) for example is equivalent to
PLCSIM_Advanced.MyItem := 123
```

- The optional parameter GroupName of data type string designates the Group Name .

Return Value

The return value has the data type any .

Example

```simtalk
param ItemPrefix: string, ItemNo: integer -> any
var ItemName: string := ItemPrefix + ItemNo
return PLCSIM_Advanced.getItemValue(ItemName)
```

**See also**

setItemValue [SimTalk] - PLCSIM\_Advanced

Items [PLCSIM\_Advanced]

Show Item Values [PLCSIM\_Advanced]

setItems [SimTalk] - PLCSIM\_Advanced

Sets the items in the items table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setItems(Table:table)

Parameter

The parameter Table of data type table designates the name of the table that contains the items.

Example

MyPLCSIM.setItems(MyItemsTable)

See also

getItems [SimTalk] - PLCSIM\_Advanced

Items [PLCSIM\_Advanced]

setItemValue [SimTalk] - PLCSIM\_Advanced

Sets the value of an item of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setItemValue(ItemName:string, NewValue:any[, GroupName:string])
```

**Parameters**

- The parameter ItemName of data type string designates the item in the PLC.

Normally you access an item in the PLC with PLCSIM\_Advanced.ItemName or with PLCSIM\_Advanced.GroupName.ItemName .

If the name of the item is only known at runtime, for example, when it is read from a user-defined attribute of data type string of a MU , then this notation is impractical. For this case we introduced the methods getItemValue and setItemValue .

PLCSIM_Advanced.setItemValue("MyItem", 123) for example

```simtalk
is equivalent to
PLCSIM_Advanced.MyItem := 123
```

- The parameter NewValue of data type any designates the new value of the item in the PLC.
- The optional parameter GroupName of data type string designates the Group Name .

**Example**

```simtalk
param ItemPrefix: string, ItemNo: integer, Value: boolean
var ItemName: string := ItemPrefix + ItemNo
PLCSIM_Advanced.setItemValue(ItemName, Value)
```

**See also**

getItemValue [SimTalk] - PLCSIM\_Advanced

Items [PLCSIM\_Advanced]

Show Item Values [PLCSIM\_Advanced]

#### Read-Only Attributes of PLCSIM\_Advanced

Read-Only Attributes of PLCSIM\_Advanced

The PLCSIM\_Advanced Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyPLCSIM_Advanced.UUID
```

##### Attributes of PLCSIM\_Advanced

\_Attributes of PLCSIM\_Advanced

The PLCSIM\_Advanced Interface provides:

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
MyPLCSIM.Active := true
print
MyPLCSIM.Active := true
posit := Station.cont.XPos
```

Active [SimTalk] - PLCSIM\_Advanced

Activates the PLCSIM\_Advanced object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

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
MyPLCSIM.Active := true
```

See also

Active [check box] - PLCSIM\_Advanced

**DatablockFilter [SimTalk]**

##### DatablockFilter [SimTalk]

Sets which datablocks the PLCSIM-Advanced-API of the object designated by &lt;Path&gt; provides.

Remarks

If the list is empty, all datablocks are available.

If the list is not empty, only those datablocks are available whose names are contained in the list.

Type

Attribute

Syntax

&lt; Path &gt;.DatablockFilter:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyPLCSIM.DatablockFilter := "\"Datablock1\",\"Datablock2\""
```

See also

Datablock Filter [PLCSIM\_Advanced]

##### DataExchangeInterval [SimTalk]

Sets the value of the Data Exchange Interval of the object designated by &lt;Path&gt;.

Remarks

This is the time span in milliseconds in which PLCSIM\_Advanced exchanges data with the virtual PLC while the simulation model runs in real time.

Specify 0 to set the operating mode SingleStep in the virtual PLC and exchanges data after each cycle of the virtual PLC. During data exchange the virtual PLC is in Freeze mode . This ensures that all data is completely transmitted before the next cycle starts. This also causes the virtual time to stand still during data exchange. Thus the virtual time progresses slower than real time. Plant Simulation synchronizes the simulation time with the virtual PLC and thus the simulation model runs slower than real time.

Type

Attribute

Syntax

&lt; Path &gt;.DataExchangeInterval:integer

Assignment Value

You can assign a value of data type integer .

Example

MyPLCSIM.DataExchangeInterval := 20 // milliseconds

See also

Data Exchange Interval [text box]

Simulation Mode

##### HMIVisibleSignalsOnly [SimTalk]

Sets if the object designated by &lt;Path&gt; only provides signals for Plant Simulation which are marked as HMI visible in the virtual PLC ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.HMIVisibleSignalsOnly:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPLCSIM.HMIVisibleSignalsOnly := true

See also

HMI-Visible Signals Only [check box]

##### InstanceName [SimTalk]

Sets with which virtual PLC the object designated by &lt;Path&gt; communicates.

Type

Attribute

Syntax

&lt; Path &gt;.InstanceName:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyPLCSIM.ServerName := "HMI16PLC"
```

See also

Instance Name [text box]

##### OfflineCycleCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation executes the control periodically within the specified Data Exchange Interval of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

< Path >.OfflineCycleCtrl:method

**Assignment Value**

You can only assign a value of data type method to the control, not a user-defined attribute of data type method .

**Example**

```simtalk
MyPLCSIM := MyCycleControl
```

See also

Data Exchange Interval [text box]

##### OfflineMode [SimTalk]

Sets if you can also read and assign the items of the object designated by &lt;Path&gt; if no connection exists to PLCSIM\_Advanced ( true ) or not ( false ).

Remarks

This way you can run the simulation model without PLCSIM\_Advanced . Be aware that then you have to emulate the logic of the PLC in the simulation model itself.

Type

Attribute

Syntax

&lt; Path &gt;.OfflineMode:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPLCSIM.OfflineMode := true RemoteRuntimeManager [SimTalk]

Sets the IP address of the computer on which the Runtime Manager of the object designated by &lt;Path&gt; runs.

Remarks

The default setting for the Runtime Manager Port is 50000 .

The Runtime Manager establishes a connection to PLCSIM Advanced .

Type

Method

Syntax

&lt; Path &gt;.RemoteRuntimeManager:string

Assignment Value

You can assign a value of data type string .

Specify an empty string "" for RemoteRuntimeManager to use the Runtime Manager on your local computer.

Example

```simtalk
MyPLCSIM.RemoteRuntimeManager := "123.456.789.101:50000"
MyPLCSIM.RemoteRuntimeManager := "" // local computer
```

See also

Remote Runtime Manager [text box]

#### Accessing PLCSIM Elements

You can address the items with their Alias . You can address the items like user-defined attributes.

**Example**

```simtalk
MyPLCSIM.MyAlias1 := true // set Input signal
MyPLCSIM.MyAlias2 := 42
print MyPLCSIM.MyAlias3   // query Output signal
```

If you assigned the same Alias in several groups, you have to address the items by their group.

```simtalk
MyPLCSIM.MyGroup1.MyAlias4 := true
MyPLCSIM.MyGroup2.MyAlias4 := 42
```

#### SIMIT

