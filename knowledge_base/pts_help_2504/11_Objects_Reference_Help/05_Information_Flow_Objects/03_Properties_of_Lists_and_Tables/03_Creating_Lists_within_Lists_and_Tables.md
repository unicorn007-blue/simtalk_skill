#### Creating Lists within Lists and Tables

Creating Lists within Lists and Tables

Create Lists within Lists and Tables in the Step-by-Step help describes how to:

- Create a sublist in a cell of the list objects DataList , DataStack , DataQueue or DataTable .
- Insert a list object from a Frame or the Class Library into a cell of the list objects.

**See also**

createNestedList [SimTalk] - DataQueue

createNestedList [SimTalk] - DataList

createNestedList [SimTalk] - DataTable

Creating a List within a DataQueue or DataStack

Creating a List within a DataList

Creating a List within a DataTable

Accessing the Name of a Sublist with a Method

Creating a List within a DataQueue or DataStack

Creating a List within a DataQueue or DataStack

To create a sublist or a subtable in objects of type DataQueue or DataStack :

- Add the sublist to a cell within the object, compare Creating Lists within Lists and Tables .
- Insert a list object from the Class Library into your simulation model: Drag that object to the active cell of the DataQueue / DataStack and drop it there. This inserts the path to and the name of the list or table into the active cell. Compare Insert a List into a DataTable from a Frame .
- Assign a DataList to a DataQueue or a DataStack in a Method .

###### Assign a DataList to a DataQueue or a DataStack in a Method

Within a Method you can declare a local variable of data type Stack , Queue , List , and Table .

After you created a list of these types, you can assign it to cells in a queue or stack . Initially, all of the cells of the local variable are void .

<!-- image -->

Only when Plant Simulation creates the list, by executing the method create [SimTalk] - local list , it will actually create it and enter a pointer to this new list into the DataList . The graphic below illustrates this.

**Syntax**

&lt;Local-variable&gt;.create

<!-- image -->

Now you can enter data. Our list will then look like this:

<!-- image -->

**Example**

```simtalk
var l: list[string]
l.create
l.insert(1,"Hello")
```

You can then insert this list into another list, as illustrated below (see also Common Format [check box] ).

**See also**

createNestedList [SimTalk] - DataQueue

createNestedList [SimTalk] - DataList

createNestedList [SimTalk] - DataTable

Creating a List within a DataList

Creating a List within a DataList

To create a list or table in an object of type DataList .

- Add the sublist to a cell within the object, compare Creating Lists within Lists and Tables .
- Insert a List into a DataList from a Frame , drag that object to the active cell of the DataList and drop it there. This inserts the path to and the name of the list or table into the active cell.
- Assign a List to a DataList in a Method .

<!-- image -->

###### Insert a List into a DataList from a Frame

When you insert a list object from the Class Library into your simulation model, it will be empty, as it is unknown at this time how many rows it will contain.

Only when Plant Simulation creates the list, by executing the method create [SimTalk] - local list , it will actually create it and enter a pointer to this new list into the DataList .

<!-- image -->

**Syntax**

&lt;DataListPath &gt;.createNestedList(integer)

The expression &lt;DataList-path&gt; is the name of the DataList in which Plant Simulation creates the entry designated by the parameter of data type integer . This list has the data type you specified. The method create can access every cell. If you type in an index that is greater than the largest index permitted, Plant Simulation inserts the entry into the first blank cell of the list, regardless of the actual index. That is to say a list never has blank cells. If you create a list in a cell that already contains another list, Plant Simulation moves all entries up one position in the index.

Let us say we have a DataList of data type stack[string] without entries:

MyDataList.createNestedList(5) // create first entry MyDataList.read(1).insert(1,"hello")

The method DataList.read(1) returns the contents of cell 1 of the DataList , a stack of data type string .

Using the method insertList [SimTalk] and the parameter, you can now insert text into the stack. The graphic below illustrates that.

<!-- image -->

