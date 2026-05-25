### DataStack

Use the DataStack for accessing data is accessed according to the LIFO method ( L ast I n F irst O ut).

Icon

<!-- image -->

**Description**

The objects DataQueue and DataStack are lists with one column. They share all methods and attributes , but differ in their built-in properties.

- Plant Simulation accesses the content of the DataStack using the LIFO method ( L ast I n F irst O ut).
- Plant Simulation accesses the content of the DataQueue using the FIFO method ( F irst I n F irst O ut).

<!-- image -->

To show a tooltip with information about the DataStack , hover with the mouse over it.

To change the length of the graphic and the anchor points of the DataStack , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the DataStack to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

InformationFlow &gt; DataStack on the Home ribbon tab.

See also

Properties of the DataQueue

#### Properties of the DataStack

The objects DataStack and DataQueue are lists with one column. They share all methods and attributes , but differ in their built-in properties.

- Plant Simulation accesses the content of the DataStack using the LIFO method ( L ast I n F irst O ut). Plant Simulation inserts new entries at the top of the DataStack and removes the contents of the cell you added last first.
- Plant Simulation accesses the content of the DataQueue using the FIFO method ( F irst I n F irst O ut). Plant Simulation saves entries you add in the order you insert them in and removes the item waiting in the queue the longest first.

You can access the functions of the list objects on the List Ribbon Tab .

**Note**

The DataStack always opens in the background behind any open dialog boxes. You can also open it in the foreground as a dialog box with the method openDialogBox .

The data type Stack shares the built-in properties of the DataStack .

Note the difference between the object DataStack , which you insert into your model, and the data type stack . You can create user-defined attributes and local and global variables of data type stack that are part of another object and thus are not an object of their own and do not have their own icon.

For this reason these variables and attributes do not recognize the SimTalk functions of the DataStack , such as Location or existsIcon . All other methods, especially for read and write access, apply to both the DataStack and to variables and attributes.

See also

Work with Data in a List or Table in the Plant Simulation Step-by-Step Help

Access Data in Lists in the Plant Simulation Step-by-Step Help

Creating a List within a DataQueue or DataStack

#### Window of the DataStack

Double-click the icon of the DataStack to open its window. In the window you can change its simulation properties . The shared properties are described under Dialog Items of the Objects . You can access the functions of the list objects on the List Ribbon Tab .

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**List Ribbon Tab**

The List Ribbon Tab provides commands pertaining to the lists and tables. Not all list objects provide all of the described commands.

<!-- image -->

#### Methods of the DataStack

#### Methods of the DataStack

The DataStack and the DataQueue provide the methods listed in the table of contents to the left for accessing them.

The DataStack and the DataQueue provide:

- The methods :

createNestedList [SimTalk] - DataQueue pop [SimTalk] - DataStack push [SimTalk] - Stack pushList [SimTalk] top [SimTalk]

- The Methods of Lists and Tables .
- The Methods of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

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

#### Read-Only Attributes of DataQueue and DataStack

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

##### Attributes of DataQueue and DataStack

Attributes of DataQueue and DataStack

The DataStack and the DataQueue provide:

- The Attributes of Lists and Tables .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

