### ActiveX

The object ActiveX provides the interface between Plant Simulation and the ActiveX controls . It enables you to embed ActiveX controls into a Plant Simulation Frame . You can access methods and attributes of ActiveX controls using methods and attributes .

Icon

<!-- image -->

Description

**Note**

ActiveX is part of the Plant Simulation Interface Package .

**Note**

The object ActiveX requires 64-bit ActiveX controls .

ActiveX is an object technology allowing you to activate objects ( ActiveX controls or other COM objects) within a container application and to exchange data with these objects using defined interfaces.

You can select from a wide variety of ActiveX controls , or you can develop them yourself, provided you have the appropriate development tools, such as Microsoft Visual C++, Microsoft Visual Basic, etc. An example of ActiveX controls which you daily use with MS Windows is the Media Player .

An ActiveX control has to register itself with the operating system so that you can use it. The control may either register with the program regsvr32.exe or with Plant Simulation . In Plant Simulation you can only use 64-bit ActiveX controls .

If you activate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , access to ActiveX via SimTalk will be prevented.

To show a tooltip with information about the ActiveX Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the ActiveX Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the ActiveX Interface to the Class Library , click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; ActiveX on the Home ribbon tab.

<!-- image -->

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Play a Video in Your Simulation Model

Accessing Methods and Attributes

Converting Data Types Between Plant Simulation and ActiveX

#### Dialog Box of the ActiveX Interface

Dialog Box of ActiveX

Double-click the icon of ActiveX to open its dialog box.

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

**Edit Animation Properties**

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**Name [text box] - ActiveX**

##### Name [text box] - ActiveX

Type in a name of your choice for the object ActiveX or accept the name which Plant Simulation suggests.

<!-- image -->

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyActiveX , MyActiveX1 , My\_ActiveX\_1 .

The name of an object cannot start with a digit, i.e., you cannot type in 1ActiveX .

SimTalk

Name [SimTalk] - general description

##### Label [text box] - ActiveX

Type a label for ActiveX into the text box Label .

<!-- image -->

Plant Simulation shows the label in the title bar of the window when you activate the object ActiveX outside of the Frame .

SimTalk

Label [SimTalk]

**Active [check box] - ActiveX**

##### Active [check box] - ActiveX

To activate the ActiveX control , select this check box. To deactivate it, clear the check box.

<!-- image -->

**Note**

You can only activate the ActiveX control after you entered the Class Name and the Callback Method !

Instead, you can also right-click the ActiveX object in the Frame and select Enable on the context menu.

To deactivate it, select Deactivate on the context menu.

SimTalk

Active [SimTalk] - ActiveX

See also

Class Name [text box]

Callback Method [ActiveX]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Class Name [text box]

Type in the Class Name of the required ActiveX control .

<!-- image -->

The command Tools &gt; ActiveX Class Overview opens a table that shows all ActiveX controls , which are installed on your computer.

You might, for example, type in excel.application , for Microsoft Excel, word.application , for Microsoft Word, or access.application for Microsoft Access.

SimTalk

ClassName [SimTalk]

See also

ActiveX Class Overview

**License Key [text box]**

###### License Key [text box]

Type in the license key if the ActiveX control requires one. Normally no license key is required.

SimTalk

LicenseKey [SimTalk]

###### Callback Method [ActiveX]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Callback Method , which is called as soon as the ActiveX control triggers an event.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

A Callback Method might look like this:

```simtalk
param event: integer, a,b,c,d: any
if event=1
	print MyActiveX.PercentDone
end
```

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

**Callback Method [ActiveX]**

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

Callback [SimTalk]

See also

Select Object [for controls]

###### Display in Frame [check box] - ActiveX

To show the active ActiveX control in the Frame , into which you inserted object ActiveX , select this check box.

**Note**

A 3D Only model does not provide Display in Frame .

Plant Simulation then shows the icon of the ActiveX control on top of the icon of the object.

<!-- image -->

**Note**

You cannot scale or move the icon of ActiveX controls , which are activated in the Frame .

SimTalk

InFrame [SimTalk]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

