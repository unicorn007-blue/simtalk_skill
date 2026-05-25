#### Methods of Lists and Tables

The lists and tables share a number of methods. The different kindsDataStack , DataQueue , DataList, DataTable , and TimeSequence -in addition provide object-specific methods.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.readFile(FileName:string[, NoDebugger:boolean:=false, CodePage:string:="ANSI"]) → boolean
```

- ◦ The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type

##### Methods of Lists and Tables

string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

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
| direction               | string         | "up", "down", " "          |
| attributes              | string         | name of an attribute       |

**See also**

- \_Methods for Accessing Lists and Tables
- \_Methods for the Order of Cells within Lists and Tables
- \_Methods for the Format of Lists and Tables
- \_Methods for Querying Statistics Values of Lists and Tables
- \_Methods for Importing and Exporting Data in Text Format

Instantiating Local Lists and Tables

- \_Methods for Indirectly Accessing Lists and Tables

Methods of the DataTable

- \_Methods of the DataList
- \_Methods of DataQueue and DataStack

**Methods for Accessing Lists and Tables**

##### \_Methods for Accessing Lists and Tables

Lists and tables provide the methods listed in the table of contents to the left for accessing them.

Read and write access depend on the object class and are described in the sub-chapters.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**See also**

**\_Methods for Accessing the DataTable**

###### closeDialog [SimTalk] - lists

closeDialog [SimTalk] - lists

Closes the dialog box of the list object designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.closeDialog → boolean

Return Value

The return value has the data type boolean .

Example

MyDataTable.closeDialog MyDataList.closeDialog MyDataStack.closeDialog MyDataQueue.closeDialog MyTimeSequence.closeDialog

See also

Close Model

###### copy [SimTalk] - lists

Copies the entire list/table designated by &lt;Path&gt; and returns it as a value of data type list / table .

Remarks

The method copy(Range) copies the specified range.

If you do not enter a range, Plant Simulation copies the entire list. A range may only encompass a single range .

If you would also like to copy the column index and/or the row index during the copy process, then enter the column 0 and/or the row 0 into the range.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.copy → list or table < Path >.copy(Range:listrange) → list or table
```

Parameter

The parameter Range of data type listrange designates the range.

You can then process the copied region in a number of ways:

- Assign the copied range to a local variable of the corresponding type.

**Example**

```simtalk
var MyDataList : list[integer]
MyDataList := MyDataList1.copy({1}..{5}) ...
```

- Insert the copied range into the column of a table. The column where you paste the range has to have the same data type as the DataList .

**Example**

MyDataTable.insertList(3,1,MyDataList.copy({1}..{5}))

**copy [SimTalk] - lists**

- Make the copied range a DataList of its own. Data type is list . Therefore you can assign it to a cell in a DataList of data type list .

**Example**

MyDataList.insertList(2,tab.copy({1,1}..{1,5}))

Return Value

The return value has the data type list / table .

See also

Copy [context menu, lists]

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

###### countMatches [SimTalk]

Counts how often the designated value occurs in the designated range of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.countMatches(Value:any[, Range:any, CaseSensitive:boolean:=false]) → integer
```

**Parameters**

- The parameter Value of data type any designates the value for which the matching values are counted.
- The optional parameter Range of data type any designates the range within which the method looks for matching values. If you do not enter a range, Plant Simulation searches the entire range, i.e., the entire range {1,1}..{*,*} .
- The optional parameter CaseSensitive of data type boolean sets if the search is case-sensitive ( true ) or not ( false ). If you do not specify this parameter, the search is not case-sensitive.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type integer .

**Example**

```simtalk
print MyDataTable.countMatches("a1", {1,1}..{3,12})
```

###### delete [SimTalk] - lists

delete [SimTalk] - lists

Deletes the contents of the list object designated by &lt;Path&gt;.

Remarks

The method delete(Range) deletes the specified range of the list object.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

**Note**

You can also delete sub-tables, which inherit their contents, with the method delete . The inheritance relation causes the reference to be passed to the origin, thus deleting the contents in the origin.

Type

Method

Syntax

< Path >.delete < Path

>.delete([Range:listrange, ...])

**Parameter**

The optional parameter Range of data type listrange designates the range which you want to delete. You can also enter several ranges.

If you do not enter a parameter, i.e. no range, Plant Simulation deletes the contents of all cells without the cells of the column or row index. Therefore specifying no range, corresponds to specifying the range {1,1}..{*,*} .

If you want to delete the user-defined row index or column index of DataTables , you have to do so explicitly by entering row 0 or column 0 respectively within the range you specify.

**Example**

MyDataStack.delete                                // deletes the data range MyDataQueue.delete({2}..{4}) MyDataList.delete({1}..{5}, {8}) MyDataTable.delete({2,2}..{*,*}) MyDataTable.delete({0,1}..{0,*})                  // deletes the row index MyDataTable.delete({"ColumnB",0}..{"ColumnB",*})  // deletes the column index

SimTalk deleteCellFormat [SimTalk] deleteContents [SimTalk] See also Delete [Home ribbon] Cell Ranges in Lists with One Column Cell Ranges in Tables with Several Columns Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### insert [SimTalk] - lists

insert [SimTalk] - lists

Adds additional entries to the list objects with one column designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.insert(Row:integer, Entry:any)
```

**Parameters**

- The parameter Row of data type integer designates the number of the cell into which Plant Simulation inserts the value.

The list objects move all cells with the same or a greater index as the designated cell down one position. If the number you enter is greater than the highest position in the list objects , Plant Simulation does not place it at the position designated by integer , but adds it after the last current entry. Remember that Plant Simulation does not allow gaps between entries in a list object .

- The parameter Entry of data type any designates the value, which you want to insert.

The data type of this parameter has to be the same as the data type of the list objects .

**Example**

MyDataList.insert(2,12.24) MyDataStack.insert(3,32.34) MyDataQueue.insert(4,42.44)

**See also**

Insert [context menu, lists]

###### insertList [SimTalk]

Inserts the contents of a list into the DataTable or DataList designated by &lt;Path&gt;.

Remarks

Plant Simulation deletes existing data in a DataTable . In a DataList it moves the data to another position.

**Note**

Copying a large amount of data from one list to another with the method insertList might be slow. For objects of type DataTable we recommend to the use the method copyRangeTo instead, whose code is executed much faster.

Type

Method

Syntax

```simtalk
< Path >.insertList(Cell:integer, SourceList:any) < Path >.insertList(Column:integer, Row:integer, SourceList:any)
```

**Parameters**

- For the DataList the parameter Cell of data type integer designates the cell from which on Plant Simulation inserts the contents of the list.
- For the DataTable the parameter Column of data type integer designates the column of the cell from which on Plant Simulation inserts the contents of the list.
- For the DataTable the parameter Row of data type integer designates the row of the cell from which on Plant Simulation inserts the contents of the list.
- The parameter SourceList of data type any designates the contents of the list that is going to be inserted.

Plant Simulation deletes all existing entries in a table , but moves entries in lists to another position.

**Example**

```simtalk
var lst: list [string] lst.create           // create
lst.insert(1,"one")  // enters value
lst.insert(2,"two")
MyDataList.insertList(3,lst)
DataTable.insertList(2,2,lst)
```

**insertList [SimTalk]**

**SimTalk**

copyRangeTo [SimTalk]

###### interSection [SimTalk]

Returns those values that the ranges of the list/table designated by &lt;Path1&gt; share, i.e., where they intersect.

Remarks

Both ranges or lists/tables have to have the same data type. The return value is a list with one column containing the shared items. Values may be listed more than once.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

< Path >1.interSection(Path2:any) → list < Path >1.interSection(Range:any, Path2:any) → list < Path >1.interSection(Range:any, Range:any) → list

**Parameters**

- The parameter Range of data type any designates a range of the table.
- The parameters Path1 and Path2 of data type any designate two lists or tables.

Return Value

The return value has the data type list .

Example

