### DataList

Use the DataList for randomly accessing to the contents of the individual cells using their position, i.e., their row number.

Icon

<!-- image -->

**Description**

The DataList is a list with one column providing random access to the contents of the individual cells using their position, i.e., their row number. Imagine the DataList as a file-card box. When you add an entry, Plant Simulation moves all entries after this one position down. You can delete an entry, and you can read an entry and add that entry back to the DataList .

You can access the functions of the list objects on the List Ribbon Tab .

**Note**

The DataList always opens in the background behind any open dialog boxes. You can also open it in the foreground as a dialog box with the method openDialogBox .

The DataList shares its built-in properties with the data type List .

Note the difference between the object DataList , which you can insert into a model, and the data type list . You can create user-defined attributes and local and global variables of data type list that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason these variables and attributes do not recognize the SimTalk functions of the DataList , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataList and to variables and attributes.

To show a tooltip with information about the DataList , hover with the mouse over it.

To change the length of the graphic and the anchor points of the DataList , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the DataList to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

InformationFlow &gt; DataList on the Home ribbon tab.

See also

Properties of Lists and Tables

Work with Data in a List or Table in the Step-by-Step Help

Access Data in Lists in the

Step-by-Step Help

Accessing a Range of Cells with a Method

<!-- image -->

**DataList**

##### Creating Lists within Lists and Tables

Creating a List within a DataList

**Window of the DataList**

Double-click the icon of the DataList to open its window. In the window you can change its simulation properties .

The shared properties are described under Dialog Items of the Objects . You can access the functions of the list objects on the List Ribbon Tab .

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

**List Ribbon Tab**

The List Ribbon Tab provides commands pertaining to the lists and tables. Not all list objects provide all of the described commands.

<!-- image -->

**Methods of the DataList**

**\_Methods of the DataList**

The DataList provides:

- The methods listed in the table of contents to the left.
- The Methods of Lists and Tables .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the DataList , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.

- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type. We use these abbreviations:

| Argument of data type   | Data type      | Range of values           |
|-------------------------|----------------|---------------------------|
| integer                 | integer        | integer greater than zero |
| any                     | all data types | depending on data type    |
| listrange               | -              | a range                   |
| any , ..., any          | any data type  | a range of cells          |

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter

If the method has a return value, the signature shows its data type after the arrow -&gt;.

**[row] [SimTalk]**

##### [row] [SimTalk]

Returns the value of the designated row of the DataList designated by &lt;Path&gt;.

Remarks

You can also assign a new value to the cell in the row.

**Note**

When reading the contents of a cell of a DataList with the bracket operator in SimTalk 2.0 , Plant Simulation reads the contents of the designated cell, but will leave it in the DataStack , DataQueue , and the DataList .

When assigning a value to the designated cell with the bracket operator in SimTalk 2.0 , this value will just overwrite the contents of the existing cell. This way a DataList will behave the same way as a DataTable with one column.

**Note**

When reading the contents of a cell of a DataList with the bracket operator in SimTalk 1.0 , Plant Simulation reads and removes the contents of the designated cell. The remaining cells move up by one position.

When assigning a value to the designated cell with the bracket operator in SimTalk 1.0 , Plant Simulation inserts this value into the cell and moves the existing cells down by one position.

Type

Method

Syntax

```simtalk
< Path >[Row:integer]
```

Parameter

The parameter Row of data type integer designates the position of the cell.

Example

```simtalk
print DataList[2] // prints the contents of row 2 DataList[2] := 42 // overwrites the cell in row 2 with the value 42
```

append [SimTalk] - DataList

Appends the specified entry to the end of the DataList designated by &lt;Path&gt;.

Remarks

Plant Simulation does not allow to exceed the number of rows you set.

Type

Method

Syntax

&lt; Path &gt;.append(Entry:any)

Parameter

The parameter Entry of data type any designates the entry you want to append.

Example

MyDataList.append("crankshaft")

See also

Number of Rows [lists]

##### appendList [SimTalk]

