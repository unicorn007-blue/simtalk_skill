### HtmlReport

#### HtmlReport [object]

Use the HtmlReport for presenting current data and results of the simulation run in a report that you can share with co-workers and customers.

Icon

<!-- image -->

Description

You can save the HtmlReport as an .htm file and open this file in an HTML-Browser, such as Microsoft Edge , Firefox , Google Chrome , etc. Plant Simulation is not required to open the HtmlReport in an external Browser, meaning that the HtmlReport can be displayed on any computer on which an HTML-Browser is installed.

**Note**

The easiest way to configure the contents of the HtmlReport is to drag an object from the Frame to the tab Content and to drop it there. You can type in additional content and formatting settings in the built-in markup language on the Tab Content .

<!-- image -->

You can also show another HtmlReport within an HtmlReport , compare Display a HtmlReport .

To show a tooltip with information about the HtmlReport , hover with the mouse over it.

To change the length of the graphic and the anchor points of the HtmlReport , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the HtmlReport to your simulation model, click Manage Class Library &gt; Basic Objects &gt; UserInterface &gt; HtmlReport on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model

#### Dialog Box of the HtmlReport

Dialog Box of the HtmlReport

Double-click the icon of the HtmlReport to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

##### Show Report

Show Report

Show Report

To open the display window of the HtmlReport , click Show Report .

- The Display Pane of the Display Window on the right-hand side shows the content of the report which you define on the Tab Content .

- The Structure Pane of the Display Window on the left-hand side shows the first two heading levels of the report. Click a heading in the structure pane to jump to this location in the display pane.

###### Show Report

<!-- image -->

Instead, you can also right-click the HtmlReport object in the Frame and select Show on the context menu.

<!-- image -->

###### Structure Pane of the Display Window

The structure pane of the display window shows the table of contents of your HtmlReport .

Proceed as follows to do the following in the structure pane of the display window:

- To jump to a certain heading of level 1 or 2 in the display window, click this heading in the structure pane.
- To print the report, click the button.

<!-- image -->

**Note**

Print and Save do not work if the local security policies deny access to the operating system within the HTML functionality.

<!-- image -->

- To show a print preview of the report, click .
- To save the content of the HTML page as a Web Page, complete , i.e., as an .htm file or an .html file, click .
- To update the displayed data with the current data of the model, click .
- To scroll the content of the structure pane and of the display pane up , roll the mouse wheel forward.
- To scroll the content of the structure pane and of the display pane down , and roll the mouse wheel backward.
- To zoom the content of the structure pane and of the display pane in , hold down Ctrl and roll the mouse wheel forward.
- To zoom the content of the structure pane and of the display pane out , hold down Ctrl and roll the mouse wheel backward.

<!-- image -->

<!-- image -->

###### Display Pane of the Display Window

The display pane of the display window displays the content of the report which you defined on the tab Content .

<!-- image -->

Proceed as follows to do the following in the structure pane of the display window:

- To scroll the content of the structure pane and of the display pane up , roll the mouse wheel forward.

##### Tab Content

- To scroll the content of the structure pane and of the display pane down , and roll the mouse wheel backward.
- To zoom the content of the structure pane and of the display pane in , hold down Ctrl and roll the mouse wheel forward.
- To zoom the content of the structure pane and of the display pane out , hold down Ctrl and roll the mouse wheel backward.
- To open the respective Frame or the respective object of a picture shown in the report, click the link of the caption line.

<!-- image -->

SimTalk

save [SimTalk] - HtmlReport

See also

Tab Content [HtmlReport]

Tab Content

Tab Content [HtmlReport]

Define the content which the HtmlReport shows on the tab Content .

<!-- image -->

The built-in report provides examples of the most important items that you might use for your standard reports.

The check box to the right of the canvas turns inheritance off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, the value from the parent object from which it was derived. When you change the value of the parent object, Plant Simulation also changes the value of the child object.

- An orange check box with a minus means that inheritance is turned off. Values you type in only apply to the selected object.

You can type in the content of the HtmlReport as text , or you can type in and select settings in the dialog Object Parameters . You define special elements, such as headings, tables, and pictures in text form . For this purpose the HtmlReport provides a markup language which is designed for easy readability. The syntax is a superset of HTML, i.e., you can also type in the text in HTML syntax. We advise against doing this as HTML syntax is complicated to type and hard to read. You can also drag an object from the Frame to the tab Content and drop it there.

You can also drag objects from the Frame onto the icon of the HtmlReport and drop them there.

- If the content of the HtmlReport is inherited, the data of the objects replaces the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.
- If the content of the HtmlReport is not inherited, Plant Simulation appends the data of the objects to the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.

<!-- image -->

To open the dialog Object Parameters for an object, which you added to the tab Content with drag-anddrop , click the mouse between the name of the object and the closing bracket, and click .

<!-- image -->

Then, select the settings you need in the dialog Select Object .

**You can:**

- Use the Default Settings of the HtmlReport
- Define a Heading
- Create a Bulleted List
- Create a Numbered List
- Highlight Text by Bolding and/or Italicizing It

- Indent Text
- Center Text
- Add a Reference to an Object on the HTML Page
- Add an Image of an Object
- Add a Bitmap File
- Collect Object Instances and Show Them
- Insert a Comment into Your Report
- Insert a Horizontal Line
- Insert HTML Tags
- Protect Characters
- Use a String Unchanged in the HTML Code

You can also add some of the formatting options by clicking the respective button on the toolbar.

<!-- image -->

**Toolbar of the HtmlReport**

<!-- image -->

| To do this                                                                                                    | Click   | Key combination        |
|---------------------------------------------------------------------------------------------------------------|---------|------------------------|
| Undo your last action                                                                                         |         | Ctrl+Z                 |
| Apply bold face to the selected text                                                                          |         | Ctrl+B                 |
| Italicize the selected text                                                                                   |         | Ctrl+I                 |
| Convert the selected text to a numbered list                                                                  |         | -                      |
| Convert the selected text to a bulleted list                                                                  |         | -                      |
| Increase the indent of the selected text by one indent level                                                  |         | Ctrl+M                 |
| Decrease the indent of the selected text by one indent level                                                  |         | Ctrl+Shift+M           |
| Insert a nonbreaking space (nonbreaking spaces are not wrapped and double-nonbreaking spaces are not removed) |         | Ctrl+Shift+Hyp hen (-) |
| Insert a page break, which is only visible in the printed report                                              |         | Ctrl+Shift+Ente r      |

