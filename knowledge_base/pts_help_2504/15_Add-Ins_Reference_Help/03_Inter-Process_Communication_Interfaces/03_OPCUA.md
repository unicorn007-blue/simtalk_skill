### OPCUA

The OPCUA Interface provides an interface between Plant Simulation and control and automation technology systems for accessing and exchanging data. It enables access to process monitors, such as PLC controls via the OPC Unified Architecture . The OPCUA Interface acts as a client and can read and write control variables and the signals of PLC controls. OPC stands for Open Platform Communications .

Icon

<!-- image -->

**Description**

Note We recommend to always use OPCUA and the OPCUA Interface if at all possible.

You should run the simulation in Plant Simulation in real-time, as controls work with a real-time-timer and do not provide a fast-forward function. When the PLC sets the value of a variable to right , then Plant Simulation calls a callback method in which you can react to the value from the external application.

The Profiler shows the entire OPCUA Communication Statistics .

To show a tooltip with information about the OPCUA Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the OPCUA Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

<!-- image -->

To add the OPCUA Interface to the Class Library , click InformationFlow &gt; OPCUA on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

#### Dialog Box of the OPCUA Interface

Dialog Box of the OPCUA Interface

Double-click the icon of the OPCUA Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Active [check box] - OPCUA

To activate the OPCUA Interface , select this check box. To deactivate it, clear the check box.

<!-- image -->

Instead, you can also right-click the OPCUA Interface object in the Frame and select Activate on the context menu. To deactivate it, select Deactivate on the context menu.

Remarks

When you select the check box Active , Plant Simulation asks if it should set the Real-time factor of the EventController to 1 and clear the setting Skip Long Event Intervals . To prevent this question in the future, select Never ask again in the message dialog. Then Plant Simulation will only ask again, when you delete the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences\VCRealTime1 .

SimTalk

Active [SimTalk] - OPCUA

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Server Name [OPCUA]

Type in the IP address and the port number of your OPC server.

<!-- image -->

A typical IP address for OPCUA servers is opc.tcp://101.102.103.104:1005

The port number to be used, 1005 in the example above, is either configured in the server or it is provided by the server provider. Consult the documentation of your OPCUA server provider for more information.

<!-- image -->

**Timeout [text box]**

###### Timeout [text box]

Type in the time in seconds for which Plant Simulation waits for an answer for a query to the OPC server.

If this time is too short, Plant Simulation shows an error if the answer of the server takes a longer time.

If the server does not answer, because you specified a wrong server address for example, or of the server is not up and running or hangs, then Plant Simulation freezes until the time you specified has expired.

SimTalk

TimeOut [SimTalk]

###### Items [OPCUA]

To open the table in which you specify the OPCUA items, click this button.

<!-- image -->

<!-- image -->

Each row in the Items table represents a group.

- Type the names of the groups into the cells below Group Name .
- Type the numbers of the Namespace into the cells below Namespace .
- Type the time in milliseconds into the cells below Read Interval . The OPC server transmits changed values to Plant Simulation after this time has elapsed. Plant Simulation then calls the callback methods assigned to the Changed-Value Control values into the cells below Write Interval .

If you do not want to be informed by a callback method , when the value of an item of the group changes, type 0 as the Write Interval . The group will then be passive, and the communication with the OPC server will be reduced. The values of elements can still be read, but this then triggers a time-intensive query to the OPC server each time a value is read.

- Type the time in milliseconds into the cells below Write Interval after which Plant Simulation transmits the values to the OPC server.

When you type a value greater than 0, Plant Simulation does not immediately transmit changes of OPC Items of this group via the method setItemValue , to the OPC server, but only after the time you typed has elapsed. This way value changes of several items can be combined and transmitted to the OPC server all at once, which saves time.

You can only specify the Write Interval as a multiple of 10 milliseconds, as the resolution internally only is 10 milliseconds.

**Note**

