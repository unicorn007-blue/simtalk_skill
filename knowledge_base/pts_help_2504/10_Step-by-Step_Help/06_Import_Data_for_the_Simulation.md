## Import Data for the Simulation

Importing Data for the Simulation shows how to work with data provided by the departments of the plant you are modeling, such as production lists, data, which machines output, etc. while you create your simulation model.

As a rule you will import this data from a spreadsheet program, such as Microsoft Excel, or from a database, into a Plant Simulation list or table. From the data bulk you will have to filter out the data you actually do need to use for your simulation project. The material flow objects can then access these lists and use the data for the simulation.

Naturally you may also want to export some or all of the data, which the simulation runs created, so that you can use and manipulate it in other programs.

### Importing and Exporting Data

#### Import and Export Data

Plant Simulation provides a number of ways to import data from other applications into Plant Simulation . In some cases you will import data into an Plant Simulation list or a table, process it there and then pass it on to the material flow objects. In other cases you will directly provide imported data to the material flow objects, for example by using the FileInterface .

You can:

- Import a Text File or an Object File into a List
- Import Data from a Microsoft Excel Worksheet
- Import a List of Services, Shifts, etc. into an Object
- Import Data in XML Format
- Import Data from a Database
- Import or Export Data in ANSI Format
- Import or Export the Contents of a List

Compare Database Interfaces

Back to Import Data for the Simulation

#### Import a Text File or an Object File into a List

The Plant Simulation lists DataTable , DataList , DataQueue , DataStack , and TimeSequence can open text files, Plant Simulation object files, XML files, and Microsoft Excel files, which contain the data you want to use in your simulation project.

- Before you open a text file, we advise to select the correct data type that fits the data you are going to import into the individual columns of the DataTable . If the text file has a column header, which you want to also use in your Plant Simulation list, activate and show the column index in the Plant Simulation list.

<!-- image -->

- To open a text file or an Plant Simulation object file in a list, click Import File on the List ribbon tab.
- Navigate to the folder where you stored the file. Select the type of file you would like to open and click Open .

<!-- image -->

<!-- image -->

Plant Simulation opened the object file with the formatting, which the original file had. For the text file we had to manually select the correct data types.

- To export the contents of an Plant Simulation list or table, click Export to File or Export Object File on the List ribbon tab.

Compare Set the Data Type of a Column

Compare Import or Export the Contents of a List

**Compare Context Menu of Embedded Lists**

Back to Import and Export Data

#### Import Data from a Microsoft Excel Worksheet

When Plant Simulation reads an MS Excel table, it attempts to convert the values in the individual columns to the data types of the columns in your Plant Simulation table. This only works, when you created the columns on the Excel worksheets so that they only contain a single data type, meaning that, when you, for example, assign the data type String to a cell of a column, the entire column may only be of data type String .

After importing the data into Plant Simulation , you have to check the data types of the individual columns, you might have to correct the type of some, and you will have to filter out data you do not need. You can either do this manually in the open Plant Simulation table, or you can program a Method to manipulate the data while importing it.

If the Excel file has a column header, which you also want to use in your Plant Simulation list, activate and show the column index in the Plant Simulation list.

<!-- image -->

- For our example we used the file MyTestData.xlsx , which looks like this in Excel.

<!-- image -->

- To open the Excel file in an Plant Simulation table, click Import File on the List ribbon tab.
- Navigate to the folder where you stored the file. Select the file you would like to open and click Open . Select the Excel worksheet you want to import and click OK .

<!-- image -->

- The imported Excel worksheet looks like this in our Plant Simulation table.

<!-- image -->

Check the file for correct data types, data you do not need, etc. You can also pre-process or post-process the data by programming a Method .

- To export the contents of a Plant Simulation list or table as an Excel file, click Export Excel File on the List ribbon tab.

Compare Import or Export the Contents of a List

Back to Import and Export Data

#### Import a List of Services, Shifts, etc. into an Object

**Note**

In most cases importing one of the mentioned lists involves two lists.

The main list contains any expression of your choice, which serves as a placeholder for the sublists. You might, for example, enter different names for the different stations. In the example below we entered Operations for MyPart A .

The second list, i.e., the sublist, contains the names of the actual stations and information pertaining to them.

<!-- image -->

To import a services list, a list of shifts or a worker creation table into one of the lists which are embedded in a Plant Simulation object:

- Open the file, which you received, in a text editor. Make sure that the text, which is to be shown in the column header, is the first line in the file. Separate the columns with tabs. Save the file as a text file (.txt).

<!-- image -->

- Open the Plant Simulation object and change to the tab Importer where you want to import the file. Click the inheritance check box to the right of Services on the sub-tab Processing so that it looks like this . Click Services .
- Right-click in the list and click Import . Navigate to the folder where you saved the text file and click OK .

<!-- image -->

<!-- image -->

<!-- image -->

If need be, you can then manipulate the contents of the list with the commands on the Context Menu of Embedded Lists . You might, for example, add rows or sort the list in ascending or descending order.

- To export the contents of an embedded list as a tab-delimited text file, right-click in the list and select Export .

Compare Specify Times During Which the Plant Works Part of the Time

Back to Import and Export Data

#### Importing Data in XML Format

Import Data in XML Format

You can import data stored in XML format into Plant Simulation and extract data from the XML file. You may, for example, use the XMLInterface to read data, which you exported from Process Designer , the Siemens program for planning, analyzing and managing manufacturing processes, or from an XML database.

You can then use the data, which the XMLInterface imported, and which you manipulated with a Method , to run a simulation in Plant Simulation . You might afterwards use the methods write and writeElement to write the simulation results back to an XML file and continue working with these simulation results in Process Designer or another program.

To get the most out of the XMLInterface , you have to be familiar with XPath ( XML Path Language ) instructions. You might, for example, check the web site http://www.w3.org/TR/xpath for more information. In addition, you have to be familiar with programming in SimTalk .

<!-- image -->

You can insert the XMLInterface into your simulation model from the folder InformationFlow in the Class Library or from the toolbar Information Flow in the Toolbox .

<!-- image -->

**You can:**

- Select File Name, Context, and Import Method
- Read and Write Data Sequentially
- Read and Access Data Randomly
- Access and Traverse Data Randomly

Back to Import and Export Data

Select File Name, Context, and Import Method

When you work with the XMLInterface , you will make extensive use of XPath (XML Path Language) instructions and of the Plant Simulation methods and attributes of the XMLInterface itself.

Into the dialog of the XMLInterface you:

- Enter the File Name of the XML file, which the XMLInterface opens, if you want to import data. When you export data, it specifies the name of the file, which it saves.
- Enter the Context of the data you want to import. The context designates the node of the structure of the XML document at which the XMLInterface starts reading data. You might, for example, enter the names of certain data, or of certain objects that you are interested in, for example Data/Objects . This

way you can restrict the data to be read, i.e., if you do not need to work with all of the data contained in the XML file, you will enter a context.

If you do not enter a context, the XMLInterface imports the entire file, which may contain a large amount of data, some of which you do not need. This might take some time to import and use up a large amount of your computer's RAM.

- Click to enter the path to and the name of the Import Method into the text box. In the Method you program how to extract and to sequentially process the imported data.

<!-- image -->

**Back to Import Data in XML Format**

Read and Write Data Sequentially

You can sequentially read the data line-by-line , write it to an Import Method , and then immediately process that data line-by-line. To restrict the amount of data to be imported, enter a Context .

This Method demonstrates how to sequentially write an XML file.

The source code looks like this:

```simtalk
XMLInterface.FileName := "D:\MSXML 4.0\writeSequentially.xml" // opens the XML document for sequential writing XMLInterface.openWrite
XMLInterface.startElement("catalog")
XMLInterface.startElement("book") // adds attributes to the item 'book'
XMLInterface.addAttribute("id", "bk01")
XMLInterface.addAttribute("xmlns","myBooks")
XMLInterface.addAttribute("xmlns:aa","specAth") // these are the children of the item 'book'
XMLInterface.writeElement("aa:author","Gambardella, Matthew")
```

// adds an attribute to the item 'author' XMLInterface.addAttribute("age","16") XMLInterface.writeElement("title","XML Developer's Guide") XMLInterface.writeElement("genre","Computer") XMLInterface.writeElement("price","44.95") XMLInterface.writeElement("publish_date","2000-10-01") XMLInterface.writeElement("description","An in-depth ...") // terminates the item 'book' XMLInterface.endElement // terminates the element 'catalog' XMLInterface.endElement XMLInterface.close

**Back to Import Data in XML Format**

Read and Access Data Randomly

You can read the data in its entirety, and then randomly process it as a whole. Here Plant Simulation imports the entire document first and then processes and analyzes all data in the Method , which you program. Randomly accessing data requires that all data you want to use is in RAM. The larger the amount of data, the more RAM the XMLInterface uses!

You might, for example:

- Select data from the XML document.

The source code looks like this:

```simtalk
// randomly accesses data via XPath instructions
var tbl:table
XMLInterface.FileName := "D:\MSXML 4.0\books.xml" // load the XML document for random access into RAM XMLInterface.openDocument // select nodes via XPath instruction // selection starts at the Context node which you entered in the XMLInterface // the second parameter is the selection depth for each node // 0 means that no children will be selected // the result is passed to a table
tbl := XMLInterface.getNodes("book[title='Midnight Rain']", 1)
XMLInterface.close
```

- Delete existing data from the XML document.

The source code looks like this:

