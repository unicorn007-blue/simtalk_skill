### AttributeExplorer

#### AttributeExplorer [object]

Use the AttributeExplorer for managing the attributes defining the settings of the individual stations in your simulation model at a single, central location.

**Icon**

<!-- image -->

**Description**

Instead of opening the dialog of each and every material flow object in your model and typing the attribute values into the text boxes, you can define which attributes of which object the AttributeExplorer gets and shows in a list window.

To do so, click Show Explorer . Then type in the different values, for the capacities, the times, etc., which Plant Simulation writes back to the objects and uses in the model. You can Export this settings table as a tab-delimited text file and Import this file into the AttributeExplorer of another simulation model, thus using identical settings in several of your simulation models.

You can also show the attribute table of an AttributeExplorer in an HtmlReport , compare Display an AttributeExplorer .

To show a tooltip with information about the AttributeExplorer , hover with the mouse over it.

To change the length of the graphic and the anchor points of the AttributeExplorer , click Show

<!-- image -->

Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the AttributeExplorer to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; AttributeExplorer on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Set Parameters with the AttributeExplorer

#### Dialog Box of the AttributeExplorer

Dialog Box of the AttributeExplorer

Double-click the icon of the AttributeExplorer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Show Explorer

**Show Explorer**

##### Show Explorer

To show the list window in which the AttributeExplorer displays the objects and the attributes you defined on the Tab Objects and the Tab Attributes , click this.

<!-- image -->

<!-- image -->

To close the list window in which the AttributeExplorer displays the objects and attributes you defined, click the X in the title bar of the window.

<!-- image -->

The results table is sorted according to Path , Name , or Label . The AttributeExplorer first shows the data of the objects you specified and then the data that is defined by the query.

Instead, you can also right-click the AttributeExplorer in the Frame and select Show on the context menu.

You can manipulate the contents of the list with the commands on the Context Menu of Embedded Lists .

SimTalk

IsShown [SimTalk] - AttributeExplorer

AttributeTable [SimTalk]

ExplorerTable [SimTalk]

See also

Tab Objects [AttributeExplorer]

**Tab Attributes [AttributeExplorer]**

Tab Data

Tab Data

Select the settings below for the mode of the attributes in the AttributeExplorer on the tab Data .

<!-- image -->

- Watch
- Edit
- Read Only

You can also select to:

- Show Objects With their Path , their Name , or their Label .
- Show Attributes With their Name , or their Alias .

In addition, you can type in a Comment and select to Show a Comment .

<!-- image -->

##### Tab Data

You can manipulate the contents of the list with the commands on the Context Menu of Embedded Lists . SimTalk

AttributeRepresentation [SimTalk]

Mode [SimTalk] - AttributeExplorer

ObjectRepresentation [SimTalk]

###### Watch [AttributeExplorer]

To display the values of the watchable attributes of any of the stations which you typed in on the tab Attributes , click Watch .

<!-- image -->

Plant Simulation displays the background of the cells in different colors to show if the attribute is watchable or not.

| Color   | Description                                  |
|---------|----------------------------------------------|
| blue    | The attribute is not watchable.              |
| gray    | The attribute is watchable.                  |
| red     | You entered an invalid path to an attribute. |

SimTalk

Mode [SimTalk] - AttributeExplorer

See also

Watchable Values

Tab Attributes [AttributeExplorer]

**Edit [AttributeExplorer]**

###### Edit [AttributeExplorer]

To allow editing the values of the attributes of any one of the stations you specified on the tab Attributes , click Edit .

<!-- image -->

Plant Simulation writes the values you modified back to the dialogs of the objects, when you click Apply/OK .

SimTalk

Mode [SimTalk] - AttributeExplorer

See also

Tab Attributes [AttributeExplorer]

###### Read Only [AttributeExplorer]

<!-- image -->

To activate read-only mode for the values of the attributes of the objects which you typed in on the tab Objects and the tab Attributes , click Read Only .

Note

Before you can type in data, click the Inheritance check box so that it looks like this .

Then, you can only view, but not edit the values. Plant Simulation updates the values when you click Apply .

SimTalk

Mode [SimTalk] - AttributeExplorer

See also

Tab Objects [AttributeExplorer]

Tab Attributes [AttributeExplorer]

**Show Objects With**

###### Show Objects With

Select how the AttributeExplorer shows the objects which you type in on the tab Objects .

<!-- image -->

###### Show Attributes With

Select how the AttributeExplorer shows the attributes, which you type in on the tab Attributes .

<!-- image -->

**With their:**

- Alias , which is a description you entered, in addition to the built-in name of the attribute.
- Name only

SimTalk

