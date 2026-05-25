#### Attributes of Lists and Tables

Attributes of Lists and Tables

All manifestations of lists and tables, DataStack , DataQueue , DataList , DataTable , and TimeSequence , share a number of predefined attributes controlling their behavior or representing their state.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

**See also**

- \_Attributes for the Format of Lists and Tables
- \_Attributes for the Text Format of Lists and Tables
- \_Attributes for Printing Lists and Tables
- \_Attributes for Showing Settings of Lists and Tables
- \_Miscellaneous Attributes of Lists and Tables

##### Attributes for the Format of Lists and Tables

##### \_Attributes for the Format of Lists and Tables

Lists and tables provide the attributes listed in the table of contents to the left for setting the format of the entire list or table.

In the dialog of the objects, you can select these settings on the List ribbon tab &gt; Edit Format .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

##### Alignment [SimTalk] - lists

Alignment [SimTalk] - lists

Sets the alignment of all cells of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

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
MyDataQueue.Alignment := "left"
print MyDataQueue.Alignment
```

See also

Alignment [cells and columns]

###### BackgroundColor [SimTalk] - lists

Sets the background color for all cells of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.BackgroundColor:integer

Assignment Value

You can assign a value of data type integer .

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow , and 7 for Cyan .

Or set the RGB values of the color with the method makeRGBValue .

Example

```simtalk
var rgb: integer
MyDataTable.BackgroundColor := makeRGBValue(120,120,120)
rgb := MyDataTable.BackgroundColor
print rgb
```

SimTalk

makeRGBValue [SimTalk]

See also

Background Color [cells]

**ColumnWidth [SimTalk]**

###### ColumnWidth [SimTalk]

Sets the column width in character widths of a non-proportional font of all cells of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.ColumnWidth:integer

Assignment Value

You can assign a value of data type integer .

Specify a value between 20 for the default setting, and 180 for the maximum column width.

Example

```simtalk
MyDataQueue.ColumnWidth := 10
```

**See also**

Column Width [text box]

DataType [SimTalk] - lists

Sets the data type of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.DataType:string

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

| Data type   | Description                                                        |
|-------------|--------------------------------------------------------------------|
| Table       | table with one or more columns, shares properties of the DataTable |
| Time        | time statement (hh:mm:ss.ss)                                       |
| Weight      | floating point number, value depends on the unit of the weight     |

**Example**

```simtalk
MyDataList.DataType := "integer"
```

**See also**

Data Type [lists]

###### EditorReadOnly [SimTalk]

Sets if you have read-only permissions to the list/table designated by &lt;Path&gt; ( true ) or if you can also edit it ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.EditorReadOnly:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataStack.EditorReadOnly := false

See also

Editor [check box]

Information Flow [check box]

**FontColor [SimTalk]**

###### FontColor [SimTalk]

Sets the font color used for displaying the data in the cells of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.FontColor:integer

Assignment Value

You can assign a value of data type integer .

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow , and 7 for Cyan .

Or set the RGB values of the color with the method makeRGBValue .

Example

MyDataTable.FontColor := 2

**SimTalk**

makeRGBValue [SimTalk]

setFontColorCells [SimTalk]

setFontColorColumn [SimTalk] - DataTable

getFontColorColumn [SimTalk] - DataTable

setFontColorRow [SimTalk] - DataTable

getFontColorRow [SimTalk] - DataTable

**See also**

**Font Color [cells]**

###### FontSize [SimTalk] - DataTable

FontSize [SimTalk] - DataTable

Sets the font size used for displaying the data in the cells of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.FontSize:integer
```

Assignment Value

You can assign a value of data type integer .

You can specify 1 for Small , 2 for Medium , 3 for Large , and 4 for Extra Large .

Example

```simtalk
MyDataTable.FontSize := 2
```

See also

Font Size [drop-down list] - cells, columns FormatString [SimTalk] - lists Sets, depending on the data type, the format string of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.FormatString:string

Assignment Value

You can assign a value of data type string .

Example

MyDataQueue.FormatString := "5.3"

See also

Format String [text box]

###### InfoflowReadOnly [SimTalk]