```simtalk
// deletes all nodes specified by XPath instructions
XMLInterface.FileName := "D:\MSXML 4.0\books.xml" // load the XML document for random access into RAM XMLInterface.openDocument
// delete all book nodes of genre 'Fantasy'
XMLInterface.deleteNodes("book[genre = 'Fantasy']")
XMLInterface.FileName := "D:\MSXML 4.0\tmp.xml" // write the document to a file XMLInterface.write // remove the document from RAM XMLInterface.close
```

- Insert new data into the XML document.

The source code looks like this:

```simtalk
// inserts new data into the XML document
var tbl:table
XMLInterface.FileName := "D:\MSXML 4.0\books.xml" // load the XML document XMLInterface.openDocument // get an empty table for writing the data to // depth=1 means that we want to write nodes with children
tbl := XMLInterface.getContainer(1) // set the parent node for the new data
XMLInterface.setContext("/catalog") // designate the node to append to the 'catalog' nodes tbl[1,1] := "book" // are the attributes of the 'book' node
tbl.createNestedList(4,1) // explicit namespace tbl[4,1][1,1] := "xmlns:aa" tbl[4,1][2,1] := "specAth" // additional attributes tbl[4,1][1,2] := "id" tbl[4,1][2,2] := "bk113" // child nodes
tbl.createNestedList(5,1) tbl[5,1][1,1] := "aa:author" tbl[5,1][2,1] := "specAth" tbl[5,1][3,1] := "XYZ" tbl[5,1][1,2] := "title" tbl[5,1][3,2] := "UNKNOWN" tbl[5,1][1,3] := "genre" tbl[5,1][3,3] := "also" tbl[5,1][1,4] := "price" tbl[5,1][3,4] := "12,45" tbl[5,1][1,5] := "publish_date" tbl[5,1][3,5] := "12.1.02" tbl[5,1][1,6] := "description" tbl[5,1][3,6] := "xx0011"
XMLInterface.insertNodes(tbl) // save the changed document
XMLInterface.FileName := "D:\MSXML 4.0\tmp.xml" XMLInterface.write // close the document XMLInterface.close
```

- Update the XML document.

The source code looks like this:

```simtalk
// updates the selected nodes of the document
var tbl:table;
XMLInterface.FileName := "D:\MSXML 4.0\books.xml" XMLInterface.openDocument; // select the nodes to be changed
tbl := XMLInterface.getNodes("/catalog/book[title='Midnight Rain']", 1) // update the values tbl[5,1][3,3] := "TEST" // write the changed values
XMLInterface.updateNodes(tbl)
XMLInterface.FileName := "D:\MSXML 4.0\tmp.xml"
XMLInterface.write
XMLInterface.close
```

- Create a new XML document.

The source code looks like this:

```simtalk
// creates a new document by calling the method newDocument
var tbl:table;
XMLInterface.newDocument("catalog")
tbl := XMLInterface.getContainer(1)
XMLInterface.setContext("/catalog") // parent node tbl[1,1] := "book" // default namespace tbl[2,1] := "MyBooks" // attributes
tbl.createNestedList(4,1) // explicit namespace tbl[4,1][1,1] := "xmlns:aa" tbl[4,1][2,1] := "specAth" // additional attributes tbl[4,1][1,2] := "id" tbl[4,1][2,2] := "bk113" // child nodes
tbl.createNestedList(5,1) tbl[5,1][1,1] := "aa:author" tbl[5,1][2,1] := "specAth" tbl[5,1][3,1] := "XYZ" tbl[5,1][1,2] := "title" tbl[5,1][3,2] := "UNKNOWN" tbl[5,1][1,3] := "genre" tbl[5,1][3,3] := "also" tbl[5,1][1,4] := "price" tbl[5,1][3,4] := "12,45" tbl[5,1][1,5] := "publish_date" tbl[5,1][3,5] := "12.1.02" tbl[5,1][1,6] := "description" tbl[5,1][3,6] := "xx0011"
XMLInterface.insertNodes(tbl)
XMLInterface.FileName := "D:\MSXML 4.0\tmp.xml"
XMLInterface.write
```

**Back to Import Data in XML Format**

Access and Traverse Data Randomly

You can extract data in its entirety from an XML document and then randomly traverse the data . You might, for example, define the starting point for traversing the structure with the method selectNodes . Then, you could get the next node with the method getNodeName , check for attributes of this node with the read-only attribute GetNumberAttributes , output the names of the attributes and recursively check all children of the selected node, to detect those that meet the condition.

The source code looks like this:

```simtalk
// selects the starting nodes and calls the method visitChildren // recusively for each node var numberAttributes
XMLInterface.FileName := "D:\Public\XML\books.xml" // load the XML document to be randomly accessed into RAM XMLInterface.openDocument // select some nodes using XPath instructions
XMLInterface.selectNodes("book[genre = 'Computer']") // define the loop for the selected nodes
while XMLInterface.getNextNode = true
	print XMLInterface.getNodeName // check for attributes of the nodes
	numberAttributes := XMLInterface.getNumberAttributes
	for var i := 0 to numberAttributes-1 // print the data of the attributes print
		XMLInterface.getAttributeName(i)+":" +XMLInterface.getAttributeValue(i)
	next // check the children of the current node VisitChildren end // remove the XML document from RAM XMLInterface.close
```

**Back to Import Data in XML Format**

#### Importing Data from a Database

Import Data from a Database

You can import data from a database into Plant Simulation and run your simulation in Plant Simulation with this data. You can then write the data resulting from the simulation runs back into the database.

To get the most out of importing data from a database, you have to be familiar with SQL ( Structured Query Language ) instructions. You might, for example, check the web site http://sqlzoo.net for more information and consult the documentation that comes with the database you are using. In addition, you have to be familiar with programming in SimTalk .

You can:

- Import Data from an ODBC Database
- Import Data from an Oracle Database
- Exchange Data with an SQL Database

Back to Import and Export Data

Importing Data from an ODBC Database

Import Data from an ODBC Database

To import data from an ODBC database into your Plant Simulation simulation model, you will use the Plant Simulation object ODBC . To access several databases at the same time, you can insert several objects of type ODBC into your simulation model, each of which communicates with another database.

**Note**

The example below only runs if 64-bit ODBC drivers are installed on your 64-bit Windows operating system.

You cannot install 64-bit ODBC drivers in parallel to a 32-bit-version of Microsoft Office.

You can also access the same database with several ODBC objects. We advise against doing so, as this may result in inconsistent data caused by conflicting commands. It might, for example, happen that one Method deletes a data set, while another Method attempts to access just this data set. Using a single ODBC object ensures that the sequence of instructions conforms to your intentions.

This holds especially true for real databases for which you have to apply any data manipulations, such as read, write delete, etc. with the SQL instruction commit , before they take effect.

To import data from an ODBC database into your Plant Simulation simulation model you have to:

- Set the Data Source Up
- Import Data into Your Simulation Model

After the simulation runs are finished, you can also export the simulation results back into the database, compare Export Data to the Database .

**Back to Import Data from a Database**

###### Set the Data Source Up

Before you can import data from an ODBC database into your Plant Simulation model, you have to set up the ODBC data source on your computer:

- Type in ODBC Data Sources (64-bit) into the text box Search .
- Add a new data source in the dialog ODBC Data Source Administrator . Depending on who will use the database you can accomplish this on the tab User DSN or on the tab System DSN . As a rule you will add the data source on the tab System DSN .
- Click Add on the tab System DSN .
- In the dialog Create New Data Source select the ODBC driver for the data source you would like to use. In our example we selected the Microsoft Access Driver . Click Finish .

<!-- image -->

<!-- image -->

- Click Select in the dialog ODBC Microsoft Access Setup and select the database in the dialog Select Database . Type in the Data Source Name . If you want to, you can also add a Description of the database. As Plant Simulation addresses the database with this name, mind the Plant Simulation conventions for the Name !
- Click Select and select the database to which you want to connect.

<!-- image -->

<!-- image -->

After successfully concluding this action, the dialog ODBC Data Source Administrator shows the Data Source , which we added.

<!-- image -->

**Back to Import Data from an ODBC Database**

Import Data into Your Simulation Model

After setting-up the ODBC data source, you have to insert the object ODBC into your Plant Simulation simulation model. This object establishes the connection with the database and enables you to import data from it. You can write this data into Plant Simulation tables, change them there, use them in your simulation runs, and re-export the changed data back into the database.

<!-- image -->

- To add the object ODBC to the toolbar Information Flow of your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow on the Home ribbon tab.

<!-- image -->

Click the object on the toolbar Information Flow and insert it into your simulation model.

In our example we inserted the following objects into our simulation model:

- An ODBC object, which controls the communication with the database.
- A Method for reading data from the database.
- A Method for writing data to the database.
- A Plant Simulation DataTable into which we import the data, and from which we export it back to the database.

<!-- image -->

- Double-click the object ODBC and type the name of the database into the text box Database . In our example we entered TestDB . This is the same name that we entered into the dialog ODBC Microsoft Access Setup above.

When you use a database with user management, such as SQL-Server, Oracle, etc., you also have to enter a User name and a Password . To apply your changes, click Apply .

To log on to the database, click Login .

<!-- image -->

When all your settings worked correctly, Plant Simulation dims the box with the name of the database and shows Ok in the box Message . When Plant Simulation encountered problems, it shows an error message describing the problem.

- Then, insert a Method into your simulation model. Within this Method you program, which data will be imported and what happens to this data.