// the second column of the DataTable contains the numbers 2,4, ... 40 // the third column contains the numbers 3,6, ... 60. The DataList // contains the square numbers from -10 to 10. destination.delete destination.insertList(2,1,MyDataTable.interSection(DataList)) // the second column of the DataTable destination // contains the numbers 4,9,16,36,36 destination.insertList(3,1,MyDataTable.interSection({2,1}..{3,2},DataList)) // the third column of the DataTable destination contains 4 dest.insertList(4,1,MyDataTable.interSection (2,1}..{2,*},{3,1}..{3,*})) // the fourth column of the DataTable // destination contains the numbers 6,12,18,24,30,36

###### openDialog [SimTalk] - lists

openDialog [SimTalk] - lists

Opens the window of the list/table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence , as well as to sub-tables and to user-defined attribute of data type table .

Type

Method

Syntax

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

Parameter

The optional parameter CallOpenControl of data type boolean sets if the Open Control will be executed ( true ) or not ( false ).

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

Example

MyDataTable.openDialog MyDataStack.openDialog(true)

SimTalk

closeDialog [SimTalk] - lists

openDialogBox [SimTalk]

See also

Open Object [context menu, lists]

###### openDialogBox [SimTalk]

Opens the window of the list object designated by &lt;Path&gt; as a dialog in front of all other windows and dialog boxes.

Remarks

The dialog box shows the contents of the list object in a uniform standard font, not with the Font Size and Font Color , which you selected in the dialog Format .

Make sure that you deactivate the command Inherit Contents / InheritContents before you attempt to type in data.

The method applies to the objects DataStack , DataQueue , DataList , and DataTable .

**Note**

To prevent you from accidentally canceling your changes in the dialog, we deactivated the Close button in the title bar of the dialog. You have to decide what is going to happen, when you close the dialog, by clicking OK or Cancel .

Type

Method

Syntax

```simtalk
< Path >.openDialogBox([AutoSizeColumns:boolean:=false]) → boolean
```

**Parameter**

The optional parameter AutoSizeColumns of data type boolean sets if the column widths are calculated automatically according to the content of the widest occupied cell for each column ( true ) or not ( false ).

This parameter applies for objects of type DataTable and for subtables and user-defined attributes of data type table .

**Default Value of the Parameter**

The default value is false .

Return Value

The return value has the data type boolean .

**Example**

MyDataTable.openDialogBox MyDataList.openDialogBox

SimTalk

openDialog [SimTalk] - lists

refillDialog [SimTalk]

InheritContents [SimTalk]

See also

Open a List as a Dialog in the Foreground

Open Object [context menu, lists]

Inherit Contents [lists]

###### printList [SimTalk]

printList [SimTalk]

Prints the contents of the list designated by &lt;Path&gt;, without the icon and information about origin and class.

Remarks

The printout is identical with the printout you get when you click Print on the List ribbon tab.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.printList([string]) → boolean
```

Return Value

The return value has the data type boolean .

Example

MyDataQueue.printList MyTimeSequence.printList

See also

Print List

###### refillDialog [SimTalk]

Fills the open dialog box of a list or a table designated by &lt;Path&gt; with the current values.

Remarks

Updating the contents of the dialog box is especially helpful if you changed values via information flow and you want to show these values in the list or table which you opened as a dialog box. If you did not open the table as a dialog box, but as a regular list window, Plant Simulation will always show the current values anyway. In this case the method recomputes any formulas contained in the list window.

**Note**

Values you changed in the dialog box but did not apply will be discarded.

Type

Method

Syntax

&lt; Path &gt;.refillDialog

**Example**

MyDataStack.refillDialog MyDataQueue.refillDialog MyDataList.refillDialog MyDataTable.refillDialog

**SimTalk**

openDialogBox [SimTalk]

showPrintDialog [SimTalk] - lists

Opens the dialog Print of the default printer you set under MS Windows.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.showPrintDialog → boolean

Return Value

The return value has the data type boolean .

Example

MyTimeSequence.showPrintDialog

See also

Print List

Methods for the Order of Cells within Lists and Tables

\_Methods for the Order of Cells within Lists and Tables

Lists and tables provide the methods listed in the table of contents to the left for manipulating the order of cells.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**find [SimTalk] - lists**

###### find [SimTalk] - lists

Searches for a value in the list/table designated by &lt;Path&gt; that is smaller than or equal to the passed value.

Remarks

**Note**

Plant Simulation searches in the list/table starting at the cursor position which you can set using setCursor and then continues column-wise until it finds the value.

When it finds a value, fi nd returns true and sets the cursor into that cell. It returns false if it did not find the value. If several values exist, Plant Simulation sets the cursor into the first one it finds. A new search starts at the position after the last result and returns the next entry toward the end of the list/table. To start a new search, use setCursor to set a new start position. Plant Simulation searches tables column-wise starting either in the first cell of the first column or in the first cell of the range you specified.

**Note**

The method fi nd(void) only searches the range of the list that contains entries, i.e., between position 1 and the positions designated by the read-only attributes XDim or YDim .

**Note**

When searching for a string, the string comparison is case-insensitive.

Plant Simulation starts searching at the current cursor position. This only applies if the cursor is located within one of the specified ranges. If this is not the case, Plant Simulation starts searching within the first specified range and then searches within the following ranges if it does not find the value, etc.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.find(Value:any) → boolean < Path >.find([Range:listrange, …,]Value:any) → boolean
```

**Parameters**

- The parameter Value of data type any designates the value you want to find.

- The optional parameter Range of data type listrange designates the range between which Plant Simulation searches to the position of the cursor, for tables the position of both cursors.

**Note**

If the cursor is located within one of the specified ranges, Plant Simulation does not search the preceding ranges, not even after the search was negative for the other ranges.

If the cursor is located in the middle of the range, Plant Simulation only searches the range after the cursor, but not the range before it. If you do not enter a range, Plant Simulation searches the list starting at the position of the cursor to the end of the list.

**Note**

If the current cursor is not located in the specified table range when searching a table, the search starts in the first cell of the table range.

If a search was finished without finding the value, the internal cursor afterward points to the starting position from which the search was started.

**Examples**

```simtalk
MyDataTable.setCursor(1, 1)  // starts searching for "abc" from the top left cell to the end
if MyDataTable.find("abc")
	print MyDataTable.CursorX, " ", MyDataTable.CursorY
else
	print "not found"
end
MyDataStack.find(12.34)  // finds the floating point value 12.34 starting from the current cursor position
MyDataQueue.find(42)     // finds the integer value 42 starting from the current cursor position
MyDataList.find({1},{4}..{8},"drill") //finds the string "drill" in row 1 and in rows 4 to 8 starting from the current cursor position
MyDataTable.find("a")        // finds the string "a" in the entire table starting from the current cursor position
MyDataTable.setCursor(3,1)   // set cursor so that next find starts search from beginning
MyDataTable.find({3,*},"a")  // finds the string "a" in column 3 starting from the current cursor position
MyDataTable.find({1,1}..{4,*},"a") // finds the string "a" in columns 1 to 4 in all rows starting from the current cursor position
```

Specify void for the parameter to find blank cells in the list. Cells containing an empty string "" are not empty!

**Example**

if data.find(void)

```simtalk
print ("data not complete")
end
```

Return Value

The return value has the data type boolean .

SimTalk

setCursor [SimTalk] - DataTable

CursorX [SimTalk]

CursorY [SimTalk]

XDim [SimTalk] - DataTable

YDim [SimTalk] - DataTable

See also

Search Lists with Methods in the Step-by-Step Help

Find [lists]

Specifying a Range of Cells [several columns]

###### findCeil [SimTalk]

Searches the list designated by &lt;Path&gt; for the value greater than or equal to the value you specify.

Remarks

The method only applies to lists and tables of data types integer , real and string , and to data types, which can be converted into the data type real , such as dateTime , weight , etc.

Type

Method

Syntax

```simtalk
< Path >.findCeil([Range:listrange, ...,] Value:any) → boolean
```

**Parameters**

- The parameter Value of data type any designates the value you want to find.
- The parameter Range of data type listrange designates the range between which Plant Simulation searches to the position of the cursor, for tables it designates the position of both cursors.

Return Value

The return value has the data type boolean .

true if Plant Simulation found a value. It then sets the cursor in that cell.

false if it did not find the value.

