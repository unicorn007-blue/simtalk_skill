### Frame

#### Frame [object]

Use the Frame as the container for creating your simulation models. It might, for example, represent a complex machine, a part of an plant, or the entire plant.

Icon

<!-- image -->

Description

The Frame serves for grouping objects and for building hierarchically structured models by inserting any of the built-in objects and any objects you design. The Frame is the principal object facilitating hierarchic modeling. The Frame represents the entire plant, while you can model subsections of the plant in Frames of their own, which you insert into the Frame representing the entire plant.

To show a tooltip with information about the Frame or a sub-Frame , hover with the mouse over it.

<!-- image -->

<!-- image -->

Model transitions from Frame to Frame with the object Interface . Connect objects within the

<!-- image -->

Frame and Frames with the object Connector . When you connect Frames with Connectors , Plant Simulation opens the dialog Select Interface in which you have to select an Interface , which you inserted into the Frame . A Frame is unconnected if one of its Interfaces is not connected to the outside.

**Select Interface**

**The dialog Select Interface :**

- Highlights the Interface that has the least number of connections. In our example the Interface named Exit has 1 out of an unlimited number of possible connections.
- Lists in brackets how many connections out of the number you defined the Interface has. In our example the Interface named Max3 has 1 out of the 3 possible connections.
- Marks the Interface , which has reached its maximum number of external connections with an asterisk * . In our example the Interface named Only1 has reached 1 out of 1 possible connections.

**Note**

We modeled most of the Tools , such as the TransferStation and the ExperimentManager , and some of the objects in the Object Libraries as application objects in a Frame . For this reason F1 opens the help for the Frame .

To open help for the tool, select Help &gt; Help on Object in its dialog.

You can show a screenshot of the contents of a Frame in an HtmlReport , compare Display a Frame .

When you insert a new Frame into your 3D Only model , it contains temporary (internal) deco graphics labeled Under Construction to represent it outwards as long as you do not insert any other object into the Frame . This is because the default (external) graphics are set to be invisible.

<!-- image -->

Add the Object to the Simulation Model

To add the Frame to your simulation model, click MaterialFlow &gt; Frame on the Home ribbon tab.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

The Frame Window

States of the Frame

Show the Contents of a Frame in the Class Library

Working with the Frame

Insert an Object from the Toolbox

Insert an Object from the Class Library

#### The Frame Window

The Frame Window

The Frame Window provides access to the most important functions you need for creating you simulation model.

The Frame window provides the View Ribbon Tab , the Icons Ribbon Tab , the Vector Graphics Ribbon Tab , and the System Menu . These provide access to the most important functions you need for creating you simulation model.

The Context Menu of the Frame Itself provides commands pertaining to the Frame . To edit the 3D properties of the Frame in the 3D model, press the spacebar . Change the settings in the dialog Edit 3D Properties .

The Context Menu of the Selected Object in the Frame provides commands pertaining to that object. You can edit the simulation properties of the object there. To edit the 3D properties of the selected object in the 3D model, press the spacebar . Change the settings in the dialog Edit 3D Properties .

See also

Work with Objects in the Frame Window

Add a Graphic and a Color to the Background or the Icon of the Frame

Draw Vector Graphics or Text onto the Background of the Frame

Drag-and-Drop While Modeling

setXYWH [SimTalk] , getXYWH [SimTalk]

RootFrame [SimTalk]

setPosition [SimTalk]

##### Drag-and-Drop While Modeling

Drag-and-drop in the Frame while modeling performs a number of actions.

You can use drag-and-drop while modeling in the Frame . The row Class Library -Class Library -objectCtrl in the second row of the table means: Dragging an object from the Class Library from one location to another location in the Class Library while holding Ctrl down copies the object to that location.

| To do this                                                                                              | Drag from         | To            | Type                                 | Acc eler ator   |
|---------------------------------------------------------------------------------------------------------|-------------------|---------------|--------------------------------------|-----------------|
| Move the object                                                                                         | Class Library     | Class Library | object                               | Shif t          |
| Copy the object                                                                                         | Class Library     | Class Library | object                               | Ctrl            |
| Derive the object                                                                                       | Class Library     | Class Library | object                               | Ctrl +Shi ft    |
| Instantiate the object                                                                                  | Class Library     | Frame         | object                               | -               |
| Move the object (makes a class out of the instance)                                                     | Frame             | Class Library | object                               | -               |
| Copy the object                                                                                         | Frame             | Class Library | object                               | Ctrl            |
| Load a graphics file (.GIF, .BMP, .PPM, .PPM RAW, .DXF, or .DWG) as the background graphic of the Frame | Windows Explorer  | Frame         | file                                 | -               |
| Insert the selected object repeatedly                                                                   | Class Library     | Frame         | object                               | Shif t          |
| Execute a Method , which expects a single parameter of data type object with this object as parameter   | Object from Frame | Method        | single parameter of data type object | -               |

**System Menu of the Frame**

##### System Menu of the Frame

The system menu shows commands with which you can manipulate or close the Frame window.

**Note**

Plant Simulation displays the system menu in the language of Windows that is installed on your computer.

<!-- image -->

###### System Menu of the Frame

**Use Left Area**

###### Use Left Area

Uses the left part of the usable area of the MDI window in which Plant Simulation shows the object windows .

In the figure below this is the entire colored area to the right of the Frame named Model .

<!-- image -->

**See also**

**Object Windows**

###### Use Right Area

Uses the right part of the usable area of the MDI window in which Plant Simulation shows the object windows .

See also

Object Windows

**Restore**

###### Restore

Restores the Plant Simulation window to normal size.

###### Move [window position]

Changes the window position of the Frame window in the Plant Simulation window.

###### Size [window position]

Size [window position]

Changes the size of the Frame window in the Plant Simulation window.

###### Minimize

Reduces the size of the Frame window to an icon in the task bar of the Plant Simulation window.

**Maximize**

###### Maximize

Enlarges the size of the Frame window to fill the entire Plant Simulation window.

When the Frame window is maximized, Plant Simulation adds the button combination Minimize ,

Maximize , Close that is otherwise located in the title bar of the window, to the Ribbon Bar .

###### Close [Frame window]

Closes the Frame window.

###### Frame Ribbon Tab

##### Frame Ribbon Tab

The Frame ribbon tab provides commands to access the functions of the Frame .

<!-- image -->

<!-- image -->

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Frame .

###### Find Object [button]

Opens the dialog Find Object .

<!-- image -->

To search for any object in the Frame window, you can also click in the Frame window and start typing its name. Plant Simulation then finds and selects the object.

See also

Find Object [context menu]

Finding Objects and Text in Your Simulation Model

###### Incremental Find Object

Clicking the button and starting to type the name of the object you want to find finds and highlights that object in the opened Frame window .

<!-- image -->

Microsoft describes Incremental Find Object as "a type of search that looks for a string in an automatic and progressive way. As the user types a string, possible matches are found, thus enabling the user to stop typing the complete string as soon as the right match is found."

Plant Simulation shows the characters you type in the status bar . You can type all characters which are allowed for object names. As we do not distinguish upper- or lower-casing in object names, you can start typing with lower-case letters.

As soon as Plant Simulation finds an object that matches these characters, it selects that object and zooms to it in the 3D scene. If you want to return to the last active scene before the search, press Backspace .

If Incremental Find Object did not find and select the object you wanted to find, it returns to the scene as it was before you started searching.

You can use these keys to control the functionality of Incremental Find Object :

- Press Backspace to delete the last character you typed. Then, type in the correct character.
- Press Tab to find the next matching object of the characters you typed. If no additional object is found, Plant Simulation selects the first object you wanted to find again and shows it. It also plays a signal tone.
- When cycling through the object that match the search, Plant Simulation shows the names of the objects in the status bar instead of the search pattern.
- Press Esc to terminate Incremental Find Object . Plant Simulation retains the current selection of the object it found.
- Press Return to terminate Incremental Find Object and execute the default operation of Return for the object, for example open the simulation properties dialog.

**Note**

To find the name of an object in an open folder in the Class Library , press Ctrl+I and start typing.

###### Show Unconnected Objects

Highlights those objects in the open Frame window that have unconnected entrance and exit points, i.e., which are not connected to any other object with a Connector .

<!-- image -->

A Frame counts as unconnected if one of its Interfaces is not connected to the outside.

###### Select Shift Calendar

Sets the ShiftCalendar which contains the data of the shifts in your installation and controls during which shifts the Frame works.

<!-- image -->

The command opens the dialog Select ShiftCalendar .

<!-- image -->

Click this and select the ShiftCalendar in the dialog Select Object or enter the name of the ShiftCalendar .

Note

The ShiftCalendar can change the states paused and unplanned of the Frame .

SimTalk

ShiftCalendarObject

Unplanned [SimTalk]

See also

Unplanned Control

Configure User-defined Ribbon Tab

Configure User-defined Ribbon Tab

Creates a user-defined ribbon tab in the selected Frame with commands, which you frequently use.

<!-- image -->

Plant Simulation adds the user-defined ribbon tab to the predefined ribbon tabs of the Frame for which you defined it. In the example below we defined a user-defined ribbon tab with the name My Ribbon Tab . Plant Simulation shows it on the tab User .

<!-- image -->

When a user-defined ribbon tab exists, the button on the Frame ribbon tab is highlighted.

<!-- image -->

You can:

- Add an Icon to a Ribbon Command
- Create a Ribbon Group
- Dynamically Add a Ribbon Command
- Add a Command Separator
- Create an Access Key

**Note**

To create a ribbon tab in a Frame , which you inserted into another Frame , deactivate the command Inherit first. Otherwise, this Frame inherits its user-defined ribbon tab from its origin.

**See also**

Create Your Own Ribbon Tab/Context Menu in the Frame Title [user-defined ribbon tab]

Type in the Title of the user-defined ribbon tab which Plant Simulation uses to show the ribbon tab to the right of the predefined ribbon tabs of the Frame .

<!-- image -->

We typed in My Ribbon Tab in our example.

<!-- image -->

**SimTalk**

UserMenuTitle [SimTalk]

**Active [check box] - user-defined ribbon tab**

To show and activate the user-defined ribbon tab , which you defined, to the right of the predefined ribbon tabs of the Frame , select this check box.

<!-- image -->

To deactivate and hide it, clear the check box.

**Note**

If the user-defined ribbon tab calls a Method , Plant Simulation assigns the anonymous identifier ? (question mark) to the respective Frame .

**SimTalk**

ShowUserMenu [SimTalk]

New [ribbon command]

New [ribbon command]

To add a New ribbon command to the ribbon tab you are configuring, click this button.

<!-- image -->

Plant Simulation then adds a row to the table in the dialog.

- Type in the Name of the ribbon command that the Frame window is to show. You can also click in the cell and select an item from the drop-down list and enter text.

<!-- image -->

- Type in the Method that the ribbon command is to execute in the Frame window.

Text to Display

Text to Display [user-defined ribbon tab]

Type in the name of the command that Plant Simulation shows on the user-defined ribbon tab in the Frame into the cells below Text to Display .

Then select or type in the name of the Method to Execute when you click the command into the cell to the right.

<!-- image -->

You can select the following in front a ribbon command or a group label:

- Select ?Formula to designate a formula that computes the text to be used as the label of a group or as the ribbon command.
- Select - Separator (hyphen) to insert a group separator. If the group separator has an attached command, the group shows its button in the right bottom corner.
- Select the # sign and no text after it to designate the end of the previous group and to start a new unnamed group.

· Select #Group Name to start a new ribbon group with the name you enter. Type in the name of or select a method that the ribbon command executes to add the ribbon launch button to the group in the Frame window. The button typically opens a dialog box or another element that is related to the group. We clicked and then Create Control .

<!-- image -->

Type in two or more hyphens --or two or more number signs ## to show them as they are.

- Select #GroupNameFormula to start a new ribbon group using a formula.

If one of the ribbon commands or group labels is dynamic as the result of computing a formula, the user-defined ribbon category gets updated each time it comes into the view. Thus, the user-defined ribbon tab will only be updated, if another tab was active before and the current tab was then activated.

Plant Simulation exchanges icons if dynamic ribbon commands or group labels change and selects an icon using one of the icon names matching rules described under Add an Icon to a Ribbon Command .

**You can:**

- Create a Ribbon Group
- Add an Icon to a Ribbon Command
- Dynamically Add a Ribbon Command
- Dynamically Add a Ribbon Command
- Create an Access Key

**SimTalk**

UserMenu [SimTalk]

**Create a Ribbon Group**

Type in or select the number sign # in front of the first command to start a ribbon group on the ribbon tab.

Ribbon groups group a number of related commands and are separated by long vertical lines between them.

<!-- image -->

In our example we typed in #Commands , #Dialogs , and #Online Help as ribbon groups.

<!-- image -->

Any text following the # is used as the name of this ribbon group. If you type in #Dialogs as Text to Display , the ribbon tab will show Dialogs preceded by a vertical line serving as a group separator.

If you just enter # and no text afterward, Plant Simulation considers this as the end of the previous group and starts a new group without a ribbon label.

The command can also consist of a formula, i.e., it can be dynamic. If a formula creates the Text to Display , Plant Simulation checks the text for line breaks. If line breaks exist, Plant Simulation splits the text and uses it as the:

- Name of the ribbon command
- Caption of the tooltip of the ribbon command
- Description of the ribbon command in the tooltip, provided you entered a description

**Compare this example:**

"Statistics Report\nShow the statistics report.\nGenerates the statistics report of the selected object and shows it."

Type in the Methods , which the commands call and execute, into the cells below Method to execute .

Back to Text to Display [user-defined ribbon tab]

**Add an Icon to a Ribbon Command**

Describes how to add an icon to a ribbon command.

To add an icon to a ribbon command, proceed as follows:

- Create a new object icon. Specify 16 by 16 pixels and/or 32 by 32 pixels as the size. Name the icon to match the label of the ribbon command, for example My Command 1 .
- Use these naming conventions for the icons:
- Use My Command 1\_16 or My Command 1\_32 for example to indicate the size of the icon. If you do not specify the size, Plant Simulation will find the icon, but will not document its desired usage in its name.
- Use ribbon , which is independent of the ribbon command label, and append the number of the command in the ribbon, for example ribbon1 .
- Plant Simulation resolves the icon name in this sequence:
1. Ribbon command label with appended size
2. Ribbon command label without appended size
3. Icon names which are independent of the label
- Plant Simulation will choose the size of the displayed icon based on available space:
1. If space is tight on the ribbon, it uses the 16 by 16 pixel icon.
2. If the ribbon has more space available, it uses the 32 x 32 pixel icon.

In our example we created three icons in our Frame named MyPlantAnytown . We typed in the same name as the text to display to which we want to add the icon: MyCommand1\_16 , My Command 2\_16 , and My Command 3\_16 . The suffix \_16 designates them as icons with a size of 16 by 16 pixels.