Reading and writing data only works, when Plant Simulation is connected to the database. For this reason the methods login and logout frame the database operation proper in the instructions.

The source code looks like this:

ODBC.login("TestDB","","") // database operation ODBC.logout

- Now you can read data from the database and write the results of the database query into an Plant Simulation table. Instead, you could also write the data into a local variable.

You'll always start the query with the command sql . Then, define the target, in our example this is the Plant Simulation table named Orders . Next, you'll enter SQL standard queries within quotation marks. The syntax you have to use depends on your database system, consult the documentation that came with your database. The ODBC driver of the database determines the range of commands you can enter.

In our example we will read the entire contents of the table Orders2 from our Access database and write it into the Plant Simulation table Orders .

<!-- image -->

The source code looks like this:

ODBC.login("TestDB","","") ODBC.sql(Orders, "select * from Orders2") ODBC.logout

If you want to format the columns of the target table in Plant Simulation according to the formatting in the database while reading the data, make sure that Format table in the dialog of the object ODBC is checked. This only applies, when Plant Simulation provides its own formats, which correspond to the formats in the database. Plant Simulation does, for example, not provide a counterpart for the typical date format in Oracle. The documentation of your database provides information about filters for changing formats during the query.

<!-- image -->

- You can use and manipulate this data in Plant Simulation in a number of ways. When working with large amounts of data, we recommend to use SQL queries with filters, as these are oftentimes considerably faster than searching large Plant Simulation tables.

In our example the query for DeliveryTime and Amount of all parts of type panel yields this result in our Plant Simulation table.

<!-- image -->

**The source code looks like this:**

```simtalk
ODBC.login("TestDB","","")
ODBC.sql(Orders, "select DeliveryTime, Amount from Orders2 where MU = '.MUs.panel'")
ODBC.logout
```

**Back to Import Data from an ODBC Database**

###### Export Data to the Database

You can also export selected results of your simulation runs back to the ODBC database. For this, you use the method sql and a number of SQL instructions.

In our example we add a new row to our Access table Orders2 using the SQL instruction insert into .

The source code looks like this:

```simtalk
ODBC.login("TestDB","","")
ODBC.sql("insert into Orders2 values ('15:00:00.0000', '.MUs.NewPart', '150', 'NewPart', 'abc')")
ODBC.logout
```

<!-- image -->

**Note**

As SQL does not provide a single statement for adding the contents of a row or of the entire table to the database, you have to type the contents of each cell into the Method .

To add data to an existing data set, thus updating the database, use the SQL instruction update :

The source code looks like this:

ODBC.login("TestDB","","") ODBC.sql("update Orders2 set Attribute = 'xyz' where Name = 'rod'") ODBC.logout

<!-- image -->

##### Back to Import Data from an ODBC Database

Import Data from an Oracle Database

In principle you will use the object Oracle11g/Oracle19c in pretty much the same was as you do the object ODBC . First, establish a connection with a database instance, which exists on the Oracle Server. This database instance determines the name of the database, which you type into the object Oracle11g . Microsoft Windows does not provide Oracle settings.

If the Oracle Server is not installed on the same computer on which you execute Plant Simulation , you have to install an Oracle Client on that computer, which establishes the connection to the server. If the Oracle Client is not included in your Oracle Installation, contact your Oracle provider to obtain it.

If you have to handle large amounts of data, the object Oracle11g performs better and provides more commands than the object ODBC.

After you established the connection to an external Oracle database server within the computer network that your local computer can access, insert the object Oracle11g into your Plant Simulation simulation model. It connects to the database and imports data from it. You can write this data into Plant Simulation tables, change them there and use them in your simulation runs and re-export the changed data back into the database.

<!-- image -->

To add Oracle11g to the toolbar Information Flow of your simulation model, click Library &gt; Basic Objects &gt; InformationFlow &gt; Oracle11g on the Home ribbon tab.

Click the object on the toolbar Information Flow and insert it into your simulation model.

**Note**

You can also use ODBC together with Oracle! Then, you do not have to install an Oracle Client. Be aware that the SQL instructions, which you use, are not necessarily compatible with the ODBC version. This may cause problems if, for example, you want to switch between an Oracle database and an Access-database for test purposes. In this case, we recommend to use ODBC for all databases.

Back to Import Data from a Database

Exchanging Data with an SQL Database

Exchange Data with an SQL Database Plant Simulation can exchange data with an SQL database using the object SQLite .

<!-- image -->

<!-- image -->

To add the object SQLite to the toolbar Information Flow of your simulation model, click Class Library &gt; Basic Objects &gt; InformationFlow &gt; SQLite on the Home ribbon tab.

<!-- image -->

Select the object on the toolbar Information Flow and insert it into your simulation model.

<!-- image -->

This sample model demonstrates how to use the object SQLite to establish a connection between Plant Simulation and an SQL database.

- The object MySQLite uses a database which is stored in main memory instead of in a file on your computer's hard disk.

- The method openDatabase opens the database and creates a table in the database using SQL statements.
- The objects SourcePart and SourcePallet produce different parts that pass through the plant. When the parts leave the respective Source objects, the method enterCreationTime records the part type and the creation time in the database.
- Once the parts reach the Drain , the method enterDeletionTime records the time at which the parts leave the plant.
- The simulation runs for six days. At the end of the simulation run the endSim method computes the average lifetime of the parts and the method fi llTable writes these results into a Plant Simulation table.
- The method closeDatabase , which is called by the endSim method , closes the database.

**Proceed as follow to create the model:**

- Configure the Connection with the SQL Database
- Configure the Material Flow Through the Facility
- Import the Simulation Results From the Database and Show Them

The finished simulation model looks like this:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category &gt; Information Flow , the Topic &gt; SQLite Introduction , and the Example in the dialog Examples Collection , and click Open Model .

**Back to Import Data from a Database**

Configure the Connection with the SQL Database

Proceed as follows to establish a connection with an SQL database with the object SQLite .

- Insert the object SQLite into the simulation model. We named it MySQLite in our model. We used the default setting :memory: , which means that the database will be stored in your computer's main memory instead of in a file on the hard disk. This greatly improves performance as compared to saving the file on disk. Be aware though that all data will be gone for good once you close Plant Simulation or if Plant Simulation crashes.

If you do want to use the data later on, enter the file name of the database from which you want to import data or to which you want to export data.

<!-- image -->

- Program the method to open the database. We named our method openDatabase and entered the following source code:

```simtalk
// called by the init method MySQLite.open          // opens the database
MySQLite.exec("CREATE TABLE MUTrace (MUName TEXT PRIMARY KEY, MUType TEXT, StartTime REAL, EndTime REAL)") // creates the table MUTrace in the database with four columns containing the // name of the part, the type of the part, the start time, and the end time
```

- Program the method to close the database. We named our method closeDatabase and entered the following source code:
- We programmed the reset method, which is called when you click the Reset Simulation button in the EventController , to delete the contents of the DataTable and the result numbers from the Comment :
- We programmed the init method to show Processing... in the Comment object and to open the database:

// called by the endsim method MySQLite.close // closes the database

```simtalk
DataTable.delete
DataTable.closeDialog
Comment.Text :=  "MU Type, Lifetime"+strChr(13)+strChr(10)+"------------------------"
Comment.Text := "Processing..." openDatabase
```

**Back to Exchange Data with an SQL Database**

Configure the Material Flow Through the Facility

Proceed as follows to configure the material flow through the facility.

<!-- image -->

- Inserted two Source objects into the model and configure them so that they produce two different types of parts. In our model the SourcePart produces parts of type Part . The SourcePallet produces parts of type Container .

<!-- image -->

Next, we selected the same rear-triggered Exit Control for both Sources .

<!-- image -->

We entered the following source code into the method enterCreationTime . It inserts the times at which the parts were created, their type, and the start time into the internal database table named MUTrace . It then binds the string values and real values to the SQL-statement and executes the SQL-statement, thus writing the values to the database.

```simtalk
MySQLite.prepare("INSERT INTO MUTrace (MUName, MUType, StartTime) VALUES (?1, ?2, ?3)")
MySQLite.bindString(1, obj_to_str(@))
MySQLite.bindString(2, @.name)
MySQLite.bindReal(3, EventController.simTime)
MySQLite.step
```

- Insert the stations which process the parts. We inserted four Stations with these settings:

<!-- image -->

- Insert the Drain , which removes the parts from the plant.
- We entered the method enterDeletionTime as the Entrance Control and left all other settings unchanged.

<!-- image -->

We entered the following source code into the method. It updates the database table MUTrace with the time at which the parts were deleted.

```simtalk
MySQLite.prepare("UPDATE MUTrace set EndTime = ?1  WHERE MUName = ?2")
MySQLite.bindReal(1, EventController.simTime)
MySQLite.bindString(2, obj_to_str(@))
MySQLite.step
```

**Back to Exchange Data with an SQL Database**

Import the Simulation Results From the Database and Show Them

To show the simulation results in our simulation model after the simulation run is finished, you can import data of interest from the database. In our sample model we calculated the average lifetime of the parts and wrote these results into a Plant Simulation table and into an object of type Comment :

To do so, we inserted a DataTable into our simulation model and assigned the data type string to column 1 and 2 and the data type time to column 3 and 4. We also inserted an object of type Comment .

We then inserted an endSim method and entered the following source code. It computes the average lifetime of the part types Part and Container and writes that result into the Comment object. It then calls the method fi llTable , which in turn writes the lifetime of the individual parts into the DataTable :

The source code looks like this:

