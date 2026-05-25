### Dialog

#### Dialog [object]

Use the Dialog for designing a dialog box for an object which is similar to the built-in dialog boxes.

Icon

<!-- image -->

Description

With the object Dialog you can:

**Dialog [object]**

- Provide the user with a simple user interface for complex simulation models other users work with. This way you can ask the user to type in information which Plant Simulation needs to carry out a task.
- Prevent the user from manipulating a Frame in which you modeled a complex machine, etc. To do so, insert a Method object as an Open Control into the Frame . Double-clicking the Frame will then not open it any longer, but call the method. The method in turn executes the parameter that you typed in, i.e., it opens the dialog, where the user can then select the settings.

Each Dialog object manages a single dialog box. If you need more than one user-defined dialog boxes in your simulation model, insert as many Dialog objects as you need.

- To create and insert a dialog item, click the right mouse button on the tab Elements and select a dialog item on the context menu, compare Insert a Dialog Item into Your Dialog .
- To show the dialog you are creating, click Show Dialog .

**Note**

The display window of the object Dialog that contains menus does not use the standard Siemens PLM theme, but your Windows theme.

<!-- image -->

The display window of the object Dialog that does not contain menus uses the standard Siemens PLM theme.

<!-- image -->

- To edit the position of a dialog item in the dialog you are creating, click Edit Dialog , select it and drag the mouse to a new location.

<!-- image -->

<!-- image -->

To show a tooltip with information about the Dialog , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Dialog , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

<!-- image -->

To add the Dialog to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

UserInterface &gt; Dialog on the Home

ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

We created the dialog boxed of all the Tools with the Dialog .

See also

Set Parameters for Objects in Your Own Dialog

#### Dialog Box of the Dialog

Dialog Box of the Object Dialog

Double-click the icon of the Dialog to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Show Dialog [Dialog]

Edit Dialog [described]

Label [text box] - Dialog

##### Label [text box] - Dialog

Label [text box] - Dialog

Type in a Label for the dialog you create.

<!-- image -->

As opposed to the name, you can type in any expression of your choice as the label, including special characters and blank spaces.

- If you type in a label, Plant Simulation shows that label in the title bar of the dialog you created.
- If you do not type in text as the label, Plant Simulation shows the Name of the Dialog object in the title bar.

<!-- image -->

<!-- image -->

SimTalk

Label [SimTalk]

##### Show Dialog [Dialog]

To show the dialog with the dialog items you created, click this button.

<!-- image -->

The Dialog executes the Callback Method with the parameters you typed into the text boxes for Argument for Open , Argument for Apply or Argument for Close . This way you can detect if they do what you programmed them to do.

**Note**

Plant Simulation shows the dialog with the settings you select under Personalization &gt; Font as well as with the settings you select under Start &gt; Settings &gt; System &gt; Display &gt; Scale &amp; layout . If you change these settings, the dialog scales text, while the images always retain their size in pixels. For this reason it can happen that text overlaps the image. We recommend to test your dialogs with different display settings to make sure that everything works as you expect it.

**Note**

Dialog items which you create may be hidden by other dialog items if they have the same X and/or Y coordinates.

**Note**

As opposed to the object Dialog , which previous versions of Plant Simulation provided, which used one Callback Method per action, the current version of Plant Simulation uses a single callback method for defining all of the actions.

Instead, you can also right-click the Dialog object and select Show Dialog on the context menu in the Frame .

<!-- image -->

<!-- image -->

##### Edit Dialog [described]

To edit a dialog item which you created in the Dialog , click this button.

<!-- image -->

The Dialog then selects the dialog item in the display window, and you can move it by dragging it to another position.

To edit its properties, click it with the right mouse button and select Open on the context menu.

Instead, you can also right-click the Dialog object and select Edit Dialog on the context menu in the Frame .

<!-- image -->

**Note**

The dialog box of the object Dialog uses the standard Siemens PLM theme.

<!-- image -->

###### Tab Elements

##### Tab Elements

The tab Elements provides a context menu with the commands for Insert a Dialog Item into Your Dialog as well as the commands Open and Delete .

To insert a dialog item into the dialog you are creating, click into the text box with the right mouse button and select the respective item on the context menu.

You can also select to show or hide the Default Buttons ( OK , Cancel and Apply ) and to open the dialog you create Modal , meaning that the user cannot open another dialog until he closes the present dialog. Then the user can only open another dialog after he closed the active dialog.

Once you have inserted dialog items, the tree shows the structure of your dialog. Changing the order in the structure modifies the layout of the dialog.

To change the order of the tabs in the dialog, select a tab on the tab Elements , hold down Shift and press the up arrow or the down arrow to move this tab to the left or to the right. The dialog shows the first tab in the structure as the leftmost tab.

Open

To modify an existing dialog item, right-click it and select Open on the context menu. This opens the dialog of the Dialog Item where you can change it.

Delete

To delete a dialog item, right-click it and select Delete on the context menu.

See also

Insert a Dialog Item into Your Dialog

Define Properties of a Dialog Item

Set Parameters for Objects in Your Own Dialog

Inserting a Dialog Item into Your Dialog

Insert a Dialog Item into Your Dialog

Before you start creating your dialog, take a few moments to decide about its structure, i.e., which dialog items do you need, can you show them all in a flat hierarchy in the dialog or do you need to insert tabs and menus.

The structure you decide upon determines how and in which order you create the dialog items. Let us say, you want to show the dialog items on tabs. Then, you first have to create the Tab Control , which is the container that accommodates the individual tabs. After this you have to create the individual Tabs , and finally you can insert the dialog items on each one of these tabs.

- To create a new dialog item, select one of these items on the context menu:

| New Button           | New List View             |
|----------------------|---------------------------|
| New Check Box        | New Menu/New Menu Command |
| New DropDownList Box | New Radio Button          |
| New Edit Text Box    | New Static Text Box       |
| New Group Box        | New Tab Control           |
| New Image            | New Tab Page              |
| New List Box         |                           |

- To add one tab at a time to a Tab Control , click it with the right mouse button on the tab Elements , select Tab Page on the context menu, and type in a name and caption into the text box Dialog Item Tab Page .
- To add a dialog item to a tab on a Tab Control you created, click the name of the tab with the right mouse button in the structure on the tab Elements and select the item you want to insert on the context menu.

You can type in the same Name for dialog items, as long as those dialog items are not located in the same group of items. Groups of items are: Group Box , Menu , Tab Control and Tab .

To rearrange the order of items of type Tab within a Tab Control and Menu in the structure on the tab Elements within these groups, use Shift+Up arrow or Shift+Down arrow . The structure shows all other dialog items according to their position in the user-defined dialog itself.

To move items out of one of the groups or place them there, click the item with the left mouse button in the structure, drag it to the new location and drop it there.

SimTalk

getItemsList [SimTalk]

See also

Define Properties of a Dialog Item

Set Parameters for Objects in Your Own Dialog

Design a Simple Dialog

Design a Tabbed Dialog

New Button

Inserts a button into the dialog.

Icon on the Tab Elements

Description

When the user clicks a button, it calls the Callback Method with the parameter you typed in into the text box Callback Argument . It in turn executes the actions you programmed.

- Type in the Name of the button.

- Type in the Caption that the button displays.

- Type in its X and Y position in the Dialog .

- Type in its Width . The default value of 0 automatically sets the width of the button to the width of the OK button.

- Select if you want to Enable the dialog item or not.

- To insert the dialog item into your dialog, click OK .

SimTalk

createButton [SimTalk]

setCaption [SimTalk]

setSensitive [SimTalk]

See also

Add a Button

**New Check Box**

**New Check Box**

Inserts a check box into the dialog. You can also select if the check box functions as an Inheritance box .

**Icon on the Tab Elements**

<!-- image -->

Description

A check box displays a setting or a set of settings that do not exclude each other. The user can select or clear one or several check boxes at the same time.

<!-- image -->

- Type in the Name of the check box.
- Type in the Caption that describes what the check box does.
- Type in the Callback Argument , which will be passed to the Callback Method as a parameter. It will be executed, when the user selects or clears the check box .
- Type in its X and Y position in the Dialog .
- Select if you want to Enable the dialog item or not.
- Select the check box Inheritance box so that the Dialog shows the check box as a check box for inheritance. It looks like a check box for inheritance in the dialogs of the built-in objects. The check box also works like this.

<!-- image -->

<!-- image -->

Clear the check box Inheritance box so that the Dialog shows the check box as a normal check box.

<!-- image -->

Our callback method looks like this:

```simtalk
param action: string
switch action
case "NameEdit"
	?.setCheckBox("NameInherit", false) // clear check box when the value changes case "Open"
	?.setCaption("NameEdit", ?.NameValue)
	?.setCheckBox("NameInherit", ?.NameValue.InheritValue)
case "Apply"
	var inherit:boolean := ?.getCheckBox("NameInherit") // 'inherit' is a user-defined variable if inherit
	?.NameValue := ?.Origin.NameValue // 'NameValue' is a user-defined attribute
	?.NameValue.InheritValue := true
	?.setCaption("NameEdit", ?.NameValue)
else
	?.NameValue := ?.getValue("NameEdit")
	?.NameValue.InheritValue := false
end
end
```

