### FileLink

Use the FileLink for placing a link, i.e., a shortcut to a file into a Frame in your simulation model.

Icon

<!-- image -->

Description

Drag a file from the Desktop or the Windows Explorer into a Plant Simulation Frame and drop it there, to create a link to the file in that Frame and place the icon of the application which is assigned to the specific file type, in the Frame .

By default, Plant Simulation enters the entire path to the file into the text boxes Label and Filename of the FileLink . Our model in 2D looks like this:

<!-- image -->

Plant Simulation opens a dialog asking if you would like to embed the file into the Plant Simulation model or not. If you click Yes , it copies the file into your Plant Simulation model file when you save the model file.

<!-- image -->

When you open the model file the next time, Plant Simulation creates a temporary file which is a copy of the original file. If you are still editing an embedded file in its originating application while you save the Plant Simulation model file, Plant Simulation shows a message.

By default, Plant Simulation assigns the Name FileLink, FileLink1 , etc. To show the entire path of the file in the Frame window as well, select View &gt; Options &gt; Show Object Labels in the Frame . Double-click the icon in the Frame to open the application and the file for editing, provided the originating application is installed on the computer. If the link is invalid, Plant Simulation opens the dialog FileLink and shows the path and name of the invalid link in the text box File Name .

The FileInterface can only open the embedded files in the associated application with a double-click, after you clear the check box File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer . The same applies for the method openFile .

<!-- image -->

You can, on the other hand, open embedded text files (.txt) and embedded .xps files by double-clicking them even if Prohibit Access to the Computer is selected.

**Note**

You can create a xps file in Microsoft Word with the command Save As . You can then use this xps file as you would a PDF file. Microsoft Windows contains a free viewer for xps files.

You can open the dialog of the FileLink by right-clicking its icon and selecting Open on the context menu.

<!-- image -->

<!-- image -->

To show a tooltip with information about the FileLink , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the FileLink , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the FileLink to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

InformationFlow &gt; FileLink on the Home ribbon tab.

**See also**

Display Data Stored in an External Program

<!-- image -->

##### Dialog Box of the FileLink

Dialog Box of the FileLink

Double-click the icon of the FileLink to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Filename [FileLink]

Embed File [check box]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Filename [FileLink]

Click the folder icon, navigate to the folder where the file is located that you want to add and, select it.

<!-- image -->

Plant Simulation shows the path and the name of the linked file in this text box after you dragged a file from the Windows Explorer to the Plant Simulation Frame and dropped it there.

SimTalk

FileName [SimTalk] - FileLink

###### Embed File [check box]

Embed File [check box]

To embed the file, which you dragged onto the Frame and dropped there, into the Plant Simulation model, select this check box.

<!-- image -->

When you embed the file, this version of the file will become part of the simulation model, meaning Plant Simulation does not care when you move the original file to another location. Changes to the file after embedding it will naturally not be reflected if you embed it. Embedding may significantly increase the file size of your .spp model file.

Clear the check box to create a link to the file in the file system of your computer. If you move or delete the file, the link will become invalid, and Plant Simulation will not be able to find the file and open it.

The FileInterface can only open the embedded files in the associated application with a double-click, after you clear the check box File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer . The same applies for the method openFile .

You can, on the other hand, open embedded text files (.txt) and embedded .xps files by double-clicking them even if Prohibit Access to the Computer is selected.

**Note**

You can create a xps file in Microsoft Word with the command Save as . You can then use this xps file as you would a PDF file. Microsoft Windows contains a free viewer for xps files.

SimTalk

Embed [SimTalk]

Prohibit Access to the Computer [model settings]

openFile [SimTalk]

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

**Navigate Menu**

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the FileLink

Methods of the FileLink

The FileLink provides:

- The method openFile [SimTalk] .
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

openFile [SimTalk]

Opens the file linked to the FileLink designated by &lt;Path&gt; in its originating application or the respective file type assigned on the computer. You can then edit it.

Remarks

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the FileLink cannot open the embedded files in the associated application with a double-click. The same applies to the method openFile .

Type

Method

Syntax

&lt; Path &gt;.openFile

Example

frame1.MyFileLink.openFile

See also

Prohibit Access to the Computer [model settings]

#### Read-Only Attributes of the FileLink

Read-Only Attributes of the FileLink

The FileLink provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

#### Attributes of the FileLink

##### \_Attributes of the FileLink