<!-- image -->

**Note**

If you use a formula for the label, Plant Simulation uses the result of this formula to search for the icon.

To prevent any problems with formula results as icon names, you can name ribbon command icons in a standardized way using the default name ribbon and appended the number of the command in the icon, for example ribbon1 .

If you do not type a Method to Execute into the text box next to Text to Display , Plant Simulation dims the icon. In our example we removed the Method to Method to the right of the command MyCommand1 :

<!-- image -->

Back to Text to Display [user-defined ribbon tab]

**Dynamically Add a Ribbon Command**

Select ?Formula and then type over Formula in the cell with the name of your formula to use this formula as a ribbon command.

<!-- image -->

When you type in ?Method1 for example, the method named Method1 will be called. The return value of this method has to be of data type string . This way you can toggle between different captions, for example between Activate and Deactivate and you can translate the commands into different languages. If the methods return an empty string "", Plant Simulation hides the respective command.

You can use any formula, even a method call with parameters, such as ?Method1(42) or a table access, such as ?MyDataTable[1,3] .

Back to Text to Display [user-defined ribbon tab]

**Add a Command Separator**

Type in or select - Separator followed by the category name as the Text to Display to insert a vertical separator between groups of ribbon commands.

<!-- image -->

Back to Text to Display [user-defined ribbon tab]

**Create an Access Key**

Type the ampersand character &amp; in front of a letter of a command on the ribbon tab to make this letter the access key (mnemonic key) on the user-defined ribbon tab .

Plant Simulation activates this command, when you press the Alt key and that letter.

If you do not type in the ampersand, Plant Simulation assigns an automatically numbered access key.

The built-in access keys take precedence over any access keys you define! This means that your access key does not work if it is already defined on one of the pre-defined ribbon tabs.

In our example we made the S in the command My Simple Dialog the access key. Holding down Alt , pressing the predefined keys U and T , and pressing the S key opens our simple dialog.

<!-- image -->

**Note**

You can only create access keys for menu items on a menu, not for dialog items in the dialog itself.

Back to Text to Display [user-defined ribbon tab]

**Method to Execute [user-defined ribbon tab]**

**Method to Execute [user-defined ribbon tab]**

Type in the name of the Method , which the Text to Display calls and executes, into the respective cell.

When Methods are called by the user-defined ribbon tab , the anonymous identifier ? (question mark) points to the Frame in which the selection was executed. Use this to selectively access objects in the respective Frame .

**Parameter**

If the method expects a parameter, Plant Simulation automatically passes it. The objects, which you selected in the Frame , are passed to this parameter, which has to be of data type list or an array of data type object .

<!-- image -->

**Example**

```simtalk
?.MyStation.proctime := str_to_time(prompt)
```

**SimTalk**

UserMenu [SimTalk]

See also

Text to Display [user-defined ribbon tab]

**Delete [ribbon command]**

To delete a command from the user-defined ribbon tab , select the respective row in the dialog and click this button.

<!-- image -->

<!-- image -->

**Inherit User-defined Ribbon Tab**

**Inherit User-defined Ribbon Tab**

Turns inheritance for a ribbon tab which you create in a Frame , which you inserted into another Frame on or off.

<!-- image -->

- When you turn it on , any Frame you derive from the active Frame will inherit the ribbon tab of its origin.
- When you turn it off it, you can define a ribbon tab that only applies to the active Frame , but will not be inherited.

**Context Menu User-defined Ribbon Tab/Context Menu**

###### Context Menu of the User-defined Ribbon Tab

The context menu of the user-defined ribbon tab and the user-defined context menu provides the commands listed in the table of contents to the left.

**Insert Row [user-defined ribbon tab]**

Inserts an empty row above the selected row in the table.

Hold down Shift and click Insert Row to insert an empty row below the selected row in the table.

<!-- image -->

**Delete Row [user-defined ribbon tab]**

**Delete Row [user-defined ribbon tab]**

Deletes the selected row from the table in the dialog.

<!-- image -->

**Cut Row [user-defined ribbon tab]**

Cuts the selected row from the table, converts the cut data to text, and places it on the clipboard.

Plant Simulation separates the two columns of the cut row with a tab stop. In the example below it looks like this:

<!-- image -->

**Copy Row [user-defined ribbon tab]**

Copies the selected row in the table, converts the copied data to text, and places it on the clipboard

Plant Simulation separates the two columns of the copied row with a tab stop. In the example below it looks like this:

<!-- image -->

**Paste Row [user-defined ribbon tab]**

Pastes the data of the row from the clipboard to the table in the dialog. While doing this Plant Simulation looks for line breaks and tabulators, separates the text accordingly, and pastes the text into the table.

To control where Plant Simulation pastes the row:

- Click in the row where you want to paste the row from the clipboard and select Paste Row to replace the current row and overwrite its contents. You can also paste the row from the clipboard at the end of the table without overwriting any content.
- Hold down Ctrl and select Paste Row to paste the row from the clipboard above the current row in the table. This does not overwrite existing data.
- Hold down Ctrl and Shift and select Paste Row to paste the row from the clipboard below the current row in the table. This does not overwrite existing data.

<!-- image -->

**Keyboard Shortcuts for User-defined Ribbon Tab/Context Menu**

The user-defined ribbon tab and the user-defined context menu provide these keyboard shortcuts:

| To do this                                                                                                                                             | Press                            |
|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| Copy the current row to the clipboard                                                                                                                  | Ctrl+C or Ctrl+Ins               |
| Cut the current row to the clipboard                                                                                                                   | Ctrl+X or Shift+Del              |
| Paste the contents of the clipboard, provided the format fits (tab-separated columns, line-break separated rows)                                       | Ctrl+V or Shift+Ins              |
| Insert the new row above the current row                                                                                                               | Ins/ Ctrl+ + or Ctrl+Num+        |
| Insert the new row below the current row                                                                                                               | Ctrl+Shift+ + or Ctrl+Shift+Num+ |
| Delete the selected row                                                                                                                                | Del                              |
| Edit the selected row                                                                                                                                  | F2                               |
| Open the Method Editor for the Method in the current row                                                                                               | Shift+F2                         |
| Open the drop-down list for selecting items in the column Text to display Open the context menu for selecting commands in the column Method to execute | F4                               |
| Create a user-defined method/control                                                                                                                   | Shift+F4                         |

Attributes of the User-defined Ribbon Tab

Attributes of the User-defined Ribbon Tab

The user-defined ribbon tab provides these attributes :

ShowUserMenu [SimTalk]

UserMenu [SimTalk]

UserMenuTitle [SimTalk]

**ShowUserMenu [SimTalk]**

Shows ( true ) or hides ( false ) the user-defined ribbon tab .

Type

Attribute

Syntax

```simtalk
< Path _to_Frame>.ShowUserMenu:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyFrame.ShowUserMenu := false
```

See also

Active [check box] - user-defined ribbon tab

**UserMenu [SimTalk]**

**UserMenu [SimTalk]**

Sets the user-defined menu of the Frame designated by &lt;Path&gt;.

Remarks

The attribute UserMenu passes a table of data type table with two columns.

String1 designates the command.

String2 designates the name of the Method , which the command executes.

**Note**

The attribute UserMenu only accesses the items of the user-defined ribbon tab , not its title.

Type the title of the user-defined ribbon tab into the text box Comment of the DataTable .

Type

Attribute

Syntax

```simtalk
< Path _to_Frame>.UserMenu:table
```

Assignment Value

You can assign a value of data type table .

**Example**

```simtalk
var tab: table[string, string]
tab.create
tab.writeRow(1, tab.YDim+1, "My Command 1", "self.control1")
tab.writeRow(1, tab.YDim+1, "My Command 2", "self.control2")
current.UserMenu := tab
current.UserMenuTitle := "My Ribbon Tab"
current.ShowUserMenu := true
```

**UserMenuTitle [SimTalk]**

Sets the title of the user-defined ribbon tab of the Frame designate by &lt;Path&gt; and shows it, if you set the attribute Active to true .

Syntax

```simtalk
< Path _to_Frame>.UserMenuTitle:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
frame2.UserMenuTitle := "My Ribbon Tab"
```

SimTalk

Title [user-defined ribbon tab]

Active [check box] - user-defined ribbon tab

ShowUserMenu [SimTalk]

See also

Configure User-defined Ribbon Tab

Configure User-defined Context Menu

Configure User-defined Context Menu

Creates a user-defined context menu in the selected Frame with menu commands you often use.

<!-- image -->

<!-- image -->

**Remarks**

The dialog, which the function opens is modal. The simulation only continues when the user reacted to the requested interaction by clicking the respective button in the dialog.

Type in a hyphen ( -) as the name of the command to insert a menu separator between groups of commands.

**Note**

The commands on the user-defined context menu only apply to the selected object(s) within the Frame for which you defined the context menu.

The Class Library does not show the user-defined context menu .

Let us demonstrate this with an example: We created a context menu in the Frame named MyComponent1 . When we insert MyComponent1 into our model MyPlantAnytown and click the icon of the inserted MyComponent1 with the right mouse button, Plant Simulation shows the context menu we created.

<!-- image -->

**Note**

To create a user-defined context menu in a Frame , which you inserted into another Frame , deactivate the command Inherit first. Otherwise, this Frame inherits its user-defined context menu from its origin.

**See also**

Create Your Own Ribbon Tab/Context Menu in the Frame

**Active [check box] - user-defined context menu**

To activate the user-defined context menu , select the check box Active . The context menu opens, when you click the right mouse button on the icon of the inserted Frame .

<!-- image -->

**Note**

The user-defined context menu is only available for the Frame for which you defined it, after you inserted this Frame in another Frame.

If Methods are called by the context menu , the anonymous identifier ? (question mark) is preallocated with the associated Frame .

<!-- image -->

**SimTalk**

**ShowUserPopupMenu [SimTalk]**

New [Context Menu Command]

New [Context Menu Command]

To add a new context menu command to a Frame in your simulation model, click this button.

<!-- image -->

Plant Simulation then adds a row to the dialog.

- Type in the name of the context menu command that the Frame window is to show.
- Type in the method that the context menu command is to execute in the Frame window.

<!-- image -->

Text to Display [user-defined context menu]

Type in the text of the command that Plant Simulation shows on the context menu you are defining into the text boxes below Text to Display .

You can also type in a formula as a command. A formula is designated by a leading question mark. When you type in ?Method1 for example, the method named Method1 will be called. The return value of this method has to be of data type string . This way you can switch between different texts, for example between Activate and Deactivate and you can translate the commands into different languages. If the methods return an empty string "", Plant Simulation hides the respective command.

**Note**

You can use any formulas, even for example a method call with parameters, such as ?Method1(42) or a table access, such as ?MyDataTable[1,3] .

Type in the names of the Methods which the commands call and execute into the text boxes below Method to Execute .

<!-- image -->

**SimTalk**

**UserPopupMenu [SimTalk]**

See also

Method to Execute [user-defined context menu]

**Method to Execute [user-defined context menu]**

Type in the name of the Method , which the Text to Display calls and executes, in the respective text box below Method to Execute .

<!-- image -->

**Parameter**

If the method expects a parameter, Plant Simulation automatically passes it. The selected objects, which are located within the same Frame as the Frame whose context menu you open, are passed to this parameter, which has to be of data type list .

**See also**

Text to Display [user-defined context menu]

UserPopupMenu [SimTalk]

**Delete [Context Menu Command]**

**Delete [Context Menu Command]**

To delete a context menu command from the user-defined context menu , select the respective row in the dialog and click this button.

<!-- image -->

<!-- image -->

Attributes of the User-defined Context Menu

Attributes of the User-defined Context Menu

The user-defined context menu provides these attributes :

ShowUserPopupMenu [SimTalk]

UserPopupMenu [SimTalk]

**ShowUserPopupMenu [SimTalk]**

Shows ( true ) or hides ( false ) the context menu which you defined in the Frame designated by&lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path _to_Frame>.ShowUserPopupMenu:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

Frame3.ShowUserPopupMenu := true

**UserPopupMenu [SimTalk]**

UserPopupMenu [SimTalk]

Sets the user-defined context menu of the Frame designated by &lt;Path&gt;.

Remarks

The attribute UserPopupMenu passes a table of data type table with two columns.

String1 designates the menu command.

String2 designates the name of the Method , which the command executes.

Type

Attribute

Syntax

```simtalk
< Path _to_Frame>.UserPopupMenu:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
var tab: table[string,string]
tab.create
tab.writeRow(1,1,"Open Component","openComponent")
current.UserPopupMenu := tab
```

See also

###### Configure User-defined Context Menu

**Inherit User-defined Context Menu**

Turns inheritance of the user-defined context menu , which you create in a Frame , and which you inserted into another Frame on or off.

<!-- image -->

- When you turn it on , any Frame you derive from the active Frame will inherit the userdefined context menu of its origin.
- When you turn it off, you can define a user-defined context menu that only applies to the active Frame , but will not be inherited.

**Replacement Mode**

###### Replacement Mode

Sets how Plant Simulation handles objects when you merge Frames .

The command provides the settings Merge , Exchange , and Inherit Replacement Mode .

<!-- image -->

The replacement mode controls how Plant Simulation treats an .psobj file which you load into the active model, when the Class Library of this model already contains another version of these user-defined classes. While doing so Plant Simulation compares the names of the existing Frame and of the Frame to be loaded, and then either merges or exchanges the Frames , depending on the setting you selected.

The replacement mode of the replacing Frame determines if the Frames are merged or replaced. The replacement mode of the replaced Frame does not have any consequences.

See also

**Merge**

**Exchange**

**Inherit Replacement Mode**

SimTalk

ReplacementMode [SimTalk]

replace [SimTalk] [SimTalk]

**Merge**

Preserves changed settings in instances of the replaced Frame and imports them into the replacing object . Plant Simulation then deletes the replaced object in the Class Library . Is the default setting for merging Frames .

This option only works for Frames that are identical. Compare Example 1 .

<!-- image -->

**SimTalk**

replace [SimTalk]

getNodeName [SimTalk]

loadObjectAs [SimTalk]

Save Object As

writeObject [SimTalk]

See also

Load Object

Save Object As

**Exchange**

**Exchange**

Transforms all instances of the replaced object into instances of the replacing object. Plant Simulation discards user-defined modifications in instances of the replaced object and deletes the replaced object from the Class Library .

<!-- image -->

**Note**

Before you Exchange Frames in Replacement Mode we recommend to save the previous version of the Frame as all changes you made will be lost and there is no way to retrieve them!

Merge Classes, Example and Exchange Classes, Example illustrate replacement mode.

SimTalk

replace [SimTalk]

getNodeName [SimTalk]

loadObjectAs [SimTalk]