AttributeRepresentation [SimTalk]

See also

Tab Attributes [AttributeExplorer]

###### Show Comment [AttributeExplorer]

Show Comment [AttributeExplorer]

To show any explanations you typed into the text box Comment , select this check box.

<!-- image -->

To not show the comment, clear the check box.

SimTalk

ShowComment [SimTalk] - AttributeExplorer

Comment [SimTalk] - AttributeExplorer

###### Comment [AttributeExplorer]

Type in an explanation for the objects and values you defined on the tab Objects and on the tab Attributes .

Select Show Comment to display it above the list field.

Note

Before you can type in your comment, click the Inheritance check box so that it looks like this .

<!-- image -->

SimTalk

Comment [SimTalk] - AttributeExplorer

ShowComment [SimTalk] - AttributeExplorer

See also

Tab Objects [AttributeExplorer]

Tab Attributes [AttributeExplorer]

##### Tab Objects [AttributeExplorer]

Tab Objects [AttributeExplorer]

View or edit the attributes of an object on the tab Objects .

Before you type in data, click the Inheritance check box so that it looks like this .

- To view or to edit the attributes of an object, drag that object from the Frame window over the tab Objects in the open dialog of the AttributeExplorer and drop it there. Plant Simulation inserts the absolute path to and the name of the object into the selected cell of the list on the tab.

You can also select and then drag-and-drop multiple objects at the same time!

<!-- image -->

Plant Simulation adds the object in the order in which you selected them in the Frame .

- To just enter the name of the object, drag that object from the Frame window over the icon of the AttributeExplorer and drop it there.

<!-- image -->

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

SimTalk

**ObjectTable [SimTalk]**

See also

Context Menu of Embedded Lists

**Tab Attributes [AttributeExplorer]**

##### Tab Attributes [AttributeExplorer]

To type the names of the attributes whose values you want to edit or view, into the cells in the column Name , click Show Attributes .

**Note**

Before you can type in data, click the Inheritance check box so that it looks like this .

**In the dialog Attribute Viewer :**

- Click and select the Object , whose attributes you want to show, in the dialog Select Object .
- Select from the drop-down list if you want to view the built-in attributes of this object, or its userdefined attributes which you defined.
- Depending on what you selected above, the AttributeExplorer displays the built-in attributes or the user-defined attributes here.
- Select one, or several contiguous attributes ( Shift+click ), and click this to add them to the attributes to be shown.
- The AttributeExplorer adds the attributes, which you selected in the left-hand list box, to the attributes, which it is going to show.
- To add a sub-attribute of an attribute, type in the attribute, and the sub-attribute into the cell. You might, for example, type in imp.priority .

Click OK to add these attributes to the list that the AttributeExplorer displays on the tab Attributes .

<!-- image -->

If the predefined Name of an attribute is not meaningful enough for your purposes, type in a descriptive term for that attribute that suits your modeling situation into the corresponding cell in the column Alias .

**Note**

Importing a file only works correctly if the file contains the Name of the attribute. It does not work correctly if the file only contains the Alias of the attribute.

If you want an attribute to be read only, click into the cell Read Only . Then, you can just view, but not edit that value in the list that the button Show Explorer opens.

Plant Simulation displays the background of the cells in different colors to show if the attribute is watchable or not.

<!-- image -->

| Color   | Description                                        |
|---------|----------------------------------------------------|
| blue    | The attribute is not watchable.                    |
| white   | The attribute is watchable.                        |
| gray    | You entered a wrong name for a built-in attribute. |

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

SimTalk

ObjectTable [SimTalk]

AttributeTable [SimTalk]

See also

Context Menu of Embedded Lists

Tab Query

Tab Query

Define a query that finds objects according to the criteria you type into the cells of the list on the tab Query .

Note

Before you can type in data, click the Inheritance check box so that it looks like this .

Select the number of opening Parentheses , type in an Attribute , select a Condition , a Value , select the number of closing Parentheses , select an Operator , and type in a Comment . Select the Frame that the AttributeExplorer queries.

Select the check box Include Subframes to also query any Frames which located within the selected Frame .

Select Include MUs to also include the parts ( MUs ) in your model in your query.

<!-- image -->

Spelled out in code our query reads like this:

Name Expr Station.* and ((XPos &gt; 100 and YPos = 200) or ExitStrategy = Cyclic)

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

SimTalk

QueryTable [SimTalk]

See also

Context Menu of Embedded Lists

**Parentheses [opening]**

###### Parentheses [opening]

Select the number of opening Parentheses of the query.

<!-- image -->

###### Attribute [AttributeExplorer]

Type in the name of the Attribute you want to query.

