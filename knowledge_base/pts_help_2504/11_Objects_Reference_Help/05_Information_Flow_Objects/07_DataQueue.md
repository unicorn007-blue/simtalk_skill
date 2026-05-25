### DataQueue

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDataStack.MaxDim := -1
MyDataQueue.Alignment := "left"
print myDataStack.MaxDim
posit := Station.Cont.XPos
```

**DataQueue**

#### DataQueue

Use the DataQueue for accessing data according to the using the LIFO method ( L ast I n F irst O ut).

Icon

<!-- image -->

**Description**

The objects DataQueue and DataStack are lists with one column. They share all methods and attributes , but differ in their built-in properties.

- Plant Simulation accesses the content of the DataQueue using the FIFO method ( F irst I n F irst O ut). Plant Simulation saves entries you add in the order you insert them in and removes the item waiting in the queue the longest first.
- Plant Simulation accesses the content of the DataStack using the LIFO method ( L ast I n F irst O ut). Plant Simulation inserts new entries at the top of the DataStack and removes the contents of the cell you added last first.

<!-- image -->

To show a tooltip with information about the DataQueue , hover with the mouse over it.

To change the length of the graphic and the anchor points of the DataQueue , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

<!-- image -->

To add the DataQueue to your simulation model, click InformationFlow &gt; DataQueue on the Home ribbon tab.

See also

Properties of the DataQueue Manage Class Library &gt; Basic Objects &gt;

#### Properties of the DataQueue

The DataQueue is a list with one column that Plant Simulation accesses using the FIFO method ( F irst I n F irst O ut).

Plant Simulation saves entries you add in the order you insert them in and removes the item waiting in the queue the longest first.

You can access the functions of the list objects on the List Ribbon Tab .

**Note**

The DataQueue always opens in the background behind any open dialog boxes. You can also open it in the foreground as a dialog box with the method openDialogBox .

The data type Queue shares the built-in properties of the DataQueue .

Note the difference between the object DataQueue , which you insert into your model, and the data type queue . You can create user-defined attributes and local and global variables of data type queue that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason these variables and attributes do not recognize the SimTalk functions of the DataQueue , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataQueue and to variables and attributes.

See also

Work with Data in a List or Table in the Step-by-Step Help

Access Data in Lists in the Step-by-Step Help

Creating a List within a DataQueue or DataStack

#### Window of the DataQueue

Double-click the icon of the DataQueue to open its window. In the window you can change its simulation properties . The shared properties are described under Dialog Items of the Objects . You can access the functions of the list objects on the List Ribbon Tab .

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**List Ribbon Tab**

The List Ribbon Tab provides commands pertaining to the lists and tables. Not all list objects provide all of the described commands.

<!-- image -->

#### Methods of DataQueue and DataStack

\_Methods of DataQueue and DataStack

The DataStack and the DataQueue provide:

- The methods listed in the table of contents to the left.
- The Methods of Lists and Tables .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- ◦ The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

If a parameter has a default value, the signature shows the default value after the parameter If the method has a return value, the signature shows its data type after the arrow -&gt;.

**· We use these abbreviations for the signature:**

| Argument of data type   | Data type      | Range of values            |
|-------------------------|----------------|----------------------------|
| integer                 | integer        | integer greater than zero  |
| any                     | all data types | depending on the data type |
| listrange               | -              | a range                    |
| direction               | string         | "up", "down", " "          |
| attributes              | string         | name of an attribute       |

createNestedList [SimTalk] - DataQueue

Creates a nested list in the DataStack or DataQueue designated by &lt;Path&gt;.

Remarks

The DataStack or DataQueue has to be of data type list , stack , queue , or table .

Plant Simulation moves existing entries down one position. When you specify an index, which is greater than the greatet valid index, Plant Simulation places the entry at the first available position in the list, regardless of the actual index, preventing gaps between entries.

Type

Method

Syntax

```simtalk
< Path >.createNestedList([Name:string]) → list
```

Parameter

The optional parameter Name of data type string designates the name of the list to be created.

Return Value

The return value has the data type list .

Is the nested list ( DataList , DataQueue , DataStack , or DataTable ) that was created.

Example

MyDataStack.createNestedList("My Sublist")

SimTalk

setCommonFormat [SimTalk]

getCommonFormat [SimTalk]

setCommonFormatData [SimTalk] - lists

getCommonFormatData [SimTalk] - lists Activating and Deactivating Common Format Creating Lists within Lists and Tables createNestedList [SimTalk] - DataList createNestedList [SimTalk] - DataTable createNestedList [SimTalk] - local variable pop [SimTalk] - DataStack pop [SimTalk] - DataStack Removes the first cell from a list with one column designated by &lt;Path&gt;.

Remarks

DataStack and DataQueue cut the entries according to their built-in properties.

Type

Method

Syntax

&lt; Path &gt;.pop

Return Value

The data type of the return value matches the data type of the DataStack or the DataQueue .

Example

```simtalk
value := MyDataStack.pop -- removes the first cell from MyDataStack
value := MyDataQueue.pop -- removes the last cell from MyDataQueue
```

push [SimTalk] - Stack

Adds the specified cell at the first position of the list with one column designated by &lt;Path&gt;.

Remarks

DataStack and DataQueue add the entries according to their built-in properties.

Type

Method

Syntax

< Path >.push(Cell:any)

Parameter

The parameter Cell of data type any designates the cell.

Example

```simtalk
MyDataStack.push("bottles") -- adds the cell containing the string bottles -- as the first cell to MyDataStack
MyDataQueue.push("cans") -- adds the cell containing the string cans -- as the last cell to MyDataQueue
```

**See also**

pop [SimTalk] - DataStack

**pushList [SimTalk]**

##### pushList [SimTalk]

Places the list designated by the parameter of data type any into the DataStack or the DataQueue designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.pushList(List:any)

**Parameter**

The parameter List of data type any has to reference a list of data type stack , queue , a list, or a single column of data type table .

Use the method copy if you only want to place a range of a list into a DataStack or a DataQueue .

The data types of the data you want to insert have to match the data types of the DataStack or DataQueue into which you insert it.

**Example**

// pastes the contents of the DataList into the DataStack MyDataStack.pushList(MyDataList.copy) // pastes the specified range from the DataList, starting in cell 4, // into the DataQueue MyDataQueue.pushList(MyDataList.copy({4}..{*}))

##### top [SimTalk]

Reads the contents of a cell in a list with one column without removing it.

Remarks

The DataStack and the DataQueue designated by &lt;Path&gt; set the position of the cell according to their built-in properties.

Type

Method

Syntax

&lt; Path &gt;.top

**Example**

print MyDataStack.top

##### Read-Only Attributes of DataQueue and DataStack

Read-Only Attributes of DataQueue and DataStack

The DataStack and the DataQueue provide:

- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of DataQueue and DataStack

Attributes of DataQueue and DataStack

The DataStack and the DataQueue provide:

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
MyDataStack.MaxDim := -1
MyDataQueue.Alignment := "left"
print myDataStack.MaxDim
posit := Station.Cont.XPos
```

#### TimeSequence