- To insert the dialog item into your dialog, click OK .

<!-- image -->

SimTalk createCheckBox [SimTalk] getCheckBox [SimTalk] getInheritanceBox [SimTalk] getValue [SimTalk] - Dialog setCaption [SimTalk] setCheckBox [SimTalk] setInheritanceBox [SimTalk] setSensitive [SimTalk] See also Add a Check Box Inheritance [general description] in the Reference Help Using Inheritance

**New DropDownList Box**

Inserts a drop-down list box into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

The user can select a single item from the drop-down list. When it is closed, it displays the current value. When the user clicks the down arrow , it opens and displays more items for changing the value.

<!-- image -->

<!-- image -->

- Type in the Name of the drop-down list.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter. It will be executed when the user closes the drop-down list box .
- Type in its X and Y position in the Dialog .
- Type in its Width . The default value of 0 sets the width to the values defined by us.
- Click Items and type in the items the list box displays into the dialog Items .
- Select if you want to Enable the dialog item or not.
- To insert the dialog item into your dialog, click OK .

**SimTalk**

createDropDownListBox [SimTalk]

setIndex [SimTalk]

getIndex [SimTalk]

setSensitive [SimTalk]

setList [SimTalk]

**See also**

**Add a Drop-down List**

**New Edit Text Box**

Inserts an edit text box into the dialog.

Icon on the Tab Elements

Description

The user can type text into the edit text box or edit text it already contains.

<!-- image -->

- Type in the Name of the text box.
- Type in the Callback Argument , which will be passed to the Callback Method as a parameter.

It will be executed when the user changes the contents of the Text Box and selects another dialog item afterward, clicks in another text box, or clicks OK , Apply or Cancel .

If the edit text box has a Callback Argument , the Callback Method of the Dialog will be called and the Callback Method is assigned the callback argument \_Enter , when the user presses the Enter key and if the dialog does not show the Standard Buttons .

- Select which kind of characters the user can type into the text box.

| Setting               | The user can type in                                                                                                                                                                          |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Any Character         | any character, which includes special characters, lower and upper case letters and numbers.                                                                                                   |
| Letters and Digits    | lower and upper case letters, including special characters, such as umlauts, and letters of any kind of language, underscores, and blank spaces. The user can also type in the digits 0 to 9. |
| Letters               | lower and upper case letters, including special characters, such as umlauts, and letters of any kind of language, and blank spaces.                                                           |
| Decimal Number        | 0123456789                                                                                                                                                                                    |
| Signed Decimal Number | decimal numbers with a negative or positive sign: -+0123456789                                                                                                                                |
| Hexadecimal Number    | ADbf09, for example.                                                                                                                                                                          |
| Octal Number          | 01234567, but not 18 for example.                                                                                                                                                             |
| Binary Number         | 0 or 1                                                                                                                                                                                        |
| Floating Point Number | 12.3E-45, for example.                                                                                                                                                                        |
| Time                  | time values.                                                                                                                                                                                  |
| Date with Time        | a date containing time values.                                                                                                                                                                |

| Setting              | The user can type in    |
|----------------------|-------------------------|
| Date                 | a date.                 |
| Positive Real Number | a positive real number. |

- Type in its X and Y position in the Dialog .
- Type in its Width .
- Select if you want to Enable the dialog item or not.
- To show a password that the user types into the text box with superscripted lower case Xes , instead of as clear text , select .
- To insert the dialog item into your dialog, click OK .

SimTalk

createEditTextBox [SimTalk]

setEditType [SimTalk]

setCaption [SimTalk]

getValue [SimTalk] - Dialog

setSensitive [SimTalk]

setPasswordMasking [SimTalk]

getPasswordMasking [SimTalk]

See also

Add a Text Box

<!-- image -->

<!-- image -->

New Group Box

Inserts a group box .

Icon on the Tab Elements

Description

A group box graphically groups a set of dialog items or controls by drawing a frame around it.

Empty

Populated

- Type in the Name of the group box.

- Type in the Caption the group box displays.

- Type in its X and Y position in the Dialog .

- Type in its Width and its Height .

- Select if you want to Enable the dialog item or not.

- To insert the dialog item into your dialog, click OK .

SimTalk

createGroupBox [SimTalk]

setCaption [SimTalk]

setSensitive [SimTalk]

See also

Add a Group Box Around Dialog Items

**New Image**

New Image

Inserts an image into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

An image is an icon you defined for the object Dialog . You can type in a number, or a name, such as Icon1 .

- Type in the Name of the image.
- Type in its X and Y position in the Dialog .
- Type in its Width and Height in the Dialog .
- Type in the Image ID , i.e., the number of the icon, or an image name. The image is an icon of the Dialog to which the image belongs.

SimTalk createImage [SimTalk] setIcon [SimTalk] getIcon [SimTalk] See also Add an Image

**New List Box**

Inserts a list box into the dialog.

Icon on the Tab Elements

<!-- image -->

**Description**

A list box displays a list of choices. The user can double-click one of the items in the list to select it. The list does not collapse.

<!-- image -->

- Type in the Name of the list box.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter.

It will be executed, when the user selects and double-clicks an item in the list box.

- Type in its X and Y position in the Dialog .
- Type in its Width and Height in the Dialog . If you do not type in values, the Dialog sets the width and height to the values defined by us. When you type in a value for the height , it adds a vertical scrollbar to the list if the list contains more items than the height .
- Click Items and type in the items the list box displays into the dialog Items .
- Select if you want to Enable the dialog item or not.
- To insert the dialog item into your dialog, click OK .

**SimTalk**

Mutation [SimTalk] - GASequence

memUsage [SimTalk]

getIndex [SimTalk]

setList [SimTalk]

setSensitive [SimTalk]

getValue [SimTalk] - Dialog

**New List Box**

**See also**

**Add a List BoxAdd a List Box**

**New List View**

Inserts a list view into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

A list view shows a table in the dialog.

<!-- image -->

**Note**

When displaying strings , Plant Simulation only shows the first 260 characters.

- Type in the Name of the list view.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter. It will be executed, when the user double-clicks a row in the list view .

**Note**

The user can only select rows, but no columns or individual cells.

- Type in the name of a table or click and select a table in the dialog Select Object .

Type the items the list view shows into the cells of the columns.

- Type in its X and Y position in the Dialog .
- Type in its Width and Height in the Dialog .
- Select if you want to Enable the dialog item or not.
- To insert the dialog item into your dialog, click OK .

**SimTalk**

createListView [SimTalk]

setTableRow [SimTalk] getTableRow [SimTalk] setSensitive [SimTalk] getTable [SimTalk] - Dialog setTable [SimTalk] - Dialog See also

**Add a List View**

**New Menu/New Menu Command**

Inserts a menu or a menu command into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

A menu provides a list of textual choices from which the user can choose. The Dialog inserts the menus along the top of the dialog you define.

- Type in the Name of the menu.
- Type in the Caption of the menu. Type in a hyphen ( -) as the caption of the menu command to insert a menu separator between groups of menu commands.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter. It will be executed when the user selects a menu or a menu command .
- Select if you want to Enable the dialog item or not.
- To insert the menu into your dialog, click OK .
- To add one menu command at a time to the selected menu, right-click it and select New Menu/New Menu Command again.
- Type in the Name of the menu command.
- Type in the Caption of the menu command.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter.
- Select if you want to Enable the dialog item or not.
- To insert the menu into your dialog, click OK .
- To add a submenu to the selected menu command, right click that menu command and select New Menu/New Menu Command again. Repeat the steps described above.

A submenu looks like this.

<!-- image -->

·

Note

The display window of the object Dialog that contains menus does not use the standard Siemens PLM theme, but your Windows theme.

The display window of the object Dialog that does not contain menus uses the standard Siemens PLM theme.

<!-- image -->

<!-- image -->

**setCaption [SimTalk] setSensitive [SimTalk] See also**

**Add a Menu and Menu Commands**

**New Radio Button**

**New Radio Button**

Inserts a radio button into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

A set of radio buttons enables the user to select a single setting from a fixed set of choices that exclude each other.

<!-- image -->

- Type in the Name of the radio button.
- Type in the Caption that describes what the radio button does and that the Dialog shows.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter. It will be executed, when the user selects the radio button .
- Type in its X and Y position in the Dialog .
- Type in a Group ID , i.e., a number, for grouping any number of radio buttons to denote which radio buttons belong together.

Group ID 1 might stand for one set of radio buttons, while Group ID 2 might stand for another set. The user can only select one radio button of a group.

- Select if you want to Enable the dialog item or not.

**Note**

You have to create all items of a group of radio buttons sequentially because Plant Simulation creates the items according to their row and column position. You cannot arrange two sets of radio buttons as shown below, where the radio buttons Red and Blue on the left-hand side and the radio buttons Round and Square on the right-hand side form a group each. Windows ignores the Group ID you type in and groups the radio buttons row by row according to the Y -coordinate, i.e., it treats Red and Round as one group and Blue and Square as the other group.

