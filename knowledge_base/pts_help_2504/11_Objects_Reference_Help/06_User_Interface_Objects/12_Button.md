### Button

#### Button [object]

Use the Button for showing a button in the Frame . When you click the button, it executes the action which you programmed in a control.

Icon

<!-- image -->

Description

The Button executes the action, which you programmed in the Control , when the user clicks it.

If you type in a label for the button, Plant Simulation shows that label on the button in the Frame .

<!-- image -->

By default, Plant Simulation does not show the name of the button as a tooltip in the Frame when you roll the mouse over it. To show your own tooltip, create a user-defined attribute and name it Tooltip .

<!-- image -->

Plant Simulation can show the button in the Frame in a number of ways:

<!-- image -->

- With the label you type in .
- With an icon you draw in the icon editor . Then, you can show text you type in as the label on that button, for example.
- With a picture you pasted into a new icon in the icon editor , and for example. You could
- name the icons play and play\_down for example.

To open its dialog box, click the button with the right mouse button and select Open on the context menu.

<!-- image -->

You can also click a Button in a sub-Frame and trigger the respective action.

<!-- image -->

To select the button in the Frame window, you can also drag a marquee over its icon.

By default, the Button looks like this in 2D and in 3D:

<!-- image -->

**Note**

In 3D Plant Simulation only accepts the click the Button if it occupies at least 10 pixels in each direction in the model window. If you zoom out very far, the picture of the Button might become too small, preventing Plant Simulation to recognize it reliably.

To show a tooltip with information about the Button , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Button , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

**Add the Object to the Simulation Model**

<!-- image -->

To add the Button to your simulation model, click UserInterface &gt; Button on the Home ribbon tab.

See also

Execute the Action

Select an Option from a Drop-down List

Configure the Buttons to Open Parts Table and Callback Method

##### Dialog Box of the Button

Dialog Box of the Button

Click the Button , which you inserted into a Frame , with the right mouse button and select Open on the context menu to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

Use Icon [check box] - Button

To show the Button in the Frame in a 2D Only model with its current icon, select this check box.

Note

A 3D Only model does not provide the setting Use Icon .

Clear the check box to show the Button with its default look.

<!-- image -->

The default look also displays the Label which you typed in as button text. Using an icon is especially handy if you want to show a picture on the button instead of text. Then, draw your icon in the icon editor .

If you select Use Icon , Plant Simulation shows the button with the width of the icon of the Button , not with the Width you type into the dialog. To change the width, hold down Ctrl+Shift and drag the left or right side of the icon.

<!-- image -->

You can use this feature in several ways:

- You can create a new icon in the icon editor and draw or paste a picture on that icon. For the example
- above we drew a green rectangle inside the button . Then, we typed in the label . To be able to tell that you clicked the button, we recommend to draw two pictures for the button, one for the unclicked state and one for the clicked state . For our example above the name of the unclicked icon is icon3 , the name of the clicked icon consequently has to be icon3\_down . The button does not stay pressed, but returns to its unclicked state when you release the mouse button.
- You can create a new icon in the icon editor and paste a picture into it, and for example.

<!-- image -->

<!-- image -->

<!-- image -->

SimTalk

UseIcon [SimTalk] - Button

**See also**

**Window of the Icon Editor**

**Width [text box] - Button**

Width [text box] - Button

Type in the Width in meters with which the object is displayed in the Frame .

If you type in long text, you have to adjust the width so that the text fits into the object boundaries without being cut off.

If you check Use Icon the icon.

in a 2D Only model , the object is shown with the width of

To change the width, you can also hold down Ctrl+Shift and drag the left or the right side of the icon.

Plant Simulation shows the Width in meters.

<!-- image -->

**Height [text box] - Button**

Type in the Height in meters with which the object is displayed in the Frame .

<!-- image -->

To change the height, you can also hold down Ctrl+Shift and drag the top or the bottom of the icon.

Plant Simulation shows the Height in meters.