**Default Settings of the HtmlReport**

| To do this                                                                         | Click   | Key combination   |
|------------------------------------------------------------------------------------|---------|-------------------|
| Add a Reference to an Object                                                       |         | Ctrl+K            |
| Add an Image of an Object                                                          |         | -                 |
| Add a Bitmap File                                                                  |         | -                 |
| Insert the markup for a heading of level 1 or remove it again                      | -       | Ctrl+1            |
| Insert the markup for a heading of level 2 or remove it again                      | -       | Ctrl+2            |
| Insert the markup for a heading of level 3 or remove it again                      | -       | Ctrl+3            |
| Insert the markup for a heading of level 4 or remove it again                      | -       | Ctrl+4            |
| Insert the markup for a heading of level 5 or remove it again                      | -       | Ctrl+5            |
| Insert the markup for a heading of level 6 or remove it again                      | -       | Ctrl+6            |
| Remove all markups for headings, no matter what level they are                     | -       | Ctrl+0            |
| Insert the markup for centering a line                                             | -       | Ctrl+E            |
| Insert a soft hyphen/ syllable hyphen to allow hyphenating words in the HtmlReport | -       | Ctrl+-            |

**See also**

Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model

###### Default Settings of the HtmlReport

We defined a number of default settings for the HtmlReport .

You can adapt them to your needs with the options described under the Tab Content .

**## Drain Statistics**

The setting ## Drain Statistics shows these values by default.

<!-- image -->

<!-- image -->

| Item English         | Description                                                                                                                                                                                | Read-Only Attribute                       | Item German             |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|-------------------------|
| Object               | Shows the names of all Drain objects within the entire simulation model that removed parts.                                                                                                | -                                         | Objekt                  |
| Name                 | Shows the names of the part types which the Drain in this row removed from the plant.                                                                                                      | -                                         | Name                    |
| Mean Life Time       | Shows the mean life time (throughput time) of all parts of this part type which the Drain in this row removed from the plant.                                                              | StatAvgLifeSpan [SimTalk] - Drain         | Mittlere Durchlaufz eit |
| Total Through put    | Shows the total throughput of all parts of this part type which the Drain in this row removed from the plant.                                                                              | StatDeleted [SimTalk] - Drain             | Durchsatz               |
| Through put per Hour | Shows the number of parts that the Drain removed from the plant in an hour over all observed times during which the Drain was available.                                                   | StatThroughput PerHour [SimTalk] - Drain  | Durchsatz pro Stunde    |
| Producti on          | Shows the time portion during which the parts spent on a resource object of type production .                                                                                              | -                                         | Produktion              |
| Transpor t           | Shows the time portion during which the parts spent on a resource object of type transport .                                                                                               | -                                         | Transport               |
| Storage              | Shows the time portion during which the parts spent on a resource object of type storage .                                                                                                 | -                                         | Lagerung                |
| Value Added          | Shows the time portion during which the parts were processed and were located on resource objects of type production . This is the time during which the value of the parts was increased. | StatProdWorkin gPortion [SimTalk] - Drain | Wertschöp fung          |
| Portion              | Shows the accumulated values of the columns production (green), transport (orange), and storage (red) as bar segments.                                                                     | -                                         | Anteil                  |

**Colors for the Portion**

The colored bars for the Portion show the accumulated values of the columns Production (green), Transport (orange), and Storage (red) as bar segments.

**Default Settings of the HtmlReport**

<!-- image -->

###### Define a Heading

Type in a number sign # at the start of a line to create a heading of level 1.

Type in two number signs ## to create a heading of level 2.

You can specify a maximum of four heading levels, i.e., you can type in ##### .

The HtmlReport also shows the headings of level 1 and 2 in the table of contents in the structure pane on the left-hand side of the HTML page.

**Heading 1 ## Heading 1.1 Text below Heading 1.1. ## Heading 1.2 Text below Heading 1.2.**

The result looks like this:

See also

Show Statistics and Other Values in a Report

**Create a Bulleted List**

###### Create a Bulleted List

Type in an asterisk followed by a space * at the start of a line to create a bulleted list.

Each asterisk followed by a space at the start of a line creates a new bullet. Each bullet can span several lines. Terminate the bulleted list with an empty line.

Instead, you can also click on the toolbar .

Insert a tab stop or type in four spaces at the start of the line, followed by * to create a sublist.

Each additional four empty spaces or each additional tab stop create sub-sublists which are indented further to the right.

* List item 1 * List item 2 * Sublist item 2.1 * Sublist item 2.2 * List item 3 Text after the list...

**The result looks like this:**

<!-- image -->

**See also**

Show Statistics and Other Values in a Report

###### Create a Numbered List

Type in 1. followed by a space 1. at the start of a line to create a numbered list.

Type in 1. at the start of a line creates a new numbered item in the list. Instead of a 1 , you can also type in any other number in front of the numbered item. Plant Simulation ignores the number and always creates the correct numbering which starts with 1. Each numbered item can span several lines. Terminate the numbered list with an empty line.

Instead, you can also click on the toolbar .

Insert a tab stop or type in four spaces at the start of the line, followed by 1. to create a sublist within the numbered list.

Each additional four spaces or each additional tab stop create sub-sublists within the numbered list which are indented further to the right.

1. Numbered item 1 1. Numbered item 2 1. Numbered item 2.1 1. Numbered item 2.2 1. Numbered item 3 Text after the numbered list...

**The result looks like this:**

Note You can also create bulleted sublists within numbered lists.

1. Numbered item 1 1. Numbered item 2 * Sublist item 2.1 * Sublist item 2.2 1. Numbered item 3 Text after the numbered list...

**Create a Numbered List**

<!-- image -->

**See also**

Show Statistics and Other Values in a Report

###### Highlight Text by Bolding and/or Italicizing It

Type in a space followed by an asterisk * , followed by the text , which you would like to show, and then an asterisk followed by a space * , to italicize the enclosed text.

Instead of an empty space, you can also use other spaces, such as a tab stop or a line break. The enclosed text cannot start or end with a space so that italicized text can be distinguished from a bulleted list ( * at the start of a line) and from the multiplication sign ( 2*3 or 2 * 3 ).

The italicized text range can span several lines and paragraphs.

Enclose the text between ** and ** to highlight this text in bold face .

Enclose the text between *** and *** to highlight this text in bold face and to italicize it.

You can also increase highlighting consecutively: If you use * in already italicized text, it will be displayed in bold face in addition. If your text is already bolded , and you use * , it will be displayed in bold face and will be italicized .

