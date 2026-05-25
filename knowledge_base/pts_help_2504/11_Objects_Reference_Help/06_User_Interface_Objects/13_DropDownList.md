### DropDownList

#### DropDownList [object]

Use the DropDownList for showing a drop-down list in the Frame . When you select one of the items, it executes the action which you programmed in the control.

**DropDownList [object]**

Icon

<!-- image -->

**Description**

The DropDownList provides the user with several options, one of which he can select. You can define the items, which the DropDownList shows, either in its dialog or with the attribute Items .

Whenever the user of your DropDownList selects another item, the drop-down list executes the action which you programmed in the Control .

The DropDownList looks like this in 2D and in 3D by default:

<!-- image -->

**Note**

In 3D Plant Simulation only accepts the click the DropDownList if it occupies at least 10 pixels in each direction in the model window. If you zoom out very far, the picture of the DropDownList might become too small, preventing Plant Simulation to recognize it reliably.

To open its dialog box, click the drop-down list with the right mouse button and select Open on the context menu.

<!-- image -->

To select the drop-down list in the Frame window, you can also drag a marquee over its icon.

You can also click a DropDownList and select an item in it in a sub-Frame and trigger the respective action.

<!-- image -->

To show a tooltip with information about the DropDownList , hover with the mouse over it.

To change the length of the graphic and the anchor points of the DropDownList , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the DropDownList to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; DropDownList on the Home ribbon tab.

See also

Select an Option from a Drop-down List

Configure the Check Box and the Drop-down List

#### Dialog Box of the DropDownList

Dialog Box of the DropDownList

Click the DropDownList , which you inserted into a Frame , with the right mouse button and select Open on the context menu to open its dialog box.

<!-- image -->

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

**Edit Animation Properties**

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

###### Tab Attributes

##### Tab Attributes

The tab Attributes provides the settings, which the object offers.

The settings are listed in the table of contents to the left.

The shared properties are described under the Tab Attributes .

<!-- image -->

###### Use Icon [check box] - Drop-down List

To show the DropDownList in the Frame in a 2D Only model with its current icon which you draw, select this check box.

<!-- image -->

Clear the check box to show the drop-down list with its default icon. Then, draw your icon in the icon editor .

When you select Use Icon , Plant Simulation shows the drop-down list with the width of the icon of the DropDownList , not with the Width you type into the dialog. To change the width, hold down Ctrl+Shift and drag the left or right side of the icon.

<!-- image -->

**SimTalk**

UseIcon [SimTalk] - DropDownList

See also

Window of the Icon Editor

###### Width [text box] - DropDownList

###### Width [text box] - DropDownList

Type in the Width in meters with which the DropDownList is shown in the Frame .

<!-- image -->

If you type in long names for the Items , you have to adjust the width so that the names of the items in the drop-down list are not cut off.

<!-- image -->

If you check Use Icon in a 2D Only model, the object is shown with the width of the icon.

To change the width, you can also hold down Ctrl+Shift and drag the left or right side of the icon. Plant Simulation shows the width in meters.

**SimTalk**

ObjectWidth [SimTalk] - DropDownList

###### Height [text box] - DropDownList

Type in the Height in meters with which the DropDownList is shown in the Frame .

<!-- image -->

If you type in a Height of more than 30 pixels, Plant Simulation uses a larger font to display the Label of the drop-down list.

<!-- image -->

To change the height, you can also hold down Ctrl+Shift and drag the top or the bottom of the icon.

**SimTalk**

ObjectHeight [SimTalk] - DropDownList

###### Value [text box] - DropDownList

Value [text box] - DropDownList

Type in which item in the DropDownList will be selected when you open it.

<!-- image -->

This is one of the items which you typed into the list of Items .

The value is identified by its index number.

<!-- image -->

**Note**

If you localize the items to another language, you will usually use the Value instead of the attribute Item . The value is a number which is language-independent, while the Item is a string which differs from language to language.

**SimTalk**

Value [SimTalk] - DropDownList

###### Items [button] - DropDownList

To open the list, into which you type the Items which the DropDownList displays when you click it, click this.

<!-- image -->

<!-- image -->

If you want to use the index number to access an item in the list, use the attribute Value .

If you want to use the name to access an item in the list, use the attribute Item .

**SimTalk**

Items [SimTalk] - DropDownList

Item [SimTalk] - DropDownList

See also

Configure the Feeder Line with Sensor and Sensor Control

**Control [DropDownList]**

###### Control [DropDownList]

Click the ellipsis button and select a Method object in the dialog Select Object. Type in the source code of the control , which is called when you select an item from the DropDownList in the Frame .

<!-- image -->

The anonymous identifiers ? and @ in the control are set to the DropDownList when the method is called.

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

