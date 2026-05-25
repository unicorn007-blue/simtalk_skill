### OPCClassic

The OPCClassic Interface provides the interface between Plant Simulation and control and automation technology systems for accessing and exchanging data. The OPCClassic Interface acts as a client and can read the control variable and the signals of PLC controls and provide other applications with data. OPC stands for Open Platform Communications .

Icon

<!-- image -->

**Description**

**Note**

OPCClassic has been superseded by the newer OPCUA Standard . We recommend to always use OPCUA and the OPCUA Interface if at all possible.

To work with the OPC Unified Architecture , use the OPCUA Interface .

The simulation in Plant Simulation runs in real-time, as controls work with a real-time-timer and do not provide a fast forward function. Let's say the external application sets the value of a variable to right , then Plant Simulation might react with an Exit Control . You might use observer methods to react to values provided by the external application.

**Note**

The OPCClassic Interface supports OPC DA 2.0 and DA 3.0.

You need a 64-bit version OPC server to address this DA.

**Note**

If no identical user account exists on both computers, no authentication can take place. To deactivate authentication, you can create the following registry key of type DWORD and assign it the value 1 , for example HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation XX\Settings\RPC\_C\_AUTHN\_LEVEL\_NONE . This might pose a security vulnerability.

To show a tooltip with information about the OPCClassic Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the OPCClassic Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the OPCClassic Interface to the Class Library , click Manage Class Library &gt; Basic Objects InformationFlow &gt; OPCClassic on the Home ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

To work with the OPC Unified Architecture , use the OPCUA Interface .

**See also**

Configuring DCOM for Remote Access

#### Dialog Box of the OPCClassic Interface

Dialog Box of the OPCClassic Interface

Double-click the icon of the OPCClassic Interface to open its dialog box.

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Active [check box] - OPCClassic

To activate the OPCClassic Interface and to write status messages to the Console , select this check box.

<!-- image -->

To deactivate it, clear the check box.

Instead, you can also right-click the OPCClassic Interface object in the Frame and select Activate on the context menu.

To deactivate it, select Deactivate on the context menu.

SimTalk

Active [SimTalk] - OPCClassic

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Host Name [OPCClassic]**

###### Host Name [OPCClassic]

Type in the name or the IP address of the host computer on which the OPC server runs.

If the OPC server runs on the same computer as the OPCClassic Interface or as the PLC, you can leave this field empty.

If the OPC server is running remote on another host, you have to configure DCOM as described under Configuring DCOM for Remote Access .

**Note**

The connection string that you enter here depends on your database provider. Consult the documentation of your database provider for more information.

SimTalk

HostName [SimTalk] - OPCClassic

###### Server Name [OPCClassic]

To open a list of all servers which are available via the host you specified, click the ellipsis button.

Selecting a server in the list inserts it into the text box Server Name .

Or type in the name of your OPC server. You might, for example, type in OPC.Simatic.Net or Matricon.OPCServer , etc.

**Note**

The connection string that you specify here depends on your database provider. Consult the documentation of your database provider for more information.

SimTalk

ServerName [SimTalk] - OPCClassic

###### Items [OPCClassic]

To open the table into which you type the OPC items, click this button.

<!-- image -->

Each row in this table represents a group.

- Type the names of the groups into the cells below Group Name .
- Type the time in milliseconds after which Plant Simulation updates the values into the cells below Update Interval .

If you do not want to be informed by a callback method , i.e., the Changed-Value Control , when the value of an item of the group changes, type -1 as the Update Interval . The group will then be passive, and the communication with the OPC server will be reduced.

- Type the time in milliseconds into the cells below Write Interval .

When you type a value greater than 0, Plant Simulation does not immediately transmit changes of OPC Items of this group via the method setItemValue , to the OPC server, but only after the time you specifed has elapsed. This way value changes of several items can be combined and transmitted to the OPC server all at once, which saves time.

You can only specify the Write Interval as a multiple of 10 milliseconds, as the resolution internally only is 10 milliseconds.

**Note**

When you change the value of an OPC Item several times before the Write Interval has elapsed, then only the last value will be transmitted to the OPC server. This saves additional time, but can cause unexpected and unwanted behavior. If, for example, you set a boolean value to true and then reset it to false a short time after that, this change might not arrive at the OPC server, i.e., the value remains constantly false . Make sure to specify short enough write intervals in this case.

