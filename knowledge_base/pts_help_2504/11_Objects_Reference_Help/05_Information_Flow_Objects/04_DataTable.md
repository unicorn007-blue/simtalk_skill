### DataTable

#### DataTable [object]

Use the DataTable for storing data in several columns, which can have different data types.

Icon

<!-- image -->

**Description**

You can access the individual cells in the DataTable via their index, i.e., by their position designated by the number of the row and the number of the column. You can compare a DataTable to a shelf in which you enter values and references to the cells and remove them again. As opposed to the DataList , the contents of the cells remain in the DataTable and the DataTable can also have blank cells in a range. You can add and remove rows and columns during a simulation run at will.

You can access the functions of the list objects on the List Ribbon Tab .

**Note**

The DataTable always opens in the background behind any open dialog boxes. You can open it in the foreground as a dialog box with the method openDialogBox .

The DataTable shares its built-in properties with the data type table . Note the difference between the object DataTable that you can insert into models and the data type table . You can create user-defined attributes and local and global variables of data type table that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason these variables and attributes do not recognize the SimTalk functions of the DataTable , such as Location or existsIcon . All other methods, especially for read and write access apply to both the DataTable and to variables and attributes.

You can also show the contents of a DataTable in an HtmlReport , compare Display a DataTable or a DataList .

To show a tooltip with information about the DataTable , hover with the mouse over it.

To change the length of the graphic and the anchor points of the DataTable , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the DataTable to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; DataTable on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**Note**

The MaterialsTable of the fluid objects shares the properties of the DataTable .

**DataTable [object]**

**See also**

Work with Data in a List or Table in the Step-by-Step Help

Work with Data in the DataTable in the Step-by-Step Help

Access Data in Lists in the Step-by-Step Help

Accessing a Range of Cells with a Method

Creating Lists within Lists and Tables

Creating a List within a DataTable

**Window of the DataTable**

As lists and tables are so versatile, we use them in a number of our example models:

| Produce Parts According to a Delivery Table                     | Produce the Parts with a Source Using a Sequence Table     |
|-----------------------------------------------------------------|------------------------------------------------------------|
| Produce Parts in a Fixed Sequence Over and Over Again           | Visualize the Occupancy of the Store Over Time             |
| Produce Parts With a Random Frequency Entered into a Data Table | Model Processing and Set-up Jobs                           |
| Produce Parts With a Percentage Entered into a Data Table       | Write the Content List into a Table for Further Processing |
| Define Times in the Class of the Processing Stations            | Select Where the Data Comes From                           |
| Create the Work Plan                                            |                                                            |

#### Window of the DataTable

Double-click the icon of the DataTable to open its window. In the window you can change its simulation properties .

The shared properties are described under Dialog Items of the Objects . You can access the functions of the list objects on the List Ribbon Tab .

<!-- image -->

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**List Ribbon Tab**

The List Ribbon Tab provides commands pertaining to the lists and tables. Not all list objects provide all of the described commands.

<!-- image -->

**Methods of the DataTable**

#### Methods of the DataTable

The DataTable provides:

- \_Methods of Columns of the DataTable
- \_Methods of Rows of the DataTable
- \_Miscellaneous Methods of the DataTable
- \_Methods for Accessing the DataTable
- \_Methods for Instantiating the DataTable
- The shared Methods of Lists and Tables .
- The shared Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- ◦ The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

If a parameter has a default value, the signature shows the default value after the parameter

If the method has a return value, the signature shows its data type after the arrow -&gt;.

- We use these abbreviations for the signature:

<!-- image -->

| Argument of data type   | Data type      | Range of values            |
|-------------------------|----------------|----------------------------|
| integer                 | integer        | integer greater than zero  |
| any                     | all data types | depending on the data type |
| listrange               | -              | a range                    |
| direction               | string         | "up", "down", " "          |
| attributes              | string         | name of an attribute       |

**See also**

**Address Columns and Rows with Methods**

##### Methods of Columns of the DataTable

##### \_Methods of Columns of the DataTable

The DataTable provides the methods listed in the table of contents to the left for columns. The first parameter designates the column, either the column index, the column range, or the column number.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**See also**

Address Columns and Rows with Methods

###### cutColumn [SimTalk]

Cuts the designated column, including all of its data, from the DataTable designated by &lt;Path&gt;.

Remarks

Plant Simulation shifts all columns with an index equal to or greater than any to the left.

Note

You cannot cut the column index with the instruction cutColumn(0) .

Type

Method

Syntax

```simtalk
< Path >.cutColumn(Column:any) → boolean
```

Parameter

The parameter Column of data type any designates the column you want to cut.

Return Value

The return value has the data type boolean .

Example

MyDataTable.cutColumn(8)

SimTalk

insertColumn [SimTalk]

See also

Remove Column [context menu, lists]

Cut [Home ribbon]

getAlignmentColumn [SimTalk] - DataTable

Returns the alignment of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAlignmentColumn(Column:any) → string
```

Parameter

The parameter Column of data type any designates the column whose alignment you want to get.

Return Value

The return value has the data type string . Left, right, or centered.

Example

```simtalk
print MyDataTable.getAlignmentColumn(4)
```

SimTalk

isAlignmentColumn [SimTalk] - DataTable

setAlignmentColumn [SimTalk] - DataTable

See also

Alignment [cells and columns]

getBackgroundColorColumn [SimTalk] - DataTable

Returns the background color of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getBackgroundColorColumn(Column:any) → integer
```

Parameter

The parameter Column of data type any designates the column whose background color you want to get.

Return Value

The return value has the data type integer .

Example

```simtalk
print MyDataTable.getBackgroundColorColumn(4)
```

SimTalk

setBackgroundColorColumn [SimTalk] - DataTable

See also

Background Color [cells]

###### getColumnNo [SimTalk]

Searches for the column which contains a user-defined column index of the DataTable designated by &lt;Path&gt;.

Remarks

**Note**

If the table contains a large number of entries, you might want to activate Fast Index Access .

The method only works for simple data types, such as string , integer , etc.

Type

Method

Syntax

```simtalk
< Path >.getColumnNo(ColumnIndex:any) → integer
```

**Parameter**

The parameter ColumnIndex of data type any designates the column index which Plant Simulation searches for.

Return Value

The return value has the data type integer .

The return value is the column number.

If the column index does not exist, Plant Simulation returns -1.

**Example**

```simtalk
var column : integer
column := MyDataTable.getColumnNo("Urgent")
```

**SimTalk**

getRowNo [SimTalk]

FastAccessColumnIndex [SimTalk]

**FastAccessRowIndex [SimTalk]**

getColumnUniqueValues [SimTalk]

Returns an array with the values, which only are contained once in the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.getColumnUniqueValues(Column:any) → any[]

Parameter

The parameter Column of data type any designates the column.

The column has to be of data type String , Integer , Real , Time , Money , Length , Weight , Speed , Acceleration , Date , or DateTime .

Return Value

The return value is an array of data type any .

Example

```simtalk
print MyDataTable.getColumnUniqueValues(1)
```

getColumnWidth [SimTalk] - DataTable

Returns the width of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getColumnWidth(Column:any) → integer
```

Parameter

The parameter Column of data type any designates the column.

Return Value

The return value has the data type integer .

Example

```simtalk
MyDataTable.getColumnWidth(1)
print MyDataTable.getColumnWidth(1)
```

SimTalk

setColumnWidth [SimTalk] - DataTable

See also

Column Width [text box]

###### getColumnYDim [SimTalk]

Returns the number of the last cell of the specified column of the DataTable designated by &lt;Path&gt; that contains an entry.

Type

Method

Syntax

```simtalk
< Path >.getColumnYDim(ColumnNumber:integer) → integer
```

Parameter

The parameter ColumnNumber of data type integer designates the number of the column you want to query.

Return Value

The return value has the data type integer .

0 if the column is empty.

Example

```simtalk
MyDataTable.getColumnYDim(1)
print MyDataTable.getColumnYDim(1)
```

SimTalk

XDim [SimTalk] - DataTable

YDim [SimTalk] - DataTable

getCommonFormat [SimTalk]

Returns if Common Format of the specified column of the DataTable designated by &lt;Path&gt; is turned on (true) or off (false).

Type

Method

**Syntax**

&lt; Path &gt;.getCommonFormat(Column:any) -&gt; boolean)

Parameter

The parameter Column of data type any designates the column.

Example

print MyDataTable.getCommonFormat(3)

SimTalk

setCommonFormat [SimTalk]

CommonFormatColumnIndex [SimTalk]

getCommonFormatData [SimTalk] - DataTable

setCommonFormatData [SimTalk] - DataTable

See also

Tab Contents

Common Format [check box]

getDataType [SimTalk]

Returns the data type of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getDataType(Column:any) → string
```