When you change the value of an OPC Item several times before the Write Interval has elapsed, then only the last value will be transmitted to the OPC server. This saves additional time, but can cause unexpected and unwanted behavior. If, for example, you set a boolean value to true and then reset it to false a short time after that, this change might possibly not arrive at the OPC server, i.e., the value remains constantly false . Make sure to specify short enough write intervals in this case.

**Note**

If a value on the Plant-Simulation-side never changes, i.e., if the value only changes on the server-side and thus only has to be read by Plant Simulation , you should specify 0 as the Write Interval . Plant Simulation then does not have to check in intervals if the value changed and thus saves time.

- Click Apply .
- Click in the cell below Group Name and press F2 to open the items list proper for this group. Then, define the items of that group on the subtable. The items, which you can type, depend on the respective program running in the PLC control and on the OPC server you are using.

<!-- image -->

An example might look like this:

<!-- image -->

- Select the Identifier Type . As a rule this is a String .

- Type the name of the item into the cell below Identifier . The name , as a rule, is a path separated by periods. An element can also be a single element of an array . We only support elements of these data types: Boolean , Int8 , UInt8 , Int16 , UInt16 , Int32 , UInt32 , Int64 , UInt64 , Real32 , Real64 , String , and DateTime . We also support Arrays of the above data types, except for String arrays . In addition, we support OPC UA server methods, which are only allowed in groups without a read/write interval.
- Leave the cells below Data Type empty as Plant Simulation automatically determines it when you activate the connection to the OPC Server.
- Type an alias for the item into the cells below Alias .
- Type the name of the attribute into the cell Simulation Model Attribute whose value is to be synchronized with the item in the OPC server.

If the group, which contains the item, has a write interval that is not 0, Plant Simulation will transmit the value of the attribute to the item in the OPC server. If the group has a read interval that is not 0, Plant Simulation will assign the value of the item in the OPC server to the attribute.

You can type one of the following values into the column Simulation Model Attribute :

- ◊ An attribute of a Plant Simulation object
- ◊ An object of type Variable
- ◊ An object of type Checkbox (only if the data type of the element is boolean )
- ◊ An object of type Method which expects two arguments

Specify a Method in the column to execute this Method when a new data value arrives. The new value is passed as a parameter to the method.

Plant Simulation passes two parameters to the callback method that is called:

- ◊ The parameter Alias of data type string designates the name of the alias which is defined in the column Alias .
- ◊ The parameter CurrentValue of data type any designates the current value of the Item . If you know the data type of the value, you can also type it directly.

```simtalk
param item : string, value : any      -- alternative 1
param item : string, value : boolean  -- alternative 2
```

If you do not specify the Simulation Model Attribute , you can still set or get the item value in a SimTalk method .

```simtalk
var OldActive : boolean := OPCUA.BeltActive  -- read the item with the Alias BeltActive from the PLC
OPCUA.BeltActive := true                     -- set the item  with the Alias BeltActive in the PLC
```

Items of type Method designate OPC UA server methods. These cannot be mapped to a Simulation Model Attribute , but can only be called from within a SimTalk method . The first parameter is the object ID for which the server method will be called. That parameter must be of type string or integer . You can pass additional parameters to the server method if the server method expects them.

```simtalk
-- Call the OPC UA server method with the alias MyServerMethod -- for the PLC object with the object ID Airconditioner.Controller -- and pass the two parameters 42 and true to the OPC UA server method.
OPCUA.MyServerMethod("Airconditioner.Controller", 42, true)
```

**Note**

When you delete items, Plant Simulation adds these items to the list of ignored items, so they will not be added when you import items later. If you want to import some of them again later on, remove those from the list of ignored items before you import items.

SimTalk

getItems [SimTalk] - OPCUA

getItemValue [SimTalk] - OPCUA

setItems [SimTalk] - OPCUA

setItemValue [SimTalk] - OPCUA