###### Assign a List to a DataList in a Method

Within a Method you can assign a local variable of data type Stack , Queue , List , and Table . After you created a list of these types, you can assign it to cells in a list . Initially, all of the cells of the local variable are void .

Only when Plant Simulation creates the list, by executing the method create [SimTalk] - local list , it will actually create it and enter a pointer to this new list into the DataList .

**Syntax**

<Local-variable>.create

Now, you can enter values.

**Example**

```simtalk
var s: stack[string]
s.create
s.insert("Hello")
```

You can then insert this list into another list, as illustrated below (see also Common Format [check box] ).

<!-- image -->

**See also**

createNestedList [SimTalk] - DataQueue

createNestedList [SimTalk] - DataList

createNestedList [SimTalk] - DataTable

###### Creating a List within a DataTable

##### Creating a List within a DataTable

To create a list or table in an object of type DataTable .

- Add the sublist to a cell within the object, compare Creating Lists within Lists and Tables .
- Insert a List into a DataTable from a Frame , drag that object to the active cell of the DataTable and drop it there. This inserts the path to and the name of the list or table into the active cell.
- Assign a List to a DataTable in a Method .

###### Insert a List into a DataTable from a Frame

When you insert a DataTable from the Class Library into your simulation model, it will be empty as it is unknown at this time how many columns and rows it will contain.

Only when Plant Simulation creates the DataTable , by running the method createNestedList , it will actually create it and enter a pointer to this new list into the DataTable .

<!-- image -->

**Syntax**

&lt; Path &gt;.createNestedList(index1,index2)

The expression Path designates the name of the DataTable in which Plant Simulation creates the subtable designated by the parameter [index1,index2].

The method create can access every position. If you create a list in an entry that already contains an entry, Plant Simulation , overwrites the existing entry.

Let us say we have a DataTable some of whose cells contain other DataTables :

**Example**

```simtalk
MyDataTable.createNestedList(2,1) // creates the first entry MyDataTable[2,1][1,1] := "Hello"  // DataTable in DataTable
```

The method DataTable[2,1] returns the table occupying the first cell on the table. Accessing the index at the coordinates [1,1] and using an assignment you now may enter a string into the table, as illustrated below.

**See also**

createNestedList [SimTalk] - DataQueue

createNestedList [SimTalk] - DataList

createNestedList [SimTalk] - DataTable

<!-- image -->

###### Assign a List to a DataTable in a Method

Within a Method you can declare a local variable of data type Stack , Queue , List , and Table . After you created a list of these types, you can assign it to cells in a table .

Initially, all of the cells of the local variable are void .

<!-- image -->

Only when Plant Simulation creates the list as a local variable, by executing the method create [SimTalk] - local list , and when assigning it, it will actually create it and enter a pointer to this new list into the DataTable .

**Example**

&lt;Local-variable&gt;.create

<!-- image -->

You now may enter values.

**Example**

```simtalk
var t: table[string,string]
t.create
t[1,1] := "Hello"
```

<!-- image -->

You can then insert this list into another list, as illustrated below (see also Common Format [check box] ).

<!-- image -->

**SimTalk**

create [SimTalk] - local list

createNestedList [SimTalk] - DataTable

setCommonFormat [SimTalk]

getCommonFormat [SimTalk]

##### Accessing the Name of a Sublist with a Method

To open the sublist, which is contained in a cell of type Stack , Queue , List , and Table , hold down Shift and double-click into the cell.

Instead, you can also right-click the cell and select Open Object or click in the text box, and press F2 .

<!-- image -->

Use the attribute Name to access the name of the sublist via information flow.

**Example**

```simtalk
var str: string
str := .Models.MyPlantAnytown.SteeringTypes ["Jacks","9149"].Name // returns the value of the cell that contains the subtable, 4 in the example
```

**See also**

Creating Lists within Lists and Tables

Name [SimTalk] - DataTable

**Methods of Lists and Tables**