Text can be *italicized* or **bolded** or ***bolded and italicized.***

**Important: *Essential information.* Do not ignore!**

The result looks like this:

**Note**

Plant Simulation does not interpret the character combination space asterisk * as the start of italicized text to prevent that object references, such as *.MUs.Part:1 , are going to be misinterpreted.

Instead, you can also click

**See also**

Show Statistics and Other Values in a Report

/

on the toolbar

.

###### Indent Text

Type in a greater than sign &gt; at the start of a line to indent a paragraph.

The paragraph can span several lines. Terminate it with an empty line. To indent the paragraph more, type in more than one greater than sign &gt;&gt; at the start of the line.

> This paragraph is indented. Non-indented body text after the indented paragraph.

The result looks like this:

See also

Show Statistics and Other Values in a Report

###### Center Text

Type in a greater than sign followed by a less-than sign &gt;&lt; at the start of a line to center the text in this line.

>< This text is centered. This text is left-aligned.

The result looks like this:

See also

Show Statistics and Other Values in a Report

Add a Reference to an Object

Add a Reference to an Object on the HTML Page

Specify the settings for displaying a reference to an object on the HTML page.

Typing Object Parameters into the Dialog Object Parameters

To select an object or an object attribute to be displayed on the HTML page, click on the toolbar

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

. Then select the object and/or the value of an attribute or a method of this object, which you would like to show, in the dialog Select Object . Click OK .

<!-- image -->

<!-- image -->

In this case the path, which was detected within brackets when you held down Shift while clicking Add Object is preselected.

Type in the Caption which the HtmlReport shows below the statistics table on the HTML page.

Select the Statistics table type you want to show for the object. The different object types provide different statistics table types.

If the text cursor is located within an object reference ([…]), Plant Simulation opens the dialog Select Object Parameters . In this case the object parameter is preselected that was detected within brackets

when you clicked Add Object

.

<!-- image -->

<!-- image -->

You can:

- Display an Attribute of an Object
- Display an AttributeExplorer
- Display a Broker
- Display a Chart
- Display a Checkbox
- Display an Object of Type Comment
- Display a DataTable or a DataList
- Display a Drain
- Display an Object of Type Display
- Display a Dropdown List
- Display a FileLink
- Compute a Formula
- Display a Frame
- Display a GanttChart
- Display a HtmlReport
- Display an Icon of an Object
- Display a Method
- Display a Picture of a 3D Scene
- Display a PythonModule
- Display a SankeyDiagram
- Display Statistics Values of an Object as a Table
- Display a Table from the SQLite Interface
- Display a Variable

Typing in the Parameters on the Tab Content

You also type in the instructions that correspond to the settings you can type into the dialog.

Type in an opening bracket, followed by the name of the object, followed by the closing bracket [ObjectName] to access that object, to read attribute values of this object, to use its icon, or to display the object itself on the HTML page.

To display the value of an attribute on the HTML page, you can also type in the path to the attribute in brackets. Relative paths are resolved starting with the Frame in which the HtmlReport is located. To read the attributes of the HtmlReport itself, use the identifier self to access it.

Depending on the type of object, you can add additional arguments to fine-tune the HTML output. You can either add arguments in a specific order separated by commas or by name separated by white spaces.

Compare these examples, which produce the same output.

[.Models.Model._3D, "caption", 100%, %planningview]

[.Models.Model._3D Caption="caption" ScaleTo=100% PlanningView=true]

If the attribute contains a floating point value, you can round the value by typing in the number of decimal places, separated by a comma.

To force a certain number of decimal places, even when these are zeros, type a 0 in front of the number of decimal places.

[Station1.statFailPortion] [Station1.statFailPortion, 2]  // round to 2 digits [Station1.statFailPortion, 02] // 2 decimal places

The result looks like this:

Typing in * to Display all Instances of an Object

Instead of displaying a single object on an HTML page by typing in its name within brackets, you can also display all instances of an object one after the other.

To do so, type in an asterisk * after the path to the object. Plant Simulation then displays all instances which inherit directly or indirectly from the object and which are located in the Frame into which you inserted the HtmlReport . This includes sub-Frames .

The result looks like this:

<!-- image -->

[.UserInterface.HtmlReport*]     // gathers all HtmlReports inserted into the model

The result looks like this:

<!-- image -->

If you select a Frame to be inserted, which provides the user-defined attribute named StatisticsObject , the dialog Object Parameters shows the available statistics functions.

If you create a user-defined attribute named ReportObject for an object, Plant Simulation does not display this object but the ReportObject instead. If the user-defined attribute has the data type object , Plant Simulation displays the object which the attribute references. In many cases this will be an HtmlReport which inserts its report into the HTML page. If you want to insert a DataTable or the result of a method call, you do not have to reference an object of type DataTable or Method , but you can set the data type of the user-defined attribute to table or method and define the table or method directly in the attribute.

If you want to reference another object in a Frame , you do not have to create a user-defined attribute of data type object , but you can rename an inserted object to ReportObject . This object will then be displayed on the HTML page instead of the Frame .

See also

Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model

**Display an Attribute of an Object**

Display attributes with a certain precision.

Specify Named Arguments

For the data types Real , Length , Weight , Speed , Time , and Acceleration the named argument Precision specifies the Integer Places and/or the Decimal Places with which the attribute is shown in the HtmlReport .

The example shows two decimal places of our user-defined attribute named a of the Station .

[Station.a precision=2]

Display an AttributeExplorer

Specify the settings for displaying an AttributeExplorer on the HTML page.

Select the Object in the Dialog Select Object

To select an AttributeExplorer whose attribute table you want to show on the HTML page, click on the toolbar . Then select the AttributeExplorer in the dialog Select Object and click OK .

Type in the Parameters on the Tab Content

You can type in the following instructions to set the columns to be displayed.