- Click Apply .
- Click in the cell below Group Name and press F2 to open the items list proper for this group. Then, define the items of that group in the subtable. The items, which you can specify, depend on the respective program running in the PLC control and on the OPC server you are using.

An example for a Siemens S7 PLC and the associated Siemens OPC server might look like this:

<!-- image -->

- Type the name of the item into the cells below Item Name .
- Select the type of the item in the cells below Type .
- Type an alias for the item into the cells below Alias .
- Type the name of a Method in which you defined what is to happen into the cells below Changed-Value Control .

<!-- image -->

| OPC data type   | Type   | Data type of the OPC Interface   |
|-----------------|--------|----------------------------------|
| B               | Uint8  | Int1                             |
| Char            | Int8   | Int1                             |
| W               | Uint16 | Int2                             |
| INT             | Int16  | Int2                             |
| DWORD           | Uint32 | Int4                             |
| DINT            | Int32  | Int4                             |
| X               | Bool   | Boolean                          |
| Real            | Real32 | Real4, Real8                     |
| Time            | U14    | Time                             |
| TOD             | Uint32 | Int4                             |
| -               | -      | String                           |
| DT              | date   | not yet supported                |

An Object Reference is preferable over long absolute paths as accessing an object reference is very fast. Object references to attribute methods are not possible though.

Instead of a Method , you can also specify a global Variable . The changed value will then be written directly into the variable.

For an item of data type boolean you can also specify an object of type Checkbox as the ChangedValue Control .

Plant Simulation passes two parameters to the Changed-Value Control that is called:

**Items [OPCClassic]**

- The parameter Alias of data type string designates the name of the alias which is defined in the column Alias .
- The parameter CurrentValue of data type any designates the current value of the Item . If you know the data type of the value, you can also type it directly.
- Type the Access Path . It suggests a data path to the server. The Access Path is an optional piece of information that can be provided by the client. As its use is highly server-specific, we recommend to consult the documentation that came with your OPC server. The Siemens OPC server does not need this information.

<!-- image -->

<!-- image -->

<!-- image -->

###### Show Item Values [OPCClassic]

To open a table that shows the values of the Items you defined, click this button.

<!-- image -->

After you selected the group name on the table that opens Plant Simulation shows the values of the items Alias , Data Type , and Update Interval of this group.

<!-- image -->

See also

Items [OPCClassic]

Tab Communication Statistics

Tab Communication Statistics [OPCClassic]

The tab Communication Statistics provides the settings listed in the table of contents to the left.

Number of changed-value control calls

Shows how often the Changed-Value Control , which you typed into the items table, was called.

<!-- image -->

###### Number of getItemValue calls

Shows how often the method getItemValue was called.

See also

getItemValue [SimTalk] - OPCClassic

**Number of setItemValue calls**

###### Number of setItemValue calls

Shows how often the method setItemValue was called.

See also

setItemValue [SimTalk] - OPCClassic

###### Time to set single item

Shows how long it took OPCClassic to transmit a single item to the OPC server.

**Time to get single item**

###### Time to get single item

Shows how long it took OPCClassic to retrieve a single item from the OPC server.

###### Time to set multiple items

Shows how long it took OPCClassic to transmit multiple items to the OPC server.

**Time to get multiple items**

###### Time to get multiple items

Shows how long it took OPCClassic to retrieve multiple items from the OPC server.

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] Edit Ignored Items Clear Ignored Items SimTalk updateDialog [SimTalk] See also View Menu [general description]

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the OPCClassic Interface**

#### \_Methods of the OPCClassic Interface

The OPCClassic Interface provides:

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

##### getItems [SimTalk] - OPCClassic

getItems [SimTalk] - OPCClassic

Returns the items which you defined in the Items table of the object designated by &lt;Path&gt; and writes them into a table.

Type

Method

Syntax

<!-- image -->

**Parameter**

The parameter Table of data type table designates the name of the table.

<!-- image -->

**Example**

```simtalk
var MyItemsTable: table
OPCClassicInterface.getItems(MyItemsTable)
```

**See also**

| Items [OPCClassic]                  | Number of changed-value control calls   |
|-------------------------------------|-----------------------------------------|
| setItems [SimTalk] - OPCClassic     | Number of getItemValue calls            |
| setItemValue [SimTalk] - OPCClassic | IsShown [SimTalk] - AttributeExplorer   |