Parameter

The parameter Column of data type any designates the column.

Return Value

The return value has the data type string .

Example

```simtalk
print MyDataTable.getDataType(1)
```

SimTalk

DataType [SimTalk] - lists

setDataType [SimTalk]

setDataTypeDefault [SimTalk]

See also

Data Type [lists]

getEditorRightsColumn [SimTalk] - DataTable

Returns the editor rights of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getEditorRightsColumn(Column:any) → boolean
```

Parameter

The parameter Column of data type any designates the column whose editor rights you want to get.

Return Value

The return value has the data type boolean :

true for read-only access.

false for read and write access.

Example

```simtalk
MyDataTable.getEditorRightsColumn(1)
print MyDataTable.getEditorRightsColumn(1)
```

SimTalk

setEditorRightsColumn [SimTalk] - DataTable

See also

Editor [check box]

Information Flow [check box]

getFontColorColumn [SimTalk] - DataTable

Returns the font color of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFontColorColumn(Column:any) → integer
```

Parameter

The parameter Column of data type any designates the column whose font color you want to get.

Return Value

The return value has the data type integer .

Example

```simtalk
MyDataTable.getFontColorColumn(2)
print MyDataTable.getFontColorColumn(3)
```

SimTalk

setFontColorColumn [SimTalk] - DataTable

See also

Font Color [cells]

getFontSizeColumn [SimTalk] - DataTable

Returns the font size of the specified column of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getFontSizeColumn(Column:any) → integer

Parameter

The parameter Column of data type any designates the column whose font size you want to get.

Return Value

The return value has the data type integer .

1 stands for Small , 2 for Medium , 3 for Large , and 4 for Extra Large .

Example

```simtalk
print MyDataTable.getFontSizeColumn(2)
```

SimTalk

setFontSizeColumn [SimTalk] - DataTable

See also

Font Size [drop-down list] - cells, columns getFormatString [SimTalk] - DataTable Returns the Format String of the specified column of the DataTable designated by &lt;Path&gt;.

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
tab1.getFormatString("paint")
print tab1.getFormatString(1)
```

SimTalk

setFormatString [SimTalk] - DataTable

See also

Format String [text box]

getVisibility [SimTalk] - DataTable

getVisibility [SimTalk] - DataTable

Returns if a column of the DataTable designated by &lt;Path&gt; is visible ( true ) or hidden ( false ).

Type

Method

Syntax

```simtalk
< Path >.getVisibility(Column:any) → boolean
```

Parameter

The parameter Column of data type any designates the column.

Return Value

The return value has the data type boolean .

Example

print MyDataTable.getVisibility(4)

SimTalk

setVisibility [SimTalk] - DataTable

See also

Work with Data in the DataTable

**insertColumn [SimTalk]**

Adds an empty column to the left of the specified column into the DataTable designated by &lt;Path&gt;.

**Remarks**

Plant Simulation shifts all columns with an index equal to or greater than the parameter any one position to the right.

<!-- image -->

Type

Method

Syntax

<!-- image -->

**Parameter**

The parameter Column of data type any designates the column number at which the empty column will be inserted into the DataTable .

**Return Value**

The return value has the data type boolean .

**Example**

MyDataTable.insertColumn(8)

SimTalk cutColumn [SimTalk] See also Insert Column [context menu, lists] Insert Column [lists]

**isAlignmentColumn [SimTalk] - DataTable**

Returns if the alignment of the specified column of the DataTable designated by &lt;Path&gt; matches the designated value (true) or not (false).

Type

Method

Syntax

```simtalk
< Path >.isAlignmentColumn(Column:any, Alignment:string) → boolean
```

**Parameters**

- The parameter Column of data type any designates the column.
- The parameter Alignment of data type string designates the value of the alignment you want to check.

You can specify "Right" , "Left" or "Center" .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
print MyDataTable.isAlignmentColumn("column4","right")
```

SimTalk

getAlignmentColumn [SimTalk] - DataTable

setAlignmentColumn [SimTalk] - DataTable

See also

Alignment [cells and columns]

###### setAlignmentColumn [SimTalk] - DataTable

setAlignmentColumn [SimTalk] - DataTable

Sets the alignment of column(s) of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAlignmentColumn(Column:any [,Column:any,...], Aligmnent:string)
```

**Parameters**

- The parameter Column of data type any designates the column whose alignment you want to set.
- The optional parameters Column of data type any designate additional columns whose alignment you want to set.
- The parameter Alignment of data type string designates the alignment you want to assign.

You can specify "Left" , "Right" , or "Centered" .

**Example**

MyDataTable.setAlignmentColumn(1,"right") MyDataTable.setAlignmentColumn(1,2,"right")

SimTalk

getAlignmentColumn [SimTalk] - DataTable

isAlignmentColumn [SimTalk] - DataTable

See also

Alignment [cells and columns]

###### setBackgroundColorColumn [SimTalk] - DataTable

Sets the background color of column(s) of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setBackgroundColorColumn(Column:any[, Column:any,...], BackgroundColor:integer)
```

**Parameters**

- The parameter Column of data type any designates the column whose background color you want to set.
- The optional parameters Column of data type any designate additional columns whose background color you want to set.
- The parameter BackgroundColor of data type integer designates the color. You can specify for Black , for Red , for Green , for Blue , for Magenta , for Yellow or for

1 2 3 4 5 6 7 Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Examples**

```simtalk
var rgb: integer // sets the background color of column 2
MyDataTable.setBackgroundColorColumn(2,makeRGBValue(120,0,0)) // sets the background color of columns 3 and 5
MyDataTable.setBackgroundColorColumn(3,5,makeRGBValue(120,10,0))
print MyDataTable.getBackgroundColorColumn(2)
```

MyDataTable.setBackgroundColorColumn(1,1)    // sets the background color MyDataTable.setBackgroundColorColumn(1,2,2)  // sets the background color

of column 1 to black of columns 1 and 2 to red

**SimTalk**

getBackgroundColorColumn [SimTalk] - DataTable

makeRGBValue [SimTalk]

**See also**

**Background Color [cells]**

###### setColumnWidth [SimTalk] - DataTable