writeObject [SimTalk]

See also

Load Object

Save Object As

**Merge Classes, Example**

In simulation model1 we modeled the object userobjectA as FrameA . We also use the model FrameA in the models FrameX and FrameY . In addition we changed the instances of FrameA in FrameX and FrameY .

We then save FrameX and FrameY with the context menu command Save Object As as object files (.psobj) to be able to reuse them in other simulation models. Plant Simulation also saves all objects you inserted into frames, especially FrameA .

Then, we load FrameX (FrameX.psobj) and FrameY (FrameY.psobj) with the context menu command Load &gt; Load Object into simulation model2 .

When loading FrameX (FrameX.psobj) and all object contained within, including FrameA , will be loaded into the Class Library of simulation model2 . Plant Simulation replaces some of the newly loaded objects with objects already present in simulation model2 . As FrameX did not exist in the Class Library , it is going to be imported as is.

When loading FrameY (FrameY.psobj) Plant Simulation loads all objects contained within. As FrameA already exists in the Class Library , Plant Simulation replaces it with the setting you selected under Replacement Mode in FrameA in the Class Library :

- Merge : All changes we made in FrameA in FrameY will be preserved.
- Exchange : All changes we made in FrameA in FrameY will be lost. FrameA in FrameY will be replaced with FrameA that already exists in the Class Library .

In this case Merge is the mode that meets our requirements.

**Exchange Classes, Example**

**Exchange Classes, Example**

In simulation model1 we modeled the user-defined object FrameA . We use FrameA several times in FrameX .

We then save FrameX with the context menu command Save Object As as object file (.psobj) to be able to reuse it in other simulation models. All objects inserted into frames, especially FrameA , are saved as well.

Then, we import FrameX into simulation model2 that contains a more up-to-date version of FrameA , FrameANew , which we would like to continue using. To replace instances of FrameA in FrameX with instances of FrameANew in FrameX , we select Exchange as Replacement Mode in FrameANew . This discards all changes in instances of FrameA in FrameX ; this means we are going to continue working with FrameANew as we intended.

Merge is not possible in this case, as FrameA differs from FrameANew .

**Inherit Replacement Mode**

Turns inheritance of the replacement mode of a Frame which you inserted into another Frame on or off.

<!-- image -->

- When you turn it on , any Frame you derive from the active Frame will inherit the replacement mode of its origin.
- When you turn it off, you can define a replacement mode that only applies to the active Frame , but will not be inherited.

**Lock Structure [Frame ribbon]**

###### Lock Structure [Frame ribbon]

Locks the structure of the Frame . Lock Structure is deactivated by default for new models, allowing you to immediately start modeling.

<!-- image -->

When you activate Lock Structure , Plant Simulation prevents unintentional changes, i.e., inserting, deleting, and changing of objects as well as changing the position of objects. You can then neither change the position of any of the objects nor their name.

<!-- image -->

Lock Structure is activated in instantiated Frames by default. This helps to prevent unintentional changes to the structure of an instance, although this change should apply to all instances and should thus be made in the class.

**SimTalk**

**LockStructure [SimTalk]**

View Ribbon Tab [2D only]

View Ribbon Tab [2D only]

The View ribbon tab of the Frame provides commands to access its functions.

**Note**

These commands on the View ribbon tab are only available in a 2D Only model .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Command                                                        | Looks like this   | Method or Attribute               |
|----------------------------------------------------------------|-------------------|-----------------------------------|
| Zoom In [2D only]                                              |                   | ZoomFactor [SimTalk]              |
| Reset to Original Size                                         |                   | ZoomFactor [SimTalk]              |
| Zoom Out [2D only]                                             |                   | ZoomFactor [SimTalk]              |
| Scaling Factor [2D only]                                       |                   | ScalingFactor [SimTalk]           |
| Representation [2D only]                                       |                   | Various                           |
| Background Color [Frame] Select Color Inherit Background Color |                   | BackgroundColor [SimTalk] - Frame |
| Show Object Names [View ribbon] - 2D                           |                   | ShowObjectNames [SimTalk]         |
| Show Connections [View ribbon] - 2D                            |                   | -                                 |
| Show Comments [View ribbon]                                    |                   | -                                 |

<!-- image -->

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Frame .

###### Zoom In [2D only]

Zooms the contents of the active Frame window in.

<!-- image -->

Instead of using Zoom In you can also:

- Hold down Ctrl and roll the mouse wheel up. Or you can hold down Ctrl and press the + key.
- Drag a marquee over the icons with the right mouse button and release the mouse button.
- Hold down Ctrl and Shift , drag a marquee over the icons and release the mouse button.

<!-- image -->

To zoom in faster, hold down Shift while clicking . Plant Simulation then zooms in steps of 100 %, for example from 100 % to 200 %, etc. To return to a zoom factor of 100 %, hold down Shift while clicking

<!-- image -->

.

**Note**

If you set a scaling percentage under Windows Settings &gt; System &gt; Display &gt; Scale and layout , this setting not only applies to the overall Windows user interface but also for Frames in 2D. Plant Simulation zooms the contents of the Frame accordingly. If you set a scale of less than 150 %, Plant Simulation does not scale the contents of the Frame accordingly.

If you set different scaling percentages for different monitors, this does not affect Plant Simulation . In this case Plant Simulation always uses the scaling percentage of the primary monitor. If you change settings, these only take effect after signing out of Windows and signing in again.

To return the objects to the size they had before zooming, select Reset to Original Size .

See also

ZoomFactor [SimTalk]

Reset to Original Size

**Reset to Original Size**

###### Reset to Original Size

Resets the contents of the Frame to its original, unzoomed size after you selected the commands Zoom In or Zoom Out .

<!-- image -->

Or you can hold down Ctrl and press 0 (zero).

See also

ZoomFactor [SimTalk]

Zoom In [2D only]

Zoom Out [2D only]

###### Zoom Out [2D only]

Zooms the contents of the Frame window out.

<!-- image -->

To zoom out you can also hold down Ctrl and roll the mouse wheel down.

<!-- image -->

To zoom out faster, hold down Shift while clicking . To return to a zoom factor of 100 %, hold down Shift while clicking . Plant Simulation then zooms out in steps of 100 %, for example from 200 % to 100 %, etc.

<!-- image -->

To return the objects to the size they had before zooming, select Reset to Original Size .

See also

##### ZoomFactor [SimTalk]

###### Scaling Factor [2D only]

Sets the Scaling Factor for displaying the objects in the Frame . Plant Simulation uses the scaling factor for converting the pixel coordinates to length coordinates.

<!-- image -->

The command opens the dialog Scaling Factor .

**Note**

When you change the Scaling Factor , Plant Simulation keeps the lengths of the length-oriented objects and the 3D coordinates and changes the dimension or the representation of the pixels respectively. Plant Simulation moves the axes origin if your change would create negative pixel coordinates.

**Note**

If one or more Frames in the hierarchy of Frames use Icon Animation and connected animation points, the parts are only animated correctly if all Frames use the same Scaling Factor .

- Type in the Scaling Factor . Plant Simulation uses it to compute the length of polygon lines that you create. The Scaling Factor is the length of one pixel in length units.
- Select length units under File &gt; Model Settings/Preferences &gt; Units &gt; Length .
- Enter grid settings under File &gt; Preferences &gt; Modeling &gt; Frame grid spacing .
- The Horizontal Grid Spacing shows the distance between two grid points on the x-axis using the Scaling Factor you entered.
- The Vertical Grid Spacing shows the distance between two grid points on the y-axis.

The default settings Frame Grid Spacing 20 x 20 pixels, Length Unit m (meters) and a Scaling Factor of 0.05 result in a horizontal and vertical grid spacing of 1 meter each.

When you change the Scaling Factor, Plant Simulation shows the new horizontal and vertical grid spacing in the dialog.

The settings Frame Grid Spacing 20 x 20 pixels, Length Unit m (meters) and a Scaling Factor of 0.5 result in a horizontal and vertical grid spacing of 10 meters each.

<!-- image -->

**SimTalk**

**ScalingFactor [SimTalk]**

See also

Map 2D Coordinates to 3D Coordinates in the Scene

Map 2D Coordinates to 3D Coordinates in the Scene

Representation [2D only]

Representation [2D only]

Sets the representation area which combines a number of built-in objects in a Frame in 2D.

<!-- image -->

The command opens the dialog Representation . You can select how you want to show these objects when you insert this Frame into another Frame . You can instantiate this group, and you can move it within a Frame at will.

<!-- image -->

The representation is especially helpful when you model a component in a Frame in the Class Library and then insert this component into your overall simulation model.

- When you select the Representation Mode &gt; Icon , Plant Simulation shows the inserted Frame with its icon . For demonstration purposes we use a filled blue rectangle in the screenshot below.

<!-- image -->

- When you select the Representation Mode &gt; Contents , Plant Simulation shows the contents of the Frame , i.e., the objects which it contains. This is like just seeing a box (icon) as compared to actually looking inside the box and seeing what it contains (contents). For this setting Plant Simulation draws a border around all objects in the Frame . You can define the size and the position of the Representation Area . When you then instantiate this Frame , Plant Simulation shows the objects within the Representation Area instead of the icon of the Frame .
- When you select the Representation Mode &gt; Contents with background , Plant Simulation draws a border around all objects in the Frame and shows the background in addition, the gray area in our example below. You can define the size and the position of the Representation Area . When you then instantiate this Frame , Plant Simulation shows the objects and the background within the Representation Area instead of the icon of the Frame .

<!-- image -->

Plant Simulation shows the background of your modeled component with the Background Color you selected for the Frame in which you modeled it. If you do not select a background color, the object will be shown transparent. This way you can 'project' the object onto a plant layout drawing so that the layout graphic shines through. The represented area does not show the grid.

<!-- image -->

The red crosshairs in the Frame designate the 3D origin of the Frame which also is the reference point of the contents of the Frame . The position of the built-in objects within the Representation Area of the Frame is relative to the reference point of the Representation Area designated by the red crosshairs.

<!-- image -->

**Note**

To hide the red crosshairs from view, type in 0 for both values of the Axes Origin .

When you instantiate your modeled object, Plant Simulation shows it with the Scaling Factor and the Zoom Factor of the Frame into which you inserted it. Zooming the Frame also zooms your modeled objects within the representation area.

You can only move or rotate it in 90 degree steps, and you can only delete the Representation Area in an instantiated Frame as a whole. Double-click the instantiated object to open and edit it.

Plant Simulation does not show Interface objects with just a single successor or predecessor. If an Interface has several predecessors or successors, Plant Simulation shows the Interfaces and the Connectors to the Interfaces which are located within the Representation Area . Connectors to Interfaces , which are located outside of the Representation Area , are clipped by the Representation Area .

See also

Representation Mode

Representation Area X

Representation Area Y

Representation Area Width

Representation Area Height

Axes Origin X/Y

<!-- image -->

**Show Content in 3D**

**Representation Mode**

Select the Representation Mode . It determines how Plant Simulation shows the selected Frame .

<!-- image -->

- With its Contents including the background

<!-- image -->

Plant Simulation shows the background of your modeled component with the Background Color color you selected for the Frame in which you modeled it. If you do not select a background color, the object will be transparent. This way you can 'project' the object onto a plant layout drawing so that the layout drawing shines through. The represented area does not show the grid.

**SimTalk**

RepresentationMode [SimTalk]

**Representation Area X**

Type the x-coordinate of the left top corner of the representation area in the Frame or click the spin buttons.

<!-- image -->

To move the x-coordinate of the left top corner of the representation area in the Frame to the right, click the right spin button. To move it to the left, click the left spin button.

The check box next to representation area turns inheritance of the settings of the Representation Area and of the Axes Origin off or on !

The position of the built-in objects within the Representation Area of the Frame is relative to the reference point of the Representation Area designated by the red crosshairs. The borders of the area itself are shown as green dashed lines.

SimTalk

setRepresentationArea [SimTalk]

getRepresentationArea [SimTalk]

**Representation Area Y**

Type the y-coordinate of the top left corner of the representation area in the Frame or click the spin buttons.

<!-- image -->

To move the y-coordinate of the top left corner of the representation area in the Frame upward, click the up spin button. To move it downward, click the down spin button.

<!-- image -->

The check box next to representation area turns inheritance of the settings of the Representation Area and of the Axes Origin off or on !

The position of the built-in objects within the Representation Area of the Frame is relative to the reference point of the Representation Area designated by the red crosshairs. The borders of the area itself are shown as green dashed lines.

SimTalk

setRepresentationArea [SimTalk]

getRepresentationArea [SimTalk]

**Representation Area Width**

Type in the Width of the representation area or click the spin buttons.

<!-- image -->

To increase the width of the representation area, click the right spin button. To decrease the width of the representation area, click the left spin button.

<!-- image -->

The check box next to representation area turns inheritance of the settings of the Representation Area and of the Axes Origin off or on !

The position of the built-in objects within the Representation Area of the Frame is relative to the reference point of the Representation Area designated by the red crosshairs. The borders of the area itself are shown as green dashed lines.

SimTalk

setRepresentationArea [SimTalk]

getRepresentationArea [SimTalk]

**Representation Area Height**

Type in the Height of the representation area or click the spin buttons.

<!-- image -->

To increase the height of the representation area, click the up spin button. To decrease the height of the representation area, click the down spin button.

<!-- image -->

The check box next to representation area turns inheritance of the settings of the Representation Area and of the Axes Origin off or on !

The position of the built-in objects within the Representation Area of the Frame is relative to the reference point of the Representation Area designated by the red crosshairs. The borders of the area itself are shown as green dashed lines.

SimTalk

setRepresentationArea [SimTalk]

getRepresentationArea [SimTalk]

**Axes Origin X/Y**

Type in the x-coordinate or the y-coordinate of the 3D origin or click the spin buttons.

The Frame shows the origin of the axes, which also is the reference point of the contents of the Frame , as red crosshairs.

<!-- image -->

To move the x-coordinate or the y-coordinate of the 3D origin to the right, click the right spin button. To move it to the left, click the left spin button.

The check box next to representation area turns inheritance of the settings of the Representation Area and of the Axes Origin off or on !

When you change the axes origin, Plant Simulation keeps the 3D coordinates and changes the pixel coordinates. Plant Simulation checks if your changes create allowed pixel coordinates and only changes them if that is the case.

In our example the axes origin is located at the coordinates X is 242 and Y is 266 .

**Note**

To hide the red crosshairs from view, type in 0 for both values of the Axes Origin .

SimTalk

AxesOrigin [SimTalk]

**Calculate Area**

To make Plant Simulation re-compute the representation area according to the objects contained in that area, click this button.

Background Color [2D only]

Background Color [Frame]

Sets the background color of the Frame , i.e., of your plant.

<!-- image -->

The command provides the subcommands Select Color and Inherit Background Color .