If several values exist, Plant Simulation sets the cursor to the cell that is closest to the value of data type any . The search starts at the current cursor position. This holds only true if the cursor is located within one of the ranges specified. If that is not the case, the search begins in the first range specified and, if finished without success, is continued in the next range, etc.

**Note**

If the cursor is located in one of the ranges specified, Plant Simulation does not search the preceding ranges, not even after the search was negative for the other ranges.

If the cursor is located in the middle of the range, Plant Simulation only searches the range after the cursor, but not the range before.

**findCeil [SimTalk]**

If you do not enter a range, Plant Simulation searches the list starting at the position of the cursor to the end of the list.

**Example**

```simtalk
-- Suppose that a DataQueue contains the values 30, 50, 20, 0, 40, 10. -- We then apply the method findCeil to it:
MyDataQueue.Cursor := 1 // prepares the search
MyDataQueue.findCeil(25) -- The cursor is set to 30 as 30 is the value greater than or equal to -- the search value 25 and is closest to 25
```

**SimTalk**

Cursor [SimTalk]

findFloor [SimTalk]

See also

Find [lists] on the Edit menu

Specifying a Range of Cells [several columns] &gt; Column Index Belongs To Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### findFirst [SimTalk]

Searches for a value in the list/table designated by &lt;Path&gt; that is smaller than or equal to the specified value .

**Remarks**

Plant Simulation searches in the list/table starting at the start of the search range or to the cell designated by the position [1,1] if you did not specify a search range.

findFirst returns false if it did not find the value. If several values exist, Plant Simulation sets the cursor to the first one it finds. A new search starts at the position after the last result and returns the next entry toward the end of the list/table. To start a new search, use setCursor to set a new start position. Plant Simulation searches tables column-wise starting either in the first cell of the first column or in the first cell of the range you specified.

**Note**

When searching for a string, the string comparison is case-insensitive.

Plant Simulation starts searching at the current cursor position. This only applies if the cursor is located within one of the specified ranges. If this is not the case, Plant Simulation starts searching within the first specified range and then searches within the following ranges if it does not find the value, etc.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.findFirst([Range:listrange, …,]Value:any) → boolean
```

**Parameters**

- The optional parameter Range of data type listrange designates the range between which Plant Simulation searches to the position of the cursor. For tables Range designates the position of both cursors.

**Note**

If the cursor is located within one of the specified ranges, Plant Simulation does not search the preceding ranges, not even after the search was negative for the other ranges.

If the cursor is located in the middle of the range, Plant Simulation only searches the range after the cursor, but not the range before it. If you do not enter a range, Plant Simulation searches the list starting at the position of the cursor to the end of the list.

**Note**

If the current cursor is not located in the specified table range when searching a table, the search starts in the first cell of the table range.

- The parameter Value of data type any designates the value you want to find.

If a search was finished without finding the value, the internal cursor afterward points to the starting position from which the search was started.

**Examples**

```simtalk
MyDataStack.findFirst(12.34) // finds the floating point value 12.34 starting from the current cursor position
MyDataQueue.findFirst(42) // finds the integer value 42 starting from the current cursor position
MyDataList.findFirst({1},{4}..{8},"drill") //finds the string "drill" in row 1 and in rows 4 to 8 starting from the current cursor position
MyDataTable.findFirst("a") // finds the string "a" in the entire table starting from the current cursor position
MyDataTable.setCursor(3,1) // set cursor so that next find starts search from beginning
MyDataTable.findFirst({3,*},"a") // finds the string "a" in column 3 starting from the current cursor position
MyDataTable.findFirst({1,1}..{4,*},"a") // finds the string "a" in columns 1 to 4 in all rows starting from the current cursor position
var
MyDataTable.setCursor(1,1) // starts searching for "abc" from the beginning to the end
if MyDataTable.findFirst("abc")
	print MyDataTable.CursorX, " ",MyDataTable.CursorY
else
	print "not found"
end
```

Specify the parameter void to make the method fi ndFirst find blank cells in the list. Cells containing an empty string "" are not empty!

**Return Value**

The return value has the data type boolean .

Example

```simtalk
if data.findFirst(void)
	print ("data not complete")
```

end

**SimTalk**

setCursor [SimTalk] - DataTable

CursorX [SimTalk]

CursorY [SimTalk]

See also

Search Lists with Methods in the Step-by-Step Help

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**findFloor [SimTalk]**

###### findFloor [SimTalk]

Searches the list designated by &lt;Path&gt; for the value that is smaller than or equal to the value you specify.

Remarks

The search starts at the current cursor position. This holds only true if the cursor is located within one of the ranges specified. If that is not the case, the search starts in the first range specified and, if finished without success, continues in the next range, etc.

**Note**

If the cursor is located in one of the ranges specified, Plant Simulation does not search the preceding ranges, not even after the search was negative for the other ranges.

If the cursor is located in the middle of the range, Plant Simulation only searches the range after the cursor, but not the range before.

If you do not enter a range, Plant Simulation searches the list starting at the position of the cursor to the end of the list.

The method only applies to lists and tables of data types integer , real , and string , and to data types, which can be converted into the data type real , such as dateTime , weight , etc.

Type

Method

Syntax

```simtalk
< Path >.findFloor([Range:listrange, ..., ]Value:any) → boolean
```

**Parameters**

- The parameter Value of data type any designates the value you want to find.
- The parameter Range of data type listrange designates the range between which Plant Simulation searches to the position of the cursor, for tables the position of both cursors.

Return Value

The return value has the data type boolean .

true if Plant Simulation found a value. It then sets the cursor onto that entry.

false if it did not find the value.

If several values exist, Plant Simulation sets the cursor to the cell that is closest to the value of data type any .

**Example**

```simtalk
-- Suppose that a DataList named c contains the entries 20, 40, 0, 30, 10, 50. -- The cursor is located in cell 5. -- We then apply the method findFloor to it:
c.Cursor := 1 // prepares the search
c.findFloor({2}..{5},25) -- The cursor is set to 10 as 10 is the value smaller or equal to the search value 25, --  being closest to 25 and that is located in the given range.
```

**SimTalk**

Cursor [SimTalk]

**findCeil [SimTalk]**

See also

Find [lists] on the Edit menu

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**inOrder [SimTalk]**

###### inOrder [SimTalk]

Inserts a new row with the value you want to sort into the existing sorted list/table designated by &lt;Path&gt;

**Remarks**

**Note**

Plant Simulation sorts empty cells at the end of the column when you sort in ascending order.

It sorts empty cells at the start of the column when you sort in descending order.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.inOrder(ColumnIndex:any, Value:any, SortOrder:any)

**Parameters**

- The parameter ColumnIndex of data type any designates the column index.
- The parameter Value of data type any designates the value, which you want to sort.
- The parameter SortOrder of data type any designates the sort order. Enter the sort direction ascending ( up ) or descending ( down ). If you do not enter a sort direction, by specifying an empty string "" , the decision over the position at which the entry is to be sorted in is shifted to the next sort direction. If you do not enter a command or a column of a table, the corresponding cell remains empty.

The parameters consist of the column index, the value you want to sort in, and the direction. Separate the parameters with commas.

**Example**

Suppose that we want to sort a new row containing the values 4711,1,9 into the following table.

|    |   "kind" |   "prio" |   "value" |
|----|----------|----------|-----------|
|  1 |      815 |       12 |         4 |
|  2 |     4711 |        8 |         9 |
|  2 |     4719 |        4 |        10 |

The value of the third column, sorted in ascending order ( 3,9,up ) is to be sorted first. Column 1 is not sorted ( 1,4711, ""), column 2 is sorted in descending order ( 2,1,down ). Enter this command to accomplish your goal:

MyDataTable.inOrder(3,9,"up",1,4711,"",2,1,"down")

After the new values are sorted in, the table will look like this:

|    |   "kind" |   "prio" |   "value" |
|----|----------|----------|-----------|
|  1 |      815 |       12 |         4 |
|  2 |     4711 |        8 |         9 |
|  3 |     4711 |        1 |         9 |
|  4 |     4719 |        4 |        10 |

**See also**

Sort Ascending [lists] on the List ribbon tab

Sort Ascending [lists] on the context menu

Sort Descending [lists] on the List ribbon tab

Sort Descending [lists] on the context menu

###### setCursor [SimTalk] - lists

setCursor [SimTalk] - lists

Sets the internal cursor of the list designated by &lt;Path&gt; to the designated cell.

Remarks

The method applies to the objects DataStack , DataQueue , and DataList .

Type

Method

Syntax

```simtalk
< Path >.setCursor(Row:integer) → boolean
```

Parameter

The parameter Row of data type integer designates the row, i.e., the internal CursorY .

Return Value

The return value has the data type boolean .

true if the cursor was set to the desired position.

Example

```simtalk
MyDataStack.setCursor(17)
MyDataList.setCursor(4)
print MyDataList.setCursor(4) // returns true if the cursor was set to row 4
```

SimTalk

Cursor [SimTalk]

CursorY [SimTalk]

###### sort [SimTalk] - lists

Sorts the list/table designated by &lt;Path&gt; according to the specified sort order.

Remarks

Sorting is case-sensitive.

For the data type string umlauts (ä, ö, ü) are sorted according to their local character set.

**Note**

For the setting Sort Ascending / SortOrder "up" , Plant Simulation places empty cells at the end of the column.

For the setting Sort Descending / SortOrder "down" , Plant Simulation places empty cells at the start of the column.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.sort(SortOrder:string) < Path >.sort(Column:any, SortOrder:string) < Path >.sort(Column:any, SortOrder:string[])
```