Sets the width of one or several columns of the DataTable designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setColumnWidth(Column:any[, Column:any, ...], ColumnWidth:integer)
```

**Parameters**

- The parameters Column of data type any designate the columns.
- The parameter ColumnWidth of data type integer designates the width in character widths of a nonproportional font.

**Example**

MyDataTable.setColumnWidth("column12",10)

SimTalk

getColumnWidth [SimTalk] - DataTable

See also

Column Width [text box]

###### setCommonFormat [SimTalk]

###### setCommonFormat [SimTalk]

Assigns the same format to all columns within the designated range of the DataTable designated by &lt;Path&gt;.

**Remarks**

If you activated Common Format for a column, assigning a subtable to a table cell creates a copy of the assigned table. Otherwise, Plant Simulation enters a reference to the assigned table. The reason for this is that it does not make sense to enter a reference if Common Format is active as the assigned table should not be subject to the common format.

Type

Method

Syntax

```simtalk
< Path >.setCommonFormat(Column:any[, Column:any, ..., ]CommonFormat:boolean)
```

**Parameters**

- The parameters Column of data type any designate the columns.
- The parameter CommonFormat of data type boolean activates ( true ) or deactivates the Common Format ( false ).

**Note**

To define the Common Format of the specified column of data type table in a method, create a subtable and then format this table with the method setDataType .

**Examples**

// activate common format for the columns 3 to 5, for column 7 and for the // column with the user-defined column index 'mycolumn'. MyDataTable.setCommonFormat({3,*}..{5,*},7,"mycolumn", true)

```simtalk
MyDataTable.setDataType(3,"Table")
MyDataTable.setCommonFormat(3,true) -- formats the subtable within the table
MyDataTable.createNestedList(3,1) MyDataTable[3,1].setDataType(2,"Boolean")
MyDataTable.createNestedList(3,7) MyDataTable[3,7][2,77] := true
```

SimTalk getCommonFormat [SimTalk] CommonFormatColumnIndex [SimTalk] getCommonFormatData [SimTalk] - DataTable setCommonFormatData [SimTalk] - DataTable setDataType [SimTalk] createNestedList [SimTalk] - DataList createNestedList [SimTalk] - DataTable createNestedList [SimTalk] - local variable See also Creating Lists within Lists and Tables Activating and Deactivating Common Format Tab Contents Common Format [check box]

###### setDataType [SimTalk]

###### setDataType [SimTalk]

Sets the data type of the specified column(s) of the DataTable designated by &lt;Path&gt; to the designated value.

**Syntax**

```simtalk
< Path >.setDataType(Column:any, [Column:any, ..., ]DataType:string)
```

**Parameters**

- The parameters Column of data type any designate the columns.
- The parameter DataType of data type string designates the data type.

| Data type    | Description                                                                                          |
|--------------|------------------------------------------------------------------------------------------------------|
| Acceleration | applies for the objects Conveyor , Track , TwoLaneTrack , and Transporter , meter per second squared |
| Boolean      | true or false                                                                                        |
| Date         | date statement ( dd.MM.yyyy )                                                                        |
| DateTime     | date statement, including the time ( dd.MM.yyyy HH:mm:ss )                                           |
| Integer      | integer value                                                                                        |
| Length       | floating point number, value depends on the unit of the length                                       |
| List         | list with one column, shares properties of the DataList                                              |
| Money        | floating point numbers                                                                               |
| Object       | reference to a simulation model or an object                                                         |
| Queue        | list with one column, shares properties of the DataQueue                                             |
| Real         | floating point number, such as 3.1415                                                                |
| Speed        | floating point number, value depends on the unit for speed                                           |
| Stack        | list with one column, shares properties of the DataStack                                             |
| String       | characters, numbers and special characters                                                           |
| Table        | table with one or more columns, shares properties of the DataTable                                   |
| Time         | time statement (hh:mm:ss.ss)                                                                         |
| Weight       | floating point number, value depends on the unit of the weight                                       |

**Example**

```simtalk
-- set data type of column 2 and column 5
MyDataTable.setDataType(2, 5, "real") -- set the data type of the row index
MyDataTable.setDataType(0, "integer") -- set the data type of columns 3 to 5, of column 7 and of the column -- with the user-defined column index "mycolumn" to the data type real
MyDataTable.setDataType({3,*}..{5,*},7,"mycolumn","real")
```

**SimTalk**

DataType [SimTalk] - lists getDataType [SimTalk] setDataTypeDefault [SimTalk] See also Data Type [lists] Tab Contents

setDataTypeDefault [SimTalk]

setDataTypeDefault [SimTalk]

Resets the data type of the specified column(s) of the DataTable designated by &lt;Path&gt; to the default data type of the table.

Type

Method

Syntax

< Path >.setDataTypeDefault(Column:any, ...)

Parameter

The parameters Column of data type any designate the columns.

Example

```simtalk
// resets the data type of the columns 3 to 4, and of column 10 to // the standard data type of the table
MyDataTable.setDataTypeDefault({3,*}..{4,*},10)
```

SimTalk

getDataType [SimTalk]

setDataType [SimTalk] See also Data Type [lists]

###### setEditorRightsColumn [SimTalk] - DataTable

Sets the editing permissions of the specified column(s) of the DataTable designated by &lt;Path&gt; to the specified value.

true

**Syntax**

```simtalk
< Path >.setEditorRightsColumn(Column:any[, Column:any, ...], ReadOnly:boolean)
```

**Parameters**

- The parameters Column of data type any designate the column(s) whose editing permissions you want to set.
- The parameter ReadOnly of data type boolean designates read-only access ( true ) or read and write access ( false ).

**Example**

// sets the editor rights of column 1 Tab1.setEditorRightsColumn(1,true) // sets the editor rights of columns 2 and 4 Tab1.setEditorRightsColumn(2,4,true)

**SimTalk**

getEditorRightsColumn [SimTalk] - DataTable

See also

Editor [check box]

Information Flow [check box]

###### setFontColorColumn [SimTalk] - DataTable

Sets the font color of the specified column(s) of the DataTable designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setFontColorColumn(Column:any[, Column:any, ...], FontColor:integer)
```

**Parameters**

- The parameters Column of data type any designate the column(s) whose font color you want to set.
- The parameter FontColor of data type integer designates the font color.

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow or 7 for Cyan .

Set the RGB values of the color with the method makeRGBValue .

**Example**

// sets the font color of column 3 to cyan Tab2.setFontColorColumn(3,7) // sets the font color of column 1 and 5 to green Tab2.setFontColorColumn(1,5,3)

**SimTalk**

getFontColorColumn [SimTalk] - DataTable

makeRGBValue [SimTalk]

See also

Font Color [cells]

###### setFontSizeColumn [SimTalk] - DataTable

Sets the font size of the specified column(s) of the DataTable designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setFontSizeColumn(Column:any[, Column:any, ...], FontSize:integer)
```

**Parameters**

- The parameters Column of data type any designate the columns whose font size you want to set.
- The parameter FontSize of data type integer designates the font size.

You can specify 1 for Small , 2 for Medium , 3 for Large or 4 for Extra Large .

**Example**

// sets the font size of column 2 to medium Tab2.setFontSizeColumn(2,2) // sets the font size of columns 3 and 5 to small Tab2.setFontSizeColumn(3,5,1)

**SimTalk**

getFontSizeColumn [SimTalk] - DataTable

See also

Font Size [drop-down list] - cells, columns

###### setFormatString [SimTalk] - DataTable

Sets, depending on the data type, the Format String of the specified column(s) of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setFormatString(Column:any[, Column:any, ...], FormatString:string)
```

**Parameters**

- The parameters Column of data type any designate the columns for which you want to set the format string.
- The parameter FormatString of data type string designates the format string.

**Example**

MyDataTable.setFormatString(1,"-15.3") // three digits after the comma

SimTalk

getFormatString [SimTalk] - DataTable

See also

Format String [text box]

###### setVisibility [SimTalk] - DataTable

Shows ( true ) or hides ( false ) the designated column(s) of the DataTable designated by &lt;Path&gt;.

**Syntax**

```simtalk
< Path >.setVisibility(Column:any[, Column:any, ...], Visibility:boolean)
```

**Parameters**

- The parameters Column of data type any designate the columns which you want to show or hide.
- The parameter Visibility of data type boolean sets if the columns will be shown ( true ) or not ( false ).

**Example**

MyDataTable.setVisibility(2,true)

SimTalk

getVisibility [SimTalk] - DataTable

See also

Work with Data in the DataTable

Methods of Rows of the DataTable

**\_Methods of Rows of the DataTable**

The DataTable provides the methods listed in the table of contents to the left for rows. The first parameter designates the column, either the column index, the column range or the column number.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**See also**

**Address Columns and Rows with Methods**

###### appendRow [SimTalk]

Adds a new row to the DataTable designated by &lt;Path&gt; and writes the passed values to the individual columns.

Remarks

If the row has a row index, Plant Simulation writes the first value into the row index.

You cannot add a row if the maximum number of rows has already been reached.

Type

Method

Syntax

```simtalk
< Path >.appendRow(Value:any[, Value:any, ..., Value:any])
-> integer
```

**Parameters**

- The parameter Value of data type any designates the value that Plant Simulation is to write to the first cell in the first free row.
- The optional parameters Value of data type any designate additional values that Plant Simulation is to write to the remaining cells in the first free row.

