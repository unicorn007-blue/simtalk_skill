### TimeSequence

Use the TimeSequence for recording the course that values take over time, such as shift plans, machine maintenance schedules, or buffer occupancies.

Icon

<!-- image -->

**Description**

The TimeSequence is a table with two columns.

- In Watch mode Plant Simulation enters the time-value-pairs each time when an watchable value changes.
- In Sample mode Plant Simulation enters the time-value-pairs periodically, during certain time intervals, no matter if the value actually changes or not.

You can use the TimeSequence several times and sort the values to see if the values are always the same over time or if the change randomly.

Each entry in the TimeSequence consists of a point in time in the first column and the value associated with that point in time in the second column. Plant Simulation sorts the contents in ascending order. The contents can change dynamically during the simulation run. When you delete a pair of entries contained in a row, Plant Simulation moves the following rows up, so that no blank rows remain.

**Note**

Although the TimeSequence has two columns it behaves like a list with one column, i.e., it does not allow blank cells or pairs of blank cells.

For the column Value , you can select the data types Boolean , Integer , Real , String , Object , Time , Money , Length , Weight , Speed , Date , and DateTime .

The data type of the column Point in Time depends on the setting you selected under Start Values &gt; Time Reference and may take the data types Time or DateTime .

To show a tooltip with information about the TimeSequence , hover with the mouse over it.

Add the Object to the Simulation Model

To change the length of the graphic and the anchor points of the TimeSequence , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

To add the TimeSequence to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; TimeSequence on the Home ribbon tab.

See also

Properties of Lists and Tables

#### Dialog Box of the TimeSequence

Dialog Box of the TimeSequence

Double-click the icon of the TimeSequence to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

**Edit Animation Properties**

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### File Menu [TimeSequence]

File Menu [TimeSequence] The menu commands are described under the List Ribbon Tab . See also Import File Export to File [lists] Export Object File Text File Format Print List Print Setup Close Model

##### Edit Menu [TimeSequence]

The menu commands are described under the Home Ribbon Tab and the List Ribbon Tab .

See also

Cut [Home ribbon]

Copy [Home ribbon]

Paste Contents of the Clipboard [Home ribbon]

Delete [Home ribbon]

Select All [Home ribbon]

Insert Row [lists]

Find [lists]

Replace [lists]

The Context Menu of the Contents of List Objects also provides the most important commands for editing the time sequence.

##### Format Menu [TimeSequence]

Format Menu [TimeSequence] The menu commands are described under the List Ribbon Tab . See also Activate Column Index Activate Row Index Inherit Format [button] Inherit Contents [lists] Inherit Comment [button]

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The commands are described under the List Ribbon Tab . See also Recompute Formulas Show Comment [lists] Show Data Type [lists] Highlight Empty Cells

**Go To Cell**

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D

##### Help Menu

Help Menu

The commands are described under the Help Menu .

Tab Contents

Tab Contents [TimeSequence]

On the tab Contents the TimeSequence shows a table with two columns in which you specify a point in time ( time ) and the value ( string ) that trigger an action.

The tab Contents provides the settings listed in the table of contents to the left.

###### Sort [TimeSequence]

To sort the contents of the cells in the time sequence in ascending order, click this button.

###### Set Value [TimeSequence]

Set Value [TimeSequence]

To fill blank cells in column 2 with the Default value you set, click this button.

SimTalk

DefaultValue [SimTalk]

See also

Default Value [TimeSequence]

Tab Start Values

Tab Start Values

Select the settings which determine how Plant Simulation interprets the time and the value column on the tab Start Values .

You can, for example, easily offset the data of a time sequence here.

<!-- image -->

The tab Start Values provides the settings listed in the table of contents to the left.

###### Time Reference [TimeSequence]

Select if the time values are Relative or Absolute values.

Depending on the setting you select, the data type of column 1 is time or dateTime . Plant Simulation automatically converts values you specify.

- For the Absolute Time Reference type a point in time on a certain date ( dateTime ) into the text box Reference Date .
- For the Relative Time Reference type a duration ( time ) into the text box Reference Time .

<!-- image -->

<!-- image -->

SimTalk

Absolute [SimTalk] - TimeSequence

See also

Reference Time/Reference Date [TimeSequence]

###### Reference Time/Reference Date [TimeSequence]

For Time Reference &gt; Relative you define a Reference Time . For Time Reference &gt; Absolute you define a Reference Date .

Plant Simulation adds this value to the time column of the TimeSequence to offset the data you set there. By changing the Reference Time/Date , you can shift the values in time without re-entering the data.

<!-- image -->

###### Default Value [TimeSequence]

Type in the Default Value of the time sequence.

<!-- image -->

The default value is especially important for a TimeSequence that defines the evolution of the value of a Trigger object because the Trigger takes the default value outside of its active interval.