Navigate Menu The commands are described under the Navigate Menu . View Menu View Menu The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] ActiveX Class Overview Type Info [ActiveX] SimTalk updateDialog [SimTalk] See also View Menu [general description]

**ActiveX Class Overview**

###### ActiveX Class Overview

Opens a table displaying all ActiveX controls installed on your computer.

The column Class Name shows the name of the ActiveX class. Type this name into the text box Class name of the ActiveX dialog.

The columns Comment and Server contain additional information that Plant Simulation does not use.

<!-- image -->

**SimTalk**

overview [SimTalk]

###### Type Info [ActiveX]

Opens a table, which displays all methods and attributes of the active ActiveX control .

An ActiveX control does not necessarily have to provide this interface documentation. If documentation is not available, the table will show the message Type info not supported . Limited access to the attributes/ methods is still possible though.

<!-- image -->

- The column Attribute/Method shows a symbolic name of the attribute or of the method.
- The column ID shows the internal number of the respective attribute/method. You can also use this number to call methods.
- The column Comment shows the description of the attribute.
- The column Type Info shows the type, i.e., if the control is an attribute or a method:
- METHOD: This is a method.
- PROPERTYPUT: This is an attribute that you can assign.
- PROPERTYGET: This is an attribute you can read out but cannot assign.
- The column Parameters contains the kind and the number of the parameters of methods.

Instead, you can also right-click the ActiveX object in the Frame and select Type Info on the context menu.

<!-- image -->

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

Help Menu

The commands are described under the Help Menu .

#### Accessing Methods and Attributes

Accessing Methods and Attributes

You can call the attributes and the methods of an activated ActiveX control just like you would call any attribute or method in Plant Simulation . If ActiveX and Plant Simulation attributes and methods have the same name, the ActiveX attribute takes precedence.

Compare the following examples for the Media Player .

**Media Player**

##### Media Player

The methods and attributes below refer to a Media Player example of class ' AMOVIE.ActiveMovie Control.1. '

aboutBox

**Syntax**

&lt; Path &gt;.aboutBox

The method aboutBox opens the dialog Info of the control.

**Example**

MyActiveX.aboutBox

FileName

**Syntax**

&lt; Path &gt;.FileName

The attribute FileName loads the file designated by the parameter of data type string .

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
MyActiveX.FileName:="C:\users\yourname\shania.avi"
```

run

**Syntax**

&lt; Path &gt;.run

The method run starts playing the media file.

**Example**

MyActiveX.run

ShowPositionControls

**Syntax**

&lt; Path &gt;.ShowPositionControls

The attribute ShowPositionControls sets if the position controls of the Media Player are displayed ( true ) or not ( false ).

**Assignment Value**

You can assign a value of data type boolean .

**Example**

MyActiveX.ShowPositionControls:=false

#### Converting Data Types

Converting Data Types Between Plant Simulation and ActiveX

The data types which Plant Simulation and ActiveX use are not identical. Data types are converted according to these tables. Passing parameters as reference (VT\_BYREF) is not supported.

Converting Data from Plant Simulation to ActiveX

Data types are converted from Plant Simulation to ActiveX as follows:

| Plant Simulation Data Type   | ActiveX Data Type   |
|------------------------------|---------------------|
| integer                      | VT_I2               |
| real                         | VT_R8               |
| length                       | VT_R8               |
| weight                       | VT_R8               |
| speed                        | VT_R8               |
| time                         | VT_R8               |

| Plant Simulation Data Type   | ActiveX Data Type   |
|------------------------------|---------------------|
| boolean                      | VT_BOOL             |
| string                       | VT_BSTR             |
| All others                   | VT_BSTR             |

Converting Data from ActiveX to Plant Simulation

Data types are converted from ActiveX to Plant Simulation as follows:

| ActiveX Data Type              | Plant Simulation Data Type                               |
|--------------------------------|----------------------------------------------------------|
| VT_UI1, VT_BYREF&#124;VT_UI1   | integer                                                  |
| VT_I2, VT_BYREF&#124;VT_I2     | integer                                                  |
| VT_I4, VT_BYREF&#124;VT_I4     | integer                                                  |
| VT_R4, VT_BYREF&#124;VT_R4     | real                                                     |
| VT_R8, VT_BYREF&#124;VT_R8     | real                                                     |
| VT_BOOL, VT_BYREF&#124;VT_BOOL | boolean                                                  |
| VT_BSTR, VT_BYREF&#124;VT_BSTR | string                                                   |
| VT_ERROR                       | string (error message in the Plant Simulation Debugger ) |
| All others                     | void                                                     |
| VT_I2, VT_BYREF&#124;VT_I2     | integer                                                  |

##### ActiveX Events

If an ActiveX control triggers an event, Plant Simulation starts the method that you entered into the text box Callback Method .

Parameter

A parameter of data type integer containing the event ID is passed to this method.

A callback method might look like this:

```simtalk
param event: integer
param a,b,c,d: any
if event=1
	print MyActiveX.PercentDone