**Return Value**

The return value has the data type integer . It is the index of the appended row.

**Example**

MyDataTable.appendRow("My value", "My value in row 2")

**See also**

Insert Row [lists] on the Edit ribbon tab

Insert Row [context menu, lists]

###### cutEmptyRows [SimTalk]

cutEmptyRows [SimTalk]

Cuts all empty rows from the DataTable designated by &lt;Path&gt;.

Remarks

In the example below we cut the empty rows 8 to 11 and row 12 thus moves up to row 8.

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.cutEmptyRows → void

Return Value

The return value is void .

Example

MyNewDataTable.cutEmptyRows cutRow [SimTalk] - DataTable Cuts a row, including all of its data, from the DataTable designated by &lt;Path&gt;.

Remarks

You cannot cut the row index with the instruction cutRow(0) .

Type

Method

Syntax

&lt; Path &gt;.cutRow(Row:any)

Parameter

The parameter Row of data type any designates the row. Plant Simulation shifts all rows with an index equal to or greater than any one position up.

Example

MyDataTable.cutRow(8)

SimTalk

insertRow [SimTalk]

remove [SimTalk] - DataList

See also

Remove Row [context menu, lists]

Cut [Home ribbon]

getAlignmentRow [SimTalk] - DataTable

Returns the alignment of the specified row of the DataTable designated by &lt;Path&gt;.

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

```simtalk
print MyDataTable.getAlignmentRow(14)
```

SimTalk

isAlignmentRow [SimTalk] - DataTable

setAlignmentRow [SimTalk] - DataTable

See also

Alignment [cells and columns]

getBackgroundColorRow [SimTalk] - DataTable

Returns the background color of a row of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getBackgroundColorRow(Row:any) → integer

Parameter

The parameter Row of data type any designates the row whose background color you want to get.

Return Value

The return value has the data type integer .

Example

print MyDataTable.getBackgroundColorRow(14)

SimTalk

setBackgroundColorRow [SimTalk] - DataTable

See also

Background Color [cells]

getEditorRightsRow [SimTalk] - DataTable

Returns the editor rights of a row of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getEditorRightsRow(Row:any) → boolean

Parameter

The parameter Row of data type any designates the row whose background color you want to get.

Return Value

The return value has the data type boolean :

true for read-only access.

false for read and write-access.

Example

print MyDataTable.getEditorRightsRow(1)

SimTalk

setEditorRightsRow [SimTalk] - DataTable

See also

Editor [check box]

Information Flow [check box]

getFontColorRow [SimTalk] - DataTable

Returns the font color of a row of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getFontColorRow(Row:any) → integer

Parameter

The parameter Row of data type any designates the row whose font color you want to get.

Return Value

The return value has the data type integer .

Example

DataTable3.getFontColorRow(34)

SimTalk

setFontColorRow [SimTalk] - DataTable

See also

Font Color [cells]

getFontSizeRow [SimTalk] - DataTable

Returns the font size of the specified column of the DataTable designated by &lt;Path&gt;.

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
print DataTable3.getFontSizeRow(34)
```

SimTalk

setFontSizeRow [SimTalk] - DataTable

See also

Font Size [drop-down list] - cells, columns getRowNo [SimTalk]

Searches for the row which contains a user-defined row index of the DataTable designated by &lt;Path&gt;.

Remarks

If the table contains a large number of entries, you might want to activate Fast Index Access .

Type

Method

Syntax

&lt; Path &gt;.getRowNo(RowIndex:any) → integer

Parameter

The parameter RowIndex of data type any designates the row index which Plant Simulation searches for.

**Note**

The method only works for simple data types, such as string , integer , etc.

Return Value

The return value has the data type integer .

Is the row number. If the row index does not exist, Plant Simulation returns -1.

Example

MyDataTable.getRowNo("article1234")

See also

getColumnNo [SimTalk]

FastAccessColumnIndex [SimTalk]

FastAccessRowIndex [SimTalk]

###### insertRow [SimTalk]

insertRow [SimTalk]

Adds an empty row above the specified row of the DataTable designated by &lt;Path&gt;.

Remarks

Use insertRow to insert a row into an existing table, where you would like to move the existing cells down one position!

You cannot add a row if the maximum number of rows has already been reached.

Type

Method

Syntax

```simtalk
< Path >.insertRow(Above:any) → boolean
```

Parameter

The parameter Above of data type any designates the row number that contains data. Plant Simulation moves all rows with an index equal to or greater than any down one position.

Return Value

The return value has the data type boolean .

Example

MyDataTable.insertRow(8)

SimTalk

cutRow [SimTalk] - DataTable

See also

Insert Row [context menu, lists]

Insert Row [lists] on the Edit ribbon tab

###### isAlignmentRow [SimTalk] - DataTable

Returns if the alignment of a row of the DataTable designated by &lt;Path&gt; matches the designated value (true) or not (false).

Type

Method

Syntax

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
print MyDataTable.isAlignmentRow(7,"center")
```

SimTalk

getAlignmentRow [SimTalk] - DataTable

setAlignmentRow [SimTalk] - DataTable

See also

Alignment [cells and columns]

###### setAlignmentRow [SimTalk] - DataTable

setAlignmentRow [SimTalk] - DataTable

Sets the alignment of row(s) of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setAlignmentRow(Row:any[, Row:any,...], Alignment:string)
```

**Parameters**

- The parameter Row of data type any designates the row whose alignment you want to set.
- The optional parameters Row of data type any designate additional rows whose alignment you want to set.
- The parameter Alignment of data type string designates the alignment you want to set.

You can specify "Left" , "Right" , or "Centered" .

**Example**

MyDataTable.setAlignmentRow(9,10,"center")

MyDataTable.setAlignmentRow(10,"center")

SimTalk

getAlignmentRow [SimTalk] - DataTable

isAlignmentRow [SimTalk] - DataTable

See also

Alignment [cells and columns]

###### setBackgroundColorRow [SimTalk] - DataTable

Sets the background color of row(s) of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setBackgroundColorRow(Row:any[, Row:any,... , ]BackgroundColor:integer)
```

**Parameters**

- The parameter Row of data type any designates the row whose background color you want to set.
- The optional parameters Row of data type any designate additional rows whose background color you want to set.
- The parameter BackgroundColor of data type integer designates the background color.

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow , or 7 for Cyan .

You can set the RGB values of the color with the method makeRGBValue .

**Examples**

MyDataTable.setBackgroundColorRow(1,1)   // sets the background color of MyDataTable.setBackgroundColorRow(1,2,2) // sets the background color of

row 1 to black rows 1 and 2 to red

```simtalk
var rgb: integer // sets the background color of row 3
MyDataTable.setBackgroundColorRow(3,makeRGBValue(0,200,0)) // sets the background color of rows 4 and 8
MyDataTable.setBackgroundColorRow(4,8,makeRGBValue(60,100,0))
print MyDataTable.getBackgroundColorRow(3)
```

**SimTalk**

###### getBackgroundColorRow [SimTalk] - DataTable

makeRGBValue [SimTalk]

**See also**

**Background Color [cells]**

###### setEditorRightsRow [SimTalk] - DataTable

