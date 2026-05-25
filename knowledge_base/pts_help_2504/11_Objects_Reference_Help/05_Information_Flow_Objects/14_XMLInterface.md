### XMLInterface

Use the XMLInterface for reading and extracting data stored in XML files.

Icon

<!-- image -->

Description

Basically an XML document contains data in ASCII format, i.e., text that is structured in a certain way.

You can, for example, use the XMLInterface to read data which you exported from Process Simulate or an XML database.

You can:

- Read and Write Data Sequentially
- Read and Access Data Randomly
- Access and Traverse Data Randomly

You can then use the data, which the XMLInterface read, and which you manipulated with a Method , to run a simulation in Plant Simulation . You might afterward use the methods write and writeElement to write the simulation results back to an XML file and continue working with these simulation results in Process Designer or another program.

**Note**

Working with the XMLInterface requires that you are familiar with XPath (XML Path Language) source code.

To show a tooltip with information about the XMLInterface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the XMLInterface , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the XMLInterface to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

InformationFlow &gt; XMLInterface on the Home ribbon tab.

See also

Import Data in XML Format

#### Dialog Box of the XML Interface

Dialog Box of the XMLInterface

Double-click the icon of the XMLInterface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

##### Tab Attributes

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Filename [XMLInterface]

Click the folder icon and select the name of the XML file which you want to access or which you want to save.

<!-- image -->

**Context [text box]**

###### Context [text box]

Type in the context of the data you want to import.

<!-- image -->

The context designates the node of the structure of the XML document at which the XMLInterface starts reading data.

You might, for example, type in the names of certain data, or of certain objects that you are interested in, for example Data/Objects .

This way you can restrict the data to be read, i.e., if you do not need to work with all of the data contained in the XML file, you will specify a context.

If you do not type in a context, the XMLInterface imports the entire file, which may contain a large amount of data, some of which you do not need. This might take some time to import and use up a large amount of your computer's RAM.

SimTalk

Context [SimTalk]

setContext [SimTalk]

###### Import Method [XML Interface]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code that controls how to extract and to sequentially process the imported data.

<!-- image -->

The Import Method is called by the method openRead for all objects, which are contained in the XML file.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

You can also create a control which is a user-defined attribute of data type Method . To do so, right-click in the text box and select Create Control . This might look like this:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.ExitControlEnginePlant .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

The standard import method as a user-defined attribute looks like this:

<!-- image -->

You might, for example, execute a callback method :

```simtalk
param Level: integer, LocalName: string, Value: string, AttrTbl: table
var row,size: integer
var nameStr,valueStr: string
var attrName,attrValue: string // print "" // print "Level: "+num_to_str(i) // print "Local Name: "+localName // print "Value: "+value
nameStr := localName
valueStr := value
size := attrTbl.Ydim
for row := 1 to attrTbl.Ydim // print "Attribute Name: "+attrTbl[1,row] // print "Attribute Value: "+attrTbl[2,row]
	attrName := attrTbl[1,row]
	attrValue := attrTbl[2,row]
next
numberCalls := numberCalls+1
```

After the Method has processed the data, you can sequentially write it back out with the method writeElement .

SimTalk

ImportMethod [SimTalk] addAttribute [SimTalk] endElement [SimTalk] openRead [SimTalk] openWrite [SimTalk] startElement [SimTalk] writeElement [SimTalk] See also Select Object [for controls]

###### Delete File [XML Interface]

To delete the XML file whose name is contained in the text box Filename , click this button.

<!-- image -->

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The View Menu provides the commands listed in the table of contents to the left. SimTalk updateDialog [SimTalk]

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the XML Interface

#### \_Methods of the XML Interface

The XML Interface provides:

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

**addAttribute [SimTalk]**

##### addAttribute [SimTalk]