```simtalk
var str := "MU Type, Lifetime"+strChr(13)+strChr(10)+"------------------------"
MySQLite.prepare("SELECT MUType, avg(EndTime-StartTime) FROM MUTrace GROUP BY MUType")
while MySQLite.step
	str := str+strChr(13)+strChr(10)+MySQLite.getColumnString(0)+", "+to_str(MySQLite.getColumnReal(1))
	Comment.Text := str fillTable     // name of the method that writes data to the DataTable closeDatabase
```

<!-- image -->

To write the lifetime of the individual parts into the DataTable , we programmed the method fi llTable .

The source code looks like this:

```simtalk
// called by the endSim method
MySQLite.prepare("SELECT * FROM MUTrace")
for var column := 1 to MySQLite.getcolumnCount
	var row := 1
	while MySQLite.step
		switch column
		case 1,2 // column 1 and 2 of data type string DataTable[column,row] :=
			MySQLite.getColumnString(column - 1)
		else // column 3 and 4 of data type time DataTable[column,row] :=
			MySQLite.getColumnReal(column - 1)
		end
		row += 1
	end
next
DataTable.opendialog
```

<!-- image -->

Back to Exchange Data with an SQL Database

#### Import or Export Data in ANSI Format

You can import data for a simulation run from a text file with the FileInterface . You can also export data directly into a text file with the FileInterface : You can write log files of your simulation runs or record statistics data, etc. The FileInterface only processes ASCII characters, i.e., letters, numbers and special characters. It provides a number of methods to move within the file.

You can insert the FileInterface into your simulation model from the folder InformationFlow in the Class Library or from the toolbar Information Flow in the Toolbox .

<!-- image -->

Enter the File Name of the text file, which the FileInterface opens, if you want to import data. When you export data, it specifies the name of the file, which it saves.

<!-- image -->

The method readLn opens the file and reads a single line from it. It then increases the internal line counter by one and closes the file again.

The FileInterface transforms the contents of the line it read into a string . You can manipulate these strings with the Functions for Editing Variables of Data Type String , such as strCopy , strOmit , strLen and with the Functions for Converting Data Types , such as str\_to\_num , str\_to\_time etc.

Calling the method readLn again and again moves to the respective next line in the text file. The method goToLine moves to the line within the text file, which you specify as an integer value. You can then import that line with the method readLn . To access the same file several times in a row, we advise to open the file beforehand, as that will increase access speed. If you do not need a file any longer, close it.

<!-- image -->

When writing data, for example with the method write , the FileInterface opens the file and sets its internal line counter to the end of the file by calling the method goBottom . Then, the FileInterface saves the data to the file and closes it. The FileInterface always adds new data to the end of the file, it does not overwrite any existing data.

To access the same file several times in a row, we advise to open it beforehand, as it buffers the data before saving it. The FileInterface saves data before the next reading access of the file or when closing it.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Import and Export Data

**Displaying Data Stored in an External Program**

### Display Data Stored in an External Program

Provides information on how to display data stored in an external program using Plant Simulation .

The FileLink enables you to place a link, i.e., a shortcut to a file, into a Frame within Plant Simulation . This feature enables you to display and edit data stored in external programs directly within your simulation model.

You can insert the FileLink into your simulation model from the folder InformationFlow in the Class Library or from the toolbar Information Flow in the Toolbox .

<!-- image -->

Drag a file from the Desktop or the Windows Explorer into a Plant Simulation Frame and drop it there. The FileLink creates a link to the file in that Frame and places the icon of the application, which is assigned to the specific file type, in the Frame . By default, Plant Simulation enters the entire path to the file into the text boxes Label and File name of the FileLink .

When prompted, choose whether to embed the file into the Plant Simulation model or not:

- Yes : Copies the file into your Plant Simulation model file when you save the model file.
- No : Creates a link to the file in the file system of your computer.

Double-click the icon in the Frame to open the application assigned to the file type and the file for editing. If the link is invalid, Plant Simulation opens the dialog FileLink and shows the path and name of the invalid link in the text box File Name . You can open the dialog of the FileLink by right-clicking its icon and selecting Open on the context menu.

**You can:**

- Open Formatted Text from within the Model
- Open a Picture From Within the Model
- Open Documents From Office Applications and PDF Files
- Play a Video in Your Simulation Model

#### Open Formatted Text from within the Model

To show a document in your simulation model, which contains formatted text, you can save it as an RTF file. This way another person can always open this file in WordPad , which is part of a standard Windows installation.

To do so, proceed as follows:

- Create the document in a program which can save RTF files. We created our document in WordPad , entered our text, applied formatting, and saved it as an RTF file with the name MyRTFDocument.rtf .
- Drag the RTF file from the Windows Explorer to the Frame . If you want to embed the file into your simulation model, click Yes .

<!-- image -->

<!-- image -->

For demonstration purposes, we changed the Label so that it does not show the path of the file but RTF Text .

When you then pass the model on to another person, and that person double-clicks the icon of the object FileLink , it opens in WordPad .

**Back to Display Data Stored in an External Program**

#### Open a Picture From Within the Model

To show a picture in your simulation model, you can save it as a BMP or as a PNG file. This way another person can always open this file in Paint , which is part of a standard Windows installation.

To do so, proceed as follows:

- Save the picture in a program which can save BMP or PNG files. We saved our picture in Paint and saved it as a PNG file with the name MyPicture .
- Drag the BMP or PNG file from the Windows Explorer to the Frame .

Plant Simulation asks you if you want to use the picture as the background image of your model. We clicked No . We then clicked Yes in the next dialog to embed the picture into our model.

<!-- image -->

<!-- image -->

<!-- image -->

For demonstration purposes, we changed the Label so that it does not show the path of the file but png graphic .

When you then pass the model on to another person, and that person double-clicks the icon of FileLink1 , it opens the picture in Paint .

Back to Display Data Stored in an External Program

#### Open Documents From Office Applications and PDF Files

To show a document from Microsoft Office applications or PDF files created from them in your simulation model, save it in the native format or as a PDF file. Other people can only open these types of files, when Microsoft Office and a PDF Viewer are installed on their computer.

To do so, proceed as follows:

- Save the Microsoft Office document in the native format of the respective application. We saved our presentation with the name MyPresentation in PowerPoint first as a Microsoft Office PowerPoint Presentation. Then we also saved it as a PDF file.
- Drag the presentation, i.e., the PPTX file, from the Windows Explorer to the Frame . Click Yes in the dialog to embed the presentation into the model.

<!-- image -->

For demonstration purposes, we changed the Label so that it does not show the path of the file but PowerPoint presentation .

When you then pass the model on to another person, and that person double-clicks the icon of FileLink2 , it opens the presentation in PowerPoint .

- Drag the PDF file created from the presentation file from the Windows Explorer to the Frame . Click Yes in the dialog to embed the PDF file of the presentation into the model.

<!-- image -->

For demonstration purposes, we changed the Label so that it does not show the path of the file but Presentation pdf .

When you then pass the model on to another person, and that person double-clicks the icon of FileLink3 , it opens the presentation in the PDF Viewer that is installed on the computer.

Back to Display Data Stored in an External Program

#### Play a Video in Your Simulation Model

To embed and play a video in a simulation model with the default media player, proceed as follows:

- Record the video in a video recording tool and save it as an .avi file.
- We recorded a worker who places parts into a work cell and then removes the processed parts from it. We named our video file MyVideo .
- Drag the video, i.e., the AVI file, from the Windows Explorer to the Frame . Click Yes in the dialog to embed the video into the model.
- Our simulation model now looks like this.

<!-- image -->

To play the video, double-click the object FileLink4 . The video then plays with the default player that is set on your computer.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Display Data Stored in an External Program

### Working with Lists and Tables

#### Work with Lists and Tables

Plant Simulation provides several types of lists. They differ in the way they access data they contain. This way you can insert just the right list object to meet your specific modeling needs. You can use lists to provide the material flow objects with data with which they work during the simulation run. You can also write data, such as the results of your simulation runs into lists, export the data, and further process them in other applications.

You can insert a DataTable , a DataList , a DataStack , a DataQueue , and a TimeSequence into your simulation model from the folder InformationFlow in the Class Library or from the toolbar Information Flow in the Toolbox .

<!-- image -->

- The DataList has one column. It accesses the cells randomly by their position. You can add new cells at any position within the DataList . When you remove a cell, all cells with a higher number move up one position.
- The DataQueue has one column. It accesses the cell you added first: The contents of the first cell you added is the first one to be processed. It adds new cells after the last existing cell.
- The DataStack has one column. It accesses the cell you added last. The contents of the last cell you added is the first to be processed. When you add a cell to the top of the stack, all existing cells move one position down. When you remove a cell, the remaining cells each move up one cell.
- The DataTable has several columns. It accesses the cells by their column number and their row number. New data you type in overwrites and replaces the existing contents of the cell.
- The TimeSequence two columns. It accesses all pairs of cells randomly by their column number and their row number. It adds new entries in ascending order according to the time. Entries with a higher position move up by one position when you remove a previous entry.

The procedures described below are the same for all types of Plant Simulation lists, which you insert into your simulation model. Before you can select your own settings, you have to deactivate inheritance: Click

<!-- image -->

on the List ribbon tab so that it is not selected. You can then change settings.

Compare Properties of Lists and Tables

Back to Import Data for the Simulation

#### Set the Data Type of a Column

For the DataList , the DataStack , and the DataQueue , which only have one column, you set the data type for the entire list. For the DataTable you can select the data type for each individual column or for a range of columns.