Sets the editing permissions of row(s) of the DataTable designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setEditorRightsRow(Row:any[, Row:any, ...], ReadOnly:boolean)
```

**Parameters**

- The parameters Row of data type any designate the row(s) editing permissions you want to set.
- The parameter ReadOnly of data type boolean designates read-only access ( true ) or read and write access ( false ).

**Example**

// sets the editor rights of row 1 Tab1.setEditorRightsRow(1,true) // sets the editor rights of row 3 and 5 Tab1.setEditorRightsRow(3,5,false)

**SimTalk**

Information Flow [check box]

getEditorRightsRow [SimTalk] - DataTable

See also

Editor [check box]

###### setFontColorRow [SimTalk] - DataTable

setFontColorRow [SimTalk] - DataTable

Sets the font color of row(s) of the DataTable designated by &lt;Path&gt; to the designated value.

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

// sets the font color of row 34 to magenta DataTable3.setFontColorRow(34,5) // sets the font color of row 3 and 5 to yellow DataTable3.setFontColorRow(3,5,6)

**SimTalk**

getFontColorRow [SimTalk] - DataTable

makeRGBValue [SimTalk]

See also

Font Color [cells]

###### setFontSizeRow [SimTalk] - DataTable

Sets the font size of row(s) of the DataTable designated by &lt;Path&gt; to the designated value.

Type

Method

Syntax

```simtalk
< Path >.setFontSizeRow(Row:any[, Row:any, ...], FontSize:integer)
```

**Parameters**

- The parameters Row of data type any designate the rows whose font size you want to set.
- The parameter FontSize of data type integer designates the font size.

You can specify 1 for Small , 2 for Medium , 3 for Large , or 4 for Extra Large .

**Example**

// sets the font size of row 2 to medium DataTable3.setFontSizeRow(2,2) // sets the font size of rows 3 and 5 to small DataTable3.setFontSizeRow(3,5,1)

**SimTalk**

getFontSizeRow [SimTalk] - DataTable See also Font Size [drop-down list] - cells, columns

Miscellaneous Methods of the DataTable

###### \_Miscellaneous Methods of the DataTable

The DataTable provides the methods listed in the table of contents to the left for miscellaneous purposes.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### calculateList [SimTalk]

Recomputes formulas of the DataTable designated by &lt;Path&gt; and shows their current values in the respective cells.

Type

Method

Syntax

&lt; Path &gt;.calculateList([Range:listrange])

Parameter

The parameter Range of data type listrange designates the range of cells for which the formulas are computed.

Example

MyDataTable.calculateList({2,*},{3,3}) // computes column 2, cell 3,3

See also

Recompute Formulas

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**copyFilteredTableTo [SimTalk]**

###### copyFilteredTableTo [SimTalk]

Copies all rows of the source table designated by &lt;Path&gt; into the target table for which the Condition returns true.

**Remarks**

copyFilteredTableTo also copies the column index if you defined it.

Type

Method

Syntax

```simtalk
< Path >.copyFilteredTableTo(TargetTable:table, Condition:string)
```

**Parameters**

- The parameter TargetTable of data type table designates the target table into which the rows of the source table will be copied.
- The parameter Condition of data type string designates the condition.

Within the condition the anonymous identifier @ references the DataTable and the variable ySelf contains the row number of the row that is to be copied.

If the Condition returns true, the row of the source table is going to be copied to the target table.

**Example**

DataTable.copyFilteredTableTo(DataTable1, "@[2, ySelf] = 3")

###### copyRangeTo [SimTalk]

Copies the designated range of the source table designated by &lt;Path&gt; into the target table.

Type

Method

Syntax

< Path >.copyRangeTo(SourceRange:listrange, TargetTable:any, TargetColumn:any, TargetRow:any)

**Parameters**

- The parameter SourceRange of data type listrange designates the range to be copied.
- The parameter TargetTable of data type any designates the target table.
- The parameter TargetColumn of data type any designates the column in the target table, where Plant Simulation inserts the copied range.
- The parameter TargetRow of data type any designates the row in the target table, where Plant Simulation inserts the copied range.

**Example**

```simtalk
tableA.copyRangeTo({2,2}..{*,*}, tableB, 1,1)
```

Depending if Column index belongs to contents is active or not, the range has different effects on the method copyRangeTo of the DataTable .

```simtalk
tableA.copyRangeTo({2,*}, tableB, 1,1)
```

- If tableA has a column index and the column index belongs to the contents, the entire contents of column 2 is copied to the designated target DataTable , including the column index.
- If tableB has a column index and the column index does not belong to the contents, only the contents of the column is copied, excluding the column index.

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**Column Index Belongs to Contents**

###### determineRange [SimTalk] - DataTable

Resolves the actual list range for the DataTable designated by &lt;Path&gt;.

Remarks

The method determineRange assigns the boundaries of the list range to these variables, which you define.

Type

Method

Syntax

```simtalk
< Path >.determineRange(Range:listrange, byRef StartColumn:integer, byRef StartRow:integer, byRef EndColumn:integer, byRef EndRow:integer)
```

**Local Variables**

- The parameter Range of data type listrange designates the range of the DataTable .
- The local variable StartColumn of data type integer designates the number of the first column.
- The local variable StartRow of data type integer designates the number of the first row.
- The local variable EndColumn of data type integer designates the number of the last column.
- The local variable EndRow of data type integer designates the number of the last row.

**Example**

```simtalk
param a: any
var fromX, fromY, toX, toY: integer
if isListRange(a)
	MyDataTable.determineRange(a, fromX, fromY, toX, toY)
	print "{",fromX,",",fromY,"}..{",toX,",",toY,"}"
end // You can call this method like this: myMethod({2,3}) myMethod({1,1}..{2,*}) // range with a user-defined column/row index myMethod({#7,"abc"}..{#8,*})
```

**See also**

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### getCommonFormatData [SimTalk] - DataTable

Gets format data of the column of data type list/table of the DataTable designated by &lt;Path&gt; for which you activated common format and writes it to the target table.

Type

Method

Syntax

```simtalk
< Path >.getCommonFormatData(TargetTable:table[, Column:any]) < Path >.getCommonFormatData(TargetList:list[, Column:any])
```

**Parameters**

- The parameter TargetTable of data type table designates the target table.

The parameter TargetList of data type list designates the target list.

- The optional parameter Column of data type any designates the column of the table designated by &lt;Path&gt;. The column has to be of data type list/table and common format has to be activated. If you do not specify this parameter, the common format data will be set for the first column.

**Example**

SourceTable.getCommonFormatData(DataTable,4)

**SimTalk**

setCommonFormatData [SimTalk] - DataTable

getCommonFormat [SimTalk]

setCommonFormat [SimTalk]

See also

Common Format [check box]

###### getFormula [SimTalk]

getFormula [SimTalk]

Returns the formula located in the specified cell of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getFormula(Column:any, Row:any) → string
```

Parameters

- The parameter Column of data type any designates the column of the cell.
- The parameter Row of data type any designates the row of the cell.

Return Value

The return value has the data type string .

Example

MyDataTable.getFormula(16,8)

SimTalk

setFormula [SimTalk]

See also

Create Formula

Calculate Values with a Formula

###### initialize [SimTalk]

Initializes the cells within the designated range in the DataTable designated by &lt;Path&gt; with the designated value.

**Remarks**

Plant Simulation overwrites any existing data.

**Note**

If the designated range contains the index and the content, Plant Simulation only initializes the content.

Type

Method

Syntax

< Path >.initialize([Range:listrange, ..., ]Value:any)

**Parameters**

- The parameter Range of data type listrange designates the range of cells.
- The parameter Value of data type any designates the value.

The data type of the parameter Value has to match the data types of the ranges of cells that are to be initialized.

**Example**

MyDataTable.initialize({1,0}..{5,*},{7,*},5) MyDataTable.initialize({*,*},"Empty")

**See also**

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### mergeTable [SimTalk]

Copies the columns of the source table to the target table designated by &lt;Path&gt;.

Remarks

The method mergeTable uses the row index to correctly assign the rows. For this reason both DataTables have to have a row index otherwise the method will not copy anything.

The method searches for the index of each row in the source table in the target table. If it exists, it adds the column values of the source table to the target table.

If the source table contains a great number of rows, we recommend activating Fast Index Access as all index entries of the target table have to be found in the source table.

Type

Method

Syntax

&lt; Path &gt;.mergeTable(SourceTable:table)

Parameters

The parameter SourceTable of data type table designates the source table whose rows will be copied to the target table.

Example

TargetTable.mergeTable(SourceTable)

Compare this example.

<!-- image -->

Our merged table looks like this:

<!-- image -->

**See also**

Fast Index Access [rows]

setCommonFormatData [SimTalk] - DataTable

Sets the common format data for the subtables contained in columns of data type list/table of the target DataTable designated by &lt;Path&gt; for which you activated Common Format for the specified column.

**Remarks**