In 3D you can set the background color on the tab Background in the dialog Edit 3D Properties .

See also

Add a Graphic and a Color to the Background of the 2D Frame

**Select Color**

**Select Color**

Opens the dialog Colors . Select a color for the background of the Frame here.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

**SimTalk**

BackgroundColor [SimTalk] - Frame

**Inherit Background Color**

<!-- image -->

Turns inheritance of the background color of the Frame off or on.

- When you turn it on , any Frame you derive from the active Frame will have the same background color as it.

- When you turn it off, you can define a background color that only applies to the active Frame , but will not be inherited.

Show Object Names [View ribbon] - 2D

Shows or hides the names of the objects below their icons in the Frame window.

<!-- image -->

<!-- image -->

**Note**

When you change one of the View Options , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

. The background for this behavior is that, as a rule, you will want to change the setting for all instances of the Frame .

**Note**

To show the names and the labels of the objects in 3D, click the class/instance of the object with the right mouse button and select Edit 3D Properties . Then select Name/Label Activated on the tab Captions . Show Object Names on the View ribbon tab then shows or hides the object names.

The settings Name/Label Activated in 3D and Show Object Names and Show Object Labels in the Frame in 2D are independent of each other.

SimTalk

ShowObjectNames [SimTalk]

\_3D.ShowNames [SimTalk]

See also

Name [general description]

Show Object Names [model settings] Show Object Names [preferences] Show Object Labels [model settings]

Show Object Labels [preferences]

###### Show Connections [View ribbon] - 2D

Shows or hides the connections , i.e., the Connectors between the objects in the Frame window.

<!-- image -->

An arrow in the middle of the Connector shows the direction. The commands Show Predecessors and Show Successors only work when you select Show Connections !

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

**SimTalk**

\_3D.ShowConnections [SimTalk]

###### Show Comments [View ribbon]

Shows or hides objects of type Comment which you inserted into your simulation model.

<!-- image -->

Comments can provide explanations and additional information about the model.

| On   | Off   |
|------|-------|

See also

Comment [object]

###### Show Grid [View ribbon] - 2D

Shows or hides the grid points in the Frame window. This is useful for automatically aligning objects when you insert them.

<!-- image -->

Type in the spacing of the grid intervals on the x-axis and the y-axis into the text boxes below Frame Grid Spacing . You might want to select the command Show Object Borders as well.

When the Grid is active, Plant Simulation places the objects which you insert onto grid points. You can then move the object by grid units only. The reference point of the icon of the object determines where Plant Simulation places the object on the grid point. By default, the reference point of a material flow object is located in the center of the icon. When you place an object, Plant Simulation places the reference point onto the grid point nearest to the mouse pointer.

You can move the reference point to any position of your choice in the Icon Editor with the command Set Reference Point . This is described under Set and Link Animation Points and Animation Lines .

Selecting Show Grid after you placed objects has no effect on the alignment of the objects which you already placed. They remain at the position at which you inserted them.

To align the objects which you already inserted, with the grid, click Align to Grid on the Icons ribbon tab of the Frame . Plant Simulation then moves all selected objects, so that their reference points are aligned with the closest grid point.

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

<!-- image -->

**More View Options**

###### More View Options

Sets what Plant Simulation shows in the Frame window.

<!-- image -->

Settings you select here override those you selected under File &gt; Preferences &gt; 2D or under File &gt; Model Settings &gt; 2D in the Plant Simulation window.

A check mark to the left of a command means that this command is active, i.e., that Plant Simulation shows the selected item.

To not show an item, click the command so that it does not show a check mark.

<!-- image -->

**Note**

When you change one of the View Options , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

. The background for this behavior is that, as a rule, you will want to change the setting for all instances of the Frame .

**See also**

Show MU Names [View ribbon] - 2D

Show Object Labels [View ribbon] - 2D

Show Display Panels [View ribbon] - 2D

Show Predecessors [View ribbon] - 2D

Show Successors [View ribbon] - 2D

Show Object Borders [View ribbon] - 2D

**Show MU Names [View ribbon] - 2D**

Shows or hides the names of the parts ( MUs ) in your simulation model. This only works, when you also activate Show Object Names .

<!-- image -->

Hiding MU Names prevents your simulation model from looking cluttered.

<!-- image -->

<!-- image -->

**See also**

Show Object Names [View ribbon] - 2D

Show Object Labels [View ribbon] - 2D

Shows or hides the Labels of the objects below their icons in the Frame window.

<!-- image -->

If you activated Show Object Names Plant Simulation shows the label below the name.

<!-- image -->

If you deactivated Show Object Names , it shows the Labels directly below the icon.

<!-- image -->

**Note**

When you change one of the View Options , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

. The background for this behavior is that, as a rule, you will want to change the setting for all instances of the Frame .

**Note**

To show the names and the labels of the objects in 3D, click the class/instance of the object with the right mouse button and select Edit 3D Properties . Then select Name/Label Activated on the tab Captions . Show Object Names on the View ribbon tab then shows or hides the object names.

SimTalk

ShowObjectLabels [SimTalk]

See also Label [general description] Show Object Labels [model settings]

Show Object Names [model settings]

Show Display Panels [View ribbon] - 2D

Shows or hides the Display Panels of the objects in the Frame window. Only 2D provides Display Panels .

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

**SimTalk**

ShowDisplayPanels [SimTalk]

See also

Display Panel [object]

**Show Predecessors [View ribbon] - 2D**

Shows or hides the number of an incoming connection for each material flow connection in the Frame window. The &gt; (greater) sign in front of the number designates an incoming connection.

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

<!-- image -->

Plant Simulation only displays the predecessor in the Frame window, if you activate Show Connections as well. For the first connection from another object to the current object, the Connector shows &gt;1 , denoting that this is the first predecessor. If the object has more than one predecessor, Plant Simulation numbers the predecessors in the order you connected them, &gt;2 for the second, &gt;3 for the third, etc.

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

**Show Predecessors [View ribbon] - 2D**

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

SimTalk

PredInterface [SimTalk]

NumPred [SimTalk] - general description

pred [SimTalk] - general description

predConnector [SimTalk] - general description

**Show Successors [View ribbon] - 2D**

Shows or hides the number of an outgoing connection for each material flow connection in the Frame window.

<!-- image -->

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the model. The sequence of the successors affects how the goods are transported through your simulation model.

<!-- image -->

Plant Simulation only displays the successors in the Frame window, if you activate Show Connections as well. For the first connection from the current object to another object, the Connector shows 1&gt;, denoting that this is the first successor. If the object has more than one successor, Plant Simulation numbers the successors in the order you connected them, &gt; 2&gt; for the second, 3&gt; for the third, etc.

3D shows the predecessors and the successors of an object in a Tooltip when you drag the mouse over the respective Connector .

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

**Show Successors [View ribbon] - 2D**

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

**SimTalk**

NumSucc [SimTalk] - general description

succ [SimTalk] - general description

succConnector [SimTalk] - general description

###### Show Object Borders [View ribbon] - 2D

Shows or hides the borders around the icons of all objects in the Frame .

<!-- image -->

This way you can see the full icon size of the icon. The size of the border depends on the size of the icon.

<!-- image -->

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

**See also**

Icon Size

###### Inherit View Options [2D only]

Inherit View Options [2D only]

Turns inheritance of the view settings of the active Frame from its class off or on.

<!-- image -->

- When you turn it on, the current Frame inherits all view settings on the Options menu from its class object.
- When you turn it off, the view settings you select only apply to the current Frame .

Icons Ribbon Tab [2D only]

Icons Ribbon Tab [2D only]

The Icons ribbon tab of the Frame provides commands for editing the icons of the objects in your simulation model.

**Note**

The Icons ribbon tab is only available in a 2D Only model .

**Note**

As long as vector graphics mode is active, you cannot manipulate any objects in the Frame . To deactivate it, and to return to normal mode, click another tab.

<!-- image -->

| Command                      | Looks like this   | Method or Attribute                                 |
|------------------------------|-------------------|-----------------------------------------------------|
| Previous Icon [Icons ribbon] |                   | -                                                   |
| Next Icon [Icons ribbon]     |                   | -                                                   |
| Mirror Horizontally          |                   | mirrorX [SimTalk] - material flow objects           |
| Mirror Vertically            |                   | mirrorY [SimTalk] - material flow objects           |
| Rotate Icon                  |                   | turnIcon [SimTalk] rotate [SimTalk] - curved object |
| Reset Icon                   |                   | resetIcon [SimTalk]                                 |
| Align to Grid [icons 2D]     |                   | rearrange [SimTalk]                                 |
| Bring to Front               |                   | -                                                   |
| Send to Back                 |                   | -                                                   |
| Double Size of Icon          |                   | ZoomX [SimTalk] ZoomY [SimTalk]                     |

###### Icons Ribbon Tab [2D only]

<!-- image -->

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to the Frame .

**See also**

| CurrIcon [SimTalk]   | putIconToClipboard [SimTalk]       |
|----------------------|------------------------------------|
| CurrIconNo [SimTalk] | resetIcon [SimTalk]                |
| closeImg [SimTalk]   | saveIconToFile [SimTalk]           |
| existsIcon [SimTalk] | setCurrIconFromClipboard [SimTalk] |
| openImg [SimTalk]    | setIconFromFile [SimTalk]          |

###### Previous Icon [Icons ribbon]

Changes to the previous icon of the selected object.

<!-- image -->

**Next Icon [Icons ribbon]**

###### Next Icon [Icons ribbon]

Changes to the next icon of the selected object.

<!-- image -->

###### Mirror Horizontally

Mirrors the icon of the selected object horizontally, i.e., it reverses left and right. To return the icon of the selected object to its original orientation, click Reset Icon .

<!-- image -->

See also

Reset Icon

mirrorY [SimTalk] - general description

mirrorY [SimTalk] - material flow objects

**Mirror Vertically**

###### Mirror Vertically

Mirrors the icon of the selected object vertically, i.e., it reverses top and bottom. To return the icon of the object to its original orientation, click Reset Icon .

<!-- image -->

See also

Reset Icon

mirrorX [SimTalk] - general description

mirrorX [SimTalk] - material flow objects

###### Rotate Icon

Rotates the icon of the selected object in 90 degree steps clockwise around its center.

<!-- image -->

The command sets the attribute ObjectAngle of the object.

**Note**

Changing the Conveying Direction of the parts permanently affects the attribute ObjectAngle . Changing the attribute ObjectAngle on the other hand does not change the Conveying Direction .

SimTalk

ObjectAngle [SimTalk] - object icons

ObjectMirrored [SimTalk] - object icons

turnIcon [SimTalk]

rotate [SimTalk] - curved object

resetIcon [SimTalk]

See also

Segments [curve] - 2D, described

Conveying Direction [described]

###### Reset Icon

Returns the icon of the selected object to its original orientation after you selected Mirror Vertically or Mirror Horizontally .

<!-- image -->

SimTalk resetIcon [SimTalk] See also Mirror Vertically Mirror Horizontally

###### Align to Grid [icons 2D]

Places the reference points of the icons of the selected objects onto grid points.

<!-- image -->

Aligning to the grid is especially helpful when Show Grid on the View ribbon tab of the Frame was deactivated while you placed the objects and models and the reference points of the icons were thus not located on the grid points.

<!-- image -->

SimTalk

rearrange [SimTalk]

See also

Set and Link Animation Points and Lines

Set Reference Point [command]

**Bring to Front**

###### Bring to Front

Brings the icon of the selected object to the front and places it in front of any other overlapping objects.

<!-- image -->

**Note**

This also changes the number of the object in the Frame , compare the method node , as the object number and the drawing layer are directly related to each other.

###### Send to Back

Sends the icon of the selected object to the back and places it behind any other overlapping objects.

<!-- image -->

**Note**

This also changes the number of the object in the Frame , compare the method node , as the object number and the drawing layer are directly related to each other.

###### Double Size of Icon

Doubles the size of the icon of the selected object in the Frame window.

<!-- image -->

To change the height of an icon, hold down the Ctrl and Shift keys, grab the top or the bottom of the icon and drag the mouse.

<!-- image -->

<!-- image -->

To change the width of an icon, hold down the Ctrl and Shift keys, grab the right or the left side of the icon and drag the mouse.

<!-- image -->

<!-- image -->

To change the width and the height of an icon at the same time, hold down the Ctrl and Shift keys, grab one of the corners of the icon and drag the mouse.

<!-- image -->

<!-- image -->

To return the icon of the selected object to its original size, select Restore Original Size .

SimTalk

ZoomX [SimTalk]

ZoomY [SimTalk]

**See also**

**Restore Original Size**

**Restore Original Size**

###### Restore Original Size

Restores the original size of the icon of the selected object after you selected the commands Double Size of Icon or Halve Size of Icon.

<!-- image -->

See also

Double Size of Icon

Halve Size of Icon

###### Halve Size of Icon

Reduces the size of the icon of the selected object by half.

<!-- image -->

To return the icon of the selected object to its original size, select Restore Original Size .

SimTalk

ZoomX [SimTalk]

ZoomY [SimTalk]

See also

Restore Original Size

**Inherit Position**

###### Inherit Position

Activates Inheritance of the position of the selected object. It also places the object at the same position in the Frame as the position of the object from which it was derived, i.e., its origin.

<!-- image -->

SimTalk

inheritAttribute [SimTalk] - object

XPos [SimTalk] - general description

YPos [SimTalk] - general description

See also

Inheritance [general description]

Context Menu for Several Selected Objects &gt; Transformation Inheritance &gt; Inherit Positions in 3D

###### Inherit Size and Orientation

Activates Inheritance of the size and the orientation of the icon of the selected object again.

<!-- image -->

It also sets the size and the orientation of the icon of the selected object to the same values as the values of the size and the orientation of the icon of the object from which it was derived, i.e., its origin.

**SimTalk**

inheritAttribute [SimTalk] - object

ZoomX [SimTalk]

ZoomY [SimTalk]

mirrorX [SimTalk] - general description

mirrorY [SimTalk] - general description

turnIcon [SimTalk]

ObjectAngle [SimTalk] - object icons

ObjectMirrored [SimTalk] - object icons

See also

**Inheritance [general description]**

Context Menu for Several Selected Objects &gt; Transformation Inheritance &gt; Inherit Rotations in 3D

Context Menu for Several Selected Objects &gt; Transformation Inheritance &gt; Inherit Scalings

Vector Graphics Ribbon Tab [2D only]

Vector Graphics Ribbon Tab [2D only]

The Vector Graphics ribbon tab of the Frame provides commands to access its functions.

**Note**

The Vector Graphics ribbon tab is only available in a 2D Only model .

**Note**

As long as the ribbon tab Vector Graphics is selected, you cannot manipulate any objects in the Frame . To deactivate vector graphics mode, and to return to normal mode, click another tab.