DirectItemAccess [SimTalk]

See also

Edit Ignored Items

Clear Ignored Items

###### Import Items [OPCUA]

To apply one or several groups in the Items Table , click this button. This can take some time.

<!-- image -->

The groups contain the items known on the server. Plant Simulation only applies the groups when you click the OK or Apply buttons.

If you close the dialog by clicking Cancel , the groups are not applied.

**Note**

Under certain circumstances elements are imported which Plant Simulation cannot read for unspecific reasons. If this is the case, Plant Simulation shows an error message when the connection to the OPC server is established.

**SimTalk**

getItems [SimTalk] - OPCUA

getItemValue [SimTalk] - OPCUA

setItems [SimTalk] - OPCUA

setItemValue [SimTalk] - OPCUA

**Show Item Values [OPCUA]**

###### Show Item Values [OPCUA]

To open a table that shows the values of the Items you defined, click this button.

<!-- image -->

Double-click a group name in the table that opens, Plant Simulation shows the values of the items of this group.

<!-- image -->

**See also**

Items [OPCUA]

Tab Security

Tab Security

The tab Security provides the settings listed in the table of contents to the left.

Login group box

Login [group box]

Type in the username and the password to log into OPCUA .

<!-- image -->

The group box Login provides these settings:

Username [OPCUA]

**Password [OPCUA]**

Inheritance

The inheritance check box turns inheritance of the Login settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you enter only applies to the attribute of this object.

**Username [OPCUA]**

**Username [OPCUA]**

Type in the Username with which you want to log in to the OPC server .

<!-- image -->

If you fill in the text boxes Username and Password , Plant Simulation logs you into the OPC server with this information.

If you leave the text boxes empty, Plant Simulation logs you in as an anonymous user.

SimTalk

setUserAndPassword [SimTalk]

**Password [OPCUA]**

Type in the Password with which you want to log in to the OPC server .

<!-- image -->

If you fill in the text boxes Username and Password , Plant Simulation logs you into the OPC server with this information.

If you leave the text boxes empty, Plant Simulation logs you in as an anonymous user.

SimTalk

setUserAndPassword [SimTalk]

Encryption

Encryption [group box]

Select the security mode and the security policy you want to use.

<!-- image -->

The group box Encryption provides these settings:

Security Mode

Security Policy

Inheritance

The inheritance check box turns inheritance of the Encryption settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you enter only applies to the attribute of this object.

**Encryption [group box]**

**Security Mode**

Select the Message Security Mode of the OPCUA Interface . These are the settings that the OPC server provides and which are usually set in the OPC server.

<!-- image -->

To enforce establishing an encrypted connection with the OPC server, select another value for the Security Policy and the Security Mode than None .

**Note**

The same values have to be set in the OPC server, as otherwise no connection can be established.

**Note**

To be able to establish an encrypted connection to an OPC server, the OPC server usually needs to know and to trust the client certificate. Consult the documentation of your OPC server on how to configure the client certificate. The Plant Simulation certificates are stored in the directory

C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation\OPC PKI client\own\certs\default.der

**SimTalk**

SecurityMode [SimTalk]

See also

SecurityPolicy [SimTalk]

Security Policy

**Security Policy**

Select the Security Policy of the OPCUA Interface . These are the settings that the OPC server provides and which are usually set in the OPC server.

<!-- image -->

To enforce establishing an encrypted connection to the OPC server, select another value for the Security Policy and the Security Mode than None .

**Note**

The same values have to be set in the OPC server, as otherwise no connection can be established.

**Note**

To be able to establish an encrypted connection to an OPC server, the OPC server usually needs to know and to trust the client certificate. Consult the documentation of your OPC server on how to configure the client certificate. The Plant Simulation certificates are stored in the directory

C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation\OPC PKI client\own\certs\default.der

**SimTalk**

SecurityPolicy [SimTalk]

See also

SecurityMode [SimTalk]

