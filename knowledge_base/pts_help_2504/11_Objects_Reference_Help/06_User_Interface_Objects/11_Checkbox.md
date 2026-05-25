### Checkbox

#### Checkbox [object]

Use the Checkbox for toggling between the states on and off, for toggling operating modes, etc.

Icon

<!-- image -->

Description

The Checkbox switches between the states on and off , it switches operating modes, it switches between runtime mode and debug mode, etc.

By default, the Checkbox looks like this in 2D and in 3D:

<!-- image -->

| Appearance in 2D   | Appearance in 3D   |
|--------------------|--------------------|

**Note**

In 3D Plant Simulation only accepts the click the Checkbox if it occupies at least 10 pixels in each direction in the model window. If you zoom out very far, the picture of Checkbox might become too small, preventing Plant Simulation to recognize it reliably.

<!-- image -->

To change between the on and the off state of the Checkbox , click the picture.

<!-- image -->

To open the dialog of the object Checkbox , double-click the name Checkbox to the right of the icon

<!-- image -->

.

You can create any number of icons for the Checkbox . Plant Simulation automatically switches between the icons of the check box according to their name/state. Assign the icons pairs of names according to their state, for example TrueIcon1 and FalseIcon1 .

You can also click the Checkbox in a sub-Frame and switch the value. Compare the check box Show Warehouse Content in the Factory51 model.

<!-- image -->

To show a tooltip with information about the Checkbox , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Checkbox , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

<!-- image -->

To add the Checkbox to your simulation model, click UserInterface &gt; Checkbox on the Home ribbon tab.

See also

Switch States with the Checkbox

Select an Option from a Drop-down List

Configure the Check Box and the Drop-down List

Show and Hide Display Panels with a Check Box

#### Dialog Box of the Checkbox

Dialog Box of the Checkbox

Double-click the name Checkbox to the right of the icon

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

in the Frame to open its dialog box.

Tab Data

Tab Data [Checkbox]

The tab Data provides the settings listed in the table of contents to the left.

###### Value [drop-down list] - Checkbox

Value [drop-down list] - Checkbox

Select if the Checkbox is active ( true ) or not ( false ).

<!-- image -->

The Checkbox looks like this in 2D and in 3D by default:

<!-- image -->

| Appearance in 2D   | Appearance in 3D   |
|--------------------|--------------------|

Plant Simulation automatically switches between the icons of the check box according to their name/state. Always create a set of two icons, one for on and one for off , and name them accordingly.

Assign names in pairs to the icons according to their state, for example TrueIcon1 and FalseIcon1 .

SimTalk

Value [SimTalk] - Checkbox

###### Control [Checkbox]

Modifies the built-in behavior of the object. The object calls the Method when the Value of the Checkbox changes when you click it.

<!-- image -->

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Control .

Plant Simulation only calls the Control of the object itself, not of instances of the object.

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

The standard OnClicked control as a user-defined attribute looks like this:

<!-- image -->

SimTalk Control [SimTalk] - Checkbox See also Select Object [for controls] Value [drop-down list] - Checkbox Configure the Check Box and the Drop-down List

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

**Tools Menu**

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

**Help Menu**

The commands are described under the Help Menu .

##### Methods of the Checkbox

Methods of the Checkbox

The Checkbox provides the Methods of All Objects .

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

##### Read-Only Attributes of the Checkbox

Read-Only Attributes of the Checkbox

The Checkbox provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyCheckbox.UUID
```

#### Attributes of the Checkbox

**\_Attributes of the Checkbox**

The Checkbox provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyCheckbox.Value := false
```

**\_Attributes of the Checkbox**

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyCheckbox.Value
posit := Station.Cont.XPos
```

**Control [SimTalk] - Checkbox**

Sets the control which the Checkbox designated by &lt;Path&gt; executes.

Remarks

Plant Simulation calls the Control when the value changes when you click the object.

Plant Simulation only calls the Control of the object itself, not of instances of the object.

Type

Attribute

Syntax

&lt; Path &gt;.Control:method

**Assignment Value**

You can assign a value of data type method .

Example

MyCheckbox.Control := "myControl"

See also

Control [Checkbox]

##### Value [SimTalk] - Checkbox

Value [SimTalk] - Checkbox

Activates ( true ) or deactivates ( false ) the Checkbox designated by &lt;Path&gt;. The Checkbox executes a Control when its value changes.

Syntax

```simtalk
< Path >.Value:boolean
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCheckbox.Value := false
```

See also

Value [drop-down list] - Checkbox

Control [Checkbox]