<!-- image -->

SimTalk

ObjectHeight [SimTalk] - Button

**Control [Button]**

###### Control [Button]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the control , which is called when you click the Button .

<!-- image -->

The anonymous identifiers ? and @ are set to the object when the method is called. Specify a control without parameter to call the control one time when you release the Button .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Parameter**

You can also specify a control which expects a boolean value as parameter. This control is called with the value true when you click the Button and with the value false when you release it.

Plant Simulation executes the control when you change the size of the Button or when you move it with Drag-and-Drop. If the control does not expect a parameter it will be called, as before, when you release the Button .

**Example**

A control might, for example, look like this:

```simtalk
self.~.~.DataTable.openDialog self.~.~.&MyMethod.openDialog // opens the dialog of the // method MyMethod, instead of executing its source code end
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
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

Control [SimTalk] - Button

See also

Select Object [for controls]

**Tab User-defined**

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

By default Plant Simulation does not show the name of the button as a tooltip in the Frame window. To show a your own tooltip, you can create a user-defined attribute and name it Tooltip .

<!-- image -->

**Navigate Menu**

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

##### Methods of the Button

#### Methods of the Button

The Button provides the Methods of All Objects .

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

#### Read-Only Attributes of the Button

Read-Only Attributes of the Button

The Button provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

**Attributes of the Button**

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyButton.UUID
```

**Attributes of the Button**

##### \_Attributes of the Button

The Button provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyButton.UseIcon := false
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyButton.UseIcon
posit := Station.Cont.XPos
```

##### Control [SimTalk] - Button

Control [SimTalk] - Button

Sets the Control , which the Button designated by &lt;Path&gt; executes when you click it.

Remarks

The anonymous identifiers ? and @ are set to the Button when the method is called.

You can also enter a control which expects a boolean value as parameter. This control is called with the value true when you click the Button and with the value false when you release it.

The control is also called when you change the size of the Button or when you move it with Drag-andDrop. If the control does not expect a parameter it will be called, as before, when you release the button.

Type

Attribute

Syntax

```simtalk
< Path >.Control:string
```

Assignment Value

You can assign a value of data type string .

Examples

```simtalk
MyButton.Control := "myControl"
self.~.~.&MyMethod.openDialog
```

ObjectHeight [SimTalk] - Button

Sets the Height of the Button designated by &lt;Path&gt; with which it is shown in the Frame .

Remarks

For an object height of more than 30 pixels the button shows the text of the label with a larger front size.

Type

Attribute

Syntax

&lt; Path &gt;.ObjectHeight:integer

Assignment Value

You can assign a value of data type integer .

Example

MyButton.ObjectHeight := 1 // meter

SimTalk

Height [text box] - Button

ObjectWidth [SimTalk] - Button ObjectWidth [SimTalk] - Button Sets the Width of the Button designated by &lt;Path&gt; with which it is shown in the Frame .

Remarks

If you enter a long label, you have to adjust the width so that the label fits on the button without the text being cut off.

If you select Use Icon the icon.

Type

Attribute

Syntax

&lt; Path &gt;.ObjectWidth:integer

Assignment Value

You can assign a value of data type integer .

Example

MyButton.ObjectWidth := 4 // meters

SimTalk

Width [text box] - Button

ObjectHeight [SimTalk] - Button in a 2D Only model , the button is shown with the width of

**UseIcon [SimTalk] - Button**

Sets if the Button designated by &lt;Path&gt; is displayed in the Frame with its current icon ( true ) or as a box ( false ).

Remarks

A 3D Only model does not provide this attribute.

<!-- image -->

| Use icon off, label   | Use icon off, no label   | Use icon on, default label   | Use icon on, your icon, your label   |
|-----------------------|--------------------------|------------------------------|--------------------------------------|

Type

Attribute

Syntax

&lt; Path &gt;.UseIcon:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyButton.UseIcon := false
```

See also

Use Icon [check box] - Button