In addition, Plant Simulation uses the default value to fill blank cells in column 2 of the TimeSequence when you click Set Value on the tab Contents .

SimTalk

DefaultValue [SimTalk]

Tab Record

Tab Record

Select the settings for the pattern of a value to be recorded while the simulation run progresses on the tab Record .

The tab Record provides the setting listed in the table of contents to the left.

**Value [TimeSequence]**

###### Value [TimeSequence]

Type in a relative or an absolute path to the value that the TimeSequence is to record.

<!-- image -->

When you specify an invalid path, the TimeSequence does not record any data. When you select Watch mode, the path must reference a watchable value.

To check which attributes of an object are watchable , select the object and press F8 . Watchable attributes are marked with an asterisk ( * ) in the column Watchable in the window Show Attributes and Methods .

<!-- image -->

**Example**

I.building2.entrance.NumMU frame.variable ResWorking

**SimTalk**

Path [SimTalk] - TimeSequence

###### Mode [drop-down list] - TimeSequence

Select the mode with which the TimeSequence adds new time-value pairs to the columns of the table: Watch or Sample .

<!-- image -->

- Watch adds a new value each time when a watchable value changes.

The column Watchable in the window Show Attributes and Methods shows if an attribute is watchable or not.

- Sample adds a new value periodically during the Interval that you specify, no matter if the value actually changes or not.

**SimTalk**

Sample [SimTalk]

###### Interval [TimeSequence]

<!-- image -->

Interval [TimeSequence]

Type in the time that elapses between the points in time at which the TimeSequence records data.

This setting applies for Sample Mode .

SimTalk

SmpPeriod [SimTalk] - TimeSequence

###### Active [check box] - TimeSequence

To record the progression of the values of the TimeSequence , select this check box. To not record any values, clear the check box.

<!-- image -->

Instead, you can also right-click the TimeSequence object in the Frame and select Activate on the context menu. To deactivate it, select Deactivate on the context menu.

SimTalk

Active [SimTalk] - TimeSequence

#### Methods of the TimeSequence

Methods for Columns of the TimeSequence

The TimeSequence provides:

- \_Methods for Columns
- \_Methods for Rows
- \_Methods for Accessing the TimeSequence
- The shared Methods of Lists and Tables .
- The shared Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- formula-not-decoded -->

- ◦ The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

If a parameter has a default value, the signature shows the default value after the parameter

If the method has a return value, the signature shows its data type after the arrow -&gt;.

- We use these abbreviations for the signature:

| Argument of data type   | Data type      | Range of values            |
|-------------------------|----------------|----------------------------|
| integer                 | integer        | integer greater than zero  |
| any                     | all data types | depending on the data type |
| listrange               | -              | a range                    |

| Argument of data type   | Data type   | Range of values      |
|-------------------------|-------------|----------------------|
| direction               | string      | "up", "down", " "    |
| attributes              | string      | name of an attribute |

**Methods for Columns**

##### \_Methods for Columns

The TimeSequence provides the methods listed in the table of contents to the left for the column format.

You can also select these settings under Format &gt; Column . In methods, the first parameter always designates the column, either the column index, the column range or the column number.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

getAlignmentColumn [SimTalk] - TimeSequence

Returns the alignment of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAlignmentColumn(Column:any) → string
```

Parameter

The parameter Column of data type any designates the column whose alignment you want to get.

Return Value

The return value has the data type string .

Example

```simtalk
str := timeSequence1.getAlignmentColumn(1)
```

SimTalk

isAlignmentColumn [SimTalk] - TimeSequence

setAlignmentColumn [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

getBackgroundColorColumn [SimTalk] - TimeSequence

Returns the background color of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getBackgroundColorColumn(Column:any) → integer

Parameter

The parameter Column of data type any designates the column whose background color you want to get.

Return Value

The return value has the data type integer .

Example

print timeSequence1.getBackgroundColorColumn(4)

SimTalk

setBackgroundColorColumn [SimTalk] - TimeSequence

See also

Background Color [cells]

getColumnWidth [SimTalk] - TimeSequence

Returns the width of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getColumnWidth(Column:any) → integer

Parameter

The parameter Column of data type any designates the column.

Return Value

The return value has the data type integer .

Example

print timeSequence1.getColumnWidth(1)

SimTalk

setColumnWidth [SimTalk] - TimeSequence

See also

Column Width [text box]

getEditorRightsColumn [SimTalk] - TimeSequence

Returns the editor rights of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getEditorRightsColumn(Column:any) → boolean

Parameter

The parameter Column of data type any designates the column whose editor rights you want to get.

Return Value

The return value has the data type boolean .

true for read-only access.

false for read and write access.

Example

```simtalk
print timeSequence1.getEditorRightsColumn(1)
```

SimTalk

setEditorRightsColumn [SimTalk] - TimeSequence

See also

Editor [check box]

Information Flow [check box]

getFontColorColumn [SimTalk] - TimeSequence

Returns the font color of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getFontColorColumn(Column:any) → integer

Parameter

The parameter Column of data type any designates the column whose font color you want to get.

Return Value

The return value has the data type integer .

Example

print timeSequence1.getFontColorColumn(3)

SimTalk

setFontColorColumn [SimTalk] - TimeSequence

See also

Font Color [cells]

getFontSizeColumn [SimTalk] - TimeSequence

Returns the font size of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFontSizeColumn(Column:any) → integer
```