**Parameters**

- The parameter SortOrder of data type string designates the sort order. Enter the sort direction ascending ( "up" ) or descending ( "down" ). (For lists with one column.)
- The parameter Column of data type any designates one or several columns as sort range for lists with several columns. You can also enter the system index or a user-defined index in the sort range. The number of columns you can enter is only limited by the number of columns on the table. If you do not enter a range, the method uses column 1 as the sort range.
- The parameter SortOrder of data type string designates the sort order. You can enter "up" or "down" . "Up" searches in an ascending, "down" in a descending order.

**sort [SimTalk] - lists**

- To sort the list or table according to several columns, you can set the sort order for each column separately with the parameter SortOrder with an array of data type string You might, for example, type in

MySortedClothes.sort(1,2,3,["up","down","down"])

**Examples**

Our original DataTable looks like this:

<!-- image -->

|   1 | Pants   | S   |
|-----|---------|-----|
|   2 | Vest    | L   |
|   3 | Shirt   | L   |
|   4 | Socks   | S   |
|   5 | Socks   | M   |
|   3 | Suit    | L   |
|   1 | Pants   | L   |
|   2 | Vest    | M   |
|   2 | Suit    | L   |

- We sort this DataTable with the instruction:

<!-- formula-not-decoded -->

This sorts the DataTable as follows:

<!-- image -->

- Sorting the original table with the instruction

MySortedClothes.sort(2,3,"up")

sorts it like this:

<!-- image -->

If you enter several columns, Plant Simulation first sorts the table according to column 1. If Plant Simulation finds the same value repeatedly, it proceeds with the next column, etc.

- Sorting the original table with the instruction

MySortedClothes.sort(1,2,3,["Up","Down","Down"])

sorts it like this:

<!-- image -->

See also Sort Ascending [lists] on the List ribbon tab Sort Ascending [lists] on the context menu Sort Descending [lists] on the List ribbon tab Sort Descending [lists] on the context menu

Methods for the Format of Lists and Tables

\_Methods for the Format of Lists and Tables

Lists and tables provide the methods listed in the table of contents to the left for setting and getting their format. In the dialog of the objects, you can select these settings under Format &gt; List Format &gt; Tab Settings .

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### copyContentTo [SimTalk]

Copies the contents of the source table designated by &lt;Path&gt; into the designated target table.

Remarks

Plant Simulation deactivates inheritance of the contents of the destination table and completely overwrites the existing contents.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.copyContentTo(DestinationTable:list)

Parameter

The parameter DestinationTable of data type list designates the target table.

Example

MySourceTable.copyContentTo(MyTargetTable)

SimTalk

copyFormatTo [SimTalk]

###### copyFormatTo [SimTalk]

Copies the format of the source table designated by &lt;Path&gt; into the designated target table.

**Remarks**

Note

Plant Simulation deactivates Common Format when you set the format for a subtable.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.copyFormatTo(FormatData:list[, WithIndexes:boolean])
```

**Parameter**

- The parameter FormatData of data type list designates the target table.
- The optional parameter WithIndexes sets if the indexes are copied as well ( true ) or not ( false ) when you copy the format. With the default setting true row index and column index are also copied. Specify false to not copy the row index. For the column index the setting Column Index Belongs to Contents determines if the column index will be copied or not.

<!-- image -->

**Example**

print MySourceTable.copyFormatTo(MyTargetTable)

copyFormatTo [SimTalk]

SimTalk

copyContentTo [SimTalk]

See also

Common Format [check box]

Column Index Belongs to Contents

###### deleteCellFormat [SimTalk]

Deletes all formatting settings you applied to cells of the list or table designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteCellFormat

Example

MyDataList.deleteCellFormat

SimTalk

delete [SimTalk] - lists

copyFormatTo [SimTalk]

getCommonFormatData [SimTalk] - lists

setAlignmentCells [SimTalk]

setBackgroundColorCells [SimTalk]

setEditorRightsCells [SimTalk]

setFontColorCells [SimTalk]

setFontSizeCells [SimTalk]

**getAlignmentCell [SimTalk]**

###### getAlignmentCell [SimTalk]

Returns the alignment of a cell of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.getAlignmentCell(Column:any, Row:any)

**Parameters**

- The parameter Column of data type any designates the column of the cell, whose alignment you want to get.
- The parameter Row of data type any designates the row of the cell, whose alignment you want to get.

**Example**

print MyDataTable.getAlignmentCell(1,14)

SimTalk

Alignment [cells and columns]

See also

setAlignmentCells [SimTalk]

###### getBackgroundColorCell [SimTalk]

Returns the background color of a cell of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.getBackgroundColorCell(Column:any, Row:any)

**Parameters**

- The parameter Column of data type any designates the column of the cell whose background color you want to get.
- The parameter Row of data type any designates the row of the cell whose background color you want to get.

**Example**

MyDataTable.getBackgroundColorCell(2,5)

SimTalk

setBackgroundColorCells [SimTalk]

See also

Background Color [cells]

getCommonFormatData [SimTalk] - lists

Gets format data of the column of data type List/Table for which you activated common format and writes it to the target table.

Remarks

The method applies to the objects DataStack , DataQueue , and DataList .

Type

Method

Syntax

```simtalk
< Path >.getCommonFormatData(TargetList:list) < Path >.getCommonFormatData(TargetTable:table)
```

Parameter

The parameter TargetList of data type list designates the target list.

The parameter TargetTable of data type table designates the target table.

Example

SourceStack.getCommonFormatData(MyDataStack) SourceTable.getCommonFormatData(MyDataTable)

SimTalk

setCommonFormatData [SimTalk] - lists

See also

Common Format [check box]

###### getEditorRightsCell [SimTalk]

Returns the editor rights of a cell of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.getEditorRightsCell(Column:any, Row:any)

**Parameters**

- The parameter Column of data type any designates the column of the cell, whose editor rights you want to get.
- The parameter Row of data type any designates the row of the cell, whose editor rights you want to get.

**Example**

MyDataTable.getEditorRightsCell(2,5)

SimTalk

setEditorRightsCells [SimTalk]

See also

Filename [FileLink]

Information Flow [check box]

**getFontColorCell [SimTalk]**

###### getFontColorCell [SimTalk]

Returns the font color of a cell of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.getFontColorCell(Column:any, Row:any)

**Parameters**

- The parameter Column of data type any designates the column of the cell, whose font color you want to get.
- The parameter Row of data type any designates the row of the cell, whose font color you want to get.

**Example**

MyDataTable.getFontColorCell(2,5)

SimTalk

setFontColorCells [SimTalk]

See also

Font Color [cells]

###### getFontSizeCell [SimTalk]

Returns the font size of a cell of the list or table TimeSequence designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.getFontSizeCell(Column:any, Row:any)

**Parameters**

- The parameter Column of data type any designates the column of the cell, whose font size you want to get.
- The parameter Row of data type any designates the row of the cell, whose font size you want to get.

**Example**

MyDataTable.getFontSizeCell(2,5)

SimTalk

setFontSizeCells [SimTalk]

See also

Font Size [drop-down list] - cells, columns

###### getHTMLCode [SimTalk] - lists

getHTMLCode [SimTalk] - lists

Returns the HTML representation of the list or table designated by &lt;Path&gt; as its HTML code.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< >.getHTMLCode([Caption:string, ColumnIndex|ColumnRange|ColumnName:any,
Path ColumnIndex|ColumnRange|ColumnName]) → string
```