Adds a new attribute to the XML file of the XMLInterface designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.addAttribute(Name:string, Value:string) → boolean
```

**Parameters**

- The parameter Name of data type string designates the name of the attribute.
- The parameter Value of data type string designates the value of the attribute.

It applies when you sequentially access data.

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.addAttribute("xmlns", "myBooks") MyXMLInterface.addAttribute("xmlns:aa", "specAth")

close [SimTalk] - XML Interface

Closes the XML file of the XMLInterface designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.close → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
MyXMLInterface.filename := "C:\users\johnE\myfile.xml"
MyXMLInterface.openRead
MyXMLInterface.close
```

SimTalk

openRead [SimTalk]

**closeChildren [SimTalk]**

##### closeChildren [SimTalk]

Closes the active level of the respective children and returns to the next higher level in the structure of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.closeChildren → boolean
```

Return Value

The return value has the data type boolean .

Example

// This method selects the children of a node and prints name and value of // each child. It will be started recursively for the selected child. // Selects the children of the current node MyXMLInterface.selectChildren // this is the loop traversing the children while MyXMLInterface.getNextNode = true // prints the name and the value of each child print MyXMLInterface.getNodeName+ ": " + MyXMLInterface.getNodeValue // checks for children of this child VisitChildren end // returns to the parent node MyXMLInterface.closeChildren

##### deleteNodes [SimTalk]

Deletes all nodes that you selected with an XPath instruction in the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

&lt; Path &gt;.deleteNodes(Instruction:string) → boolean

**Parameter**

The parameter Instruction of data type string designates the nodes that you selected with an XPath instruction .

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// delete all nodes specified by XPath instructions
MyXMLInterface.filename := "D:\MSXML 4.0\books.xml" // load the XML document to be randomly accessed into RAM MyXMLInterface.openDocument // delete all 'book' nodes of genre 'Fantasy'
MyXMLInterface.deleteNodes("book[genre = 'Fantasy']")
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml" // write the document to a file MyXMLInterface.write // remove the document from RAM MyXMLInterface.close
```

**SimTalk**

insertNodes [SimTalk]

##### endElement [SimTalk]

endElement [SimTalk]

Terminates an item of the XMLInterface designated by &lt;Path&gt; that you started with the method startElement .

Remarks

This applies when you sequentially access data.

Type

Method

Syntax

&lt; Path &gt;.endElement → boolean

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.endElement

SimTalk

startElement [SimTalk]

##### getAttributeName [SimTalk]

Returns the name of the attribute of the XMLInterface designated by &lt;Path&gt; at the designated position.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

&lt; Path &gt;.getAttributeName(Position:integer) → string

Parameter

The parameter Position of data type integer designates the position of the attribute.

Return Value

The return value has the data type string .

Example

MyXMLInterface.getAttributeName(i)+":" + MyXMLInterface.getAttributeValue(i)

##### getAttributeValue [SimTalk]

getAttributeValue [SimTalk]

Returns the value of the designated attribute of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

&lt; Path &gt;.getAttributeValue(Parameter:any) → string

Parameter

The parameter Parameter of data type any designates the attribute.

Return Value

The return value has the data type string .

Example

MyXMLInterface.getAttributeName(i)+":" + MyXMLInterface.getAttributeValue(i)

##### getContainer [SimTalk]

