### Variable

Show Statistics and Other Values in a Report

###### Display a Picture of a 3D Scene

Specify the settings for displaying a picture of a 3D scene on the HTML page.

Typing in the Parameters on the Tab Content

[Object._3D] [Object._3D, w, h] [Object._3D, [caption,] w, h] [Object._3D, w, h, crx, crz] [Object._3D, [caption,] w, h, crx, crz] [Object._3D, w, h, cpx, cpy, cpz, crx, crz] [Object._3D, [caption,] w, h, cpx, cpy, cpz, crx, crz]

**Note**

You can also embed \_3D without specifying any additional arguments at all.

To display a picture of a 3D scene on the HTML page, type in the following statement:

[Object._3D, w, h] [Object._3D, [caption,] w, h] [Object._3D, w, h, crx, crz] [Object._3D, [caption,] w, h, crx, crz] [Object._3D, w, h, cpx, cpy, cpz, crx, crz] [Object._3D, [caption,] w, h, cpx, cpy, cpz, crx, crz]

The setting [Object.\_3D, w, h] creates the picture with the angles crx=45° and crz=15° and as a View All view.

The individual arguments designate the following settings:

- The optional argument caption designates the caption which the HtmlReport shows below the picture.
- The named argument object designates the object whose picture you want do display.
- The named argument w designates the width of the picture in pixels.
- The named argument h designates the height of the picture in pixels.
- The named argument cpx designates the x-coordinate of the camera position.
- The named argument cpy designates the y-coordinate of the camera position.
- The named argument cpz designates the z-coordinate of the camera position.
- The named argument crx designates the rotation angle of the camera on the x-axis.
- The named argument crz designates the rotation angle of the camera on the z-axis.

You might, for example, type in:

[Station._3D, 150, 100, -29.596, -31.985, 39.985, 46.983, -36.669]

The result looks like this:

<!-- image -->

The coordinates are those that the command Marks &gt; Generate SimTalk Code and Copy to Clipboard on the View ribbon tab of the 3D window copies.

For a 3D scene you can select the command Generate HtmlReport Code and Copy to Clipboard and then paste the code into the HtmlReport .

- If Planning View is active, Plant Simulation generates the respective code.

<!-- image -->

[.Models.Model.\_3D Size=[874,491] PlanningView=true ViewPos=[21.483,-11.597] ViewZoom=23.294]

- If Planning View is not active, Plant Simulation uses the current camera position or camera rotation in the 3D scene respectively and copies it to the generated code.

<!-- image -->

[.Models.Model._3D Size=[874,491] PlanningView=false CameraPos=[15.211,-46.816,29.319] CameraRotX=48.000 CameraRotZ=-8.500]

**In a 3D Only model you can access the 3D window .**

To allow this, we support the parameters for the rotation or for the rotation and position of the camera in a Frame in a 3D Only model :

[Frame[,Caption][, {Width, Height} {Percent}][, CameraPositionX, CameraPositionY, CameraPositionZ, CameraRotationX, CameraRotationZ} {CameraRotationX, CameraRotationZ}]]

If you specify the camera rotation, you have to type in two asterisks instead of one asterisk:

[current, *, *, -45.0]

If you specify the camera position and the camera rotation, you have to type in two asterisks instead of one asterisk:

[current, *, *, -7.12, 8.123, 1.24, -45.0, 15,0]

Instead of the camera information you can also specify the keyword %planningview in a 3D Only model or for 3D scenes . Then the HtmlReport shows the 3D scene in the planning view .

[current, *, *, %planningview]

You can show the views of 3D scenes in the HtmlReport with the keyword %modelingview .

If a 3D scene is shown in Planning View , you can circumvent this state and show the modeling view instead of the planning view with the keyword %modelingview in the HtmlReport .

[current, *, *, %modelingview]

Specifying Named Arguments

The HtmlReport provides these arguments for showing a picture of a 3D scene:

- The named argument Caption specifies the caption with which the picture is shown in the HtmlReport .