You can type in any of the attributes of the object which the window Show Attributes and Methods displays.

<!-- image -->

###### Condition [AttributeExplorer]

Click in the cell once with the left mouse button and select a Condition from the drop-down list.

- &lt; (less than)
- &lt;= (less than or equal to)
- &gt; (greater than)
- &gt;= (greater than or equal to)
- = (equal to), compares attributes of data type real , length , weight , speed , and time for the exact value
- ~= (equal to, case-insensitive) compares if strings are equal not considering lower and upper-casing, or compares if the values of attributes are about equal
- /= (not equal to)
- Expr , which is a regular expression, compare regex\_search . You might, for example, type in ^Inf , which finds any word beginning with Inf .
- Exists , checks if the object has the designated attribute or not.

<!-- image -->

Then, type the value into the corresponding cell in the column Value .

###### Value [AttributeExplorer]

Type in the Value of the attribute which the AttributeExplorer is to find.

<!-- image -->

**Parentheses [closing]**

###### Parentheses [closing]

Select the number of closing Parentheses of the query.

<!-- image -->

###### Operator [AttributeExplorer]

Click in the cell once with the left mouse button and select a boolean Operator from the drop-down list.

This operator connects the boolean values of the active row with the next row. The boolean values result from evaluating the logical expression that you defined in a row of the query table.

- and
- or

<!-- image -->

**Comment [query]**

###### Comment [query]

Type in any Comment explaining what you intended with this query.

<!-- image -->

###### Frame [find attribute in]

Click the ellipsis button and select the Frame in the dialog Select Object , in which you want to start finding the attributes of the objects which you defined on the tab Objects .

<!-- image -->

Select Include Subframes to also include any Frames located within the Frame you selected.

SimTalk

StartNode [SimTalk]

See also

Select Object

Tab Objects [AttributeExplorer]

**Include Subframes [AttributeExplorer]**

###### Include Subframes [AttributeExplorer]

To also include the Frames which are inserted in the Frame , which you selected under Frame in the text box above, into your query, select this check box.

<!-- image -->

SimTalk

IncludeSubframes [SimTalk]

See also

Frame [find attribute in]

<!-- image -->

###### Include MUs [AttributeExplorer]

To also include the MUs located within the Frame , which you selected under Frame in the text box above, into your query, select this check box.

<!-- image -->

SimTalk

IncludeMUs [SimTalk]

See also

Frame [find attribute in]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] SimTalk updateDialog [SimTalk] See also View Menu [general description]

Tools Menu Tools Menu The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D Export Import

###### Export [AttributeExplorer]

To export the contents of the tab Objects and of the tab Attributes to a tab-delimited text file, select this command.

You can then import this file into another list, thus using identical settings in several of your simulation models.

See also

Tab Objects [AttributeExplorer]

Tab Attributes [AttributeExplorer]

###### Import [AttributeExplorer]

Import [AttributeExplorer]

To import a tab-delimited text file containing the data of the tab Objects and of the tab Attributes , select this command.

You can thus use identical settings in several of your simulation models.

See also

Tab Objects [AttributeExplorer]

Tab Attributes [AttributeExplorer]

**Help Menu**

The commands are described under the Help Menu .

#### Methods of the AttributeExplorer

Methods of the AttributeExplorer

The AttributeExplorer provides the Methods of All Objects .

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

##### Read-Only Attributes of the AttributeExplorer

Read-Only Attributes of the AttributeExplorer

The AttributeExplorer provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyAttributeExplorer.UUID
```

#### Attributes of the AttributeExplorer

\_Attributes of the AttributeExplorer

The AttributeExplorer provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyAttributeExplorer.Comment := "Processing time changes globally"
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyAttributeExplorer.AttributeRepresentation
posit := Station.Cont.XPos
```

##### AttributeRepresentation [SimTalk]

Shows the attributes with their Name or with their Alias in the Explorer window of AttributeExplorer designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.AttributeRepresentation:string

Assignment Value

You can assign a value of data type string .

You can specify "Name" or "Alias" .

Example

MyAttributeExplorer.AttributeRepresentation := "Alias"

See also

Show Attributes With

##### AttributeTable [SimTalk]

AttributeTable [SimTalk]

Sets the attribute table of the AttributeExplorer designated by &lt;Path&gt; for object attributes.

Remarks

This table contains the attributes you enter on the tab Attributes .

Type

Attribute

Syntax

&lt; Path &gt;.AttributeTable:table

Assignment Value

You can assign a value of data type table .

Example

MyAttributeExplorer.AttributeTable := tableAttributes

See also

Tab Attributes [AttributeExplorer]

##### Comment [SimTalk] - AttributeExplorer