**Parameter**

- The optional parameter Caption of data type string designates the caption of the list or table .
- The optional parameters ColumnIndex|ColumnRange|ColumnName of data type integer designate ColumnIndex|ColumnRange|ColumnName of the column.

**Return Value**

The return value has the data type string .

**Example**

MyDataTable.getHTMLCode() MyDataTable.getHTMLCode("SampleTable") MyDataTable.getHTMLCode(1,2,"6") MyDataTable.getHTMLCode(1,"3..6") MyDataTable.getHTMLCode("SampleTable", "0", "#Name", "#Destination")

**See also**

Display a DataTable or a DataList in the HtmlReport

###### isAlignment [SimTalk]

Returns if the alignment of the cells of the list or table designated by &lt;Path&gt; matches a value (true) or not (false).

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.isAlignment(Alignment:string)
-> boolean
```

Parameter

The parameter Alignment of data type string designates the value

You can specify "Right" , "Left" , or "Center" .

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyDataStack.isAlignment("Center")
print MyDataList.isAlignment("left")
print MyDataQueue.isAlignment("right")
print MyDataTable.isAlignment("Center")
print MyTimeSequence.isAlignment("Center")
```

**See also**

Alignment [cells and columns]

**setAlignmentCells [SimTalk]**

###### setAlignmentCells [SimTalk]

Sets the alignment of the cells of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