[.Models.Model._3D Caption="My Caption" Size=[874,491] PlanningView=true]

**Default Value of the Argument**

The default value is the object path.

- The named argument PlanningView specifies if the picture to be shown in the HtmlReport is created in Planning View ( true ) or in Modeling View ( false ).

[.Models.Model._3D Caption="My Caption" Size=[874,491] PlanningView=true]

**Default Value of the Argument**

The default value is the setting you selected for the View Options of the Frame . Otherwise, it is false.

- The named argument Size sets the size with which the picture is shown in the HtmlReport .

Specify * (asterisk) or [*, *] to make Plant Simulation set the size automatically.

Specify [*, Height] or [Width, *] to make Plant Simulation set the size designated by * via the default aspect ratio from the other size.

Specify [Width, Height] to make Plant Simulation set the width and the height of the picture.

The default value is 700 by 500 pixels.

[.Models.Model._3D Caption="My Caption" Size=[874,491] PlanningView=true]

- The named argument ScaleTo specifies the scaling of the picture relative to the width of the HtmlReport in percent.

**Default Value of the Argument**

The default value is 100%.

[.Models.Model._3D Caption="My Caption" ScaleTo=80% PlanningView=true]

The HtmlReport provides these additional arguments for showing a picture of the planning view of a 3D scene:

- The named argument ViewPos sets that the picture is shown centered in the HtmlReport .
- The named argument ViewZoom sets the zoom factor or the view that is shown in the HtmlReport .

[.Models.Model._3D Size=[874,491] PlanningView=true ViewPos=[21.483,-11.597] ViewZoom=23.294]

The HtmlReport provides these additional arguments for showing a picture of the modeling view of a 3D scene:

- The named argument CameraPos sets the camera position with which the picture is shown it in the HtmlReport .
- The named argument CameraRotX sets the camera rotation in degrees around the x-axis with which the picture is shown in the HtmlReport .
- The named argument CameraRotZ sets the camera rotation in degrees around the z-axis with which the picture is shown in the HtmlReport .

[.Models.Model._3D Size=[874,491] PlanningView=false CameraPos=[15.211,-46.816,29.319] CameraRotX=48.000 CameraRotZ=-8.500]

See also

Generate HtmlReport Code and Copy to Clipboard

Generate SimTalk Code and Copy to Clipboard [camera mark]

**Compute a Formula**

###### Compute a Formula

To compute any formula, type in the formula between an opening bracket, followed by the equal sign [= and a closing bracket ] .

You can type in the number of decimal places, separated by a comma, as parameter. To force a certain number of decimal places, even when these are zeros, type in a space followed by zero 0 in front of the number of decimal places.

[=Station1.statWorkingPortion + Station1.statBlockingPortion] [=Station1.statWorkingPortion + Station1.statBlockingPortion, 2] [=Station1.statWorkingPortion + Station1.statBlockingPortion, 02]

The result looks like this:

<!-- image -->

If you query an attribute or compute a formula, and if the return value has the data type object , Plant Simulation displays the object path on the HTML page. If you want to display the object itself instead of the object path on the HTML page, type in the attribute or the formula between [&gt; and ] .

[>Source.path]  // displays the table of the delivery list [>@.~]  // displays the location of @m (for example the contents // of the Frame when @ is a Station inserted into the Frame) [>=str_to_obj(Variable)]

**See also**

Show Statistics and Other Values in a Report

###### Add an Image of an Object

Specify the settings for displaying the current icon of an object, or for displaying an object and an icon on the HTML page.

Selecting the Object in the Dialog Select Object

To display an object to display its current icon, or an object and an icon to be displayed on the HTML page, click on the toolbar . Select the icon you want to use in the dialog that opens and click OK .

<!-- image -->

Type in the Caption which the HtmlReport shows below the picture.

Type in the Image Size in percent to which the HtmlReport scales the picture. Instead, you can also type in the Image Width and the Image Height . You can also type in an asterisk ( * ) for either the Width or the Height to ensure that the image will not be distorted. The relative size takes precedence over the absolute size.

<!-- image -->

