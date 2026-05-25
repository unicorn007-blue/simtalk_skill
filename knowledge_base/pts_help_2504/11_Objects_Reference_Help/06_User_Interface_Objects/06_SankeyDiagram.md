### SankeyDiagram

#### SankeyDiagram [object]

Use the SankeyDiagram for visualizing the Sankey flows of parts as well as Sankey flows of Workers , who walk freely within the area or walk on FootPaths .

Icon

<!-- image -->

Description

**Note**

In the current version the SankeyDiagram does not record the AGV that is driving freely within the area.

To show a tooltip with information about the SankeyDiagram , hover with the mouse over it.

To change the length of the graphic and the anchor points of the SankeyDiagram , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the SankeyDiagram to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; SankeyDiagram on the Home ribbon tab.

See also

Show Part Flows in a SankeyDiagram

Display a SankeyDiagram in the HtmlReport

#### Dialog Box of the SankeyDiagram

Dialog Box of the SankeyDiagram

Double-click the icon of the SankeyDiagram to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

##### Dialog Box of the SankeyDiagram

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Show Diagram

Collect Data [check box] - SankeyDiagram

##### Show Diagram

To show the Sankey flows in the Frame , click Show Diagram .

<!-- image -->

To hide the Sankey flows, click Hide Diagram .

<!-- image -->

Instead, you can also select the context menu command Show/Hide .

Click Update to update the displayed Sankey flows with the current values

<!-- image -->

**SimTalk**

IsShown [SimTalk] - SankeyDiagram

See also

Update [in Frame]

##### Collect Data [check box] - SankeyDiagram

Collect Data [check box] - SankeyDiagram

To make the SankeyDiagram collect data, select this check box.

To deactivate the collection of data, clear the check box.

SimTalk

CollectData [SimTalk] - SankeyDiagram

Tab Attributes

Tab Attributes

On the tab Attributes the SankeyDiagram provides the settings listed in the table of contents to the left.

###### Maximum Width [SankeyDiagram]

Type in the maximum width of the Sankey flows which visualize the paths of parts and Workers in the Frame .

<!-- image -->

**Color [SankeyDiagram]**

###### Color [SankeyDiagram]

Select the color of the Sankey flows which visualize the paths of the parts and Workers in the Frame .

<!-- image -->

SimTalk

Color [SimTalk] - SankeyDiagram

###### 2D Graphics Layer

<!-- image -->

Type in the graphics layer on which Plant Simulation shows the graphics of the Sankey flows in 2D.

Note

The SankeyDiagram only shows the text box 2D Graphics Layer for a 2D Only or for a 2D and 3D model.

The default value of -500 usually ensures that the Sankey flows are always displayed in front of all objects and vector graphics in the Frame which contains your model. If you use your own vector graphics, make sure that the negative value is sufficiently large and that it does not overlap with user-defined values.

If you insert several SankeyDiagrams into the same Frame , the default value will automatically be incremented.

SimTalk

Layer [SimTalk]

Tab Objects

Objects

On the tab Objects you can assign Objects to the SankeyDiagram for which it is to display Sankey flows .

**Objects [SankeyDiagram]**

###### Objects [SankeyDiagram]

To show the Sankey flows for class objects , drag parts classes ( Part , Container , Transporter ), Worker classes , or WorkerPool classes from the Class Library over the respective cell in the list and drop it there.

<!-- image -->

To show Sankey flows of individual parts ( Part , Container , Transporter ), Worker instances , or WorkerPool instances , type their names into the respective cells of the list, for example .MUs.Part:3 .

**Note**

If inheritance of the objects on the tab is activated, the SankeyDiagram replaces the default object class with the class which you set with drag-and-drop.

This does, for example, make switching the SankeyDiagram from parts to Workers easy.

**SimTalk**

Objects [SimTalk] - SankeyDiagram

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The commands are described under the View Menu .

SimTalk

updateDialog [SimTalk]

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

**Methods of the SankeyDiagram**

#### \_Methods of the SankeyDiagram

The SankeyDiagram provides the methods listed in the table of contents for accessing it.

The SankeyDiagram provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

##### getPartFlowData [SimTalk]

Writes the flows that the SankeyDiagram designated by &lt;Path&gt; collected during the simulation to the designated DataTable .

