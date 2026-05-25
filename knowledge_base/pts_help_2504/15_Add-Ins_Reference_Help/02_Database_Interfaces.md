## Database Interfaces

Plant Simulation provides database interface objects to connect to SQLite , to ODBC , and to Oracle 11g databases.

Plant Simulation provides these database interfaces:

SQLite . It gives access to the embedded SQLite database engine. SQLite is a software library that implements a self-contained, server-less, zero-configuration, transactional SQL database engine.

ODBC [object] . It connects to any existing data source which you set up beforehand. To provide several database connections, duplicate the object ODBC in the Class Library as often as you need to.

Oracle11g/Oracle 19c [object] . It establishes a connection with an external Oracle database. The object Oracle11g may establish a connection to any Oracle database server in the computer network that your local computer can access.

<!-- image -->

To add them to the Class Library , click Manage Class Library &gt; Basic Objects &gt; InformationFlow on the Home tab.

<!-- image -->

<!-- image -->

#### SQLite

**SQLite**

### SQLite

The object SQLite gives access to the embedded SQLite database engine. SQLite is a software library that implements a self-contained, server-less, zero-configuration, transactional SQL database engine.

Icon

<!-- image -->

**Description**

For more information about SQLite , consult http://www.sqlite.org . According to this website SQLite is the most widely deployed SQL database engine in the world. The source code for SQLite is in the public domain.

The SQLite database engine implements most of the SQL92 standard as good as possible, meaning that you can use every book about SQL92 as a reference. There is also extensive documentation available on the website of SQLite . From the website you also can download a small program, called sqlite3.exe , to access the database without using Plant Simulation .

This SQLite database engine is embedded in Plant Simulation . You can access it with the object SQLite .

When you open a file-based SQLite database , Plant Simulation applies the following default settings, which deactivate transaction support:

PRAGMA locking\_mode=EXCLUSIVE

PRAGMA journal\_mode=NORMAL

**PRAGMA synchronous=OFF**

These settings considerably accelerate access to the database.

To restore the SQLite default settings, which support transactions, you can use the following instructions:

SQLite.exec("PRAGMA locking_mode=NORMAL") SQLite.exec("PRAGMA journal_mode=DELETE") SQLite.exec("PRAGMA synchronous=FULL")

To show a tooltip with information about the SQLite Interface , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the SQLite Interface , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

To add SQLite to the Class Library , click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt;

SQLite on the Home ribbon tab.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Exchange Data with an SQL Database

#### Dialog Box of the SQLite Interface

Dialog Box of the SQLite Interface

Double-click the icon of the SQLite Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Filename [SQLite]

Click the folder icon and select the database file in the dialog Open .

<!-- image -->

Or type in the File Name of the database from which you want to import data. Or enter the name of the database to which you want to export data. Plant Simulation creates the file in the folder, in which you stored the simulation model. Your computer will only show the file once the simulation model executes SQL commands.

If you do not enter a File Name for the database, Plant Simulation creates it in memory. This is the same as if you had entered :memory: .

<!-- image -->

The default setting :memory: means that the database will be stored in main memory instead of in a file on the hard disk. This greatly improves performance and access speed. Be aware that all data will be lost when you close the simulation model or if Plant Simulation crashes!

**Note**

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer [model settings] , SQLite can still work with the database in memory. It cannot save the database or create it in the file system though.

**SimTalk**

FileName [SimTalk] - SQLite

**Statements**

###### Statements

To save the statements of often used SQL statements, click this button.

<!-- image -->

Then, type in the statement into the table that opens. You might, for example, type select * from TestTable .

You can activate one of the saved statements with the method useStatement by specifying its row number in the table.

<!-- image -->

**SimTalk**

<!-- image -->

###### Delete File [SQLite]

To delete the database file, whose name is contained in the text box Filename from the hard disk drive, click this button.

<!-- image -->

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The commands are described under the View Menu .

SimTalk

updateDialog [SimTalk]

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the SQLite Interface**

#### \_Methods of the SQLite Interface

The SQLite Interface provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

**bindInteger [SimTalk]**

##### bindInteger [SimTalk]

Binds the parameter IntegerToBind to the parameter in the current prepared SQL statement of the SQLite object designated by &lt;Path which has the number of the parameter ArgumentIndex .

Type

Method

Syntax

&lt; Path &gt;.bindInteger(ArgumentIndex:integer, IntegerToBind:integer)

**Parameters**

- The parameter ArgumentIndex of data type integer designates the number to which the parameter IntegerToBind is going to be bound.
- The parameter IntegerToBind of data type integer designates the number that is going to be bound to the parameter ArgumentIndex .

**Example**

```simtalk
MySQLite.prepare("INSERT INTO MUTrace (MUName, MUType, StartTime) VALUES (? 1, ?2, ?3)")
MySQLite.bindString(1, obj_to_str(@))
MySQLite.bindString(2, @.name)
MySQLite.bindReal(3, EventController.simTime)
MySQLite.step
```

**See also**

bindReal [SimTalk]

bindString [SimTalk]

executeStatement [SimTalk]

Statements

##### bindReal [SimTalk]

Binds the parameter RealToBind to the parameter in the current prepared SQL statement of the SQLite object designated by &lt;Path&gt; which has the number of the parameter type ArgumentIndex .

Type

Method

Syntax

```simtalk
< Path >.bindReal(ArgumentIndex:integer, RealToBind:real)
```

**Parameters**

- The parameter ArgumentIndex of data type integer designates the number to which the parameter RealToBind is going to be bound.
- The parameter RealToBind of data type real designates the number that is going to be bound to the parameter ArgumentIndex .

**Example**

```simtalk
MySQLite.prepare("INSERT INTO MUTrace (MUName, MUType, StartTime) VALUES (? 1, ?2, ?3)")
MySQLite.bindString(1, obj_to_str(@))
MySQLite.bindString(2, @.name)
MySQLite.bindReal(3, EventController.simTime)
MySQLite.step
```

**See also**

bindInteger [SimTalk]

bindString [SimTalk]

executeStatement [SimTalk]

Statements

**bindString [SimTalk]**

##### bindString [SimTalk]

Binds the parameter StringToBind to the parameter in the current prepared SQL statement of the SQLite object designated by &lt;Path&gt; which has the number of the parameter ArgumentIndex .

Type

Method

Syntax

&lt; Path &gt;.bindString(ArgumentIndex:integer, StringToBind:string)

**Parameters**

- The parameter ArgumentIndex of data type integer designates the number to which the parameter StringToBind is going to be bound.
- The parameter StringToBind of data type string designates the string that is going to be bound to the parameter ArgumentIndex .

**Example**

```simtalk
MySQLite.prepare("INSERT INTO MUTrace (MUName, MUType, StartTime) VALUES (? 1, ?2, ?3)")
MySQLite.bindString(1, obj_to_str(@))
MySQLite.bindString(2, @.name)
MySQLite.bindReal(3, EventController.simTime)
MySQLite.step
```

**See also**

bindInteger [SimTalk]

bindReal [SimTalk]

executeStatement [SimTalk]

Statements close [SimTalk] - SQLite Closes the database connection of the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.close

Example

MySQLite.close

See also

open [SimTalk] - SQLite

**createTable [SimTalk]**

##### createTable [SimTalk]

Creates the designated SQL table with the contents of the source table in the SQLite object designated by &lt;Path.

Type