To set the data type of a list or table:

- Deactivate inheritance of the format: Click on the List ribbon tab so that the button is not selected.
- Click Edit Format on the List ribbon tab. Or
- Click into the column for which you would like to set the data type with the right mouse button and select Format .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- To show the tabs Dimension and Data Type , click in the column header of a column.
- Select one of the data types from the drop-down list.

<!-- image -->

| Data type    | Description                                                                                  |
|--------------|----------------------------------------------------------------------------------------------|
| Acceleration | applies for the objects Conveyor , Track , TwoLaneTrack , and Transporter per second squared |
| Boolean      | true or false                                                                                |
| Date         | date statement ( dd.MM.yyyy )                                                                |
| DateTime     | date statement, including the time ( dd.MM.yyyy HH:mm:ss )                                   |
| Integer      | integer value                                                                                |
| Length       | floating point number, value depends on the unit of the length                               |
| List         | list with one column, shares properties of the DataList                                      |
| Money        | floating point numbers                                                                       |
| Object       | reference to a simulation model or an object                                                 |
| Queue        | list with one column, shares properties of the DataQueue                                     |
| Real         | floating point number, such as 3.1415                                                        |
| Speed        | floating point number, value depends on the unit for speed                                   |
| Stack        | list with one column, shares properties of the DataStack                                     |

| Data type   | Description                                                        |
|-------------|--------------------------------------------------------------------|
| String      | characters, numbers and special characters                         |
| Table       | table with one or more columns, shares properties of the DataTable |
| Time        | time statement (hh:mm:ss.ss)                                       |
| Weight      | floating point number, value depends on the unit of the weight     |

**Note**

Double-clicking a cell of data type string or boolean with the value true or false in a list or table toggles the value from true to false and vice versa.

- For the data types Integer , Real , and String you can also enter a Format String .
- If you want to hide the data type of the cells in the column, click Data Type on the List ribbon tab so that the button is not selected.

**Back to Tables**

#### Set the Dimension of a List

To set the dimension, i.e., the borders of a list or a table:

<!-- image -->

- Deactivate inheritance of the format: Click on the List ribbon tab so that the button is not selected.
- Click Format on the List ribbon tab. Or
- Click into the column for which you would like to set the data type with the right mouse button and select Format .

<!-- image -->

<!-- image -->

- To set the standard width of a single column, click in the column header. This shows the tabs Dimension and Data Type . Enter the column width in character widths of a non-proportional font that fit in a cell into the text box Column width .

To simultaneously change the width of several columns, mark the range of columns before you enter the width. To do so, click in the first column, hold down the mouse button and drag the mouse to the last column. The box Range shows which columns you have selected.

<!-- image -->

<!-- image -->

- To limit the size of a table, click Select All in the top left corner of the table area. Or
- Click the Select All button on the toolbar of the context menu.

<!-- image -->

For all lists you can enter the Number of rows .

For the DataTable you can, in addition, enter the Number of columns . If you do not enter a Number of columns and/or a Number of rows , the size of the list is not limited, which might be memoryconsuming.

<!-- image -->

- To insert a blank column to the left of the selected column, right-click it and select Insert Column . Plant Simulation assigns the data type string to this new column. You can change it afterwards as described above.
- To insert a blank row above the selected row, right-click it and select Insert Row .
- To delete the selected column or row, right-click it and select Cut .

Back to Work with Lists and Tables

#### Set Alignment and Colors of Cells

To set the alignment, the font size, the font color of cells and the background color of the list or table:

<!-- image -->

- Deactivate inheritance: Click on the List ribbon tab so that the button is not selected.
- Click Format on the List ribbon tab. Or

<!-- image -->

- Click into the column for which you would like to set the data type with the right mouse button and select Format .
- Click in the column header and select the columns to which you want to apply the settings. Or Click in the row header and select the rows to which you want to apply the settings. The box Range show which columns or rows you have selected.
- Select the Alignment , the Font Size , the Font Color and the Background Color of the selected columns and rows.

<!-- image -->

Back to Work with Lists and Tables

<!-- image -->

#### Insert, Cut and Delete Rows and Columns

To insert a row of empty cells:

- Right-click into any cell in the row above which you would like to insert a row of blank cells. In our example, we clicked a cell in row 1 to insert a new row above row 1.
- Select Insert Row .

<!-- image -->

To insert a column of empty cells:

- Right-click into any cell in a column to the left of which you would like to insert a column. If you select the first column, Plant Simulation inserts the new column to the right of it! In our example, we clicked a cell in column 1 to insert a new column to the left of column 1. All other columns automatically move one position to the right.
- Select Insert Column .

<!-- image -->

<!-- image -->

To delete the contents of an entire row or of an entire column of cells but to leave the empty row or column in the list, right-click it and select Delete on the mini toolbar.

To clear the contents of the selected cell, double-click, right-click it and select Delete on the context menu.

<!-- image -->

To delete an entire row or an entire column of cells with its contents from the table, right-click in the row header/column header and select Remove Column .

<!-- image -->

**Back to Work with Lists and Tables**

#### Work with Data in a List or Table

You can work with a list or table, which you inserted into a Frame , like this:

- Click the cell into which you would like to enter data and type in your data. Or type in data into the text box above the columns and rows.

When you click in a cell that contains data and start typing, Plant Simulation deletes the current contents of the cell and enters the characters you type in.

- You can use the following keys/key combinations to navigate in lists:
- To move one cell down, press Enter .

<!-- image -->

**Work with Data in a List or Table**

To move one cell up, press Shift+Enter .

To move one cell to the right, press Tab .

To move one cell to the left, press Shift+Tab .

To jump to the start of the cell below the current cell, press Ctrl+Enter .

To select a range of cells, press Shift+Cursor Up/Down/Left/Right .

- To apply the data you entered, press Enter or move the cursor into another cell ( Shift +arrow keys).
- To restore the previous contents of the cell while the cursor is still located in that cell, press Esc .
- To move the cursor within the cell, press one of the arrow keys.
- To move from cell to cell to the right or the left within the table, hold down Shift and press the right or left arrow.
- To delete the contents of a cell, double-click it, then right-click in the cell and select Delete .
- To move or to copy the contents of a cell to another location, use drag-and-drop within the list or table:
- Click the cell once and drag the mouse over a border of the cell until the cursor changes into crosshairs .
- Press the mouse button, and drag the contents of the cell to move it to another location. The move cursor looks like this
- Hold down Ctrl , press the mouse button, and drag the contents of the cell to copy it to another cell. The copy cursor looks like this .
- To paste data, which you copied to the clipboard with Home &gt; Copy into other applications, select Home &gt; Paste .
- To scroll up or down in a column, roll the mouse wheel or use the scrollbars.
- To select an entire column or row, their visible and invisible areas, click the column header or the row header.
- To select several contiguous columns of a DataTable , click in the column header of the first column, hold down the mouse button and drag the mouse in the column header until you have selected the range you want.
- To select all columns and rows of the list, click Select All , i.e., the button in the top left corner of the list file, where column and row headers meet. Or click the Select All button on the toolbar of the context menu. Or press Ctrl+A .
- To show blank cells in a different color in a list, click Highlight Empty Cells on the List ribbon tab.
- To create a sublist in a cell of type Table , List , Stack or Queue , you can either type in its name and path or use drag-and-drop to enter it.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- To open the sublist or an object, which is contained in a cell of type Table , List , Stack , Queue or Object bold down Shift and double-click the cell. Instead, you can also right-click the cell and select Open Object or press F2 .
- To set the standard column width, select List &gt; Format &gt; Dimension &gt; Column Width and enter a value. Or you can change it by dragging the cursor:
- Place the cursor into the topmost row of the column. The cursor changes into a double-headed arrow .
- Drag the mouse to the left or to the right until the width of the column meets your needs.

**Back to Work with Lists and Tables**

#### Work with Data in the DataTable

You can work with a DataTable , which you inserted into a Frame , like this:

**· Cut or Copy a Range of Cells**

To cut or to copy a range of cells within a DataTable , select the range: Click into the cell that is to be the first corner of the range, hold the mouse button down, and drag the mouse to the opposite corner of the range. Plant Simulation highlights the selected range.

When you cut a range ( Home &gt; Cut ), Plant Simulation just removes the contents of these cells, but leaves the empty cells in the table. When you insert the range you cut at a new location, by clicking in the cell that is to be the upper left corner of the range and then select Home &gt; Paste , Plant Simulation overwrites the contents of the cells in that range. You can also select entire columns or rows: Click in the gray area outside the column or row where the system index is located, i.e., the numbering of the columns and rows. When you select Home &gt; Cut , Plant Simulation removes the entire column or row. It then shifts the remaining columns to the left, and the remaining rows up. When you select an entire column or row by clicking in the column or row index, Plant Simulation pastes a column you cut, to the right of the current column and pastes a row you cut below the current row.

**· Work with Drag-and-Drop in DataTables**

Accelerator designates the listed key on the keyboard.

| To do this             | Drag from    | To           | Accelerator   |
|------------------------|--------------|--------------|---------------|
| Move the selected text | table window | table window | -             |
| Copy the selected text | table window | table window | Ctrl          |
| Insert selected text   | any          | table window | any           |
| Copy the selected text | table window | any          | Ctrl          |
| Cut the selected text  | table window | any          | -             |

**· Insert a Range of Cells**