<!-- image -->

<!-- image -->

- To insert the dialog item into your dialog, click OK .

<!-- image -->

##### getValue [SimTalk] - Dialog

See also

**Add a Set of Radio Buttons**

**New Static Text Box**

**New Static Text Box**

Inserts a static text box into the dialolg.

Icon on the Tab Elements

Description

A static text box shows text that the user can view, but not edit.

<!-- image -->

- Type in the Name of the static text box.
- Type in the Caption that the static text box shows.
- Type in its X and Y position in the Dialog .
- Select if you want to Enable the dialog item or not.
- To insert the dialog item into your dialog, click OK .

SimTalk

createStaticTextBox [SimTalk]

setCaption [SimTalk]

setSensitive [SimTalk]

See also

**Add a Static Text Box**

**New Tab Control**

Inserts a tab control into the dialog.

Icon on the Tab Elements

<!-- image -->

Description

A tab control resembles a notebook that contains any number of pages.

<!-- image -->

The user can navigate between different tabs and/or sections of information within the dialog box.

<!-- image -->

When the user selects another tab, the Dialog calls the Callback Method , which in turn executes the actions you programmed with the first parameter you typed in as Callback Argument .

- Type in the Name of the tab control.
- Type in the Callback Argument which will be passed to the Callback Method as a parameter. It will be executed when the user selects a tab in the tab control .

- Type in its X and Y position in the Dialog .
- Type in its Width and Height in the Dialog .
- To insert the tab control into your dialog, click OK .
- To add one tab at the time to the tab control , click it with the right mouse button on the tab Elements and select New Tab Page on the context menu.

**Note**

To change the order of the tabs in the dialog, select a tab on the tab Elements , hold down Shift and press the up arrow or the down arrow to move this tab to the left or to the right. The dialog shows the first tab in the structure as the leftmost tab.

See also

createTabControl [SimTalk]

setTab [SimTalk]

memUsage [SimTalk]

getIndex [SimTalk]

getValue [SimTalk] - Dialog

setList [SimTalk] , applies for all tab pages of the tab control.

See also

Add a Tab Control

**New Tab Page**

To insert a tab at the time to the tab control , click it with the right mouse button on the tab Elements and select New Tab Page .

Icon on the Tab Elements

<!-- image -->

Description

A tab offers settings that belong together.

<!-- image -->

- Type in the Name of the tab into the dialog named Dialog Item Tab Page .
- Type in the Caption of the tab into the dialog named Dialog Item Tab Page . The tab on the tab control shows this caption as the title on the tab itself.

<!-- image -->

**SimTalk**

createTabPage [SimTalk]

###### Defining Properties of a Dialog Item

setCaption [SimTalk] applies, when you change the caption of one tab page only.

setTab [SimTalk]

See also

**Add Tabs to a Tab Control**

Defining Properties of a Dialog Item

Define Properties of a Dialog Item

Depending on the type of item you define, the Dialog shows one or all of these items in the dialog of the item you are defining:

| Name              | Image ID   |
|-------------------|------------|
| Caption           | Width      |
| Callback Argument | Height     |
| X                 | Enable     |
| Y                 | Items      |
| Group ID          |            |

**Name [dialog item in Dialog]**

Type in the Name of the dialog item.

<!-- image -->

The Dialog shows this Name in the text box on the tab Elements .

You can type in the same Name for dialog items, as long as those dialog items are not located in the same group of items. Groups of items are: Group Box , Menu , Tab Control and Tab .

We recommend to type in a unique identifier, containing the type of dialog item, for example xyz\_button , xyz\_list , etc.

**Note**

You cannot use a period ( . ) in the name of a dialog item. As SimTalk treats this name as a string, you can also type in special characters.

A Method object can call this dialog item using the Name you typed in. For some dialog items you can type in a Caption in addition.

SimTalk

setCaption [SimTalk]

getValue [SimTalk] - Dialog Caption [text box] - Dialog Certain dialog items shows the text box Caption . Type in the text which the Dialog shows as the caption of the dialog item in your dialog.

A caption is especially handy if you develop libraries in several languages and want the user to be able to switch languages. In addition, you can type in special characters and blanks, which you cannot use in the name.

The Caption applies to these dialog items:

New Static Text Box

New Button

New Group Box

New Check Box

New Menu/New Menu Command

New Tab Page

New Radio Button

Create an Access Key

Type in the ampersand character &amp; in front of a letter of the Caption of the dialog items listed above to make this letter the access key (mnemonic key). Plant Simulation activates this dialog item, when you press Alt and that letter.

If you want to use the ampersand character &amp; instead of and in a dialog item, for example Drag &amp; Drop , type in the &amp; twice, Drag &amp;&amp; Drop .

<!-- image -->

<!-- image -->

**Callback Argument [text box] - Dialog**

A a number of dialog elements show the text box Callback argument .

Type in the parameter that is passed to the Callback Method . Be aware that the parameters are casesensitive!

The callback method executes this parameter when the user performs the respective action, when he:

- Closes the DropDownList Box .
- Selects and double-clicks an item in the List Box .
- Changes the contents of the Text Box and selects another dialog item afterward, clicks in another text box, or clicks OK , Apply , or Cancel .

If the edit text box has a Callback Argument , the Callback Method of the Dialog will be called and the Callback Method is assigned the callback argument \_Enter .

- Clicks the Button .
- Selects or clears the Check Box .
- Selects the Radio Button .
- Selects a row in the List View and double-clicks it.
- Selects a tab in the Tab Control .
- Selects a Menu/Menu Command .

SimTalk

setCallbackArgument [SimTalk]

See also

Program Actions which the Dialog Items Execute X [text box] - Dialog Type in the position on the x-axis where Plant Simulation places the dialog item in the Dialog you define.

<!-- image -->

<!-- image -->

The value you type in matches the average width of characters of your system font, not to pixels.

If you cannot see the dialog items you inserted, check the settings for the position first. If you typed in identical values for different dialog items, the Dialog places them on top of each other, so that you can only see the first item(s) you inserted.

SimTalk

DialogX [SimTalk]

DialogY [SimTalk]

Y [text box] - Dialog

Y [text box] - Dialog

Type in the position on the y-axis where Plant Simulation places the dialog item in the Dialog you define.

<!-- image -->

<!-- image -->

The value you type in corresponds to lines of characters of the system font, not to pixels. You can type in a value from 0 to 10 for example.

If you cannot see the dialog items you inserted, check the settings for the position first. If you typed in identical values for different dialog items, the Dialog places them on top of each other, so that you can only see the first item(s) you inserted.

SimTalk

DialogY [SimTalk]

DialogX [SimTalk]

**Group ID**

For a dialog item of Type &gt; Radio Button the Dialog shows the text box Group ID .

<!-- image -->

Type in a Group ID , i.e., a number, for grouping any number of radio buttons to denote which radio buttons belong together.

Group ID 1 might stand for one set of radio buttons, while Group ID 2 might stand for another set. The user can only select one radio button of a group.

SimTalk

setGroupID [SimTalk]

See also

New Radio Button

**Image ID**

**Image ID**

For a dialog item of Type &gt; Image the Dialog shows the text box Image ID .

<!-- image -->

Type in an Image ID , i.e., the number of the icon, or the name of the image. The image is an icon of the Dialog to which the image belongs.

SimTalk

createImage [SimTalk]

setIcon [SimTalk]

getIcon [SimTalk]

See also

New Image

<!-- image -->

<!-- image -->

**Width [text box] - dialog item**

Type in the Width of the dialog item in the average width of characters of your system font.

The default value of 0 sets the width to the values defined by us.

**Height [text box] - dialog item**

**Height [text box] - dialog item**

Type in the Height of the dialog item in lines of characters of your system font.

<!-- image -->

<!-- image -->

The default value of 0 sets the height to the values defined by us.

**Enable [check box] - dialog item**

A number of dialog items provide this check box.

<!-- image -->

For a dialog item of Type New Button , New Check Box , New Radio Button , New Edit Text Box , New List Box , and New List View the Dialog shows the check box Enable .

- Select Enable to activate the respective dialog item, for example, in the Dialog . When the user selects it, it triggers the Callback Method , which executes the actions you programmed.
- Clear it to deactivate the dialog item, i.e., to gray it out in the Dialog , and thus make it not available to the user.

SimTalk

setSensitive [SimTalk]

**Items [Dialog]**

**Items [Dialog]**

The Dialog shows the button Items for a dialog item of Type &gt; DropDown List Box and ListBox .

Click Items to open a dialog into which you type the items they show.

- To add an item to the list field, type its name into the text box and click Insert or press the Enter key. Repeat this for all the items you want to add.
- To delete an item from the list, select it in the list field and click Delete .
- To move an item up one position in the list, select it in the list field and click Move Up .
- To change the name of an item in the list, select it in the list field, type another name into the text box, and click Rename .

To apply the items you typed in and to close the dialog, click OK .

To discard what you have done so far, click Cancel .

**SimTalk**

setIndex [SimTalk]

getIndex [SimTalk]

See also

DropDownList Box

List Box

setList [SimTalk]