Returns a pre-formatted table that provides the container for accepting the data to be written by the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.getContainer(Depth:integer) → table
```

Parameter

The parameter Depth of data type integer sets the depth of the data to be written.

Return Value

The return value has the data type table .

Example

```simtalk
// insert new data into a XML document
var tbl:table
MyXMLInterface.filename := "D:\MSXML 4.0\books.xml" // load the XML document MyXMLInterface.openDocument // get an Empty table to write the data to // depth = 1 means that we want to write nodes with children
tbl := MyXMLInterface.getContainer(1) // set the parent node for the new data
MyXMLInterface.setContext("/catalog") // first the node to append to the 'catalog' nodes tbl[1,1] := "book" // then the attributes of the 'book' node
tbl.createNestedList(4,1) // explicit namespace tbl[4,1][1,1] := "xmlns:aa" tbl[4,1][2,1] := "specAth" // additional attributes tbl[4,1][1,2] := "id" tbl[4,1][2,2] := "bk113" // child nodes
tbl.createNestedList(5,1) tbl[5,1][1,1] := "aa:author" tbl[5,1][2,1] := "specAth" tbl[5,1][3,1] := "XYZ" tbl[5,1][1,2] := "title" tbl[5,1][3,2] := "UNKNOWN" tbl[5,1][1,3] := "genre" tbl[5,1][3,3] := "also" tbl[5,1][1,4] := "price" tbl[5,1][3,4] := "12,45" tbl[5,1][1,5] := "publish_date" tbl[5,1][3,5] := "12.1.02" tbl[5,1][1,6] := "description" tbl[5,1][3,6] := "xx0011"
MyXMLInterface.insertNodes(tbl) // saves the changed document
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml" MyXMLInterface.write // closes the document MyXMLInterface.close
```

##### getNextNode [SimTalk]

Returns the next node after the one you selected with the method selectChildren located on the active level of the structure of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.getNextNode → boolean
```

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// select the children of a node and prints name and value of // each child. It will be started recursively for the selected child. // select the children of the current node MyXMLInterface.selectChildren // this is the loop traversing the children
while MyXMLInterface.getNextNode = true // print the name and the value of each child print MyXMLInterface.getNodeName+ ": " + MyXMLInterface.getNodeValue // check for children of this child VisitChildren end //
	return to the parent node MyXMLInterface.closeChildren
```

**SimTalk**

**selectChildren [SimTalk]**

##### getNodeName [SimTalk]

getNodeName [SimTalk]

Returns the name of the node located on the active level of the structure of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.getNodeName → string
```

Return Value

The return value has the data type string .

Example

print MyXMLInterface.getNodeName+ ": " + MyXMLInterface.getNodeValue

##### getNodes [SimTalk]

Returns all nodes of the XPath instruction of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.getNodes(Instruction:string, NumberOfLevels:integer) → table
```

**Parameters**

- The parameter Instruction of data type string designates the name of the XPath instruction .
- The parameter NumberOfLevels of data type integer designates the levels of the structure to which this applies.

**Return Value**

The return value has the data type table .

**Example**

MyXMLInterface.getNodes("book[title='MidnightRain']",1)

##### getNodeValue [SimTalk]

getNodeValue [SimTalk]

Returns the value of the node located on the active level of the structure of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.getNodeValue → string
```

Return Value

The return value has the data type string .

Example

print MyXMLInterface.getNodeName+ ": " + MyXMLInterface.getNodeValue insertNodes [SimTalk]

Inserts the nodes contained in a table into the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

&lt; Path &gt;.insertNodes(NodesTable:list) → boolean

Parameter

The parameter NodesTable of data type list designates the name of the table.

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.insertNodes(tbl)

SimTalk

deleteNodes [SimTalk]

**newDocument [SimTalk]**

##### newDocument [SimTalk]

