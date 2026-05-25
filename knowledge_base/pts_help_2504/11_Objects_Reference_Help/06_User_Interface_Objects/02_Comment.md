### Comment

- Use the Checkbox for toggling between the states on and off, for toggling operating modes, etc.
- Use the Comment for showing explanatory notes which you added to your simulation model.
- Use the CostAnalyzer for analyzing costs that the individual machines and the Worker cause.
- Use the Dialog for designing a dialog box for an object which is similar to the built-in dialog boxes.
- Use the Display for presenting current data and results of the simulation run.
- Use the DropDownList for showing a drop-down list in the Frame . When you select one of the items, it executes the action which you programmed in the control.
- Use the GanttChart for showing the chronological sequence of activities as bars on the time axis.
- Use the HtmlReport for presenting current data and results of the simulation run in a report that you can share with co-workers and customers.
- Use the SankeyDiagram for visualizing the Sankey flows of parts as well as Sankey flows of Workers , who walk freely within the area or walk on FootPaths .

**Comment**

#### Comment [object]

Use the Comment for showing explanatory notes which you added to your simulation model.

Icon

<!-- image -->

**Description**

A comment helps you and your colleagues to better understand the intentions behind your model and how it is supposed to work.

You can access it like you do any other object, be aware though that the Comment usually is not involved in the simulation itself. Select Options &gt; Show Comments on the View ribbon tab of the Frame or click

<!-- image -->

to display all Comment objects, which you inserted into that Frame . Plant Simulation displays the text in the Frame window which you entered under Display &gt; Text .

To open a window that only shows the comment you entered, without formatting and editing options, click the Comment object with the right mouse button and select Open Comment Window on the context menu.

<!-- image -->

<!-- image -->

<!-- image -->

To show a tooltip with information about the Comment , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Comment , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

<!-- image -->

To add the Comment to your simulation model, click UserInterface &gt; Comment on the Home ribbon tab.

See also

Add Text and Display Boards

#### Dialog Box of the Comment

Dialog Box of the Comment

Double-click the icon of the Comment , which you inserted into a Frame , to open its dialog box.

Edit Simulation Properties

To make the dialog box larger or smaller, grab any of its sides or corners, and drag the mouse.

To open a window that only shows the comment you entered, without formatting and editing options, click the Comment object with the right mouse button and select Open Comment Window on the context menu.

Manage Class Library &gt; Basic Objects &gt;

Plant Simulation opens the comment window with the size that the tab Comment in the dialog box had, when you entered the comment and with the formatting you applied.

<!-- image -->

To close the comment window, click Close in the title bar.

<!-- image -->

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### Name [text box] - Comment

<!-- image -->

Shows the name of the object here, either the predefined name or a name that you specify. To change the name, double-click and type over it.

You can type in a combination of letters, digits, and underscore (\_) characters, for example MyComment , MyComment1 , My\_Comment\_1 . The name of an object cannot start with a digit, i.e., you cannot type in 1Comment .

SimTalk

Name [SimTalk] - general description

Tab Comment

Tab Comment [Comment]

Type a detailed description appending the short note you entered into the Text box on the Tab Display .

<!-- image -->

<!-- image -->

- Apply formatting properties to the selected text with the buttons of the Formatting Toolbar or the commands of the Context Menu for Formatting the Comment . Note The buttons are only active if you select the check box Save the Content in Rich-text Format .
- For each character format property you can:
- Apply a typeface, a Font size, and a font color.
- Apply Bold face, Underline , or italicize text.

- For each paragraph format property you may:
- ◊ Set the alignment: Align Left , Center , or Align Right .
- ◊ Set an indentation with Bullets .
- Or copy text you formatted in a word processing application that works with rich text format (.rtf), such as the MS Windows WordPad or MS Word, to the clipboard and paste that text, including all of its formatting properties into the text box.
- Or type text into the text box, copy it back to the word processing application, apply formatting and paste it back to the text box. Press Ctrl+A to select all of the text into the text box, Ctrl+C to copy the text, and Ctrl+V to paste it.

To open a window that only shows the comment you typed in, without formatting and editing options, click the Comment object with the right mouse button and select Open Comment Window on the context menu.

<!-- image -->

**Formatting Toolbar**

###### Formatting Toolbar

You can apply formatting properties to the selected text with the buttons on the toolbar.