Security Mode

###### Client Certificate

Type in the file path to a file which contains an OPC-UA-conform digital certificate.

You can also embed the certificate file into an object of type FileLink and then specify the object path to the FileLink .

If you leave this text box empty, Plant Simulation will create a standard certificate, named default .

The Plant Simulation certificates are stored in the directory C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation\OPC PKI client\own

You can create your own digital certificate the method createCertificate .

SimTalk

createCertificate [SimTalk]

CertificateFile [SimTalk]

##### Navigate Menu

Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

Edit Ignored Items

Clear Ignored Items

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

###### Edit Ignored Items

Edits the list of items that are to be ignored when you import items. This is handy if you want to import some of the items that you thought should not be imported before.

When you delete items, Plant Simulation adds these items to the list of ignored items, so they will not be added when you import items later.

<!-- image -->

###### Clear Ignored Items

Clears the list of items when you import items.

When you delete items, Plant Simulation adds these items to the list of ignored items, so they will not be added when you import items later. If you want to import some of them again later on, remove those items from the list of ignored items before you import items.

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the OPCUA Interface**

#### \_Methods of the OPCUA Interface

The OPCUA Interface provides:

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

##### createCertificate [SimTalk]

Creates a file with a digital certificate on your computer and enters the file name into the attribute CertificateFile .

**Remarks**

When Plant Simulation establishes a connection with the OPC server, Plant Simulation identifies itself as OPC client with this certificate.

Type

Method

Syntax

```simtalk
< Path >.createCertificate(CommonName:string, Organization:string, OrganizationalUnit:string, Locality:string, State:string, Country:string [, DomainComponent:string]) → string
```

**Parameters**

- The parameter CommonName of data type string designates the common name.
- The parameter Organization of data type string designates the name of the organization.
- The parameter OrganizationalUnit of data type string designates the name of the organizational unit.
- The parameter Locality of data type string designates the name of the locality, i.e., the city/location.
- The parameter State of data type string designates the name of the state in which your organization is located.
- The parameter Country of data type string designates the name of the country in which your organization is located.
- The optional parameter DomainComponent of data type string designates the domain component.

**Return Value**

The return value has the data type string .

It is the file name without the file extension.

**Example**

MyOPCUA.createCertificate("PlantSimulation@ComputerName", "MyOrganization", "MyUnit", "Plano", "Texas", "US")

See also

Client Certificate

CertificateFile [SimTalk]

##### getItems [SimTalk] - OPCUA

Returns the items which you defined in the items table of the object designated by &lt;Path&gt; and writes them into a table.

Type

Method

Syntax

<!-- image -->

**Parameter**

The parameter Table of data type table designates the name of the table.

<!-- image -->

**Example**

| var   | MyItemsTable: table          |
|-------|------------------------------|
|       | OPCUA.getItems(MyItemsTable) |

**See also**

| Items [OPCClassic] table            | Number of changed-value control calls   |
|-------------------------------------|-----------------------------------------|
| setItems [SimTalk] - OPCClassic     | Number of getItemValue calls            |
| setItemValue [SimTalk] - OPCClassic | IsShown [SimTalk] - AttributeExplorer   |

##### getItemValue [SimTalk] - OPCUA

Returns the current value of an item in the PLC of the object designated by &lt;Path&gt;.

**Remarks**

<!-- image -->

Type

Method

Syntax

<!-- image -->

**Parameter**

The parameter ItemAlias of data type string designates the name of the alias of the element which you would like to read.

If you want to, you can also query the Group Name in addition to the Alias . You then have to type in the group name and a pipe symbol | , followed by the alias name.

<!-- image -->

Return Value

The return value has the data type any .

**Example**

```simtalk
print OPCUA.getItemValue("Random.INT4")
print OPCUA.getItemValue("MyGroup|MyAlias",5)
```

**See also**

Items [OPCUA]