Sets if you can only read the list or table via methods ( true ) or if methods may also write to the list/table designated by &lt;Path&gt; ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.InfoflowReadOnly:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataStack.InfoflowReadOnly := true
```

See also

Information Flow [check box]

Attributes for the Text Format of Lists and Tables

\_Attributes for the Text Format of Lists and Tables

Lists and tables provide the attributes listed in the table of contents to the left for working with them in text format.

In the dialog of the objects, you can select these settings under Export &gt; Text File Format on the List ribbon tab.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

###### ColumnSeparator [SimTalk]

Sets the separator between columns when saving the list/table designated by &lt;Path&gt; in text format.

Remarks

**Note**

We strongly advise against using the comma (,) as decimal separator as well as as column separator. Only use it either as decimal separator or as column separator.

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.ColumnSeparator:string
```

**Assignment Value**

You can assign a value of data type string .

You can specify Tab , a blank Space , , (comma), or ; (semicolon).

Example

```simtalk
MyDataQueue.ColumnSeparator := " "
```

See also

Text File Format

###### DecimalSeparator [SimTalk]

Sets the decimal separator, when saving the list/table designated by &lt;Path&gt; in text format.

Remarks

**Note**

We strongly advise against using the comma (,) as decimal separator as well as as column separator. Only use it either as decimal separator or as column separator.

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.DecimalSeparator:string
```

**Assignment Value**

You can assign a value of data type string : "." (period) or "," (comma).

Example

```simtalk
MyDataStack.DecimalSeparator := "," // comma
```

See also

Text File Format

###### TimeFormat [SimTalk]

TimeFormat [SimTalk]

Sets the time format when saving the list/table designated by &lt;Path&gt; in text format.

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

```simtalk
< Path >.TimeFormat:string
```

Assignment Value

You can assign a value of data type string .

You can specify "D:H:M:S" , "H:M:S" , "M:S" , or "S" .

Example

```simtalk
MyDataList.TimeFormat := "M:S"
```

See also

Text File Format

Attributes for Printing Lists and Tables

\_Attributes for Printing Lists and Tables

Lists and tables provide the attributes listed in the table of contents to the left for printing their contents.

In the dialog of the objects, you can select these settings by clicking Print &gt; Print Setup on the List ribbon tab.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

###### GenerateColumnWidth [SimTalk]

Uses the widest column of the list when printing the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.GenerateColumnWidth:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataQueue.GenerateColumnWidth := true

See also

Print Setup

###### PrintColumnNumber [SimTalk]

Prints the column number of the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.PrintColumnNumber:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataStack.PrintColumnNumber := false

See also

Print Setup

###### PrintDataType [SimTalk]

PrintDataType [SimTalk]

Prints the data type of the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.PrintDataType:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataStack.PrintDataType := false

See also

Print Setup

###### PrintInternalLists [SimTalk]

Prints nested lists located in the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.PrintInternalLists:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataStack.PrintInternalLists := false

See also

Print Setup

**PrintRowNumber [SimTalk]**

###### PrintRowNumber [SimTalk]

Prints the row number of the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.PrintRowNumber:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataStack.PrintRowNumber := false

See also

Print Setup

###### RepeatColumnIndex [SimTalk]

Prints the user-defined column index on each page of the printed list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.RepeatColumnIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataQueue.RepeatColumnIndex := false

See also

Print Setup

**RepeatRowIndex [SimTalk]**

###### RepeatRowIndex [SimTalk]

Prints the user-defined row index on each page of the printed list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.RepeatRowIndex:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataQueue.RepeatRowIndex := true
```

See also

Print Setup

Attributes for Showing Settings of Lists and Tables

\_Attributes for Showing Settings of Lists and Tables

Lists and tables provide the attributes listed in the table of contents to the left for showing and hiding their settings.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

###### ShowComment [SimTalk] - lists

ShowComment [SimTalk] - lists

Shows the comment of the list/table designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.ShowComment:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataQueue.ShowComment := true

See also

Show Comment [lists]

ShowDataType [SimTalk] - lists