Method

Syntax

&lt; Path &gt;.createTable(TableName:string, SourceTable:table)

**Parameters**

- The parameter TableName of data type string designates the name of the SQL table to be created.
- The parameter SourceTable of data type table designates the name of the source table whose contents will be created.

**Example**

MySQLite.createTable("MyDataBaseTable", MySourceTable)

**See also**

dropTable [SimTalk]

dropTable [SimTalk]

Deletes the specified SQLite table from the SQLite database .

Type

Method

Syntax

```simtalk
< Path >.dropTable(TableName:string)
-> void
```

Parameter

The parameter TableName of data type string designates the name of the SQL table to be deleted.

Return Value

The return value is void.

Example

MySQLite.dropTable("MySQLTable")

See also

createTable [SimTalk]

##### exec [SimTalk]

exec [SimTalk]

Executes an SQL command of the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.exec(SQLString:string)
```

Parameter

The parameter SQLString of data type string designates the command.

For the SQL syntax you can consult any book about SQL92 or you can check the web site of SQLite .

Example

MySQLite.exec("CREATE TABLE MUTrace (MUName TEXT PRIMARY KEY, MUType TEXT, StartTime REAL, EndTime REAL)")

See also

[http://www.sqlite.org](http://www.sqlite.org/)

**executeStatement [SimTalk]**

Executes the saved SQL statement of the SQLite object designated by &lt;Path&gt;.

**Remarks**

executeStatement combines the methods useStatement , bindInteger , bindReal , bindString , step , and resetStatement .

Type

Method

Syntax

```simtalk
< Path >.executeStatement(StatementHandle:integer[, SQLParameter:any, ...])
-> any
```

**Parameters**

- The parameter StatementHandle of data type integer designates the SQL statement.

The StatementHandle can either be the return value of the method storeStatement or the number of the SQL statement in the list of the saved SQL instructions which the button Statements opens.

The StatementHandles which storeStatement returns are negative .

The StatementHandles for the SQL statements in the list of the saved SQL instructions are positive .

- The optional parameter SQLParameter of data type any designates the required parameter of the SQL statement.

**Return Value**

The return value has the data type any .

executeStatement only returns a value if the result of the executed SQL statement yields a single value. Otherwise the return value is void .

**Example**

```simtalk
// step 1:
MySQLite.prepare("insert into TestTabelle values (?1, ?2, ?3)")
var statementHandle := SQLite.storeStatement // step 2:
MySQLite.executeStatement(statementHandle, "Name", 1, 3.14) // provided the columns of the table have the data types string, integer, and real
```

See also Statements useStatement [SimTalk] bindInteger [SimTalk] bindReal [SimTalk] bindString [SimTalk] step [SimTalk] - SQLite resetStatement [SimTalk] storeStatement [SimTalk]

##### finalize [SimTalk]

Deletes a prepared statement of the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.finalize

Example

MySQLite.finalize

getColumn [SimTalk]

getColumn [SimTalk]

Returns the contents of the specified column the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getColumn(ColumnIndex:integer) → any
```

Parameter

The parameter ColumnIndex of data type integer designates the column number.

Return Value

The return value depends on the data type of the column in the database. It has the data type any .

Example

print MySQLite.getColumn(1)

##### getColumnCount [SimTalk]

Returns the number of columns of the data which is returned by the last executed SQL statement of the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getColumnCount

Example

print MySQLite.getColumnCount

##### getColumnInteger [SimTalk]

getColumnInteger [SimTalk]

Returns the contents of the specified column of the SQLite object designated by &lt;Path&gt; as an integer number.

Type

Method

Syntax

```simtalk
< Path >.getColumnInteger(ColumnIndex:integer) → integer
```

Parameter

The parameter ColumnIndex of data type integer designates the column number.

Return Value

The return value has the data type integer .

Example

print MySQLite.getColumnInteger(0)

##### getColumnReal [SimTalk]

Returns the contents of the specified column of the SQLite object designated by &lt;Path&gt; as a real number.

Type

Method

Syntax

```simtalk
< Path >.getColumnReal(ColumnIndex:integer) → real
```

Parameter

The parameter ColumnIndex of data type integer designates the column number.

Return Value

The return value has the data type real .

Example

print MySQLite.getColumnReal(0)

##### getColumnString [SimTalk]

getColumnString [SimTalk]

Returns the contents of the specified column of the SQLite object designated by &lt;Path&gt; as a string .

Type

Method

Syntax

```simtalk
< Path >.getColumnString(ColumnIndex:integer) → string
```

Parameter

The parameter ColumnIndex of data type integer designates the column number.

Return Value

The return value has the data type string .

Example

```simtalk
MySQLite.prepare("SELECT * FROM MUTrace")
while MySQLite.step
	print MySQLite.getColumnString(0), " ", MySQLite.getColumnString(1), " ", MySQLite.getColumnReal(2), " ", MySQLite.getColumnReal(3)
end
```

loadFromFile [SimTalk]

Loads an SQLite database, stored in a file, into an in-memory database of the SQLite object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.loadFromFile(Filename:string)

Parameter

The parameter Filename of data type string designates the file name of the SQLite database.

Example

MySQLite.loadFromFile("MySQLDatabaseFile")

See also

saveToFile [SimTalk]

open [SimTalk] - SQLite open [SimTalk] - SQLite

Opens the database of the SQLite object designated by &lt;Path&gt;. You have to open the database before any SQL command can be executed.

Remarks

When you open a file-based SQLite database , Plant Simulation applies the following default settings, which deactivate transaction support:

PRAGMA locking\_mode=EXCLUSIVE

PRAGMA journal\_mode=NORMAL

PRAGMA synchronous=OFF

These settings considerably accelerate access to the database.

To restore the SQLite default settings, which support transactions, you can use the following instructions:

SQLite.exec("PRAGMA locking_mode=NORMAL") SQLite.exec("PRAGMA journal_mode=DELETE") SQLite.exec("PRAGMA synchronous=FULL")

To speed up database performance, we recommend to use the following settings instead:

SQLite.exec("PRAGMA locking_mode = EXCLUSIVE") SQLite.exec("PRAGMA journal_mode = MEMORY") SQLite.exec("PRAGMA synchronous = OFF")

For more information, consult the SQL website. .

Type

Method

Syntax

```simtalk
< Path >.open[ReadOnly:boolean := false]
```

Parameter

The optional parameter ReadOnly of data type boolean sets if the database can be opened in read-only mode ( true ) or can also be written to ( false ).

**Default Value of the Parameter**

The default value is false. This way Plant Simulation can read the database even if the access to the computer is prohibited is active.

**Example**

MySQLite.open

**See also**