setItemValue [SimTalk] - OPCUA

setItems [SimTalk] - OPCUA

Sets the items in the items table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setItems(ItemsTable:Table)

Parameter

The parameter Table of data type table designates the name of the table that contains the items.

Example

OPCUA.setItems(MyItemsTable)

See also

Items [OPCUA]

getItems [SimTalk] - OPCUA

setItemValue [SimTalk] - OPCUA

##### setItemValue [SimTalk] - OPCUA

setItemValue [SimTalk] - OPCUA

Sets the value of an item of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setItemValue(ItemAlias:string, NewValue:any)
```

**Parameters**

- The parameter ItemAlias of data type string designates the alias you defined. If you want to, you can also enter the Group Name in addition to the Alias . You then have to type in the group name and a pipe symbol | , followed by the alias name.
- The parameter NewValue of data type any designates the value you defined.

If setItemValue does not succeed in setting the value of an item for any reason, it raises a runtime error.

The method setItemValue can fail for three reasons:

1. The connection to the OPCUA server has not been established. ( OPCUA.Active = false ).
2. An item with the given alias does not exist.
3. The data type of the value-to-set does not match the data type of the item.

Example

OPCUA.setItemValue("Random.INT4",7) OPCUA.setItemValue("MyGroup|MyAlias",5)

See also

Items [OPCUA]

getItemValue [SimTalk] - OPCUA

OPC UA Communication Statistics

##### setUserAndPassword [SimTalk]

Sets the User Name and the Password with which Plant Simulation logs on to the OPC server.

Remarks

Plant Simulation saves the User Name and the Password to the model file.

Type

Method

Syntax

&lt; Path &gt;.setUserAndPassword(Username:string, Password:string)

**Parameters**

- The parameter Username of data type string designates the User Name . Specify an empty string "" or "anonymous" as the Password anonymous user without Password .
- to log on to the OPC server as an
- The parameter Password of data type string sets the Password .

Example

OPCUA.setUserAndPassword("john", "my:pAsswORd!123")

See also

Username [OPCUA]

Password [OPCUA]

#### Read-Only Attributes of the OPCUA Interface

Read-Only Attributes of the OPCUA Interface

The OPCUA Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyOPCUA.UUID

#### Attributes of the OPCUA Interface

\_Attributes of the OPCUA Interface

The OPCUA Interfaces provides:

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
OPCUAInterface.ServerName := "127.0.0.1"
print OPCUAInterface.ServerName
posit := Station.cont.XPos
```

##### Active [SimTalk] - OPCUA

Active [SimTalk] - OPCUA

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
OPCUAInterface.Active := true
```

See also

Active [check box] - OPCUA

##### CertificateFile [SimTalk]

Sets the file path to a certificate file on your computer of the object designated by &lt;Path&gt; or the object path to an object of type FileLink in the simulation model.

Remarks

The file has to contain a digital certificate. When Plant Simulation connects to the OPC server, it sends this certificate to the OPC server. This is necessary if the OPC server does not accept the generic certificate that Plant Simulation usually sends.

Type

Attribute

Syntax

&lt; Path &gt;.CertificateFile:string

Assignment Value

You can assign a value of data type string .

Example

OPCUAInterface.CertificateFile := "FileLink"

See also

Client Certificate

createCertificate [SimTalk]

##### DirectItemAccess [SimTalk]

Sets if you can directly access the items and groups of the object designated by &lt;Path&gt; via their name ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.DirectItemAccess:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
OPCUA.DirectItemAccess := true
i := OPCUA.ItemAlias
OPCUA.ItemAlias := 123
```

See also

Items [OPCUA]

setItemValue [SimTalk] - OPCUA

setItemValue [SimTalk] - OPCUA

##### SecurityMode [SimTalk]

Sets the message security mode of the object designated by &lt;Path&gt;.

Remarks

To enforce establishing an encrypted connection to the OPC server, set SecurityMode and SecurityPolicy to another value than "None" .