You can paste a range, which you cut or copied from a table, into another range. This only works, if the target range, which you selected, has the same number of columns and rows or is an integer multiple of the number of columns and rows. If the data types of the copied range are not compatible with the data types of the target range, Plant Simulation marks it in red.

**· Hide and Show Columns**

To hide and then show contiguous columns again:

- Drag the cursor to the left or right border of the topmost row of the column or the range of columns you would like to hide. The cursor changes into a double arrow .
- Click the left mouse button and drag to the left until the columns you want to hide are not visible any more. In the example we hid columns 2 through 14 . You recognize hidden columns by the symbol that is shown at the end of column 1.

<!-- image -->

<!-- image -->

To show hidden columns again, drag the cursor over the symbol. The cursor changes into an arrow pointing to the right . To expand the columns to their original width, click the left mouse button once.

<!-- image -->

**· Insert a Drop-down List into a Cell**

You can use the Format String to insert a drop-down list into a cell of a DataTable , a DataList , a DataStack , or a DataQueue .

Select a cell with the data type String . Right-click it and select Format . Change to the tab Data Type .

Enter several terms of your choice, separated by a semicolon, and not followed by a blank into the text box Format string to create the drop-down list in the cell of the formatted range into which the user clicks. He can then select one of the terms you entered from the drop-down list.

If you enter Entry1;Entry2;Random , for example, Plant Simulation creates a drop-down list with the commands Entry1 , Entry2 , and Random and provides it in the cells you click within the range you formatted.

<!-- image -->

When you open the list window with the method openDialogBox , Plant Simulation shows the dropdown list immediately.

Back to Work with Lists and Tables

#### Accessing Data in Lists

Access Data in Lists

To access a cell in a list or table with a Method , you can either use the system index , i.e., the number , which Plant Simulation assigns to columns and rows or you can define your own user-defined index , which can be any meaningful expression .

<!-- image -->