The settings above result in this statement:

<!-- image -->

**Add an Image of an Object**

The result looks like this:

<!-- image -->

If the text cursor is located within a picture reference ([!…]), Plant Simulation first opens the dialog Open

File and then the dialog Object Parameters for the path within brackets when you click Add Icon

<!-- image -->

If the text cursor is located within a picture reference ([!…]), Plant Simulation first opens the dialog Open File and then the dialog Object Parameters in which the path is preselected that was detected within

brackets when you hold down Shift while clicking Add Icon

Specifying the Parameters on the Tab Content

Instead, you can also directly type in an opening bracket, followed by an exclamation mark, the path to the object, and a closing bracket, for example [!MyObject] . To not show the current icon, but a certain icon of the object, type in the name or the number of the icon, separated by a comma.

[!Station1] [!Station1, Default] [!Station1, 0]

The result looks like this:

<!-- image -->

In addition, you can set the size of the icon as follows:

- Type in an asterisk * to also zoom the icon out, when you zoom the report window out. When zooming in, the icon is never enlarged to more than its original size.
- Type in a number and the percent sign % to scale the icon with this value.

<!-- image -->

.

- Type in the width and the height of the icon in millimeters to show the icon with these measurements. You can also replace one of the two values with an * .

[!Station1, "Operational","My Station 50 x 50%", 50, 50] [!Station1, "Operational", "My Station scaled to 110%", 110%]

The result looks like this:

<!-- image -->

<!-- image -->

See also

Add a Menu and Menu Commands

Show Statistics and Other Values in a Report

**Add a Bitmap File**

###### Add a Bitmap File

Specify the settings for creating an icon from a bitmap file and for displaying this icon on the HTML page.

Selecting the Object in the Dialog Select Object

To select a bitmap file to create an icon in this HtmlReport and to display this icon on the HTML page, click on the toolbar . Select the bitmap file in the dialog Open and click OK .

<!-- image -->

Type in the object parameters:

<!-- image -->

In our example we selected the bitmap file named SiemensLogo . It is 31 mm wide and 6 mm high.

[!self, "SiemensLogo", "Show Siemens Logo"]

The result looks like this:´

<!-- image -->

See also

Show Statistics and Other Values in a Report

###### Collect Object Instances and Show Them

To insert all instances of a certain object into the HtmlReport , type in the path to the object followed by an asterisk * as parameter.

```simtalk
**Collect all instances of the object 'DataTable' [.InformationFlow.DataTable*]**
```

The result looks like this:

<!-- image -->

The title in the HtmlReport can also contain a formula. In the simplest form it looks like this:

```simtalk
**Collect object instances as per
@.Label [.InformationFlow.DataTable*, "=@.Label"] [.UserInterface.Chart*, "=@.Label"]**
```

The result looks like this:

<!-- image -->

Start the formula, just like in the normal syntax of the HtmlReport , with "=" . As the formula is enclosed in double quotation marks, you have to protect the double quotation marks within the formula itself with a backslash, for example "=\"#\" , to prevent it from being evaluated in the HtmlReport itself, so that the double quotation marks only matter in the formula itself.

For the evaluation of the formulas you will use the usual anonymous identifiers where the anonymous identifier @ always points to the instance to be shown.

If you access the name with @.Name or the label with @.Label in formulas and if either the name or the label is used for the title, Plant Simulation adds the name or the label as link to the HtmlReport . When you then click the link, Plant Simulation opens the instance.

Compare this example:

```simtalk
**Collect object instances as per
@.Name [.InformationFlow.DataTable*, "=@.Name"]**
```

The result looks like this:

<!-- image -->

If the thus generated title contains a valid path to an existing object, Plant Simulation inserts the path as a link into the HtmlReport .

The following example generates an HTML table for each instantiated DataTable within the Frame in which the HtmlReport is located and a title with the absolute path to the instance of the DataTable . You can then click the underlined link to open this DataTable instance.

These instructions