<!-- image -->

<!-- image -->

| Command                          | Looks like this   | Method or Attribute      |
|----------------------------------|-------------------|--------------------------|
| Draw Textbox                     |                   | drawText [SimTalk]       |
| Graphic Settings                 |                   | -                        |
| Group Vector Graphics            |                   | -                        |
| Ungroup Vector Graphics          |                   | -                        |
| Delete Objects [vector graphics] |                   | -                        |
| Delete Layer                     |                   | eraseLayer [SimTalk]     |
| Delete All Layers                |                   | eraseAllLayers [SimTalk] |
| Inherit Vector Graphics          |                   | -                        |

**See also**

Draw Vector Graphics or Text onto the Background of the Frame

**Select Mode**

###### Select Mode

Changes from draw mode to select mode . In select mode you can modify any of the vector objects, you can group them for example. To change to draw mode click any of the drawing tools.

<!-- image -->

<!-- image -->

###### Draw Line [vector graphic]

Draws a line on the background of the Frame .

For the line styles solid line , dashed line , dotted line , dash dot line , and dash dot dot line the operating system only enables a line width of 1 or 0. For a line Weight of 1 Plant Simulation always draws the line style as a solid line, when you zoom the contents of the Frame .

To change properties of the line in the dialog Graphic Settings , double-click the line.

SimTalk

drawLine [SimTalk]

**Draw Ellipse [vector graphic]**

###### Draw Ellipse [vector graphic]

Draws an ellipse on the background of the Frame .

<!-- image -->

If you do not want to zoom the outline of the ellipse, enter a line Weight of 0 instead of 1 .

To change properties of the ellipse in the dialog Graphic Settings , double-click the ellipse.

SimTalk

drawEllipse [SimTalk]

###### Draw Filled Ellipse

Draws a filled ellipse on the background of the Frame .

<!-- image -->

If you do not want to zoom the outline of the ellipse, enter a line Weight of 0 instead of 1 .

To change properties of the filled ellipse in the dialog Graphic Settings , double-click the filled ellipse.

SimTalk

drawEllipse [SimTalk]

**Draw Rectangle [vector graphic]**

###### Draw Rectangle [vector graphic]

Draws a rectangle on the background of the Frame .

<!-- image -->

If you do not want to zoom the outline of the rectangle, enter a line Weight of 0 instead of 1 .

To change properties of the rectangle in the dialog Graphic Settings , double-click the rectangle.

SimTalk

drawRectangle [SimTalk]

###### Draw Filled Rectangle [vector graphic]

Draws a filled rectangle on the background of the Frame .

<!-- image -->

If you do not want to zoom the outline of the rectangle, enter a line Weight of 0 instead of 1 .

You can add a color gradient to a filled rectangle.

<!-- image -->

To change properties of the filled rectangle in the dialog Graphic Settings , double-click the filled rectangle.

**SimTalk**

drawRectangle [SimTalk]

**Draw Textbox**

###### Draw Textbox

Draws a textbox on the background of the Frame .

<!-- image -->

Type the text into the text box Text in the dialog Graphic Settings and select the Text Color , the Layer on which the text will be placed, and the Font Size of the text.

<!-- image -->

**SimTalk**

drawText [SimTalk]

###### Graphic Settings

Opens the dialog Graphic Settings . The settings you select and type in here determine how Plant Simulation draws the vector graphics you are going to create.

<!-- image -->

To edit the settings of the selected vector object, you can double-click that vector object.

<!-- image -->

You can change the following settings.

- Select a color by clicking the drop-down arrow.

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

- Select Filled , to fill an ellipse or a rectangle with the Color you selected.
- Select the direction in which the Color Gradient blends. This feature is only available for filled rectangles .

<!-- image -->

<!-- image -->

- Type in the Line Weight , i.e., the thickness of the line you draw, in pixels.
- Select a Line Style of the line. You can also draw lines with arrowheads pointing left or right at their ends.
- Type in the Layer onto which Plant Simulation draws the vector object.
- Type in a negative number, -1 for example, to draw the vector object onto the foreground of the Frame .
- Type in a positive number to draw the vector object onto the background of the Frame .
- Select a Font Size for the text you type into the text box or into the dialog Enter Text .
- Type in the Text , which you want to show on the background/foreground of the Frame .
- To apply your settings, and to see what the item looks like, click Apply .
- To apply your settings and to close the dialog, click OK .

<!-- image -->

SimTalk drawEllipse [SimTalk] drawLine [SimTalk] drawRectangle [SimTalk] drawText [SimTalk] eraseAllLayers [SimTalk] eraseLayer [SimTalk] See also Vector Graphics Ribbon Tab [2D only]

**Group Vector Graphics**

###### Group Vector Graphics

Groups the selected vector graphics.

<!-- image -->

###### Ungroup Vector Graphics

Ungroups the group and restores the individual vector graphics.

<!-- image -->

**Delete Objects [vector graphics]**

###### Delete Objects [vector graphics]

Deletes the selected vector graphics.

<!-- image -->

Delete Layer

Deletes all vector graphics on the layer, whose number you type into the dialog Delete Layer .

<!-- image -->

SimTalk

eraseLayer [SimTalk]

###### Delete All Layers

Delete All Layers

Deletes all vector graphics on all layers.

<!-- image -->

SimTalk

**eraseAllLayers [SimTalk]**

###### Inherit Vector Graphics

Turns inheritance of the vector graphics you drew in the Frame , when you insert the Frame into another Frame on or off.

<!-- image -->

##### Context Menu of the Frame Itself

The context menu of the Frame itself provides these commands. To open it, click into the background of the Frame with the right mouse button.

<!-- image -->

Some of the commands are located on the mini toolbar , while others are commands on the context menu itself.

You can also close the context menu and leave the mini toolbar open

<!-- image -->

button.

<!-- image -->

| To do this                                          | click or select                             |
|-----------------------------------------------------|---------------------------------------------|
| Reset the simulation in the Frame                   | Reset Simulation [Home ribbon]              |
| Start or stop the simulation in the Frame           | Start/Stop Simulation [Home ribbon]         |
| Start the simulation without animation in the Frame | Start Fast Forward Simulation [Home ribbon] |
| Show the objects which Frame contains               | Show Structure [Home ribbon]                |

by clicking the border of the mini toolbar with the left mouse

<!-- image -->

<!-- image -->

| To do this                                    | click or select                                            |
|-----------------------------------------------|------------------------------------------------------------|
| Show the objects which inherit from the Frame | Show Inheritance [Home ribbon]                             |
| Show the attributes and methods of the Frame  | Show Attributes and Methods [Home ribbon]                  |
| Show or hide view options for the Frame       | More View Options , Show MUNames [View ribbon] - 2D , etc. |

###### Context Menu of the Selected Object in the Frame

##### Context Menu of the Selected Object in the Frame

The context menu of an object, which you insert into a Frame , provides some of these commands, when you click it with the right mouse button.

Some of the commands are located on the mini toolbar , while others are commands on the context menu itself.

<!-- image -->

You can also close the context menu and leave the mini toolbar open by clicking the border of the mini toolbar with the left mouse button.

<!-- image -->

<!-- image -->

<!-- image -->

| Activate                 | Open                           | Show                             |
|--------------------------|--------------------------------|----------------------------------|
| Arrange Icons            | Open Class                     | Show Assigned Objects [in Frame] |
| Calculate Angles         | Open Comment Window            | Show Attributes and Methods      |
| Controls [in Frame]      | Open Debugger                  | Show Dialog                      |
| Create Sensor            | Open External Connections List | Show Exported Services           |
| Create Tugger Train [2D] | Open Origin                    | Show External Connected Objects  |
| Delete Sensor            | Open Sensor                    | Show Sessions Log                |
| Deactivate               | Open Values Table              | Show Statistics Report           |
| Down One Level           | Open Without Control           | Show Structure                   |
| Edit Dialog              | Previous Icon                  | Start/Stop Simulation            |
| Edit Display Panel       | Rename                         | Start Fast Forward Simulation    |

| Edit Icons                   | Reorder Successors                                                | Statistics Wizard   |
|------------------------------|-------------------------------------------------------------------|---------------------|
| Edit User-defined Attributes | Reset Simulation                                                  | Type Info           |
| Event Debugger               | Run                                                               | Update              |
| Next Icon                    | Segments > Append Edit Delete Point Insert Point Reverse Split Up |                     |

The context menu looks like this in a 2D model :

<!-- image -->

The context menu looks like this in a 3D model :

<!-- image -->

<!-- image -->

The mini toolbar above the context menu proper always provides these commands:

<!-- image -->

| To do this                                | click                     |
|-------------------------------------------|---------------------------|
| Open the origin of the selected object    | Open Origin [Home ribbon] |
| Open the class of the selected object     | Open Class [Home ribbon]  |
| Cut the selected object from the Frame    | Cut [Home ribbon]         |
| Copy the selected object in the Frame     | Copy [Home ribbon]        |
| Delete the selected object from the Frame | Delete [Home ribbon]      |

Some objects provide additional commands on the mini toolbar to the left or the right of the default buttons.

You can also close the context menu and leave the mini toolbar open by clicking the border of the mini toolbar with the left mouse button.

**Note**

Not all objects provide all of the context menu commands listed above.

###### Activate [in Frame]

To activate the selected object, select this command.

It then selects the check box Active [check box] - ShiftCalendar

For the ShiftCalendar it looks like this:

<!-- image -->

You can deactivate the selected object with the command Deactivate .

.

**Arrange Icons [Frame]**

###### Arrange Icons [Frame]

The subcommands of the command Arrange Icons align, distribute or reverse the order of the selected icons within the Frame window.

First, select the objects whose icons you would like to arrange by dragging a marquee around them or by holding down Shift and clicking the objects with the left mouse button one by one. Then, click the object to which you want to align the other selected objects with the right mouse button and select the respective subcommand.

<!-- image -->

**Align Horizontally**

To align the icons of the selected objects horizontally in the Frame window, select this command. Plant Simulation aligns the objects to the y-coordinate of the object, which you clicked, and for which you selected the command.

**Align Vertically**

To align the icons of the selected objects vertically in the Frame window, select this command. Plant Simulation aligns the objects to the x-coordinate of the object, which you clicked, and for which you selected the command.

**Distribute Horizontally**

To distribute the icons of the selected objects with equal distances to each other horizontally in the Frame window, select this command.

**Distribute Vertically**

To distribute the icons of the selected objects with equal distances to each other vertically in the Frame window, select this command.

**Reverse Order Horizontally**

To reverse the order of the icons of selected objects horizontally in the Frame window, select this command.

<!-- image -->

**Reverse Order Vertically**

To reverse the order of the icons of the selected objects vertically in the Frame window, select this command.

<!-- image -->

**Arrange Icons [Frame]**

**Bring to Front**

To place the selected objects in front of other overlapping objects in the Frame window, select this command.

**Note**

This also changes the number of the object in the Frame , compare the method node , as the object number and the drawing layer are directly related to each other.

**Send to Back**

To place the selected objects behind other overlapping objects in the Frame window, select this command.

**Note**

This also changes the number of the object in the Frame , compare the method node , as the object number and the drawing layer are directly related to each other.

3D provides similar functions under Arrange Objects .

###### Calculate Angles

To make the Turntable and the PickAndPlace robot compute the angles at which you connected them with their predecessors and with their successors in the Frame , select this command.

<!-- image -->

The Turntable then enters the entry angles into the Entry Angle Table and the exit angles into the Exit Angle Table .

The PickAndPlace robot then enters the angles into the Angles Table .

See also

Pick Up Parts and Place Them with the Robot

calculateAngles [SimTalk] - PickAndPlace

calculateAngles [SimTalk] - Turntable

**Controls [in Frame]**

###### Controls [in Frame]

To open one of the controls, which you entered on the Tab Controls , by clicking Edit Controls on the Home ribbon tab, select the name of the control on the submenu.

The command also shows the controls you entered by selecting Tools &gt; Edit Controls [material flow objects] in the dialog of an object.

The context menu only shows the menu item Controls if you actually did enter one or several controls.

<!-- image -->

**See also**

Tab Controls [general description]

Edit Controls [material flow objects]

###### Create Sensor [in Frame]

To create a new sensor on the length-oriented object, click at the rough position at which you would like to insert the sensor with the right mouse button and select this command. Enter the precise position and the remaining data defining to the sensor into the dialog that opens.

<!-- image -->

<!-- image -->

To open the sensor at a later point in time, click it with the right mouse button and select Open Sensor .

To delete the sensor at a later point in time, click it with the right mouse button and select Delete Sensor [in Frame] . To delete the sensor in 3D, press Del on your keyboard.

<!-- image -->

Instead, you can also click Sensors [general description] in the dialog of the object.

**Create Tugger Train [2D]**

###### Create Tugger Train [2D]

To create a tugger train , right-click the first and the last Transporter , which you would like to hitch to each other, and select this command.

The tractor and all trailers do not have to touch, as long as all Transporters are located in their entirety on the same Track . If necessary Plant Simulation moves the other Transporters up to the frontmost Transporter or to the tractor .

<!-- image -->

**See also**

Model a Tugger Train

###### Delete Sensor [in Frame]

To delete a sensor from a length-oriented object, select the sensor with the right mouse button and select this command. To delete the sensor in 3D, press Del on your keyboard.

<!-- image -->

###### Deactivate

To deactivate the selected object, select this command. This command clears the check box Active of the objects.

For the ShiftCalendar it looks like this:

<!-- image -->

You can activate the selected object with the command Activate .

###### Down One Level

To close the open Frame and open the Frame which is located within the Frame for which you selected Down one Level in your hierarchically structured simulation model, select this command.

<!-- image -->

**Edit Display Panel [in Frame]**

###### Edit Display Panel [in Frame]

To edit the Display Panel of the selected object, select this command.

You can add a New [display panel] Display Panel [object] item, or Edit [display panel item] or Delete [display panel item] an existing item.

**Note**

3D models do not provide this command as they do not show display panels .

<!-- image -->

###### Edit Dialog [in Frame]

To edit the Dialog you created, select this command.

<!-- image -->

**Edit Icons [in Frame]**

###### Edit Icons [in Frame]

To open the Icon Editor , select this command. You can then edit, delete, or add new icons to the selected object or model.

**Note**

In a 2D Only model you can open the Icon Editor by pressing Ctrl+Shift+I .

<!-- image -->

###### Edit User-defined Attributes [in Frame]

To open the dialog User-defined Attributes , select this command. You can then edit, delete, or add new user-defined attributes to the selected object or to the Frame .

<!-- image -->

**See also**

User-defined Attributes [general description]

###### Event Debugger [in Frame]

Event Debugger [in Frame]

To open the dialog box of the EventDebugger , select this command.

See also

Dialog Box of the Event Debugger