Remarks

The SankeyDiagram collects the number of the parts which move between point-oriented objects or along length-oriented objects. It does not consider the direction nor the sequence of the movements of the parts, and they cannot be traced back from the returned data.

Type

Method

Syntax

&lt; Path &gt;.getPartFlowData(DataTable:table)

Parameter

The parameter DataTable of data type table designates the table into which Plant Simulation writes the data of the flows.

Example

MySankeyDiagram.getPartFlowData(MyDataTable)

update [SimTalk] - SankeyDiagram

update [SimTalk] - SankeyDiagram

Refreshes the displayed SankeyDiagram designated by &lt;Path&gt; with the current values.

Type

Method

Syntax

&lt; Path &gt;.update

Example

MySankeyDiagram.update

See also

Update [in Frame]

#### Read-Only Attributes of the SankeyDiagram

Read-Only Attributes of the SankeyDiagram

The SankeyDiagram provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of the SankeyDiagram

\_Attributes of the SankeyDiagram

The SankeyDiagram provides:

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
MySankeyDiagram.IsShown := true
print MySankeyDiagram.IsShown
posit := Station.Cont.XPos
```

CollectData [SimTalk] - SankeyDiagram

Sets if the SankeyDiagram designated by &lt;Path&gt; collects data ( true ) or does not collect data ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.CollectData:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MySankeyDiagram.CollectData := true

See also

Collect Data [check box] - SankeyDiagram Color [SimTalk] - SankeyDiagram Sets the color which Plant Simulation uses for displaying the Sankey flows of the parts and Workers of the SankeyDiagram designated by &lt;Path&gt; in the Frame .

Remarks

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

&lt; Path &gt;.Color:integer

Assignment Value

You can assign a value of data type integer .

Example

MySankeyDiagram.Color := makeRGBValue(255,0,0)

SimTalk

makeRGBValue [SimTalk]

See also

Color [SankeyDiagram]

IsShown [SimTalk] - SankeyDiagram

Activates ( true ) or deactivates ( false ) the display of the SankeyDiagram designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.IsShown:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MySankeyDiagram.IsShown := false

See also

Show Diagram

**Layer [SimTalk]**

##### Layer [SimTalk]

Sets the graphics layer on which Plant Simulation shows the graphics of the Sankey flows of the SankeyDiagram designated by &lt;Path&gt; in 2D.

Remarks

**Note**

The attribute is only available for a 2D Only or for a 2D and 3D model.

The default value of -500 usually ensures that the Sankey flows are always displayed in front of all objects and vector graphics in the Frame which contains your model. If you use your own vector graphics, make sure that the negative value is sufficiently great and that it does not overlap with user-defined values.

If you insert several SankeyDiagrams into the same Frame , the default value will automatically incremented.

Type

Attribute

Syntax

```simtalk
< Path >.Layer:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MySankeyDiagram.Layer := 200
```

See also

2D Graphics Layer

##### MaximumWidth [SimTalk]

Sets the maximum width with which Plant Simulation visualizes the Sankey flows of the parts and Workers of the SankeyDiagram designated by &lt;Path&gt; in the Frame .

Type

Attribute

Syntax

&lt; Path &gt;.MaximumWidth:length

Assignment Value

You can assign a value of data type length .

Example

MySankeyDiagram.MaximumWidth := 1.0 -- meters

See also

Maximum Width [SankeyDiagram]

Objects [SimTalk] - SankeyDiagram

Objects [SimTalk] - SankeyDiagram

Sets the objects, i.e., the Parts or Workers whose Sankey flows which the SankeyDiagram designated by &lt;Path&gt; visualizes in the Frame .

Type

Attribute

Syntax

< Path >.Objects:array

Assignment Value

You can assign a value of data type array .

**Example**

```simtalk
MySankeyDiagram.Objects := [.Resources.Worker]         // all Workers of this class
MySankeyDiagram.Objects := [.Resources.WorkerPool]     // all WorkerPool classes
MySankeyDiagram.Objects := [.Models.Model.WorkerPool]  // all Workers of the WorkerPool in the Frame named Frame
MySankeyDiagram.Objects := [.Resources.Worker:1]       // the Worker with the number 1
```

See also

Objects , tab

#### CostAnalyzer