[AttributeExplorer] [AttributeExplorer, "Tab. 1: Mean value of the throughput times"] [AttributeExplorer, 0, 2..4, 7] [AttributeExplorer, *..4, 7] [AttributeExplorer, 0, 2..4, 7..*] [AttributeExplorer, 0, 2..4, 7, #ColumnName]

The result looks like this:

<!-- image -->

<!-- image -->

<!-- image -->

**See also**

**Show Statistics and Other Values in a Report**

**Display a Broker**

**Display a Broker**

Specify the settings for displaying a Broker on the HTML page.

Type Object Parameters into the Dialog Object Parameters

To display the statistics table of the Broker on the HTML page, click on the toolbar

. Then select the Broker in the dialog Select Object and click OK .

Type in the Caption which the HtmlReport shows below the statistics table of the Broker .

Select the Statistics table type you want to show for the Broker .

<!-- image -->

If you do not select the Statistics Type Table , the HtmlReport displays the broker statistics table .

[MyBroker] // our Broker is called MyBroker [MyBroker, "Tab. 1: Broker Service Statistics"] [Broker1, 0, 2..4, 7] [Broker2, *..4, 7] [Broker3, 0, 2..4, 7..*]

The result looks like this:

<!-- image -->

See also

Display Statistics Values of an Object as a Table

**Show Statistics and Other Values in a Report**

**Display a Chart**

**Display a Chart**

Specify the settings for displaying a Chart on the HTML page.

Type Object Parameters into the Dialog Object Parameters

To select an Chart whose diagram picture you want to show on the HTML page, click on the toolbar

<!-- image -->

<!-- image -->

. Then select the Chart in the dialog Select Object and OK .

<!-- image -->

Type in the Caption which the HtmlReport shows below the Chart .

Type in the Image Width with which the HtmlReport shows the picture of the object. You can also type in an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted.

Type in the Image Height with which the HtmlReport shows the picture of the object. You can also type in an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted.

<!-- image -->

Type in the Parameters on the Tab Content

Instead, you can also type in the instructions that correspond to the settings you can enter into the dialog.

[StationChart] // our Chart is called StationChart [StationChart, 80, 60] [StationChart, "This is my caption"] [StationChart, "This is my caption", 80, 60]

The result looks like this:

<!-- image -->

**Specify Named Arguments**

- The named argument Caption specifies the caption with which the specified Chart is shown in the HtmlReport .
- The named argument Size specifies the size with which the specified Chart is shown in the HtmlReport . You can specify the size like this:
- Do not specify the argument to show the picture of the Chart with its default size.
- Specify [*, y] to set the height of the picture of the Chart to y and to use the width of the default width of the picture.
- Specify [x, *] to set the width of the picture of the Chart to x and to use the height of the default height of the picture.
- Specify [x, y] to scale the picture of the Chart to the size x and the height y. This might distort the picture though.

[Chart Caption="This is my caption"]

[Chart Size=80,60]

**See also**

Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model

**Display a Checkbox**

Specify the settings for displaying a Checkbox on the HTML page.

Specify Object Parameters in the Dialog Object Parameters

To display a Checkbox , which you inserted into your simulation model, on the HTML page, click on

<!-- image -->

the toolbar . Then select the Checkbox in the dialog Select Object and click OK

To show the Label of the object Checkbox to the right of the check mark on the HTML page, select the check box.

<!-- image -->

To display the Label of the check box to the right of the icon , you can also type in the following:

<!-- image -->

The result looks like this:

To display the Label of the check box to the left of the icon , type in:

<!-- image -->

The result looks like this:

Specify Named Arguments

The named argument CheckBeforeText specifies if the check mark of the Checkbox is shown to the left of the text in the HtmlReport ( true ) or if it is shown to the right ( false ).

The default value is false.

[Checkbox CheckBeforeText=true]

**See also**

Show Statistics and Other Values in a Report

**Display an Object of Type Comment**

Specify the settings for displaying an object of type Comment on the HTML page.

Select the Object in the Dialog Select Object

<!-- image -->

To display a Comment , which you inserted into your simulation model, on the HTML page, click on the toolbar . Then select the Comment in the dialog Select Object and click OK .

<!-- image -->

The HtmlReport shows the text you typed in on the tab Comment to draw attention to information that you deem important. When you click the text/link, Plant Simulation opens the Comment object on the tab Comment .

<!-- image -->

<!-- image -->

Specify the Parameters on the Tab Content

Instead of selecting the object, you can also type it in directly:

<!-- image -->

**Display a DataTable or a DataList**

Specify the settings for displaying a DataTable/list object on the HTML page.

Specify Object Parameters in the Dialog Object Parameters

To display a DataTable or a list object ( DataList , DataQueue , DataStack ) in table form on the HTML page, click on the toolbar . Then select the DataTable/list object in the dialog Select Object and click OK .

Type in the Caption which the HtmlReport shows below the DataTable/List .

Type in the identifiers of the List columns of the DataTable/list object which the HtmlReport shows on the HTML page.

<!-- image -->

Specify the Parameters on the Tab Content

Instead, you can also type in the instructions that correspond to the settings you can type into the dialog.

[ThroughputList] // our DataTable is called ThroughputList [ThroughputList, "Figure 1: Mean value of the throughput times"] [ThroughputList, 0, 2]       // columns 0 and 2 [ThroughputList, *..4, 7]    // all columns until column 4 and column 7 [ThroughputList, 0, 2..4, 7..*] [ThroughputList, 0, 2..4, 7, #MyColumnName] // columns 0, 2 to 4, and column 7, and the columns named MyColumnName

The result looks like this:

<!-- image -->

Access Cells of Lists and Tables to Add Their Content to the HtmlReport

The syntax for accessing cells of lists and tables to add their content to the HtmlReport is similar to the syntax used in formulas:

[MyDataTable[Column, Row]]

You can specify the Column or Row with its number or with its index (if available). The text in the column or row index has to be surrounded by quotation marks and has to be started with the number sign/hash # :

[MyDataTable[1, 1]] [MyDataTable["Name", 1]] [MyDataTable["Name", "Part type 1"]] [MyDataTable[#Name, 1]] [MyDataTable[#Name, #Part type 1]]

You have to protect characters, that have a special meaning in the HtmlReport , within the text of the column index:

[MyDataTable["\"Name\"", 1] [MyDataTable["Speed\, km/h", 1]] [MyDataTable[#Speed\, km/h, 1]]

Specify Named Arguments

- The named argument Caption specifies the caption with which the DataTable is shown in the HtmlReport .
- The named argument Columns specifies the columns of the DataTable that are shown in the HtmlReport .

[DataTable Caption=Test Columns=[1,3,4]]

See also

Show Statistics and Other Values in a Report

Protect Characters

getHTMLCode [SimTalk] - lists

**Display an Object of Type Display**

Specify the settings for displaying an object of type Display on the HTML page.

Specify Object Parameters in the Dialog Object Parameters

To display the numeric value of an object of type Display on the HTML page, click on the toolbar . Then select the Display in the dialog Select Object click OK .

and

To use the Font Size and the Font Color , which you selected for the object Display , on the HTML page, select .

<!-- image -->

Specify the Parameters on the Tab Content

Instead, you can also type in the instructions that correspond to the settings you can type into the dialog.

You can type in true or false as the optional parameter. If you type in true , Plant Simulation displays the value using the Color and the Font Size which you selected on the tab Display of the Display .

[Display] [Display, true] [Display, false]

The result looks like this:

<!-- image -->

<!-- image -->

Specify Named Arguments

The named argument UseFontStyle specifies if the Display is shown in the HtmlReport with the Font Size and the Font Color of the Display object ( true ) or if it is shown with default values ( false ).

The default value is false.

[Display UseFontStyle=true]

See also

Show Statistics and Other Values in a Report

**Display a Drain**

Specify the settings for displaying an object of type Drain on the HTML page by specifying object parameters.

Specify Object Parameters in the Dialog Object Parameters

To display statistics values of the Drain as a table on the HTML page, click on the toolbar

. Then select the Drain in the dialog Select Object and click OK .

Type in the Caption which the HtmlReport shows below the statistics table of the Drain .

Select the Statistics Table Type you want to show for the Drain .

<!-- image -->

If you do not select the Statistics Type Table , the HtmlReport displays the same report on the HTML page that you can activate by checking Show Summary Report in the EventController . The Drain report does not show the first column with the name of the Drain as each Drain has its own Drain report in case no matching statistics table was provided.

Specify the Parameters on the Tab Content

Instead, you can also type in the instructions that correspond to the settings you can enter into the dialog.

<!-- image -->

See also Display Statistics Values of an Object as a Table Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model Display a Dropdown List Specify the settings for displaying an object of type DropDownList on the HTML page.

Select the Object in the Dialog Select Object

To display the text of the selected item of a DropDownList , which you inserted into your simulation

<!-- image -->

model, on the HTML page, click on the toolbar . Then select the DropDownList in the dialog Select Object and click OK .

Specify the Parameters on the Tab Content

Instead, you can also type in

[DropDownList]

The result looks like this:

See also

Show Statistics and Other Values in a Report

**Display a FileLink**

**Display a FileLink**

Specify the settings for displaying an object of type FileLink on the HTML page.

Specify Object Parameters in the Dialog Object Parameters

To display a Bitmap file or an SVG file , which you imported with a FileLink , on the HTML page. Then select the bitmap file or the SVG file in the dialog of the FileLink and click OK .

<!-- image -->

<!-- image -->

Click on the toolbar . Then select the DropDownList in the dialog Select Object and click OK .

Type in the Caption which the HtmlReport shows below the FileLink image file.

Type in the Image Size in percent to which the HtmlReport scales the screenshot of the FileLink . Instead, you can also enter the Image Width and the Image Height . You can also type in an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted. The relative size takes precedence over the absolute size.

<!-- image -->

[FileLink, "Siemens logo imported via the FileLink", 110%]

The result looks like this:

**Specify Named Arguments**

- The named argument Caption specifies the caption with which the specified FileLink linked to a picture is shown in the HtmlReport .
- The named argument Size specifies the size of the icon (or of the non-SVG file ).

[FileLink Caption="Siemens logo imported via the FileLink"]

You can specify the size like this:

- Specify * or [*, ] or do not specify the argument to show the icon with its default size.
- Specify [*, y] to set the height of the icon to y and to use the width of the default width of the icon.
- Specify [x, *] to set the width of the icon to x and to use the height of the default height of the icon.
- Specify a percentage to scale the icon by the specified factor.
- Specify [x, y] to scale the icon to the size x and the height y. This might distort the icon though.

The named argument Size specifies the size of the SVG file .

You can specify the size like this:

- Do not specify the argument to show the picture with its default size.
- Specify [*, y] to set the height of the picture to y and to use the width of the default width of the picture.

**Display a FileLink**

- Specify [x, *] to set the width of the picture to x and to use the height of the default height of the picture.
- Specify [x, y] to scale the picture to the size x and the height y. This might distort the picture though.

[FileLink Size=110%]

**See also**

Show Statistics and Other Values in a Report

**Display a Frame**

Specify the settings for displaying a Frame on the HTML page.

Specify Object Parameters in the Dialog Object Parameters

<!-- image -->

To display a screenshot of a Frame , which contains the icons of all objects inserted into this Frame , on the HTML page, click on the toolbar .

Then select the Frame whose screenshot you would like to show and click OK .

Type in the Caption which the HtmlReport shows below the Frame . If you do not type in a Caption , the report shows the path to the Frame as the caption .

Type in the relative Image Size in percent to which the HtmlReport scales the screenshot of the object. Instead, you can also type in the Image Width and the Image Height . You can also type in an asterisk * for either the Width or the Height to ensure that the image will not be distorted. The relative size takes precedence over the absolute size.

<!-- image -->

Specify the Parameters on the Tab Content

You can also set the size of the screenshot on the HTML page by typing in these instructions:

- Type in an asterisk * to zoom the screenshot out, when you zoom the report window out. When zooming in, the icon is never enlarged to more than its original size.
- Type in a number and the percent sign % to scale the screenshot with this value.
- Type in the width and the height of the image in millimeters to show the screenshot with these measurements. You can also type in an asterisk * for either the Width or the Height to ensure that the image will not be distorted.

[MyEngines] // our Frame, which we inserted into 'MyPlant', is called 'MyEngines' [MyEngines, *] [MyEngines, 150%] [MyEngines, 100, 150]

[MyEngines, 100, *] [MyEngines, *, 150] [MyEngines, "This is my caption"] [MyEngines, "This is my caption", *] [MyEngines, "This is my caption", 150%] [MyEngines, "This is my caption", 100, 150] [MyEngines, "This is my caption", 100, *] [MyEngines, "This is my caption", *, 150]

**The result looks like this:**

<!-- image -->

If you create a user-defined attribute named ReportObject for an object, Plant Simulation does not display the object itself anymore, but its ReportObject instead. If the user-defined attribute has the data type object , Plant Simulation shows the object which the attribute references. In many cases this will be a HtmlReport which inserts its report into the HTML page. To insert a DataTable or the result of a method call, you do not have to reference an object of type DataTable or Method , but you can set the data type of the user-defined attribute to table or method respectively and define the DataTable or Method respectively in the attribute.

If you want to reference another object in a Frame , you do not have to create a user-defined attribute of data type object , but you can name an inserted object ReportObject . This object will then be shown instead of the Frame on the HTML page.

In this case only the parameters of the HtmlReport apply, not those of the 2D Frame , or of the 3D Frame .

Specify Named Arguments

The HtmlReport provides the same named arguments as a picture of a 3D scene for showing a Frame .

See also

Show Statistics and Other Values in a Report Display a HtmlReport getHTMLCode [SimTalk] - Frame getHTMLCode [SimTalk] - Chart

**Display a GanttChart**

**Display a GanttChart**

Specify the settings for displaying an object of type GanttChart on the HTML page.

Select the Object in the Dialog Select Object

To display the diagram picture of a GanttChart on the HTML page, click on the toolbar

<!-- image -->

<!-- image -->

. Then select the GanttChart in the dialog Select Object and click OK .

Specify the Parameters on the Tab Content

Instead, you can also type in the instructions that correspond to the settings you can enter into the dialog.

**GanttChart [GanttChart, "My Caption", 0.5] // adds our GanttChart with a time scale of 0.5, with the caption My Caption.**

The result looks like this:

<!-- image -->

Drag the scroll bar to the right to scroll to the right in the GanttChart .

Specify Named Arguments

- The named argument Caption specifies the caption with which the GanttChart is shown in the HtmlReport .

[GanttChart Caption="My Caption"]

- The named argument Scale sets the scaling on the time axis with which the GanttChart is shown in the HtmlReport .

[GanttChart Scale=0.5]

See also

GanttChart [object]

Show Statistics and Other Values in a Report

Show Reports in a Hierarchically Structured Model

exportChart [SimTalk]

**Display a HtmlReport**

Display a HtmlReport

Specify the settings for displaying an object of type HtmlReport on the HTML page.

Select the Object in the Dialog Select Object

To display an HtmlReport on the HTML page, click on the toolbar

<!-- image -->

<!-- image -->

and select it or type its name within brackets. Then select the HtmlReport which you would like to show and click OK .

<!-- image -->

<!-- image -->

Specify the Parameters on the Tab Content

You can specify an object as argument for the HtmlReport . You can then access the object in the called HtmlReport by typing in @ within brackets, [@] . This is especially useful if you want to display several objects in the same way.

At times, you might also display an HtmlReport on its own and also embed it as part of a larger report. Suppose that you model a production line in a sub-Frame and assign this sub-Frame an HtmlReport . In this case you might want to display the HtmlReport individually on its own but also integrate it into the HtmlReport of the surrounding Frame . Then you might want to treat the heading for the sub-report different from for the individual report. You might, for example, want to display headings of level 1 in the sub-report as headings of level 2 and headings of level 2 as headings of level 3, etc. Then you can specify the numbers sign/hash # in the HtmlReport . You can also specify several number signs ## . The HtmlReport increases the heading levels by 1 per a single number sign, meaning that the size of the heading levels is decreased.

[HtmlReport2] [HtmlReport2, Station1] [HtmlReport2, Station1, #]

If you create a user-defined attribute named ReportObject for an object, Plant Simulation does not display the object itself anymore, but its ReportObject instead. If the user-defined attribute has the data type object , Plant Simulation shows the object which the attribute references. In many cases this will be a HtmlReport which inserts its report into the HTML page. To insert a DataTable or the result of a method call, you do not have to reference an object of type DataTable or Method , but you can set the data type of the user-defined attribute to table or method respectively and define the DataTable or Method respectively in the attribute.

If you want to reference another object in a Frame , you do not have to create a user-defined attribute of data type object , but you can name an inserted object ReportObject . This object will then be shown instead of the Frame on the HTML page.

You can also create sub-reports for all instances of an object. To do so, type in the path to the object, followed by an asterisk * ) as parameter. Plant Simulation then calls the specified HtmlReport for all instances which inherit directly or indirectly from the object, and which are inserted into the Frame , in which the outer HtmlReport is located. This also includes sub-Frames .

[HtmlReport2, .MaterialFlow.Station*]

See also

HtmlReport [object]

Show Statistics and Other Values in a Report

Collect Object Instances and Show Them

**Display an Icon of an Object**

Specify the settings for displaying an icon of an object on the HTML page.

Type Object Parameters into the Dialog Object Parameters

<!-- image -->

To display the icon of an object on the HTML page, click on the toolbar

<!-- image -->

. Then select the object whose icon you want to show in the dialog Select Object and click OK .

<!-- image -->

Select the icon you want to show and click OK .

<!-- image -->

Type in the Caption which the HtmlReport shows below the icon.

Either type in the Image Size in percent.

Or type in the Image Width and the Image Height .

<!-- image -->

The settings in the dialog Object Parameters translate to this statement:

[!.Models.Model.Station, "Operational", "Operational icon", 200, 200]

Specify Named Arguments

**Note**

When specifying named arguments to display an object icon, you have to type in an exclamation mark ! in front of the actual statement.

- The named argument Icon specifies the icon of the object that is going to be shown in the HtmlReport . Specify a string to show the icon with the specified name of the specified object. Specify a number to show the icon with the specified number of the specified object. The number 2 for
- example shows the second icon of the object.

If you not specify the named argument Icon , Plant Simulation shows the active icon.

- The named argument Caption specifies the caption with which the specified icon of the object is shown in the HtmlReport .
- The named argument Size specifies the size of the icon.

You can specify the size like this:

- Specify * or [*, *] or do not specify the argument to show the icon with its default size.
- Specify [*, y] to set the height of the icon to y and to use the width of the default width of the icon.
- Specify [x, *] to set the width of the icon to x and to use the height of the default height of the icon.
- Specify a percentage to scale the icon by the specified factor.

- Specify [x, y] to scale the icon to the size x and the height y. This might distort the icon though.

[!Station Icon=Operational]

**Display a Method**

Specify the settings for displaying an object of type Method on the HTML page.

Specify the Parameters on the Tab Content

To run the Method , whose name you type in brackets, and to display the return value on the HTML page, type in the following instructions.

Within parentheses, you can also pass parameters to the Method .

[Method] [Method(Argument1, Argument2])

The source code of our Method named MyMethod queries the x-position and the y-position of the object named MyStation .

The source code looks like this:

```simtalk
param obj: object ->string
return to_str("x=", obj.XPos, ", y=", obj.YPos)
```

The following statement displays these positions in the HtmlReport .

[MyMethod(MyStation)]

The result looks like this:

See also

Method

Show Statistics and Other Values in a Report

Display a PythonModule

You might want to display an object of type PythonModule on the HTML page in the HtmlReport to make use of the vast array of charting and display libraries that are available for Python .

Specify the settings for displaying a PythonModule by doing the following.

Select the Object in the Dialog Select Object

To display a PythonModule , which you inserted into your simulation model, on the HTML page, click on the toolbar . Then select the PythonModule in the dialog Select Object and click OK .

The HtmlReport then adds [PythonModule] to the Tab Content .

If you do not specify a function, the PythonModule shows its source code in the HtmlReport .

Specify Named Arguments

The named argument Call specifies the function that is going to be called and whose return value, provided it has the data type string , is to be shown in the HtmlReport .

[PythonModule Call="multiply"]

See also

PythonModule Display a SankeyDiagram Specify the settings for displaying an object of type SankeyDiagram on the HTML page.

Select the Object in the Dialog Select Object

To display the diagram picture of a SankeyDiagram on the HTML page, click on the toolbar

<!-- image -->

<!-- image -->

. Then select the SankeyDiagram in the dialog Select Object and click OK .

<!-- image -->

<!-- image -->

Type in the Parameters on the Tab Content

Instead, you can also or type in the following instructions. The syntax resembles the syntax of the Frame , as the SankeyDiagram also depicts Frame images.

Path[, Title][, SizeParameters]

You might, for example, type in these instructions:

[SankeyDiagram, Workers Sankey flows, 90, 90] [SankeyDiagramm1, Parts Sankey flows, 85%]

If we do not specify a size, the depiction looks best though:

<!-- image -->

<!-- image -->

In 3D Only models you can type in the camera position and the camera rotation in addition:

Path[, Title][, SizeParameters][[CameraPosX, CameraPosY, CameraPosZ], CameraRotX, CameraRotZ]

If you do not specify any camera parameters, Plant Simulation shows the SankeyDiagram in the Planning View .

Specify Named Arguments

In a 3D Only model a SankeyDiagram expects the same named arguments as a picture of a 3D scene . If you do not specify the argument PlanningView , a SankeyDiagram will be shown in the PlanningView .

- The named argument Type "exclusive" specifies that the SankeyDiagram is shown by itself in the HtmlReport .
- The named argument Type "additional" specifies that the SankeyDiagram is shown together with the other visible Sankey Diagrams in the HtmlReport .
- The named argument Type "all" specifies that all Sankey Diagrams of the Frame , in which the SankeyDiagram is located, are shown in the HtmlReport .

[SankeyDiagram Type="exclusive"]

[SankeyDiagram Type="additional"]

[SankeyDiagram Type="all"]

**Default Value of the Parameter**

The default value is "exclusive".

**Note**

The named arguments Type "exclusive", Type "additional", Type "all" only work in simulation models with the model language English, Chinese, Japanese , and Hungarian .

The named arguments Type "exklusiv", Type "zusätzlich", Type "alle" only work in simulation models with the model language German .

See also

SankeyDiagram

Display a Frame Show Statistics and Other Values in a Report Show Reports in a Hierarchically Structured Model

**Display Statistics Values of an Object as a Table**

Specify the settings for displaying statistics values of an object as a table on the HTML page.

Select the Object in the Dialog Select Object

<!-- image -->

To display statistics values as a table, click on the toolbar . Then select the object for which you would like to show statistics values. Click OK .

<!-- image -->

<!-- image -->

Type in the Caption which the HtmlReport shows below the statistics table on the HTML page.

Select the Statistics Table Type you want to show for the object. The different object types provide different table types. If you do not type anything into the text box List Columns , the HtmlReport shows all portions.

<!-- image -->

The settings above result in this source code:

<!-- image -->

The result might look like this:

<!-- image -->

To only show certain columns, type in their column index, separated by commas, into the text box List columns , for example.

The settings above result in this source code:

<!-- image -->

The result might look like this:

<!-- image -->

**Note**

If the selected object collected statistics values, the HtmlReport shows values in a table. If the object did not collect statistics, the HtmlReport naturally cannot show any data.

If the HtmlReport lists several objects one below the other, it aggregates their values if possible, i.e., it lists their values row-by-row in a table. If the HtmlReport cannot aggregate the values, it shows the non-aggregated values and starts a new table. If you want to show instances of a class object, the HtmlReport lists the values of all instances row-by-row.

As statistics data can cover various values, the objects provide a number of different settings you can select in the drop-down list Statistics Table Type :

| Drop-down list item                                                      | corresponds to this text you can type in, English      | corresponds to this text you can type in, German        |
|--------------------------------------------------------------------------|--------------------------------------------------------|---------------------------------------------------------|
| Portions of the States                                                   | %ResStates                                             | %Stati                                                  |
| Material Flow Properties                                                 | %MatFlowProperties                                     | %Matflusseigenschaften                                  |
| Rotation Time                                                            | %RotationTime ( Turnplate , Turntable , PickAndPlace ) | %Drehungszeit ( Drehplatte , Drehtisch , PickAndPlace ) |
| Moving Time                                                              | %MovingTime ( Converter )                              | %Umsetzzeit ( Umsetzer )                                |
| Working Time                                                             | %WorkingTime                                           | %Arbeitszeit                                            |
| Set-up Time                                                              | %SetupTime                                             | %Rüstzeit                                               |
| Waiting Time                                                             | %WaitingTime                                           | %Wartezeit                                              |
| Blocked Time                                                             | %BlockedTime                                           | %Blockiertzeit                                          |
| Powering up/down Time                                                    | %PowerUpDownTime                                       | %HochHerunterfahrzeit                                   |
| Stopped Time                                                             | %StoppedTime                                           | %Angehaltenzeit                                         |
| Failed Time                                                              | %FailedTime                                            | %Störungszeit                                           |
| Paused Time                                                              | %PausedTime                                            | %Pausenzeit                                             |
| Empty Time                                                               | %EmptyTime                                             | %Leerzeit                                               |
| Material Flow Properties of Mobile Units                                 | %MUMatFlowProperties                                   | %BEMatflusseigenschaften                                |
| Empty Time of Mobile Units                                               | %MUEmptyTime                                           | %BELeerzeit                                             |
| Cumulated Statistics of the Parts Which the Drain Deleted                | %DrainCumulated                                        | %SenkeKumuliert                                         |
| Part Types Which the Drains Deleted                                      | %DrainAllTypes                                         | %SenkeAlleTypen                                         |
| Detailed Portions of the Part Types which the Drain Deleted              | %DrainTypesPortions (non summable)                     | %SenkeTypenanteile (nicht addierbar)                    |
| Detailed Times of the Part Types which the Drain Deleted                 | %DrainTypesTimes (non summable)                        | %SenkeTypenzeiten (nicht addierbar)                     |
| Total Consumption and Portions of the Energy States                      | %Energy                                                | %Energie                                                |
| Product-Oriented Statistics of all Existing and Deleted MUs (by Classes) | %MUClassStatistics                                     | %BEKlassenStatistik                                     |
| Mean Time Portions of a MUClass of the Mean Life Span                    | %MUClassTimePortions                                   | %BEKlassenZeitanteile                                   |

| Drop-down list item                                        | corresponds to this text you can type in, English   | corresponds to this text you can type in, German   |
|------------------------------------------------------------|-----------------------------------------------------|----------------------------------------------------|
| Mean Time Portions of a Individual MUof the Mean Life Span | %MUTimePortions                                     | %BEZeitanteile                                     |
| Usage of the Transporters                                  | %TransUsageTime                                     | %TransVerwendungszeit                              |
| Ready Times                                                | %TransReadyTime                                     | %TransBereitzeit                                   |
| Pauses                                                     | %TransPausedTime                                    | %TransPausenzeit                                   |
| Failures                                                   | %TransFailedTime                                    | %TransStörungszeit                                 |
| Traveled Distance                                          | %TransTraveledDistance                              | %TransWegstrecke                                   |
| Battery                                                    | %TransBatteryTime                                   | %TransBatteriezeit                                 |
| Broker Statistics                                          | %Broker                                             | %Broker                                            |
| Mediation Time                                             | %BrokerMediationTime                                | %BrokerVermittlungsdauer                           |
| Dwelling Time                                              | %BrokerDwellTime                                    | %BrokerVerweildauer                                |
| Capacities and States of the Exporters                     | %Exporter                                           | %Exporter                                          |
| Time Portions of the Exporters                             | %ExporterTimePortions                               | %ExporterZeitanteile                               |
| Traveled Distance by Workers                               | %WorkerTraveleledDistance                           | %WerkerWegstrecke                                  |
| Importers Waiting for Services and Parts                   | %ImporterWaiting                                    | %ImporterWartend                                   |
| Waiting Times for Services and Parts                       | %ImporterWaitingTime                                | %ImporterWartezeit                                 |
| Waiting Times for Parts                                    | %ImporterMUWaitingTime                              | %ImporterBEWartezeit                               |
| Waiting Times for Set-up Exporters                         | %ImporterSetpWaitingTime                            | %ImporterRüstWartezeit                             |

If you did not select a Statistics Type Table , the HtmlReport shows these default statistics types:

| Object                               | Default Type, English   | Default Type, German     |
|--------------------------------------|-------------------------|--------------------------|
| Part                                 | %MUTimePortions         | %BEZeitanteile           |
| Container                            | %MUMatFlowProperties    | %BEMatFlusseigenschaften |
| Transporter                          | %TransUsageTime         | %TransVerwendungszeit    |
| Worker                               | %WorkerTraveledDistance | %WerkerWegstrecke        |
| Turnplate , Turntable , PickAndPlace | %RotationTime           | %Drehungszeit            |
| Converter                            | %MovingTime             | %Umsetzzeit              |
| Drain                                | %DrainCumulated         | %SenkeKumuliert          |

| Object            | Default Type, English   | Default Type, German     |
|-------------------|-------------------------|--------------------------|
| Exporter          | %Exporter               | %Exporter                |
| Broker            | %BrokerMediationTime    | %BrokerVermittlungsdauer |
| All other objects | %States                 | %Stati                   |

Specify the Parameters on the Tab Content

Instead of selecting the Statistics Table Type in the dialog and typing the caption, you can also type the instructions into the tab Contents of the dialog of the HtmlReport :

```simtalk
[Object path, caption, statistics table type]
```

You might, for example, type in:

[Receiving, "Statistics of the Source 'Receiving'", %States] [Station, "My values", %States, 1..4]                 // shows columns 1 to 4 [Station, "My values", %States, #Working, #SettingUp] // shows columns 1 and 2

See also

Display a Drain

Display a Broker

Show Statistics and Other Values in a Report

**Display a Table from the SQLite Interface**

Display a Table from the SQLite Interface

Specify the settings for displaying a table containing data of a table of the SQLite interface on the HTML page.

Select the Object in the Dialog Select Object

To display data of a table of the SQLite interface on the HTML page, click on the toolbar

<!-- image -->

. Then select the SQLite interface in the dialog Select Object and click OK .

Specify the Parameters on the Tab Content

This instruction displays the contents of the table called MUTrace .

[MySQLite, "select * from MUTrace"]

**Specify Named Arguments**

- The named argument Statement specifies the SQL statement of the SQLite object which is shown in the HtmlReport .
- The named argument MaxRows shows the maximum number of rows which the SQLite object shows in the HtmlReport .

[MySQLite Statement="select * from MUTrace"]

[MySQLite MaxRows=5]

See also

**SQLite**

Show Statistics and Other Values in a Report

**Display a Variable**

Specify the settings for displaying the contents of a Variable , according to the type of its contents on the HTML page.

Select the Object in the Dialog Select Object

To display the contents of a Variable on the HTML page, click on the toolbar

. Then select the Variable in the dialog Select Object and click OK .

If the Variable has the data type real , length , money , weight , time , speed , or acceleration , you can specify the Number of Decimal Places and/or the Number of Integer Places to which the value will be rounded as an optional parameter.

If the Variable contains a DataTable/List object , it will be treated like a reference to a DataTable/List object , and you can parametrize it just like these. In the other case you cannot enter any parameters.

If the Variable references an object, Plant Simulation displays the path of the object. If this object does not exist, the report shows a question mark ( ? ) after the Path .

Plant Simulation inserts all other values, in some cases with the respective unit, as text.

```simtalk
[Variable] [Variable, "Tab. 1: List of all tabular values"] [Variable, 0, 2..4, 7] [Variable, *..4, 7] [Variable, 0, 2..4, 7..*] [>Variable] // Shows the object specific content instead of the // object path if the variable references an object.
```

**Specify Named Arguments**

The named argument Precision specifies the Number of Decimal Places and/or the Number of Integer Places with which the Variable is shown in the HtmlReport .

[Variable Precision=5]

See also