###### Next Icon [in Frame]

To change to the next icon of the selected object, select this command.

<!-- image -->

**Open [in Frame]**

###### Open [in Frame]

To open the dialog box of the selected object, select this command.

<!-- image -->

Instead, you can also double-click the icon of the object in the Frame window.

###### Open Class [in Frame]

To open the class of the selected object in the Class Library , select this command.

<!-- image -->

When you select the command Open Class for an instance of an object, Plant Simulation moves up in the inheritance structure until it reaches an object in the Class Library . It then opens this object.

<!-- image -->

**Open Comment Window**

###### Open Comment Window

To open a window that only shows the text which you typed into the Comment , without formatting and editing options, select this command.

<!-- image -->

**See also**

Text [text box] - Comment

Comment [object]

<!-- image -->

<!-- image -->

###### Open Debugger

To open the Method Debugger at the suspended line of code, select this command.

If the Method is suspended, Plant Simulation opens the Watch Window instead and highlights all lines of code for this Method there.

Compare the ribbon tab Debugger &gt; Suspended Methods .

###### Open External Connections List

To open the list, which shows the paths of the external connections in the Frame in which you inserted the Interface object, select this command.

The column Connector shows the Connector at the exit of the Frame . The column Object shows the name of the succeeding object.

<!-- image -->

<!-- image -->

Instead, you can also select View &gt; External Connections in the dialog of the Interface.

###### Open Origin [in Frame]

To open the class from which the selected object was derived, select this command.

<!-- image -->

###### Open Sensor

To open the dialog of the selected sensor of the length-oriented object, select this command.

<!-- image -->

###### Open Values Table

To open the TimeSequence object that contains the current sequence of Values of the Trigger , select this command.

<!-- image -->

**See also**

Values [Trigger]

<!-- image -->

**Open Without Control**

###### Open Without Control

To open the dialog of the object without calling the Open Control , select this command. This does not apply if the Open Control is an encrypted user-defined attribute of type method .

To prevent the Open Control from being executed, you can also hold down Alt while double-clicking the icon of the object.

See also

Open Control

###### Previous Icon [in Frame]

To return to the previously displayed icon of the selected object, select this command.

<!-- image -->

**Rename [in Frame]**

###### Rename [in Frame]

To enter a new name for the selected object, select this command.

<!-- image -->

Instead, you can also select Home &gt; Rename [Home ribbon] in the Frame window or press F2 .

###### Reorder Successors

To reorder the sequence of the successors of the selected object, select this command. This way you can change the order of the Connectors without having to delete these and reconnect the objects.

<!-- image -->

**Note**

The sequence of the successors affects how the parts are transported through your simulation model. Plant Simulation establishes the sequence of the Connector when you connect the objects which you inserted into a Frame .

To move the selected object up in the sequence of the successors, click Up .

To move the selected object down in the sequence of the successors, click Down .

To delete the Connector from the selected object to its successor, click Delete or press the Delete key. This is helpful if you cannot see the Connectors because the objects are placed so close that they touch each other.

**Note**

The command does not affect instances of the selected object.

<!-- image -->

###### Reset Simulation [in Frame]

To reset your simulation model, click the button on the mini toolbar .

<!-- image -->

Instead, you can also click Reset Simulation [EventController] in the dialog of the EventController or on the Home Ribbon Tab .

<!-- image -->

**Run [Method in Frame]**

###### Run [Method in Frame]

To run the source code of the Method , select this command.

<!-- image -->

Instead, you can also select Run [button] - Method on the Run menu of the Method or press F5 .

###### Show [in Frame]

To show the display window of the AttributeExplorer , the HtmlReport , or the Chart , select this command.

<!-- image -->

###### Show Assigned Objects [in Frame]

Show Assigned Objects [in Frame]

To select the objects which are assigned to the LockoutZone or to the ShiftCalendar as resources in the Frame , select this command.

<!-- image -->

Instead, you can also select View &gt; Show Assigned Objects [LockoutZone] in the dialog of the LockoutZone or the ShiftCalendar .

###### Show Attributes and Methods [in Frame]

To show the attributes and methods of the instance of the object class, which you inserted into the Frame , select this command.

<!-- image -->

Instead, you can also press the F8 key or click Show Attributes and Methods [Home ribbon] on the Home Ribbon Tab .

**Show Dialog [in Frame]**

###### Show Dialog [in Frame]

To show the Dialog with the dialog items you created, select this command.

<!-- image -->

###### Show Exported Services

To open the list that shows all services which the Exporter exports at this time, select this command.

<!-- image -->

<!-- image -->

Instead, you can also select View &gt; Exported Services [Exporter] in the dialog of the Exporter .

**Show External Connected Objects**

###### Show External Connected Objects

To select the objects in the Frame in which they are inserted and which are connected to the Interface. object, select this command. If the Frame is closed, Plant Simulation also opens the Frame .

<!-- image -->

Instead, you can also select View &gt; External Connections in the dialog of the Interface

###### Show Sessions Log

To show the sessions log of the MQTT interface , select this command.

Instead, you can also click the Tab Session Log in the dialog of the MQTT interface .

###### Show Statistics Report [in Frame]

To show statistics of the selected object in the Statistics Report , select this command or press F6 .

<!-- image -->

To show statistics of several objects, select them ( Shift +click or drag a marquee over them) and press F6 .

To add one or several objects to an open report, select it/them and press F6 .

The report adds statistics of the objects, which you selected to the drop-down list. To jump to any of the topics, which interest you, select that topic from the drop-down list:

<!-- image -->

Then the report just shows the page with this topic in the display window. To just print this topic, click Print this page . To show all topics shown in the Report window, click Show all . To print the entire report, click Print .

To save the report as an HTML file (*.htm or *.html) or as a text file (*.txt) click Save . Enter a name for the file and select the folder into which you want to save it.

To update the report with the current values, click Refresh .

To print the report, click Print .

Instead, you can also select View &gt; Statistics Report in the dialog of the objects.

See also

Statistics Report [described]

showStatisticsReport [SimTalk]

Viewing the Statistics Report

**Show Structure [in Frame]**

###### Show Structure [in Frame]

To show the internal structure of the selected object, on which parts can be located, select this command. The dialog Structure then shows the parts/objects which are located on the material flow object or are loaded onto the Container or the Transporter .

<!-- image -->

###### Start/Stop Simulation [in Frame]

To start the simulation run, click the button on the mini toolbar . To stop the simulation after the active simulation event has been processed, select this command again.

<!-- image -->

Instead, you can also click Start/Stop Simulation [EventController] in the dialog of the EventController or on the Home Ribbon Tab .

**Start Fast Forward Simulation [in Frame]**

###### Start Fast Forward Simulation [in Frame]

To start the simulation run without the animation of MUs and States , click the button on the mini toolbar .

<!-- image -->

###### Statistics Wizard [in Frame]

To open the Statistics Wizard of the Chart , select this command.

<!-- image -->

<!-- image -->

**Type Info [in Frame]**

###### Type Info [in Frame]

To open a table that shows all methods and attributes of the active ActiveX control , select this command.

<!-- image -->

Instead, you can also select View &gt; Type Info [ActiveX] in the dialog of the ActiveX control .

###### Update [in Frame]

To update the displayed Sankey flows of the Sankey Diagram with the current values, select this command.

<!-- image -->

**SimTalk**

SankeyDiagram [object]

update [SimTalk] - SankeyDiagram

#### LEDs and States of the Frame

During the simulation runs Plant Simulation shows the state of the Frame as one or more colored dots in the LED display along the upper border of the icon of the Frame .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Description                                             | LED        | Looks like this   | Attribute                      |
|---------------------------------------------------------|------------|-------------------|--------------------------------|
| The Frame is Failed                                     | red        |                   | Failed [SimTalk] - Frame       |
| The Frame is Stopped                                    | pink       |                   | Stopped [SimTalk] - Frame      |
| The Frame is Paused                                     | blue       |                   | Pause [SimTalk] - Frame        |
| The Frame is Unplanned                                  | light blue |                   | Unplanned [SimTalk] - Frame    |
| The Frame is Working                                    | green      |                   | StateWorking [SimTalk]         |
| The Frame is Blocked                                    | yellow     |                   | StateBlocked [SimTalk]         |
| The Frame is Setting-Up                                 | brown      |                   | StateSetup [SimTalk]           |
| The Entrance of the Frame is closed                     | cyan       |                   | StateEntryShut [SimTalk]       |
| The Frame is Waiting for services and/or mounting parts | orange     |                   | StateResourceMissing [SimTalk] |

3D shows the states, that correspond to the LEDs in 2D, in the state graphic.

See also

Tab States &gt; State Graphic in 3D

LEDs and States of the Material Flow Objects

LEDs and States the Mobile Objects

LEDs and States of the Energy Features

LEDs and States of the Exporter

LEDs and States of the Method

**Methods of the Frame**

#### \_Methods of the Frame

The Frame provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.

##### \_Methods of the Frame

- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

copyBitmapToClipboard [SimTalk] - Frame

Copies the specified part of the window of the Frame designated by &lt;Path&gt; to the clipboard as a bitmap.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.copyBitmapToClipboard(X:integer, Y:integer, Width:integer, Height:integer)

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the bitmap.
- The parameter Y of data type integer designates the y-coordinate of the bitmap.
- The parameter Width of data type integer designates the width of the bitmap.
- The parameter Height of data type integer designates the height of the bitmap.

As the height and the width up to which objects are positioned in the Frame cannot be easily determined, you cannot specify any parameters. Then Plant Simulation copies the bitmap starting at the top left corner, i.e., the coordinates (0,0), up to the coordinates that the objects have.

**Example**

current.copyBitmapToClipboard(200,200,130,70)

**SimTalk**

copyBitmapToFile [SimTalk] - Frame

##### copyBitmapToFile [SimTalk] - Frame

copyBitmapToFile [SimTalk] - Frame

Copies the graphic of the window of the Frame designated by &lt;Path&gt; to a file as a .png file.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