Shows the data type of the list/table designated by &lt;Path&gt; ( true ) or hides it ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.ShowDataType:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataQueue.ShowDataType := false

See also

Show Data Type [lists]

**ShowVoid [SimTalk]**

###### ShowVoid [SimTalk]

Shows empty cells in the list/table designated by &lt;Path&gt; in gray ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.ShowVoid:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyDataQueue.ShowVoid := false
```

See also

Highlight Empty Cells

Miscellaneous Attributes of Lists and Tables

\_Miscellaneous Attributes of Lists and Tables

Lists and tables provide the attributes listed in the table of contents to the left for miscellaneous purposes.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataTable.MaxXDim := -1
print MyDataTable.MaxXDim
posit := Station.Cont.XPos
```

###### Comment [SimTalk] - lists

Comment [SimTalk] - lists

Sets the comment of the list/table designated by &lt;Path&gt;.

Remarks

The attribute applies to the DataTable , the DataList , the DataStack , and the DataQueue .

Type

Attribute

Syntax

```simtalk
< Path >.Comment:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDataQueue.Comment := "parts produced"
print MyDataQueue.Comment
```

SimTalk

ShowComment [SimTalk] - lists

See also

Show Comment [lists]

###### Cursor [SimTalk]

Sets the cell in the list with one column designated by &lt;Path&gt; in which the cursor is placed.

Remarks

The attribute applies to the DataList , the DataStack , and the DataQueue .

All methods that use ranges, such as fi nd or max , use the current position of the cursor. Plant Simulation ignores ranges located before the current cursor position. The method starts its task beginning at the cursor position. If a method does not return the expected values, check the cursor position.

**Note**

You can also set the cursor by using a user-defined index. Use the method setCursor when using a user-defined index of data type integer .

Type

Attribute

Syntax

```simtalk
< Path >.Cursor:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyDataStack.Cursor := 1
MyDataQueue.Cursor := 2
MyDataList.Cursor := MyDataList.Cursor + 1
```

SimTalk

CursorX [SimTalk]

CursorY [SimTalk]

setCursor [SimTalk] - lists

find [SimTalk] - lists

**Cursor [SimTalk]**

###### max [SimTalk] - lists

See also

**Search Lists with Methods**

###### InheritComment [SimTalk]

Makes the list/table designated by &lt;Path&gt; inherit its comment ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.InheritComment:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataTable.InheritComment := true

See also

Inherit Comment [button]

###### InheritContents [SimTalk]

Makes the list/table designated by &lt;Path&gt; inherit its contents from the class ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

**Note**

Plant Simulation does not deactivate Inherit Contents when you instantiate the class of a list containing a sublist, and then write to the instance with a method , or when you write to the sublist with a method . If you model like that, you have to deactivate Inherit Contents yourself in the window of the list object.

Note

User-defined attributes and local variables do not provide this attribute.

Type

Attribute

Syntax

&lt; Path &gt;.InheritContents:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDataList.InheritContents := false

See also

Inherit Contents [lists]

###### InheritFormat [SimTalk]

Makes the list/table designated by &lt;Path&gt; inherit its format from the class ( true ) or not ( false ).

Remarks

The attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Attribute

Syntax

&lt; Path &gt;.InheritFormat:boolean

**Assignment Value**

You can assign a value of data type boolean .

**Note**

User-defined attributes and local variables do not provide this attribute.

Example

MyDataStack.InheritFormat:= true

See also

Inherit Format [button]

**MaxDim [SimTalk]**

###### MaxDim [SimTalk]

Sets the maximum number of cells for a list with one column designated by &lt;Path&gt;.

Remarks

The attribute applies to the objects DataStack , DataQueue , and DataList .

Type

Attribute

Syntax

```simtalk
< Path >.MaxDim:integer
```

Assignment Value

You can assign a value of data type integer .

Specify -1 for an infinite size.

Example

```simtalk
MyDataStack.MaxDim := -1                  // unlimited dimension
MyDataQueue.MaxDim := 20                  // 20 entries
MyDataList.MaxDim := 2*MyDataList.MaxDim  // double the number of entries
```

**See also**

Number of Rows [lists]