**Normal caption formula evaluations without quotation marks [.InformationFlow.DataTable*, "=@.Location"] [.InformationFlow.DataTable*, "=@.Name + \" in \" + to_str(@.Location)"]**

insert this into the HtmlReport :

<!-- image -->

In general Plant Simulation underlines all titles below object depictions which contain a valid path. You can then click this link to open the respective object.

This also applies for titles which, among others, contain a valid path. Here Plant Simulation adds the path to the contained Frame for each DataTable in the title as a link.

These instructions

```simtalk
**Collect object instances with complex expressions ## Captions in quotation marks as column index/image width [.InformationFlow.DataTable*, "=1+sin(pi/2)"] [.InformationFlow.DataTable*, "=\"#\" + @.Name"] [.UserInterface.Chart*,"=1+sin(pi/2)"]**
```

insert this into the HtmlReport .

<!-- image -->

Statistics data do not support caption formulas. These instructions

**Statistics data do not support caption formulas [.MaterialFlow.Station*, "=@.Name"]**

insert this into the HtmlReport :

<!-- image -->

This source code demonstrates the functions described above for our Frame . The DataTables have to contain data.

<!-- image -->

[.InformationFlow.DataTable*, "=@.Location"] [.InformationFlow.DataTable*, "=@.Name + \" in \" + to_str(@.Location)"] # Statistics data do not support caption formulas [.MaterialFlow.Station*, "=@.Name"]

**See also**

**Display a HtmlReport**

Insert a Comment into Your Report

Type in two hyphens --to start a comment which extends to the end of the line.

The comments will be ignored when generating the HTML page, meaning they do not affect the look of the HTML page. The comment is not part of the .htm file when you save the HtmlReport .

This text will be displayed. -- This text will not be displayed.

The result looks like this:

See also

Show Statistics and Other Values in a Report

###### Insert a Horizontal Line

Type in three hyphens ---, which are not followed by text, to create a solid horizontal line.

You can also type more than three hyphens. If you type in other characters than the hyphens into the line of characters, Plant Simulation interprets ---as the start of a comment.

```simtalk
Text above the line. ------Text below the line. --- This is a comment ---
```

The result looks like this:

See also

Show Statistics and Other Values in a Report

**Insert HTML Tags**

###### Insert HTML Tags

Type the HTML tags within angle brackets, according to HTML syntax.

Plant Simulation only recognizes the HTML tag if no space follows directly after the opening angle bracket ( &lt; ), and only if the closing angle bracket ( &gt; ) is located in the same line. If this is not the case, Plant Simulation displays a normal opening angle bracket.

Plant Simulation does not analyze the markup language within the HTML tags. This way * , 1. , --, etc. do not have any special meaning within the angle brackets.

```simtalk
<span style="color:blue">My blue text</span> <a href="http://www.siemens.com">Visit us on the Siemens Homepage</a> <!-- This is an HTML comment which is exported to the .htm file. -->
```

The result looks like this:

<!-- image -->

&lt;a href="mailto:Max.Mustermann@siemens.com?subject=Simulation report"&gt;Max.Mustermann@siemens.com&lt;/a&gt; -- Opens the E-Mail program, enters the name and the E-Mail address into

the field To and Simulation report into the field Subject.

<!-- image -->

The result looks like this:

<!-- image -->

**See also**

Show Statistics and Other Values in a Report

**Protect Characters**

###### Protect Characters

When you type a character, which has a special meaning in the markup language, Plant Simulation does not display this character on the HTML page, but treats it as part of the notation of the markup language.

To show such a character on the HTML page, type in a backslash \ to the left of the character.

```simtalk
\-- This is not a comment. 1\. This is not a numbered list. \[%\] This is a percentage sign within brackets.
```

The result looks like this:

You can protect the following special characters with a backslash \ , but you do not have to protect them in each and every case:

| Special character   | Stands for      | Type in to protect   |
|---------------------|-----------------|----------------------|
| \                   | backslash       | \\                   |
| *                   | asterisk        | \*                   |
| #                   | number sign     | \#                   |
| [                   | opening bracket | \[                   |
| ]                   | closing bracket | \]                   |
| -                   | hyphen          | \-                   |
| .                   | period          | \.                   |
| <                   | less-than       | \<                   |
| >                   | greater-than    | \>                   |