If you activated Common Format for a column, assigning a subtable to a table cell creates a copy of the assigned table. Otherwise Plant Simulation enters a reference to the assigned table. The reason for this is that it does not make sense to enter a reference if Common Format is active as the assigned table should not be subject to the common format.

setCommonFormatData applies to the DataTable and the TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.setCommonFormatData(FormatData:table[, Column:any]) < Path >.setCommonFormatData(FormatData:list[, Column:any])
```

**Parameters**

- The parameter FormatData of data type table designates the table which contains the desired formatting for the subtables.

The parameter FormatData of data type list designates the list which contains the desired formatting for the sublists.

- The optional parameter Column of data type any designates the column of the table designated by &lt;Path&gt;. The column has to be of data type list/table and Common Format has to be activated. If you do not specify this parameter, the common format data will be set for the first column.

**Example**

MyTargetTable.setCommonFormatData(DataTable,2)

SimTalk

getCommonFormatData [SimTalk] - DataTable

setCommonFormatData [SimTalk] - lists

**See also**

**Common Format [check box]**

**setCursor [SimTalk] - DataTable**

###### setCursor [SimTalk] - DataTable

Sets the internal cursors of the DataTable designated by &lt;Path&gt; to the designated cell.

Remarks

The method fi nd starts searching from the current cursor position and sets the cursor to the next found item.

The methods max and min set the cursor to the maximum or minimum value of the given range.

Type

Method

Syntax

```simtalk
< Path >.setCursor(Column:any, Row:any) → boolean
```

**Parameters**

- The parameter Column of data type any designates the column, i.e., the internal cursor CursorX .
- The parameter Row of data type any designates the row, i.e., the internal cursor CursorY .

Return Value

The return value has the data type boolean .

true tells that the cursors were set to the desired position.

Examples

MyDataTable.setCursor(1,1)

MyDataTable.setCursor(1, "Test") // returns false if the index named Test does not exist

SimTalk

CursorX [SimTalk]

CursorY [SimTalk]

find [SimTalk] - lists max [SimTalk] - lists min [SimTalk] - lists

**setFormula [SimTalk]**

###### setFormula [SimTalk]

Enters the formula into the table cell(s) of the designated range of the DataTable designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setFormula([Range:listrange, ..., ]Formula:string)
```

**Parameters**

- The optional parameter Range of data type any designates the range of cells for which you want to set a formula. You can also enter several ranges.
- The parameter Formula of data type string designates the formula.

**Example**

```simtalk
// 'myFormula' is a method whose
return value is the result of the formula
MyDataTable.setFormula({1,2}..{2,3},"myFormula") // column 3 results from the difference of column 1 and column 2
MyDataTable.setFormula({3,1}..{3,*}, "@[1,yself] - @[2,yself]")
```

SimTalk

getFormula [SimTalk]

See also

Create Formula

Calculate Values with a Formula

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**Methods for Accessing the DataTable**

##### \_Methods for Accessing the DataTable

The DataTable provides the methods listed in the table of contents to the left for accessing it.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**[ , ] [SimTalk] - read cell contents, DataTable**

###### [ , ] [SimTalk] - read cell contents, DataTable

Returns the data of the designated cell of the DataTable designated by &lt;Path&gt;.

Remarks

**Note**

If you use a string as the column/row index, the string is case-insensitive, for example when you print it with the method DataTable["my text", "aa bb"] .

If the table contains numerous entries, you might want to activate Fast Index Access .

Type

Method

Syntax

```simtalk
< Path >[Column:integer or string, Row:integer or string] → contents of the cell
```

**Parameters**

- The optional parameter Column of data type integer or string designates the column.
- The optional parameter Row of data type integer or string designates the row.

Return Value

The return value is the contents of the cell.

Is a zero value if the cell is empty.

0 for numerical data types.

false for the data types Boolean .

The empty string "" for strings .

void for the data types object , table , list , stack , and queue .

**Note**

Plant Simulation reads the contents of the cell, but does not remove it.

**Example**

```simtalk
print MyDataTable[1,2]
print MyDataTable["Value",2]
```

**[ , ] [SimTalk] - write cell contents, DataTable**

###### [ , ] [SimTalk] - write cell contents, DataTable

Writes data to the DataTable designated by &lt;Path&gt;.

Remarks

First you access the cell by its index and then you assign a value. The index statement begins and ends with a bracket. In the bracket you first enter the column and then the row of the cell to be accessed. You can use the system index or a user-defined index which you assigned.

The data type of the new value has to be the same as the data type of the table cell.

Type

Method

Syntax

```simtalk
< Path >[Column:integer or string, Row:integer or string]
```

**Parameters**

- The optional parameter Column of data type integer or string designates the column of the cell.
- The optional parameter Row of data type integer or string designates the row of the cell.

**Example**

```simtalk
MyDataTable[2,3] := 12.34                // system index orderList["OrderNo","Miller"] := 12.34   // user-defined index
```

**deleteContents [SimTalk]**

Deletes the contents of the DataTable designated by &lt;Path&gt;.

Remarks

The contents also includes the row index. If you also activated Settings &gt; Column Index Belongs to Contents in the format of the DataTable , the column index will be deleted as well.

Type

Method

Syntax

&lt; Path &gt;.deleteContents

Example

MyDataTable.deleteContents

See also

delete [SimTalk] - lists

deleteCellFormat [SimTalk]

Column Index Belongs to Contents

###### writeRow [SimTalk]

writeRow [SimTalk]

Writes data to the DataTable designated by &lt;Path&gt; at the designated position.

Remarks

Plant Simulation replaces any data that may be located in the designated cells.

Type

Method

Syntax

< Path >.writeRow(Column:any, Row:any, Value:any[, Value:any, ..., Value:any])

**Parameters**

- The parameter Column of data type any designates the column of the table.
- The parameter Row of data type any designates the row of the table.
- The parameter Value of data type any designates the value(s) to be written.

**Examples**

```simtalk
var servicesTable : table[string,integer,string]
Station.imp.getServices(servicesTable)
servicesTable.delete
switch
	@.Name
case "PartA"
	servicesTable.writeRow(1,1, "ServiceA",2)
case "PartB"
	servicesTable.writeRow(1,1, "ServiceB",1)
case "PartC"
	servicesTable.writeRow(1,1, "ServiceA",1)
	servicesTable.writeRow(1,2, "ServiceB",1)
end
Station.imp.setServices(servicesTable)
end
```

MyDataTable.writeRow(1,2,"Smith")

##### Methods for Instantiating the DataTable

###### \_Methods for Instantiating the DataTable

The DataTable provides the methods create [SimTalk] - DataTable and createNestedList [SimTalk] DataTable for instantiating it.

Remember that a local variable of data type table does not contain the data itself, but only a reference to the corresponding data structure. When the variables are entered into a Method object, they are void , i.e., they do not contain a reference to a data structure yet. You have to create the variable, before you can access the data.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**create [SimTalk] - DataTable**

create [SimTalk] - DataTable

Creates a data structure without contents in the local variable designated by &lt;var&gt;.

Remarks

The method create only applies to a local variable of data type table .

Type

Method

Syntax

```simtalk
<
var >.create
```

**Example**

```simtalk
var OrderList : table[string,real]
OrderList.create
OrderList[1,1] := "Cans"
OrderList[2,1] := 3000.0
```

See also

Data Types in Local Variables

###### createNestedList [SimTalk] - DataTable

Creates a nested list in the designated cell in the DataTable designated by &lt;Path&gt;.

Remarks

The data type of the columns of this DataTable has to be list, stack, queue , or table .

Type

Method

Syntax

&lt; Path &gt;.createNestedList(Column:any, Row:any[, Name:string]) → list

**Parameters**

- The parameter Column of data type any designates the column of the cell.
- The parameter Row of data type any designates the row of the cell.
- The optional parameter Name of data type string designates the name of the subtable to be created.

**Return Value**

The return value has the data type list .

Is the nested list ( DataList , DataQueue , DataStack , or DataTable ) that was created.

**Example**

MyDataTable.createNestedList(1,2,"My subtable")

**See also**

setCommonFormatData [SimTalk] - DataTable

