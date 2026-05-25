### Interface

Use the Interface for modeling transitions between Frames , i.e., from one part of the model to another. It also facilitates hierarchic modeling.

**Description**

The Interface , which can be an entrance or an exit, is the place at which the MUs move from one Frame to another in your simulation model. You can position the Interface anywhere in a Frame . You can address these connections via their names.

- You always have to insert Interfaces into a sub-Frame , when it contains more than one material flow object. If a sub-Frame contains Interfaces , the materials always flow across these.

For an Interface , which you inserted into a Frame , Plant Simulation shows if the Interface is connected to another object with a Connector or not . Plant Simulation also recognizes if an Interface is an

Entrance or an Exit .

<!-- image -->

To open the list showing all externally connected objects, select Open External Connections List on the context menu or Tools &gt; External Connections in the dialog of the Interface .

<!-- image -->

<!-- image -->

To show a tooltip containing the externally connected objects, roll the mouse over the Interface in the Frame .

<!-- image -->

To select the objects connected with this Interface , select Show External Connected Objects on the context menu.

The Interface shows the number of the next selected exit on the tab Exit provided you already determined it, for example by calling the method succ for the successor object.

- If the sub-Frame only contains a single material flow object, you do not have to insert Interfaces in 2D and in 3D, but can connect the sub-Frame directly with its predecessor and its successor. Connections without Interfaces only work across a single lower hierarchy level, not across several nested hierarchy levels.

The tooltip shows the externally connected objects.

<!-- image -->

**Note**

If Interfaces are inserted into your simulation model, the simulation in 3D runs across these Interfaces .

Add the Object to the Simulation Model

To add the Interface to your simulation model, click MaterialFlow &gt; Interface on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Model Transitions Between Frames

Adapt the 3D Model to the 2D Model

#### Dialog Box of the Interface

Dialog Box of the Interface

Double-click the icon of the Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

- Select the object in the model and press the spacebar .

Tab Attributes

Tab Attributes

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

The tab Attributes provides the settings listed in the table of contents to the left.

**Type [Interface]**

###### Type [Interface]

An Interface object, which you insert into a Frame and connect with a Connector , shows its type here:.

An Entrance through which MUs enter the Frame or an Exit through which MUs exit the Frame .

SimTalk

IsEntry [SimTalk]

IsExit [SimTalk]

###### Maximum Number of External Connections [Interface]

Type in the maximum number of external connections the Interface may have.

Depending on the type, any number of Interfaces may have more than one predecessor or successor.

The default value -1 designates an unlimited number of external connections.

SimTalk

MaxConnections [SimTalk] - Interface

###### Side [drop-down list]

Side [drop-down list]

Select the side at which Plant Simulation places the Interface :

The Top , the Right , the Bottom , the Left of the Frame , or depending on the Angle .

Angle-dependent takes into account the angle between the objects when determining the starting point or the end point of the Connector .

<!-- image -->

SimTalk

Side [SimTalk]

###### Position in % [Interface]

Type in the position at which Plant Simulation shows an arriving or leaving Connector at the icon of the Frame .

<!-- image -->

You can type in a value between 0 and 100 %. Position 0 is either the top or the left-hand side at the icon of the Frame , position 100 the bottom or the right-hand side at the icon.

Plant Simulation uses the value you enter here, when you activate File &gt; Preferences &gt; Modeling &gt; Connect Objects Automatically . Connecting objects automatically only works, if the exit of FrameA and the entrance of FrameB are not more than three pixels apart.

SimTalk

Position [SimTalk] - Interface

See also

Connect objects automatically

**Tab Exit [Interface]**

##### Tab Exit [Interface]

Select to which of its successors the object moves the MU on the tab Exit .

**Note**

If Plant Simulation determines the n-th successor of an object, for example with print MyStation. succ(n) and if the n-th successor is an Interface , Plant Simulation does not return the Interface itself, but any successor of the Interface according to the Exit strategy of the Interface .

If you select a non-blocking exit strategy , Plant Simulation returns the next available successor according to the exit strategy or it returns VOID, when no successor can receive parts.

