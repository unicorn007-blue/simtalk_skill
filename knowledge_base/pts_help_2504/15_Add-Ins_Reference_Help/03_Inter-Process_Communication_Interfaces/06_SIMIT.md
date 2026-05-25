### SIMIT

The SIMIT Interface provides the interface between Plant Simulation and process control devices, such as PLC controls, via SIMIT, which stands for Simulation &amp; Testing.

Icon

<!-- image -->

Description

"The simulation platform SIMIT enables comprehensive tests of automation applications and provides a realistic training environment for operator even before the real startup." Siemens Website

To show a tooltip with information about the SIMIT Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the SIMIT Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

<!-- image -->

To add the SIMIT Interface to the Class Library , click InformationFlow &gt; SIMIT on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

#### Dialog Box of the SIMIT Interface

Dialog Box of the SIMIT Interface

Double-click the icon of the SIMIT Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Active [check box] - SIMIT

To activate the SIMITInterface and to write status messages to the Console , select this check box.

<!-- image -->

To deactivate it, clear the check box.

Instead, you can also right-click the SIMITInterface object in the Frame and select Activate on the context menu.

To deactivate it, select Deactivate on the context menu.

Remarks

When you select the check box Active , Plant Simulation asks if it should set the Real-time Factor of the EventController to 1 and clear the setting Skip Long Event Intervals . To prevent this question in the future, select Never Ask Again in the message dialog. Then Plant Simulation will only ask again, when you delete the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences\VCRealTime1 .

SimTalk

Active [SimTalk] - SIMIT

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Shared Memory Name [text box]

Type in the name of the shared memory block.

<!-- image -->

The SIMIT server has to run on the same computer as the SIMIT Interface .

SimTalk

SharedMemoryName [SimTalk]

Update Interval [text box]

Type in the time in milliseconds after which Plant Simulation updates the values, i.e., reads them from the shared memory and writes them back to it.

SimTalk

UpdateInterval [SimTalk]

###### Update Interval [text box]

###### Items [SIMIT]

To open the table in which you define the SIMIT Items , click this button.

<!-- image -->

Each row in this table represents a group.

- Type the name of the item into the cells below Item Name .
- Select the type of the item in the cells below Type .
- Type an alias for the item into the cells below Alias .
- Type the name of a Method in which you defined what is to happen into the cells below Changed-Value Control .

| SIMIT data type   | Type   | Data type of the SIMIT Interface   |
|-------------------|--------|------------------------------------|
| BOOL              | -      | BOOL                               |
| BYTE              | UI1    | BYTE                               |
| WORD              | UI2    | WORD                               |
| INT               | I2     | INT                                |
| DWORD             | UI4    | DWORD                              |
| DINT              | I4     | DINT                               |
| REAL              | R4     | REAL                               |

An Object Reference is preferable over long absolute paths as accessing an object reference is very fast. Object references to attribute methods are not possible though.

Instead of a Method , you can also specify a global Variable . The changed value will then be written directly into the variable.

For an item of data type boolean you can also specify an object of type Checkbox as the ChangedValue Control .

Plant Simulation passes two parameters to the Changed-Value Control that is called:

- The parameter ItemName of data type string designates the name of the alias which is defined in the column Alias .
- The parameter CurrentValue of data type any designates the current value of the Item . If you know the data type of the value, you can also specify it directly.

```simtalk
param item : string, value : any      // alternative 1
param item : string, value : boolean  // alternative 2
```

**Items [SIMIT]**

- Select under In/Out if the item is an input value or an output value.

SimTalk getItems [SimTalk] - SIMIT getItemValue [SimTalk] - SIMIT setItems [SimTalk] - SIMIT DataType [SimTalk] - GASetAllocation

###### Import Items [SIMIT]

To import items from a shared memory block provided by SIMIT, click this button.

<!-- image -->

**Show Item Values [SIMIT]**

###### Show Item Values [SIMIT]

To open a table that shows the values of items Alias , Data Type , and Value , click this button.

<!-- image -->

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

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

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the SIMIT Interface**

