### Method

#### Method [object]

Use the Method for programming controls, which other objects start, and which Plant Simulation then executes during the simulation run.

**Icon**

<!-- image -->

<!-- image -->

**Description**

In this topic we will only describe the object Method as such, reserving the description of the programming language SimTalk for the SimTalk Reference .

You can build your own routines using a combination of built-in methods, Keywords , assignments, and control structures in the Method . Also check if one of the built-in Templates meets your needs. If this is not the case, you can write your own templates for your use and for sharing them with your colleagues.

This construct combines productivity and flexibility. You can modify the behavior of an object, so that it exactly fits your modeling needs, by writing user-defined methods. The built-in properties of the objects, the large number of built-in methods provided, and the inheritance strategies help build valid models in a short amount of time.

You can access the functions of the Method on the Edit Ribbon Tab and on the Tools Ribbon Tab of the Method .

You can select preferences for the Method Editor under File &gt; Preferences &gt; Editor .

**Note**

You can specify the settings that Plant Simulation applies when calling Methods during the simulation runs under File &gt; Model Settings/Preferences &gt; Simulation &gt; Methods .

The Method and user-defined attributes of data type Method have their own random number stream which you can set with the attribute RandomSeed . As you are used to from the material flow objects, Plant Simulation automatically assigns the random number stream when you insert an object, so that each object has its own random number stream.

You can show the return value of a Method in an HtmlReport , compare Display a Method .

To show a tooltip with information about the Method , hover with the mouse over it.

<!-- image -->

Use the Profiler to record the run-times and the call frequency of the Methods which are executed in your simulation model. This way you can detect which Methods consume the most time and find out how changes in modeling affect the performance of your model.

To change the length of the graphic and the anchor points of the Method , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Method to your simulation model, click Manage Class Library &gt; Basic Objects &gt; InformationFlow &gt; Method on the Home ribbon tab.

See also

Programming a Method

Working in the Method Window

Calling a Method

Colors for Syntax Highlighting

Working with Breakpoints

Icons of the Method

LEDs and States of the Method

The Method Editor