<!-- image -->

**Note**

You can also select most of the formatting options on the Context Menu for Formatting the Comment .

###### Inherit Contents [Comment]

To inherit or not inherit the contents of the Comment , click the inheritance check box next to the text box.

<!-- image -->

**Save the Content in Rich-text Format**

###### Save the Content in Rich-text Format

To save the contents of the text box in rich-text format, which preserves all of the formatting properties which you applied, select this check box.

<!-- image -->

###### Context Menu for Formatting the Comment

Context Menu for Formatting the Comment

The context menu provides the menu commands listed in the table of contents to the left.

<!-- image -->

.

<!-- image -->

**Font [Comment]**

**Font [Comment]**

Opens the dialog Font .

<!-- image -->

- Select the Font , the Font Style , the font Size , and font Effects .
- Click OK to apply these settings to the text, which you selected in the text box.

<!-- image -->

**Color [Comment]**

Opens the dialog Color .

- Select a Color .
- Click Apply to apply these settings to the selected text into the text box and leave the dialog open.
- Click OK to apply this color to the selected text into the text box and close the dialog.

<!-- image -->

Instead, you can also click

See also

Color [SimTalk] - Comment on the Formatting Toolbar

.

**Bold [Comment]**

**Bold [Comment]**

Applies bold face to the text which you selected in the text box.

<!-- image -->

.

**Italic [Comment]**

Italicizes the text which you selected in the text box.

<!-- image -->

**Underline**

**Underline**

Underlines the text which you selected in the text box.

<!-- image -->

.

<!-- image -->

**Center [Comment]**

**Center [Comment]**

Centers the text.

<!-- image -->

.

.

<!-- image -->

**Bullets**

**Bullets**

Adds a bullet in front of the text which you selected in the text box.

Press Enter to insert a line break in front of a sentence where you want to add a bullet.

Instead, you can also click on the Formatting Toolbar .

**Insert Date or Time**

Opens the dialog Insert Date and Time .

- Select one of the available formats from the list box.
- Click OK to enter this time or date at the position of the cursor into the text box.

<!-- image -->

**Tab Display**

##### Tab Display

On the tab Display you can select how to display the Comment in your simulation model.

The tab Display provides the settings listed in the table of contents to the left.

.

**Text [text box] - Comment**

###### Text [text box] - Comment

Type in the text that Plant Simulation shows when you insert the Comment object into a Frame .

Type in a short text, or you will not be able to see or select the Comment in the Frame .

<!-- image -->

If you only entered Text here and nothing on the tab Comment , Plant Simulation shows the tab Display when you open the dialog of the Comment the next time.

**Inherit text**

To inherit or not inherit the Text of the Comment , which you type into the box to the left, click the inheritance check box.

**SimTalk**

Text [SimTalk] - Comment

###### Font Size [drop-down list] - Comment

Select a font size for displaying the Comment in the Frame into which you inserted it.

<!-- image -->

**Font Color [Comment]**

###### Font Color [Comment]

To select the color of the text proper with which Plant Simulation shows the Comment in the Frame , click the drop-down arrow.

<!-- image -->

Plant Simulation only shows the color in the Frame into which you inserted the Comment , not in the open dialog box.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

Color [SimTalk] - Comment

###### Background Color [drop-down list] - Comment

To select the color of the background of the Comment which you inserted into a Frame , click the dropdown arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

**SimTalk**

BackgroundColor [SimTalk] - Comment

###### Transparent [check box] - Comment

Transparent [check box] - Comment

To make the background of a Comment object, which you inserted into a Frame , shine through the hollow parts of the text, select this check box.

<!-- image -->

Then, Plant Simulation shows the Comment in the color which you selected as the Font Color on the background of the Frame .

To show the text on a white background, clear the check box.

The setting Transparent also applies in 3D.

<!-- image -->

| Not transparent   | Transparent   |
|-------------------|---------------|

**SimTalk**

Transparent [SimTalk] - Comment

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk updateDialog [SimTalk]

Tools Menu

The Tools Menu provides commands to access its functions.

**Edit Observers**

3D

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Comment**

#### \_Methods of the Comment

The Comment provides:

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

##### appendToContent [SimTalk]

Appends the passed text to the existing text on the tab Comment which the Comment designated by &lt;Path&gt; shows.