#### \_Methods of the SIMIT Interface

The SIMIT Interface provides:

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

getItems [SimTalk] - SIMIT

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
simitinterface.getItems(MyItemsTable)
```

See also

Items [SIMIT]

setItems [SimTalk] - SIMIT

setItemValue [SimTalk] - SIMIT

##### getItemsFromSimit [SimTalk]

getItemsFromSimit [SimTalk]

Returns the items from the current shared memory of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getItemsFromSimit(Table:table)

Parameter

The parameter Table of data type table designates the table into which the method writes the items.

Example

```simtalk
var MySimitItemsTable: table
simitinterface.getItemsFromSimit(MySimitItemsTable)
print simitinterface.getItemsFromSimit(MySimitItemsTable)
```

See also

Import Items [SIMIT]

##### getItemValue [SimTalk] - SIMIT

Returns the current value of an item in the PLC of the object designated by &lt;Path&gt;.

**Syntax**

```simtalk
< Path >.getItemValue(ItemName:string) → any
```

Parameter

The parameter ItemName of data type string designates the name of the item in the PLC. If you want to, you can also query the Group Name in addition to the Alias . You then have to type in the group name and a pipe symbol | , followed by the alias name.

Return Value

The return value has the data type any .

Example

```simtalk
print simitinterface.getItemValue("Random.INT4")
print simitinterface.getItemValue("MyGroup|MyAlias")
```

**See also**

setItemValue [SimTalk] - SIMIT

Items [SIMIT]

setItems [SimTalk] - SIMIT

Sets the items in the items table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setItems(Table:table)

Parameter

The parameter Table of data type table designates the name of the table that contains the items.

Example

simitinterface.setItems(MyItemsTable)

See also

getItems [SimTalk] - SIMIT

Items [SIMIT]

##### setItemValue [SimTalk] - SIMIT

Sets the value of an item of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setItemValue(ItemName:string, NewValue:any) < Path >.setItemValue(ItemName:string|string, NewValue:any)
```

**Parameter**

- The parameter ItemName of data type string designates the alias you defined.

If you want to, you can also enter the Group Name in addition to the Alias . You then have to type in the group name and a pipe symbol | , followed by the alias name.

- The parameter NewValue of data type any designates the new value you defined.

**Example**

simitinterface.setItemValue("Random.INT4",7) simitinterface.setItemValue("MyGroup|MyAlias",5)

See also

getItemValue [SimTalk] - SIMIT

Items [SIMIT]

#### Read-Only Attributes of the SIMIT Interface

Read-Only Attributes of the SIMIT Interface

The SIMIT Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MySIMIT.UUID

#### Attributes of the SIMIT Interface

Attributes of the SIMIT Interface

The SIMIT Interface provides:

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
MySimitInterface.HostName := "127.0.0.1"
print MySimitInterface.HostName
posit := Station.cont.XPos
```

##### Active [SimTalk] - SIMIT

Active [SimTalk] - SIMIT

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
SIMITInterface.Active := true
```

See also

Active [check box] - SIMIT

##### SharedMemoryName [SimTalk]

Sets the name of the shared memory of the object designated by &lt;Path&gt;.

Remarks

The SIMIT server has to run on the same computer as the SIMIT Interface .

Type

Attribute

Syntax

&lt; Path &gt;.SharedMemoryName:string

Assignment Value

You can assign a value of data type string .

Example

SIMITInterface.SharedMemoryName := "mySharedMemory"

See also

Shared Memory Name [text box]

##### UpdateInterval [SimTalk]

UpdateInterval [SimTalk]

Sets the time in milliseconds after which Plant Simulation updates the values of the elements of the object designated by &lt;Path&gt;, i.e., reads them from shared memory and writes them back to it.

Type

Attribute

Syntax

&lt; Path &gt;.UpdateInterval:integer

Assignment Value

You can assign a value of data type integer .

Example

SIMITInterface.UpdateInterval := 100 // milliseconds

See also

Update Interval [text box]

#### Socket