Creates a new, empty XML document in RAM into which you insert data for the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.newDocument(Name:string) → boolean
```

Parameter

The parameter Name of data type string designates the name of the new XML document.

Return Value

The return value has the data type boolean .

Example

```simtalk
// create a new document using the method newDocument
var tbl:table
MyXMLInterface.newDocument("catalog")
tbl := MyXMLInterface.getContainer(1)
MyXMLInterface.setContext("/catalog") // parent node tbl[1,1] := "book" // default namespace tbl[2,1] := "MyBooks" // attributes
tbl.createNestedList(4,1) // explicit namespace tbl[4,1][1,1] := "xmlns:aa" tbl[4,1][2,1] := "specAth" // additional attributes tbl[4,1][1,2] := "id" tbl[4,1][2,2] := "bk113" // child nodes
tbl.createNestedList(5,1) tbl[5,1][1,1] := "aa:author" tbl[5,1][2,1] := "specAth"
tbl[5,1][3,1] := "XYZ" tbl[5,1][1,2] := "title" tbl[5,1][3,2] := "UNKNOWN" tbl[5,1][1,3] := "genre" tbl[5,1][3,3] := "also" tbl[5,1][1,4] := "price" tbl[5,1][3,4] := "12,45" tbl[5,1][1,5] := "publish_date" tbl[5,1][3,5] := "12.1.02" tbl[5,1][1,6] := "description" tbl[5,1][3,6] := "xx0011"
MyXMLInterface.insertNodes(tbl)
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml"
MyXMLInterface.write
```

**openDocument [SimTalk]**

##### openDocument [SimTalk]

Opens an XML file of the XMLInterface designated by &lt;Path&gt;, reads the data contained within, and places it into RAM.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.openDocument → boolean
```

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// random access using XPath instructions
var tbl: table
MyXMLInterface.filename := "D:\MSXML 4.0\books.xml" // load the XML document to be randomly accessed into RAM MyXMLInterface.openDocument // select nodes using an XPath instruction. Selection starts with // the context node you entered into the MyXMLInterface. // The second parameter defines the selection depth for each node // 0 means no children. The result is passed to a table.
tbl := MyXMLInterface.getNodes("book[title='Midnight Rain']", 1)
MyXMLInterface.close
```

**SimTalk**

close [SimTalk] - XML Interface

##### openRead [SimTalk]

Opens the XML file, which you want to read sequentially of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

The import method is called by the method openRead for all objects, which are contained in the XML file.

Type

Method

Syntax

```simtalk
< Path >.openRead → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
MyXMLInterface.filename := "C:\users\johnE\myfile.xml"
```

MyXMLInterface.openRead MyXMLInterface.close

SimTalk

openWrite [SimTalk]

See also

Import Method [XML Interface]

##### openWrite [SimTalk]

openWrite [SimTalk]

Opens the XML file, which you want to write sequentially of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

**Note**

openWrite encodes the xml file in UTF-8 format. This enables the xml files to be treated as ASCII files provided only characters from the ASCII character set are used.

Type

Method

Syntax

```simtalk
< Path >.openWrite → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
MyXMLInterface.filename := "D:\MSXML 4.0\writeSequ.xml" // opens the XML document for sequential writing MyXMLInterface.openWrite
MyXMLInterface.startElement("catalog")
MyXMLInterface.startElement("book")
```

SimTalk

openRead [SimTalk]

remove [SimTalk] - XML Interface

Deletes the XML file of the XMLInterface designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.remove → boolean
```

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.remove

See also

Delete File [XML Interface]

##### selectChildren [SimTalk]

selectChildren [SimTalk]

Selects all children of the active node of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.selectChildren → boolean
```

Return Value

The return value has the data type boolean .

Example

// select the children of a node and print name and value of // each child. It will be started recursively for the selected child. // Select the children of the current node MyXMLInterface.selectChildren // this is the loop traversing the children while MyXMLInterface.getNextNode = true // print the name and the value of each child print MyXMLInterface.getNodeName+ ": " + MyXMLInterface.getNodeValue // check for children of this node VisitChildren end // returns to the parent node MyXMLInterface.closeChildren

##### selectNodes [SimTalk]

Selects the designated nodes of the XPath instruction of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Method

Syntax

```simtalk
< Path >.selectNodes(Instruction:string) → boolean
```

Parameter

The parameter Instruction of data type string designates the nodes of the XPath instruction .

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.selectNodes("book[genre = 'Computer']")

**setContext [SimTalk]**

**setContext [SimTalk]**

Sets the context of the XMLInterface designated by &lt;Path&gt;.

Remarks

This way you can restrict the data to be read. As a rule you will enter a context, if you do not need to work with all of the data contained in the XML file.

If you do not specify a context, the XMLInterface imports the entire file, which may contain a large amount of data, some of which you do not need. This might take some time to import and use up a large amount of your computer's RAM. It applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.setContext(Node:string) → boolean
```

Parameter

