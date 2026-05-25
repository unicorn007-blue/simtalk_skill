#### Read-Only Attributes of Lists and Tables

\_Read-Only Attributes of Lists and Tables

Lists and tables provide the read-only attributes listed in the table of contents to the left for returning their state.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyDataTable.Full Dim [SimTalk] - lists Returns the dimension, i.e., the number of entries, of the list/table designated by &lt;Path&gt;.

Remarks

For a DataTable the dimension is the product of x-dimension times the y-dimension.

The read-only attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Dim → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print MyDataStack.Dim
number := MyDataQueue.Dim
print MyDataList.Dim
number := table.Dim
```

##### Empty [SimTalk] - lists

Empty [SimTalk] - lists

Returns if the list/table designated by &lt;Path&gt; contains blank cells (true) or no blank cells (false).

Remarks

The read-only attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Empty → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyDataQueue.Empty
print MyDataList.Empty
print MyDataTable.Empty
```

SimTalk

Full [SimTalk] - lists

Occupied [SimTalk] - lists Full [SimTalk] - lists Returns if the list/table designated by &lt;Path&gt; is full (true) or not (false).

Remarks

Normally the number of entries/cells in a list/table is unlimited, meaning it will never be full. You can limit the number of cells in the dialog or with the attributes MaxDim or MaxXDim and MaxYDim though.

The read-only attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Full → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyDataStack.Full
print MyDataList.Full
print MyDataTable.Full
```

SimTalk

Empty [SimTalk] - lists

Occupied [SimTalk] - lists

MaxDim [SimTalk]

MaxXDim [SimTalk]

MaxYDim [SimTalk]

##### Occupied [SimTalk] - lists

Returns if at least one cell of the list/table designated by &lt;Path&gt; contains an entry (true) or not (false).

Remarks

The read-only attribute applies to the objects DataStack , DataQueue , DataList , DataTable , and TimeSequence .

Type

Read-only attribute

Syntax

```simtalk
< Path >.Occupied → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyDataStack.Occupied
print MyDataList.Occupied
print MyDataTable.Occupied
```

SimTalk

Empty [SimTalk] - lists

Full [SimTalk] - lists