Parameter

The parameter Column of data type any designates the column whose font size you want to get.

Return Value

The return value has the data type integer .

1 stands for Small , 2 for Medium , 3 for Large , and 4 for Extra Large .

Example

```simtalk
print timeSequence1.getFontSizeColumn(2)
```

SimTalk

setFontSizeColumn [SimTalk] - TimeSequence

See also

Font Size [drop-down list] - cells, columns getFormatString [SimTalk] - TimeSequence Returns the format string of the column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFormatString(Column:any) → string
```

Parameter

The parameter Column of data type any designates the column whose format string you want to get.

Return Value

The return value has the data type string .

Example

```simtalk
timeSequence1.getFormatString("paint")
print timeSequence1.getFormatString(1)
```

SimTalk

setFormatString [SimTalk] - TimeSequence

See also

Format String [text box]

getVisibility [SimTalk] - TimeSequence

Returns if a column of the TimeSequence designated by &lt;Path&gt; is visible ( true ) or hidden ( false ).

Type

Method

Syntax

```simtalk
< Path >.getVisibility(Column:any) → boolean
```

Parameter

The parameter Column of data type any designates the column whose visibility you want to get.

Return Value

The return value has the data type boolean .

Example

print timeSequence1.getVisibility(4)

SimTalk

setVisibility [SimTalk] - TimeSequence

See also

Work with Data in the DataTable .

isAlignmentColumn [SimTalk] - TimeSequence

Returns if the alignment of the specified column of the TimeSequence designated by &lt;Path&gt; matches the designated value (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >.isAlignmentColumn(Column:any, Alignment:string) → boolean
```

**Parameters**

- The parameter Column of data type any designates the column.
- The parameter Alignment of data type string designates the value of the alignment you want to check.

You can specify "Right" , "Left" , or "Center" .

Return Value

The return value has the data type boolean .

Example

```simtalk
print timeSequence1.isAlignmentColumn("column4","right")
```

SimTalk

getAlignmentColumn [SimTalk] - TimeSequence