See also

Show Statistics and Other Values in a Report

###### Use a String Unchanged in the HTML Code

To integrate a string into the HTML code without changing it, enclose it between two opening angle brackets &lt;&lt; and two closing angle brackets &gt;&gt; .

The string can have any length and can contain any number of line breaks.

This may be required for two reasons:

- To prevent that a long string of text is being interpreted as markup language.

To prevent that a long string of text from being interpreted as markup language, you can type in a backslash \ . This might prove to be cumbersome though. Imagine that you want to display the string ------on the HTML page. To prevent two consecutive hyphens from being interpreted as comment, you would have to protect each second hyphen with a backslash: -\--\--\-. Instead, you can also enclose the string within two angle brackets: &lt;&lt;------&gt;&gt; .

<!-- image -->

- To generate characters which have a special meaning in HTML.

When you type in a character that has a special meaning in HTML, Plant Simulation automatically converts this character into an HTML entity. An example for a special meaning in HTML are the quotation marks ( " ). For this reason Plant Simulation generates the HTML entity &amp;quot; for quotation marks within the HTML code.

<!-- image -->

If you want to generate a quotation mark within the HTML code (this way you can easily generate invalid HTML), you cannot accomplish this by protecting the quotation mark with a backslash. Plant Simulation will convert this quotation mark into an HTML entity to avoid generating invalid HTML code. To prevent this, you can enclose the quotation mark in two opening and two closing angle brackets &lt;&lt;'&gt;&gt; .

<!-- image -->

Suppose that you want to display the per mille sign ‰ but that you cannot enter it by typing on the keyboard. If you know that the per mille sign has the Unicode code 8240, you can formulate the sign as the HTML entity &amp;#8240; . As the sign &amp; has a special meaning in HTML (namely to open the HTML entities), Plant Simulation generates the HTML code &amp;amp;#8240; , so that the Browser displays the string &amp;#8240; .

If you want to display the per mille sign in the Browser, you have to enclose the string in two angle brackets so that Plant Simulation integrates it into the HTML code: &lt;&lt;&amp;#8240;&gt;&gt; without changing it.

<!-- image -->

See also

Show Statistics and Other Values in a Report

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk updateDialog [SimTalk]

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the HtmlReport

\_Methods of the HtmlReport

The HtmlReport provides:

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

##### append [SimTalk] - HtmlReport

append [SimTalk] - HtmlReport

Appends text to the Content of the HtmlReport designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.append(Text:string)
```

Parameter

The parameter Text of data type string designates the text that you want to append.

Example

```simtalk
MyReport.Content := "#Heading"
for var i := 1 to numNodes
	MyReport.append(strChr(10))
	MyReport.append("Name: ")
	MyReport.append(object(i).name)
next
```

See also

Tab Content [HtmlReport]

appendLine [SimTalk]

Appends a line of text to the Content of the HtmlReport designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.appendLine(Text:string)
```

Parameter

The parameter Text of data type string designates the text of the line that you want to append.

Example

```simtalk
MyReport.Content := "#Heading" + strChr(10)
for var i := 1 to numNodes
	MyReport.appendLine(object(i).name)
next
```

See also

Tab Content [HtmlReport]

##### appendPlainText [SimTalk]

appendPlainText [SimTalk]

Appends a special character as plain text to the content of the HtmlReport designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.appendPlainText(PlainText:string)
```

Parameter

The parameter PlainText of data type string designates the special character that you want to append as plain text.

Example

```simtalk
MyReport.Content := "#Heading" + strChr(10)
```

MyReport.appendPlainText("##**")

See also

Tab Content [HtmlReport]

close [SimTalk] - HtmlReport

Closes the window that you opened by clicking Show Report of the HtmlReport designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.close → boolean

Return Value

The return value has the data type boolean .

Example

MyReport.close

See also

show [SimTalk]

##### getHTMLCode [SimTalk] - HtmlReport

getHTMLCode [SimTalk] - HtmlReport

Returns the HTML code of the HtmlReport designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getHTMLCode([WithButtonsAndLinks:boolean:=false]) → string

**Parameter**

The optional parameter WithButtonsAndLinks of data type boolean sets if the returned string contains HTML-code for the buttons in the top left corner of the display window and links for the objects, for example in statistics tables of the material flow objects.

<!-- image -->

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type string .

**Example**

print MyHtmlReport.getHTMLCode

See also

Display a HtmlReport save [SimTalk] - HtmlReport Saves the HtmlReport designated by &lt;Path&gt; as an HTML file.

<!-- image -->

Remarks

You can also specify the location of the file on your hard drive.

Type

Method

Syntax

&lt; Path &gt;.save(FileName:string)

Parameter

The parameter FileName of data type string designates the path to and the name of the HTML file you want to save.

Example

MyReport.save("C:\temp\MyReport.html")

show [SimTalk] Shows the HtmlReport designated by <Path> as an HTML page. Type Method Syntax show [SimTalk]

```simtalk
< Path >.show([Anchor:string])
```

Parameter

The optional parameter Anchor of data type string designates the anchor to which Plant Simulation navigates when it opens the HTML page.

**Example**

MyHtmlReport.show("DrainStat") // jumps to the anchor defined by: // << <a id="DrainStat"> </a> >> // on the tab Content

**SimTalk**

close [SimTalk] - HtmlReport

See also Show Report

#### Read-Only Attributes of the HtmlReport

Read-Only Attributes of the HtmlReport

The HtmlReport provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyHtmlReport.UUID

#### Attributes of the HtmlReport

\_Attributes of the HtmlReport

The HtmlReport provides:

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
MyReport.TocLevels := 3
print MyReport.TocLevel
```

##### Content [SimTalk] - HtmlReport

Sets the Content which the HtmlReport designated by &lt;Path&gt; displays.

Type

Attribute

Syntax

```simtalk
< Path >.Content:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
HtmlReport.Content := "[!self, Header, *]\ # General Information\ [Receiving, \"Statistics of the Source named 'Receiving' and the station named 'MyStation'\"]\ [MyStation]\ Created on [=day(sysdate)].[=month(sysdate)].[=year(sysdate)+1900]"
```

See also

Tab Content [HtmlReport]

IsShown [SimTalk] - HtmlReport

Sets if the HtmlReport designated by &lt;Path&gt; is displayed in the Frame window into which it is inserted ( true ) or not ( false ).

Type

Method

Syntax

&lt; Path &gt;.IsShown:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyReport.IsShown := true
```

See also

Show Report

##### TocLevels [SimTalk]

Sets the number of levels of the table of contents which the HtmlReport designated by &lt;Path&gt; shows.

Type

Attribute

Syntax

&lt; Path &gt;.TocLevels:integer

Assignment Value

You can assign a value of data type integer .

Specify a value between 1 and 4 .

If you specify a value greater than 4 , Plant Simulation treats this value as 4.

**Example**

```simtalk
MyReport.TocLevels := 4
```

See also

Study the HtmlReport WindowHeight [SimTalk]

Sets the height in pixels with which Plant Simulation opens the display window of the HtmlReport designated by &lt;Path&gt;.

Syntax

&lt; Path &gt;.WindowHeight:integer

Assignment Value

You can assign a value of data type integer .

Example

MyHtmlReport.WindowHeight := 600 // pixels

SimTalk

WindowHeight [SimTalk]

WindowWidth [SimTalk]

See also

Show Report

##### WindowWidth [SimTalk]

Sets the width in pixels with which Plant Simulation opens the display window of the HtmlReport designated by &lt;Path&gt;.

Syntax

&lt; Path &gt;.WindowWidth:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyHtmlReport.WindowWidth :=  800 // pixels
```

SimTalk

WindowWidth [SimTalk]

WindowHeight [SimTalk]

See also

Show Report