A control might, for example, look like this:

switch ?.Value

case 1

```simtalk
print "Item 1 selected"
print "Item 2 selected"
```

case 2 end

SimTalk

Control [SimTalk] - DropDownList

See also

Select Object [for controls]

Configure the Check Box and the Drop-down List

Item [SimTalk] - DropDownList

Value [SimTalk] - DropDownList

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the DropDownList

Methods of the DropDownList

The DropDownList provides the Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

#### Read-Only Attributes of the DropDownList

Read-Only Attributes of the DropDownList

The DropDownList provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyDropDownList.UUID
```

#### Attributes of the DropDownList

\_Attributes of the DropDownList

The DropDownList provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyDropdownList.UseIcon := false
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyDropdownList.UseIcon
posit := Station.Cont.XPos
```

##### Control [SimTalk] - DropDownList

##### Control [SimTalk] - DropDownList

Sets the Control which the DropDownList designated by &lt;Path&gt; executes when you select an item in the DropDownList in the Frame .

Remarks

The anonymous identifiers ? and @ are set to the DropDownList when the method is called.

Type

Attribute

Syntax

```simtalk
< Path >.Control:string
```

**Assignment Value**

You can assign a value of data type string .

**Examples**

```simtalk
MyDropdownList.Control := "myControl"
switch
	?.Value
case 1
	print "Item 1 selected"
case 2
	print "Item 2 selected"
end
```

**See also**

**Control [DropDownList]**

Item [SimTalk] - DropDownList

Sets which Item in the DropDownList designated by &lt;Path&gt; will be selected using its name.

Remarks

If you localize the items, you will usually use the attribute Value instead of the attribute Item . The value is a number which is language-independent, while the Item is a string which differs from language to language.

Type

Attribute

Syntax

```simtalk
< Path >.Item:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDropdownList.Item := "My item text 1"
```

SimTalk

Items [SimTalk] - DropDownList

Value [SimTalk] - DropDownList

See also

Items [button] - DropDownList

##### Items [SimTalk] - DropDownList

Items [SimTalk] - DropDownList

Sets or gets the Items which the DropDownList designated by &lt;Path&gt; shows.

Remarks

If you want to use the index number to access an item in the list, use the attribute Value .

If you want to use the name to access an item in the list, use the attribute Item .

Type

Attribute

Syntax

< Path >.Items:array

Assignment Value

You can assign a value of data type array .

Example

```simtalk
var a :
string[] := ["Item 1", "Item 2", "Item 1"]
MyDropdownList.Items := a
```

SimTalk

Value [SimTalk] - DropDownList

Item [SimTalk] - DropDownList

See also

Items [button] - DropDownList

Configure the Feeder Line with Sensor and Sensor Control ObjectHeight [SimTalk] - DropDownList Sets the Height of the Drop-Down List designated by &lt;Path&gt; with which it is shown in the Frame .

Type

Attribute

Syntax

&lt; Path &gt;.ObjectHeight:integer

Assignment Value

You can assign a value of data type integer .

Example

MyDropDownList.ObjectHeight := 1 // meter

See also

Height [text box] - DropDownList ObjectWidth [SimTalk] - DropDownList Sets the Width of the DropDownList designated by &lt;Path&gt; with which it is shown in the Frame .

Remarks

If you enter long identifiers for the Items , you have to adjust the width so that the label fits on the DropDownList without the text being cut off.

If you select Use Icon width of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.ObjectWidth:integer

Assignment Value

You can assign a value of data type integer .

Example

MyDropDownList.ObjectWidth := 4 // meters

See also

Width [text box] - Button

Items [button] - DropDownList in a 2D Only model , the DropDownList is shown with the

##### UseIcon [SimTalk] - DropDownList

Sets if the DropDownList designated by &lt;Path&gt; is displayed in the Frame with its current icon ( true ) or with the default look which we defined ( false ).

Remarks

Note

A 3D Only model does not provide the attribute UseIcon .

Type

Attribute

Syntax

&lt; Path &gt;.UseIcon:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDropdownList.UseIcon := false

See also

Use Icon [check box] - Drop-down List Value [SimTalk] - DropDownList Value [SimTalk] - DropDownList Sets which item in the DropDownList designated by &lt;Path&gt; will be selected. Plant Simulation uses the index number of the item to do so.

Remarks

If you localize the items to other languages, you will usually use the attribute Value instead of the attribute Item . The value is a number which is language-independent, while the Item is a string which differs from language to language.

Type

Attribute

Syntax

```simtalk
< Path >.Value:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDropdownList.Value := 3
```

SimTalk

Item [SimTalk] - DropDownList

See also

Value [text box] - DropDownList