[http://www.sqlite.org](http://www.sqlite.org/)

close [SimTalk] - SQLite

Prohibit Access to the Computer [model settings]

##### prepare [SimTalk]

prepare [SimTalk]

Prepares an SQL command of the SQLite object designated by &lt;Path&gt; for execution.

Type

Method

Syntax

```simtalk
< Path >.prepare(SQLString:string)
```

Parameter

The parameter SQLString of data type string designates the SQL command. You can insert parameters into this statement which can be replaced with values using the methods bindString , bindInteger , and bindReal .

The parameters have to start with a ? followed by a number.

Example

```simtalk
MySQLite.prepare("INSERT INTO MUTrace (MUName, MUType, StartTime) VALUES (? 1, ?2, ?3)")
MySQLite.bindString(1, obj_to_str(@))
MySQLite.bindString(2, @.name)
MySQLite.bindReal(3, EventController.simTime)
MySQLite.step
```

See also

bindString [SimTalk]

bindInteger [SimTalk]

bindReal [SimTalk]

remove [SimTalk] - SQLite

Deletes the database file of the SQLite object designated by &lt;Path&gt; from the hard disk drive.

Type

Method

Syntax

&lt; Path &gt;.remove -&gt; boolean

Return Value

The return value has the data type boolean .

true if Plant Simulation deleted the file.

false if an error occurred and the file could not be deleted. Make sure that the file exists and is not read-only.

Example

MySQLite.remove

See also

Delete File [SQLite]

**resetStatement [SimTalk]**

##### resetStatement [SimTalk]

Resets a prepared statement of the SQLite object designated by &lt;Path&gt; to its initial state, ready to be re-executed.

Remarks

Any SQL statement variables which had values bound to them retain their values.

Type

Method

Syntax

&lt; Path &gt;.resetStatement

Example

MySQLite.resetStatement

See also

executeStatement [SimTalk]

saveToFile [SimTalk]

Saves the in-memory database of the SQLite object designated by &lt;Path&gt; into an SQLite database file.

Type

Method

Syntax

&lt; Path &gt;.saveToFile(Filename:string)

Parameter

The parameter Filename of data type string designates the file name of the SQLite database.

Example

MySQLite.saveToFile("MySQLDatabase")

See also

loadFromFile [SimTalk]

```simtalk
sql [SimTalk] - SQLite Executes the provided SQL statement of the SQL object designated by <Path>. Type Method Syntax sql [SimTalk] - SQLite
< Path >.sql([Result:table, ]SQLString:string)
-> integer < Path >.sql([Result:table, ]SQLString:string[, SQLParameter:any, ...])
-> integer
```

**Parameters**

- If an SQL command returns a result, the first optional parameter in the method call must define a results table of data type table that is to receive the data. The format of this table (number of columns, column index, data type of the column) depends on the result of the SELECT query and is generated automatically.
- The parameter SQL string of data type string designates the sql string.

SQLite.sql(MyResultsTable, "select * from xyz")

In the SQL statement text you can replace literals with a parameter that matches one of following templates:

◦ ? ◦ ?NNN ◦ :VVV ◦ @VVV ◦ $VVV

You can use one of the methods bindString , bindInteger , and bindReal to bind a value to this parameter.

In the templates above, NNN represents an integer literal, and VVV represents an alphanumeric identifier.

- The leftmost SQL parameter has an index of 1. When the same named SQL parameter is used more than once, second and subsequent occurrences have the same index as the first occurrence. The index for " ?NNN " parameters is the value of NNN .
- The optional parameters SQLParameters of data type any designate additional parameters which you can specify.

**Return Value**

The return value has the data type integer .

**Examples**

SQLite.sql("delete from xyz")

```simtalk
var uid: integer
var type: string uid := 1
type := "U"
SQLite.sql(dataInput, "SELECT name FROM xyz WHERE\ uid = ?1 AND type = ?2", uid, type)
```

**See also**

bindString [SimTalk]

bindInteger [SimTalk]

bindReal [SimTalk]

##### step [SimTalk] - SQLite

step [SimTalk] - SQLite

Executes the prepared statement of the SQLite object designated by &lt;Path&gt; and reads the first line of data.

Remarks

The prepared statement can either be created by a call of the method prepare or by a call to the method useStatement .

You can retrieve the data:

- By specifying the parameters into which the data will be written.
- By calling one of the methods getColumn , getColumnInteger , getColumnReal , or getColumnString .

Type

Method

Syntax

```simtalk
< Path >.step([byRef ColumnValue:any, ...])
-> boolean
```

**Parameter**

The parameter ColumnValue of data type any designated the columns into which the data will be written.

Return Value

The return value has the data type boolean .

- true means that there are additional data sets which can be retrieved by further calls of the method step .
- false means that no further data is available.

**Example**

```simtalk
MySQLite.open
MySQLite.prepare("SELECT * FROM employees")
var columnName:string
var columnAge:integer
while MySQLite.step(columnName, columnAge)
	print columnName+": "+to_str(columnAge)
end
```

See also Statements executeStatement [SimTalk] useStatement [SimTalk] getColumn [SimTalk] getColumnInteger [SimTalk] getColumnReal [SimTalk] getColumnString [SimTalk] prepare [SimTalk]

**storeStatement [SimTalk]**

##### storeStatement [SimTalk]

Saves the current SQL expression of the SQLite object designated by &lt;Path&gt;, which has been prepared with the method prepare , for later re-use.

Type

Method

Syntax

```simtalk
< Path >.storeStatement → integer
```

Return Value

The return value has the data type integer .

You can use the return value in the method useStatement to activate the saved SQL expression.

**Note**

Returned values are negative, they start with -1 and decrement by 1 (-2, -3, etc.) each time a storeStatement is executed.

**Example**

```simtalk
SQLite.prepare("INSERT INTO BETrace (BEName, BEType, StartTime) VALUES (? 1, ?2, ?3)")
var iReturnedValue : integer := SQLite.storeStatement()
print iReturnedValue  // first execution of storeStatement results in  -1
```

**See also**

Statements

executeStatement [SimTalk]

useStatement [SimTalk]

prepare [SimTalk]

##### useStatement [SimTalk]

Activates the SQL expression of the SQLite object designated by &lt;Path&gt;, which you saved with the method storeStatement .

Type

Method

Syntax

```simtalk
< Path >.useStatement(StatementHandle:integer)
```

Parameter

The parameter StatementHandle of data type integer designates the number of the SQL expression.

Example

```simtalk
SQLite.useStatement(1)
SQLite.bindString(1, obj_to_str(@))
SQLite.bindString(2, @.name)
SQLite.bindReal(3, EventController.simTime)
SQLite.step
```

See also

Statements

executeStatement [SimTalk]

storeStatement [SimTalk]

#### Read-Only Attributes of the SQLite Interface

Read-Only Attributes of the SQLite Interface

The SQLite Interface provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MySQLite.IsOpen IsOpen [SimTalk] - SQLite Returns if the database of the SQLite object designated by &lt;Path&gt; is open (true) at the moment or not open (false).

Remarks

The database is the text file into which data is to be written or from which data is to be imported.

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsOpen → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MySQLite.IsOpen
```

See also

Filename [SQLite]

FileName [SimTalk] - SQLite

open [SimTalk] - SQLite

**SQLiteVersion [SimTalk]**

##### SQLiteVersion [SimTalk]

Returns the version of the SQL library which the object SQLite designated by &lt;Path&gt; uses.

Syntax

```simtalk
< Path >.SQLiteVersion → string
```

Type

Read-only attribute

Return Value

The return value has the data type string .

Example

```simtalk
print SQLiteVersion // might
return "3.36.0"
```

#### Attributes of the SQLite Interface

Attributes of the SQLite Interface

The SQLite Interface provides:

- The attribute FileName [SimTalk] - SQLite .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MySQLite.FileName := "C:\users\johnE\myData.txt"
print MySQLite.FileName
posit := Station.cont.XPos
```

FileName [SimTalk] - SQLite

Sets the filename of the database of the SQLite object designated by &lt;Path&gt; from which you want to import data.

Remarks

You can also enter the file name :memory: . Then the database is stored in main memory instead of in a file on the hard disk. This greatly improves performance and access speed. Be aware that all data will be lost when you close the simulation model or if Plant Simulation crashes!

**Note**

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , SQLite can still work with the database in memory. It cannot save the database or create it in the file system.

Type

Attribute

Syntax

```simtalk
< Path >.FileName:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MySQLite.FileName := ":memory:"
```

See also

Filename [SQLite]

Prohibit Access to the Computer [model settings]

### ODBC

#### ODBC [object]

The object ODBC connects to any existing data source which you set up beforehand. To provide several database connections, duplicate the object ODBC in the Class Library as often as you need to.

**Icon**

<!-- image -->

**Description**

Plant Simulation can access a wide variety of data sources via the ODBC interface . The advantage of the ODBC (Open Database Connectivity) interface over product-specific interfaces is that it enables you to access different data sources, such as Microsoft Excel , dBase , and text files as well as Database Management Systems (DBMS) such as Oracle or Informix , as long as the corresponding drivers are installed on your computer.

Plant Simulation and the data source communicate via the ODBC Driver Manager and the ODBC Database Driver .

Plant Simulation implements the ODBC interface employing so called ODBC calls. This interface enables you to establish a connection to any data source, for which an ODBC driver is available, to define SQL run time statements and to send those to the data source.

Microsoft Windows provides the ODBC Driver Manager by default. It will load and manage the driver needed for specific tasks. The drivers form the ODBC interface for the data source and are provided by Dynamic Link Libraries (DLLs). They are divided in Single Tier and Multiple Tier drivers.

- Single Tier drivers are intended for data sources that do not have an SQL interface, such as Microsoft Excel , dBase or text files . In this case, the driver processes the ODBC calls and the SQL statements. The driver converts them into elementary file operations. These drivers usually limit the SQL statements offered. As a minimum they have to provide the minimum commands defined by ODBC.
- Multiple Tier drivers require a server that processes the SQL statements and is the interface to the data source. The driver processes ODBC calls and forwards the SQL commands to the server. It is also possible to define DBMS specific calls. Other calls are modified by the driver to fit the syntax required by DBMS. Multiple Tier drivers are intended for typical client/server architectures, such as Oracle , Informix or Sybase . The combination of application and driver forms the client.

**Note**

You need 64-bit ODBC drivers for the object ODBC . Starting with Microsoft Office 2010 Microsoft provides 64-bit ODBC drivers for Access , Excel , etc.

You cannot install 64-bit ODBC drivers in parallel to a 32-bit-version of Microsoft Office.

To show a tooltip with information about the ODBC Interface , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the ODBC Interface , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the ODBC interface to the Class Library , click InformationFlow &gt; ODBC on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also Setting the ODBC User Data Source Up ODBC Data Types Import Data from a Database Import Data from an ODBC Database

#### Setting the ODBC User Data Source Up

Select Start &gt; Control Panel &gt; Administrative Tools &gt; Data Sources [ODBC] to set up the user database. Click Add in the window Create New Data Source . Pick the driver you need. Enter the settings for the data source in the window that opens.

**Note**

You do not necessarily have to set up a user data source. If you just want to access the data source via Plant Simulation , you can also temporarily establish the connection with the data source with the method driverConnect . In this case you do not have to enter anything into the control panel or into the dialog of the object ODBC in Plant Simulation .

<!-- image -->

**See also**

Set the Data Source Up

#### ODBC Data Types

The column DATA\_TYPES of the table Data Types shows which of the ODBC data types the used driver actually supports.

For data, which you load into a Plant Simulation DataTable via a SELECT statement, the data type mapping in column 3 of the following table apply.

The mapping of the Informix data types to the data type of the table is as follows:

| ODBC data type   | Description                                                                       | Plant Simulation data type        |
|------------------|-----------------------------------------------------------------------------------|-----------------------------------|
| CHAR(n)          | Text with a fixed length of n (1 = n = 254)                                       | String                            |
| VARCHAR          | Text with a variable length; the maximum length is n (1 = n = 254)                | String                            |
| LONG VARCHAR     | Text with a variable length; the maximum length depends on the data source        | String                            |
| DECIMAL(p,s)     | Fixed-point number with precision p and s decimals (1 = p = 15; 0 = s = p)        | Real (s>0 or p>0) Integer (other) |
| NUMERIC(p,s)     | Analog to DECIMAL                                                                 | Real (s>0 or p>0) Integer (other) |
| INTEGER          | Numeric value n (-2(31) = n = 2(31)-1)                                            | Integer                           |
| SMALLINT         | Numeric value n (-32768 = n = 32767)                                              | Integer                           |
| REAL             | Floating-point number; significant digits 7                                       | Real                              |
| FLOAT            | Floating-point number; significant digits 15                                      | Real                              |
| DOUBLE PRECISION | Analog to FLOAT                                                                   | Real                              |
| BIT              | Binary data (1-Bit)                                                               | Boolean                           |
| TINYINT          | Numeric value n (-128 = n = 127)                                                  | Integer                           |
| BIGINT           | Numeric value n (-2(63) = n = 2(63)-1)                                            | Integer                           |
| BINARY(n)        | Binary data with a fixed length of n (1 = n = 255)                                | not defined                       |
| VARBINARY(n)     | Binary data with a variable length; the maximum length is n (1 = n = 255)         | not defined                       |
| LONG VARBINARY   | Binary data with a variable length; the maximum length depends on the data source | not defined                       |

| ODBC data type   | Description   | Plant Simulation data type   |
|------------------|---------------|------------------------------|
| DATE             | Date          | Date                         |
| TIME             | Time          | Time                         |
| TIMESTAMP        | Date/time     | DateTime                     |

See also

Data Types [button] - ODBC

#### Dialog Box of the ODBC Interface

Dialog Box of the ODBC Interface

Double-click the icon of the ODBC Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### Database [text box] - ODBC

Select or enter the name of the Database ( Data Source Name ), which you assigned, when you created the user data source.

<!-- image -->

To work with the default server, you do not have to enter anything. The default server usually is the local server. The list shows all data sources which are available on your computer network.

**Note**

The connection string that you specify here depends on your database provider. Consult the documentation of your database provider for more information.

**SimTalk**

DataBase [SimTalk] - ODBC

**Driver**

##### Driver

To open the table Info Driver , click this button.

<!-- image -->

The table shows information about the used driver.

<!-- image -->

| Entry               | Description                                                                                                                                                              |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Driver Name         | Name of the driver                                                                                                                                                       |
| Driver Version      | Version of the driver                                                                                                                                                    |
| Driver ODBC Version | ODBC version which the driver supports                                                                                                                                   |
| ODBC Version        | ODBC version which the Driver Manager supports                                                                                                                           |
| API Conformance     | The API Conformance Levels define a fixed functionality which the driver can realize to meet a defined level. Possible values are None , Level1 , or Level2              |
| SAG Conformance     | Shows if all functions, which are set by SAG (SQL Access Group), are supported by the driver. Possible values are SAG compliant or Not SAG compliant .                   |
| SQL Conformance     | Shows the SQL grammar which the driver supports. Possible values are Minimum , Core , or Extended .                                                                      |
| File Usage          | Is important for Single-Tier -drivers only. It shows if the driver treats a file as a table or as a database. Possible values are Not supported , Table , or Qualifier . |
| Number Connections  | Shows the maximum number of concurrently active connections. The value 0 stands for an unlimited number of connections.                                                  |
| Number Statements   | Shows how many instructions can be active at the same time for this driver. The value 0 stands for an unlimited number of instructions.                                  |

**SimTalk**

**InfoDriver [SimTalk]**

##### Data Source [ODBC]

To open the table Info Data Source , click this button.

<!-- image -->

The table shows information about the used data source.

<!-- image -->

| Entry               | Description                                                                                                                                                                                                                                                                                                                                                    |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DBMS name           | Name of the DBMS (database management system)                                                                                                                                                                                                                                                                                                                  |
| DBMS version        | Version of the DBMS                                                                                                                                                                                                                                                                                                                                            |
| Server name         | Name of the server belonging to the data source                                                                                                                                                                                                                                                                                                                |
| Database name       | Name of the current database. This can also be a folder, for example for dBase , or a file, for example for Access .                                                                                                                                                                                                                                           |
| Qualifier location  | Shows if a qualifier (database name) stands at the start or at the end of a table name identifier. Possible values are Qualifier at the start or Qualifier at the end .                                                                                                                                                                                        |
| Qualifier separator | Shows the qualifier separator.                                                                                                                                                                                                                                                                                                                                 |
| Qualifier name      | Qualifier name of the DBMS developer, for example DATABASE for Access or Workbook for Excel .                                                                                                                                                                                                                                                                  |
| Qualifier usage     | Lists the instruction groups in which a qualifier can be specified. Possible values are DML_STATEMENTS (all data manipulation statements), PROCEDURE_INVOC (procedure invocation statement), TABLE_DEF (all instructions for defining tables), INDEX_DEF (all instructions for defining indexes), or PRIVILEGE_DEF (all instructions for defining privileges). |

**SimTalk**

**InfoDataSource [SimTalk]**

**Data Types [button] - ODBC**

##### Data Types [button] - ODBC

To open the table Info Data Types , click this button.

<!-- image -->

The table shows information about the supported data types. The table shows the data types which the selected ODBC data source supports.

<!-- image -->

**SimTalk**

**InfoDataTypes [SimTalk]**

##### User Name [ODBC]

Type in the User Name with which you want to log in to the ODBC database.

**Note**

You only have to type in the User Name and the Password for data sources that support user management.

**Password [ODBC]**

##### Password [ODBC]

<!-- image -->

Type in the Password for accessing the database.

**Note**

You only have to type in the User Name and the Password for data sources that support user management.

Save

To save the Password in the model file in encrypted form, select this.

##### Stop on Errors [ODBC]

To stop the execution of the active method and to show the SQL error in the Debugger when an SQL error occurs, select this check box.

To continue executing the Method , clear the check box.

The method sqlError returns the error number as an integer value. This way you can react on the error within the method.

SimTalk

ErrorStop [SimTalk] - ODBC

sqlError [SimTalk]

##### Format Table [check box] - ODBC

Format Table [check box] - ODBC

To automatically format the data table according to the requirements, select this check box.

<!-- image -->

Clear the check box and select if the driver ( Data Conversion by Driver ) or Plant Simulation ( Data Conversion by Application ) converts the data.

SimTalk

ConvertingDataDriver [SimTalk]

FormatTable [SimTalk]

##### Message [ODBC]

Plant Simulation shows the message that was returned for the last interaction with the database here.

SimTalk

sqlError [SimTalk]

##### Login [button] - ODBC

Login [button] - ODBC

To log in to the database, click this button.

<!-- image -->

After a successful Login , you can click the buttons Driver , Data Source , and Data Types to open tables containing information about the current driver/data source connection.

Instead, you can also click the object ODBC with the right mouse button in the Frame and select Activate on the context menu.

To deactivate it, select Deactivate on the context menu.

SimTalk

login [SimTalk] - ODBC [SimTalk]

##### Logout [button] - ODBC

To log out of the database, click this button.

<!-- image -->

Instead, you can also click the object ODBC with the right mouse button in the Frame and select Deactivate on the context menu.

SimTalk

logout [SimTalk] - ODBC

**Methods of the ODBC Interface**

#### \_Methods of the ODBC Interface

The ODBC Interface provides:

- The methods listed in the table of contents to the left.
- The Methods of the Material Flow Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- formula-not-decoded -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

beginTrans [SimTalk]

Starts a transaction of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.beginTrans → integer
```

Return Value

The return value has the data type integer .

Example

ODBC.beginTrans

See also

commitTrans [SimTalk]

**commitTrans [SimTalk]**

##### commitTrans [SimTalk]

Terminates the transaction of the object designated by &lt;Path&gt; and applies your changes.

Type

Method

Syntax

&lt; Path &gt;.commitTrans

Example

ODBC.commitTrans

See also

beginTrans [SimTalk]

deleteRows [SimTalk] - ODBC

Makes the object designated by &lt;Path&gt; delete all rows from a database table.

Type

Method

Syntax

```simtalk
< Path >.deleteRows(SQLTable:string) → boolean
```

Parameter

The parameter SQLTable of data type string designates the name of the database table.

Return Value

The return value has the data type boolean .

Example

ODBC.deleteRows("Name\_of\_Table")

**driverConnect [SimTalk]**

##### driverConnect [SimTalk]

Establishes a connection of the object designated by &lt;Path&gt; to a data source.

Type

Method

Syntax

```simtalk
< Path >.driverConnect(ConnectString:string) → string
```

Parameter

The parameter ConnectString of data type string designates the name of the connection string.

The syntax of the connection string depends on the type of the data source. In our example the connection string is called once for the MS-Access data source and once for the MS Excel data source.

Return Value

The return value has the data type string .

Examples

```simtalk
var tab: table
var path, file: string
var tempdir, str: string
path := "C:\\temp"
file := "test.mdb"
tempdir := "C:\temp"
// reading a table from of an access database
str := "DRIVER=Microsoft Access Driver(*.mdb);DBQ="+path+"\\"+file
str := str+";DefaultDir="+tempdir+";DriverId=281;FIL=MS Access;MaxBufferSize=2048;PageTimeout=5;"
ODBC_mdb.driverconnect(str)
ODBC_mdb.sql( tab, "select * from dataTable;")
// read data from an excel sheet. // remember the 'datafield' has to be defined in the excel sheet
file := "test.xls"
str := "Driver=Microsoft Excel Driver (*.xls);FIRSTROWHASNAMES=1;READONLY=FALSE;CREATE_DB=";
str := str + path+ "\\" + file
str := str + ";DBQ="+ path + "\\" + file + ";"
ODBC_XLS.DriverConnect( str )
ODBC_xls.sql( tab, "select * from datafield;" )
```

**See also**

Setting the ODBC User Data Source Up insertTable [SimTalk] - ODBC

Makes the object designated by &lt;Path&gt; insert a Plant Simulation table into the database table.

Type

Method

Syntax

```simtalk
< Path >.insertTable(SourceData:any, SQLTable:string) → boolean
```

**Parameters**

- The parameter SourceData of data type any designates the Plant Simulation table.
- The parameter SQLTable of data type string designates the database table.

Return Value

The return value has the data type boolean .

Example

ODBC.insertTable(DataTable,"Name_of_Table")

See also

readTable [SimTalk] - ODBC

##### login [SimTalk] - ODBC

Establishes a connection of the object designated by &lt;Path&gt; to a database.

Type

Method

Syntax

```simtalk
< Path >.login(Database:string, UserName:string, Password:string) → boolean
```

**Parameters**

- The parameter Database of data type string designates the database.
- The parameter UserName of data type string designates the user name.
- The parameter Password of data type string designates the password.

Return Value

The return value has the data type boolean .

true if login was successful. The password which was passed is not saved in the model.

**Example**

ODBC.login("database","billJ","bj65mc")

See also

Login [button] - ODBC

logout [SimTalk] - ODBC

##### logout [SimTalk] - ODBC

logout [SimTalk] - ODBC

Terminates the database connection of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.logout

Example

ODBC.logout

See also

Logout [button] - ODBC

login [SimTalk] - ODBC

##### readTable [SimTalk] - ODBC

Makes the object designated by &lt;Path&gt; read the contents of a Plant Simulation table from a database table .

Type

Method

Syntax

```simtalk
< Path >.readTable(Result:table, SQLTable:string) → integer
```

**Parameters**

- The parameter Result of data type any designates the name of the Plant Simulation table.
- The parameter SQLTable of data type string designates the name of the ODBC table.

**Return Value**

The return value has the data type integer .

**Example**

ODBC.readTable(MyDataTable,"select * from def")

**See also**

insertTable [SimTalk] - ODBC

##### rollbackTrans [SimTalk]

Terminates the transaction of the object designated by &lt;Path&gt; with the database without applying your changes.

Type

Method

Syntax

&lt; Path &gt;.rollbackTrans

Example

ODBC.rollbackTrans

**rollbackTrans [SimTalk]**

##### sql [SimTalk] - ODBC

Controls the actual communication of the object designated by &lt;Path&gt; with the data source.

Remarks

You can invoke this method within SimTalk , the information flow language of Plant Simulation .

The method sql sends SQL statements to an ODBC driver.

Syntax

```simtalk
< Path >.sql([Result:table, ]SQLString:string)
-> integer < Path >.sql([Result:table, ]SQLString:string[, SQLParameter:any, ...])
-> integer
```

Type

Method

Parameters

- If an SQL command returns a result, the first optional parameter in the method call must define a results table of data type table that is to receive the data. The format of this table (number of columns, column index, data type of the column) depends on the result of the SELECT query and is generated automatically. The list editor of Plant Simulation shows the list immediately. The data in the list is available for further use in the simulation model.
- To increase the flexibility of the calls, you can include program variables in the SQL string of data type string . The representation of program variables in the SQL statement is determined by conversion specifications which begin with the percent sign %.

```simtalk
ODBC.sql(table,"select * from xyz")
```

A conversion specification has this format:

%[flags][field format>]conversion signs

The items of the conversion specification can accept these values:

```simtalk
flags: -: left bound representation of the program variable +: display of the sign also
if the program variable is positive field format: field
	length.decimal digits conversion signs: s: string
d: integer u: positive integer o: octal x: hexadecimal f: floating point
```

If you do not want Plant Simulation to interpret the percentage sign % as a control character, enter two percentage signs %% . Each conversion specification is assigned to one parameter, which follows the SQL command. In this example, the database table xyz is accessed and entries from the column name are passed to the SQL command and are put in the Plant Simulation data table dataInput.

```simtalk
var uid : integer
var type : string uid := 1
type := "U"
ODBC.sql(dataInput, "SELECT name FROM xyz WHERE\ uid = %d AND type = '%s'", uid, type)
```

In this example we write data from Plant Simulation into a database.

```simtalk
var uid : integer
var type : string uid := 5 t
ype := "Z"
ODBC.sql("UPDATE xyz SET type = '%s' WHERE\ uid = %d", type, uid)
```

- The optional parameters SQLParameters of data type any designate additional parameters which you can specify.

**Return Value**

The return value has the data type integer .

**Example**

ODBC.insertTable(DataTable,"Name_of_Table") ODBC.sql("delete from xyz")

##### sqlError [SimTalk]

Returns the SQL state, the error code, and the error message of the most recent SQL command of the object designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.sqlError(byref SQLState:string, byref ErrorCode:integer, byref ErrorMessage:string)
```

**Parameters**

- The parameter SQLState of data type string designates the SQL state of the most recent SQL command.
- The parameter ErrorCode of data type integer designates its error code.
- The parameter ErrorMessage of data type string designates the error message.

**Example**

```simtalk
var sSQLError, sErrorMessage : string
var nErrorCode : integer
ODBC.sqlError(sSQLError, nErrorCode, sErrorMessage) MessageBox(to_str(sErrorMessage, strChr(10), "SQLError=", sSQLError, strChr(10), "ErrorCode=", nErrorCode))
```

**See also**

Stop on Errors [ODBC]

Message [ODBC]

##### updateTable [SimTalk] - ODBC

updateTable [SimTalk] - ODBC

Makes the object designated by &lt;Path&gt; update the database table with the values from the Plant Simulation table.

Type

Method

Syntax

```simtalk
< >.updateTable(SourceData:table, SQLTable:string, ColumnNumber:integer)
Path → boolean
```

**Parameters**

- The parameter SourceData of data type table designates the Plant Simulation table.
- The parameter SQLTable of data type string designates the database table.
- The parameter RowNumber of data type integer designates the primary index used to identify which rows of the tables match.

Return Value

The return value has the data type boolean .

Example

```simtalk
// the contents of row 3 of the Plant Simulation table replaces // the existing contents of row 3 of the database table
ODBC.updateTable(DataTable,"Name_of_Table",3)
```

#### Read-Only Attributes of the ODBC Interface

\_Read-Only Attributes of the ODBC Interface

The ODBC Interface provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyODBC.InfoDataSource

**InfoDataSource [SimTalk]**

##### InfoDataSource [SimTalk]

Returns the data source table of the object designated by &lt;Path&gt;.

Remarks

The table shows these values.

| Entry               | Description                                                                                                                                                                                                                                                                                                                                                    |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DBMS name           | Name of the DBMS (database management system)                                                                                                                                                                                                                                                                                                                  |
| DBMS version        | Version of the DBMS                                                                                                                                                                                                                                                                                                                                            |
| Server name         | Name of the server belonging to the data source                                                                                                                                                                                                                                                                                                                |
| Database name       | Name of the current database. This can also be a folder, for example for dBase , or a file, for example for Access .                                                                                                                                                                                                                                           |
| Qualifier location  | Shows if a qualifier (database name) stands at the start or at the end of a table name identifier. Possible values are Qualifier at the start or Qualifier at the end .                                                                                                                                                                                        |
| Qualifier separator | Shows the qualifier separator.                                                                                                                                                                                                                                                                                                                                 |
| Qualifier name      | Qualifier name of the DBMS developer, for example DATABASE for Access or Workbook for Excel .                                                                                                                                                                                                                                                                  |
| Qualifier usage     | Lists the instruction groups in which a qualifier can be specified. Possible values are DML_STATEMENTS (all data manipulation statements), PROCEDURE_INVOC (procedure invocation statement), TABLE_DEF (all instructions for defining tables), INDEX_DEF (all instructions for defining indexes), or PRIVILEGE_DEF (all instructions for defining privileges). |

Type

Read-only attribute

Syntax

&lt; Path &gt;.InfoDataSource → table

Return Value

The return value has the data type table .

**Example**

TableVariable := ODBC.InfoDataSource

**See also**

Data Source [ODBC]

##### InfoDataTypes [SimTalk]

InfoDataTypes [SimTalk]

Returns the data type table of the object designated by &lt;Path&gt;.

Remarks

The table shows the data types which the selected ODBC data source supports.

Type

Read-only attribute

Syntax

```simtalk
< Path >.InfoDataTypes → table
```

Return Value

The return value has the data type table .

Example

```simtalk
TableVariable := ODBC.InfoDataTypes
```

See also

Data Types [button] - ODBC

##### InfoDriver [SimTalk]

Returns the driver table of the object designated by &lt;Path&gt;.

Remarks

The table shows these values.

| Entry               | Description                                                                                                                                                              |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Driver Name         | Name of the driver                                                                                                                                                       |
| Driver Version      | Version of the driver                                                                                                                                                    |
| Driver ODBC Version | ODBC version which the driver supports                                                                                                                                   |
| ODBC Version        | ODBC version which the Driver Manager supports                                                                                                                           |
| API Conformance     | The API Conformance Levels define a fixed functionality which the driver can realize to meet a defined level. Possible values are None , Level1 , or Level2              |
| SAG Conformance     | Shows if all functions, which are set by SAG (SQL Access Group), are supported by the driver. Possible values are SAG compliant or Not SAG compliant .                   |
| SQL Conformance     | Shows the SQL grammar which the driver supports. Possible values are Minimum , Core , or Extended .                                                                      |
| File Usage          | Is important for Single-Tier -drivers only. It shows if the driver treats a file as a table or as a database. Possible values are Not supported , Table , or Qualifier . |
| Number Connections  | Shows the maximum number of concurrently active connections. The value 0 stands for an unlimited number of connections.                                                  |
| Number Statements   | Shows how many instructions can be active at the same time for this driver. The value 0 stands for an unlimited number of instructions.                                  |

Type

Read-only attribute

Syntax

```simtalk
< Path >.InfoDriver → table
```

Return Value

The return value has the data type table .

**Example**

```simtalk
TableVariable := ODBC.InfoDriver
```

See also

Driver

#### Attributes of the ODBC Interface

##### \_Attributes of the ODBC Interface

The ODBC Interface provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
.ODBC.Transaction := false
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print .ODBC.Transaction
posit := Station.cont.XPos
```

##### ConvertingDataDriver [SimTalk]

Sets that the driver ( true ) converts the data or that Plant Simulation does that ( false ) for the object designated by &lt;Path&gt;.

Remarks

You can only do this if you specified false for the attribute FormatTable .

Type

Attribute

Syntax

&lt; Path &gt;.ConvertingDataDriver:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyODBC.ConvertingDataDriver := true
```

See also

Format Table [check box] - ODBC

FormatTable [SimTalk]

**DataBase [SimTalk] - ODBC**

Designates the name of an ODBC server for the object designated by &lt;Path&gt; which can be reached within the computer network. SQL*Net determines the format.

Remarks

To work with the default server, you do not have to specify anything. The default server usually is the local server.

**Note**

The connection string that you enter here depends on your database provider. Consult the documentation of your database provider for more information.

Type

Attribute

Syntax

&lt; Path &gt;.DataBase:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
ODBC.Database := "ODBC"
```

See also

Database [text box] - ODBC

**ErrorStop [SimTalk] - ODBC**

Sets if Plant Simulation continues processing the method when an error occurs within the SQL call of the object designated by &lt;Path&gt; ( true ) or if it opens the Debugger ( false ).

Remarks

If ErrorStop is true , Plant Simulation stops the execution of the method and shows the error in the Debugger .

If ErrorStop is false , Plant Simulation does not stop the execution of the method.

The method sqlError returns the number of the error as an integer value allowing you to correct the source code.

Type

Attribute

Syntax

```simtalk
< Path >.ErrorStop:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyODBC.ErrorStop := false
print MyODBC.errorStop
```

See also

Stop on Errors [ODBC]

sqlError [SimTalk]

##### FormatTable [SimTalk]

Sets if Plant Simulation automatically formats the data table according to the requirements ( true ) or not ( false ).

Remarks

Specify false to use the attribute ConvertingDataDriver to set if the driver ( true ) converts the data or if Plant Simulation does that ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.FormatTable:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyODBC.FormatTable := true
```

See also

Format Table [check box] - ODBC

ConvertingDataDriver [SimTalk]

**Transaction [SimTalk]**

##### Transaction [SimTalk]

Sets how transactions in the SQL call of the object designated by &lt;Path&gt; are treated.

Remarks

If Transaction is set to true , the executed SQL commands will not be terminated automatically as a transaction . In this case it is supposed that the SQL statement is part of a complex transaction. Indicate the termination of the transaction by an additional SQL call.

If Transaction is set to false , every SQL statement, passed with the method sql , will be completed as a transaction .

Type

Attribute

Syntax

&lt; Path &gt;.Transaction:boolean

**Assignment Value**

You can assign a value of data type boolean .

Example

```simtalk
ODBC.Transaction := false
```

See also

sql [SimTalk] - ODBC

### Oracle11g/Oracle 19 c

#### Oracle11g/Oracle 19c [object]

The object Oracle11g establishes a connection with an external Oracle database. The object Oracle11g may establish a connection to any Oracle database server in the computer network that your local computer can access.

**Icon**

<!-- image -->

**Description**

You can establish a maximum of six simultaneous connections to different database servers. Duplicate the object Oracle11g for each connection in the Class Library .

**Note**

Plant Simulation supports Oracle Netclients Version 11g to access Oracle databases. Oracle Netclient 11g can also access Oracle databases of Version 10.x or older.

If you use the Oracle SQL*Net Netclient, it has to be installed on the computer on which you are running Plant Simulation . Within the Oracle-Administration you have to configure the Netclient, so that you can access the database that contains the data you want to use.

**Note**

Consult the documentation that came with your Oracle database, when it shows error messages.

To show a tooltip with information about the Oracle Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Oracle Interface , click Show

**Manipulators**

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the object Oracle to the Class Library , click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Oracle on the Home ribbon tab.

<!-- image -->

<!-- image -->

See also

Import Data from an Oracle Database

##### Dialog Box of the Oracle11g Interface

Dialog Box of the Oracle11g Interface

Double-click the icon of the Oracle11g Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**Database [text box] - Oracle**

##### Database [text box] - Oracle

Select or specify the name of an Oracle server into the text box Database that may be reached over a computer network.

<!-- image -->

SQL*Net determines the format. To work with the default server, you do not have to specify anything. The default server usually is the local server.

**Note**

The connection string that you specify here depends on your database provider.

Consult the documentation of your database provider for more information.

**SimTalk**

DataBase [SimTalk] - Oracle

**User Name [Oracle]**

Type in the User Name with which you want to log in to the Oracle database.

The database has to know this name. The database administrator has to register the user with the database.

**Password [Oracle]**

##### Password [Oracle]

Type in your Password for accessing the database.

Save

To save the Password in the model file in encrypted form, select this.

##### Stop on Errors [Oracle]

To stop the execution of the active method and to show the SQL error in the Debugger when an SQL error occurs, select this check box. To continue executing the Method , clear the check box.

The method sql returns the number of the error as an integer value allowing you to correct the source code.

SimTalk

ErrorStop [SimTalk] - Oracle

sql [SimTalk] - Oracle

**Message [Oracle]**

##### Message [Oracle]

Plant Simulation shows the message that was returned for the last interaction with the database here.

##### Login [button] - Oracle

To log in to the database, click this button.

<!-- image -->

SimTalk

login [SimTalk] - Oracle

##### Logout [button] - Oracle

Logout [button] - Oracle

To log out of the database, click this button.

<!-- image -->

#### Methods of the Oracle11g Interface

##### \_Methods of the Oracle11g Interface

The Oracle11g Interface provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

deleteRows [SimTalk] - Oracle

deleteRows [SimTalk] - Oracle

Deletes all rows from a database table of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteRows(SQLTable:string) → boolean

Parameter

The parameter SQLTable of data type string designates the name of the database table.

Return Value

The return value has the data type boolean .

Example

MyOracle.deleteRows("Name\_of\_Database\_Table")

##### insertTable [SimTalk] - Oracle

Inserts the contents of a Plant Simulation table into a database table of the object designated by &lt;Path&gt; .

Type

Method

Syntax

```simtalk
< Path >.insertTable(SourceTable:table, SQLTable:string) → boolean
```

**Parameters**

- The parameter SourceTable of data type table designates the Plant Simulation table.
- The parameter SQLTable of data type string designates the database table.

Return Value

The return value has the data type boolean .

true if login was successful. The password is not saved in the model file.

**Example**

MyOracle.insertTable(MyDataTable, "Name_of_Database_Table")

**See also**

readTable [SimTalk] - Oracle

##### login [SimTalk] - Oracle

login [SimTalk] - Oracle

Establishes a connection of the object designated by &lt;Path&gt; to a database.

Type

Method

Syntax

```simtalk
< Path >.login(Database:string, UserName:string, Password:string) → boolean
```

**Parameters**

- The parameter Database of data type string designates the database.
- The parameter UserName of data type string designates the user name.
- The parameter Password of data type string designates the password. The password does not appear in the dialog box.

Return Value

The return value has the data type boolean .

**Example**

MyOracle.login("Our Company Database","SYSTEM","manager")

See also

Login [button] - Oracle

logout [SimTalk] - Oracle logout [SimTalk] - Oracle Terminates the database connection of the object designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.logout

Example

MyOracle.logout

See also

Logout [button] - Oracle

login [SimTalk] - Oracle

**readTable [SimTalk] - Oracle**

##### readTable [SimTalk] - Oracle

Makes the object designated by &lt;Path&gt; read the contents of a Plant Simulation table from a database table .

Type

Method

Syntax

```simtalk
< Path >.readTable(Result:table, SQLTable:string) → integer
```

**Parameters**

- The parameter Result of data type table designates the name of the Plant Simulation table.
- The parameter SQLTable of data type string designates the name of the Oracle table.

Return Value

The return value has the data type integer .

**Example**

MyOracle(.MyDataTable,"select * from abc")

**See also**

insertTable [SimTalk] - Oracle

##### sql [SimTalk] - Oracle

Controls the communication of the object designated by &lt;Path&gt; with the database server by sending SQL statements.

Remarks

Plant Simulation Oracle supports all SQL commands. The sql call is passed as a parameter of data type string .

Plant Simulation returns the resulting error code, i.e., the contents of sqlca.sqlcode. An example would be -955 for a create call for an already existing table. The error message in the dialog box is ORA-00955: name is already used by an existing object .

Type

Method

Syntax

```simtalk
< Path >.sql([Result:table, ]SQLString:string) → integer < Path >.sql([Result:table, ]SQLString:string[, SQLParameter:any, ...]) → integer
```

**Parameters**

- If a SQL command returns result lines, the first optional parameter of the method call must define a results table of data type table that is to receive the data. The format of the table, i.e., the number of columns, names of columns, data types of columns, depend on the result of the database query and are created automatically. Data from this list is then available for further use in the simulation model or may be viewed on the table editor on screen.
- To increase the flexibility of the calls, you can include program variables in the SQL string of data type string . The position of the program variable in the SQL command is marked by conversion signs and has this format:

```simtalk
%[flags][field format]conversion signs -: left bound representation of the program variable +: sign displayed
if program variable is positive field format: field length.[decimal digits] conversion signs: s: string d: integer u: positive integer o: octal x: hexadecimal f: floating point
```

**sql [SimTalk] - Oracle**

If you do not want Plant Simulation to interpret the percentage sign % as a control character, enter two percentage signs %% . Each conversion specification is assigned one of the parameters that follow the SQL command in the method call.

- The optional parameters SQLParameters of data type any designate additional parameters which you can specify.

**Return Value**

The return value has the data type integer .

**Example**

```simtalk
MyOracle("delete from xyz") MyOracle(.MyDataTable,"select * from xyz")
var uid : integer
var type : string uid := 1
type := "U"
MyOracle.sql("select name from xyz where uid = %d \ AND type = '%s'", uid, type)
```

**See also**

readTable [SimTalk] - Oracle

##### updateTable [SimTalk] - Oracle

Makes the object designated by &lt;Path&gt; update the database table with the values from the Plant Simulation table.

Type

Method

Syntax

```simtalk
< Path >.updateTable(SourceData:table, SQLTable:string, ColumnNumber:integer) → boolean
```

**Parameters**

- The parameter SourceData of data type table designates the Plant Simulation table.
- The parameter SQLTable of data type string designates the database table.
- The parameter ColumnNumber of data type integer designates the primary index used to identify which rows of the tables match.

Return Value

The return value has the data type boolean .

Example

```simtalk
// the contents of row 3 of the Plant Simulation table replaces the existing // contents of row 3 of the database table
MyOracle.updateTable(MyDataTable, "Name_of_Database_Table", 3)
```

#### Read-Only Attributes of the Oracle11g Interface

Read-Only Attributes of the Oracle11g Interface

The Oracle11g Interface provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyOracle11g.UUID

#### Attributes of the Oracle11g Interface

**\_Attributes of the Oracle11g Interface**

The Oracle11g Interface provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyOracle.ErrorStop := false
print
print oracle.ErrorStop
posit := Station.cont.XPos
```

##### DataBase [SimTalk] - Oracle

Designates the name of an Oracle server that the object designated by &lt;Path&gt; can reach within the computer network. SQL*Net determines the format to be applied.

Remarks

To work with the default server, you do not have to specify anything. The default server usually is the local server.

**Note**

The connection string that you enter here depends on your database provider. Consult the documentation of your database provider for more information.

Type

Attribute

Syntax

&lt; Path &gt;.DataBase:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
print.MyOracle.Database := "Oracle"
```

See also

Database [text box] - Oracle

##### ErrorStop [SimTalk] - Oracle

Sets if Plant Simulation continues processing the method when an error occurs within the SQL call of the object designated by &lt;Path&gt; ( true ) or if it opens the Debugger ( false ).

Remarks

If ErrorStop is true , Plant Simulation stops the execution of the method and shows the error in the Debugger .

If ErrorStop is false , Plant Simulation does not stop the execution of the method.

The method sql returns the number of the error as an integer value allowing you to correct the source code.

Type

Attribute

Syntax

```simtalk
< Path >.ErrorStop:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyOracle.ErrorStop := false
print MyOracle.ErrorStop
```

See also

Stop on Errors [Oracle]

sql [SimTalk] - Oracle

### Inter-Process Communication Interfaces