The FileLink provides:

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
frame1.FileLink2.Embed := false
print frame1.FileLink2.Embed
posit := Station.Cont.XPos
```

**Embed [SimTalk]**

##### Embed [SimTalk]

Makes the FileLink designated by &lt;Path&gt; embed the file into the Plant Simulation Frame ( true ) or not ( false ).

Remarks

Embed is not inherited and it is set to false by default.

To embed the file into the Plant Simulation model, assign true . Then that version of the file will become part of the simulation model, meaning the program does not mind, when you move the original file to another location. Changes to file after embedding it will naturally not be reflected if you embed it. Embedding may significantly increase the file size of your .spp model file.

If you assign false , Plant Simulation creates a link to the file in the file system of your computer. If you move or delete the file, the link will become invalid and Plant Simulation will not be able to find the file and open it.

Type

Attribute

Syntax

```simtalk
< Path >.Embed:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
Model1.FileLink2.Embed := false
print Model1.FileLink2.Embed
```

See also

Embed File [check box]

**FileName [SimTalk] - FileLink**

Sets the name of the linked or embedded file of the FileLink designated by &lt;Path&gt; or returns it.

Remarks

You also have to specify the file extension when assigning the filename.

Type

Attribute

Syntax

&lt; Path &gt;.FileName:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
frame1.FileLink1.FileName := "myName.xls" // MS Excel file
print frame1.FileLink1.FileName
```

See also

Filename [FileLink]

**FileInterface**

#### FileInterface

Use the FileInterface for accessing data you create and store in other programs in ASCII format.

Icon

<!-- image -->

**Description**

You can create data for a simulation run in text files and import it into Plant Simulation during the simulation run with the FileInterface . You can also write protocol files, statistics tables, etc. directly into a text file, without having to take a detour by using tables or lists. You can then visualize or manipulate this data in a spreadsheet program or a word processing application.

**Note**

Plant Simulation can keep 10 files open at any one time. The FileInterface handles letters, numbers, and special characters. It cannot process binary data, such as programs, graphics, etc. One FileInterface manages one file at a time.

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; &gt; Prohibit Access to the Computer , the FileInterface can only change files in the model folder as these are automatically opened for reading. Write functions of the FileInterface always return false. In addition the FileInterface can only delete files in the model folder and its sub-folders.

To show a tooltip with information about the FileInterface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the FileInterface , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the FileInterface to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

InformationFlow &gt; FileInterface on the Home ribbon tab.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Import or Export Data in ANSI Format

#### Dialog Box of the FileInterface

Dialog Box of the FileInterface

Double-click the icon of the FileInterface to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

Edit 3D Graphic Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

##### Tab Attributes

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

<!-- image -->

See also

Filename [FileInterface]

Delete File [FileInterface]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Filename [FileInterface]**

Click the folder icon and select a file in the dialog Open .

<!-- image -->

Or type in the name of the text file from which you want to import data or to which you want to export data.

**SimTalk**

FileName [SimTalk] - FileInterface

**Encoding [drop-down list]**

###### Encoding [drop-down list]

Select the encoding with which Plant Simulation saves the text file which it writes.

<!-- image -->

- ANSI is an 8-bit character set that enables you to represent up to 256 characters (0 through 255). The ANSI character set is a superset of the 7-bit ASCII character set.
- UTF-8 is another encoding of the Unicode character set. Each character is represented by one to three bytes.
- UTF-16 is another encoding of the Unicode character set.
- Unicode is a 16-bit character set that includes almost all of the written languages of the world. Plant Simulation saves Unicode in UTF-16 encoding. Each character is represented by two bytes.

When Plant Simulation reads a file, the attribute contains the encoding of the file. If Plant Simulation cannot recognize an encoding, it returns ANSI.

**SimTalk**

Encoding [SimTalk]

**Delete File [FileInterface]**

To delete the file whose name is contained in the text box Filename , click this button.

<!-- image -->

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu

The View Menu provides commands to access its functions.

Refresh [on View menu]

Show Attributes and Methods [on View menu]

SimTalk

updateDialog [SimTalk]

See also

View Menu [general description]

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D Export Import

##### Help Menu

The commands are described under the Help Menu .

**Methods of the FileInterface**

#### \_Methods of the FileInterface

The FileInterface provides:

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

close [SimTalk] - FileInterface

close [SimTalk] - FileInterface

Saves all unsaved data of the FileInterface designated by &lt;Path&gt; and then closes the file.

Type

Method

Syntax

&lt; Path &gt;.close → boolean

Return Value

The return value has the data type boolean .

Example

MyFileInterface.close

See also

open [SimTalk] - FileInterface

##### formFeed [SimTalk]

Adds a FormFeed character to the end of the file of the FileInterface designated by &lt;Path&gt; and places the cursor at the end of the entry.

Remarks

When printing a file, the printer starts a new page after this character.

If the file is not open, the FileInterface opens it and leaves it open after accessing it.

Type

Method

Syntax

&lt; Path &gt;.formFeed → boolean

**Description**

Return Value

The return value has the data type boolean .

Example

MyFileInterface.formFeed