setCaption [SimTalk]

getValue [SimTalk] - Dialog

Show Default Buttons [check box]

To show the standard buttons in the dialog that you are creating, select this check box.

To hide these buttons, clear the check box.

If you do not show the button combination OK , Cancel , and Apply , you have to define your own buttons to provide the user with a way to apply or to discard settings he chose.

SimTalk

ShowStandardButtons [SimTalk]

<!-- image -->

###### Open Modal [check box]

To open the dialog box you are creating modal , select this check box.

Then, the user cannot open any other Plant Simulation dialog boxes until he closes the dialog box of the user-defined dialog.

To allow the user to open other dialog boxes in addition to the dialog box you are creating, clear the check box.

SimTalk

OpenModal [SimTalk]

Tab Position

Tab Position

**Open Modal [check box]**

<!-- image -->

The Tab Position provides the settings listed in the table of contents to the left.

###### X-Position [dialog item]

Type in the position on the x-axis of your computer screen at which Plant Simulation shows the Dialog when you open it.

<!-- image -->

The default setting -1 for both X-Position and Y-Position centers the Dialog on screen.

The unit is pixels, the zero point is the top left corner of the screen.

SimTalk

getUserDialogXYWH [SimTalk]

**Y-Position [dialog item]**

###### Y-Position [dialog item]

Type in the position on the y-axis of your computer screen at which Plant Simulation shows the Dialog when you open it.

The default setting -1 for both X-Position and Y-Position centers the Dialog on screen.

The unit is pixels, the zero point is the top left corner of the screen.

SimTalk

getUserDialogXYWH [SimTalk]

Tab Method

Tab Method

The Tab Method provides the settings listed in the table of contents to the left.

The parameters are going to be called when Plant Simulation executes the callback method .

###### Callback Method [text box] - Dialog

Creates a Callback Method for the Dialog .

<!-- image -->

**To create the Callback Method :**

- Click and select a Method in the dialog box Select Object . Type in the source code of the callback method. It sets the actions which the dialog items execute. Or you can accept the default, namely the user-defined attribute of data type method named self.callback .
- Select the Method in a Frame , drag it to the text box and drop it there.
- Select Create Control and create the control as a Method of the object .

<!-- image -->

Type in the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

**Parameters**

The callback method can have the following parameters:

- The Open section initializes the contents of the dialog box or sets the dialog items to values of your choice.
- The Dialog executes the Apply section when the user clicks OK or Apply in the dialog box of the Dialog you define. The source code you type in may evaluate new or changed values.
- The Dialog executes the Close section when the user clicks Cancel in the dialog box of the Dialog you define, or when he closes it with Close on the title bar.

- The Dialog executes the Callback Argument of a drop-down list box when the user closes it.
- The Dialog executes the callback argument of a list box when the user selects and double-clicks an item in it.
- The Dialog executes the callback argument of a text box when the user changes its contents and selects another dialog item afterward, clicks in another text box, or clicks OK , Apply , or Cancel .
- The Dialog executes the callback argument of a button when the user clicks the button .
- The Dialog executes the callback argument of a check box when the user selects or clears it.
- The Dialog executes the callback argument of a radio button when the user selects it.
- The Dialog executes the callback argument of a list view when the user selects a row in it and double-clicks it.
- The Dialog executes the callback argument of a tab control when the user selects a tab.
- The Dialog executes the callback argument of a menu/menu command when the user selects a menu or a menu command.

The standard callback method as a user-defined attribute looks like this:

<!-- image -->

**SimTalk**

CallbackMethod [SimTalk] - Dialog

See also

Program Actions which the Dialog Items Execute

Callback Argument [text box] - Dialog

###### Argument for Open [text box]

Type in the name of the callback argument for the Open action into the text box.

<!-- image -->

The Dialog executes it when it executes the Callback Method . The default setting is Open .

The Open section of the callback method initializes the contents of the dialog box or sets the dialog items to values of your choice.

SimTalk

ArgumentForOpen [SimTalk]

See also

Program Actions for Interacting with the Dialog

**Argument for Apply [text box]**

###### Argument for Apply [text box]

Type in the name of the callback argument for the Apply action into the text box.

<!-- image -->

The Dialog executes it when it executes the Callback Method . The default setting is Apply .

The Dialog executes the Apply section of the callback method when the user clicks OK or Apply in the dialog box of the Dialog you define. The source code that you type in may evaluate new or changed values.

**Note**

When the user clicks OK , the Dialog executes the callback method twice. The first time the Apply section is called. The second time the Close section is called.

When the user clicks Apply , the Dialog only executes the Apply section of the callback method .

**SimTalk**

**ArgumentForApply [SimTalk]**

See also

Program Actions for Interacting with the Dialog

###### Argument for Close [text box]

Type in the name of the callback argument for the Close action into the text box.

<!-- image -->

The Dialog executes it when it executes the Callback Method . The default setting is Close .

The Dialog executes the Close section of the callback method when the user clicks Cancel in the dialog box of the Dialog you define, or when he closes it with the Close button on the title bar.

**Note**

When the user clicks OK , the Dialog executes the callback method twice. The first time the Apply section is called. The second time, the Close section is called.

When the user clicks Apply , the Dialog only executes the Apply section of the callback method .

**SimTalk**

ArgumentForClose [SimTalk]

See also

Program Actions for Interacting with the Dialog

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

The Dialog provides the Callback method as a user-defined attribute .

<!-- image -->

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

##### Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Dialog**

#### \_Methods of the Dialog

The Dialog provides:

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

clearData [SimTalk]

Deletes the dialog items of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.clearData

Example

MyDialog.clearData

##### clearData [SimTalk]

close [SimTalk] - Dialog

Closes the dialog box of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.close(OK:boolean)

Parameter

The parameter OK of data type boolean designates the action which the dialog takes, OK or Cancel .

Specify true to apply the changes the user made.

Specify false to cancel all changes.

Example

MyDialog.close(true)

SimTalk

open [SimTalk] - Dialog

See also

Show Dialog [Dialog]

##### closeDialog [SimTalk] - Dialog

closeDialog [SimTalk] - Dialog