```simtalk
< Path >.copyBitmapToFile(FileName:string[, X:integer, Y:integer, Width:integer, Height:integer]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the file to which Plant Simulation writes the .png file.
- The optional parameter X of data type integer designates the x-coordinate of the bitmap on your computer's screen.
- The optional parameter Y of data type integer designates the y-coordinate of the bitmap.
- The optional parameter Width of data type integer designates the width of the bitmap.
- The optional parameter Height of data type integer designates the height of the bitmap.

If you do not specify the optional parameters, Plant Simulation automatically computes the size of the bitmap.

Return Value

The return value has the data type boolean .

**Example**

.Models.Model.copyBitmapToFile("myBackgroundImage",200,200,130,70)

**SimTalk**

copyBitmapToClipboard [SimTalk] - Frame

##### drawEllipse [SimTalk]

Draws an ellipse on the background of the Frame designated by &lt;Path&gt;.

**Remarks**

Note

A 3D Only model does not provide this method.

To draw the ellipse in the foreground , i.e., in front of the objects in the Frame , specify a negative number for the layer, designated by the parameter integer .

Type

Method

Syntax

```simtalk
< Path >.drawEllipse(Layer:integer, X:integer, Y:integer, Width:integer, Height:integer, RGB:integer, LineWidth:integer)
```

**Parameters**

| Parameter of data type integer   | Description                                                                                                                                                                                     |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Layer                            | Designates the layer.                                                                                                                                                                           |
| X                                | Designates the x-coordinate of the top left corner of the bounding rectangle of the ellipse.                                                                                                    |
| Y                                | Designates the y-coordinate of the top left corner of the bounding rectangle of the ellipse.                                                                                                    |
| Width                            | Designates the width of the ellipse.                                                                                                                                                            |
| Height                           | Designates the height of the ellipse.                                                                                                                                                           |
| RGB                              | Designates the line color of the ellipse.                                                                                                                                                       |
| LineWidth                        | Designates the line width of the outline of the ellipse in pixels. Enter -1 to draw a filled ellipse. If you do not want to zoom the line of the ellipse, enter a LineWidth of 0 instead of 1 . |

**Example**

.Models.Model.drawEllipse(2,13,34,58,17,200,2)

SimTalk

eraseAllLayers [SimTalk]

eraseLayer [SimTalk]

makeRGBValue [SimTalk]

See also

Draw Ellipse [vector graphic]

Draw Vector Graphics or Text onto the Background of the Frame in 2D

##### drawLine [SimTalk]

Draws a line on the background of the Frame designated by &lt;Path&gt;.

**Remarks**

Note

A 3D Only model does not provide this method.

To draw the line in the foreground , i.e., in front of the objects in the Frame , specify a negative number for the layer, designated by the parameter integer .

Type

Method

Syntax

```simtalk
< Path >.drawLine(Layer:integer, X1:integer, Y1:integer, X2:integer, Y2:integer, RGB:integer, LineWidth:integer[, LineStyle:integer])
```

**Parameters**

| Parameter of data type integer   | Description                                                                                                                                                                                                 |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Layer                            | Designates the layer.                                                                                                                                                                                       |
| X1                               | Designates the starting point of the line on the x-axis.                                                                                                                                                    |
| Y1                               | Designates the starting point of the line on the y-axis.                                                                                                                                                    |
| X2                               | Designates the end point of the line on the x-axis.                                                                                                                                                         |
| Y2                               | Designates the end point of the line on the y-axis.                                                                                                                                                         |
| RGB                              | Designates the color of the line.                                                                                                                                                                           |
| LineWidth                        | Designates the width of the pen in pixels of the line. When you use the line width 0, Plant Simulation always draws the line with a width of 1. This also applies when you zoom the contents of the Frame . |
| LineStyle                        | Designates the line style of the line. -1 looks like this .                                                                                                                                                 |

**drawLine [SimTalk]**

| Parameter of data type integer   | Description                                                                                                                                                                                                                                                                                                                                                                                                    |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                  | -2 looks like this . 0 stands for a solid line . 1 stands for a dashed line . 2 stands for a dotted line . 3 stands for a dash dot line . 4 stands for a dash dot dot line . For the line styles with the number 1 to 4 the operating system only permits a line width of 1 or 0. For a line width of 1 Plant Simulation always draws the line style as a solid line when you zoom the contents of the Frame . |

**Example**

.Models.Model.drawLine(1,8,15,58,17,166,4,0)

SimTalk

eraseAllLayers [SimTalk]

eraseLayer [SimTalk]

makeRGBValue [SimTalk]

See also

Draw Line [vector graphic]

Draw Vector Graphics or Text onto the Background of the Frame in 2D

##### drawRectangle [SimTalk]

Draws a rectangle on the background of the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this method.

To draw the rectangle in the foreground , i.e., in front of the objects in the Frame , specify a negative number for the layer, designated by the parameter integer .

Type

Method

Syntax

```simtalk
< Path >.drawRectangle(Layer:integer, X:integer, Y:integer, Width:integer, Height:integer, RGB:integer, LineWidth:integer[, Gradient:integer])
```

**Parameters**

| Parameter of data type integer   | Description                                                                                                                                                                                              |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Layer                            | Designates the layer.                                                                                                                                                                                    |
| X                                | Designates the position of the rectangle on the x-axis.                                                                                                                                                  |
| Y                                | Designates the position of the rectangle on the y-axis.                                                                                                                                                  |
| Width                            | Designates the width of the rectangle.                                                                                                                                                                   |
| Height                           | Designates the height of the rectangle.                                                                                                                                                                  |
| RGB                              | Designates the line color of the rectangle.                                                                                                                                                              |
| LineWidth                        | Designates the line width of the outline of the rectangle in pixels. Enter -1 to draw a filled rectangle. If you do not want to zoom the outline of the rectangle, enter a LineWidth of 0 instead of 1 . |
| Gradient                         | Designates the color gradient for filled rectangles: 0 stands for None                                                                                                                                   |

| Parameter of data type integer   | Description                                                                                                 |
|----------------------------------|-------------------------------------------------------------------------------------------------------------|
|                                  | 1 stands for Top To Bottom 2 stands for Bottom To Top 3 stands for Left To Right 4 stands for Right To Left |

**Example**

.Models.Model.drawRectangle(3,30,30,80,40,133,1)

**SimTalk**

eraseAllLayers [SimTalk]

eraseLayer [SimTalk]

makeRGBValue [SimTalk]

See also

Draw Rectangle [vector graphic]

Draw Vector Graphics or Text onto the Background of the Frame in 2D

##### drawText [SimTalk]

Draws the text, which you specify as the parameter of data type string , on the background of the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this method.

To draw the text in the foreground , i.e., in front of the objects in the Frame , specify a negative number for the layer, designated by the parameter integer .

Syntax

```simtalk
< Path >.drawText(Layer:integer, X:integer, Y:integer, RGB:integer, FontSize:integer, Text:string)
```

Type

Method

Parameters

| Parameter of data type integer   | Description                                        |
|----------------------------------|----------------------------------------------------|
| Layer                            | Designates the layer.                              |
| X                                | Designates the position of the text on the x-axis. |
| Y                                | Designates the position of the text on the y-axis. |
| RGB                              | Designates the color of the text.                  |
| FontSize                         | Designates the size of the text in points.         |

The parameter Text of data type string designates the text proper that Plant Simulation draws.

Example

current.drawText(4,48,15,80,18,"Forge in plant anytown, MyTown")

SimTalk

eraseAllLayers [SimTalk]

**drawText [SimTalk]**

eraseLayer [SimTalk]

makeRGBValue [SimTalk]

See also

Draw Textbox

Draw Vector Graphics or Text onto the Background of the Frame in 2D

##### eraseAllLayers [SimTalk]

Deletes all vector graphics on all layers in the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this method.

eraseAllLayers applies to vector graphics, which you drew manually or inserted with the methods drawEllipse , drawLine , drawRectangle , and drawText .

Type

Method

Syntax

&lt; Path &gt;.eraseAllLayers

Example

current.eraseAllLayers

SimTalk

drawEllipse [SimTalk]

drawLine [SimTalk]

drawRectangle [SimTalk]

drawText [SimTalk]

See also

Delete All Layers

##### eraseLayer [SimTalk]

eraseLayer [SimTalk]

Deletes all vector graphics on a single layer in the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this method.

eraseLayer applies to vector graphics, which you drew manually or inserted with the methods drawEllipse , drawLine , drawRectangle , and drawText .

Use the method eraseAllLayers to delete all vector graphics on all layers.

Type

Method

Syntax

&lt; Path &gt;.eraseLayer(Layer:integer)

Parameter

The parameter Layer of data type integer designates the layer.

Example

current.eraseLayer(-3) // deletes all vector graphics on layer -3

SimTalk

drawEllipse [SimTalk]

drawLine [SimTalk]

drawRectangle [SimTalk]

drawText [SimTalk]

eraseAllLayers [SimTalk]

**See also**

###### Delete Layer

**getHTMLCode [SimTalk] - Frame**

##### getHTMLCode [SimTalk] - Frame

Returns the contents of the Frame designated by &lt;Path&gt; as HTML code of a pixel-based graphic and assigns it to the passed parameters.

Type

Method

Syntax

```simtalk
< Path >.getHTMLCode([Caption:string, Width:integer, Height:integer, SizeInPercent:string, CameraPositionX:real, CameraPositionY:real, CameraPositionZ:real, CameraRotationX:real, CameraRotationZ:real, CameraRotationX:real, CameraRotationZ:real]) → string
```

**Parameters**

- The optional parameter Caption of data type string designates the desired caption of the graphic. If you specify the caption, Plant Simulation shows the graphic with this caption.
- The optional parameter Width of data type integer designates the desired Width of the graphic. If you do not specify the Width and the Height , Plant Simulation uses the width and the height of the 2D view or of the 3D view respectively in which all objects contained in the Frame are visible.
- The optional parameter Height of data type integer designates the desired Height of the graphic. If you do not specify the Width and the Height , Plant Simulation uses the width and the height of the 2D view or of the 3D view respectively in which all objects contained in the Frame are visible.
- The optional parameter SizeInPercent of data type string designates the desired size of the graphic in percent, for example "75%" . You can specify the percentage instead of the parameters for the Width and the Height .
- The optional parameter CameraPositionX of data type real designates the x-axis of the camera position.
- The optional parameter CameraPositionY of data type real designates the y-axis of the camera position.
- The optional parameter CameraPositionZ of data type real designates the z-axis of the camera position. You only have to specify the optional parameters for the CameraPosition if you also specify the optional parameters for the CameraRotation .
- The optional parameter CameraRotationX of data type real designates the rotation of the camera around the x-axis.
- The optional parameter CameraRotationZ of data type real designates the rotation of the camera around the z-axis.

You can also use the optional parameters for the CameraRotation without specifying the CameraPosition .

If you specify the optional parameters for the CameraPosition and/or CameraRotation , you also have to specify the parameters for the Width and the Height or for the SizeInPercent .

**Return Value**

The return value has the data type string .

**Examples**

```simtalk
print MyFrame.getHTMLCode
MyFrame.getHTMLCode("Caption")
MyFrame.getHTMLCode(100, 100) // size in mm
MyFrame.getHTMLCode("Caption", 100, 100) // caption and size in mm
MyFrame.getHTMLCode("75%") // size in percent of the graphic showing all objects
MyFrame.getHTMLCode(*) // as big as necessary to show all objects and shown as big as possible in the HtmlReport
MyFrame.getHTMLCode(100,*) // width in mm, height proportional calculated from the size required to show all objects
MyFrame.getHTMLCode(*, 100) // height in mm, width proportional calculated from the size required to show all objects
MyFrame.getHTMLCode(100%, -1.123, 2.345, -3.456, -45.0, 15.0) // 100% of the size of the graphic showing all objects while specifying CameraPosition and CameraRotation
```

See also

**Display a Frame**

Display a HtmlReport

##### getRepresentationArea [SimTalk]

Returns the parameters of the representation area of the visible objects of the Frame designated by &lt;Path&gt;.

Remarks

Plant Simulation then assigns the parameters to the local variables, which you specify.

Note

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.getRepresentationArea(byRef X:integer, byRef Y:integer, byRef Width:integer, byRef Height:integer)

**Local Variables**

- The local variable X of data type integer , to which the value is assigned, designates the x-coordinate of the representation area.
- The local variable Y of data type integer designates the y-coordinate of the representation area.
- The local variable Width of data type integer designates its width.
- The local variable Height of data type integer designates its height.

**Example**

```simtalk
var x,y,w,h: integer
Frame1.getRepresentationArea(x,y,w,h)
print x," ",y," ",w," ",h
```

SimTalk

setRepresentationArea [SimTalk]

See also

Representation Area X

Representation Area Y Representation Area Width Representation Area Height

##### node [SimTalk] - Frame

node [SimTalk] - Frame

Returns the designated object in the Frame designated by &lt;Path&gt;.

Remarks

Plant Simulation numbers the objects within models in the order in which you insert them. You can also call the method for the Class Library .

Type

Method

Syntax

```simtalk
< Path >.node(ObjectNumberOrName:integer/string) → object
```

Parameter

The parameter ObjectNumberOrName of data type integer designates the number of the object.

The parameter ObjectNumberOrName of data type string designates the name of the object.

If a string is passed, the method returns the object with the name of the parameter. If no such object exists, it returns void.

Return Value

The return value has the data type object .

**Examples**

```simtalk
print .model.node(3) // might, for example,
return .Models.MyPlant.MyStation
// Writes all objects in the Frame and in Sub-frames to the DataTable. // Assign the data type object to the first column.
param Frame: object := void
if Frame = VOID
	Frame := current
end
for var i := 1 to Frame.numNodes
	DataTable[1, DataTable.yDim + 1] := Frame.Node(i)     // object DataTable [2, DataTable.yDim] :=
	Frame.Node(i).Name   // string
	if Frame.Node(i).InternalClassType = "Frame"          // substructure
self.execute(Frame.Node(i))                      // recursive call end next
```

**See also**

node [SimTalk] - folder

NumNodes [SimTalk] - Frame pasteClipboard [SimTalk] - Frame pasteClipboard [SimTalk] - Frame Pastes the contents of the clipboard into the Frame designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.pasteClipboard([TargetTable:table])
```

Parameter

The optional parameter TargetTable of data type table writes all pasted objects to the specified table after it executed the method .

The table has one column of data type object .

Example

```simtalk
var tbl: table
var   i: integer pasteClipboard(tbl)
for var i := 1 to tbl.yDim
	print tbl[1,i]  // outputs all pasted objects
next
```

SimTalk

copyObjectsToClipboard [SimTalk]

See also

Paste Contents of the Clipboard [Home ribbon]

Copy [Home ribbon]

##### rearrange [SimTalk]

Aligns the icons in the Frame designated by &lt;Path&gt; to the grid.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.rearrange

**Example**

.MyModel.rearrange

See also

Align to Grid [icons 2D]

selectContents [SimTalk]

Selects all objects located in the Frame designated by &lt;Path&gt; ( true ) or deselects them ( false ).

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.selectContents(SelectAllObjects:boolean) -&gt; boolean

Parameter

The parameter SelectAllObjects of data type boolean sets if all objects will be selected ( true ) or deselected ( false ).

Return Value

The return value has the data type boolean .

Example

frame2.selectContents(true)

See also

Select All [Home ribbon]

##### selectionToClipboard [SimTalk]

Copies the selected objects, compare selectContents , in the Frame designated by &lt;Path&gt; to the clipboard.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.selectionToClipboard

**Example**

```simtalk
var tab: table[object] selectContents(true) selectionToClipboard current.~.frame2.pasteClipboard(tab) tab[1,1].ProcTime := 120 // sets the parameters of pasted objects
```

SimTalk

copyObjectsToClipboard [SimTalk]

See also

selectContents [SimTalk]

Copy [Home ribbon]

**setBackgroundImage [SimTalk]**

##### setBackgroundImage [SimTalk]

Sets the image designated by the parameters as the background image of the Frame designated by &lt;Path&gt;.

Remarks

**Note**

A 3D Only model does not provide this method.

**Note**

setBackgroundImage applies to the icon of the addressed instance of the Frame , not to icon of the object class.

Type

Method

Syntax

```simtalk
< Path >.setBackgroundImage(FileName:string[, ScalingFactor:real, XOrigin:integer, YOrigin:integer]) → boolean
```

**Parameters**

- The parameter FileName of data type string designates the name of the image file.
- When you designate an AutoCad or a Microstation file in the formats DWG or DXF, you can enter:
- The scaling factor ScalingFactor as the optional parameter of data type real . When you use the same units in AutoCad/Microstation and Plant Simulation , you will enter the scaling factor 1 . When you use different units, you have to enter a scaling factor that takes the conversion factor into account.
- The x-coordinate of the origin as the optional parameter XOrigin of data type integer .
- The y-coordinate of the origin as the optional parameter YOrigin of data type integer .

**Return Value**

The return value has the data type boolean .

**Example**

```simtalk
var x, y: integer
MyFrame.setBackgroundImage("myDWGfile.dwg",1.0, x,y)
```

**See also**

**Add a Graphic and a Color to the Background of the 2D Frame**

##### setRepresentationArea [SimTalk]

Sets the parameters of the visible objects of the Frame object designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this method.

Note

The axes origin always has to be located within the representation area.

Type

Method

Syntax

&lt; Path &gt;.setRepresentationArea(X:integer, Y:integer, Width:integer, Height:integer)

Parameters

The parameters designate the pixel coordinates.

The x-y coordinates designate the top left corner of the representation area.

- The parameter X of data type integer designates the x-coordinate of the representation area.
- The parameter Y of data type integer designates the y-coordinate.
- The parameter Width of data type integer designates the width of the representation area.
- The parameter Height of data type integer designates the height of the representation area.

**Example**

Frame1.setRepresentationArea(500,100,15,25)

SimTalk

getRepresentationArea [SimTalk]

See also Representation Area X Representation Area Y Representation Area Width Representation Area Height

**setXYOrigin [SimTalk]**

##### setXYOrigin [SimTalk]

Sets the zero point for scrolling in the Frame designated by &lt;Path&gt;. setXYOrigin applies if the contents does not fit in the viewable area.

Remarks

A 3D Only model does not provide this method.

Type

Method

Syntax

&lt; Path &gt;.setXYOrigin(X:integer, Y:integer)

**Parameters**

- The parameter X of data type integer designates the x-coordinate of the zero point for scrolling.
- The parameter Y of data type integer designates its y-coordinate.

**Example**

- .frame2.setXYOrigin(45,59)

##### statistics [SimTalk] - Frame

Returns the statistics of all material flow objects collecting statistical data of the Frame designated by &lt;Path&gt;.

Remarks

Also applies for objects on lower levels of the model, i.e., models within models.

Type

Method

Syntax

```simtalk
< Path >.statistics < Path >.statistics(NameOfTable:table_path) < Path >.statistics(FileName:string[, CodePage:string:="UTF-8"])
```

**Parameters**

- Specify the parameter NameOfTable of data type table\_path to write the data to that table.
- Specify the parameter FileName of data type string to write the table to that file. Plant Simulation will overwrite existing entries.

Specify a filename and use the optional parameter CodePage of data type string to set the encoding you want to use: ANSI , UTF-8 , or Unicode .

**Default Value of the Parameter**

If you do not specify this parameter, the encoding UTF-8 is used as default value.

**Example**

```simtalk
building12.statistics                             // outputs to the screen .plant.statistics(stat_tab)                       // outputs to a table
MySubFrame.statistics("C:\temp\statistics1.txt")  // outputs to a file
```