getCommonFormatData [SimTalk] - DataTable

Activating and Deactivating Common Format

Creating Lists within Lists and Tables

createNestedList [SimTalk] - DataQueue createNestedList [SimTalk] - DataList createNestedList [SimTalk] - local variable of data type list or table

#### Read-Only Attributes of the DataTable

\_Read-Only Attributes of the DataTable

The DataTable provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyDataTable.Full
```

**XDim [SimTalk] - DataTable**

Returns the number of the last column of the DataTable designated by &lt;Path&gt; that contains an entry.

Remarks

Plant Simulation does not count the user-defined index.

Type

Read-only attribute

Syntax

```simtalk
< Path >.XDim
-> integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print MyDataTable.XDim
print timeSequence.XDim
```

See also

YDim [SimTalk] - DataTable XDimIndex [SimTalk]

Returns the last cell of the column index of the DataTable designated by &lt;Path&gt; that contains an entry.

Remarks

Plant Simulation does not count column 0.

Type

Read-only attribute

Syntax

&lt; Path &gt;.XDimIndex -&gt; integer

Return Value

The return value has the data type integer .

Example

print MyDataTable.XDimIndex

SimTalk

YDimIndex [SimTalk]

ColumnIndex [SimTalk]

See also

Number of Columns [lists]

##### YDim [SimTalk] - DataTable

Returns the number of the last row of the DataTable designated by &lt;Path&gt; that contains an entry.

Remarks

Plant Simulation does not count the user-defined index.

Type

Read-only attribute

Syntax

```simtalk
< Path >.YDim
-> integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print MyDataTable.YDim
print timeSequence.YDim
```

SimTalk

XDim [SimTalk] - DataTable

##### YDimIndex [SimTalk]

YDimIndex [SimTalk]

Returns the last cell of the row index of the DataTable designated by &lt;Path&gt; that contains an entry.

Type

Read-only attribute

Syntax

&lt; Path &gt;.YDimIndex -&gt; integer

Return Value

The return value has the data type integer .

Example

print MyDataTable.YDimIndex

SimTalk

XDimIndex [SimTalk]

RowIndex [SimTalk]

See also

Number of Rows [lists]

**Attributes of the DataTable**

\_Attributes of the DataTable

The DataTable provides:

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
MyDataTable.ColumnIndex := false
MyDataTable.calculateList({1,3}..{2,4})
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

##### Alignment [SimTalk] - DataTable

Alignment [SimTalk] - DataTable

Sets the alignment of all cells of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Alignment:string
```

Assignment Value

You can assign a value of data type string .

You can specify "left" , "right" , or "center" .

Example

```simtalk
MyDataTable.Alignment := "left"
```

See also

Alignment [cells and columns]

##### Changed [SimTalk]

Is set to true if the contents of the DataTable designated by &lt;Path&gt; changed.

Remarks

You can reset the attribute to false at any time to detect a change at a later point in time.

Type

Attribute

Syntax

&lt; Path &gt;.Changed:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
while true
	MyDataTable.Changed := false
	stopuntil MyDataTable.Changed
	print "Contents of the table has changed."
	print "New sum of all values: ", MyDataTable.sum"
end
```

**ColumnIndex [SimTalk]**

##### ColumnIndex [SimTalk]

Activates ( true ) or deactivates ( false ) the user-defined column index of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.ColumnIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataTable.ColumnIndex := true
```

See also

Activate Column Index

ShowColumnIndex [SimTalk] - DataTable

###### ColumnIndexContents [SimTalk]

Makes the column index belong to the contents of the DataTable designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

Then the column index is inherited together with the contents of the DataTable if Inherit Contents is active.

If you enter false , the column index belongs to the format of the DataTable . Then the column index is inherited together with the format of the DataTable when Inherit Format is active.

Type

Attribute

Syntax

&lt; Path &gt;.ColumnIndexContents:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataTable.ColumnIndexContents := true

See also

Column Index Belongs to Contents

Inherit Contents [lists]

Inherit Format [button]

##### CommonFormatColumnIndex [SimTalk]

Activates the common format for the column index of the DataTable designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Remarks

This applies if the column index is of data type table , list , stack or queue .

If you activated Common Format for a column, assigning a subtable to a table cell creates a copy of the assigned table. Otherwise Plant Simulation enters a reference to the assigned table. The reason for this is that it does not make sense to enter a reference if Common Format is active as the assigned table should not be subject to the common format.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.CommonFormatColumnIndex:boolean

**Assignment Value**

You can assign a value of data type boolean .

<!-- image -->

**Example**

MyDataTable.CommonFormatColumnIndex := true

SimTalk

setCommonFormat [SimTalk]

getCommonFormat [SimTalk]

CommonFormatColumnIndex [SimTalk]

getCommonFormatData [SimTalk] - DataTable

setCommonFormatData [SimTalk] - DataTable

See also

Common Format [check box]

Tab Contents

**CursorX [SimTalk]**

##### CursorX [SimTalk]

Sets the column in which the internal cursor of the DataTable designated by &lt;Path&gt; is located.

Remarks

The method fi nd starts searching from the current cursor position and sets the cursor to the next found item.

The methods max and min set the cursor to the maximum or minimum value of the given range.

Plant Simulation ignores ranges located before the current cursor position. The Method starts its task beginning at the cursor position. If a Method does not return the expected values, check the cursor position. The first row has the number 1. If you also want to include the user-defined index, set the attribute CursorX to 0.

**Note**

This attribute applies to the DataTable and the TimeSequence .

**Note**

You can also set the pointer by using a user-defined index. For a user-defined index of data type integer , use the method setCursor !

Type

Attribute

Syntax

```simtalk
< Path >.CursorX:integer
```

Assignment Value

You can assign a value of data type integer .

**Example**

```simtalk
MyDataTable.CursorX := 1 // starting position
MyDataTable.CursorY := 1 // set
if MyDataTable.find({1,*},4712)
	print "found in row:", MyDataTable.CursorY
end
```

SimTalk setCursor [SimTalk] - DataTable CursorY [SimTalk] find [SimTalk] - lists findCeil [SimTalk] findFloor [SimTalk] findAttr [SimTalk] min [SimTalk] - lists max [SimTalk] - lists

**CursorY [SimTalk]**

##### CursorY [SimTalk]

Sets the row in which the internal cursor of the DataTable designated by &lt;Path&gt; is located.

Remarks

The method fi nd starts searching from the current cursor position and sets the cursor to the next found item.

The methods max and min set the cursor to the maximum or minimum value of the given range.

Plant Simulation ignores ranges located before the current cursor position. The Method starts its task beginning at the cursor position. If a Method does not return the expected values, check the cursor position. The first column has the number 1. If you also want to include the user-defined index, set the attribute CursorY to 0.

**Note**

This attribute applies to the DataTable and the TimeSequence .

Attribute

Type

Attribute

Syntax

```simtalk
< Path >.CursorY:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDataTable.CursorX := 1 // starting position
MyDataTable.CursorY := 1 // set
if MyDataTable.find({1,*},4712)
	print "found in row:", MyDataTable.CursorY
end
```

**Note**

You can also set the pointer by employing a user-defined index. For a user-defined index of data type integer , use the method setCursor !

```simtalk
MyDataTable.CursorY := "urgent" // user-defined index
MyDataTable.CursorX := 3.1415
```

**SimTalk**

setCursor [SimTalk] - DataTable

CursorX [SimTalk]

find [SimTalk] - lists

findCeil [SimTalk]

findFloor [SimTalk]

findAttr [SimTalk]

min [SimTalk] - lists

max [SimTalk] - lists

###### DataType [SimTalk] - DataTable

Sets the default data type of the DataTable designated by &lt;Path&gt; to the value designated by the value you enter as a string .

Type

Attribute

Syntax

&lt; Path &gt;.DataType:string

**Assignment Value**

You can assign a value of data type string .