Closes the dialog box of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.closeDialog([ApplyChanges:boolean:=true]) → boolean
```

Parameter

The optional parameter ApplyChanges of data type boolean determines if Plant Simulation ignores all changes the user made in the dialog or if it accepts and applies these changes.

Specify true to make the Dialog evaluate all settings in the dialog box and apply them as the new values.

Specify false to make the Dialog discards the changes.

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type boolean .

Example

MyDialog.closeDialog(true)

SimTalk

openDialog [SimTalk] - Dialog

See also

Show Dialog [Dialog]

##### createButton [SimTalk]

Creates a Button in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createButton(Name:string, X:integer, Y:integer, Width:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the button.

**Note**

You can set the Caption of the button with the method setCaption .

- The parameter X of data type integer designates the position of the button on the X-axis in the Dialog .
- The parameter Y of data type integer designates the position of the button on the Y-axis in the Dialog .
- The parameter Width of data type integer designates the Width of the button.
- The optional parameter Parent of data type string designates the parent of the drop-down list box, for example a Group Box or Tab Page .

**Return Value**

The return value has the data type boolean .

**Example**

MyTabbedDialog.createButton("Order", 7, 7, 18, "MyTab4")

**See also**

**New Button**

##### createCheckBox [SimTalk]

createCheckBox [SimTalk]

Creates a Check Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createCheckBox(Name:string, X:integer, Y:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the check box.

Note

You can set the Caption of the check box with the method setCaption .

- The parameter X of data type integer designates the position of the check box on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the check box on the Y-Axis in the Dialog .
- The optional parameter Parent of data type string designates the parent of the check box, for example a Group Box or Tab Page .

Return Value

The return value has the data type boolean .

**Example**

MySimpleDialog.createCheckBox("SunRoof", 9, 6)

SimTalk

getValue [SimTalk] - Dialog

See also

New Check Box

##### createDropDownListBox [SimTalk]

Creates a Drop-Down List Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createDropDownListBox(Name:string, X:integer, Y:integer, Width:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the drop down list box.
- The parameter X of data type integer designates the position of the drop- down list box on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the drop- down list box on the Y-Axis in the Dialog .
- The parameter Width of data type integer designates the Width of the drop down list box.
- The optional parameter Parent of data type string designates the parent of the drop-down list box, for example a Group Box or Tab Page .

**Return Value**

The return value has the data type boolean .

**Example**

MyDialog.createDropDownListBox("unit", 12, 1, 10, "Page.Group") units.create units.insert(1,"mm") units.insert(2,"m") units.insert(3,"km") MyDialog.setList("unit",units)

**SimTalk**

getValue [SimTalk] - Dialog

See also

New DropDownList Box

##### createEditTextBox [SimTalk]

Creates a Edit Text Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createEditTextBox(Name:string, X:integer, Y:integer, Width:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the edit text box.
- The parameter X of data type integer designates the position of the text box on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the text box on the Y-Axis in the Dialog .
- The parameter Width of data type integer designates the Width of the edit text box.
- The optional parameter Parent of data type string designates the parent of the edit text box, for example a Group Box or Tab Page .

**Return Value**

The return value has the data type boolean .

Example

MySimpleDialog.createEditTextBox("Vanity text", 15, 7, 18)

**SimTalk**

getValue [SimTalk] - Dialog

See also

New Edit Text Box

##### createGroupBox [SimTalk]

createGroupBox [SimTalk]

Creates a Group Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createGroupBox(Name:string, X:integer, Y:integer, Width:integer, Height:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the group box.

**Note**

You can set the Caption of the group box with the method setCaption .

- The parameter X of data type integer designates the position of the group box on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the group box on the Y-Axis in the Dialog .
- The parameter Width of data type integer designates the Width of the group box.
- The parameter Height of data type integer designates the Height of the group box.
- The optional parameter Parent of data type string designates the parent of the group box, for example a Tab Page .

Return Value

The return value has the data type boolean .

**Example**

MySimpleDialog.createGroupBox("Drive", 4, 26, 4)

**See also**

New Group Box

##### createImage [SimTalk]

Creates an Image in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.createImage(Name:string, X:integer, Y:integer[, Parent:string]) → boolean

**Parameters**

- The parameter Name of data type string designates the Name of the image.
- The parameter X of data type integer designates the position of the image on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the image on the Y-Axis axis in the Dialog .
- The optional parameter Parent of data type string designates the parent of the image, for example a Group Box or a Tab Page .

Return Value

The return value has the data type boolean .

Example

MyTabbedDialog.createImage("ImageItem", 40, 1, "MyTab4") MyTabbedDialog.setIcon("ImageItem", "CompanyLogo")

SimTalk

setIcon [SimTalk]

See also

New Image

```simtalk
createListBox [SimTalk] Creates a List Box in the Dialog designated by <Path>. Type Method Syntax < Path >.createListBox(Name:string, X:integer, Y:integer, Width:integer, Height:integer[, Parent:string]) → boolean createListBox [SimTalk]
```

**Parameters**

- The parameter Name of data type string designates the Name of the list box.
- The parameter X of data type integer designates the position of the list box on the X-axis in the Dialog .
- The parameter Y of data type integer designates the position of the list box on the Y-axis in the Dialog .
- The parameter Width of data type integer designates the Width of the list box.
- The parameter Height of data type integer designates the Height of the list box.
- The optional parameter Parent of data type string designates the parent of the list box, for example a Group Box or a Tab Page .

**Return Value**

The return value has the data type boolean .

**Example**

MyTabbedDialog.createListBox("ModelList", 18, 0, 16, 2, "MyTab1")

SimTalk

getValue [SimTalk] - Dialog

See also

New List Box

##### createListView [SimTalk]

Creates a List View in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createListView(Name:string, X:integer, Y:integer, Width:integer, Height:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the list view.
- The parameter X of data type integer designates the position of the list view on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the list view on the Y-Axis in the Dialog .
- The parameter Width of data type integer designates the Width of the list view.
- The parameter Height of data type integer designates the Height of the list view.
- The optional parameter Parent of data type string designates the parent of the list view, for example a Group Box or a Tab Page .

**Return Value**

The return value has the data type boolean .

**Example**

MyTabbedDialog.createListView("Configuration", 0, 1, 36, 5, "MyTab4")

**See also**

New List View

##### createMenu [SimTalk]

createMenu [SimTalk]

Creates a Menu/Menu Command in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.createMenu(Name:string[, Parent:string]) → boolean

Parameters

- The parameter Name of data type string designates the Name of the menu.

Note

You can set the Caption of the menu with the method setCaption .

- The optional parameter Parent of data type string designates the parent of the menu items or of the sub-menus. For the top level menu you do not need a parent.

Return Value

The return value has the data type boolean .

Example

MySimpleDialog.createMenu("Show")

See also

New Menu/New Menu Command

##### createRadioButton [SimTalk]

Creates a Radio Button in the Dialog designated by &lt;Path&gt;.

**Remarks**

You have to create all items of a group of radio buttons sequentially because Plant Simulation creates the items according to their row and column position. You cannot arrange two sets of radio buttons as shown below, where the radio buttons Red and Blue on the left-hand side and the radio buttons Round and Square on the right-hand side form a group each. Windows ignores the Group ID you enter and groups the radio buttons row by row according to the Y -coordinate, i.e., it treats Red and Round as one group and Blue and Square as the other group.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you want to model like this, do not place the radio buttons loosely onto the dialog, but group them within group boxes.

<!-- image -->

<!-- image -->

Type

Method

Syntax

```simtalk
< Path >.createRadioButton(Name:string, X:integer, Y:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the radio button.

**Note**

You can set the Caption of the radio button with the method setCaption .

- The parameter X of data type integer designates the position of the radio button on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the radio button on the Y-Axis in the Dialog .
- The optional parameter Parent of data type string designates the parent of the radio button, for example a Group Box or a Tab Page .

Return Value

The return value has the data type boolean .

Example

MySimpleDialog.createRadioButton("Frontwheel", 3, 0)

SimTalk

setGroupID [SimTalk]

getValue [SimTalk] - Dialog

See also

New Radio Button

Add a Set of Radio Buttons

##### createStaticTextBox [SimTalk]

createStaticTextBox [SimTalk]

Creates a Static Text Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createStaticTextBox(Name:string, X:integer, Y:integer[, Parent:string]) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the static text box.
- The parameter X of data type integer designates the position of the static text box on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the static text box on the Y-Axis in the Dialog .
- The optional parameter Parent of data type string designates the parent of the static text box, for example a Group Box or a Tab Page .

Note You can set the Caption of the static text box with the method setCaption .

**Return Value**

The return value has the data type boolean .

**Example**

MySimpleDialog.createStaticTextBox("Vanity", 5, 7)

**See also**

New Static Text Box

##### createTabControl [SimTalk]

Creates a Tab Control in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createTabControl(Name:string, X:integer, Y:integer, Width:integer, Height:integer) → boolean
```

**Parameters**

- The parameter Name of data type string designates the Name of the tab control.
- The parameter X of data type integer designates the position of the tab control on the X-Axis in the Dialog .
- The parameter Y of data type integer designates the position of the tab control on the Y-Axis in the Dialog .
- The parameter Width of data type integer designates the Width of the tab control.
- The parameter Height of data type integer designates the Height of the tab control.

Return Value

The return value has the data type boolean .

Example

MyTabbedDialog.createTabControl("TabControl", 0, 0, 64, 10)

SimTalk

getValue [SimTalk] - Dialog

See also

New Tab Control

##### createTabPage [SimTalk]

createTabPage [SimTalk]

Creates a Tab Page in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.createTabPage(Name:string[, Parent:string]) → boolean
```

Parameters

- The parameter Name of data type string designates the Name of the tab page.

Note

You can set the Caption of the tab page with the method setCaption .

- The optional parameter Parent of data type string designates the parent of the tab page, i.e., the Tab Control .

Return Value

The return value has the data type boolean .

Example

MyTabbedDialog.createTabPage("MyTab1")

See also

New Tab Page getCheckBox [SimTalk]

Returns if the Check Box or the Radio Button in the Dialog designated by &lt;Path&gt; is selected (true) or cleared (false).

Type

Method

Syntax

```simtalk
< Path >.getCheckBox(DialogItem:string) → boolean
```

Parameter

The parameter DialogItem of data type string designates the Check Box or the Radio Button .

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyDialog.getCheckBox("My_CheckBox")
```

See also

setCheckBox [SimTalk]

getIcon [SimTalk]

getIcon [SimTalk]

Returns the Image ID or the image name of the image in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getIcon(DialogItem:string) → string
```

Parameter

The parameter DialogItem of data type string designates the dialog item.

Return Value

The return value has the data type string .

Example

```simtalk
print MyDialog.getIcon("My_Image")
```

SimTalk

setIcon [SimTalk]

See also

New Image

Image ID

##### getIndex [SimTalk]

Returns the number of the designated dialog item in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getIndex(DialogItem:string) → integer

**Parameter**

The parameter DialogItem of data type string designates the List Box , the Drop-Down List Box , or the Tab Page . The leftmost tab has the number 1.

If you assign another list, and if it is possible, the Dialog selects the item at the same position in the list box.

<!-- image -->

If you assign another list, and it is not possible to select the same position in the list box that the previous selection had, the Dialog automatically selects the first item in the new list.

<!-- image -->

**getIndex [SimTalk]**

**Return Value**

The return value has the data type integer .

Is 0 if the drop-down list box does not contain any items.

Is 1 if it does contain items, and no item is selected. Then the Dialog automatically selects the first item in the list.

**Example**

```simtalk
print MyDialog.getIndex("doors")
print MyDialog.getIndex("units")
```

**SimTalk**

**setIndex [SimTalk]**

See also

Position of the item in the Items [Dialog] list

##### getInheritanceBox [SimTalk]

Returns the current mode (selected or cleared) of the Inheritance Box of the specified check box in the Dialog designated by &lt;Path&gt;.

**Remarks**

If you assigned true , the Dialog shows the check box as a check box for inheritance.

<!-- image -->

<!-- image -->

If you assigned false , the Dialog shows the check box as a normal check box.

<!-- image -->

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.getInheritanceBox(DialogItemName:string) → boolean

Parameter

The parameter DialogItemName of data type string designates the name of the check box which you defined as an Inheritance Box .

Return Value

The return value has the data type boolean .

Example

print MySimpleDialog.getInheritanceBox("InheritanceBoxSunRoof")

SimTalk

setInheritanceBox [SimTalk]

See also

New Check Box

##### getItemsList [SimTalk]

Returns the full path within the dialog, the name and the type of dialog item in the Dialog designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

```simtalk
< Path >.getItemsList(Table:table)
```

**Parameter**

The parameter Table of data type table designates the name of the table.

<!-- image -->

**Example**

MyDialog.getItemsList(MyElementsTable)

**See also**

Name [dialog item in Dialog]

getPasswordMasking [SimTalk]

Returns the state of the check box Password for a dialog item of type Edit Text Box in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getPasswordMasking(DialogItem:string) → boolean

Parameter

The parameter DialogItem of data type string designates the check box Password .

Return Value

The return value has the data type boolean .

true if the check box is selected.

false if the check box is cleared.

Example

print MyDialog.getPasswordMasking("MyEditTextBox")

SimTalk

setPasswordMasking [SimTalk]

See also

New Edit Text Box getTable [SimTalk] - Dialog Returns the name of the table that defines the items which a List View in the Dialog designated by &lt;Path&gt; shows.

Type

Method

Syntax

```simtalk
< Path >.getTable(ListView:string) → string
```

Parameter

The parameter ListView of data type string designates the list view.

Return Value

The return value has the data type string .

Example

```simtalk
var table_path : string
table_path := MyDialog.getTable("myListView")
```

SimTalk

setTable [SimTalk] - Dialog

See also

New List View getTableRow [SimTalk]

getTableRow [SimTalk]

Returns the number of the row in the Items Table that defines the items which a List View in the Dialog designated by &lt;Path&gt; shows and which the user selected.

Type

Method

Syntax

```simtalk
< Path >.getTableRow(Table:string) → integer
```

Parameter

The parameter ListView of data type string designates the list view.

Return Value

The return value has the data type integer .

Example

```simtalk
print MyDialog.getTableRow("ListView")
```

SimTalk

setTableRow [SimTalk]

See also

setTableRow [SimTalk]

Items [Dialog]

New List View

##### getUserDialogXYWH [SimTalk]

Returns the position of the Dialog designated by &lt;Path&gt; and assigns them to the local variables, which you define.

Type

Method

Syntax

```simtalk
< >.getUserDialogXYWH(byRef X:integer, byRef Y:integer, byRef
Path Width:integer, byRef Height:integer)
```

**Parameters**

- The local variable X of data type integer designates the x-coordinate of the dialog of the object.
- The local variable Y of data type integer designates the y-coordinate of the dialog of the object.
- The local variable Width of data type integer designates its width.
- The local variable Height of data type integer designates its height.

**Example**

```simtalk
var x,y,w,h: integer
MyDialog.getUserDialogXYWH(x,y,w,h)
print x," ",y," ",w," ",h
```

**SimTalk**

setXYWH [SimTalk]

getXYWH [SimTalk]

getValue [SimTalk] - Dialog Returns the changed value of the dialog item in the Dialog designated by <Path>. Type Method Syntax getValue [SimTalk] - Dialog

```simtalk
< Path >.getValue(DialogItem:string) → string
```

Parameter

The parameter DialogItem of data type string designates the dialog item of type Drop-Down List Box , Check Box , Radio Button , List Box , Edit Text Box , and Tab Control . If you apply the method to the Tab Control , Plant Simulation returns the name of the active tab.

Return Value

The return value has the data type string .

Example

```simtalk
var value: string
value := MyDialog.getValue("unit")
var number : integer
number := str_to_num(value)
```

SimTalk

createCheckBox [SimTalk]

createDropDownListBox [SimTalk]

createEditTextBox [SimTalk]

Mutation [SimTalk] - GASequence

createRadioButton [SimTalk]

createTabControl [SimTalk]

setCaption [SimTalk]

open [SimTalk] - Dialog

Opens the dialog box of the Dialog designated by &lt;Path&gt; at the specified position on screen.

Type

Method

Syntax

&lt; Path &gt;.open(X:integer, Y:integer)

**Parameters**

- The parameter X of data type integer designates the X-Position at which Plant Simulation opens the dialog box.
- The parameter Y of data type integer designates the Y-Position at which Plant Simulation opens the dialog box.

**Example**

MyDialog.open(100,100)

SimTalk

close [SimTalk] - Dialog

See also

Show Dialog [Dialog]

X-Position [dialog item]

Y-Position [dialog item]

openDialog [SimTalk] - Dialog Opens the dialog box of the Dialog designated by <Path>. Type Method Syntax openDialog [SimTalk] - Dialog

```simtalk
< Path >.openDialog → boolean < Path >.openDialog(CallOpenControl:boolean:=false) → boolean
```

Parameter

The parameter CallOpenControl of data type boolean sets if Plant Simulation opens the dialog box the same way as double-clicking the icon does and also executes any existing Open Control ( true ) or if it only opens the dialog ( false ).

**Default Value of the Parameter**

The default value is false.

Return Value

The return value has the data type boolean .

true if Plant Simulation succeeded in opening the dialog.

Example

myDialog.openDialog .Models.Model.myDialog.openDialog(false)

SimTalk

closeDialog [SimTalk] - Dialog

See also

Show Dialog [Dialog]

Open Control

##### setActiveTabPage [SimTalk]

Activates the designated tab of the designated tab control of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setActiveTabPage(TabControl:string, TabPageName:string)

**Parameters**

- The parameter TabControl of data type string designates the tab control that contains the tab to be activated.
- The parameter TabPageName of data type string designates the tab that will be activated.

**Example**

MyDialog.setActiveTabPage("MyTabControl", "Page1")

See also

New Tab Control

New Tab Page

**setCallbackArgument [SimTalk]**

##### setCallbackArgument [SimTalk]

Sets the Callback Argument which the Callback Method of the Dialog designated by &lt;Path&gt; executed.

Remarks

The Console shows this parameter if you show it in the Callback method .

Type

Method

Syntax

&lt; Path &gt;.setCallbackArgument(DialogItem:string, Argument:string) → integer

**Parameters**

- The parameter DialogItem of data type string designates the dialog item to which the callback argument applies.
- The parameter Argument of data type string designates the value of the callback argument.

Return Value

The return value has the data type integer .

Example

MyDialog.setCallbackArgument("TabControl.Page1.Save","Bill")

See also

Callback Argument [text box] - Dialog

Callback Method [text box] - Dialog

##### setCaption [SimTalk]

Sets the Caption , i.e., the description of a dialog item, and the settings described below of the Dialog designated by &lt;Path&gt;.

Remarks

Plant Simulation shows changes immediately.

setCaption applies to these dialog items:

- Static Text Box which changes its caption.
- Edit Text Box which changes the contents of the text box.
- Tab Page which changes the label of the tab.
- Button which changes the label of the button.
- Group Box which changes its caption.
- Menu/Menu Command which changes its caption.
- Check Box which changes its caption.
- Radio Button which changes its caption.

Type

Method

Syntax

```simtalk
< Path >.setCaption(DialogItem:string, Caption:string) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item to which the caption applies.
- The parameter Caption of data type string designates the text that you want to assign as the caption.

**Return Value**

The return value has the data type boolean .

**Example**

```simtalk
MyDialog.setCaption("object",current.name)
if Station.failed
```

**setCaption [SimTalk]**

MyDialog.setCaption("state","failed") else MyDialog.setCaption("state","ready") end

**SimTalk**

Caption [text box] - Dialog getValue [SimTalk] - Dialog

##### setCheckBox [SimTalk]

Sets if the Check Box or the Radio Button of the Dialog designated by &lt;Path&gt; will be selected ( true ) or cleared ( false ).

Type

Method

Syntax

&lt; Path &gt;.setCheckBox(DialogItem:string, Active:boolean) → boolean

**Parameters**

- The parameter DialogItem of data type string designates the dialog item.
- The parameter Active of data type boolean sets if it will be activated ( true ) or not ( false ).

Return Value

The return value has the data type boolean .

Example

MyDialog.setCheckBox("My\_CheckBox",true)

SimTalk

getCheckBox [SimTalk]

See also

New Check Box

New Radio Button

**setEditType [SimTalk]**

##### setEditType [SimTalk]

Sets the data type of the Edit Text Box of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setEditType(DialogItem:string, Type:string)

**Parameters**

- The parameter DialogItem of data type string designates the name or the name and the path of the edit text box.
- The parameter Type of data type string designates which kind of characters the user can type into the edit text box.

| Setting               | The user can type in                                                                                                                                                                          |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Any Character         | any character, which includes special characters, lower and upper case letters and numbers.                                                                                                   |
| Letters and Digits    | lower and upper case letters, including special characters, such as umlauts, and letters of any kind of language, underscores, and blank spaces. The user can also type in the digits 0 to 9. |
| Letters               | lower and upper case letters, including special characters, such as umlauts, and letters of any kind of language, and blank spaces.                                                           |
| Decimal Number        | 0123456789                                                                                                                                                                                    |
| Signed Decimal Number | decimal numbers with a negative or positive sign: -+0123456789                                                                                                                                |
| Hexadecimal Number    | ADbf09, for example.                                                                                                                                                                          |
| Octal Number          | 01234567, but not 18 for example.                                                                                                                                                             |
| Binary Number         | 0 or 1                                                                                                                                                                                        |
| Floating Point Number | 12.3E-45, for example.                                                                                                                                                                        |
| Time                  | time values.                                                                                                                                                                                  |
| Date with Time        | a date containing time values.                                                                                                                                                                |
| Date                  | a date.                                                                                                                                                                                       |
| Positive Real Number  | a positive real number.                                                                                                                                                                       |

**Example**

MyDialog.setEditType("MyEditTextBox", "Letters and Digits")

**See also**

New Edit Text Box

**setGroupID [SimTalk]**

##### setGroupID [SimTalk]

Sets the Group ID of dialog items of a Radio Button of the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setGroupID(DialogItem:string, Group:integer)
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item.
- The parameter Group of data type integer designates the group ID.

**Example**

MySimpleDialog.setGroupID("Frontwheel", 1) MySimpleDialog.setGroupID("Rearwheel", 1) MySimpleDialog.setGroupID("MagRim", 2) MySimpleDialog.setGroupID("SteelRim", 2)

See also

Group ID

New Radio Button

##### setIcon [SimTalk]

Sets the Image ID of a dialog item of the Dialog designated by &lt;Path&gt; to the specified value.

Type

Method

Syntax

```simtalk
< Path >.setIcon(DialogItem:string, ImageID:string) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item,
- The parameter ImageID of data type string designates the value. You can enter an Image ID or an Image Name that is an icon of the Dialog to which the image belongs.

Return Value

The return value has the data type boolean .

Example

MyDialog.setIcon("My_Image","Logo")

MyDialog.setIcon("My_Image","3")

SimTalk

getIcon [SimTalk]

createImage [SimTalk]

See also

Image ID

**setIndex [SimTalk]**

##### setIndex [SimTalk]

Sets the number of the item, which the List Box , the Drop-down List Box , or the Tab Page of the Dialog designated by &lt;Path&gt; shows.

Type

Method

Syntax

```simtalk
< Path >.setIndex(DialogItem:string, ItemNumber:integer) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the List Box , the Drop-down List Box , or the Tab Page .
- The parameter ItemNumber of data type integer designates the item that will be shown.

If you do not enter an item, the Dialog selects the first entry in the list.

The parameter DialogItem of data type string can also designate a Tab Control .

The parameter ItemNumber of data type integer can also designate a tab, which the dialog activates within this Tab Control . The leftmost tab has the number 1.

Return Value

The return value has the data type boolean .

**Example**

MyDialog.setIndex("units",6) MyDialog.setIndex("myTabControl",3)

MyDialog.setIndex("listView",3)

**SimTalk**

**getIndex [SimTalk]**

See also

Position of the item in the Items [Dialog] list

New List Box

**New DropDownList Box**

**New Tab Page**

**setInheritanceBox [SimTalk]**

##### setInheritanceBox [SimTalk]

Selects ( true ) the Inheritance Box of the specified check box in the Dialog designated by &lt;Path&gt; or clears it ( false ).

Type

Method

Syntax

<!-- image -->

**Parameter**

- The parameter DialogItemName of data type string designates the check box for which you want to activate the feature Inheritance Box .
- The parameter Value of data type boolean selects ( true ) or clears ( false ) the check box Inheritance Box .

Assign true so that the Dialog shows the check box as a check box for inheritance.

<!-- image -->

<!-- image -->

Assign false so that the Dialog shows the check box as a normal check box.

<!-- image -->

**Example**

MySimpleDialog.setInheritanceBox("InheritanceBoxSunRoof", true)

**SimTalk**

getInheritanceBox [SimTalk]

See also

New Check Box

<!-- image -->

**setList [SimTalk]**

##### setList [SimTalk]

Sets the items of a list which the designated dialog items of the Dialog designated by &lt;Path&gt; shows.

Type

Method

Syntax

```simtalk
< Path >.setList(DialogItem:string, List:any) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates a List Box , a Drop-down List Box , or a Tab Control .
- The parameter List of data type any designates the one-columned list into which you enter the Items which the dialog items List Box or Drop-down List Box or the tabs of Tab Control show.

Return Value

The return value has the data type boolean .

true if the item in the list was addressed and if it changed its display.

**Examples**

MyDialog.setList("sedan",ListSedan)

```simtalk
var units: list[string]
units.create
units.insert(1,"pound")
units.insert(2,"stone")
MyDialog.setList("unit",units)
```

See also

New List Box

New DropDownList Box

New Tab Control

Items [Dialog]

**setList [SimTalk]**

**setPasswordMasking [SimTalk]**

##### setPasswordMasking [SimTalk]

Sets if the check box Password of a dialog item of type Edit Text Box in the Dialog designated by &lt;Path&gt; will be selected or cleared.

Type

Method

Syntax

&lt; Path &gt;.setPasswordMasking(DialogItem:string, Selected:boolean) → boolean

**Parameters**

- The parameter DialogItem of data type string designates the check box Password .
- The parameter Selected of data type boolean sets if the check box Password will be selected ( true ) or cleared ( false ).

When it is selected the Dialog shows text that the user enters into the text box with superscripted lower case xes . When it is cleared it shows the password as clear text .

Return Value

The return value has the data type boolean .

Example

MyDialog.setPasswordMasking("Password",true)

See also

New Edit Text Box

getPasswordMasking [SimTalk]

##### setSensitive [SimTalk]

Sets if the Dialog designated by &lt;Path&gt; shows and activates a dialog item or shows it and dims it.

Remarks

setSensitive applies to all dialog items, except for the Tab Control , the Tab Page and the Image .

Type

Method

Syntax

```simtalk
< Path >.setSensitive(DialogItem:string, Activated:boolean) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item.
- The parameter Activated of data boolean sets if the dialog item will be shown and activated ( true ) or be shown and unavailable ( false ).

**Return Value**

The return value has the data type boolean .

true if the state of the dialog item is activated and has changed.

false if the state of the dialog item is deactivated, and has not changed.

**Example**

```simtalk
if MyDialog.setSensitive("MyButton",false)
	print "The button 'MyButton' was deactivated."
else
	print "The button 'MyButton' has already been deactivated."
end
```

**setTab [SimTalk]**

##### setTab [SimTalk]

Moves a dialog item onto a Tab in the Dialog designated by &lt;Path&gt;.

Remarks

Do not use setTab for dynamically creating tabs in your dialog!

You cannot move a dialog item within a group with this method.

Type

Method

Syntax

```simtalk
< Path >.setTab(DialogItem:string, NewTabPage:string) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item.
- The parameter NewTabPage of data type string designates the Tab to which the dialog item is moved.

Return Value

The return value has the data type boolean

Example

MyDialog.setTab("button","Properties.Settings")

setTable [SimTalk] - Dialog

Sets the table that defines the Items which a dialog item of type List View shows in the Dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setTable(DialogItem:string, AttributeTable:string/object) → boolean
```

**Parameters**

- The parameter DialogItem of data type string designates the dialog item of type List View .
- The parameter AttributeTable of data type object or the user-defined variable of data type string designated by the parameter string designate the attribute table.

Return Value

The return value has the data type boolean .

Example

MyDialog.setTable("list_view",".Models.Model.Station.ListViewTable")

MyDialog.setTable("list_view",.Models.Model.ListViewTable)

SimTalk

getTable [SimTalk] - Dialog

See also

Items [Dialog]

New List View

getTable [SimTalk] - Dialog

**setTableRow [SimTalk]**

##### setTableRow [SimTalk]

Sets the number of the row of the Items table which will be selected in a List View of the dialog designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setTableRow(Table:string, Row:integer) → boolean
```

**Parameters**

- The parameter Table of data type string designates the items table.
- The parameter Row of data type integer designates the row which will be selected.

Return Value

The return value has the data type boolean .

Example

MyDialog.setTableRow("MyListViewTable",4)

SimTalk

getTableRow [SimTalk]

See also

Items [Dialog]

New List View

##### updateUserDialog [SimTalk]

Updates the contents of the Dialog designated by &lt;Path&gt;.

Remarks

The Dialog then shows features that you changed in tables defining the items, or shows new or changed pictures and icons of the items.

Type

Method

Syntax

&lt; Path &gt;.updateUserDialog

**Example**

MyDialog.updateUserDialog

#### Read-Only Attributes of the Dialog

Read-Only Attributes of the Dialog

The Dialog provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

**Attributes of the Dialog**

#### \_Attributes of the Dialog

The Dialog provides:

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
MyDialog.Locked := true MyDialog.openDialog // show the effect
print MyDialog.ArgumentForApply
posit := Station.Cont.XPos
```

**ArgumentForApply [SimTalk]**

##### ArgumentForApply [SimTalk]

Designates an Argument for Apply for the Callback Method when the user clicks Apply or OK in the dialog box of the Dialog designated by &lt;Path&gt;.

Remarks

If the user clicks OK , the Dialog executes the Callback Method twice. The first time the Apply section is called. The second time, the Close section is called.

If the user clicks Apply , the Dialog only executes the Apply section of the Callback Method .

Type

Attribute

Syntax

```simtalk
< Path >.ArgumentForApply:string
```

**Assignment Value**

You can assign a value of data type string .

Examples

```simtalk
MyDialog.ArgumentForApply := "Apply"
param action : string
print "Current action: ",action
switch action
case "Open"
	@.setCaption("Number_Inp",to_str(Variable1))
case "Apply"
	var str:string := @.getValue("Number_Inp")
	Variable1 := str_to_num(str)
case "Close"
end
```

SimTalk

CallbackMethod [SimTalk] - Dialog

**See also**

**Argument for Apply [text box]**

Callback Method [text box] - Dialog

##### ArgumentForClose [SimTalk]

Designates an Argument for Close for the Callback Method when the user clicks Cancel in the dialog of the Dialog designated by &lt;Path&gt; or the close button in its title bar.

Remarks

If the user clicks OK , the Dialog executes the Callback Method twice. The first time the Apply section is called. The second time, the Close section is called.

If the user clicks Apply , the Dialog only executes the Apply section of the Callback Method .

Type

Attribute

Syntax

&lt; Path &gt;.ArgumentForClose:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyDialog.ArgumentForClose := "Close"
```

SimTalk

CallbackMethod [SimTalk] - Dialog

See also

Argument for Close [text box]

Callback Method [text box] - Dialog

##### ArgumentForOpen [SimTalk]

Designates an Argument for Open for the Callback Method when the user opens the Dialog designated by &lt;Path&gt;.

Remarks

You might, for example, use it to preallocate data in the dialog box.

Type

Attribute

Syntax

&lt; Path &gt;.ArgumentForOpen:string

Assignment Value

You can assign a value of data type string .

Example

MyDialog.ArgumentForOpen := "Open"

SimTalk

CallbackMethod [SimTalk] - Dialog

See also

Argument for Open [text box]

Callback Method [text box] - Dialog

##### CallbackMethod [SimTalk] - Dialog

Sets the path to a Method that the dialog items in the Dialog designated by &lt;Path&gt; triggers.

Type

Attribute

Syntax

**&lt; Path &gt;.CallbackMethod:object**

Parameters

The Callback Method can contain the following parameters:

- The Open section initializes the contents of the dialog box or sets the dialog items to values of your choice.
- The Dialog executes the Apply section when the user clicks OK or Apply in the dialog box of the Dialog you define. The source code you enter may evaluate new or changed values.
- The Dialog executes the Close section when the user clicks Cancel in the dialog box of the Dialog you define, or when he closes it with Close on the title bar.
- The Dialog executes the Callback Argument of a Drop-down List Box when the user closes it.
- The Dialog executes the Callback Argument of a List Box when the user selects and double-clicks an item in it.
- The Dialog executes the Callback Argument of a Text Box when the user changes its contents and selects another dialog item afterward, clicks in another text box, or clicks OK , Apply or Cancel .
- The Dialog executes the Callback Argument of a Button when the user clicks the button .
- The Dialog executes the Callback Argument of a Check Box when the user selects or clears it.
- The Dialog executes the Callback Argument of a Radio Button when the user selects it.
- The Dialog executes the Callback Argument of a List View when the user selects a row in it and double-clicks it.
- The Dialog executes the Callback Argument of a Tab Control when the user selects a tab.
- The Dialog executes the Callback Argument of a Menu/Menu Command when the user selects a menu or a menu command.

Assignment Value

You can assign a value of data type object .

**Examples**

```simtalk
MyDialog.CallbackMethod := .Models.Model.&DialogMethod // this method executes these actions // .Models.Model.DialogMethod
param CallbackArgument : string
switch CallbackArgument
case "Open"
	print CallbackArgument
case "Apply"
	print CallbackArgument
case "Close"
	print CallbackArgument
case "Text_box"
	print CallbackArgument
case "Button"
	print CallbackArgument
case "Drop_down_list_box"
	print CallbackArgument
case "Group_box"
	print CallbackArgument
case "Check_box"
	print CallbackArgument
case "List_box"
	print CallbackArgument
case "List_view"
	print CallbackArgument
case "Tab_control"
	print CallbackArgument
else
	print "No argument defined: ",CallbackArgument
end
param action: string
switch action
case "Open" then @.setIndex("VariantType", @.VariantNo)
	@.setCheckbox("SunRoof", true)
	@.setValue("Vanity text", "Enter your text")
case "Apply"
	@.VariantNo := @.getIndex("VariantType")
case "Close" // no action is required case "CallbackChart" then
	mychart.active := true
case "CallbackReport" then
	myreport.show
end
param action : string
print "Current action: ",action
switch action
case "Open"
```

case "Apply" case "Close" case "Item_1_1" promptmessage("Action 1") case "Item_1_2" promptmessage("Action 2") case "Item_2_1" promptmessage("Mission 1") case "Item_2_2" promptmessage("Mission 2") case "X_but" promptmessage("Button action") end

```simtalk
param action : string
print "Current action: ",action
switch action
case "Open"
	switch Color
	case "Red"
		@.setCheckBox("red_RB",true)
	case "Blue"
		@.setCheckBox("blue_RB",true)
	case "Green"
		@.setCheckBox("Green_RB",true)
	end
	switch Lang
	case "English"
		@.setCheckBox("eng_RB",true)
	case "German"
		@.setCheckBox("ger_RB",true)
	end
case "Apply"
case "Close"
case "red_RB"
	Color := "Red"
case "blue_RB"
	Color := "Blue"
case "Green_RB"
	Color := "Green"
case "eng_RB"
	Lang := "English"
case "ger_RB"
	Lang := "German"
```

end

```simtalk
param action : string
print "Current action: ",action
switch action
case "Open"
	@.setCheckBox("Option_CB",Option)
	@.setList("ListBox",CardFile)
case "Apply"
case "Close"
case "Option_CB"
	if @.getCheckBox("Option_CB")
		Option := true
	else
		Option := false
	end
case "ListBox"
	var n:integer := @.getIndex("ListBox")
	Selection := CardFile[n]
end
```

**See also**

Callback Method [text box] - Dialog

Callback Argument [text box] - Dialog

**DialogX [SimTalk]**

##### DialogX [SimTalk]

Sets the position on the x-axis where Plant Simulation shows the dialog box of the Dialog designated by &lt;Path&gt;.

Remarks

The unit is a pixel.

The zero point is the top left corner of the screen or the dialog box.

Type

Attribute

Syntax

&lt; Path &gt;.DialogX:integer

Assignment Value

You can assign a value of data type integer .

Specify -1 for either DialogX or DialogY to center the Dialog on screen.

Example

MyDialog.DialogX := 350

SimTalk

DialogY [SimTalk]

See also

X-Position [dialog item]

##### DialogY [SimTalk]

Sets the position on the y-axis where Plant Simulation shows the dialog box of the Dialog you designed when you open it.

Remarks

The unit is one pixel.

The zero point is the top left corner of the screen or the dialog box.

Type

Attribute

Syntax

&lt; Path &gt;.DialogY:integer

Assignment Value

You can assign a value of data type integer .

Specify -1 for either DialogX or DialogY to center the Dialog on screen.

Example

MyDialog.DialogY := 300

SimTalk

DialogX [SimTalk]

See also

Y-Position [dialog item]

**Locked [SimTalk]**

##### Locked [SimTalk]

Sets what Plant Simulation opens when the user double-clicks the icon of the Dialog designated by &lt;Path&gt;:

Type

Attribute

Syntax

```simtalk
< Path >.Locked:boolean
```

Assignment Value

You can assign a value of data type boolean .

- Specify true to lock the dialog box of the object Dialog , preventing the user from making changes to the layout of the dialog. A double-click opens the Dialog .
- Specify false to unlock the Dialog and open the dialog box when the user double-clicks the icon, so he can modify the layout of the dialog.

**Example**

```simtalk
MyDialog.Locked := true
MyDialog.openDialog
```

##### OpenModal [SimTalk]

Sets if the dialog box of the Dialog designated by &lt;Path&gt; will be opened modal ( true ) or not modal ( false ).

Remarks

Modal means that the user cannot open any other Plant Simulation dialog windows until he closes the window of the user-defined dialog.

Not modal means that the user can open other Plant Simulation boxes when the dialog box of the dialog is open.

Type

Attribute

Syntax

```simtalk
< Path >.OpenModal:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Models.MyPlant.MyDialog.OpenModal := true
```

See also

Open Modal [check box]

ShowStandardButtons [SimTalk]

Sets if the Dialog designated by &lt;Path&gt; shows the standard buttons OK , Cancel and Apply ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.ShowStandardButtons:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Dialog.ShowStandardButtons := false

See also

Show Default Buttons [check box]