##### goBottom [SimTalk]

goBottom [SimTalk]

Moves the cursor to the end of the last line of the file of the FileInterface designated by &lt;Path&gt;.

Remarks

After reaching the end of the last line of the file, no more data will be read. If the file is not open, the FileInterface opens it and leaves it open after accessing it.

Type

Method

Syntax

```simtalk
< Path >.goBottom → boolean
```

Return Value

The return value has the data type boolean .

Example

MyFileInterface.goBottom

See also

goTop [SimTalk]

goToLine [SimTalk]

Moves the cursor in the file of the FileInterface designated by &lt;Path&gt; to the start of the designated line.

Remarks

The FileInterface processes the file starting at this line. It returns false if the file contains fewer lines than you enter.

If the file is not open, the FileInterface opens it and leaves it open after accessing it.

Type

Method

Syntax

&lt; Path &gt;.goToLine(LineNumber:integer) → boolean

Parameter

The parameter LineNumber of data type integer designates the line.

Return Value

The return value has the data type boolean .

Example

MyFileInterface.goToLine(2)

goTop [SimTalk]

goTop [SimTalk]

Moves the cursor to the start of the first line of the file of the FileInterface designated by &lt;Path&gt;.

Remarks

If the file is not open, the FileInterface opens it and leaves it open after accessing it.

Type

Method

Syntax

&lt; Path &gt;.goTop → boolean

Return Value

The return value has the data type boolean .

Example

MyFileInterface.goTop

See also

goBottom [SimTalk]

##### newLine [SimTalk]

Adds a carriage return to the end of the file of the FileInterface designated by &lt;Path&gt; and sets the cursor to the end of the entry.

Remarks

The FileInterface inserts new entries into a new line. You can format the protocol file like this.

If the file is not open, the FileInterface opens it and leaves it open after accessing it.

Type

Method

Syntax

```simtalk
< Path >.newLine → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
// evaluate the DataTable Tab. Insert an empty line into the table Tab every ten lines
var y: integer
for var y := 1 to Tab.YDim
	MyFileInterface.writeLn(Tab[1,y], Tab[2,y])
	if index mod 10 = 0
		MyFileInterface.newLine
	end
next
```

open [SimTalk] - FileInterface

Opens the file of the FileInterface designated by &lt;Path&gt;.

Remarks

The FileInterface leaves the file open until you close it again with the method close .

To execute several operations one after the other, open the file beforehand to increase access speed. Close the file afterward, as data will not be saved to the file if Plant Simulation terminates unexpectedly. You can also increase access speed of an open file significantly if you collect the data beforehand and save it.

**Note**

Plant Simulation can only open 10 files at a time. We advise to close files you do not need any more.

Type

Method

Syntax

```simtalk
< Path >.open([ReadOnly:boolean:=false]) → boolean
```

**Parameter**

The optional parameter ReadOnly of data type boolean sets if the user has read-only permission only ( true ) or read and write permission ( false ).

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

Example

MyFileInterface.open

See also

close [SimTalk] - FileInterface read [SimTalk] - FileInterface read [SimTalk] - FileInterface Reads the entire file starting at the current position into the FileInterface designated by &lt;Path&gt;.

Remarks

If the file was just opened, Plant Simulation also recognizes the encoding according to the byte order marks and uses this encoding.

If Plant Simulation does not recognize the encoding, it uses the specified encoding.

Type

Method

Syntax

&lt; Path &gt;.read → string

Return Value

The return value has the data type string .

Example

```simtalk
var fileContent:string := FileInterface.read
```

See also

open [SimTalk] - FileInterface

##### readLn [SimTalk]

Reads the line, in which the file cursor is located, into the file of the FileInterface designated by &lt;Path&gt; and increases the counter by one.

Remarks

readLn passes the entire line as a string . You might have to use one of the conversion functions, such as str\_to\_num , to convert the string into another data type.

If the file is not open for write , the FileInterface opens it and reads the line. If the file cannot be opened, for example because the path to the file is invalid, the function fails with an error. To avoid this error, you can explicitly call the method open which returns false if the file cannot be opened.

Type

Method

Syntax

```simtalk
< Path >.readLn → string
```

Return Value

The return value has the data type string .

Example

```simtalk
// A file contains numbers in several lines. These will be read // into the second column of a DataTable
var y: integer, line: string
y := 1
while not MyFileInterface.EoF      // until end of file reached
	line := MyFileInterface.readLn  // get next line MyDataTable[2,y] := line
	y += 1
end
```

SimTalk

writeLn [SimTalk]

open [SimTalk] - FileInterface remove [SimTalk] - FileInterface Closes the file of the FileInterface designated by &lt;Path&gt; if it was open and deletes it for good.

Type

Method

Syntax

&lt; Path &gt;.remove → boolean