< >.setAlignmentCells(Range:listrange[, Range:listrange, ...],

```simtalk
Path Alignment:string)
-> string
```

**Parameters**

- The parameters Range of data type listrange designate the range of cells, whose alignment you want to set.

**Note**

You can only use the asterisk * to designate a range if the object has a Dimension . Plant Simulation considers the object to have a dimension if you either entered the number of rows and columns in the dialog or if the object contains entries.

- The parameter Alignment of data type string designates the value.

You can specify "Left" , "Right" , or "Centered" .

Return Value

The return value has the data type string .

**Example**

MyDataTable.setAlignmentCells({1,2}..{1,6},"left") timeseq.setAlignmentCells({1,5}..{1,112},"right")

**SimTalk**

getAlignmentCell [SimTalk]

**See also**

Alignment [cells and columns]

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**setBackgroundColorCells [SimTalk]**

###### setBackgroundColorCells [SimTalk]

Sets the background color of the cells in the designated range of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.setBackgroundColorCells(Range:listrange[, Range2:listrange, ...], BackgroundColor:integer) -&gt; integer

**Parameters**

- The parameters Range of data type any designate the cells, whose background color you want to set.

**Note**

You can only use the asterisk * to designate a range if the object has a Dimension . Plant Simulation considers the object to have a dimension if you either entered the number of rows and columns in the dialog or if the object contains entries.

<!-- image -->

- The parameter BackgroundColor of data type integer designates the color.

You can specify 1 for Black , 2 for Red , 3 for Green , 4 for Blue , 5 for Magenta , 6 for Yellow or 7 for Cyan .

Set the RGB values of the color with the method makeRGBValue .

Return Value

The return value has the data type integer .

Example

MyDataTable.setBackgroundColorCells({2,2}..{2,5},makeRGBValue(0,0,155))

SimTalk

getBackgroundColorCell [SimTalk]

makeRGBValue [SimTalk]

See also

Background Color [cells]

setCommonFormatData [SimTalk] - lists

Sets the common format data for the subtables contained in the column of data type List/Table of the target list object designated by &lt;Path&gt; for which you activated Common Format .

Remarks

The method applies to the objects DataStack , DataQueue , and DataList .

Type

Method

Syntax

```simtalk
< Path >.setCommonFormatData(FormatData:list) < Path >.setCommonFormatData(FormatData:table)
```

**Parameter**

The parameter FormatData of data type list designates the list which contains the desired formatting for the sublists.

The parameter FormatData of data type table designates the table which contains the desired formatting for the subtables.

Example

MyTargetDataList.setCommonFormatData(MyDataList)

SimTalk

getCommonFormatData [SimTalk] - lists

getCommonFormat [SimTalk]

setCommonFormat [SimTalk]

setCommonFormatData [SimTalk] - DataTable

See also

Common Format [check box]

###### setEditorRightsCells [SimTalk]

Sets the editing permissions for a range of cells of the list or table designated by &lt;Path&gt;.

**Remarks**

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

**Syntax**

&lt; Path &gt;.setEditorRightsCells(Range:listrange[, Range2:listrange, ...], ReadOnly:boolean)

**Parameters**

- The parameters Range of data type listrange designate the cells.

**Note**

You can only use the asterisk * to designate a range if the object has a Dimension . Plant Simulation considers the object to have a dimension if you either entered the number of rows and columns in the dialog or if the object contains entries.

<!-- image -->

**setEditorRightsCells [SimTalk]**

- The parameter ReadOnly of data type boolean designates read-only access ( true ) or read and write access ( false ).

Example

MyDataTable.setEditorRightsCells({2,1}..{3,2},true) // read-only access

SimTalk

getEditorRightsCell [SimTalk]

See also

Editor [check box]

Information Flow [check box]

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### setFontColorCells [SimTalk]

Sets the font color of a range of cells of the list or table designated by &lt;Path&gt;.

**Remarks**

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

**Syntax**

```simtalk
< Path >.setFontColorCells(Range:listrange [, Range2:listrange, ...], FontColor:integer)
-> integer
```

**Parameters**

- The parameters Range of data type listrange designate the cells, whose font color you want to set.

**Note**

You can only use the asterisk * to designate a range if the object has a Dimension . Plant Simulation considers the object to have a dimension if you either entered the number of rows and columns in the dialog or if the object contains entries.

<!-- image -->

**setFontColorCells [SimTalk]**

- The parameter FontColor of data type integer designates the font color. You can specify for Black , for Red , for Green , for Blue , for Magenta , for Yellow , or for

1 2 3 4 5 6 7 Cyan .

- Set the RGB values of the color with the method makeRGBValue .

Return Value

The return value has the data type integer .

Example

MyDataTable.setFontColorCells({3,2}..{5,6},7)

SimTalk

getFontColorCell [SimTalk]

makeRGBValue [SimTalk]

See also

Font Color [cells]

###### setFontSizeCells [SimTalk]

Sets the font size of the range of cells of the list or table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.setFontSizeCells(Range:listrange[, Range2:listrange, ...], FontSize:integer)
```

**Parameters**

- The parameters Range of data type listrange designate the cells, whose font color you want to set.

**Note**

You can only use the asterisk * to designate a range if the object has a Dimension . Plant Simulation considers the object to have a dimension if you either entered the number of rows and columns in the dialog or if the object contains entries.

- The parameter FontSize of data type integer designates the font size.

You can specify 1 for Small , 2 for Medium , 3 for Large , or 4 for Extra Large .

<!-- image -->

**Example**

<!-- image -->

Methods for Querying Statistics Values of List and Tables

\_Methods for Querying Statistics Values of Lists and Tables

Lists and tables provide the methods listed in the table of contents to the left for querying statistics values.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

max [SimTalk] - lists

max [SimTalk] - lists

Returns the greatest value in the range of cells of the list or table designated by &lt;Path&gt;.

Remarks

After it found the greatest value, the method sets the cursor into the cell in which it found the value.

The method only applies to entries of data types real or integer . Plant Simulation ignores entries of other data types in the ranges to be searched or considers their value to be 0.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.max([Range:listrange, ...])
-> real
```

Parameter

The parameters Range of data type listrange designate the range of cells.

max treats the boolean value true like 1.0 and the boolean value false like 0.0.

Return Value

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

Example

```simtalk
print MyDataStack.max({*})
print MyDataQueue.max({1}..{*})
print MyDataList.max({*})
print MyDataTable.max({3,3}..{3,*}) // maximum number of entries
```

SimTalk

min [SimTalk] - lists CursorX [SimTalk]

CursorY [SimTalk]

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### meanValue [SimTalk]

meanValue [SimTalk]

Returns the arithmetic mean of all values in a range of cells of the list or table designated by &lt;Path&gt;.

Remarks

The method only applies to entries of data types real or integer . Plant Simulation ignores entries of other data types in the ranges to be searched or considers their value to be 0.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.meanValue([Range:listrange, ...])
-> real/integer
```

Parameter

The parameters Range of data type listrange designate the range of cells.

meanValue treats the boolean value true like 1.0 and the boolean value false like 0.0.

Return Value

The return value has the data type real or integer .

Example

```simtalk
print MyDataStack.meanValue({*})
print MyDataQueue.meanValue({1}..{*})
print MyDataList.meanValue({*})
print MyDataTable.meanValue({3,3}..{3,*})
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents min [SimTalk] - lists Returns the smallest value in a range of cells of the list or table designated by &lt;Path&gt;.

Remarks

When the method finds the smallest value, it sets the cursor to the cell in which it found the value.

The method only applies to entries of data types real or integer . Plant Simulation ignores entries of other data types in the ranges to be searched or considers their value to be 0.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.min([Range:listrange, ...])
-> real
```

Parameter

The parameters Range of data type listrange designate the range of cells.

min treats the boolean value true like 1.0 and the boolean value false like 0.0.

Return Value

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

Example

```simtalk
print MyDataStack.min({*})
print MyDataQueue.min({1}..{*})
print MyDataList.min({3}..{*})
print MyDataTable.min({3,3}..{3,*}) // minimum number of entries
```

SimTalk

max [SimTalk] - lists CursorX [SimTalk]

CursorY [SimTalk]

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### standardDeviation [SimTalk]

Returns the standard deviation from the mean of all values in a range of cells of the list or table designated by &lt;Path&gt;.

Remarks

The method only applies to entries of data types real or integer . Plant Simulation ignores entries of other data types in the ranges to be searched or considers their value to be 0.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.standardDeviation([Range:listrange, ...])
-> real/integer
```

Parameter

The parameters Range of data type listrange designate the range of cells.

standardDeviation treats the boolean value true like 1.0 and the boolean value false like 0.0.

Return Value

The return value has the data type real or integer .

Example

```simtalk
print MyDataStack.standardDeviation({*})
print MyDataQueue.standardDeviation({1}..{*})
print MyDataList.standardDeviation({*})
print MyDataTable.standardDeviation({3,3}..{3,*})
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### sum [SimTalk] - lists

sum [SimTalk] - lists

Returns the sum of all values in a range of cells of the list or table designated by &lt;Path&gt;.

Remarks

The method only applies to entries of data types real or integer . Plant Simulation ignores entries of other data types in the ranges to be searched or considers their value to be 0.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.sum([Range:listrange, ...])
-> real/integer
```

Parameter

The optional parameter Range of data type listrange designate the range of cells.

If you do not specify the parameter, the sum is calculated over all cells.

sum treats the boolean value true like 1.0 and the boolean value false like 0.0.

Return Value

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

Example

```simtalk
print MyDataStack.sum({*})
print MyDataQueue.sum({1}..{*})
print MyDataList.sum({*})
print MyDataTable.sum({3,3}..{3,*})
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

**Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents**

Methods for Importing and Exporting Data in Text Format

\_Methods for Importing and Exporting Data in Text Format

Lists and tables provide the methods listed in the table of contents to the left for working with them in text format, instead of in table format (.pslist).

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

**readExcelFile [SimTalk]**

###### readExcelFile [SimTalk]

Imports data from the designated Excel file (*.xls) into the list or table designated by &lt;Path&gt;.

**Remarks**

**Note**

Plant Simulation overwrites any existing data.

Plant Simulation does not overwrite the column index and/or the row index of the Plant Simulation DataTable if the respective Excel cells are empty. To overwrite the contents of the column index and/or the row index in the Plant Simulation DataTable , delete this content before importing the Excel data.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

**Note**

Plant Simulation uses Excel as COM-server when reading and writing MS Excel-files. For this reason MS Excel has to be installed on your computer. To continue using the previous, no longer supported Excel interface, you can use the start option -NativeExcel .

Type

Method

Syntax

```simtalk
< Path >.readExcelFile(FileName:string[, Sheet:string, NoDebugger:boolean:=false, Password:string]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the path to and the name of the Excel file (*.xls).
- The optional parameter Sheet of data type string designates the worksheet. If you do not specify it and if the Excel file has more than one worksheets, Plant Simulation opens a dialog allowing you to select the desired worksheet.
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

If you do not specify this parameter, the Method Debugger always opens.

If you type in true , the Method Debugger does not open and the method returns the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

- The optional parameter Password of data type string designates the password.

Return Value

The return value has the data type boolean .

**Example**

MyDataList.readExcelFile("C:\users\johnE\times.xls") MyDataTable.readExcelFile("C:\temp\product_plan.xls","plant xy anytown") if MyDataStack.readExcelFile("C:\temp\data.xls", true) = false // could not read file end

**See also**

**Import File**

Specifying Start Options , -NativeExcel

###### readFile [SimTalk] - lists

readFile [SimTalk] - lists

Imports data from the designated file into the list or table designated by &lt;Path&gt;. Plant Simulation overwrites any existing data.

**Remarks**

The method readFile can import text files, which you exported with the method writeFile , as well as object files, which you exported with the method writeObjectFile .

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.readFile(FileName:string[, NoDebugger:boolean:=false, CodePage:string:="ANSI"]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the path to and the name of the text file (*.txt).
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

Do not specify this parameter to always open the Method Debugger .

Specify true to not open the Method Debugger and to make the method return the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

- The optional parameter CodePage of data type string sets the encoding you want to use.

You can specify "ANSI" or "System" , "UTF-8" , or "Unicode" .

Do not specify this parameter to use the default encoding ANSI .

**Default Value of the Parameter**

The default value is "ANSI" .

Return Value

The return value has the data type boolean .

**Example**

MyDataList.readFile("C:\users\johnE\times.txt") MyDataTable.readFile("C:\temp\product_plan.psobj") if MyDataStack.readFile("C:\temp\data.txt", true) = false // could not read file end

**SimTalk**

writeFile [SimTalk] - lists

writeObjectFile [SimTalk]

See also

Import File

**readXMLFile [SimTalk]**

###### readXMLFile [SimTalk]

Imports data from the designated XML file (*.xml) into the list/table designated by &lt;Path&gt;. Plant Simulation overwrites any data that this file might already contain.

**Remarks**

**Note**

When reading an XML file that does not use our proprietary format, but Plant Simulation tries to construct a list/table from any XML data contained in the specified file. For complex XML files some XML data might not be entirely imported.

If you need to read complex XML files, use the XMLInterface instead.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.readXMLFile(FileName:string[, NoDebugger:boolean:=false]) → boolean

**Parameters**

- The parameter FileName of data type string designates the path to and the name of the XML file (*.xml).
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

If you do not specify this parameter, the Method Debugger always opens.

Specify true to not open the Method Debugger and to return the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

**Example**

MyDataTable.readXMLFile("D:\MyName\Public\xmltest.xml")

SimTalk

writeXMLFile [SimTalk]

See also

Import File

XMLInterface

**readXMLString [SimTalk]**

###### readXMLString [SimTalk]

Imports the designated string, which contains valid XML syntax, into the list or table designated by &lt;Path&gt;.

**Remarks**

Plant Simulation overwrites any existing data.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.readXMLString(XML:string[, NoDebugger:boolean:=false]) → boolean

**Parameters**

- The parameter XML of data type string designates the text of the XML content.
- The optional parameter NoDebugger of data type boolean sets if the Debugger opens after an unsuccessful access or not.

When you do not specify the optional parameter of data type boolean , the Debugger always opens.

When you specify true , the Debugger does not open and the method returns the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

SimTalk

**writeXMLFile [SimTalk]**

See also

Import File

###### writeExcelFile [SimTalk]

Exports the contents of the list/table designated by &lt;Path&gt; to the designated Excel file.

**Remarks**

Plant Simulation overwrites any existing content and the format of the Excel file.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

**Note**

Plant Simulation uses Excel as COM-server when reading and writing MS Excel-files. For this reason MS Excel has to be installed on your computer. To continue using the previous, no longer supported Excel interface, you can use the start option -NativeExcel .

**Note**

If you defined a background color in the Plant Simulation DataTable , Plant Simulation writes this background color to the Excel file. If this is not the case and if the contents of the Plant Simulation DataTable is written to an existing Excel file, its background color is not altered.

Type

Method

Syntax

```simtalk
< Path >.writeExcelFile(FileName:string[, Sheet:string, NoDebugger:boolean=false]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the Excel file into which Plant Simulation exports the data.

The file name has to have one of the following extensions: .xls, .xlsx, .xlsm, or .xlsb. The file extension determines which Excel file format Plant Simulation writes.

- The optional parameter Sheet of data type string designates the worksheet. If you do not type it in, Plant Simulation saves the list with the name of the worksheet, as Table1 .
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .
- Do not specify this parameter to always open the Method Debugger .

Specify true to not open the Method Debugger and to return the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

**Example**

MyDataStack.writeExcelFile("C:\users\nelly\factory_a.xls") MyDataTable.writeExcelFile("C:\temp\factory_a.xls","Engines",true) if MyDataList.writeExcelFile("C:\temp\data.xls") // data written successfully else // take appropriate measures end

**SimTalk**

readExcelFile [SimTalk]

writeExcelXMLFile [SimTalk]

See also

Export Excel File

Specifying Start Options , -NativeExcel

###### writeExcelXMLFile [SimTalk]

Exports the contents of the list/table designated by &lt;Path&gt; to the designated Excel file in Microsoft Excel Spreadsheet 2003-Format.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Plant Simulation overwrites any existing content of the file.

**Note**

As opposed to the method writeExcelFile Plant Simulation does not need a Microsoft Excel Installation on your computer. For this reason writeExcelXMLFile is considerably faster than writeExcelFile .

**Note**

If you defined a background color in the Plant Simulation DataTable , Plant Simulation writes this background color to the Excel file. If this is not the case and if the contents of the Plant Simulation DataTable is written to an existing Excel file, its background color is not altered.

Type

Method

Syntax

```simtalk
< Path >.writeExcelXMLFile(FileName:string[, Sheet:string, NoDebugger:boolean:=false]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the Excel file into which Plant Simulation exports the data.

The file name has to have the extension xml.

- The optional parameter Sheet of data type string designates the worksheet. If you do not enter it, Plant Simulation saves the list with the name of the worksheet, as Table1 .
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

If you do not specify this parameter, the Method Debugger always opens.

Specify true to not open Method Debugger and to return the value false when an error occurs.

Default Value of the Parameter

**writeExcelXMLFile [SimTalk]**

The default value is false.

Return Value

The return value has the data type boolean .

**Example**

MyDataStack.writeExcelXMLFile("C:\users\nelly\factory_a.xml") MyDataTable.writeExcelXMLFile("C:\temp\factory_a.xml","Engines",true) if MyDataList.writeExcelXMLFile("C:\temp\data.xml") // data written successfully else // take appropriate measures end

**SimTalk**

readExcelFile [SimTalk]

writeExcelFile [SimTalk]

See also

Export Excel File writeFile [SimTalk] - lists The method writeFile exports the contents of the list/table designated by &lt;Path&gt; to the designated text file.

Remarks

Plant Simulation overwrites any data that this file might already contain.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.writeFile(FileName:string[, NoDebugger:boolean:=false, CodePage:string:="UTF-8"]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the text file into which Plant Simulation exports the data.
- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

Do not specify this parameter to always open the Method Debugger .

Specify true to not open the Method Debugger and to make the method return the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

- The optional parameter CodePage of data type string sets the encoding you want to use.

You can specify "ANSI" or "System" , "UTF-8" , or "Unicode" .

If you don't specify this parameter, the default encoding ANSI is used.

**Default Value of the Parameter**

The default value is "ANSI" .

Return Value

The return value has the data type boolean .

**Example**

MyDataStack.writeFile("C:\users\nelly\times.txt") MyDataTable.writeFile("C:\temp\run1.txt") if MyDataList.writeFile("C:\temp\data.txt", true) // data written successfully else // take appropriate measures end

**SimTalk**

readFile [SimTalk] - lists

See also

Export to File [lists]

###### writeObjectFile [SimTalk]

Exports data of the list/table designated by &lt;Path&gt; to the designated file of type .pslist.

**Remarks**

Plant Simulation overwrites any data that this file might already contain.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.writeObjectFile(FileName:string[, NoDebugger:boolean:=false]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the object file of data type .pslist into which Plant Simulation exports the data.

Plant Simulation saves the file either to the current folder, compare setCurrentDirectory or to the folder which you pass as the absolute path.

- The optional parameter NoDebugger of data type boolean sets if the Method Debugger opens after an unsuccessful access ( false ) or not true .

If you do not specify this parameter, the Method Debugger always opens.

Specify true to not open the Method Debugger and to return the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

**Return Value**

The return value has the data type boolean .

**Example**

MyDataStack.writeObjectFile("C:\users\johnE\times.pslist") MyDataTable.writeObjectFile("C:\temp\run1.pslist") if MyDataList.writeObjectFile("C:\temp\data.pslist", true) // data written successfully

**writeObjectFile [SimTalk]**

else // take appropriate measures end

SimTalk

readFile [SimTalk] - lists

setCurrentDirectory [SimTalk]

See also

Export Object File

###### writeXMLFile [SimTalk]

Exports the contents of the list/table designated by &lt;Path&gt; to the designated XML file. Plant Simulation overwrites any data that this file might already contain.

**Remarks**

**Note**

When writing an XML file, Plant Simulation always uses our proprietary format.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.writeXMLFile(FileName:string[, NoDebugger:boolean:=false]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the XML file into which Plant Simulation exports the data.
- The optional parameter NoDebugger of data type boolean sets if the Debugger opens after an unsuccessful access or not. When you do not specify a value for this optional parameter, the Debugger always opens. When you specify true the Debugger does not open and the method returns the value false when an error occurs.

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

Example

MyDataTable.writeXMLFile("D:\MyName\Public\xmltest.xml")

**SimTalk**

readXMLFile [SimTalk]

See also

**Export XML File**

Methods for Indirectly Accessing Lists and Tables

##### \_Methods for Indirectly Accessing Lists and Tables

Lists and tables provide the methods listed in the table of contents to the left for indirectly accessing them. These methods only apply to ranges of data type object . The contents of the cells are references to objects whose attributes are to be processed.

To view all of the methods , read-only attributes , and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### asObject [SimTalk]

Returns the contents of a cell of data type string or object of the list/table designated by &lt;Path&gt; if the cell contains a valid path to an object.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

< Path >.asObject(Column:any, Row:any) → any

**Parameters**

- The parameter Column of data type any designates the column of the table.
- The parameter Row of data type any designates the row.

Return Value

The return value has the data type any .

**Note**

The return value is the lane of the TwoLaneTrack if the table cell, which asString returned, contains a valid path to a lane of a TwoLaneTrack . This returned value does not have the data type object and thus cannot be assigned to a variable of data type object . You can, however, assign it to a local variable of data type any .

If a table cell of data type object contains a path to a lane, reading the contents of the cell with brackets ( table[x,y] ) returns VOID as a lane does not have the data type object .

**Example**

```simtalk
var a : any
if .MUs.Transporter:1.getRoute(DataTable)
	a := MyDataTable.asObject(1,1)
	if isObject(a)
		print "first object: ", a.name
	else
		print "first object is a two-lane track: ", a.~.name
```

**asObject [SimTalk]**

```simtalk
end
print "the length is: ", a.length
```

**SimTalk**

asString [SimTalk] - DataTable

###### asString [SimTalk] - DataTable

Returns the designated cell of the DataTable designated by &lt;Path&gt; as a string .

Remarks

This is especially handy if the cell of data type object contains a path for which Plant Simulation would return the contents either as an object or as VOID.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.asString(Column:any, Row:any) → string
```

**Parameters**

- The parameter Column of data type any designates the column of the table.
- The parameter Row of data type any designates its row.

Return Value

The return value has the data type string .

Example

```simtalk
MyDataTable[1,2] := "Station" // writes an absolute path
MyDataTable.asString(1,2)     // reads a relative path
```

**See also**

asObject [SimTalk]

**findAttr [SimTalk]**

###### findAttr [SimTalk]

Searches for an object which contains the attribute with the passed name and passed attribute value in the List/Table designated by &lt;Path&gt;.

**Remarks**

The method fi ndAttr only searches in columns of data type object , i.e, it ignores columns with other data types. The method finds built-in attributes as well as user-defined attributes. If you just want to search for an object, which has this attribute, independent of the attribute value, then enter VOID as the value to be searched for.

findAttr starts its search at the position of the internal pointer of the List/Table . If fi ndAttr finds such an object, then the method sets the internal pointer to the respective cell and returns true. If fi ndAttr does not find such an object starting at the position of the internal pointer, it returns false.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

&lt; Path &gt;.findAttr([Range:listrange, ]AttributeName:string, Value:any) → boolean

**Parameters**

- The optional parameter Range of data type listrange designates the range which you would like to search. If you do not specify this parameter, Plant Simulation searches the entire Table . You can also specify several list ranges, all of which the method then searches.
- The parameter AttributeName of data type string designates the name of the attribute to be searched for.
- The parameter Value of data type any designates the value of the attribute for which you are searching. If Plant Simulation finds this value, it terminates the search. If you enter VOID as value, the search ends if an attribute with the name of the parameter AttributeName is found. fi ndAttr sets the internal pointer to the entry of the object and returns true. If the value does not match, fi ndAttr continues searching. If it does not find a matching entry, it returns false.

**Note**

The search for attribute names and attribute values is not case-sensitive.

Depending if Column Index Belongs to Contents is active or not, the range has different effects on the method fi ndAttr of the DataTable .

- If the DataTable has a column index and the column index belongs to the contents, the method relates to the entire contents of the DataTable , including the column index. See Column Index Belongs to Contents .
- If the DataTable has a column index and the column index does not belong to the contents, the method only relates to the contents of the DataTable , excluding the column index. See Column Index Does Not Belong to Contents .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
var wanted: object,
var row,column: integer
MyDataList.Cursor := 1
if MyDataList.findAttr("color", "red")
	wanted := MyDataList.read(MyDataList.Cursor)
end
MyDataTable.CursorX := 1
MyDataTable.CursorY := 1
if MyDataTable.findAttr({1,1}..{4,4},"order",VOID)
	column := MyDataTable.CursorX
	row := MyDataTable.CursorY
	print table[column,row].order
end
```

SimTalk

CursorX [SimTalk]

CursorY [SimTalk]

Cursor [SimTalk]

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**maxAttr [SimTalk]**

###### maxAttr [SimTalk]

Returns the maximum of the designated attribute of all objects in the list/table designated by &lt;Path&gt; to the designated value.

**Remarks**

In addition, Plant Simulation sets the file cursor into the cell in which the object with the maximum attribute value is located.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.maxAttr(Range:listrange, ..., AttributeName:string) → real
```

**Parameters**

- The parameters Range of data type listrange designate the range of the list.
- The parameter AttributeName of data type string designates the name of the attribute.

**Return Value**

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

**Example**

```simtalk
// search all entries within the specified range on the table and determine // the maximum of the user-defined attribute Time
MyDataTable.setCursor(1,1)
print MyDataTable.maxAttr({1,2}..{3,5},"time")
```

**SimTalk**

minAttr [SimTalk]

**See also**

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**meanValueAttr [SimTalk]**

###### meanValueAttr [SimTalk]

Returns the mean value of the designated attribute of all objects within the designated range of the list/table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.meanValueAttr(Range:listrange, ... AttributeName:string) → real
```

**Parameters**

- The parameters Range of data type listrange designate the range of the list.
- The parameter AttributeName of data type string designates the name of the attribute.

Return Value

The return value has the data type real .

Example

```simtalk
MyDataStack.Cursor := 1
print MyDataStack.meanValueAttr({3}..{*},"SetupTime")
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### minAttr [SimTalk]

Returns the minimum of the designated attribute of all objects in the list/table designated by &lt;Path&gt; to the designated value.

Remarks

Plant Simulation sets the file cursor into the cell in which the object with the minimum attribute value is located.

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.minAttr(Range:listrange, ... AttributeName:string) → real
```

**Parameters**

- The parameters Range of data type listrange designate the range of the list.
- The parameter AttributeName of data type string designates the name of the attribute.

**Return Value**

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

**Example**

```simtalk
// cycle through all cells in the lixg, query their processing time // and
return the minimum of the processing times as result
MyDataList.Cursor := 1
print MyDataList.minAttr({*},"ProcTime")
table.setCursor(1,1)
print MyDataTable.minAttr({1,2}..{3,5},"time")
```

**SimTalk**

**maxAttr [SimTalk]**

**minAttr [SimTalk]**

See also Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

###### standardDeviationAttr [SimTalk]

Returns the standard deviation of the designated attribute of all objects in the designated range of the list/table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.standardDeviationAttr(Range:listrange, ... AttributeName:string) → real
```

**Parameters**

- The parameters Range of data type listrange designate the range of the list.
- The parameter AttributeName of data type string designates the name of the attribute.

Return Value

The return value has the data type real .

Example

```simtalk
MyDataList.Cursor := 1
print MyDataList.standardDeviationAttr({*},"ProcTime")
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**sumAttr [SimTalk]**

###### sumAttr [SimTalk]

Returns the sum of the designated attributes of all objects in the designated range of the list/table designated by &lt;Path&gt;.

Remarks

The method applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Method

Syntax

```simtalk
< Path >.sumAttr(Range:listrange, ... AttributeName:string) → real
```

**Parameters**

- The parameters Range of data type listrange designate the range of the list.
- The parameter AttributeName of data type string designates the name of the attribute.

Return Value

The return value has the data type of the designated list range if this list range has a uniform data type.

If the data type is not uniform, the return values are converted to the data type real and the method returns the data type real .

**Example**

```simtalk
// cycle through all cells in the DataQueue, sum up the processing times // and
return the sum as the result
MyDataQueue.Cursor := 1
print MyDataQueue.sumAttr({1}..{5},"ProcTime")
```

See also

Specifying a Range of Cells [several columns] &gt; Column Index Belongs to Contents

Specifying a Range of Cells [several columns] &gt; Column Index Does Not Belong to Contents

**Read-only Attributes and Attributes of Cells**

##### \_Read-only Attributes and Attributes of Cells

Cells in lists and tables provide the read-only attribute Void [SimTalk] - cells of lists/tables and the attribute Name [SimTalk] - cells .

Read and write access depend on the object class and are described in the sub-chapters.

To view all of the read-only attributes and attributes of the list object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

###### Name [SimTalk] - cells

Name [SimTalk] - cells

Sets the name of the sublist or subtable contained in the addressed cell of the list/table designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path -of-the-list[row]>.Name.string < Path -of-the-table[column,row]>.Name.string
```

Return Value

The return value has the data type string .

Example

```simtalk
DataTable.createNestedList(1, 1, "abc")
print DataTable[1,1].Name  // prints "abc" DataTable[1,1].Name := "XY"
print DataTable[1,1].Name  // prints "XY"
```

###### Void [SimTalk] - cells of lists/tables

Returns if specified cell of the list/table designated by &lt;Path&gt; is empty (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path -of-the-list[row]>.void
-> boolean < Path -of-the-table[column,row]>.void
-> boolean
```

Return Value

The return value has the data type boolean .

Example

if not DataTable[1,1].void DataTable[1,1] += 1 end