| Data type    | Description                                                                                          |
|--------------|------------------------------------------------------------------------------------------------------|
| Acceleration | applies for the objects Conveyor , Track , TwoLaneTrack , and Transporter , meter per second squared |
| Boolean      | true or false                                                                                        |
| Date         | date statement ( dd.MM.yyyy )                                                                        |
| DateTime     | date statement, including the time ( dd.MM.yyyy HH:mm:ss )                                           |
| Integer      | integer value                                                                                        |
| Length       | floating point number, value depends on the unit of the length                                       |
| List         | list with one column, shares properties of the DataList                                              |
| Money        | floating point numbers                                                                               |
| Object       | reference to a simulation model or an object                                                         |
| Queue        | list with one column, shares properties of the DataQueue                                             |
| Real         | floating point number, such as 3.1415                                                                |
| Speed        | floating point number, value depends on the unit for speed                                           |
| Stack        | list with one column, shares properties of the DataStack                                             |
| String       | characters, numbers and special characters                                                           |
| Table        | table with one or more columns, shares properties of the DataTable                                   |

| Data type   | Description                                                    |
|-------------|----------------------------------------------------------------|
| Time        | time statement (hh:mm:ss.ss)                                   |
| Weight      | floating point number, value depends on the unit of the weight |

**Example**

```simtalk
MyDataTable.DataType := "real"
```

**See also**

Data Type [lists]

##### DataTypeColumnIndex [SimTalk]

Sets the data type of the user-defined column index of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.DataTypeColumnIndex:string

Assignment Value

You can assign a value of data type string .

| Data type    | Description                                                                                          |
|--------------|------------------------------------------------------------------------------------------------------|
| Acceleration | applies for the objects Conveyor , Track , TwoLaneTrack , and Transporter , meter per second squared |
| Boolean      | true or false                                                                                        |
| Date         | date statement ( dd.MM.yyyy )                                                                        |
| DateTime     | date statement, including the time ( dd.MM.yyyy HH:mm:ss )                                           |
| Integer      | integer value                                                                                        |
| Length       | floating point number, value depends on the unit of the length                                       |
| List         | list with one column, shares properties of the DataList                                              |
| Money        | floating point numbers                                                                               |
| Object       | reference to a simulation model or an object                                                         |
| Queue        | list with one column, shares properties of the DataQueue                                             |
| Real         | floating point number, such as 3.1415                                                                |
| Speed        | floating point number, value depends on the unit for speed                                           |
| Stack        | list with one column, shares properties of the DataStack                                             |
| String       | characters, numbers and special characters                                                           |
| Table        | table with one or more columns, shares properties of the DataTable                                   |
| Time         | time statement (hh:mm:ss.ss)                                                                         |
| Weight       | floating point number, value depends on the unit of the weight                                       |

**Example**

MyDataTable.DataTypeColumnIndex := "queue"

See also

Data Type [lists]

##### FastAccessColumnIndex [SimTalk]

Uses the faster access to the user-defined column index ( true ) or not ( false ) for the DataTable designated by &lt;Path&gt;.

Remarks

The more columns and rows your table has, the more you benefit from the improved access speed.

Type

Attribute

Syntax

&lt; Path &gt;.FastAccessColumnIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataTable.FastAccessColumnIndex := true
```

See also

Fast Index Access [columns]

getColumnNo [SimTalk]

UniqueKeyColumnIndex [SimTalk]

##### FastAccessRowIndex [SimTalk]

Uses the faster access to the user-defined row index ( true ) or not ( false ) for the DataTable designated by &lt;Path&gt;.

Remarks

The more columns and rows your table has, the more you benefit from the improved access speed.

Type

Attribute

Syntax

&lt; Path &gt;.FastAccessRowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataTable.FastRowColumnIndex := true
```

See also

Fast Index Access [rows]

getRowNo [SimTalk]

UniqueKeyRowIndex [SimTalk]

FormatString [SimTalk] - DataTable

FormatString [SimTalk] - DataTable

Sets the format string of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.FormatString:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDataTable.FormatString := "-9"
```

See also

Format String [text box]

##### FormatStringColumnIndex [SimTalk]

Sets, depending on the data type, the Format String of the column index of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.FormatStringColumnIndex:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDataTable.FormatString := "3.3"
```

See also

Format String [text box]

FormatStringRowIndex [SimTalk]

Sets, depending on the data type, the Format String of the row index of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.FormatStringRowIndex:string

Assignment Value

You can assign a value of data type string .

Example

MyDataTable.FormatStringRowIndex := "-2.3"

See also

Format String [text box]

##### MaxXDim [SimTalk]

Sets the maximum number of columns of the DataTable designated by &lt;Path&gt;.

Remarks

MaxXDim applies to the DataTable and to the TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.MaxXDim:integer
```

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite size.

Example

```simtalk
MyDataTable.MaxXDim := 10   // 10 columns
DataTable1.MaxXDim := -1    // unlimited
```

See also

Number of Columns [lists]

**MaxYDim [SimTalk]**

##### MaxYDim [SimTalk]

Sets the maximum number of rows of the DataTable designated by &lt;Path&gt;.

Remarks

MaxYDim applies to the DataTable and the TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.MaxYDim:integer
```

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite size.

Example

```simtalk
MyDataTable.MaxYDim := 50 // 50 rows
DataTable1.MaxYDim := -1  // unlimited
```

See also

Number of Rows [lists]

##### Name [SimTalk] - DataTable

Sets the name of the DataTable designated by &lt;Path&gt; to the designated expression.

Remarks

You can use the attribute Name to access the name of the sublist via information flow.

Type

Attribute

Syntax

```simtalk
< Path >.Name:string
```

Assignment Value

You can assign a value of data type string .

Examples

```simtalk
DataTable.createNestedList(1, 1) DataTable[1,1].Name := "MyName"
var str : string
str := .Models.MyPlantAnytown.SteeringTypes["Jacks","9149"].Name // returns the value of the cell that contains the subtable, 4 in the example
```

See also

Cut [Home ribbon]

Accessing the Name of a Sublist with a Method

**RowIndex [SimTalk]**

##### RowIndex [SimTalk]

Activates ( true ) or deactivates ( false ) the user-defined row index of the DataTable designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.RowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataTable.RowIndex := false

SimTalk

RowIndex [SimTalk]

See also

Activate Row Index ShowColumnIndex [SimTalk] - DataTable Shows the column index of the DataTable designated by &lt;Path&gt; ( true ) or hides it ( false ).

Remarks

You can activate or deactivate the column index with the attribute ColumnIndex .

Type

Attribute

Syntax

&lt; Path &gt;.ShowColumnIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataTable.ShowColumnIndex := false

SimTalk

ColumnIndex [SimTalk]

See also

Activate Column Index ShowRowIndex [SimTalk] - DataTable Shows the row index ( true ) of the DataTable designated by &lt;Path&gt; or hides it ( false ).

Remarks

You can activate or deactivate the row index with the attribute RowIndex .

Type

Attribute

Syntax

&lt; Path &gt;.ShowRowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataTable.ShowRowIndex := true

SimTalk

RowIndex [SimTalk]

See also

Activate Row Index

##### UniqueKeyColumnIndex [SimTalk]

Applies a unique key to the user-defined column index ( true ) to the DataTable designated by &lt;Path&gt; or not ( false ).

Remarks

UniqueKeyColumnIndex only works while you manually edit a DataTable . It does not work when writing to an index using a Method . Plant Simulation does not detect multiple entries via information flow.

Type

Attribute

Assignment Value

You can assign a value of data type boolean .

Syntax

&lt; Path &gt;.UniqueKeyColumnIndex:boolean

Example

Tab.UniqueKeyColumnIndex := true

See also

Unique Index Key [columns]

##### UniqueKeyRowIndex [SimTalk]

Applies a unique key to the user-defined row index ( true ) to the DataTable designated by &lt;Path&gt; or not ( false ).

Remarks

UniqueKeyRowIndex only works while you manually edit a DataTable . It does not work when writing to an index using a Method . Plant Simulation does not detect multiple entries via information flow.

Type

Attribute

Syntax

&lt; Path &gt;.UniqueKeyRowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

tab2.UniqueKeyRowIndex := false

See also

Unique Index Key [rows]

#### DataList