**Note**

The same values have to be set in the OPC server, as otherwise no connection can be established.

Type

Attribute

Assignment Value

You can assign a value of data type string .

You can specify "None" , "Sign" , or "SignAndEncrypt" . These are the settings that the OPC server provides and which are usually set in the OPC server.

**Note**

To be able to establish an encrypted connection to an OPC server, the OPC server usually needs to know and to trust the client certificate. Consult the documentation of your OPC server on how to configure the client certificate. You can normally find the client certificate of Plant Simulation here:

C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation\OPC PKI client\own\certs\default.der

Syntax

```simtalk
< Path >.SecurityMode:string
```

**Example**

```simtalk
OPCUAInterface.SecurityMode := "SignAndEncrypt"
OPCUAInterface.SecurityPolicy := "Basic256Sha256"
```

See also

Active [SimTalk] - OPCUA

Security Mode SecurityPolicy [SimTalk] Security Policy

##### SecurityPolicy [SimTalk]

Sets the security policy of the object designated by &lt;Path&gt;.

Remarks

To enforce establishing an encrypted connection to the OPC server, set SecurityPolicy and SecurityMode to another value than "None" .

**Note**

The same values have to be set in the OPC server, as otherwise no connection can be established.

Type

Attribute

Syntax

```simtalk
< Path >.SecurityPolicy:string
```

**Assignment Value**

You can assign a value of data type string .

You can specify "None" , "Basic128Rsa15" , "Basic256" , "Basic256Sha256" ,

"Aes128\_Sha256\_RsaOaep" , or "Aes256\_Sha256\_RsaPss" . These are the settings that the OPC server provides and which are usually set in the OPC server.

**Note**

To be able to establish an encrypted connection to an OPC server, the OPC server usually needs to know and to trust the client certificate. Consult the documentation of your OPC server on how to configure the client certificate. You can normally find the client certificate of Plant Simulation here:

C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation\OPC PKI client\own\certs\default.der

**Example**

```simtalk
OPCUAInterface.SecurityMode := "SignAndEncrypt"
OPCUAInterface.SecurityPolicy := "Basic256Sha256"
```

See also Active [SimTalk] - OPCUA Security Policy SecurityMode [SimTalk] Security Mode

##### ServerName [SimTalk] - OPCUA

Sets the server name to which you want to establish a connection. You have to set the attribute ServerName to the IP address of your OPC server so that the object designated by &lt;Path&gt; can establish a connection with the server.

Remarks

The port number to be used, 1005 in the example, either is configured in the server or it is provided by the server provider. Consult the documentation of your OPCUA server provider for more information.

**Note**

To establish the connection with a slow server, you can set a timeout with the attribute TimeOut .

Type

Attribute

Syntax

&lt; Path &gt;.ServerName:string

Assignment Value

You can assign a value of data type string .

Example

OPCUAInterface.ServerName := "opc.tcp://101.102.103.104:1005"

See also

Server Name [OPCUA]

TimeOut [SimTalk]

##### StatisticsActive [SimTalk] - OPCUA

Sets if the object designated by &lt;Path&gt; collects statistics values for the CPU time usage ( true ) or not ( false ).

Remarks

This can help you in finding the optimal setting for your read and write intervals.

Type

Attribute

Syntax

&lt; Path &gt;.StatisticsActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

OPCUAInterface.myAttribute.StatisticsActive := true

##### TimeOut [SimTalk]

Sets the timeout of the object designated by &lt;Path&gt; for the communication with the OPC server.

Remarks

This might be necessary to establish the connection with a slow server.

Type

Attribute

Syntax

&lt; Path &gt;.TimeOut:time

Assignment Value

You can assign a value of data type time .

Example

OPCUAInterface.TimeOut := 15 // increase timeout to 15 seconds

See also

Timeout [text box]

#### OPCClassic