#### Read-Only Attributes of the Frame

\_Read-Only Attributes of the Frame

The Frame provides:

- The read-only attributes listed in the table of contents to the left.

- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print .Models.Model.Capacity

##### Capacity [SimTalk] - Frame

Returns the capacity of all static material flow objects located in the Frame designated by &lt;Path&gt;.

Remarks

Plant Simulation does not include the capacities of MUs . When you place additional models into the selected model, Plant Simulation adds their capacities. If you insert at least one object with unlimited capacity, such as a Conveyor with a capacity of -1 in the Frame , Plant Simulation returns -1.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Capacity → integer
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
print .Models.MyPlant.Capacity
```

EventController [SimTalk] - Frame

Returns the EventController that is located in the root Frame .

Type

Read-only attribute

Syntax

```simtalk
EventController → object
```

Return Value

The return value has the data type object .

Example

```simtalk
print EventController // returns for example .Models.Model.EventController
```

See also

EventController [object]

##### NumberOfLimitedObjects [SimTalk]

Counts the number of inserted objects per Frame containing an EventController .

**Remarks**

Plant Simulation does not count the following objects: Lists and Tables , Methods , Variables , Comments , MUs , Connectors , Interfaces , EventControllers , the Toolbar , Folders , and Class objects .

**Note**

NumberOfLimitedObjects applies to the Standard license , the Educational license , the Foundation license , and to the Student license .

| License name        |   number of allowed objects |
|---------------------|-----------------------------|
| Standard license    |                        4000 |
| Educational license |                        1000 |
| Foundation license  |                         500 |
| Student license     |                          80 |

For the Student license Plant Simulation shows the number of the objects inserted into this Frame next to the name of the Frame and the maximum number of allowed objects for the Student license in the Class Library .

**Note**

Plant Simulation only shows the value for Frames into which you inserted an EventController .

For a model that you created with a Student license it might look like this:

**Type**

Read-only attribute

Syntax

```simtalk
NumberOfLimitedObjects → integer
```

**Return Value**

The return value has the data type integer .

**Example**

```simtalk
print NumberOfLimitedObjects // returns 10 for the Frame named 'Model'
```

**SimTalk**

numOfLimitedObjects [SimTalk]

See also

Start Plant Simulation with Different Kinds of Licenses NumNodes [SimTalk] - Frame Returns the number of objects in the Frame designated by &lt;Path&gt;.

<!-- image -->

Remarks

Each additional Frame you insert into the selected Frame counts as a single object. Plant Simulation does not count the objects contained within the Frames .

Connectors also count as objects.

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumNodes → integer

Return Value

The return value has the data type integer .

Example

```simtalk
print .Models.MyPlant.NumNodes
```

See also

node [SimTalk] - Frame

#### Attributes of the Frame

\_Attributes of the Frame

The Frame provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the Frame , open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute by assigning values to the respective attributes and you can get its value:

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
Frame.StateBlocked := true
print .Models.Model.BackgroundColor
posit := MyStation.Cont.XPos
```

##### AxesOrigin [SimTalk]

Sets x-coordinate and the y-coordinate of the 3D origin, i.e., the reference point of the representation area of the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

**Note**

To hide the red crosshairs, specify 0 for both values of the axes origin.

Type

Attribute

Syntax

&lt; Path &gt;.AxesOrigin:array

Assignment Value

You can assign an array of data type integer with two values.

Example

```simtalk
MyPlant.AxesOrigin := [400,450]
```

See also

Axes Origin X/Y

BackgroundColor [SimTalk] - Frame

Sets the background color of the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

Set the RGB values of the color with the method makeRGBValue .

Type

Attribute

Syntax

&lt; Path &gt;.BackgroundColor:integer

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.Models.Model.BackgroundColor := makeRGBValue(100,100,100) .Models.Model.BackgroundColor := 6579300 // is the same as the color above
```

SimTalk

makeRGBValue [SimTalk]

See also

Background Color [Frame]

##### Failed [SimTalk] - Frame

Fails the Frame designated by &lt;Path&gt; ( true ) or does not fail it ( false ).

Remarks

The Frame shows a red dot in the LED area of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.Failed:boolean

Watchable

The attribute is watchable and Plant Simulation calls a control.

Assignment Value

You can assign a value of data type boolean .

**Note**

During the reset phase of the simulation Plant Simulation resets all failures.

Example

subFrame.failed := true

See also

LEDs and States of the Frame

Failed [check box] - material flow objects

<!-- image -->

##### LockStructure [SimTalk]

LockStructure [SimTalk]

Locks the structure of the Frame designated by &lt;Path&gt; ( true ) or unlocks it ( false ).

Remarks

LockStructure is deactivated by default, meaning that the Frame is unlocked so that you can create your model in it.

<!-- image -->

When you activate Lock Structure , Plant Simulation prevents unintentional changes, i.e., inserting, deleting, and changing of objects. You can then neither change the position of objects nor their name.

Lock Structure is activated in instantiated Frames by default. This helps to prevent unintentional changes to the structure of an instance, although this change should apply to all instances and should thus be made in the class.

Type

Attribute

Syntax

&lt; Path &gt;.LockStructure:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.frame2.LockStructure := true
print .frame2.LockStructure
```

See also

Lock Structure [Frame ribbon]

**Pause [SimTalk] - Frame**

Pauses the Frame designated by &lt;Path&gt; ( true ) or does not pause it ( false ).

Remarks

The Frame shows a blue dot in the LED area of the icon

<!-- image -->

Plant Simulation resets the pause, when you reset the EventController .

Type

Attribute

Syntax

&lt; Path &gt;.Pause:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
EngineAssembly.Pause := true
```

See also

Pause Material Flow Objects and Frames

Paused Frames

LEDs and States of the Frame ReplacementMode [SimTalk]

Sets the replacement mode for the Frame designated by &lt;Path&gt;.

Remarks

The replacement mode of the replacing Frame determines if the Frames are merged or replaced. The replacement mode of the replaced Frame does not have any consequences.

Type

Attribute

Syntax

&lt; Path &gt;.ReplacementMode:string

Assignment Value

You can assign a value of data type string .

You can specify "exchange" or "merge"

Example

Frame1.ReplacementMode := "merge"

SimTalk

loadObjectAs [SimTalk]

replace [SimTalk]

writeObject [SimTalk]

See also

Replacement Mode

Load Object

##### RepresentationMode [SimTalk]

Sets the representation mode of the Frame designated by &lt;Path&gt;.

Remarks

<!-- image -->

The value of data type string designates the representation mode.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.RepresentationMode:string

**Assignment Value**

You can assign a value of data type string .

You can specify "Icon" , "Contents" , or "Contents with background" .

Example

```simtalk
MyFrame.RepresentationMode := "Contents"
```

See also

Representation Mode

##### RotateMUs [SimTalk] - Frame

Rotates the icons of the MUs in the Frame designated by &lt;Path&gt; ( true ) or does not rotate them ( false ).

**Remarks**

Plant Simulation then matches the rotation of the point-oriented material flow object , when the parts transfer onto a rotated object as they move across any of the material flow objects.

**Note**

A 3D Only model does not provide this attribute.

**Note**

A rotation triggered by Same as the Object ( RotateMUs ) on a point-oriented object only has an effect as long as the part is located on this object. When leaving the object the part again assumes the rotation it had before. When entering a new object, the part considers the rotation of this new object when Same as the Object is active.

<!-- image -->

**Note**

If Plant Simulation shows a length-oriented object in curve mode, Plant Simulation evaluates the setting Rotate Movables / RotateMovables .

<!-- image -->

**Note**

We advise to not deactivate Rotate Movables as this setting does not affect the behavior in 3D .

**Note**

For Transporter and Container this applies: When Same as the Object is true , loaded parts are rotated in the same direction as Transporter or Container .

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.RotateMUs:boolean

**Assignment Value**

You can assign a value of data type boolean .

Specify true to rotate the part to match the rotation of the material flow object.

Specify false to make the part keep its previous rotation/direction.

**Example**

```simtalk
MyFrame.RotateMUs := true
```

SimTalk

RotateMUs [SimTalk] - material flow objects

RotateMovables [SimTalk]

**ScalingFactor [SimTalk]**

**ScalingFactor [SimTalk]**

Sets the ScalingFactor for displaying the objects in the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

Plant Simulation uses the scaling factor for converting the pixel coordinates to length coordinates.

**Note**

When you change the Scaling Factor , Plant Simulation keeps the lengths of the length-oriented objects and the 3D coordinates and changes the dimension or the representation of the pixels respectively. Plant Simulation moves the axes origin if your change would create negative pixel coordinates.

**Note**

If one or more Frames in the hierarchy of Frames use Icon Animation and connected animation points, the parts are only animated correctly if all Frames use the same Scaling Factor .

Type

Attribute

Syntax

&lt; Path &gt;.ScalingFactor:real

Assignment Value

You can assign a value of data type real .

Example

MyFrame.ScalingFactor := 1

See also

Scaling Factor [2D only]

##### ShiftCalendarObject [SimTalk] - Frame

Sets the ShiftCalendar , which controls the shifts worked in the Frame designated by &lt;Path&gt;.

Syntax

&lt; Path &gt;.ShiftCalendarObject:path

Assignment Value

You can assign a value of data type object/path .

Example

EngineAssembly.ShiftCalendarObject := MyShiftCalendar

**See also**

**Select Shift Calendar**

##### ShowDisplayPanels [SimTalk]

Shows ( true ) or hides ( false ) all display panels of the objects in the Frame designated by &lt;Path&gt;.

Remarks

Note

A 3D Only model does not provide this attribute.

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

Type

Attribute

Syntax

&lt; Path &gt;.ShowDisplayPanels:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyPlantAnytown.ShowDisplayPanels := true

See also

Display Panel [object]

Show Display Panels [model settings]

##### ShowObjectLabels [SimTalk]

Shows the labels of the objects in the Frame designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

**Note**

A 3D Only model does not provide this attribute.

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

Type

Attribute

Syntax

&lt; Path &gt;.ShowObjectLabels:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyPlantAnytown.showobjectlabels := true .Models.MyPlantAnytown.ShowObjectNames := false
```

See also

Label [general description]

Show Object Labels [model settings]

##### ShowObjectNames [SimTalk]

ShowObjectNames [SimTalk]

Shows the names of the objects in the Frame designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

Note

A 3D Only model does not provide this attribute.

**Note**

If you change this View Option , Plant Simulation changes this setting in the class from which this setting is inherited.

If you only want to change the setting in the local instance, you have to deactivate inheritance first

<!-- image -->

.

Type

Attribute

Syntax

&lt; Path &gt;.ShowObjectNames:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyPlantAnytown.showobjectlabels := false .Models.MyPlantAnytown.ShowObjectNames := true
```

See also

Name [general description]

Show Object Names [model settings]

##### StateBlocked [SimTalk]

Sets the state of the Frame designated by &lt;Path&gt; to blocked ( true ) or not blocked ( false ).

Remarks

The Frame shows a yellow dot in the LED area of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.StateBlocked:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Frame.StateBlocked := true

See also

LEDs and States of the Frame

Blocked [state, material flow objects]

<!-- image -->

**StateEntryShut [SimTalk]**

##### StateEntryShut [SimTalk]

Sets the state of the Frame designated by &lt;Path&gt; to entrance closed ( true ) or not closed ( false ).

Remarks

The Frame shows a light blue dot in the LED area of the icon.

<!-- image -->

The Frame only shows this state if the Recovery Time is active.

Type

Attribute

Syntax

&lt; Path &gt;.StateEntryShut:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Frame.StateEntryShut := true

See also

LEDs and States of the Frame

Recovery Time [general description]

##### StateResourceMissing [SimTalk]

Sets the state of the Frame designated by &lt;Path&gt; to resource missing/waiting for an Exporter ( true ) or not missing ( false ).

Remarks

The Frame shows an orange dot in the LED area of the icon.

<!-- image -->

This state applies when the Frame is waiting for resources, i.e., for services or MUs .

Type

Attribute

Syntax

&lt; Path &gt;.StateResourceMissing:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Frame.StateResourceMissing := true

See also

LEDs and States of the Frame

Waiting [state, material flow objects]

##### StateSetup [SimTalk]

StateSetup [SimTalk]

Sets the state of the Frame designated by &lt;Path&gt; to setting-Up ( true ) or not setting-up ( false ).

Remarks

The Frame shows a brown dot in the LED area of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.StateSetup:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
Frame.StateSetup := true
```

See also

LEDs and States of the Frame

Setting-Up [state, material flow objects]

<!-- image -->

##### StateWorking [SimTalk]

Sets the state of the Frame designated by &lt;Path&gt; to working ( true ) or not working ( false ).

Remarks

The Frame shows a green dot in the LED area of the icon.

Syntax

```simtalk
< Path >.StateWorking:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
Frame.StateWorking := true
```

See also

LEDs and States of the Frame

Working [state, material flow objects]

<!-- image -->

##### Stopped [SimTalk] - Frame

Stopped [SimTalk] - Frame

Stops the Frame designated by &lt;Path&gt; ( true ) or does not stop it ( false ).

Remarks

The Frame shows a pink dot in the LED area of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.Stopped:boolean

Watchable

The attribute is watchable .

You can use an observer to find out if the state changed.

Assignment Value

You can assign a value to the data type boolean .

Example

```simtalk
Frame.Stopped := true
```

See also

LEDs and States of the Frame

Stopped [state, material flow objects]

<!-- image -->

##### Unplanned [SimTalk] - Frame

Sets the Frame designated by &lt;Path&gt; to unplanned when the current time is outside of any shift of the ShiftCalendar to which the Frame is assigned ( true ).

Remarks

The Frame shows a light blue dot in the LED area of the icon.

Type

Attribute

Syntax

&lt; Path &gt;.Unplanned:boolean

Assignment Value

You can assign a value of data type boolean .

Assign false to set it to planned to work.

Example

EngineAssembly.Unplanned := false

See also

LEDs and States of the Frame

Unplanned [state, material flow objects]

<!-- image -->

**ZoomFactor [SimTalk]**

##### ZoomFactor [SimTalk]

Sets the zoom factor with which you view the contents of the Frame designated by &lt;Path&gt;.

Remarks

A 3D Only model does not provide this attribute.

Type

Attribute

Syntax

```simtalk
< Path >.ZoomFactor:real
```

Assignment Value

You can assign a value of data type real .

Specify a factor from 0.25 (25 %) to 10 (1000 %).

Example

```simtalk
Frame.ZoomFactor := 2              // sets the zoom factor to 200 percent
EngineAssembly.ZoomFactor := 0.25  // sets the zoom factor to 25 percent
```

See also

Zoom In [2D only]

Zoom Out [2D only]

#### Interface