end
```

**See also**

Callback Method [ActiveX]

##### Persistence

Some ActiveX controls can save their state to a file and restore that state when they are activated again, provided the ActiveX control has implemented the IPersist interface.

If this interface is not available, Plant Simulation saves the data to a temporary file and uses that file when the control is called again. As soon as the model file is saved, the data is added to it.

#### Methods of the ActiveX Interface

##### \_Methods of the Object ActiveX

The object ActiveX provides:

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

##### getParam [SimTalk]

getParam [SimTalk]

Returns the contents of a parameter of the ActiveX object designated by &lt;Path&gt;.

Remarks

**Note**

Using the attribute/method ID in the call is slightly faster, as otherwise Plant Simulation has to find the ID of the name of the attribute or method first.

Type

Method

Syntax

< Path >.getParam(Parameter:any, Parameter:any, ...) → any

Parameter

The parameters Parameter of data type any designate the contents of the parameter.

Return Value

The return value has the data type any .

Example

```simtalk
print MyActiveX.getParam("FileName")
print MyActiveX.getParam(3) // 3 is the ID of the attribute FileName
```

See also

putParam [SimTalk]

##### invoke [SimTalk]

Calls a method if the type information of the ActiveX object designated by &lt;Path&gt; is not available, preventing you from calling methods directly.

Remarks

Using the attribute/method ID in the call is slightly faster, as otherwise Plant Simulation has to find the ID of the name of the attribute or method first.

Type

Auxiliary method

Syntax

```simtalk
< Path >.invoke(Method:any, Parameter:any, ...) → boolean
```

**Parameters**

- The parameter Method of data type any designates the name of the method or the ID of the method of the ActiveX control .
- All additional parameters of data type any are going to be passed to the method that is called.

Return Value

The return value has the data type boolean .

Example

MyActiveX.invoke("Navigate", "www.siemens.com") MyActiveX.invoke(104, "www.siemens.com")

load [SimTalk] - ActiveX

load [SimTalk] - ActiveX

Loads an ActiveX control into the ActiveX object designated by &lt;Path&gt; from a file.

Type

Method

Syntax

```simtalk
< Path >.load(Filename:string) → boolean
```

Parameter

The parameter FileName of data type string designates the name of the control.

Return Value

The return value has the data type boolean .

true if the control was loaded.

false if it could not be loaded.

Example

MyActiveX.load("MyActiveX")

overview [SimTalk]

Returns the class overview of all ActiveX controls installed on your computer of the ActiveX object designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.overview → list

Return Value

The return value has the data type list .

Example

```simtalk
print MyActiveX.overview
```

See also

ActiveX Class Overview

##### putParam [SimTalk]

putParam [SimTalk]

Sets the parameter, the name, or the ID of a parameter of an ActiveX control of the ActiveX object designated by &lt;Path&gt;.

Remarks

Using the attribute/method ID in the call is slightly faster, as otherwise Plant Simulation has to find the ID of the name of the attribute or method first.

Type

Method

Syntax

```simtalk
< Path >.putParam(Parameter:any, Parameter:any, ...) → boolean
```

Parameter

The parameter named Parameter of data type any designates the contents of the parameter.

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyActiveX.putParam(3,"C:\temp\t.txt") // 3 is the ID of the attribute
print MyActiveX.putParam("FileName","C:\temp\t.txt") FileName
```

See also

getParam [SimTalk]