The advantage of a user-defined index over the standard system index is that assigning names to columns and rows is more meaningful than the numbers, which Plant Simulation assigns by default. The userdefined index Vehicle["limo",#1] may tell you and your co-modelers more than the system index Vehicle[3,1] when debugging your model. Both expressions access the same cell. As a user-defined index you might, for example, enter:

Switch["Light","220 Volts"] Vehicle["limo",#1] Plant["Chicago",.building1.drill]

In addition, the user-defined index is not as error-prone as the system index: When you add an additional column or a row to the table, Plant Simulation increases the system index of the succeeding columns or rows by one. This naturally make any assignment in a Method to the previous system index invalid. The identifier of the user-defined index, on the other hand, remains the same and is still valid. Be aware that accessing a user-defined index is slightly slower than accessing the system index.

You can:

- Set the Column Index .

##### Set the Column Index

- Set the Row Index .
- Create a User-defined Column and Row Index .
- Set and Get the Upper Bound of a List .
- Address Columns and Rows with Methods .

**Back to Work with Lists and Tables**

**Set the Column Index**

**To set the column index:**

- Click Activate Column Index on the List ribbon tab.

<!-- image -->

When you click the button again, Plant Simulation deactivates the column index and deletes the existing contents.

- Select the row of the column index located above the first row of cells and click Format .
- Select the data type of the column index from the drop-down list on the tab Data Type . For the data types Integer , Real and String you can also enter a Format String to limit the number of digits the user can manually enter into these cells.

<!-- image -->

- To allow for quickly accessing the user-defined column index, select the check box Fast Index Access .
- To only allow unique entries in user-defined indexes, depending on the data type, select the check box Unique Index Key .

**Back to Access Data in Lists**

##### Set the Row Index

To set the row index:

- Click Activate Row Index on the List ribbon tab. When you click the button again, Plant Simulation deactivates the row index and deletes the existing contents.
- Select the column of the row index and select the command Format . Select the data type of the row index from the drop-down list on the tab Data Type . For the data types Integer , Real and String you can also enter a Format String .
- To allow for quickly accessing the user-defined row index, select the check box Fast Index Access .
- To only allow unique entries in user-defined indexes, depending on the data type, select the check box Unique Index Key .

<!-- image -->

<!-- image -->

- To allow for quickly accessing the user-defined column index, select the check box Fast Index Access .
- To only allow unique entries in user-defined indexes, depending on the data type, select the check box Unique Index Key .

**Back to Access Data in Lists**

##### Create a User-defined Column and Row Index

To create a user-defined column index and a user-defined row index:

<!-- image -->

- Deactivate inheritance: Click in the List ribbon tab so that the button is not selected.
- To activate and to show the column index, click Activate Column Index . Enter a meaningful term into the first row of cells to the right of string .

In most cases, you will select the data type String for the user-defined column index. When you select Integer , you have to enter a number sign # in front of the term you enter as your user-defined index to distinguish it from the system index.

<!-- image -->

- To activate and to show the row index, click Activate Row Index . Enter a meaningful expression into the first column of cells below string 0 .

In most cases, you will select the data type String for the user-defined row index. When you select Integer , you have to enter a number sign # in front of the expression, which you enter as your user-defined index, to distinguish it from the system index.

<!-- image -->

**Note**

When both column and row index are active, the cell [0,0], i.e., the cell at which column and row index intersect, counts as part of the column index, not as part of the row index.

**Back to Access Data in Lists**

Set and Get the Upper Bound of a List

To set the upper bound of a list or table:

##### Set and Get the Upper Bound of a List

- Deactivate inheritance: Click on the List ribbon tab so that the button is not selected.
- To select the entire list or table, click Select All , i.e., the button in the top left corner of the list file, where column and row headers meet. Or click the Select All button on the toolbar of the context menu. Or press Ctrl+A .
- Click Format on the List ribbon tab. Or

<!-- image -->

<!-- image -->

<!-- image -->

Click into the column and select Format .

<!-- image -->

- Click the Tab Dimension . Enter the Number of Columns and the Number of Rows . Plant Simulation automatically sets the lower bound to 1. When you use a user-defined index the lower bound is 0.

<!-- image -->

Back to Lists

<!-- image -->

For lists with one column, you can also set the upper bound with the attribute MaxDim . For lists with two columns you can set it with the attributes MaxXDim and MaxYDim . For tables the read-only attributes XDim and YDim return the dimension of the current occupancy.

The read-only attribute XDimIndex returns the last cell of the column index, which contains an entry. The read-only attribute YDimIndex returns the last cell of the row index, which contains an entry.

The dialog Go To also shows the number of occupied columns and rows.

To move to a certain cell within a list or table, click Go To on the List ribbon tab and type in the location of the cell.

<!-- image -->

##### Address Columns and Rows with Methods

Plant Simulation uses these conventions when addressing columns and rows in a DataTable in Methods . You can:

**Set the Format of Columns and Rows**

- The syntax for setting the format of columns and rows is:
- The number of parameters always is greater than or equal to 2.
- The last parameter sets-depending on the action you want to perform-the column or row:

```simtalk
setXX(Parameter:any, ..., Parameter:any, Parameter:integer)
```

You can use the system index, i.e., the absolute number of the column or row. Or

You can use a user-defined column or row index. To set a common format for a contiguous range of columns or rows, first define a range. For column functions it only applies to the columns within the specified range. Enter an asterisk ( * ) to designate all rows within the specified range. For row functions it only applies to the rows within the specified range.

Compare this example:

```simtalk
MyDataTable.setDataType({3,*}..{4,*},6,"column1","real")
```

| Enter        | to designate                                         |
|--------------|------------------------------------------------------|
| {3,*}..{4,*} | the range, all cells in columns 3 and 4 in this case |
| 6            | the system index of a column                         |
| "column1"    | a column index                                       |
| "real"       | a value                                              |

**Get the Format of Columns or Rows**

- The syntax for getting the format of columns and rows is:
- The number of parameters always is 1.
- The parameter ColumnOrRow of data type any designates the column or the row:
- You can use the system index, i.e., the absolute number of the column or row. Or
- You can use a user-defined row or a user-defined column index.

getXX(ColumnOrRow:any)

**Compare this example:**

MyDataTable.getDataType(1)

This Method returns the data type of column 1.

**Back to Access Data in Lists**

#### Search Lists with Methods

Lists and tables have an internal cursor pointing to a cell of the list. You can query the current position of the cursor with the attribute Cursor and set it anew by assigning an integer value to it. A search, for example with the method fi nd , begins at the current cursor position. Before starting the search, make sure that the list cursor is placed at the cell from which on you want to search.

After a successful search, Plant Simulation places the cursor in the cell where it found the value. If the list contains the value you searched for more than once, a new call of the method fi nd finds the next value starting at that cell, and so on.

When you set a range for the fi nd command, Plant Simulation determines the starting position of the cursor by combining the cursor and the range. The search begins at the first entry of the list in the range you entered, starting at the cursor position. The search ignores any range, which is located before the current cursor position. If the cursor is located in the middle of the range you entered, Plant Simulation does not search for entries before of the cursor position! The search goes on until Plant Simulation finds the value or reaches the end of the list. When Plant Simulation finds the value you searched for, it places the cursor into the cell, which contains the value. A new search begins at the next cell. If the search does not find the value, the internal cursor remains in the cell it had before the search.

```simtalk
MyDataStack.find(12.34) // finds the floating point value 12.34 starting from the current cursor position
MyDataQueue.find(42) // finds the integer value 42 starting from the current cursor position
MyDataList.find({1},{4}..{8},"drill") //finds the string "drill" in row 1 and in rows 4 to 8 starting from the current cursor position
MyDataTable.find("a") // finds the string "a" in the entire table starting from the current cursor position
MyDataTable.setCursor(3,1) // set cursor so that next find starts search from beginning
MyDataTable.find({3,*},"a") // finds the string "a" in column 3 starting from the current cursor position
MyDataTable.find({1,1}..{4,*},"a")
// finds the string "a" in columns 1 to 4 in all rows starting from the current cursor position
var
MyDataTable.setCursor(1,1) // starts searching for "abc" from the beginning to the end
if MyDataTable.find("abc")
	print MyDataTable.CursorX, " ",MyDataTable.CursorY
else
	print "not found"
end
```

The same principle applies to tables. As a table has rows and columns, it naturally has two cursors: CursorX designates the column and CursorY designates the row, which identifies the cell.

**Note**

Set the cursor anew after inserting or deleting rows, to determine its position.

In the example below we have this DataTable containing several values in a column.

<!-- image -->

We need to know if one or several of these values already exist in the DataTable . We program this as follows in a Method .

```simtalk
var lst : list;
lst.create
for var i := 1 to DataTable5.YDim
```

lst.setcursor(1) // Sets the cursor into the first cell. Searching starts there. if not lst.find(DataTable5[1, i]) // Checks if a value already exists in the list variable. lst.append(DataTable5[1, i]) end next promptListN(lst, "Found these values:") // Presents all values in the list.

We present already existing values in a dialog box with the method promptListN .

<!-- image -->

**Back to Work with Lists and Tables**

#### Search Lists with the Find Dialog

To search and optionally replace a string with another string, right-click in the list and select Find or press Ctrl+F .

<!-- image -->

- Type the search term you would like to find into the text box Find What .
- Select Match Case to only find text that has the same pattern of upper and lower case as the search term you typed into the text box Find what .
- Select Match Entire Cell Contents to only find the characters in cells, which exactly and completely match the search term you typed into the text box Find What .
- Select if you want to Search in Rows , i.e., to the right across rows, or down through Columns .
- Select the Search Criterion from the drop-down list:

Find : Finds the search term you typed into the text box Find What , compare the method fi nd .

Find ceil(ing) : Finds a value greater than or equal to the search term you typed into the text box Find What , compare the method fi ndCeil .

Find floor : Finds a value less than or equal to the search term you typed into the text box Find What , compare the method fi ndFloor .

- Click Find Next to find the next instance of the search term, which you type into the text box Find What .
- Click Replace to show the text box Replace With . Type the search term into the text box Replace With that is to replace the search term you typed into the text box Find What .
- Click Replace to replace the search term.

Back to Work with Lists and Tables

#### Create Lists within Lists and Tables

To create a sublist or a subtable in a cell of the DataList , the DataStack , the DataQueue , or the DataTable :

- Open the list object to which you want to add a sublist/subtable.
- Click on the List ribbon tab so that the button is not selected.
- Right-click the column header of the column to which you want to add a sublist and select Format .
- Select the data type of the sublist you want to insert: Table , List , Stack , or Queue . You will choose the data type depending on how you want to access the entries of the sublist.

<!-- image -->

<!-- image -->

<!-- image -->

If you want all sublists in that column to have the same formatting, select Common Format .

<!-- image -->

Apply formatting properties on the Tab Contents . Click OK .

<!-- image -->

- Click OK .
- Enter a name of your choice, which identifies the sublist, into the cells of the changed column. This name identifies the subtable.
- Hold down Shift and double-click the subtable , MySubtable in our case, to open it. Edit the subtable according to your needs.

<!-- image -->

<!-- image -->

<!-- image -->

To insert a list object from a Frame or the Class Library into a cell of the list objects DataList , DataStack , DataQueue , or DataTable :

- Open the list object to which you want to add a sublist/subtable.
- Click on the List ribbon tab so that the button is not selected.
- Right-click the column header of the column to which you want to add a sublist and select Format .
- Select the data type Object .
- Drag the table to a cell of the list and drop it there. This inserts the absolute path of the inserted list.

<!-- image -->

Type the name of the list you want to insert into the cell, when this list is located in the same Frame . This way Plant Simulation uses the relative path .

<!-- image -->

To open the sublist or a list object, which is contained in a cell of type Table , List , Stack , or Queue , hold down Shift and double-click into the cell. Instead, you can also right-click the cell and select Open Object or press F2 .

Compare Accessing the Name of a Sublist with a Method

Back to Work with Lists and Tables

#### Sort DataList, DataTable, and TimeSequence

To sort the contents of a DataList , a DataTable , or a TimeSequence :

- To sort the selected column in ascending (A to Z, or 0 to 9) order, click Sort Ascending [lists] or Sort Ascending on the context menu.
- To sort the selected column in descending order (Z to A, or 9 to 0), click Sort Ascending [lists] or Sort Descending on the context menu.

You can also only sort the DataList , the DataTable and the TimeSequence with methods :

- The method sort sorts the lists in ascending (A to Z, or 0 to 9) or in descending order (Z to A, or 9 to 0).
- The method inOrder sorts a value into an existing sequence of values at the position where you want it to be.

**Back to Work with Lists and Tables**

#### Calculate Values with a Formula

A Formula is an expression, which can read out and link the values of other table cells and attribute values of objects. With these values, the formula then makes the calculations you specified.

For linking the values within a formula, you can use the same arithmetic operators and mathematical functions as you use in methods , compare Operators and Expressions .

**Procedure**

1. To activate Formula mode, click Create Formula on the List ribbon tab so that it is selected
2. To enter a formula into a cell, click in it and type the expression in. Instead, you can also type it into the text box above the list. In our example we add the value of cell 2 in column 1 to the value of cell 3 in column 2. To do so, we typed in @[1,2]+@[2,3] .
3. To show the result of the calculation of the formula, i.e., its value, in the cell, press Enter .

<!-- image -->

<!-- image -->

<!-- image -->

.

<!-- image -->

4. To show the formula itself in the text box, double-click in the cell that contains the formula. Then, you can change the formula. You can also access the values in a column via the column index.

<!-- image -->

The list shows cells containing a formula in color. Turquoise designates a formula with a correct syntax, red a formula with syntax errors.

##### Access a Cell in a DataTable with @ in a Formula

Within a formula you can access the value of another cell of the same DataTable with the anonymous identifier @ :

<!-- image -->

| Formula             | Executes                                                                   |
|---------------------|----------------------------------------------------------------------------|
| @[1,1]+@[1,2]       | adds the contents of the cell [1,1] to the contents of the cell [1,2].     |
| @[1,1]*track.length | multiplies the contents of cell [1,1] with the length of the object track. |
| @[1,@.ydim]+5       | adds 5 to the value of the last cell in the first column.                  |
| @[xSelf+1,ySelf]-7  | subtracts 7 from the value of the neighboring cell to the right            |
| @.sum({3,*})        | computes the sum of the third column.                                      |
| @.min({1,2}..{1,*}) | determines the smallest value of the first column, starting from cell 2.   |

**Note**

The data type of the result of a formula has to have the same data type as the cell or the column in which the cell containing the formula is located.

##### Access a Cell in a Local Variable of Data Type Table with ? in a Formula

Within a formula you can access the value of another cell of the same local variable of data type table with the anonymous identifier ?

##### Access a Sublist with ?

In sublists, you can access the list, into which you inserted the sublist, with the anonymous identifier ? . For user-defined attributes of lists, the anonymous identifier ? accesses the object for which you defined the user-defined attribute.

xSelf and ySelf contain the number of the column or the number of the row respectively, which contains the formula. This way you can easily access neighboring cells.

##### Catch Runtime Errors in Formulas

You can catch runtime errors in formulas with local error handlers.

To catch an error in a table formula for example, add a user-defined attribute of data type Method to the DataTable and name it ErrorHandler . Assign an empty string ("") to the error message to suppress the error. If the error is suppressed, you can assign a new value to the wrong table cell by letting the error handler return a value.

**Back to Work with Lists and Tables**

#### Import or Export the Contents of a List

You can save an Plant Simulation list in several formats:

- To save the list with all of its Plant Simulation formatting as a Plant Simulation list, click Export &gt; Export Object File on the List ribbon tab. You can then open the saved list object within a list in other Frames or in other simulation models.

To import a DataTable , which you saved as an .psobj file into another DataTable , click Import on the List ribbon tab. To import a list with one column into a DataTable , select the same data type for the left column that the list with one column has.

<!-- image -->

- To only save the contents of the list, without any of its formatting, click Export &gt; Export Text File on the List ribbon tab.

<!-- image -->

To change the settings with which Plant Simulation exports ASCII data, click Export &gt; Text File Format on the List ribbon tab. Then, you can select which sign you want to use for separating columns, etc., depending on the program into which you want to import the data.

<!-- image -->

Select the encoding with which the text file will be exported in the dialog Save As .

<!-- image -->

The sample table shown below, which we exported with the default settings, looks like this when we open it in a word processing program. We chose Notepad++ to show the tabs, which Plant Simulation exported.

<!-- image -->

- To save the contents of the Plant Simulation list as an Excel worksheet, click Export &gt; Export Excel File on the List ribbon tab.

Enter the name of the worksheet, on which Excel opens the data, into the dialog Worksheets .

<!-- image -->

<!-- image -->

When Plant Simulation exports data to Excel, it applies these conventions:

| Plant Simulation data type   | Excel data type   | Excel format            |
|------------------------------|-------------------|-------------------------|
| String                       | String            | -                       |
| Boolean                      | Boolean           | -                       |
| Integer                      | Number            | -                       |
| Real                         | Number            | -                       |
| Object                       | String            | -                       |
| Table                        | String            | -                       |
| List                         | String            | -                       |
| Stack                        | String            | -                       |
| Queue                        | String            | -                       |
| Money                        | Number            | -                       |
| Length                       | Number            | -                       |
| Weight                       | Number            | -                       |
| Speed                        | Number            | -                       |
| Acceleration                 | Number            | -                       |
| DateTime                     | Number            | dd/mm/yyyy hh:mm:ss.000 |

| Plant Simulation data type   | Excel data type   | Excel format    |
|------------------------------|-------------------|-----------------|
| Date                         | Number            | dd/mm/yyyy      |
| Time                         | Number            | dd:hh:mm:ss.000 |

**Note**

Plant Simulation only exports integers in the range between -536.870.912 and 536.870.911 in the required format. Plant Simulation saves values outside of this range as 0.

When you open the .xlsx file in Excel, it looks like this. You might still have to adapt settings of the imported file in Excel.

<!-- image -->

When Plant Simulation reads an Excel table, it attempts to adapt the data types of the individual columns to the available Plant Simulation data types. This only works, if you created the columns on the Excel worksheets, so that they only contain a single data type, meaning that, when you, for example, assign the data type String to a cell of a column, the entire column may only be of data type String .

Row 0 (zero) is an exception to this rule: When the table, which Plant Simulation reads, has a column index, it interprets row 0 as the column index and it will not be part of the data type designation of the columns.

**Compare Export Excel File**

**Unshare a List or Data Table**

Compare Import Data from a Microsoft Excel Worksheet

Compare \_Methods for Importing and Exporting Data in Text Format

Compare \_Attributes for the Text Format of Lists and Tables

Back to Work with Lists and Tables

#### Unshare a List or Data Table

When you assign the value of a Variable of data types table/list/stack/queue to a cell in a subtable, Plant Simulation does not copy this value, but creates a reference to it. The Variable and value in the DataTable then access the same value, meaning that if you change one of the values, this also changes the respective other value.

The same applies if you assign a user-defined attribute of data types table/list/stack/queue to another user-defined attribute . Both user-defined attributes then access the same list, meaning that if you change the value of one of the two attributes this also changes the value of the other attribute.

If you would like to use two different values, you can accomplish this with the method unshare .

Our sample model looks like this.

<!-- image -->

We use a Variable of data type table and a DataTable whose leftmost cell contains a subtable.

<!-- image -->

When we run the source code of our method ShareTable Value1 is written to the table of the Variable and to the subtable of the DataTable . In the DataTable you can also unshare by clicking the button Unshare .

```simtalk
Variable := DataTable[1,1]
Variable[1,2] := "Value1" // Value1 appears in DataTable[1,1]
```

<!-- image -->

<!-- image -->

When we run the source code of our method UnShareTable Value2 is written to the table of the Variable and Value1 to the subtable of the DataTable .

```simtalk
&Variable.unshare
Variable[1,2] := "Value2" // Value2 doesn't appear in DataTable[1,1]
```

#### Open a List as a Dialog in the Foreground

Back to Work with Lists and Tables

<!-- image -->

**Open a List as a Dialog in the Foreground**

By default the windows of the objects DataList , DataQueue , DataStack , and DataTable always open in the background behind any open dialog boxes. This can make working with lists and tables cumbersome at times as it involves a lot of moving dialog boxes around on screen.

<!-- image -->

<!-- image -->

To prevent this, you can also open the DataList , the DataQueue , the DataStack , and the DataTable in the foreground as a dialog box with the method openDialogBox .

To open our table SteeringTypes as a dialog box in the foreground, we typed in the instructions below into our method openTableAsDialog .

SteeringTypes.openDialogBox Be aware that the window of a list does not provide all of the functions which the normal list windows offers on the List ribbon tab.

<!-- image -->

It also offers a reduced set of functions on the context menu.

<!-- image -->

Another important difference is that the list window applies entries as you type them in, while the list opened as a window only applies them when you click Apply or OK .

Back to Tables

### Exchange Data via a Network Socket

The object Socket provides a TCP/IP interface for Plant Simulation . It communicates with other applications, which also provide a socket interface.

Socket communication is the foundation of the most widespread communication software. Sockets are point-to-point connections, established during initialization, allowing the online exchange of data. As the socket connection is directly based upon the TCP/IP protocol, it ensures fast communication without much data overhead.

With socket connections one process works as a server with additional processes registering as clients. Plant Simulation can be a client as well as a server.

<!-- image -->

To add the object Socket to the Class Library , click Manage Class Library &gt; Basic Objects &gt; Socket on

the Home ribbon tab.

<!-- image -->

You can insert the object Socket into your simulation model from the folder InformationFlow in the Class Library or from the toolbar Information Flow in the Toolbox .

<!-- image -->

In our sample model a serverSocket , located in a Frame of its own in Plant Simulation , communicates with a client Socket , also located in a Frame of its own, and vice versa.

To exchange data with the Socket interface , proceed as follows:

- Model the Frame ServerSocket .
- Insert the objects required for the ServerSocket communicating with the ClientSocket : The Socket object, a Callback Method for the ServerSocket , a Variable each for recording the sent message and the received message, and a Method in which you program how to send messages.

We named our server Socket object MyServerSocket . We used the default settings and selected our callback method, which we called MyCallbackMethod .

Make sure to only select the check boxes On and Server Socket in the object MyServerSocket !

When you select TCP as the Protocol for transmitting the data, Plant Simulation establishes a connection across which the data will be exchanged. The TCP protocol ensures that the data packages arrive at the destination.

When you select UDP , Plant Simulation can exchange data without a connection having to be established. This creates less overhead, but does not guarantee that the data actually does arrive at the destination.

<!-- image -->

- Insert the Variables for recording the sent message and the received message.

We named our Variables MessageReceived and MessageSent and selected the following settings:

<!-- image -->

- Program the method with the message which you would like to send.

We entered the following source code to create a random number between 0 and 100, write this value to the Variable , which we named MessageSent , and send the value. We named our method sendMessages and entered this source code.

```simtalk
var str: string // generates a random number between 0 and 100
str := to_str(round(z_uniform(1,0,100),1)) // writes the value of the random number to the variable 'MessageSent'
MessageSent := str // sends the message using channel 0
MyServerSocket.write(0,str)
```

- Program the Callback Method which the ServerSocket calls when it receives data. We named our Callback Method MyCallbackMethod and entered the following source code.
- The finished Frame ServerSocket looks like this:

```simtalk
param SocketChannelNo: integer, SocketMessage: string // writes the value to the global variable 'MessageReceived' if strLen(SocketMessage) = 1
MessageReceived := to_str(strAscii(SocketMessage)) // byte received
else
	MessageReceived := to_str(SocketMessage)           // string received end // writes the message to the Plant Simulation Console print "--------------------------------------------------------------------"
	print self
	print "Message: The number ", MessageReceived, " was received at ", sysdate
```

<!-- image -->

- Model the Frame ClientSocket :
- Insert the objects required for the ClientSocket communicating with the ServerSocket : The Socket object, a Callback Method for the ClientSocket , a Variable each for recording the sent message and the received message, and a Method in which you program how to send messages.
- We named our client Socket object MyClientSocket . We used the default settings and selected our Callback Method , which we called MyCallbackMethod .
- Make sure to select the check box On and to clear Server Socket in the object MyClientSocket !

<!-- image -->

- Insert the Variables for recording the sent message and the received message.

We named our Variables MessageReceived and MessageSent and selected the same settings as above.

Program the method with the message which you would like to send.

We entered the following source code to create a random number between 0 and 100, write this value to the Variable , which we named MessageSent , and send the value. We named our method sendMessages and entered this source code.

```simtalk
var str: string // generates a random number between 0 and 100
str := to_str(round(z_uniform(1,0,100),1)) // writes the value of the random number to the variable 'MessageSent'
MessageSent := str // sends the message using channel 0
MyClientSocket.write(0,str)
```

- Program the Callback Method which the ClientSocket calls when it receives data. We named our Callback Method MyCallbackMethod and entered the following source code.

```simtalk
param SocketChannelNo: integer, SocketMessage: string // writes the value to the global variable 'MessageReceived' if strLen(SocketMessage) = 1
MessageReceived := to_str(strAscii(SocketMessage)); // byte received
else
	MessageReceived := to_str(SocketMessage); // string received end // writes the message to the Plant Simulation Console print "--------------------------------------------------------------------"
	print self
	print "Message: The number ", MessageReceived, " was received at ", sysdate; )
```

- The finished Frame ClientSocket looks like this:
- Activate the check box On in MyServerSocket and MyClientSocket .
- To transmit data, click the method sendMessages in the Frame ServerSocket with the right mouse button and select Run on the context menu. Watch what the variables show. The variable MessageSent in the Frame ServerSocket shows that the method calculated the number 1.8 and sent it to the variable MessageReceived in the Frame ClientSocket , which naturally also shows the number 1.8 . Also check what the Console shows.

<!-- image -->

<!-- image -->

<!-- image -->

- Then, click the method sendMessages in the Frame ClientSocket with the right mouse button and select Run on the context menu. Watch what the variables show. MessageSent in the Frame ClientSocket shows that the method calculated the number 72.878 and sent it to the variable MessageReceived in the Frame ServerSocket , which naturally also shows the number 72.878 . Also check what the Console shows.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Import Data for the Simulation