appendList [SimTalk]

Adds the contents of all cells of the specified list to the DataList designated by &lt;Path&gt;.

Remarks

The contents of the existing cells remains untouched.

Type

Method

Syntax

< Path >.appendList(List:any)

Parameter

The parameter List of data type any designates the list you want to append.

Example

```simtalk
var s: stack[string]
s.create
s.insert("one")
s.insert("two")
MyDataList.appendList(s)
```

##### createNestedList [SimTalk] - DataList

Creates a nested list in the DataList designated by &lt;Path&gt;, containing lists and tables.

Remarks

The DataList has to be of data type list , stack , queue , or table .

Plant Simulation overwrites the existing sublist without moving existing list one row downward.

Local variables of data type list have to be treated differently as they cannot contain the data itself but only references to the respective data structures. When entering the Method object, variables of this type do not contain a reference to such a data structure yet (void). You can only access the data after the nested list has been created.

Type

Method

Syntax

```simtalk
< Path >.createNestedList([Row:integer, Name:string]) → list
```

**Parameters**

- The optional parameter Row of data type integer designates the row of the cell. If you do not specify a row, Plant Simulation adds the list to the end of the DataList .
- The optional parameter Name of data type string designates the name of the nested that is to be created.

Return Value

The return value has the data type list .

Is the nested list ( DataList , DataQueue , DataStack , or DataTable ) that was created.

**Example**

MyDataList.createNestedList(1,"MyNestedlist")

See also

setCommonFormat [SimTalk]

getCommonFormat [SimTalk] setCommonFormatData [SimTalk] - lists getCommonFormatData [SimTalk] - lists Activating and Deactivating Common Format Creating Lists within Lists and Tables createNestedList [SimTalk] - DataQueue createNestedList [SimTalk] - DataTable createNestedList [SimTalk] - local variable

##### determineRange [SimTalk] - DataList

Resolves the actual list range for the DataList designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.determineRange(Range:listrange, byRef StartColumn:integer, byRef StartRow:integer, byRef EndStartColumn:integer, byRef EndRow:integer)
```

**Parameters**

The method assigns the boundaries of the list range to the variables, which you define:

- The parameter Range of data type listrange designates the range of the list.
- The local variable StartColumn of data type integer designates the number of the first column of the range.
- The local variable StartRow of data type integer designates the number of the first row of the range.
- The local variable EndStartColumn of data type integer designates the number of the last column of the range.
- The local variable EndRow of data type integer designates the number of the last row of the range.

**Example**

```simtalk
param a: any
var fromX, fromY, toX, toY: integer
if isListRange(a)
	myDataList.determineRange(a, fromX, fromY, toX, toY)
	print "{",fromY,"}..{",toY,"}"
end // You can call this method like this: myMethod({*}) myMethod({1}..{*}) // range with a user-defined row index myMethod({#7}..{*})
```

**See also**

Specifying a Range of Cells [several columns] &gt; Column index belongs to contents Specifying a Range of Cells [several columns] &gt; Column index does not belong to contents remove [SimTalk] - DataList Removes the contents of a cell from the DataList designated by &lt;Path&gt; and returns it.

Remarks

The DataList moves all cells with an index greater than the designated index up by one position.

Type

Method

Syntax

```simtalk
< Path >.remove(Row:integer) → any
```

Parameter

The parameter Row of data type integer designates the position of the cell.

Return Value

The return value has the data type any .

The data type of the return value matches the data type of the DataList .

Example

```simtalk
value := MyDataList.remove(2)
```

SimTalk

cutRow [SimTalk] - DataTable

See also

Remove Row [context menu, lists]

**Read-Only Attributes of the DataList**

Read-Only Attributes of the DataList

The DataList provides:

- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- formula-not-decoded -->

#### Attributes of the DataList

#### Attributes of the DataList

The DataList provides:

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
myDataList.InfoflowReadOnly := true
print myDataList.InfoflowReadOnly
posit := Station.Cont.XPos
```

#### DataStack