Sets the comment, which the AttributeExplorer designated by &lt;Path&gt; displays above the list box.

Type

Attribute

Syntax

&lt; Path &gt;.Comment:string

Assignment Value

You can assign a value of data type string .

Example

MyAttributeExplorer.Comment := "Processing time changes globally"

See also

Comment [AttributeExplorer]

Show Comment [AttributeExplorer]

##### ExplorerTable [SimTalk]

ExplorerTable [SimTalk]

Sets the table which the AttributeExplorer designated by &lt;Path&gt; shows.

Remarks

The AttributeExplorer enters the attributes, which you type into row 0 of the table into the Attribute Table .

- The AttributeExplorer enters the objects, which you type into column 0 of the table into the Object Table .
- The AttributeExplorer enters the attributes, which you type into any of the columns of the table into the Explorer table.

Type

Attribute

Syntax

&lt; Path &gt;.ExplorerTable:table

Assignment Value

You can assign a value of data type table .

Example

MyAttributeExplorer.ExplorerTable := MyExplorerTable

SimTalk

AttributeTable [SimTalk]

ObjectTable [SimTalk]

See also

Show Explorer

##### IncludeMUs [SimTalk]

Makes the AttributeExplorer designated by &lt;Path&gt; also search MUs located within the active Frame ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.IncludeMUs:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyAttributeExplorer.IncludeMUs := true

See also

Include MUs [AttributeExplorer]

Frame [find attribute in]

IncludeSubframes [SimTalk]

Makes the AttributeExplorer designated by &lt;Path&gt; also search Frames located within the active Frame ( true ), or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.IncludeSubframes:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyAttributeExplorer.IncludeSubframes := true

See also

Include Subframes [AttributeExplorer]

Frame [find attribute in]

IsShown [SimTalk] - AttributeExplorer

Shows ( true ) or hides ( false ) the attribute table of the AttributeExplorer designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.IsShown:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

MyAttributeExplorer.IsShown := false

See also

ExplorerTable [SimTalk]

Show Explorer

##### Mode [SimTalk] - AttributeExplorer

Mode [SimTalk] - AttributeExplorer

Sets the mode that the AttributeExplorer designated by &lt;Path&gt; uses.

Type

Attribute

Syntax

&lt; Path &gt;.Mode:string

Assignment Value

You can assign a value of data type string -

You can specify "Watch" , "Edit" , or "Read" .

Example

MyAttributeExplorer.Mode := "Edit"

See also

Watch [AttributeExplorer]

Edit [AttributeExplorer]

Read Only [AttributeExplorer]

##### ObjectRepresentation [SimTalk]

Shows the objects of the AttributeExplorer designated by &lt;Path&gt; with their entire Path , their Name , or their Label in the Explorer window .

Type

Attribute

Syntax

&lt; Path &gt;.ObjectRepresentation:string

Assignment Value

You can assign a value of data type string .

You can specify "Path" , "Name" , or "Label" .

Example

```simtalk
MyAttributeExplorer.ObjectRepresentation := "Label"
```

See also

Show Objects With

##### ObjectTable [SimTalk]

ObjectTable [SimTalk]

Sets the table containing the Plant Simulation objects of the AttributeExplorer designated by &lt;Path&gt;.

Remarks

The objects table contains the objects which you type in on the tab Objects .

Type

Attribute

Syntax

&lt; Path &gt;.ObjectTable:table

Assignment Value

You can assign a value of data type table .

Example

MyAttributeExplorer.ObjectTable := tableObjects

See also

Tab Objects [AttributeExplorer]

QueryTable [SimTalk]

Sets the query table of the AttributeExplorer designated by &lt;Path&gt;.

Remarks

The query table contains the settings which you enter on the tab Query .

Type

Attribute

Syntax

&lt; Path &gt;.QueryTable:table

Assignment Value

You can assign a value of data type table .

Example

MyAttributeExplorer.QueryTable := myQueryTable

See also

Tab Query ShowComment [SimTalk] - AttributeExplorer Shows the text box for the specifying a comment above the list field of the AttributeExplorer designated by &lt;Path&gt; ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowComment:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyAttributeExplorer.ShowComment := true
```

See also

Show Comment [AttributeExplorer]

Comment [AttributeExplorer]

##### StartNode [SimTalk]

Sets the Frame in which the AttributeExplorer designated by &lt;Path&gt; starts finding the attributes of the objects.

Type

Attribute

Syntax

&lt; Path &gt;.StartNode:object

Assignment Value

You can assign a value of data type object .

Example

MyAttributeExplorer.StartNode := MyPlant.MyFrame

See also

Frame [find attribute in]

#### FileLink