When the Interface has a single successor , Plant Simulation returns this successor, even if you selected a non-blocking exit strategy and if the successor is occupied or failed/paused.

The Interface shows the number of the next selected exit ( next Aimed Successor ) provided you already determined it, for example by calling the method succ for the successor object.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

See also Tab Exit [general description] Blocking [exit strategy]

Strategy [material flow objects]

**Tab User-defined**

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

Navigate Menu The commands are described under the Navigate Menu . View Menu View Menu The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] External Connections Forward Blocking List SimTalk updateDialog [SimTalk]

###### External Connections

Opens a table displaying the paths of the external connections in the Frame in which the Interface object is located.

<!-- image -->

The column Connector designates the Connector at the exit of the Frame .

The column Object designates the object name of the succeeding object.

Instead, you can also click the Interface with the right mouse button in the Frame and select Open External Connections List on the context menu.

<!-- image -->

**See also**

**Refresh [on View menu]**

Context menu &gt; Open External Connections List

Context menu &gt; Show External Connected Objects

**Tools Menu**

The commands are described under the Tools Menu .

**Help Menu**

The commands are described under the Help Menu .

##### Methods of the Interface

#### Methods of the Interface

The Interface provides the Methods of All Objects .

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

#### Read-Only Attributes of the Interface

\_Read-Only Attributes of the Interface

The Interface provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print .Models.Model.MyFrame.Interface.IsEntry
```

IsEntry [SimTalk]

Returns if the Interface designated by &lt;Path&gt; is of type Entrance (true) or not (false).

Remarks

The Interface has to be connected with a Connector .

Type

Read-only attribute

Syntax

&lt; Path &gt;.IsEntry → boolean

Return Value

The return value has the data type boolean .

Example

print .Models.Model.Frame.Interface.IsEntry

SimTalk

IsExit [SimTalk]

See also

Type [Interface]

##### IsExit [SimTalk]

IsExit [SimTalk]

Returns if the Interface designated by &lt;Path&gt; is of type Exit (true) or not (false).

Remarks

The Interface has to be connected with a Connector .

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsExit → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print .Models.Model.Frame.interface.IsExit
```

SimTalk

IsEntry [SimTalk]

See also

Type [Interface]

#### Attributes of the Interface

\_Attributes of the Interface

The Interface provides:

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
Interface1.Position := 53
print Interface1.Position
posit := MyStation.Cont.XPos
```

MaxConnections [SimTalk] - Interface

Sets the Maximum Number of External Connections of the Interface designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.MaxConnections:integer

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite number of connections.

Example

```simtalk
Interface1.MaxConnections := 2
```

See also

Maximum Number of External Connections [Interface]

##### Position [SimTalk] - Interface

Sets the Position in % of the Interface designated by &lt;Path&gt; at which an incoming or outgoing Connector is shown at the icon of the Frame .

Remarks

Plant Simulation uses the value you specify, when you activate File &gt; Preferences &gt; Modeling &gt; Connect Objects Automatically .

Connecting objects automatically only works, when the exit of FrameA and the entrance of FrameB are not more than three pixels apart.

Type

Attribute

Syntax

&lt; Path &gt;.Position:integer

Assignment Value

You can assign a value of data type integer .

Specify a value between 0 and 100 percent.

Position 0 is either the top or the left-hand side at the icon of the Frame .

Position 100 is the bottom or the right-hand side at the icon.

Example

```simtalk
interface.Position := 53
```

See also

Position in % [Interface]

Connect Objects Automatically [model settings]

##### Side [SimTalk]

Side [SimTalk]

Sets the Side of the Frame on which the Interface designated by &lt;Path&gt; is located.

Type

Attribute

Syntax

```simtalk
< Path >.Side:string
```

Assignment Value

You can assign a value of data type string .

You can specify "Top" , "Right" , "Bottom" , "Left" , or "Angle-dependent" .

"Angle-dependent" takes the angle between the objects into account when determining the starting point or the end point of the Connector .

**Example**

```simtalk
interface.Side := "right"
```

See also

Side [drop-down list]

#### Source