Return Value

The return value has the data type boolean .

true if deleting the file succeeded.

false if deleting fails. Then, check if the file exists and make sure that it is not read-only.

Example

MyFileInterface.remove

See also

Delete File [FileInterface]

write [SimTalk] - FileInterface

Adds the designated data to the end of the file of the FileInterface designated by &lt;Path&gt;, without starting a new line.

Remarks

The FileInterface places the cursor at the end of the entry. If the file does not exist, the FileInterface creates it. If the file is not open for write , the FileInterface opens it, writes the data, and closes it afterwards.

If the file cannot be opened, for example because the path to the file is invalid, the function fails with an error. To avoid this error, you can explicitly call the method open , which returns false if the file cannot be opened.

Method

Type

Method

Syntax

```simtalk
< Path >.write(Data:any) → boolean
```

Parameter

The parameter Data of data type any designates the data that is appended to the end of the file.

Return Value

The return value has the data type boolean .

Example

```simtalk
var FIF : object
FIF := FileInterface
FIF.write("ProcTime: ")
FIF.write(.machine.ProcTime,"[s]")
```

See also

open [SimTalk] - FileInterface

##### writeLn [SimTalk]

writeLn [SimTalk]

Adds the data designated by the parameter of data type any and a carriage return character and a line feed character to the file, i.e., any data added after this will be written to a new line.

Remarks

If the file is not open for write, the FileInterface opens it and closes it afterward. If you write many lines, it is therefore faster if you open the file once before you are calling writeLn .

If the file cannot be opened, for example because the path to the file is invalid, the function fails with an error. To avoid this error, you can explicitly call the method open , which returns false if the file cannot be opened.

Method

Type

Method

Syntax

```simtalk
< Path >.writeLn(Data:any, ...) → boolean
```

Parameter

The parameter Data of data type any designates the data that is appended to the end of the file.

Return Value

The return value has the data type boolean .

Example

```simtalk
var FIF : object
FIF := FileInterface
FIF.writeLn("length of track:")
FIF.writeLn(.Track.length,"meters")
FIF.writeLn(3.1415,true,"text",3+4)
```

SimTalk

readLn [SimTalk]

open [SimTalk] - FileInterface

#### Read-Only Attributes of the FileInterface

**\_Read-Only Attributes of the FileInterface**

The FileInterface provides:

- The read-only attributes listed in the table of contents to the left.
- \_Read-Only Attributes of All Objects

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyFileInterface.IsOpen

##### EoF [SimTalk]

EoF [SimTalk]

EoF returns if the file of the FileInterface designated by &lt;Path&gt; is still closed, as no data is provided for processing (true).

Type

After you opened the file with the method open , EoF ( e nd o f f ile) returns false as long as lines of text may still be read in with the method readLn .

Type

Read-only attribute

Syntax

```simtalk
< Path >.EoF → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
MyFileInterface.open
while not MyFileInterface.EoF
	print MyFileInterface.readLn
end
MyFileInterface.close
```

SimTalk

open [SimTalk] - FileInterface

readLn [SimTalk]

##### IsOpen [SimTalk] - FileInterface

Returns if the file of the FileInterface designated by &lt;Path&gt; into which data is to be written is open (true) or not open (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.IsOpen → boolean
```

Return Value

The return value has the data type boolean .

Example

printMyFileInterface.IsOpen

#### Attributes of the FileInterface

\_Attributes of the FileInterface

The FileInterface provides:

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
print MyFileInterface.FileName
posit := Station.Cont.XPos
```

##### Encoding [SimTalk]

Sets the encoding with which Plant Simulation saves the file of the FileInterface designated by &lt;Path&gt; which it writes.

Remarks

When Plant Simulation reads a file, the attribute contains the encoding of the file. If Plant Simulation cannot recognize an encoding, it returns ANSI.

Type

Attribute

Syntax

&lt; Path &gt;.Encoding:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "ANSI" is an 8-bit character set that enables you to represent up to 256 characters (0 through 255). The ANSI character set is a superset of the 7-bit ASCII character set.
- "UTF-8" is another encoding of the Unicode character set. Each character is represented by one to three bytes.
- "UTF-16" is another encoding of the Unicode character set.
- "Unicode" is a 16-bit character set that includes almost all of the written languages of the world. Plant Simulation saves Unicode in UTF-16 encoding. Each character is represented by two bytes.

Example

MyFileInterface.Encoding := "Unicode"

See also

Encoding [drop-down list]

##### FileName [SimTalk] - FileInterface

FileName [SimTalk] - FileInterface

Sets the name of the file of the FileInterface designated by &lt;Path&gt;.

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
MyFileInterface.FileName := "C:\users\johnE\myData.txt"
```

See also

Filename [FileInterface]