isAlignmentColumn [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

###### setAlignmentColumn [SimTalk] - TimeSequence

Sets the alignment of the specified column(s) of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAlignmentColumn(Column:any[, Column:any,...,], Aligmnent:string)
```

**Parameters**

- The parameter Column of data type any designates the column whose alignment you want to set.
- The optional parameters Column of data type any designate additional columns whose alignment you want to set.
- The parameter Alignment of data type string designates the alignment you want to assign. You can specify "Left" , "Right" , or "Centered" .

**Example**

timeSequence1.setAlignmentColumn(5,"center") timeSequence1.setAlignmentColumn("Value","right")

SimTalk

getAlignmentColumn [SimTalk] - TimeSequence

isAlignmentColumn [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

setBackgroundColorColumn [SimTalk] - TimeSequence

Sets the background color of the specified column(s) of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setBackgroundColorColumn(Column:any [,Column:any,...], BackgroundColor:integer)
```

**Parameters**

- The parameter Column of data type any designates the column whose background color you want to set.
- The optional parameters Column of data type any designate additional columns whose background color you want to set.
- The parameter BackgroundColor of data type integer designates the color. You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow or 7 for Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Example**

timeSequence1.setBackgroundColorColumn(1,1) // sets the background color of column 1 to black timeSequence1.setBackgroundColorColumn(1,2,2) // sets the background color of columns 1 and 2 to red

**SimTalk**

getBackgroundColorColumn [SimTalk] - DataTable

makeRGBValue [SimTalk]

See also

Background Color [cells]

**setColumnWidth [SimTalk] - TimeSequence**

Sets the width of the specified column of the TimeSequence designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

&lt; Path &gt;.setColumnWidth(Column:any, ..., ColumnWidth:integer)

**Parameters**

- The parameters Column of data type any designate the columns whose width you would like to set.
- The parameter ColumnWidth of data type integer designates the width in character widths of a nonproportional font.

**Example**

timeSequence1.setColumnWidth("column2",10)

SimTalk

getColumnWidth [SimTalk] - TimeSequence

See also

Column Width [text box]

setEditorRightsColumn [SimTalk] - TimeSequence

Sets the editing permissions of the specified column(s) of the TimeSequence designated by &lt;Path&gt; to the specified value.

Type

Method

Syntax

&lt; Path &gt;.setEditorRightsColumn(Column:any, ..., ReadOnly:boolean)

**Parameters**

- The parameters Column of data type any designate the columns whose editor permissions you want to set.
- The parameter ReadOnly of data type boolean designates read-only access ( true ) or read and write access ( false ).

Example

timeSequence1.setEditorRightsColumn(1,true)

SimTalk

getEditorRightsColumn [SimTalk] - TimeSequence

See also

Editor [check box]

Information Flow [check box]

###### setFontColorColumn [SimTalk] - TimeSequence

Sets the font color of specified column(s) of the TimeSequence designated by &lt;Path&gt; to the specified value.

Type

Method

Syntax

&lt; Path &gt;.setFontColorColumn(Column:any, ..., FontColor:integer)

**Parameters**

- The parameters Column of data type any designate the column(s) whose font color you want to set.
- The parameter FontColor of data type integer designates the font color. You can specify for Black , for Red , for Green , for Blue , for Magenta , for Yellow or for

1 2 3 4 5 6 7 Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Example**

timeSequence1.setFontColorColumn(3,7)

**SimTalk**

getFontColorColumn [SimTalk] - TimeSequence

makeRGBValue [SimTalk]

See also

Font Color [cells]

###### setFontSizeColumn [SimTalk] - TimeSequence

Sets the font size of the specified column(s) of the TimeSequence designated by &lt;Path&gt; to the specified value.

Type

Method

Syntax

```simtalk
< Path >.setFontSizeColumn(Column:any, ..., FontSize:integer)
```

**Parameters**

- The parameters Column of data type any designate the columns whose font color you want to set.
- The parameter FontSize of data type integer designates the font size. You can enter 1 for Small , 2 for Medium , 3 for Large or 4 for Extra Large .

**Example**

timeSequence1.setFontSizeColumn("Value",2)

SimTalk

getFontSizeColumn [SimTalk] - TimeSequence

See also

Font Size [drop-down list] - cells, columns

###### setFormatString [SimTalk] - TimeSequence

Sets, depending on the data type, the format string of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setFormatString(Column:any, ..., FormatString:string)
```

**Parameters**

- The parameters Column of data type any designate the columns.
- The parameter FormatString of data type string designates the format string.

**Example**

timeSequence1.setFormatString(1,"8")

SimTalk

getFormatString [SimTalk] - TimeSequence

See also

Format String [text box]

###### setVisibility [SimTalk] - TimeSequence

Shows or hides the specified column(s) of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setVisibility(Column:any, ..., Visible:boolean)

**Parameters**

- The parameters Column of data type any designate the columns.
- The parameter Visibility of data type boolean sets if the columns will be shown ( true ) or not ( false ).

**Example**

timeSequence1.setVisibility(2,true)

SimTalk

getVisibility [SimTalk] - TimeSequence

Methods for Rows of the TimeSequence

###### \_Methods for Rows

The TimeSequence provides the methods listed in the table of contents to the left for the row format.

You can also select these settings under Format &gt; Row of the TimeSequence .

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

getAlignmentRow [SimTalk] - TimeSequence

Returns the alignment of the specified row of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAlignmentRow(Row:any) → string
```

Parameter

The parameter Row of data type any designates the row whose alignment you want to get.

Return Value

The return value has the data type string .

Example

print timeSequence1.getAlignmentRow("BurnIn")

SimTalk

isAlignmentRow [SimTalk] - TimeSequence

setAlignmentRow [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

getBackgroundColorRow [SimTalk] - TimeSequence

Returns the background color of the specified row of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getBackgroundColorRow(Row:any) → integer

Parameter

The parameter Row of data type any designates the row whose background color you want to get.

Return Value

The return value has the data type integer .

Example

print timeSequence1.getBackgroundColorRow(14)

SimTalk

setBackgroundColorRow [SimTalk] - TimeSequence

See also

Background Color [cells]

getEditorRightsRow [SimTalk] - TimeSequence

Returns the editor rights of the specified row of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getEditorRightsRow(Row:any) → boolean

Parameter

The parameter Row of data type any designates the row whose background color you want to get.

Return Value

The return value has the data type boolean .

true for read-only access.

false for read and write-access.

Example

```simtalk
print timeSequence1.getEditorRightsRow(1)
```

SimTalk

setEditorRightsRow [SimTalk] - TimeSequence

See also

Editor [check box]

Information Flow [check box]

getFontColorRow [SimTalk] - TimeSequence

Returns the font color of the specified row of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFontColorRow(Row:any) → integer
```

Parameter

The parameter Row of data type any designates the row whose font color you want to get.

Return Value

The return value has the data type integer .

Example

timeSequence1.getFontColorRow(34)

SimTalk

setFontColorRow [SimTalk] - TimeSequence

See also

Font Color [cells]

getFontSizeRow [SimTalk] - TimeSequence

Returns the font size of the specified column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFontSizeRow(Row:any) → integer
```

Parameter

The parameter Row of data type any designates the row whose font size you want to get.

Return Value

The return value has the data type integer .

1 stands for Small , 2 for Medium , 3 for Large , and 4 for Extra Large .

Example

```simtalk
print timeSequence1.getFontSizeRow(34)
```

SimTalk

setFontSizeRow [SimTalk] - TimeSequence

See also

Font Size [drop-down list] - cells, columns

###### isAlignmentRow [SimTalk] - TimeSequence

Returns if the alignment of the specified row of the TimeSequence designated by &lt;Path&gt; matches the designated value (true) or not (false).

**Syntax**

```simtalk
< Path >.isAlignmentRow(Row:any, Alignment:string) → boolean
```

**Parameters**

- The parameter Row of data type any designates the row.
- The parameter Alignment of data type string designates the value of the alignment you want to check.

You can specify "Right" , "Left" , or "Center" .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
print timeSequence1.isAlignmentRow(7,"center")
```

SimTalk

getAlignmentRow [SimTalk] - TimeSequence

setAlignmentRow [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

setAlignmentRow [SimTalk] - TimeSequence

Sets the alignment of the specified row(s) of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAlignmentRow(Row:any[, Row:any,...], Aligmnent:string)
```

**Parameters**

- The parameter Row of data type any designates the row whose alignment you want to set.
- The optional parameters Row of data type any designate additional rows whose alignment you want to set.
- The parameter Alignment of data type string designates the alignment you want to set. You can specify "Left" , "Right" , or "Centered" .

**Example**

timeSequence1.setAlignmentRow(2,"right")

SimTalk

isAlignmentRow [SimTalk] - TimeSequence

getAlignmentRow [SimTalk] - TimeSequence

See also

Alignment [cells and columns]

###### setBackgroundColorRow [SimTalk] - TimeSequence

Sets the background color of the specified row(s) of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setBackgroundColorRow(Row:any[, Row:any,...], BackgroundColor:integer)
```

**Parameters**

- The parameter Row of data type any designates the row whose background color you want to set.
- The optional parameters Row of data type any designate additional rows whose background color you want to set.
- The parameter BackgroundColor of data type integer designates the background color. You can specify for Black , for Red , for Green , for Blue , for Magenta , for Yellow , or for

1 2 3 4 5 6 7 Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Examples**

```simtalk
var rgb: integer // sets the background color of row 3
MyTimeSequence.setBackgroundColorRow(3,makeRGBValue(0,200,0)) // sets the background color of rows 4 and 8
MyTimeSequence.setBackgroundColorRow(4,8,makeRGBValue(60,100,0))
print MyTimeSequence.getBackgroundColorRow(3)
```

// sets the background color of row 1 to black MyTimeSequence.setBackgroundColorRow(1,1) // sets the background color of rows 1 and 2 to red MyTimeSequence.setBackgroundColorRow(1,2,2)

**SimTalk**

**getBackgroundColorRow [SimTalk] - DataTable**

makeRGBValue [SimTalk]

**See also**

**Background Color [cells]**

###### setEditorRightsRow [SimTalk] - TimeSequence

Sets the editing permissions of the designated row(s) of the TimeSequence designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setEditorRightsRow(Row:any[, Row:any, ...], ReadOnly:boolean)
```

**Parameters**

- The parameter Row of data type any designate the row(s).
- The parameter ReadOnly of data type boolean designates read-only access ( true ) or read and write access ( false ).

**Example**

timeSequence1.setEditorRightsRow(1,true)

SimTalk

getEditorRightsRow [SimTalk] - TimeSequence

See also

Editor [check box]

Information Flow [check box]

setFontColorRow [SimTalk] - TimeSequence

Sets the font color of the designated row(s) of the TimeSequence designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setFontColorRow(Row:any[, Row:any, ...], FontColor:integer)
```

**Parameters**

- The parameters Row of data type any designate the cells whose font color you want to set.
- The parameter FontColor of data type integer designates the color.

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow , or 7 for Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Example**

timeSequence1.setFontColorRow(34,5)

**SimTalk**

getFontColorRow [SimTalk] - TimeSequence

makeRGBValue [SimTalk]

See also

Font Color [cells]

###### setFontSizeRow [SimTalk] - TimeSequence

Sets the font size of the designated row(s) of the TimeSequence designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setFontSizeRow(Row:any[, Row:any, ...], FontSize:integer)
```

**Parameters**

- The parameters Row of data type any designate the rows whose font color you want to set.
- The parameter FontSize of data type integer designates the font size.

You can specify 1 for Small , 2 for Medium , 3 for Large , or 4 for Extra Large .

**Example**

timeSequence1.setFontSizeRow(2,2)

SimTalk

getFontSizeRow [SimTalk] - TimeSequence

See also

Font Size [drop-down list] - cells, columns

Methods for Accessing the TimeSequence

\_Methods for Accessing the TimeSequence

The TimeSequence provides the methods listed in the table of contents to the left for accessing it.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### [ , ] [SimTalk] - read cell contents, TimeSequence

The TimeSequence designated by &lt;Path&gt; enables you to randomly access the contents of the cells by employing the column and row indexes.

Remarks

The index statement begins and ends with a bracket. Within the bracket you first enter the column and then the row of the cell to be accessed. The data type of the return value is the same as the data type of the table cell. Plant Simulation just reads the contents of the cell but does not remove it!

Type

Method

Syntax

```simtalk
< Path >[Column:integer, Row:integer] → contents of the cell
```

**Parameters**

- The parameter Column of data type integer designates the column.
- The parameter Row of data type integer designates the row.

Return Value

The return value is the contents of the cell.

VOID if the cell is empty.

Example

```simtalk
print timeSequence[1,2]
print timeSequence["Value",2]
```

**[ , ] [SimTalk] - write cell contents, TimeSequence**

###### [ , ] [SimTalk] - write cell contents, TimeSequence

Writes data to the specified cell of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >[Column:integer, Row:integer]
```

**Parameters**

- The parameter Column of data type integer designates the column.
- The parameter Row of data type integer designates the row.

First you access the cell by its index and then you assign a value.

The index statement starts and ends with a bracket. In the bracket you first enter the column and then the row of the cell to be accessed. The data type of the new value has to be the same as the data type of the table cell.

Example

timeSequence[2,3] := 12.34

###### add [SimTalk]

Either adds a numerical value to all entries of the value column of the TimeSequence designated by &lt;Path&gt; or combines the time and value columns of two TimeSequence objects.

Type

Method

Syntax

&lt; Path &gt;.add(ValueToBeAdded:any)

**Parameter**

If the parameter ValueToBeAdded of data type any which is to be added is a numerical value, Plant Simulation adds it to each entry of the value column. The time column remains unchanged.

If the parameter ValueToBeAdded is another TimeSequence , Plant Simulation adds time value pairs in sections. The values in the time columns determine the extent of the individual sections. If for a certain time value there are multiple entries in one time sequence, and only one entry in the other time sequence, the single entry will be added to all other entries. If both time sequences have the same number of multiple entries with a particular time value, the entries will be combined in pairs and added afterwards. If the number of entries with the same time value differs, the last entry will be duplicated, before the addition is performed, until the number of entries with the same time matches.

**Example**

MyTimeSequence.add(5) shiftA.add(shiftB)

###### and [SimTalk] - operator

and [SimTalk] - operator

You can use boolean operations, such as and and or , in a TimeSequence of data type boolean .

Remarks

The boolean operation may be executed with a single boolean parameter or another TimeSequence object. In the latter case, the sequence of values in the time column will be the union of the time columns of both time sequences involved in the operation.

Type

Method/operator

Syntax

&lt; Path &gt;.and(Operand:any)

Parameter

The parameter Operand of data type any designates the operand which will be applied.

Example

failureA.and(failureB) workerA.or(workerB) MyTimeSequence.or(true) MyTimeSequence.and(false)

See also

or [SimTalk] - operator

###### deleteInterval [SimTalk]

Deletes all values located within the designated time interval from the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteInterval([BeginningOfInterval:time, EndOfInterval:time])

**Parameters**

- The optional parameter BeginningOfInterval of data type time designates the beginning of the time interval.
- The optional parameter EndOfInterval of data type time designates the end of the time interval.

The TimeSequence also deletes entries matching one of the boundaries.

**Example**

resultList.deleteInterval(0,3600)

divide [SimTalk]

divide [SimTalk]

Divides all items of the value column of the TimeSequence designated by &lt;Path&gt; by a numerical value.

Remarks

In addition, a time sequence may be divided by another time sequence. Then, the time column of the result is the combination of the time column of both time sequences. The value column of the result contains the quotient of the values of both time sequences at the respective times.

Note

All divisors must be non-zero.

Type

Method

Syntax

&lt; Path &gt;.divide(Divisor:any)

Parameter

The parameter Divisor of data type any designates the divisor which will be applied.

Example

MyTimeSequence.divide(5) numEntities.divide(current.NumMU)

###### include [SimTalk]

Takes all entries of the TimeSequence designated by the parameter of data type object and inserts them in the TimeSequence designated by &lt;Path&gt;.

Remarks

Inserting all entries may result in a single time sequence containing multiple entries with the same time value. If this happens, the order of the entries with identical time values, with respect to each other, is undefined.

The data types of the affected time sequences must be identical or compatible.

Type

Method

Syntax

&lt; Path &gt;.include(TimeSequence:object)

**Parameter**

The parameter TimeSequence of data type object designates the TimeSequence whose values will be included.

Example

timeSequence1.include(timeSequence2)

**insert [SimTalk] - TimeSequence**

###### insert [SimTalk] - TimeSequence

Inserts a time/value pair into the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.insert(GivenTime:any, Value:any)

**Parameters**

- The parameter GivenTime of data type any designates the time.

For the time reference Absolute , this parameter is expected to be of data type dateTime . Otherwise, the data type time is required.

- The parameter Value of data type any designates the value.

The type of the value for this parameter, must match or be compatible with the data type of the TimeSequence .

**Example**

MyTimeSequence.insert(eventcontroller.simtime,3) MyTimeSequence.insert(sysdate,3)

###### multiply [SimTalk]

Multiplies all items of the value column of the TimeSequence designated by &lt;Path&gt; with a numerical value. In addition, a time sequence may be multiplied with another time sequence.

Remarks

The time column of the result is the union of the time column of both time sequences. The value column of the result contains the product of the values of both time sequences at the respective times.

Type

Method

Syntax

&lt; Path &gt;.multiply(Factor:any)

Parameter

The parameter Factor of data type any designates the multiplication factor.

Example

MyTimeSequence.multiply(5) dimx.multiply(dimy)

###### not [SimTalk] - TimeSequence

not [SimTalk] - TimeSequence

Applies a boolean NOT operation to all values in the value column of the TimeSequence designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.not

Example

MyTimeSequence.not // reverses all inputs

or [SimTalk] - operator

You can use boolean operations, such as and and or , in a TimeSequence of data type boolean .

Remarks

The boolean operation may be executed with a single boolean parameter or another TimeSequence object. In the latter case, the sequence of values in the time column will be the union of the time columns of both time sequences involved in the operation.

Type

Method

Syntax

< Path >.or(Operand:any)

Parameter

The parameter Operand of data type any designates the operand which will be applied.

Example

failureA.and(failureB) workerA.or(workerB) MyTimeSequence.or(true) MyTimeSequence.and(false)

SimTalk

and [SimTalk] - operator

###### repeat [SimTalk] - TimeSequence

Deletes all entries of the TimeSequence designated by &lt;Path&gt; and replaces them with copies of a subrange of the data of another TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.repeat(TimeSequence:object, Subrange:time, NumberOfCopies:real)

**Parameters**

- The parameter TimeSequence of data type object designates the TimeSequence whose subrange will be pasted.
- The parameter Subrange of data type time designates the sub-range. It starts with the time zero and ends at the time designated by this parameter.
- The parameter NumberOfCopies of data type real designates the number of copies of the data which are to be inserted.

You might, for example, use this to create a week's schedule from a day's schedule by repeating it five times.

**Example**

LengthOfDay := str\_to\_time("1:00:00:00.00") weekPlan.repeat(dayPlan,lengthOfDay,5)

###### repeatTo [SimTalk]

Removes all entries of the TimeSequence designated by &lt;Path&gt; and replaces them with copies of a sub-range of the data of the designated TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.repeatTo(TimeSequence:object, Subrange:time, RangeToBeFilled:time)
```

**Parameters**

- The parameter TimeSequence of data type object designates the TimeSequence whose data will replace the existing data.
- The parameter Subrange of data type time designates the sub-range. It starts with the time zero and ends at the time designated by this parameter.
- The parameter RangeToBeFilled of data type time designates the range of the TimeSequence designated by &lt;Path&gt; that is to be filled with copies of the sub-range.

Consequently, the range of the TimeSequence designated by &lt;Path&gt; must be greater than the subrange of the TimeSequence designated by the parameter of data type object. Otherwise, it would remain empty.

**Examples**

```simtalk
weekPeriod := str_to_time("5:00:00:00.00")
dayPeriod := str_to_time("1:00:00:00.00")
weekPlan.repeatTo(dayPlan,weekPeriod,dayPeriod)
MyTimeSequence.or(true) // all
values := true
MyTimeSequence.and(false) // all
values := false
```

**subtract [SimTalk]**

###### subtract [SimTalk]

Either subtracts a numerical value from all entries of the value column of the TimeSequence designated by &lt;Path&gt; or it combines the time and value columns of two TimeSequence objects.

Type

Method

Syntax

```simtalk
< Path >.subtract(ValueToBeSubtracted:integer) < Path >.subtract(ValueToBeSubtracted:real) < Path >.subtract(ValueToBeSubtracted:object)
```

**Parameters**

- If the parameter to subtract is a numerical value designated by the parameter ValueToBeSubtracted of data type integer or real , Plant Simulation subtracts it from each entry of the value column. The time column remains unchanged.
- If the parameter to subtract is another TimeSequence designated by the parameter ValueToBeSubtracted of data type object , Plant Simulation subtracts time value pairs in sections. The values in the time columns set the extent of the individual sections. If for a certain time value there are multiple entries in one time sequence, and only one entry in the other time sequence, the single entry will be subtracted from all other entries.

If both TimeSequences contain the same number of multiple entries with a particular time value, Plant Simulation combines the entries in pairs and subtracts them afterwards. If the number of entries with the same time value differs, Plant Simulation duplicates the last entry, before it subtracts it, until the number of entries with the same time matches.

**Example**

MyTimeSequence.subtract(5) stock.subtract(missingEntities)

value [SimTalk] - TimeSequence

Returns the value the TimeSequence designated by &lt;Path&gt; taken at a given time.

Remarks

If there are multiple entries with the same time, Plant Simulation returns the entry with the highest number.

Type

Method

Syntax

< Path >.value(GivenTime:time) -> any

Parameter

The parameter GivenTime of data type time designates the column.

Return Value

The return value has the data type any .

Example

```simtalk
print ts1.value(1.5)+ts2.value(1.5)
```

#### Read-Only Attributes of the TimeSequence

Read-Only Attributes of the TimeSequence

The TimeSequence provides:

- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyTimeSequence.Full

#### Attributes of the TimeSequence

**\_Attributes of the TimeSequence**

The TimeSequence provides:

- The attributes listed in the table of contents to the left.
- The Attributes of Lists and Tables .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTimeSequence.ReferenceTime := str_to_time("1:00:00:00.00")
print MyTimeSequence.Active
posit := Station.Cont.XPos
```

Absolute [SimTalk] - TimeSequence

Sets the Time Reference of the TimeSequence designated by &lt;Path&gt; to Absolute ( true ) or Relative ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Absolute:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTimeSequence.Absolute := true

See also

Time Reference [TimeSequence]

##### Active [SimTalk] - TimeSequence

Activates the object designated by &lt;Path&gt; ( true ), i.e., makes it record data, or deactivates it ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Active:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTimeSequence.Active := true
```

See also

Active [check box] - TimeSequence DefaultValue [SimTalk]

DefaultValue [SimTalk]

Sets the Default Value of the TimeSequence designated by &lt;Path&gt;.

Remarks

The data type of the TimeSequence matches the data type of the column Value on the tab Contents of the TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.DefaultValue:any

Assignment Value

You can assign a value of data type any .

Example

MyTimeSequence.DefaultValue := "Body"

See also

Default Value [TimeSequence]

###### Path [SimTalk] - TimeSequence

Sets the Path to the value which the TimeSequence designated by &lt;Path&gt; is to record.

Remarks

The value can be specified as a relative or as an absolute path.

Type

Attribute

Syntax

```simtalk
< Path >.Path:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyTimeSequence.Path := "Station.NumMU"
MyTimeSequence.Path := "&MyVariable"
```

See also

Value [TimeSequence]

##### ReferenceDate [SimTalk] - TimeSequence

Sets the off-set value of the time sequence inputs for the setting Time Reference &gt; Absolute of the TimeSequence designated by &lt;Path&gt;.

Remarks

Plant Simulation adds it to each time value in the TimeSequence table. By changing the reference time, you can shift the values in time without re-entering the data.

Type

Attribute

Syntax

&lt; Path &gt;.ReferenceDate:dateTime

Assignment Value

You can assign a value of data type dateTime .

Example

```simtalk
ts1.ReferenceDate := sysdate
```

See also

Start Date [Trigger]

ReferenceTime [SimTalk] - TimeSequence

Sets the Start Time of the TimeSequence designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.ReferenceTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
ts1.ReferenceTime := str_to_time("1:00:00:00.00")
```

See also

Start Time [Trigger]

**Sample [SimTalk]**

##### Sample [SimTalk]

Makes the TimeSequence designated by &lt;Path&gt; record data periodically ( true ) or watch data, i.e., records them only when its value changes ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Sample:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
ts.Sample := true
```

See also

Mode [drop-down list] - TimeSequence ShowColumnIndex [SimTalk] - TimeSequence Shows the column index of the TimeSequence designated by &lt;Path&gt; ( true ) or hides it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowColumnIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

timeSequence2.ShowColumnIndex := false

See also

Activate Column Index ShowRowIndex [SimTalk] - TimeSequence Shows the row index of the TimeSequence designated by &lt;Path&gt; ( true ) or hides it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowRowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

timeSequence2.ShowRowIndex := true

See also

Activate Row Index

###### SmpPeriod [SimTalk] - TimeSequence

Sets how often the TimeSequence designated by &lt;Path&gt; takes samples, when Sample mode is active.

Remarks

SmpPeriod applies when the attribute Sample is set to true .

Type

Attribute

Syntax

&lt; Path &gt;.SmpPeriod:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
ts.smpPeriod := 60
```

See also

Interval [TimeSequence]

Sample [SimTalk]