The parameter Node of data type string designates the node of the structure of the XML document at which the XMLInterface starts reading data.

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// create a new document by calling the methods openDocument and setContext
var tbl:table // load no file
MyXMLInterface.filename := "" MyXMLInterface.openDocument // set the context to the root node
MyXMLInterface.setContext("/") // set the document item
tbl := MyXMLInterface.getContainer(0)
tbl[1,1] := "catalog"
MyXMLInterface.insertNodes(tbl) // set the context to the document item
MyXMLInterface.setContext("/catalog") // returns a container for a subtree
tbl := MyXMLInterface.getContainer(1) // parent node
tbl[1,1] := "book" // default namespace tbl[2,1] := "MyBooks" // attributes
tbl.createNestedList(4,1) // explicit namespace tbl[4,1][1,1] := "xmlns:aa" tbl[4,1][2,1] := "specAth" // additional attributes tbl[4,1][1,2] := "id" tbl[4,1][2,2] := "bk113" // child nodes
tbl.createNestedList(5,1) tbl[5,1][1,1] := "aa:author" tbl[5,1][2,1] := "specAth" tbl[5,1][3,1] := "XYZ" tbl[5,1][1,2] := "title" tbl[5,1][3,2] := "UNKNOWN" tbl[5,1][1,3] := "genre" tbl[5,1][3,3] := "also" tbl[5,1][1,4] := "price" tbl[5,1][3,4] := "12,45" tbl[5,1][1,5] := "publish_date" tbl[5,1][3,5] := "12.1.02" tbl[5,1][1,6] := "description" tbl[5,1][3,6] := "xx0011"
MyXMLInterface.insertNodes(tbl) // set the filename to save the file with
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml" // write the document MyXMLInterface.write
```

startElement [SimTalk]

startElement [SimTalk]

Designates the start of the designated item of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly access data.

Type

Method

Syntax

```simtalk
< Path >.startElement(Element:string) → boolean
```

Parameter

The parameter Element of data type string designates the item.

Return Value

The return value has the data type boolean .

Example

MyXMLInterface.startElement("catalog") MyXMLInterface.startElement("book")

##### updateNodes [SimTalk]

Updates the nodes you selected with the method getNodes of the XMLInterface designated by &lt;Path&gt;, and writes them into a table.

Type

Method

Syntax

```simtalk
< Path >.updateNodes(NodesTable:list) → boolean
```

**Parameter**

The parameter NodesTable of data type table designates the name of the table.

You can then manipulate the contents of the resulting table, and finally update the selected nodes. It applies when you randomly access data.

Return Value

The return value has the data type boolean .

Example

```simtalk
// update the selected nodes of the document
var tbl: table
MyXMLInterface.filename := "D:\MSXML 4.0\books.xml" MyXMLInterface.openDocument // select the nodes to be changed
tbl := MyXMLInterface.getNodes("/catalog/book[title='Midnight Rain']", 1) // update the value tbl[5,1][3,3] := "TEST" // write the changed data
MyXMLInterface.updateNodes(tbl)
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml"
MyXMLInterface.write
MyXMLInterface.close
```

See also

getNodes [SimTalk]

##### write [SimTalk] - XML Interface

write [SimTalk] - XML Interface

Writes the XML data of the XMLInterface designated by &lt;Path&gt; from RAM into a file.

Type

Method

Syntax

```simtalk
< Path >.write → boolean
```

Return Value

The return value has the data type boolean .

**Example**

```simtalk
// delete all nodes specified by XPath
MyXMLInterface.filename := "D:\MSXML 4.0\books.xml" // load the XML document to be randomly accessed into memory MyXMLInterface.openDocument // delete all 'book' nodes of genre 'Fantasy'
MyXMLInterface.deleteNodes("book[genre = 'Fantasy']")
MyXMLInterface.filename := "D:\MSXML 4.0\tmp.xml" // write the document to a file MyXMLInterface.write // remove the document from memory MyXMLInterface.close
```

##### writeElement [SimTalk]

Writes the item of the XMLInterface designated by &lt;Path&gt; and closes it at the same time.

Remarks

This applies when you sequentially access data.

Type

Method

Syntax

```simtalk
< Path >.writeElement(Name:string, Value:string) → boolean
```

**Parameters**

- The parameter Name of data type string designates the name of the item.
- The parameter Value of data type string designates the value of the item.

**Return Value**

The return value has the data type boolean .

**Example**

```simtalk
// demonstrate how to sequentially write an XML file
MyXMLInterface.filename := "D:\MSXML 4.0\writeSequ.xml" // open the XML document for sequential writing MyXMLInterface.openWrite
MyXMLInterface.startElement("catalog")
MyXMLInterface.startElement("book") // add attributes to the 'book' item'
MyXMLInterface.addAttribute("id", "bk01")
MyXMLInterface.addAttribute("xmlns", "myBooks")
MyXMLInterface.addAttribute("xmlns:aa", "specAth") // these are the children of the 'book' item
MyXMLInterface.writeElement("aa:author", "Gambardella, Matthew") // add an attribute to the 'author' item
MyXMLInterface.addAttribute("age", "16")
MyXMLInterface.writeElement("title", "XML Developer's Guide")
MyXMLInterface.writeElement("genre", "Computer")
MyXMLInterface.writeElement("price", "44.95")
MyXMLInterface.writeElement("publish_date", "2000-10-01")
MyXMLInterface.writeElement("description", "An in-depth ...") // terminate the item 'book' MyXMLInterface.endElement
```

// terminate the item 'catalog MyXMLInterface.endElement MyXMLInterface.close

#### Read-Only Attributes of the XMLInterface

Read-Only Attributes of the XMLInterface

The XMLInterface provides:

- The read-only attribute GetNumberAttributes [SimTalk] .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyXMLInterface.GetNumberAttributes

##### GetNumberAttributes [SimTalk]

Returns the number of attributes of the active node of the XMLInterface designated by &lt;Path&gt;.

Remarks

This applies when you randomly traverse data.

Type

Read-only attribute

Syntax

&lt; Path &gt;.GetNumberAttributes → integer

Return Value

The return value has the data type integer .

Example

numberAttributes := MyXMLInterface.GetNumberAttributes

#### Attributes of the XML Interface

\_Attributes of the XML Interface

The XMLInterface provides:

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
MyFileInterface.FileName := "C:\users\johnE\myData.txt"
print MyXMLInterface.Context
posit := Station.Cont.XPos
```