Type

Method

Remarks

Plant Simulation requests memory in larger blocks from the operating system so that memory does not have to be increased with each call. This makes putting a message together from many text blocks faster.

Syntax

&lt; Path &gt;.appendToContent(Text:string)

Parameter

The parameter Text of data type string designates the text which you want to add.

Example

MyComment.appendToContent("my added text")

See also

Tab Comment [Comment]

##### openComment [SimTalk]

Opens a window that only shows the comment you entered into the Comment designated by &lt;Path&gt; without any formatting options.

<!-- image -->

Type

Method

Syntax

```simtalk
< Path >.openComment → boolean
```

Return Value

The return value has the data type boolean .

Example

MyComment.openComment

See also

Tab Comment [Comment]

#### Read-Only Attributes of the Comment

Read-Only Attributes of the Comment

The Comment provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyComment.UUID

#### Attributes of the Comment

##### \_Attributes of the Comment

The Comment provides:

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
MyComment.Color := makeRGBColor(255,0,0)
print MyComment.font
posit := Station.Cont.XPos
```

BackgroundColor [SimTalk] - Comment

Sets the Background Color of the Comment designated by &lt;Path&gt; which you inserted into a Frame .

Remarks

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

```simtalk
< Path >.BackgroundColor:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyComment.BackgroundColor := makeRGBValue(100,100,100)
MyComment.BackgroundColor := 6579300 // is the same as the color above
```

SimTalk

makeRGBValue [SimTalk]

See also

Background Color [drop-down list] - Comment

##### Color [SimTalk] - Comment

Sets the Color with which Plant Simulation displays the text of the Comment designated by &lt;Path&gt; in the Frame .

Remarks

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

&lt; Path &gt;.Color:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyComment.Color := makeRGBValue(255,0,0)
```

SimTalk

makeRGBValue [SimTalk]

See also

Font Color [Comment]

Cont [SimTalk] - Comment

Cont [SimTalk] - Comment

Sets the Contents of the text box on the tab Comment of the Comment designated by &lt;Path&gt;.

Remarks

Enter a backslash \ to insert a line break.

Type

Attribute

Syntax

```simtalk
< Path >.Cont:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyComment.Cont := "Species: Aardvark\ amount: 45 \ weight: 780kg" // assign a multi-line comment
```

SimTalk

mu [SimTalk] - material flow objects

See also

Tab Comment [Comment]

##### Font [SimTalk] - Comment

Sets the Font Size with which Plant Simulation displays the Comment designated by &lt;Path&gt; in the Frame .

Type

Attribute

Syntax

```simtalk
< Path >.Font:integer
```

Assignment Value

You can assign a value of data type integer .

You can specify 1 for Small , 2 for Medium , 3 for Large , 4 for Extra Large .

Example

```simtalk
if MyComment.Font < 4
	MyComment.Font := MyComment.Font + 1
```

See also

Font Size [drop-down list] - Comment

**SaveAsRichedit [SimTalk]**

##### SaveAsRichedit [SimTalk]

Makes the Comment designated by &lt;Path&gt; save the contents of the text box in rich-text format ( true ) or not ( false ).

Remarks

Rich-text preserves all the formatting properties you applied.

Type

Attribute

Syntax

&lt; Path &gt;.SaveAsRichedit:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyComment.SaveAsRichedit := false

See also

Save the Content in Rich-text Format Text [SimTalk] - Comment Sets the comment text that the Comment designated by &lt;Path&gt; shows in the Frame .

Remarks

The text may also contain blanks and/or special characters.

Type

Attribute

Syntax

```simtalk
< Path >.Text:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyComment.Text := "Buffer utilization in %"
```

See also

Text [text box] - Comment

##### Transparent [SimTalk] - Comment

Makes the background of the object designated by &lt;Path&gt; transparent in the Frame ( true ) or not transparent ( false ).

Remarks

The setting Transparent also applies in 3D.

Type

Attribute

Syntax

&lt; Path &gt;.Transparent:boolean

Assignment Value

You can assign a value of data type boolean .

Specify true to show the Comment in the color that you selected as the Font Color on the background of the Frame .

Specify false to show the space around the text in white.

Example

```simtalk
MyComment.Transparent := false
```

See also

Transparent [check box] - Comment

Font Color [Comment]