Method Debugger

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=scd-CDCJJVcBEPPP&amp;t=40](https://youtu.be/MXDcx2yplxc?si=scd-CDCJJVcBEPPP&t=40)

<!-- image -->

<!-- image -->

#### Programming a Method

The Method is the container for program routines which you write. To open it and type in the source code to be executed, double-click its icon in the Frame into which you inserted it. Then, type in your source code.

You can access the functions of the Method on the Edit Ribbon Tab and on the Tools Ribbon Tab .

The figure below shows the following exemplified:

- In the Frame the Tooltip of the Method below the mouse pointer.
- In the Method window the class breakpoint as a filled red circle .
- In the Method window a bookmark as a filled rectangle .
- In the Method window the instance breakpoint which we set to not active, as a white star within a red circle .
- In the Method window the instance breakpoint as a red star

<!-- image -->

.

<!-- image -->

The structure of a Method is divided into several parts. If you do not need a certain part, you can delete or omit it.

A Method which we might, for example, use as an Exit Control , could look like this:

```simtalk
// My Tooltip. My text, my text, my text, ...
param Sender:object
if Sender /= void
	@.move(Sender)
	return
```

**Programming a Method**

```simtalk
end
var MUName:string := @.Name
if MUName = "A"
	@.move(1) // parts named 'A' will be moved to the first successor
else
	@.move(2) // parts named 'B' will be moved to the second successor end
```

Plant Simulation highlights the different parts of the syntax of the SimTalk source code in different colors .

<!-- image -->

**Parameters**

The structure begins with the declaration of parameters with the keyword param . If you do not need any parameters, you do not have to declare any.

**See also**

Parameters [SimTalk]

Declare Parameters

Declare Default Arguments

Return Value

Type in the data type of the return value next if the Method is going to return a result (see Declare the Function Result of a Method ).

**Local Variables**

Declare a local variable by typing in its name and its data type. If you do not need any local variables, you do not have to declare any.

**See also**

Local Variables

Declare Local Variables in the Source Code

Data Types in Local Variables

Source Code

Type in the source code which the Method executes. You can type in built-in methods, assignments, control structures, method calls, branches, and loops. To comment your source code type in two forward slashes // or two hyphens --followed by the comment proper.

The Method Editor shows commented source code in a different color than the source code proper.

**Note**

SimTalk normally does not distinguish between upper- and lower-casing for the names of methods , attributes , and read-only attributes which you type into the source code of your Method objects.

**Note**

Click Edit &gt; Reformat to check if you typed the source code for branching and looping correctly.

See also

SimTalk 2.0 and SimTalk 1.0 Compared

A Quick Tour Through SimTalk 2.0

General Access to SimTalk

Parameters [SimTalk]

Colors for Syntax Highlighting

Suspending Methods

#### Working in the Method Window

Double-click the icon of the Method , which you inserted into a Frame , to open its window. Then type in your source code, run, and debug it.

To change the properties of the Class of the object, double-click it in the Class Library or on the tab Information Flow in the Toolbox . The method window provides access to the Method Editor and to the Method Debugger .

<!-- image -->

- Click Debug on the Tools ribbon tab or press F11 to switch from the Method Editor to the Method Debugger .
- Click any of the Step buttons on the debugger toolbar

<!-- image -->

<!-- image -->

repeatedly or once to return to the Method Editor .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- To select a single word, double-click it. To select an entire line of source code, triple-click anywhere in the line.
- To select all text in the method window, press Ctrl+A or click the mouse button four times.
- To copy the selected text, press Ctrl+C , to paste text from the clipboard, press Ctrl+V .

If you copy source code in the Method Editor , Plant Simulation pastes the copied source code in a suitable program, for example MS Word, with its color highlighting of the SimTalk syntax.

Plant Simulation places the text, in addition to simple text, as RTF Text, on the clipboard. Suitable programs paste the formatted RTF text or provide options for the format to be pasted.

Compare this example: We copy the source code of the method MyMethod . Then we paste it with the paste option Keep Source Formatting into our Word file. When we then copy the source code in Word, Plant Simulation pastes it with the saved formatting into a new Method .

<!-- image -->

<!-- image -->

<!-- image -->

If your source code contains Class Breakpoints , Plant Simulation copies these as well when you copy the source code.

Plant Simulation also applies Class Breakpoints from the class of a Method when you insert an instance of that Method into your simulation model.

If you export the source code of the Method with the command Export to File , you can select the format of the text file to be exported. To save color highlighting of keywords and comments in the source code, select HTML Files or RichText Files .

- To move the selected text, drag the mouse to a different location, and drop it.
- To undo the last changes you made to the source code, click
- To restore ( redo ) the source code to the text it had before an undo action, click
- To insert a line break , type in a backslash \ if the source code is too long to fit on one line. This makes it easier to read the source code in the method window while Plant Simulation still interprets the source code as a single entity.
- To type in a comment explaining the intention of your source code, type in two forward slashes // or two hyphens --at the beginning of the line and then type in the comment. The Method displays comments in green.

<!-- image -->

<!-- image -->

```simtalk
priority:= "Urgent"
very_long_text := "Frank Jones\ Halford Lane 9\ Cedar Rapids, IA 52409"
Text := "It is \"very\" urgent." // outputs It is "very" urgent.
```

Comments improve the legibility of a Method and help to understand the intentions behind your source code. A comment is especially helpful in a long Method , when you or a colleague look at it again at a later point in time to extend its functionality or to debug it. We encourage you to make extensive use of comments. Comments do not affect the simulation speed at all!

You can insert a comment anywhere, except within a string value of your source code. This means that you cannot type in a comment within the quotation marks "My string" that designate a string.

- To start a one-lined comment, type in two forward slashes // and type in your remarks. This comment ends at the end of the line.
- To start a comment that spans several lines, type in a forward slash and an asterisk /* , and type in your remarks. To end the comment, type in an asterisk and a forward slash */ .
- To work with breakpoints in the Method window , use the following key combinations or the respective context menu commands. The Tools ribbon tab of the Method then activates or deactivates the respective buttons.
- To insert or to delete Class Breakpoints , click in the area of the row markers and breakpoints with the middle mouse button or the mouse wheel.

```simtalk
// comment to the end of the line
price := price * 1.16 // value added tax /* start of the comment block covering several lines end of the comment block */
```

- To insert or to delete Instance Breakpoints , hold down Shift and click in the area of the row markers and breakpoints with the middle mouse button or the mouse wheel.
- To activate the breakpoint contained in a line of source code, hold down Ctrl and click the middle mouse button or the mouse wheel. Instead, you can also press Ctrl+F9 .
- To open the dialog Breakpoint Settings , press Ctrl+B .
- To show a tooltip for a breakpoint, drag the mouse pointer over it and hover.

<!-- image -->

The tooltip always shows if the respective breakpoint is inactive.

<!-- image -->

If you configured a Start Time and a Condition , the tooltip shows these as well.

The Method window shows breakpoints like this:

<!-- image -->

- To scroll horizontally in the Method Editor , hold down Shift and roll the mouse wheel.
- To run the source code of the Method , click Run Method or press F5 or click Debug Method

<!-- image -->

<!-- image -->

or press F11 .

- To increase or decrease the font size in the window of the Method Editor or the Method Debugger , hold down Ctrl and roll the mouse wheel forward and backward.

To decrease the font size, hold down Ctrl and roll the mouse wheel backward. If you change the font size with the mouse wheel, Plant Simulation uses the changed font size until you change it the next time or until the end of the Plant Simulation session for all Methods which you open afterward. Plant Simulation uses the changed font size in all open Method windows, not just in the one in which you rolled the mouse wheel.

Instead of rolling the mouse wheel, you can also use these key combinations:

Ctrl plus + (plus sign) increases the font size

Ctrl plus 0 resets the font size to the standard size of 10 points

Ctrl plus -(minus sign) decreases the font size

- Select if you want to Show Line Numbers , if you want to highlight keywords and what kind of indentation you want to use on the Edit Ribbon Tab and on the Tools Ribbon Tab in the active instance of the Method .
- Select how Plant Simulation shows SimTalk code in all Method objects under File &gt; Preferences &gt; &gt; Editor in the Plant Simulation window.

An asterisk ( * ) in the title bar of the Method window shows that the Method contains changes that have

<!-- image -->

not been applied yet. To do so, click Apply changes on the Edit Ribbon Tab .

The Context Menu of the Method Debugger and the Tools Ribbon Tab also provide a number of pertaining commands.

#### Calling a Method

You can call a Method you wrote in a number of ways. Either directly, by clicking Run or by calling it Method from another Method .

<!-- image -->

- By clicking Run on the Tools ribbon tab in the Method window. You have to click Apply Changes first if you made changes to the source code. Pressing F5 and then F7 does the same.

<!-- image -->

If the Method expects parameters to be passed, Plant Simulation opens the Debugger where you type in the parameters. You mainly use this way of calling a Method while developing your simulation model.

- By a call from a control from within another object. An Entrance Control in a Track object may, for example, trigger a Method when a MU enters.
- By a call from another Method . This only works if the name of the Method is known. If the Method is located in a different namespace, you also have to type in the Path to that Method .
- By a call from the EventController . The call &amp;method.executeIn(time) will start the designated Method after the time in seconds designated by the parameter of data type time has elapsed.
- By calling a reference . If a variable of data type object contains a reference to a Method , you type in &amp;Variable.execute .

**Example**

```simtalk
Method1                  // same namespace
root.Frame2.Method1      // path and name &Method1.executeIn(8.5)  // pass to EventController, execute Method1 after 8.5 seconds Variable.execute         // call the referenced Method, note that the // object Variable has the data type object
```

**Video on YouTube**

[https://youtu.be/5t-wLNmKpbU?si=wmQWlCx1uV34HBDY&amp;t=284](https://youtu.be/5t-wLNmKpbU?si=wmQWlCx1uV34HBDY&t=284)

#### Colors for Syntax Highlighting

Plant Simulation highlights elements in the source code in different colors according to their meaning.

<!-- image -->

<!-- image -->

| Color in source code   | Description                                                                                                                                                                     | Example   |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| Black                  | Designates normal source code.                                                                                                                                                  |           |
| Medium green           | Designates a comment you added to the source code.                                                                                                                              |           |
| Medium blue            | Designates a SimTalk function.                                                                                                                                                  |           |
| Purple                 | Designates a keyword in SimTalk .                                                                                                                                               |           |
| Brown                  | Designates a value of data type string .                                                                                                                                        |           |
| Medium red             | Designates an outdated function that is no longer supported. Compare Outdated SimTalk Names .                                                                                   |           |
| Gray blue              | Designates a deprecated function which is outdated and should not be used. It is currently supported for backward compatibility, but it might become unsupported in the future. |           |

| Color in source code   | Description                                                                       | Example   |
|------------------------|-----------------------------------------------------------------------------------|-----------|
|                        | Compare Outdated SimTalk Names .                                                  |           |
| Red                    | Designates a template argument which you have to replace in the Method template . |           |

See also

Programming a Method

A Quick Tour Through SimTalk 2.0

#### Working with Breakpoints

To work with breakpoints in the Method window , click the buttons on the Tools ribbon tab of the Method or select the respective context menu commands.

- To insert or to delete a Class Breakpoint , click in the area of the row markers and breakpoints with the middle mouse button or the mouse wheel.

To delete all class breakpoints, click Delete All Class Breakpoints .

- To insert or to delete an Instance Breakpoint , hold down Shift and click in the area of the row markers and breakpoints with the middle mouse button or the mouse wheel.
- To delete all instance breakpoints, click Delete All Instance Breakpoints .
- To activate the breakpoint contained in a line of source code, hold down Ctrl and click the middle mouse button or the mouse wheel. Instead, you can also press Ctrl+F9 .
- To open the dialog Breakpoint Settings , press Ctrl+B .
- To show a tooltip for a breakpoint, drag the mouse pointer over it and hover.

<!-- image -->

The tooltip always shows if the respective breakpoint is inactive.

<!-- image -->

If you configured a Start Time and a Condition , the tooltip shows these as well.

**See also**

**Tools Ribbon Tab**

#### Icons of the Method

The Method has a number of icons. Plant Simulation shows the Method in the Class Library with the icon named Default .

If you find that the icons we defined do not meet your needs, you can also draw any number of additional icons and assign a name to each one of them. Plant Simulation automatically selects the corresponding icon when it calls the methods init , reset , and endSim .

To show and to edit the icons of the Method , right-click the icon and select Edit Icons or click Edit Icons on the Home Ribbon tab. Click the Previous Icon or the Next Icon button on the Edit ribbon tab of the Icon Editor to cycle through the predefined icons.

<!-- image -->

| Icon   | Name             | Description                                      |
|--------|------------------|--------------------------------------------------|
|        | Default/Standard | Designates the icon shown in the Class Library . |
|        | ExitCtrl         | Designates an Exit Control .                     |
|        | EntranceCtrl     | Designates an Entrance Control .                 |
|        | User             | Designates a user-defined control.               |
|        | Interface        | Designates an Interface control.                 |
|        | Dialog           | Designates a Dialog control.                     |
|        | Init             | Designates an init control.                      |
|        | Reset            | Designates a reset control.                      |
|        | EndSim           | Designates an endSim control.                    |

To show all existing icons of the Method , click Overview on the Edit ribbon tab of the Icon Editor , or press F12 .

**See also**

**LEDs and States of the Method**

<!-- image -->

#### LEDs and States of the Method

During the simulation runs Plant Simulation shows the state of the Methods with colored dots in the LED display area along the upper border of their icons in the Frame .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Description                                                  | LED shows a    | Looks like this   |
|--------------------------------------------------------------|----------------|-------------------|
| The source code contains syntax errors                       | red dot        |                   |
| The source code is being executed                            | green dot      |                   |
| Has been suspended by a stopuntil or a waituntil instruction | purple dot     |                   |
| Has been suspended by a wait instruction                     | blue dot       |                   |
| The source code is encrypted                                 | dark gray dot  |                   |
| The source code is inherited                                 | dark green dot |                   |

3D shows the state as a colored rectangle along the upper border of the picture. The colors are the same as in 2D.

<!-- image -->

See also

States &gt; State Graphic in 3D

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Exporter

Icons of the Method

#### The Method Editor

The Method Editor

Double-click the icon of the Method , which you inserted into a Frame , to open its window.

To change the properties of the Class of the object, double-click it in the Class Library or on the tab Information Flow in the Toolbox . It provides access to the Method Editor and to the Method Debugger .

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog box Edit 3D Properties .

See also

Edit Ribbon Tab [Method]

Tools Ribbon Tab

Context Menu of the Method

Drag-and-Drop in the Method Editor

Method Debugger

Programming a Method

Working in the Method Window

Colors for Syntax Highlighting

Edit Ribbon Tab

Edit Ribbon Tab [Method]

The Edit ribbon tab provides commands for editing the source code of your Method .

<!-- image -->

<!-- image -->

| Command                                                         | Looks like this   | Method   |
|-----------------------------------------------------------------|-------------------|----------|
| Undo [source code]                                              |                   | -        |
| Redo [source code]                                              |                   | -        |
| Auto Complete                                                   |                   | -        |
| Toggle Comment                                                  |                   | -        |
| Increase Indent                                                 |                   | -        |
| Decrease Indent                                                 |                   | -        |
| Reformat Selection                                              |                   | -        |
| Move Up [source code]                                           |                   | -        |
| Move Down [source code]                                         |                   | -        |
| Line Operations Line Operations Line Operations Line Operations |                   | -        |
| Select Template                                                 |                   | -        |

###### Edit Ribbon Tab [Method]

<!-- image -->

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Method .

###### Import from File

Opens the dialog Open . Select the text file that contains the source code that you would like to import into the active Method and click OK .

<!-- image -->

SimTalk

load [SimTalk] - source code

See also

Working in the Method Window

**Export to File [Method]**

###### Export to File [Method]

Opens the dialog Save As . Select the folder , type in the fi le name of the text file to which you would like to save the source code of the active Method , select the fi le type , and click OK .

<!-- image -->

To save color highlighting of keywords and comments in the source code, select HTML Files or RichText Files .

<!-- image -->

Plant Simulation adds a comment before the source code proper with the path of Method . This way you can always tell which text file belongs to which source code.

**SimTalk**

writeStringToFile [SimTalk]

See also

Working in the Method Window

###### Print [source code]

Opens the dialog Print . Select the settings for printing the source code of the object Method and print the source code by clicking OK .

<!-- image -->

Find Text

**Find Text [in Method]**

Opens the dialog Find . With its settings you can find expressions in your source code and replace them if necessary.

<!-- image -->

You can select text in your source code and temporarily mark it by pressing Ctrl+F2 . In our example below we marked the expression MUName . To delete this selection again, we marked the expression Station and pressed Ctrl+F2 again. Instead, you can also click Clear Bookmarks on the Tools ribbon tab.

<!-- image -->

If you select text with Shift and with the arrow keys on your keyboard or with the mouse pointer, Plant Simulation highlights all occurrences of this text fragment in the source code in color. You can then jump to these occurrences like you jump to bookmarks by clicking the respective buttons on the ribbon or by pressing F2 .

When searching for the corresponding text fragments, Plant Simulation does not differentiate between upper- and lower-casing. Find Text searches for:

- Whole words, except for the selected text contains blank spaces, tabulators, or line breaks.
- Entire rows.
- Line comments starting at the character you typed in ( --or // ).
- Text which starts or ends with SimTalk -syntax-specific characters, such as '(' , '[' , '"' , ')' , ']' , ';' , etc.

When you move the text cursor with keyboard keys or with the mouse pointer, this also deletes or changes highlighting.

See also

<!-- image -->

**Find What**

Type the expression that you want to find into the text box Find What .

<!-- image -->

**Regular Expressions**

To use regular expressions in your search, click the button with the arrow pointing to the right. This opens the window Regular Expression .

Select one of the regular expressions listed below. Plant Simulation then enters it into the text box Find What . Compare the examples under regex\_search .

| Select                           | To enter and to find   |
|----------------------------------|------------------------|
| Any single character             | .                      |
| Beginning of line                | ^                      |
| End of line                      | $                      |
| Beginning of word                | \<                     |
| End of word                      | \>                     |
| Group                            | \(\)                   |
| Zero or one matches              | ?                      |
| Zero or more matches             | *                      |
| One or more matches              | +                      |
| Any one character in the set     | [ ]                    |
| Any one character not in the set | [^]                    |
| Or                               | \&#124;                |

<!-- image -->

Plant Simulation only finds a search term with a regular expression if you select the check box Regular Expression .

**Replace With**

Type the expression that replaces the search term which you typed into the text box Find What .

<!-- image -->

**Match Whole Word Only**

**Match Whole Word Only**

To only find whole words only instead of searching for the expression you typed into the text box inside longer words, select the check box.

**Match Case**

To only find text that has the same pattern of upper and lower case as the expression you typed into the text box Find what , select the check box.

Regular Expression

To use regular expressions in your search, select the check box.

<!-- image -->

**Direction [in Search]**

Select the direction in which Plant Simulation searches.

- Select Up to search toward the beginning of the Method .

- Select Down to search toward the end of the Method .

**Note**

Shift+Ctrl+F3 searches for the next occurrence upward without having to use the Find dialog.

Ctrl+F3 searches for the next occurrence downward.

**Find Next [source code]**

**Find Next [source code]**

To find the next instance of the expression which you typed into the text box Find What , click this button.

<!-- image -->

Plant Simulation selects the expression it found in the source code.

**Replace [source code]**

To replace the expression from the text box Find What with the expression you typed into the text box Replace With , click this button.

<!-- image -->

Then Plant Simulation searches for the next occurrence of the search term and stops there.

**Mark All**

**Mark All**

To highlight all instances of the expression which you typed into the text box Find What , click this button.

To execute the action of your choice, use the commands on the Tools ribbon tab ( Toggle Bookmarks , Clear All Bookmarks , Next Bookmark , and Previous Bookmark ).

**Replace All**

To replace all instances of the expression from the text box Find What with the expression you typed into the text box Replace With , click this button.

**Find Previous [source code]**

###### Find Previous [source code]

Finds and highlights the previous occurrence of the search term you typed into the text box Find What .

<!-- image -->

See also

Find Next [source code]

###### Find Next [source code]

Finds and highlights the next instance of the expression you type into the text box Find What starting at the cursor position.

<!-- image -->

See also

Find Previous [source code]

###### Incremental Search

Finds the expression which you start typing. Plant Simulation highlights the character combination while you type in the text window.

<!-- image -->

Microsoft describes Incremental Search as "a type of search that looks for a string in an automatic and progressive way. As the user types a string, possible matches are found, thus enabling the user to stop typing the complete string as soon as the right match is found."

- If you mistype a word, delete the last character you typed by pressing Backspace . Then, type in the correct character.
- Press F3 to find the next instance of the expression.
- Press Esc to terminate Incremental Search .

Incremental Search for Workers

Incremental Search also finds Workers , which are located on Workplaces , FootPaths , and on their way to the WorkerPool . It does not find Workers located in the WorkerPool though.

In general, Incremental Search finds objects by their name. For Workers Incremental Search also includes the name of the class and the counter of the instance . For Worker:1 Incremental Search finds the first instance of the class named Worker for example.

###### Undo [source code]

Undoes the last change that you made to the source code and returns the source code to the state it had before the last change.

<!-- image -->

See also

Redo [source code]

**Redo [source code]**

###### Redo [source code]

Redoes all changes of the source code you made with an undo action.

<!-- image -->

**See also**

**Undo [source code]**

###### Auto Complete

Auto Complete is an automatic data entry mechanism: Type in the first letter or letters the name of an attribute/read-only attribute/method , and press Ctrl+Spacebar or Shift+Ctrl+Spacebar or click Auto Complete .

<!-- image -->

When Plant Simulation reaches a point at which the name is not unique anymore, it opens a window in which you can select an attribute/read-only attribute/method . Move the cursor over the name of the attribute/read-only attribute/method of your choice and double-click to select it or use the up and down keys on your keyboard to move within the list. Press the Enter key to select the entry of your choice. Plant Simulation then automatically completes the name for you and adds the corresponding characters -period, opening parenthesis, assignment operator (:=), and closing parenthesis to your source code if necessary.

You can filter the attribute/read-only attribute/method , which the object provides, according to the same criteria as in the window Show Attributes and Methods . To make the window larger, drag the mouse over one of the sides or a corner of the window and drag the mouse.

<!-- image -->

<!-- image -->

| To do this                                                                                                                                                                                               | Click   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|
| Show General Attributes/Methods                                                                                                                                                                          |         |
| Show User Interface/Animation Attributes/Methods                                                                                                                                                         |         |
| Show Control Attributes/Methods                                                                                                                                                                          |         |
| Show Simulation Attributes/Methods                                                                                                                                                                       |         |
| Show Energy related Attributes/Methods                                                                                                                                                                   |         |
| Show 3D Attributes and Methods                                                                                                                                                                           |         |
| Show Statistics Attributes/Methods                                                                                                                                                                       |         |
| Show Attributes . This encompasses the built-in attributes, local variables, and objects of type Variable .                                                                                              |         |
| Show Read-Only Attributes . These are attributes and methods , which do not expect parameters, which do not have side effects, and which return a value.                                                 |         |
| Show Methods . Methods as a rule have parameters, have side effects, and return a value. The command shows the built-in methods, user- defined attributes of type method, and objects of type Variable . |         |
| Show Global Functions . This encompasses global functions and constants.                                                                                                                                 |         |
| Show Objects . This encompasses objects in the Frame , objects of type Variable and objects of type Method .                                                                                             |         |
| Show Keywords                                                                                                                                                                                            |         |

If you insert a function or a Method with parameters into a Method , Plant Simulation shows the status bar. The status bar shows the signature of the function/ Method and thus makes typing the required parameters in easier. Plant Simulation hides the status bar again when you type in the closing parenthesis or when you press Esc .

**See also**

Show Completion Tooltip [preferences]

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=NS9lkfDV2ERnn83N&amp;t=457](https://youtu.be/MXDcx2yplxc?si=NS9lkfDV2ERnn83N&t=457)

<!-- image -->

**Toggle Comment**

###### Toggle Comment

Changes the current line or selection into a comment or into normal source code and vice versa.

<!-- image -->

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=pS2IRdpKXzPBWu0u&amp;t=560](https://youtu.be/MXDcx2yplxc?si=pS2IRdpKXzPBWu0u&t=560)

###### Increase Indent

Moves the selected range of the source code one tab length to the right.

<!-- image -->

Select the tab size under File &gt; Preferences &gt; Editor &gt; Text settings &gt; Tab Size .

See also

**Decrease Indent**

**Decrease Indent**

###### Decrease Indent

Moves the selected range of the source code one tab length to the left.

<!-- image -->

Select the tab size under File &gt; Preferences &gt; Editor &gt; Text settings &gt; Tab Size .

See also

**Increase Indent**

###### Reformat Selection

Automatically indents the selected selection of the source code according to the tab settings to show the Method's structure more clearly.

<!-- image -->

It automatically indents all rows inside of an if-else-end block to make it easier to detect the logic used for example.

To reformat the entire source code , click anywhere within the source code and select Reformat Selection .

**Note**

The command Reformat Selection is not available in SimTalk Version 1.0 .

###### Move Up [source code]

Move Up [source code]

Moves the selected line or the selected lines of source code up one line.

<!-- image -->

Move Down [source code]

Moves the selected line or the selected lines of source code down one line.

<!-- image -->

**Line Operations**

###### Line Operations

Provides subcommands for manipulating the lines of source code.

<!-- image -->

Duplicate Line

The command Duplicate Line duplicates the selected line or the selected lines of source code.

Delete Line

The command Delete Line deletes the selected line or the selected lines of source code.

Copy Line

The command Copy Line copies the selected line or the selected lines of source code.

Cut Line

The command Cut Line cuts the selected line or the selected lines of source code.

**Select Template**

###### Select Template

Opens a dialog in which you can select one of the templates we provide for a number of commonly used tasks.

<!-- image -->

- Select the Category of template you want to use in the left list box.
- Select the Template you want to use in the middle list box.
- View the description of the selected category of the template in the right text box.

<!-- image -->

You can select the Template Directory under Preferences &gt; Editor .

Creating Your Own Templates describes how to add template which you or a colleague created to the dialog.

SimTalk

setErrorHandler [SimTalk]

**Creating Your Own Templates**

**Creating Your Own Templates**

Create a method template of your own in a text editor and save it as a text file (*.txt).

The syntax used is quite simple:

- Create the file in the sub-folder C:\Program Files\Siemens\Plant Simulation XX\Templates\English\Name\_of\_Your\_Category . The dialog Select Template shows this name in the field below Select the Category .
- Type in two hyphens --followed by the key combination which you want to use if you want to set a key combination.
- Type in two hyphens --and the name of the template. The dialog Select Template shows this name in the field below Select the Template .
- Type in two hyphens --and a description of the template. The dialog Select Template shows this description in the rightmost field.
- Type in /* and then the comment which the template itself shows after you loaded it into the Method Editor . Close this comment with */ .

Type in the variable you want to use and any comment you would like to add.

Type in the item you want the user to replace in the source code within left and right pointing double angle quotation marks, «attribute»=«value» in our example.

If the user drags the mouse over this item, the Method shows the text you type in at the end of the file as a Tooltip : Start this tooltip text with /* followed by the search term you typed in in the double angle quotation marks. Finish it with §§*/ . You can type in the Tooltip , but do not have to do it.

- Type in the key combination that the user can type in to insert the code snippet.

Proceed as follows to insert the code snippet: Suppose that the key combination is Ctrl+T C . Hold down Ctrl and press T on the keyboard. Then release Ctrl and type in the letter that is assigned to the code snippet, C in our case.

The text for the Processing Time depending on an attribute of the part looks like this.

```simtalk
-- Determines the processing time of a station in a formula -- according to an attribute of the MU. -- @ is the MU that triggers the formula -- ? is the station calling this method
->time
if @.«attribute»=«value»
	result:=«time» -- add your code here
elseif @.«attribute»=«value»
	result:=«time» -- add your code here
else
-- add your code here
```

end

The Method shows it like this after loading it.

<!-- image -->

**Note**

Compare any of the method templates that are part of your program package.

**Insert Control Structure**

###### Insert Control Structure

Provides subcommands for inserting statements into the source code of the Method .

<!-- image -->

**Note**

The control structures create ready-made SimTalk source code.

**Note**

The command Insert Control Structure is not available in SimTalk Version 1.0 .

**See also**

**Select Template**

Creating Your Own Templates

**Template Directory**

if-else

Inserts an if-else -statement at the position of the cursor into the source code.

Type in the condition of the if -statement. Press the Tab key to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command if-else . Then Plant Simulation inserts an if -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

Branching with if-else-end

Multiple Branching with if-elseif-end

Back To

Insert Control Structure

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=\_YMongIShycaXDze&amp;t=920](https://youtu.be/MXDcx2yplxc?si=_YMongIShycaXDze&t=920)

**if-else-end**

if-else-end

Inserts an if -statement at the position of the cursor into the source code.

Type in the condition of the if -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command if-else-end . Then Plant Simulation inserts an if -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

Branching with if-else-end

Multiple Branching with if-elseif-end

Back To

Insert Control Structure if-elseif-end Inserts an if -statement at the position of the cursor into the source code.

Type in the condition of the if -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command if-elseif-end . Then Plant Simulation inserts an if -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

Branching with if-else-end

Multiple Branching with if-elseif-end

Back To

Insert Control Structure switch-case-end Inserts a switch -statement at the position of the cursor into the source code.

Type in the condition of the switch -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command switch-case-end . Then Plant Simulation inserts a switch -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

Check for a Large Amount of Different Values with switch [SimTalk]

Back To

Insert Control Structure

**switch-case-else-end**

Inserts a switch -statement at the position of the cursor into the source code.

Type in the condition of the switch -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command switch-case-else-end . Then Plant Simulation inserts a switch -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

Check for a Large Amount of Different Values with switch [SimTalk]

Back To

Insert Control Structure while-end Inserts a while -statement at the position of the cursor into the source code.

Type in the condition of the while -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command while-end . Then Plant Simulation inserts a while -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

while loop [SimTalk]

Back To

Insert Control Structure

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=6cpRg5pPk7FGjOb-&amp;t=1122](https://youtu.be/MXDcx2yplxc?si=6cpRg5pPk7FGjOb-&t=1122)

repeat-until

Inserts a repeat -statement at the position of the cursor into the source code.

Type in the condition of the repeat -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command repeat-until . Then Plant Simulation inserts a repeat -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

repeat loop [SimTalk]

Back To

Insert Control Structure

**for-next**

Inserts a for -statement at the position of the cursor into the source code.

Type in the condition of the for -statement. Press Tab to jump to the location within the source code, at which you can type in the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command for-next . Then Plant Simulation inserts a for -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

for loop [SimTalk]

Back To

Insert Control Structure

Video on YouTube

[https://youtu.be/MXDcx2yplxc?si=qlDd80am3ktq\_zcw&amp;t=1030](https://youtu.be/MXDcx2yplxc?si=qlDd80am3ktq_zcw&t=1030)

**for-downto-next**

Inserts a backward loop at the position of the cursor into the source code.

Type in the condition of the for -statement. Press Tab to jump to the location within the source code, at which you can type the statement that is to be executed, when the condition becomes true.

You can also highlight several statements before you select the command for-downto-next . Then Plant Simulation inserts a backward for -statement around these statements in the source code.

Note

Drag the mouse over the sections marked in red to show a Tooltip .

See also

for loop [SimTalk]

Back To

Insert Control Structure

**Inherit Source Code**

###### Inherit Source Code

Turns inheritance of the source code of a Method object which you insert into a Frame off or on.

<!-- image -->

As long as it is turned on, you cannot modify the source code that tells Plant Simulation what to do; the Method then uses the source code of the Method from which it is derived, i.e., its origin.

Click Inherit Source Code to turn it off and thus be able to edit the source code in an open Method .

SimTalk

getAttribute [SimTalk] - object

###### Apply Changes [source code]

Applies any changes you made to the source code and leaves the dialog box open.

<!-- image -->

###### Help on Word

Opens the help topic for the highlighted word which you double-clicked or in front of which you placed the input cursor.

<!-- image -->

This way you can quickly and easily get help for an instruction, for a built-in attribute/read-only attribute/ method/function .

**Tools Ribbon Tab**

##### Tools Ribbon Tab

The Tools ribbon tab of the Method provides commands for working with the source code of your Method .

<!-- image -->

<!-- image -->

| Command                               | Looks like this   | Method                     |
|---------------------------------------|-------------------|----------------------------|
| Run [button] - Method                 |                   | execute [SimTalk] - Method |
| Debug Method [button]                 |                   | debug [SimTalk]            |
| Toggle Bookmarks                      |                   | -                          |
| Clear All Bookmarks                   |                   | -                          |
| Previous Bookmark                     |                   | -                          |
| Next Bookmark                         |                   | -                          |
| Toggle Class Breakpoint               |                   | -                          |
| Toggle Instance Breakpoint            |                   | -                          |
| Delete All Class Breakpoints          |                   | -                          |
| Delete All Instance Breakpoints       |                   | -                          |
| Delete All Breakpoints [Tools ribbon] |                   | -                          |
| Previous Breakpoint [Tools ribbon]    |                   | -                          |
| Next Breakpoint [Tools ribbon]        |                   | -                          |

###### Tools Ribbon Tab

<!-- image -->

<!-- image -->

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Method .

You can also select some of these settings under the File Menu &gt; Preferences &gt; Editor . These settings then apply to all new Methods that you insert afterward.

The settings on the Tools ribbon tab of the Method only apply to the open Method .

See also

Edit Ribbon Tab [Method]

**Run [button] - Method**

###### Run [button] - Method

Runs the entire Method , i.e., executes the entire source code.

<!-- image -->

Or you can right-click the Method and select Run on the context menu.

<!-- image -->

**SimTalk**

execute [SimTalk] - Method

###### Debug Method [button]

Runs the Method , i.e., executes the source code one step at a time in the Debugger .

<!-- image -->

Plant Simulation opens the Method Debugger where you can step through the source code using the Step Into or Step Over commands/buttons. The command Debug does the same as running the Method while holding down the Ctrl+Alt+Shift keys.

- If Plant Simulation is stuck in an endless loop and if Plant Simulation is running in the foreground, hold down the Ctrl+Alt+Shift left keys for 5 seconds to open the Method Debugger while a Method is being executed.
- If Plant Simulation is stuck in an endless loop and if Plant Simulation is not running in the foreground, hold down the Ctrl+Alt+Shift right keys for 5 seconds to open the Method Debugger while a Method is being executed.

SimTalk

debug [SimTalk]

**Toggle Bookmarks**

###### Toggle Bookmarks

Adds a bookmark for the current row or the currently selected range of the source code. Plant Simulation highlights the bookmark in the bar to the left. Bookmarks facilitate navigation in source code that extends over many lines.

<!-- image -->

Plant Simulation marks temporary bookmarks in the source code of a Method in a brighter color than saved bookmarks . This might, for example, be the case if you changed the source code of a Method and set a bookmark after the original end of the source code. Temporary bookmarks will be lost if you do not apply the source code.

###### Clear All Bookmarks

Deletes all bookmarks from the source code.

<!-- image -->

**Previous Bookmark**

###### Previous Bookmark

Goes to the previous bookmark.

<!-- image -->

###### Next Bookmark

Goes to the next bookmark.

<!-- image -->

**Toggle Class Breakpoint**

###### Toggle Class Breakpoint

Adds or deletes a breakpoint to all instances sharing this source code.

<!-- image -->

Click in the line in which you would like to set a class breakpoint . Then, click Toggle Class Breakpoint or press F9 to set a class breakpoint in front of the statement of the line of code.

A class breakpoint is designated by a filled red circle .

If you insert a class breakpoint and an instance breakpoint in the same line, the Method shows a white star within a red circle .

Once the Method reaches a breakpoint while being executed, the Method Debugger opens and highlights the line in yellow. You can then inspect and modify the contents of the local variables and the parameters.

**Instead, you can also:**

- Click in the line in which you would like to set a class breakpoint with the right mouse button and select the command Class Breakpoint in the Context Menu of the Method Debugger .
- Click on the Toolbar of the Method Debugger .
- Click in the area of the row markers and breakpoints.

<!-- image -->

To activate all breakpoints contained in a line of source code, hold down Ctrl and double-click a breakpoint.

To open the dialog Breakpoint Settings , hold down Shift and Ctrl and double-click a breakpoint.

If a line of source code contains an Instance Breakpoint and a Class Breakpoint , Plant Simulation opens the dialog Breakpoint Settings of the Class Breakpoint .

Plant Simulation marks temporary breakpoints in the source code of a Method in a brighter color than saved breakpoints. This might, for example, be the case if you changed the source code of a Method and set a breakpoint after the original end of the source code. These breakpoints will be lost if you do not apply the source code.

You can also set a Class Breakpoint and/or an Instance Breakpoint for an encrypted method. The Method then stops during method execution in the Method Debugger .

If you did set a breakpoint, the Method shows the breakpoint within the Method Editor or the Method Debugger to the left of the message Source code is encrypted .

See also Working with Breakpoints Classes, Subclasses, and Instances Breakpoint Active [Debug menu] Breakpoint Settings [Debug menu] Breakpoint Active [context menu]

Breakpoint Settings [context menu]

###### Toggle Instance Breakpoint

Adds or deletes a breakpoint to this instance of the source code only.

<!-- image -->

Click in the line in which you would like to set an Instance Breakpoint . Then, select the command Toggle Instance Breakpoint or press Shift+ F9 to set an Instance Breakpoint that only applies to this instance.

<!-- image -->

An Instance Breakpoint is designated by a red star

.

If you insert a Class Breakpoint and an Instance Breakpoint in the same line, the Method shows a white star within a red circle .

Once the Method reaches this breakpoint while the Method is being executed, Plant Simulation opens the Method Debugger and displays the line inverted in yellow. You can then inspect and modify the contents of the local variables and the parameters.

Instead, you can also click in the line in which you would like to set an Instance Breakpoint with the right mouse button and select the command Instance Breakpoint in the Context Menu of the Method Debugger .

Plant Simulation shows temporary breakpoints in the source code of a Method in a brighter color than saved breakpoints. This might, for example, be the case when you changed the source code of a Method and set a breakpoint after the original end of the source code. These breakpoints will be lost if you do not apply the source code.

To activate or deactivate Instance Breakpoints , hold down Shift and click in the area of the row markers and breakpoints.

You can also set a Class Breakpoint and/or an Instance Breakpoint for an encrypted method. The Method then stops during method execution in the Method Debugger .

If you did set a breakpoint, the Method shows the breakpoint within the Method Editor or the Method Debugger to the left of the message Source code is encrypted .

See also

Working with Breakpoints

Classes, Subclasses, and Instances

Breakpoint Active [Debug menu]

**Breakpoint Settings [Debug menu] Breakpoint Active [context menu] Settings**

**Delete All Class Breakpoints**

###### Delete All Class Breakpoints

Deletes all breakpoints that you activated with the command Toggle Class Breakpoints of the Method and its class.

<!-- image -->

See also

Working with Breakpoints

Toggle Class Breakpoint

###### Delete All Instance Breakpoints

Deletes all breakpoints that you activated with the command Toggle Instance Breakpoints of the Method in the Debugger window.

<!-- image -->

See also

Working with Breakpoints

Toggle Instance Breakpoint Delete All Breakpoints [Tools ribbon]

Deletes all class breakpoints and all instance breakpoints you have set.

<!-- image -->

###### Previous Breakpoint [Tools ribbon]

Goes to the previous class or instance breakpoint in the source code.

<!-- image -->

See also

Working with Breakpoints

###### Next Breakpoint [Tools ribbon]

Next Breakpoint [Tools ribbon]

Goes to the next class or instance breakpoint in the source code.

<!-- image -->

See also

Working with Breakpoints

###### Toggle Outline

Switches the collapsed state of the outline in which the cursor is located in the source code of the Method to the uncollapsed state and vice versa.

<!-- image -->

Instead, you can also click to the left of the source code.

<!-- image -->

**Previous Outline**

###### Previous Outline

Goes to the previous outline in the source code of the Method .

<!-- image -->

Outlines have a + sign ( ) in front of a line of code.

###### Next Outline

Goes to the next outline in the source code of the Method .

<!-- image -->

Outlines have a + sign ( ) in front of a line of code.

**Collapse All Outlines**

###### Collapse All Outlines

Collapses all outlines in the source code of the Method .

<!-- image -->

Outlines have a + sign ( ) in front of a line of code.

###### Expand All Outlines

Expands all outlines in the source code of the Method .

<!-- image -->

Outlines have a + sign ( ) in front of a row of code.

**Hide/Unhide Text**

###### Hide/Unhide Text

Creates an outline from the selected source code or deletes an existing outline for the text.

<!-- image -->

###### Encrypt Method

Encrypts the source code of the Method . This prevents unauthorized access by other users if you pass the model on to colleagues or customers.

<!-- image -->

Type in the password for encrypting the Method into the text box Password .

Type in the password for encrypting the Method again into the text box Confirm Password .

Make sure to remember the password, as only this password will allow you to decrypt the source code afterward. After clicking OK , the source code cannot be accessed anymore without the password you typed in.

After you have encrypted the Method , the command Encrypt changes to Decrypt . In addition, you can encrypt all Methods in the entire model, except for Methods in the Class Library , by selecting File &gt; Options &gt; Encrypt Methods in the Plant Simulation main window.

SimTalk

encrypt [SimTalk]

decrypt [SimTalk]

See also

Decrypt Method

Encrypt Methods

Decrypt Methods

###### Decrypt Method

Decrypts the encrypted source code of a Method .

<!-- image -->

Type the correct password you used to encrypt the Method into the text box Password . In addition, you can decrypt the entire model by selecting File &gt; Options &gt; Decrypt Methods in the Plant Simulation main window.

SimTalk

decrypt [SimTalk]

encrypt [SimTalk]

See also

Encrypt Methods

Decrypt Methods

###### New Syntax [command]

Activates SimTalk 2.0 syntax.

<!-- image -->

Then you have to type the source code into Methods in the improved, abbreviated notation.

If you want to use SimTalk 2.0 syntax for all new Methods which you are going to program, activate New Syntax in the Method class in the Class Library .

**Note**

Clicking New Syntax for an existing Method , whose source code you created in SimTalk 1.0 notation , automatically converts that source code to source code in the correct SimTalk 2.0 notation .

Plant Simulation writes the setting New Syntax to the model file.

If New Syntax is deactivated, you have to type the source code into Methods using SimTalk 1.0 notation .

To convert the source code of all existing Methods in a simulation model to the new syntax, hold down Shift , click the object Basis in the Class Library with the right mouse button and click Convert all Methods to New Syntax .

**SimTalk**

UsingNewSyntax [SimTalk]

See also

SimTalk 2.0 and SimTalk 1.0 Compared

A Quick Tour Through SimTalk 2.0

General Access to SimTalk

<!-- image -->

###### Syntax-controlled Indentation [Tools ribbon]

Activates or deactivates the indentation of the source code you type in according to the predefined SimTalk syntax.

<!-- image -->

<!-- image -->

If it is active, Plant Simulation automatically indents the cursor when starting a new line of code according to the delimiting keywords. Plant Simulation indents, for example, the text between if and end , making it easier to follow the logic behind the source code.

The Method Editor aligns the source code with the previous line of code.

If you change this setting, the change applies during the entire Plant Simulation session for all newly opened Methods .

**Note**

The command Syntax-controlled Indentation is not available in SimTalk Version 1.0 .

**Show Line Numbers [Tools ribbon]**

###### Show Line Numbers [Tools ribbon]

Shows or hides line numbers to the left of the rows of the source code.

<!-- image -->

<!-- image -->

If you change this setting, the change applies during the entire Plant Simulation session for all newly opened Methods .

View

**View [Method]**

The commands on the submenu View set what Plant Simulation shows in the Frame window.

Settings you select here override those you selected under File &gt; Preferences &gt; Editor in the Plant Simulation window.

A check mark to the left of a command means that this command is active, i.e., that Plant Simulation shows the selected item.

To not show an item, click the command so that it does not show a check mark.

<!-- image -->

If you change one of these settings, the change applies during the entire Plant Simulation session for all newly opened Methods .

- Show Outlining [Method]
- Highlight Current Line [source code]
- Show Completion Tooltip [command]

**Show Outlining [Method]**

**Show Outlining [Method]**

Shows the outlining of a sequence of source code lines, such as control and loop structures, as an expansible and collapsible structure. To show the collapsed structure again, reselect the command.

<!-- image -->

If you change this setting, the change applies during the entire Plant Simulation session for all newly opened Methods .

**Note**

The command Show Outlining is not available in SimTalk Version 1.0 .

**Highlight Current Line [source code]**

Highlights or does not highlight the current line of source code.

<!-- image -->

If you change this setting, the change applies during the entire Plant Simulation session for all newly opened Methods .

**Show Completion Tooltip [command]**

**Show Completion Tooltip [command]**

Activates or deactivates if Plant Simulation shows a Tooltip when Auto Complete reaches a point from which on the name is unique.

This way you can press Ctrl+Spacebar without having to type in too many letters.

<!-- image -->

If you change this setting, the change applies during the entire Plant Simulation session for all newly opened Methods .

**See also**

Show Completion Tooltip [preferences]

Auto Complete

##### Context Menu of the Method

The context menu that a click with the right mouse button opens, provides the most important commands for the Method .

Some of the commands are located on the mini toolbar , while others are commands on the context menu itself.

<!-- image -->

You can also close the context menu and leave the mini toolbar open by clicking the border of the mini toolbar with the left mouse button.

<!-- image -->

<!-- image -->

| Command                    | Button   |
|----------------------------|----------|
| Open Class                 |          |
| Copy Objects               |          |
| Cut Objects                |          |
| Paste Objects              |          |
| Delete Objects             |          |
| Inherit Source Code        |          |
| Apply Changes              |          |
| Toggle Class Breakpoint    |          |
| Toggle Instance Breakpoint |          |
| Open Object                | -        |
| Show Object                | -        |
| Run                        |          |
| Debug                      | -        |
| Insert Control Structure   | -        |

**See also**

Context Menu of the Method Debugger Drag-and-Drop in the Method Editor Drag-and-drop in the Method Editor performs a number of actions.

Hold down the keys described below when dragging and dropping in the Method Editor .

| To do this                                                               | Drag from    | To          | Type   | Accelerator   |
|--------------------------------------------------------------------------|--------------|-------------|--------|---------------|
| Move the selected text                                                   | text window  | text window | text   | none          |
| Copy the selected text                                                   | text window  | text window | text   | Ctrl          |
| Insert the selected text                                                 | any          | text window | text   | any           |
| Copy the selected text                                                   | text window  | any         | text   | Ctrl          |
| Cut the selected text                                                    | text window  | any         | text   | none          |
| Pass the dropped objects as a parameter of data type array to the Method | Frame window | Method      | object | none          |

Multiple Drag and Drop with SimTalk

An example of multiple drag-and-drop with SimTalk might look like this:

```simtalk
param a: object[]
for var i := 1 to a.Dim
	print "i=", i, " : ", a[i]
next
```

If we select the objects Station , Station1 , and ParallelStation in the Frame window, drag them onto the icon of the Method and drop them there, the Console shows this:

i=1 : .Models.Model.Station i=2 : .Models.Model.ParallelStation i=3 : .Models.Model.Station1

See also

Use a Drag-and-Drop Control for Several Objects

#### The Method Debugger

##### Method Debugger

Debug the source code which you wrote in the Method Editor in the Method Debugger while the Method is being executed.

To open the Method Debugger you can either:

- Press F11 in the Method Editor window.
- Select the command Debug Method on the Tools Ribbon Tab in the Method Editor window.

**Note**

If Plant Simulation is running in the foreground and is stuck in an endless loop, hold down Ctrl+Alt+left Shift for several seconds to open the Debugger while a Method is being executed.

If Plant Simulation is not running in the foreground, hold down Ctrl+Alt+right Shift for several seconds to open the Debugger while a Method is being executed.

**Note**

Plant Simulation opens the Debugger automatically when it encounters an error while executing the source code or when it hits a breakpoint.

<!-- image -->

The Debugger window shows source code with the parameters and local variables of the Method . You can set breakpoints at critical points and then check each step of the Method execution to see if the source code does what you programmed it to do:

**Method Debugger**

- Press F9 and select the context menu command or click the right mouse button while holding Shift down to insert a Class Breakpoint , designated by a filled red circle to the left of the line.
- Press Shift+F9 and select the context menu command or click the right mouse button while holding Shift+Ctrl down to insert an Instance Breakpoint , designated by a red star to the left of the line. It only applies to this instance.

Once execution of the Methods reaches this Method , Plant Simulation opens the Method Debugger . It shows the values of attributes and local variables as a Tooltip when you drag the mouse over the instruction.

Double-click a word to select it. Triple-click in a line to select the entire line. Quadruple-click to select the entire source code.

The Method highlights lines with faulty source code in red in the Method Debugger . It shows a message telling you what's wrong in the status bar of the Method Debugger window.

To restart executing the source code that follows after break point or an error, hold down Ctrl and double-click that line.

If the Method Debugger was opened because of a runtime error and if you then close the Method Debugger , Plant Simulation terminates all call chains without asking and stops the simulation.

If you only want to terminate the incorrect call chain and continue the simulation, press F5 instead of closing the Method Debugger .

If you do not want to terminate the incorrect call chain, you can continue executing the incorrect Method in a certain line of code by calling the context menu command Set Next Statement , or by placing the input cursor into this line and by pressing Ctrl+F10 , or by holding down Ctrl and double-clicking this line. Then press F5 to continue executing the Method in this line.

The lower part of the Debugger window shows the Watch Window with the Tab Variables , the Tab Anonymous Identifiers , the Tab Call Stack , the Tab Call Chains , the Tab Suspended , and the Tab Expressions .

<!-- image -->

This is especially handy if you want to show the contents of two tabs of the Watch Window at the same

<!-- image -->

time. Then, you can click and open a second watch window and click another tab there. You can change its height by dragging the splitter.

###### See also

Toolbar of the Method Debugger

Menu Bar of the Method Debugger

Context Menu of the Method Debugger

\_Functions for Debugging the Model

###### Video on YouTube

[https://youtu.be/pbOQD0p4hO4?si=P0Frai1pltBZLxAD&amp;t=614](https://youtu.be/pbOQD0p4hO4?si=P0Frai1pltBZLxAD&t=614)

Watch Window

Watch Window [described]

The Watch window shows information about the variables and anonymous identifiers used in your source code.

**Opening the Watch Window**

<!-- image -->

- Press the F12 key.
- Select the menu command Debug &gt; Watch Window . By default, the Watch Window is part of the Debugger window.

<!-- image -->

**See also**

@ [at sign, Method Debugger]

? (Question mark)

.

###### Tab Variables [Watch window]

Tab Variables [Watch window]

The tab Variables shows the names of all local variables and their values in their source code.

If you double-click a variable, Plant Simulation opens the dialog Variable in which you can change the value of the variable. Click OK to apply the new value and to close the dialog. Click Cancel to discard your changes and to close the dialog.

<!-- image -->

The context menu shows the exact value with 17 floating point digits for local variables of data type real , length , weight , speed , and acceleration . For values with a physical unit ( length , weight , speed , and acceleration ) the value is shown in the respective SI unit, as Plant Simulation always keeps values internally in SI units. If you selected another unit, Plant Simulation only converts the value for display purposes when showing it. This has the advantage that Plant Simulation always computes with the same numbers, independent of the selected unit, and that then the same rounding inaccuracies occur. Plant Simulation thus always computes the same simulation results independent of the selected units.

**See also**

**Local Variables**

Tab Anonymous Indentifiers

Tab Anonymous Identifiers [Watch window]

The tab Anonymous Identifiers shows the anonymous identifiers @ , ? , current , self , root , and rootfolder .

For user-defined attributes of data type Method Plant Simulation shows self.~ in addition.

For formulas and tables Plant Simulation shows xSelf and ySelf .

<!-- image -->

The cells next to the anonymous identifiers @ and ? allow you to test the Method without running a simulation. You only need to type something into these cells if you used @ and ? in your method.

If you type a path for @ or ? in the Method Debugger and type this anonymous identifier into a Method , Plant Simulation will internally replace this anonymous identifier with the specified path.

The Watch Window shows changed values in red in the cells under Value .

**See also**

Anonymous Identifiers [described]

Object Paths in SimTalk

@ [at sign, Method Debugger]

? [question mark, Method Debugger]

current [SimTalk] - anonymous identifier

self [SimTalk] - anonymous identifier

root [SimTalk] - anonymous identifier

rootfolder [SimTalk] - anonymous identifier

**Video on YouTube**

[https://youtu.be/pbOQD0p4hO4?si=dZeZUnfEYpNkq8uQ&amp;t=552](https://youtu.be/pbOQD0p4hO4?si=dZeZUnfEYpNkq8uQ&t=552)

**@ [at sign, Method Debugger]**

**@ [at sign, Method Debugger]**

The cell @ in the column Name shows the identifier of the active MU , i.e., the MU that triggers the call of the current Method in a control. You cannot change the contents of the cell!

<!-- image -->

Press F2 to open the dialog box of the MU . If a user-defined method contains the identifier @ and if you would like to test the Method without running the simulation, you have to specify a suitable object in the object Method . The Debugger uses the contents of the cell @ of the Method .

The Watch Window shows changed values in red in the cells under Value .

See also

Anonymous Identifiers &gt; @ [SimTalk] - anonymous identifier

**? [question mark, Method Debugger]**

The cell ? in the column Name shows the name of the object that calls the Method .

If that is another Method , the cell contains the name of that Method . Otherwise, it contains the name of the object in which a MU triggered a control call. You cannot change the contents of the cell!

<!-- image -->

Press F2 to open the dialog box of the calling object. If a user-defined Method contains the identifier ? and you would like to test the Method without running the simulation, you have to specify a suitable object in the object Method . The Debugger uses the contents of the cell ? of the Method .

The Watch Window shows changed values in red in the cells under Value .

See also

Anonymous Identifiers [described] &gt; ? [SimTalk] - anonymous identifier

###### Tab Call Stack [Watch window]

Shows the sequence in which the Methods are called, i.e., the call chain. The first Method to be activated is always located at the bottom of the list, while the top line shows the Method being executed at the moment.

<!-- image -->

Double-click a cell on the tab Call Stack to open the respective Method , together with its current settings of local variables and parameters, in the Debugger . Double-click the topmost cell to return to the Method being executed at the moment.

The column Method shows the name of the Method .

The column Parameters shows the parameters of the Method .

**Note**

The column always shows the current value of the parameters, i.e., if the value was changed in the meantime, the new value is shown, not the value that was originally passed to the Method .

**SimTalk**

**getCallStack [SimTalk]**

Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=A\_B8xFC\_7MKVPVu1&amp;t=552](https://youtu.be/5t-wLNmKpbU?si=A_B8xFC_7MKVPVu1&t=552)

###### Tab Call Chains [Watch window]

Shows Methods which are ready to be executed immediately.

Do not confuse these with the active Method being executed at the moment.

<!-- image -->

Active Methods are methods that were called and are now waiting to be executed while other Methods , such as other controls triggered by events, are still being executed.

**Video on YouTube**

[https://youtu.be/5t-wLNmKpbU?si=A\_B8xFC\_7MKVPVu1&amp;t=552](https://youtu.be/5t-wLNmKpbU?si=A_B8xFC_7MKVPVu1&t=552)

###### Tab Suspended [Watch window]

Shows Methods that were suspended by a waituntil-statement or by a stopuntil-statement .

It also shows Methods , which have been suspended by a wait -instruction or by a sleep [SimTalk] -instruction.

The caller of the Method is displayed in parentheses, preceded by the absolute Path . Double-click an entry to change to that Method . The third column shows the statement which suspended the Method .

<!-- image -->

If you add a comment after a waituntil-statement , a stopuntil-statement , a wait-statement , or a sleepstatement to the source code of your Method and if this comment starts with three hyphens ---or with three forward slashes /// , Plant Simulation does not show the entire statement on the Tab Suspended of the Watch Window and of the Method Debugger , but only the comment.

<!-- image -->

The method deleteSuspendedMethods deletes all suspensions of all methods.

Plant Simulation shows as tooltip in the Frame window .

<!-- image -->

The tooltip shows the caller of the method , in our case the ExitContr , and the suspended instruction , in our case waituntil SP.empty prio @.ID wait 5:00 ? = PP , which is suspended three times.

**SimTalk**

deleteSuspendedMethods [SimTalk]

See also

Maximum Number of Suspended Methods [preferences]

waituntil [SimTalk] and stopuntil [SimTalk]

Suspending Methods

Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=EdR1UR3xDQhZTeZq&amp;t=993](https://youtu.be/5t-wLNmKpbU?si=EdR1UR3xDQhZTeZq&t=993)

Tab Expressions [Watch window]

Type in any kind of expression which the Debugger is going to evaluate on the tab Expressions .

<!-- image -->

Double-click a row in the list, type in an expression, for example self.xPos+1 , and click OK , so that Plant Simulation applies this entry.

You will notice that the Debugger shows self.xPos+1 in the column Expression and current value in the column Value . If you select Show Expression for all Methods , Plant Simulation shows this expression in the dialog of all Methods .

You can edit the contents of the tab Expressions on the tab itself. To open a variable or an expression whose value has the data type object , click in the cell and press F2 . If the tab Expressions shows a local variable or an attribute, you can edit its value in the cells in the column Value .

**Note**

The tab Expressions is not available if the Method is executed as a formula.

**Video on YouTube**

[https://youtu.be/5t-wLNmKpbU?si=A\_B8xFC\_7MKVPVu1&amp;t=552](https://youtu.be/5t-wLNmKpbU?si=A_B8xFC_7MKVPVu1&t=552)

##### Toolbar of the Method Debugger

The toolbar of the Method Debugger provides buttons with commands helping you to debug your methods.

<!-- image -->

| To do this                                                                                                                                   | Click   | Menu command, SimTalk                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------|---------|------------------------------------------------------------|
| Open the location of the Method , i.e., the Frame in which the Method is located.                                                            |         | Open Location , Location [SimTalk] - material flow objects |
| Open the origin of the Method from which the active Method was derived.                                                                      |         | Open Origin , Origin                                       |
| Return the Debugger to the currently executed Method .                                                                                       |         | -                                                          |
| Open the Watch Window .                                                                                                                      |         | Watch Window                                               |
| Execute one line of the debugged Method at a time. Any methods being called in that line of the source code will not be loaded.              |         | Step Over                                                  |
| Execute one line of the debugged Method at a time. If that line of the source code happens to call other Methods , these are loaded as well. |         | Step Into                                                  |

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| To do this                                                                                                                                                                          | Click   | Menu command, SimTalk                                  |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------|--------------------------------------------------------|
| Step out of the current Method and move on to beginning of the next statement in the calling Method .                                                                               |         | Step Out                                               |
| Continue executing the active Method .                                                                                                                                              |         | Continue                                               |
| Stop the simulation, i.e., stop the execution of all active Methods .                                                                                                               |         | Terminate Simulation                                   |
| Insert a breakpoint into the class or remove it from it.                                                                                                                            |         | Class Breakpoint                                       |
| Insert a breakpoint into the instance or remove it from it.                                                                                                                         |         | Instance Breakpoint                                    |
| Delete all breakpoints in the Method .                                                                                                                                              |         | Remove All Breakpoints , clearAllBreakpoints [SimTalk] |
| Temporarily activate or deactivate the animation of the moving objects and object states. Plant Simulation restores the original setting as soon as you close the Debugger window . |         | MUand State Animation                                  |

Menu Bar of the Method Debugger

Menu Bar of the Method Debugger

The menu bar provides the File Menu , the Edit Menu , the Navigate Menu , the Debug Menu , the View Menu , the Tools Menu , and the Help Menu .

File Menu [Method Debugger]

The File menu provides commands to access its functions.

Export to File [Method]

Print [source code]

Apply Changes [source code]

They are described under the Edit Ribbon Tab [Method] .

Edit Menu [Method Debugger]

The commands are described under the Edit Ribbon Tab .

Navigate Menu

Navigate Menu

The Navigate Menu provides commands to access its functions.

Open Location [described]

Open Origin [described]

Open Class [described]

Go to Class [described]

Open Frame [Method Debugger]

Open Frame [Method Debugger]

Opens the Frame into which you inserted the Method if that Frame window is closed.

If the Frame window is open, Open Frame brings it to the foreground.

Debug Menu

Debug Menu

The Debug menu provides the commands listed in the table of contents to the left.

You can select most of these settings for all Methods on the Debugger Ribbon Tab in the program window.

**Stop On**

Opens a submenu on which you can select at which event the Method Debugger stops when executing a Method .

<!-- image -->

**Stop on Controls**

**Stop on Controls**

The command Stop on Controls stops the simulation when the EventController encounters a Method -an Entrance Control or Exit Control which you typed into an object-that is started from an object and before executing the calling Method . Plant Simulation only executes calls by control methods during a simulation run.

Instead, you can also click Stop on Controls

**Stop on Formulas**

The command Stop on Formulas stops the simulation and opens the Method Debugger whenever a formula is evaluated.

<!-- image -->

Instead, you can also click Stop on Formulas on the Debugger Ribbon Tab .

**Stop on Error Handler**

The command Stop on Error Handler stops the simulation and opens the Method Debugger whenever an error handling method is executed.

<!-- image -->

Instead, you can also click Stop on Error Handlers on the Debugger Ribbon Tab .

**Stop on Wakeup**

The command Stop on Wakeup stops the simulation and opens the Method Debugger whenever the execution of a suspended method is being continued.

Plant Simulation stops the simulation when waking up all suspended Methods that were suspended with waituntil , stopuntil , wait , or sleep(true, false) .

Instead, you can also click Stop on Wakeup on the Debugger Ribbon Tab .

<!-- image -->

<!-- image -->

**On Step Into [submenu]**

Opens a submenu on which you select into which parts of the source code the Method Debugger steps when debugging a Method .

<!-- image -->

**Step into Controls**

The command Step into Controls steps into other call chains to debug the executed Method . Such a call chain can either be a control or a woken up suspended Method , the instruction @.move could, for example, activate an Entrance Control .

**Step into Formulas**

The command Step into Formulas steps into other formulas to debug the executed Method . The instruction print table[1,1] could, for example, compute a formula which is located in this cell.

**Step into Encrypted Methods**

The command Step into Encrypted Methods sets if the command Step Into ( F11 ) stops in encrypted Methods or not.

- By default Step into Encrypted Methods is deactivated, meaning that the command Step Into does not stop in encrypted Methods .
- If you activate Step into Encrypted Methods , Step Into also stops in encrypted Methods . The Method-Debugger then shows the message The source code is encrypted instead of the source code as such.

**Ignore**

**Ignore**

Opens a submenu on which you can select which types of events the Method Debugger ignores when executing a Method .

<!-- image -->

**Ignore Breakpoints**

The command Ignore Breakpoints ignores the user-defined breakpoints you set with the commands Toggle Class Breakpoint and Toggle Instance Breakpoint .

Instead, you can also click Ignore Breakpoints

**SimTalk**

**ignoreBreakpoints**

Ignore Error Handlers

The command Ignore Error Handlers does not execute error handling methods if a runtime error in a Method occurs while it is being executed.

Instead, Plant Simulation opens the Method Debugger at the position in the source code at which the runtime error occurred.

Instead, you can also click Ignore Error Handlers

**SimTalk**

ignoreBreakpoints [SimTalk]

<!-- image -->

<!-- image -->

**Ignore Errors**

The command Ignore Errors stops the simulation after an error occurred in the current Method . Plant Simulation opens the Method Debugger with the Method containing the error and highlights the line containing the error in red.

**Note**

The simulation might continue if additional events are contained in the Event List in the EventController . This way you can continue working, although your model contains methods with faulty source code.

If an error occurs, Plant Simulation shows an error message in the status bar. It contains a description of the error, the Method , the line number of the error, and the active call chain

Instead, you can also click Ignore Errors

**SimTalk**

**setErrorStop [SimTalk]**

Ignore Errors in Formulas

The command Ignore Errors in Formulas prevents opening the Method Debugger when a runtime error occurs in a formula.

Instead, you can also click Ignore Errors in Formulas on the Debugger Ribbon Tab .

**Step Over**

Executes the source code of the Method one line at a time. Method execution stops before the next line of source code.

Other Methods that are being called in that line of the source code are not loaded into the Method Debugger .

<!-- image -->

.

<!-- image -->

<!-- image -->

on the Debugger Ribbon Tab .

The Method Debugger shows the elapsed time when you execute one or several instructions in a Method with the commands Step Over , Step Into [Method] , Step Out , or Run to Cursor and if executing the instructions takes 10 milliseconds or longer.

<!-- image -->

**Video on YouTube**

[https://youtu.be/pbOQD0p4hO4?si=P0Frai1pltBZLxAD&amp;t=614](https://youtu.be/pbOQD0p4hO4?si=P0Frai1pltBZLxAD&t=614)

**Step Into [Method]**

Executes one line of the source code of the debugged Method at a time.

If the line happens to call other methods, Plant Simulation loads this Method into the Method Debugger as well. Method execution stops before the next line in the called Method .

The command Step Into does not jump into encrypted Methods . If the next instruction is the call of an encrypted Method , the command Step Into behaves like the command Step Over , meaning that it executes the source code of the Method line by line.

<!-- image -->

**Note**

Step Into and Step Over do not differ if the next line of the source code to be executed does not contain a method call.

The Method Debugger shows the elapsed time when you execute one or several instructions in a Method with the commands Step Over , Step Into , Step Out , or Run to Cursor and if executing the instructions takes 10 milliseconds or longer.

<!-- image -->

**Video on YouTube**

[https://youtu.be/5t-wLNmKpbU?si=T8hXaB\_8xak8P6Rv&amp;t=453](https://youtu.be/5t-wLNmKpbU?si=T8hXaB_8xak8P6Rv&t=453)

**Step Out**

Finishes executing the current Method and steps out of it. It then stops at the next statement of the calling Method .

<!-- image -->

The Method Debugger shows the elapsed time when you execute one or several instructions in a Method with the commands Step Over , Step Into [Method] , Step Out , or Run to Cursor and if executing the instructions takes 10 milliseconds or longer.

<!-- image -->

**Video on YouTube**

[https://youtu.be/5t-wLNmKpbU?si=T8hXaB\_8xak8P6Rv&amp;t=453](https://youtu.be/5t-wLNmKpbU?si=T8hXaB_8xak8P6Rv&t=453)

**Continue [method execution]**

Continues executing the active Method .

<!-- image -->

**Run to Cursor**

Continues executing the Method until it reaches the statement at which the cursor is located.

The Method Debugger shows the elapsed time if you execute one or several instructions in a Method with the commands Step Over , Step Into [Method] , Step Out , or Run to Cursor and if executing the instructions takes 10 milliseconds or longer.

<!-- image -->

**Set Next Statement**

Sets the next statement that is going to be executed.

Click Yes in the dialog that opens to continue executing the current Method in the line in which the cursor is located.

Click No if you do not want this and to return to the current position of the cursor.

Let us illustrate this with an example: Suppose a Method is caught in an endless loop. To get out of this, hold down the Shift+Ctrl+Alt keys to stop method execution, and set the cursor outside of the loop.

Then, press Ctrl+F10 to get out of the loop and press F5 to continue executing the Method .

<!-- image -->

**Return From Current Call Chain**

Terminates the entire call chain which was invoked to start the current Method . The simulation run will continue afterward.

**Terminate Simulation**

**Terminate Simulation**

Terminates all call chains, i.e., the current and all other call chains pointing to waiting methods, and stops the simulation.

<!-- image -->

**Restart Simulation**

Starts the simulation again after you stopped it.

Restart Simulation does the same as clicking Reset Simulation and then clicking Start/Stop Simulation in the EventController does, i.e., it terminates the active simulation run and resets and starts the simulation again.

**Class Breakpoint**

Inserts a breakpoint into the class of the source code or removes it from it.

The command is described under Toggle Class Breakpoint .

<!-- image -->

.

**Instance Breakpoint**

Adds an instance breakpoint to this instance of the source code or deletes it.

Instance Breakpoint Command

The command is described under Toggle Instance Breakpoint .

<!-- image -->

To insert an instance breakpoint, you can also click

<!-- image -->

Breakpoint Active [Debug menu]

Activates or deactivates the selected breakpoint.

**See also**

Tools ribbon tab &gt; Manage Breakpoints

Breakpoint Active [Debug menu]

Breakpoint Active [context menu]

Breakpoint Settings [context menu]

Working in the Method Window

Breakpoint Settings

Breakpoint Settings [Debug menu]

Opens the dialog Breakpoint in which you can set a Start time and a Condition for the breakpoint.

.

on the Toolbar of the Method Debugger

**Active**

To activate the breakpoint, select this.

To deactivate the breakpoint, clear the check box. Plant Simulation then does not stop at this breakpoint anymore.

**Start Time**

Type in the Start time at which the breakpoint is going to be activated. Plant Simulation only stops if the EventController has reached or exceeded that point in time.

**Condition**

Type in the Condition which Plant Simulation evaluates each time when the breakpoint is reached. Plant Simulation only stops if the condition is fulfilled.

**See also**

The Dialog Box Breakpoint

&gt; Breakpoint Active [Debug menu]

Tools ribbon tab &gt; Manage Breakpoints

Breakpoint Active [context menu]

Breakpoint Settings [context menu]

Working in the Method Window

<!-- image -->

**Next Breakpoint [Debug menu]**

Goes to the next breakpoint, be it a class breakpoint or an instance breakpoint.

See also

**Next Breakpoint [Tools ribbon]**

Previous Breakpoint [Debug menu]

Goes to the previous breakpoint be it a class breakpoint or an instance breakpoint.

See also

**Previous Breakpoint [Tools ribbon]**

**Delete Class Breakpoints**

Deletes all breakpoints that you inserted with the command Toggle Class Breakpoint of the Method and its class.

See also

**Toggle Class Breakpoint**

**Delete Instance Breakpoints**

Deletes all breakpoints that you inserted with the command Toggle Instance Breakpoint of the Method in the Debugger window.

See also

**Toggle Instance Breakpoint**

**Delete All Breakpoints [Debug menu]**

Deletes all class breakpoints and all instance breakpoints you have set.

To delete all breakpoints, you can also click

<!-- image -->

<!-- image -->

See also

clearAllBreakpoints [SimTalk]

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

on the Toolbar of the Method Debugger

<!-- image -->

<!-- image -->

.

**Delete Breakpoints in All Methods**

Delete Breakpoints in All Methods

Deletes all breakpoints in all Methods .

To delete all breakpoints in all methods, you can also select Delete All Breakpoints [Debugger ribbon] on the Toolbar of the Method Debugger .

**SimTalk**

clearAllBreakpoints [SimTalk]

Watch Window [Debug menu]

Opens the Watch Window , which shows information about the executed source code.

See also

Watch Window [described]

View Menu

View Menu [Method]

The View Menu provides various commands.

Show Line Numbers [Tools ribbon]

Syntax-controlled Indentation [Tools ribbon]

MUs and States [Method Debugger]

MUs and States [Method Debugger]

Switches the animation of mobile units and icons temporarily on or off. The previous setting is restored after closing the Debugger.

Plant Simulation restores the original state as soon as you close the Debugger window .

<!-- image -->

Instead, you can also click on the Toolbar of the Method Debugger .

**See also**

MUs and States [Home ribbon]

Toolbar of the Method Debugger

**Tools Menu**

**Tools Menu**

The Tools Menu provides commands to access its functions.

| Edit Controls           | 3D             |
|-------------------------|----------------|
| Edit Observers          | Rename         |
| User-defined Attributes | Decrypt Method |

See also

**User-defined Attributes [Method Debugger]**

Opens a dialog in which you can add new user-defined attributes to the Method or in which you can edit and delete existing user-defined attributes .

Click New to open the dialog User-defined Attributes [general description] .

**Rename [Method]**

Opens the dialog Rename . Type in another name and another label for the Method .

###### Help Menu [Method Debugger]

The Help Menu provides commands to access its functions.

**Help on Debugger**

The command Help on Debugger opens the help topic pertaining to the Method Debugger .

**Help on Word**

The command Help on Word or F1 open help topic for the word over which the input cursor is located.

This way you can quickly and easily get help for an instruction, for a built-in attribute or for a built-in method.

##### Context Menu of the Method Debugger

Context Menu of the Method Debugger

Context Menu of the Method Debugger

The context menu of the Method Debugger provides these menu commands:

| Breakpoint Active          | Open Object   |
|----------------------------|---------------|
| Breakpoint Settings        | Show Object   |
| Toggle Class Breakpoint    | Cut           |
| Toggle Instance Breakpoint | Copy          |
| Run to Cursor              | Paste         |
| Set Next Statement         | Delete        |

**See also**

**Context Menu of the Method**

Breakpoint Active [context menu]

To activate or deactivate the selected breakpoint, select Breakpoint Active .

**See also**

Debugger ribbon tab &gt; Manage Breakpoints

Breakpoint Active [Debug menu]

Breakpoint Settings [Debug menu]

Breakpoint Settings [context menu]

To open the dialog Breakpoint in which you can set a Start time and a Condition for the breakpoint, select Breakpoint Settings .

**See also**

The Dialog Box Breakpoint

Debugger ribbon tab &gt; Manage Breakpoints

Breakpoint Active [Debug menu]

**Breakpoint Settings [Debug menu]**

###### Open Object [Method Debugger]

To open the object above whose instruction you moved the mouse in the source code, select Open Object .

<!-- image -->

Show Object [Method Debugger]

To open the Frame in which the object is inserted and select the object in this Frame , right-click it and select Show Object .

If the selected object references another object, for example with a Variable , the command shows the referenced object, not the referencing object!

The context menu of the Variable in the Method Debugger also provides the command Show Object .

<!-- image -->

**Cut [in Method Debugger]**

###### Cut [in Method Debugger]

To cut the selected text and place it on the clipboard, select Cut .

Copy [in Method Debugger]

To copy the selected text to the clipboard, select Copy .

###### Paste [in Method Debugger]

To paste the contents of the clipboard at the cursor position, select Paste .

###### Delete [in Method Debugger]

To delete the selected text, select Delete .

#### Methods of the Method

**\_Methods of the Method**

Accessing a Method automatically executes its source code. If you want to access built-in methods , read-only attributes , or attributes , you have to use the reference operator &amp; .

The object Method provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

**Note**

You can only access the methods of the object Method , which refer to the object itself, via the reference operator &amp; . Without the &amp; operator the method will be applied to the contents of the Method .

To view all of the methods , read-only attributes , and attributes of the Method , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax of the individual methods might look like this:

```simtalk
&Method.execute([Argument1:any, ...[, @:object:=@, ?:object:=self]])
```

The signature of the method, consisting of the anonymous identifier &amp;, the name of the method, and the data type of the parameter, which is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter

If the method has a return value, the signature shows its data type after the arrow -&gt;.

**\_Methods of the Method**

##### checkArguments [SimTalk]

Checks if the parameters passed to the Method designated by the reference operator &lt;&amp;&gt; have a compatible data type.

Remarks

Use checkArguments to make sure that values, which you or a user of a model you create enters into a dialog, may be passed to Methods .

Type

Method

Syntax

< & >Method.checkArguments([Argument1:any, ...])´

Parameter

The optional parameters Argument of data type any designate the arguments that are to be checked.

Example

&amp;MyMethod.checkArguments(42,void)

decrypt [SimTalk]

decrypt [SimTalk]

Decrypts the Method designated by the reference operator &lt;&amp;&gt; which you or somebody else encrypted.

Type

Method

Syntax

```simtalk
< & >Method.decrypt(Key:string) → boolean
```

Parameter

The parameter Key of data type string designates the password.

Return Value

The return value has the data type boolean .

Example

&amp;MyMethod.decrypt("zTrqYa8%e")

SimTalk

encrypt [SimTalk]

See also

Decrypt Method

##### deleteMethCall [SimTalk]

Deletes all scheduled calls of the Method designated by the reference operator &lt;&amp;&gt; in the EventController .

Remarks

Use deleteMethCall to delete calls you do not need any longer.

Type

Method

Syntax

&lt; &amp; &gt;Method.deleteMethCall

**Example**

&amp;MyMethod.deleteMethCall // deletes all scheduled method calls

See also

executeIn [SimTalk]

encrypt [SimTalk]

encrypt [SimTalk]

Encrypts the source code of the Method designated by the reference operator &lt;&amp;&gt;.

Type

Method

Syntax

```simtalk
< & >Method.encrypt(Key:string) → boolean
```

Parameter

The parameter Key of data type string designates the password.

Return Value

The return value has the data type boolean .

Example

&amp;MyMethod.encrypt("zTrqYa8%e")

SimTalk

decrypt [SimTalk]

See also

Encrypt Method

##### execute [SimTalk] - Method

Runs the Method designated by the reference operator &lt;&amp;&gt; as a subroutine.

Remarks

The execution of the calling Method will be interrupted until the called Method is finished.

The method execute is especially handy if the path to a Method is stored in a Variable of data type object .

Type

Method

Syntax

```simtalk
< & >Method.execute([Argument1:any, ... ][, @:object=@, ?:object=self])
```

**Parameters**

The optional parameters Argument of data type any designate the arguments which are to be executed.

If you type in two additional optional parameters of data type object , then the parameter @ is assigned to the anonymous identifier @ and the parameter ? is assigned self .

**Example**

```simtalk
Variable := &MyMethod1      // variable is of data type object Variable.execute            // executes MyMethod1 &MyMethod2.execute("abc")   // executes myMethod2 // that expects 1 parameter // of data type string
self.execute(n+1)           // calls a method recursively
```

**Note**

You can call the method execute from Python . In this case execute will be executed like a formula. Therefore you cannot move or delete MUs in the Method , and you cannot use a wait-instruction , a waituntil-instruction , or a stopuntil-instruction .

In addition, Plant Simulation does not show the tab Expressions of the Method Debugger .

**call myMethod from Python res = current.myMethod.execute() print(res)**

**See also Run [button] - Method Tab Expressions [Watch window]**

##### executeIn [SimTalk]

Calls the Method or the user-defined attribute of data type method designated by the reference operator &lt;&amp;&gt; after the specified number of seconds of simulation time has elapsed.

**Remarks**

Plant Simulation enters a MethCall event into the list of scheduled events in the EventController at the simulation time which is the current simulation time plus the time you passed as the parameter CallAt . Since the Method will be called at some time in the future, the parameter CallAt must be greater than or equal to 0. If events are already scheduled at this time, the MethCall will be appended at the end of the existing simultaneous events.

In the called Method the anonymous identifier ? references the caller, i.e., the Method which contained the Method executeIn .

If the caller is a user-defined attribute of data type method , it references the location of this user-defined attribute . The anonymous identifier @ references the EventController .

Type

Method

Syntax

< & >Method.executeIn(CallAt:time[, Argument1:any, ...]) < & >Method.executeIn(CallAt:dateTime[, Argument1:any, ...])

**Parameters**

- The parameter CallAt of data type time designates the time in seconds after which the Method will be called. Instead, you can also pass a value of data type dateTime . Then the Method will be called at the specified point in time.
- The following optional parameters (Argument1, ...) are passed to the Method when it is being called.

**Example**

&MyMethod1.executeIn(23.5) // throttle the engine in 5 seconds to 85 percent &ThrottleEngine.executeIn(5, 0.85) // New year's day 2025 midnight, year-month-day notation &MyMethod2.executeIn(str_to_date("2025/12/31")) // New year's day 2025 midnight, day-month-year notation &MyMethod2.executeIn(str_to_date("31.12.2025")) // call the method with a local variable reference, passing two parameters

```simtalk
to the method
var obj: object := &MyMethod3
obj.executeIn(4, "my string", true)
```

See also

deleteMethCall [SimTalk]

executeNewCallChain [SimTalk]

List of Events

Video on YouTube

[https://youtu.be/5t-wLNmKpbU?si=mzWCkc2Y2B1VGtIF&amp;t=1121](https://youtu.be/5t-wLNmKpbU?si=mzWCkc2Y2B1VGtIF&t=1121)

##### executeNewCallChain [SimTalk]

Runs the Method designated by the reference operator &lt;&amp;&gt; after Plant Simulation has processed all active call chains.

Remarks

The effect of &amp;Method.executeNewCallChain is similar to &amp;Method.executeIn(0) . Let's say you schedule a method in a reset method with executeNewCallChain , then the scheduled method will only be executed after all already scheduled methods have been finished.

**Note**

If executing a method triggers controls, Plant Simulation interrupts the method and runs the controls. Let's say that the instruction @.move triggers an Entrance Control and an Importer Request Control . The interrupted method will only be continued, after these controls have been processed all the way. If one of the controls schedules a new method with executeNewCallChain , this method will be executed after controls have been executed, but before interrupted method will be continued.

The method executeNewCallChain behaves differently than the method executeIn(0) . The difference is that executeIn requires an EventController and that a method, that was scheduled with &amp;Method.executeIn(0) , will only be executed after the already scheduled simultaneous events.

In the called method the anonymous identifier ? references the caller, i. e., the method, which contained the method executeNewCallChain .

If the caller is a user-defined attribute of data type method , ? references the location of the user-defined attribute .

Type

Method

Syntax

```simtalk
< & >Method.executeNewCallChain([Argument1:any, ...] [,@:object:=@, ?:object:=self])
```

Parameter

The optional parameters Argument1 of data type any and following designate the arguments which are to be executed.

If you enter two additional optional parameters of data type object , then the parameter @ is assigned to the anonymous identifier @ and the parameter ? is assigned self .

**Example**

```simtalk
var o : object := .Models.Model.&MyMethodWithoutParameters
o.executeNewCallChain
```

**See also**

&amp; [SimTalk] - reference operator

executeIn [SimTalk]

##### hasSyntaxError [SimTalk]

Returns if the source code of the Method designated by the reference operator &lt;&amp;&gt; has syntax errors.

Remarks

The method also applies to user-defined attributes of type method .

Type

Method

Syntax

```simtalk
< & >Method.HasSyntaxError([byref ErrorMessage:string])
-> boolean
```

**Parameter**

The optional parameter ErrorMessage of data type string designates a local variable to which Plant Simulation assigns an error message if the Method contains a syntax error.

If the Method does not contain a syntax error, Plant Simulation assigns an empty string ("") to the local variable.

**Return Value**

The return value has the data type boolean .

**Example**

```simtalk
var NewSourceCode: string := prompt  -- user input &MyMethod.Program := NewSourceCode   -- assign new source code if &MyMethod.HasSyntaxError print "syntax error"
else MyMethod   -- call the Method and execute the new source code end
```

##### load [SimTalk] - source code

load [SimTalk] - source code

Loads the contents of a text file in ASCII format as source code into the Method designated by the reference operator &lt;&amp;&gt;.

Type

Method

Syntax

```simtalk
< & >Method.load(FileName:string) → boolean
```

Parameter

The parameter FileName of data type string designates the name of the text file.

Return Value

The return value has the data type boolean .

Example

&MyMethod.load("C:\Users\Ralf\sourcecode.txt")

See also

Import from File

##### Read-Only Attributes of the Method

Read-Only Attributes of the Method

The Method provides:

- The read-only attribute Encrypted [SimTalk] .
- The read-only attribute NumInExecution [SimTalk] .
- The \_Read-Only Attributes of All Objects .

**Note**

You can only access the read-only attributes of the object Method , which refer to the object itself, via the reference operator &amp; .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print &amp;Method.Encrypted

**Encrypted [SimTalk]**

##### Encrypted [SimTalk]

Returns if the Method or the user-defined attribute of data type method designated by the reference operator &lt;&amp;&gt; is encrypted (true) or not (false).

Type

Read-only attribute

Syntax

&lt; &amp; &gt;Method.Encrypted → boolean

Return Value

The return value has the data type boolean .

Example

print &amp;MyMethod.Encrypted

##### NumInExecution [SimTalk]

Returns how often the Method designated by the reference operator &lt;&amp;&gt; is being executed at the moment.

Type

Read-only attribute

Syntax

&lt; &amp; &gt;Method.NumInExecution → integer

Return Value

The return value has the data type integer .

Example

print &amp;MyMethod.NumInExecution

**Attributes of the Method**

\_Attributes of the Method

The object Method provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

**Note**

You can only access the attributes of the object Method , which refer to the object itself, via the reference operator &amp; . Without the &amp; operator the attribute will be applied to the contents of the Method .

To view all of the methods , read-only attributes , and attributes of the Method , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To access the Method , use the reference operator or the anonymous identifier self .

**Example**

```simtalk
&MyMethod.Program := "->real return 0.0"
self.Program := "->real return 0.0"
```

// next call with the changed instructions

##### Program [SimTalk]

Designates the source code which is passed to the Method designated by the reference operator &lt;&amp;&gt;.

Remarks

The assigned source code is executed when the Method is called the next time.

Type

Attribute

Syntax

```simtalk
< & >Method.Program:string
```

**Assignment Value**

You can assign a value of data type string .

**Examples**

```simtalk
&MyMethod.Program := "->real return 0.0"
self.Program := "->real return 0.0" // next call with the changed instructions
var bInherit:boolean // checks if the attribute 'Programm' is activated or
not getAttribute("Program", bInherit)
print bInherit
```

##### RandomSeed [SimTalk] - Method/User-defined Attribute

Sets the random number stream of the Method designated by the reference operator &lt;&amp;&gt; or of the user-defined attribute of data type Method or RandTime .

Remarks

As you are used to from the material flow objects, Plant Simulation automatically assigns the random number seed value when you insert an object, so that each object has its own random number seed value.

If you call one of the distribution functions in a Method , the first parameter, which specifies the random number stream, is optional. If you do not specify the stream, Plant Simulation uses the random number stream of the Method or of the user-defined attribute of data type method .

This affects the following distribution functions :

z\_beta, z\_binomial, z\_cEmp, dEmp, z\_emp, z\_erlang, z\_frechet, z\_gamma, z\_geom, z\_gumbel, z\_hypgeom, z\_laplace, z\_logistic, z\_logLogistic z\_lognorm, z\_negexp, z\_normal, z\_paraLogistic, z\_pareto, z\_poisson, z\_triangle, z\_uniform, and z\_weibull.

You can still call the distribution functions with the parameter for the random number stream as you did in previous versions. For formulas it is required, as formulas never use the random number stream of the surrounding object.

The random number sequences, which are generated by the random number streams of the Methods , differ from the random number sequences of the global random number streams, whose seed values you can set under File &gt; Options &gt; Random Number Seed Values even if they have the same random number seed value.

Plant Simulation keeps a common seed value in the object. Plant Simulation automatically assigns the random number value when inserting an object, but only if the object can create random numbers. This is then the case when the object itself can create random numbers, for example a Station for its Processing Time , or when the object has a user-defined attribute of data type Method or RandTime . If both is not the case, Plant Simulation assigns the value 0 to the attribute RandomSeed when inserting the object. If the value of the attribute RandomSeed is 0, the attribute will not be shown in the window Show Attributes and Methods and will not be written to the folder model. When you create a user-defined attribute of data type Method or RandTime for such an object, Plant Simulation sets a random number value automatically as well.

Type

Attribute

Syntax

<!-- image -->

&lt; &amp; &gt;Method.RandomSeed:integer

**Assignment Value**

You can assign a value of data type integer .

**Examples**

&amp;Method1.RandomSeed := 1313

DataTable.RandomSeed := 101

**See also**

Method [SimTalk] - data type

Formula [distribution]

Distribution Functions, z\_ functions

Random Number Seed Values

##### UsingNewSyntax [SimTalk]

Activates ( true ) SimTalk 2.0 syntax for the Method designated by the reference operator &lt;&amp;&gt; or deactivates it ( false ).

Remarks

Note

Clicking for an existing Method , whose source code you created in SimTalk 1.0 notation , automatically converts that source code to source code in the correct SimTalk 2.0 notation .

<!-- image -->

If UsingNewSyntax is active, you have to enter the source code into Methods in the improved, abbreviated SimTalk 2.0 notation .

If you want to use SimTalk 2.0 syntax for all new Methods which you are going to program, activate UsingNewSyntax in the Method class in the Class Library .

Plant Simulation writes the setting UsingNewSyntax to the model file.

If UsingNewSyntax is deactivated, you have to enter the source code into Methods using SimTalk 1.0 notation.

Type

Attribute

Syntax

<!-- image -->

&lt; &amp; &gt;Method.UsingNewSyntax:boolean

Assignment Value

You can assign a value of data type boolean .

Example

&amp;Method1.UsingNewSyntax := true See also New Syntax [command]

SimTalk 2.0 and SimTalk 1.0 Compared

A Quick Tour Through SimTalk 2.0

General Access to SimTalk

#### PythonModule