##### Context [SimTalk]

Sets the context of the data of the XMLInterface designated by &lt;Path&gt; that you want to read.

Type

Attribute

Syntax

```simtalk
< Path >.Context:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyXMLInterface.Context := "Data/Objects"
```

See also

Context [text box]

##### FileName [SimTalk] - XML Interface

FileName [SimTalk] - XML Interface

Sets the name of the XML file of the XMLInterface designated by &lt;Path&gt; that you want to read.

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
MyXMLInterface.FileName := "C:\users\johnE\myfile.xml"
```

See also

Filename [XMLInterface]

##### ImportMethod [SimTalk]

Sets the name of the Method in which you programmed how to extract and to sequentially process the imported data for the XMLInterface designated by &lt;Path&gt;.

Remarks

The import method is called by the method openRead for all objects, which are contained in the XML file.

Type

Attribute

Syntax

```simtalk
< Path >.ImportMethod:object
```

**Assignment Value**

You can assign a value of data type object .

**Examples**

```simtalk
MyXMLInterface.ImportMethod := &MyImportMethod
param Level: integer, LocalName: string, Value: string, AttrTbl: table
var row,size: integer
var nameStr,valueStr: string
var attrName,attrValue: string // print "" // print "Level: "+num_to_str(i) // print "Local Name: "+localName // print "Value: "+value
nameStr := localName
valueStr := value
size := attrTbl.Ydim
for row := 1 to attrTbl.Ydim // print "Attribute Name: "+attrTbl[1,row] // print "Attribute Value: "+attrTbl[2,row]
	attrName := attrTbl[1,row]
	attrValue := attrTbl[2,row]
next
numberCalls := numberCalls+1
```

<!-- image -->