getItemValue [SimTalk] - OPCClassic

Returns the current value of an item of the object designated by &lt;Path&gt; in the PLC.

**Remarks**

<!-- image -->

Type

Method

Syntax

<!-- image -->

Parameters

- The parameter ItemName of data type string designates the name of the item in the PLC. If you want to, you can also query the Group Name in addition to the Alias . You then have to type in the group name, a pipe symbol |, followed by the alias name.
- The optional parameter FromCache of data type boolean determines if the value it to be read from the cache ( true ) or from the server ( false ).

<!-- image -->

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type any .

Example

```simtalk
print OPCClassicInterface.getItemValue("Random.INT4")
print OPCClassicInterface.getItemValue("MyGroup|MyAlias",5)
```

See also

Items [OPCClassic]

setItemValue [SimTalk] - OPCClassic

Number of getItemValue calls

**setItems [SimTalk] - OPCClassic**

setItems [SimTalk] - OPCClassic

Sets the items in the Items table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

<!-- image -->

Parameter

The parameter Table of data type table designates the name of the table that contains the items.

<!-- image -->

**Example**

OPCClassicInterface.setItems(MyItemsTable)

**See also**

| Items [OPCClassic]                  | Number of changed-value control calls   |
|-------------------------------------|-----------------------------------------|
| getItems [SimTalk] - OPCClassic     | Number of getItemValue calls            |
| setItemValue [SimTalk] - OPCClassic | IsShown [SimTalk] - AttributeExplorer   |

##### setItemValue [SimTalk] - OPCClassic

Sets the value of an item of the object designated by &lt;Path&gt;.

**Remarks**

<!-- image -->

Type

Method

Syntax

<!-- image -->

**Parameters**

- The parameter ItemName of data type string designates the alias you defined.

You can also enter the Group Name in addition to the Alias . You then have to type in the group name, a pipe symbol |, followed by the alias name.

<!-- image -->

- The parameter NewValue of data type any designates the value you defined.
- The optional parameter Asynchronous of data type boolean sets if data is transmitted synchronous ( false ) or asynchronous ( true ).

Do not specify a value or specify true , to transmit data asynchronous.

- Specify false , to transmit data synchronous.

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type boolean .

**Example**

OPCClassicInterface.setItemValue("Random.INT4",7) OPCClassicInterface.setItemValue("MyGroup|MyItemName",5)

See also

Items [OPCClassic]

getItemValue [SimTalk] - OPCClassic

IsShown [SimTalk] - AttributeExplorer

#### Read-Only Attributes of the OPCClassic Interface

Read-Only Attributes of the OPCClassic Interface

The OPCClassic Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of the OPCClassic Interface

##### Attributes of the OPCClassic Interface

The OPCClassic Interface provides:

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
OPCClassicInterface.HostName := "127.0.0.1"
print OPCClassicInterface.HostName
posit := Station.cont.XPos
```

##### Active [SimTalk] - OPCClassic

Active [SimTalk] - OPCClassic

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

OPCClassicInterface.Active := true

See also

Active [check box] - OPCClassic

##### HostName [SimTalk] - OPCClassic

Sets the name or the IP address of the host computer on which the OPC server of the object designated by &lt;Path&gt; runs.

Remarks

If the OPC server runs remotely on another host, you have to configure DCOM.

If the OPC server runs on the same computer as the OPCClassic Interface or as the PLC, you do not have to assign a value.

**Note**

The connection string that you enter here depends on your database provider. Consult the documentation of your database provider for more information.

Type

Attribute

Syntax

&lt; Path &gt;.HostName:string

Assignment Value

You can assign a value of data type string .

Example

OPCClassicInterface.HostName := "myOPChost"

See also

Host Name [OPCClassic]

Configuring DCOM for Remote Access ServerName [SimTalk] - OPCClassic Sets the Server Name of the OPC server of the object designated by &lt;Path&gt;.

Remarks

The connection string that you enter here depends on your database provider. Consult the documentation of your database provider for more information.

Type

Attribute

Syntax

&lt; Path &gt;.ServerName:string

Assignment Value

You can assign a value of data type string .

You might, for example, specify "OPC.Simatic.Net" or " Matricon.OPCServer" , etc.

Example

OPCClassicInterface.ServerName := "OPC.Simatic.Net"

See also

Server Name [OPCClassic]

**PLCSIM\_Advanced**