registerControl [SimTalk]

Registers an ActiveX control of the ActiveX object designated by &lt;Path&gt; with the operating system.

Type

Method

Syntax

&lt; Path &gt;.registerControl(Name:string) -&gt; boolean

Parameter

The parameter Name of data type string designates the name of the control.

Return Value

The return value has the data type boolean .

Example

MyActiveX.registerControl("MyActiveX")

See also

unregisterControl [SimTalk]

##### save [SimTalk] - ActiveX

save [SimTalk] - ActiveX

Saves the data of the ActiveX object designated by &lt;Path&gt; to a file.

Type

Method

Syntax

```simtalk
< Path >.save(Filename:string) → boolean
```

Parameter

The parameter FileName of data type string designates the name of the file to which you want to save the data.

Return Value

The return value has the data type boolean .

true if the file has been saved.

false if the file has not been saved.

Example

MyActiveX.save("MyActiveX")

##### setWindowPosition [SimTalk] - ActiveX

Sets the position at which Plant Simulation shows the window of the ActiveX object designated by &lt;Path&gt; on screen.

Type

Method

Syntax

```simtalk
< Path >.setWindowPosition(X:integer, Y:integer, Width:integer, Height:integer) → boolean
```

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the window.
- The parameter Y of data type integer designates its y-coordinate.
- The parameter Width of data type integer designates the width of the window.
- The parameter Height of data type integer designates its height.

**Return Value**

The return value has the data type boolean .

Example

MyActiveX.setWindowPosition(100,150,90,90)

##### typeInfo [SimTalk]

typeInfo [SimTalk]

Returns the type information table of the ActiveX object designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.typeInfo → list

Return Value

The return value has the data type list .

Example

```simtalk
print MyActiveX.typeInfo
```

See also

Type Info [ActiveX]

unregisterControl [SimTalk]

Unregisters an ActiveX control of the ActiveX object designated by &lt;Path&gt; with the operating system.

Type

Method

Syntax

```simtalk
< Path >.unregisterControl(Name:string) → boolean
```

Parameter

The parameter Name of data type string designates the name of the control.

Return Value

The return value has the data type boolean .

Example

MyActiveX.unregisterControl("MyActiveX")

See also

registerControl [SimTalk]

#### Read-Only Attribute of the ActiveX Interface

Read-Only Attribute of the ActiveX Interface

The ActiveX Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of the ActiveX Interface

**\_Attributes of the ActiveX Interface**

The object ActiveX provides:

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
MyActiveX.CallBack := &MyActiveXMethod
print MyActiveX.CallBack
posit := Station.cont.XPos
```

##### Active [SimTalk] - ActiveX

Active [SimTalk] - ActiveX

Activates the ActiveX object designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

You can only activate the ActiveX control after you specified the Class Name and the Callback Method !

Type

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyActiveX.Active := true

See also

Active [check box] - ActiveX

ClassName [SimTalk]

Callback [SimTalk]

##### Callback [SimTalk]

Sets the Callback Method of the ActiveX object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as the ActiveX control triggers an event.

Type

Attribute

Syntax

< Path >.Callback:method

Assignment Value

You can assign a value of data type method .

Example

```simtalk
MyActiveX.CallBack := &MyActiveXCallbackMethod
```

A callback method might look like this:

```simtalk
param event: integer, a,b,c,d: any
if event=1
	print MyActiveX.PercentDone
end
```

See also

Callback Method [ActiveX]

##### ClassName [SimTalk]

ClassName [SimTalk]

Sets the Class Name of the ActiveX class of the ActiveX object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.ClassName:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyActiveX.ClassName := "Image"
```

See also

Class Name [text box]

##### InFrame [SimTalk]

Sets if the active ActiveX control will be displayed inside the Frame into which you inserted of ActiveX object designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

**Note**

A 3D Only model does not provide the attribute InFrame .

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.InFrame:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyActiveX.InFrame := true

**See also**

**Display in Frame [check box] - ActiveX**

LicenseKey [SimTalk]

Sets the License Key of the ActiveX object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.LicenseKey:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyActiveX.LicenseKey := "MyLicenseKey123"
```

See also

License Key [text box]

