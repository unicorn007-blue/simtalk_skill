## Class Library

The Class Library shows the built-in objects in a hierarchical view grouped in folders and sub-folders.

By default, the Class Library contains a folder for Material Flow Objects , for Fluid Objects , for Resource Objects , for Information Flow Objects , for Display and User Interface Objects , for Mobile Units [MUs] , for UserObjects , for Tools , and for Models .

<!-- image -->

You can show or hide the Class Library by clicking Class Library on the Window ribbon tab.

<!-- image -->

Instead of closing and reopening the Class Library , you can also AutoHide it: Click to auto hide the window. When you then click in another window, Plant Simulation hides the window until you move the mouse over the name of the window again. To deactivate AutoHide , click .

Plant Simulation initially opens the Frame named Model for creating your simulation model, and any other Frames you add later on, in the Models folder.

When you add an add-in program by clicking Manage Class Library on the Home ribbon tab, the Class Library also shows its objects-either loose or in a folder of its own-on the topmost level of the structure below Basis . Basis designates the Class Library itself, compare the anonymous identifier basis .

When you add your own objects to the Class Library and want to make sure that Plant Simulation shows their icons in the structure with the same size as those of the built-in objects, proceed as follows:

- Create a 16 by 16 pixel icon in the Icon Editor .
- Name that icon ClassLibrary .

The Class Library window also shows the objects of libraries which you purchased. When you modeled your own objects, either in Frames or by modifying any of the built-in objects, the Class Library also shows these objects. We call these objects application objects. You find examples of built-in application objects in the folder Tools : The ExperimentManager [object] , the TransferStation , etc.

<!-- image -->

The Toolbox also shows the objects contained by default in the folder.

<!-- image -->

The Class Library also shows the structure of the selected 3D graphic in the window Show 3D Graphic Structure [context menu] .

<!-- image -->

### Class Library

Introducing Classes Show the Contents of a Frame in the Class Library Insert an Object from the Class Library Work with Folders, Frames, Objects in the Class Library Show the Contents of a Frame in the Class Library Arranging the Order of Folders in the Tree Window Context Menu of the Selected Object in the Class Library Context Menu of a Simulation Object \_SimTalk Access to the Folder in the Class Library Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=yVabboCucmgc64Br&amp;t=180](https://youtu.be/FNpiAaUK8iM?si=yVabboCucmgc64Br&t=180)

### UserObjects

Create and store the objects, which you yourself develop, in the folder UserObjects .

**Note**

If at all possible, we recommend to not change the standard settings of the built-in objects. If you customize them and then merge models later on or if you update the Class Library later on, your customized settings are going to be discarded and replaced by the standard settings. You then have to make your customizations again.

If you need objects with your own settings, we recommend to duplicate the respective object in the Class Library and then work with this class. Plant Simulation places duplicated and derived objects in the folder UserObjects .

<!-- image -->

The folder UserObjects provides these objects by default:

- PartA has the same graphic and the same simulation settings as the Part but has the color blue .
- PartB has the same graphic and the same simulation settings as the Part but has the color teal .
- Box has the graphic simulation settings of the storage box in the folder 3D\s3dgraphics\Containers\BoxFor1x1x3Entities.s3d .

<!-- image -->

- MyFrame is a sample Frame that shows how to model user-defined objects. You can insert this Frame into your model and connect it with Connectors .

The Toolbox also shows the objects contained by default in the folder.

<!-- image -->

### Arranging the Order of Folders in the Tree Window

To arrange the order in which Plant Simulation shows objects within a folder in the tree window, for example sort them by function or by name.

- Click the object with the left mouse button to select it.
- Hold the mouse button down, drag the object to the location of your choice in the folder and drop it there.

To add icons of objects to the toolbar in the tree window:

- Click the object with the left mouse button to select it.
- Drag the object to the object name of the toolbar&gt; located at the bottom of the respective folder and drop it there.

#### Context Menu of the Selected Object in the Class Library

### Context Menu of the Selected Object in the Class Library

The context menu of a folder or an object in the Class Library provides menu commands pertaining to the folder or object.

<!-- image -->

<!-- image -->

| New [Folder, Frame, Toolbar]   | Show Inheritance [object]                      |
|--------------------------------|------------------------------------------------|
| Paste [object class]           | Show MUStatistics                              |
| Open [object class]            | Show Attributes and Methods [Home ribbon]      |
| Open in 3D [object class]      | Edit User-defined Attributes [Class Library]   |
| Duplicate                      | Edit Icons [context menu] of an object         |
| Derive                         | Edit 3D Properties [Frame]                     |
| Cut Inheritance                | Edit Display Panel [context menu] of an object |
| Delete [class library]         | Make Library / Edit Library Information        |
| Delete [class library]         | Find Object [context menu]                     |
| Rename [model or object]       | Save Object As                                 |

| Show Origin [class library]              | Save/Load                               |
|------------------------------------------|-----------------------------------------|
| Show Structure [class library]           | Convert all Methods to New Syntax       |
| Show 3D Graphic Structure [context menu] | Revert all Objects to Standard Graphics |

Plant Simulation shows a short description of the selected command in the status bar.

When you hold down Shift and click Basis or a folder in the Class Library with the right mouse button, Plant Simulation shows the commands Convert all Methods to New Syntax and Revert all Objects to Standard Graphics .

<!-- image -->

#### New [Folder, Frame, Toolbar]

Creates a new Folder , a new Frame , or a new Toolbar in the active simulation model.

- Select the level in the structure, i.e., the folder, to which you would like to add the item.
- Select the item that you would like to add under New :
- Folder creates a new folder.
- Toolbar creates a new toolbar in the Class Library and in the Toolbox .
- The three different Frame types are based on the built-in Frame . Each uses different parameters. You can change these parametrizations at any time in Frames you created. You are not bound to a certain type after you created it.

**◊ Model Frame**

Creates a Frame that shows it Caption and its default graphic toward the outside, but does not show its contents . The Model Frame contains an EventController by default. This is the Standard Model Frame , which Plant Simulation shows in the Class Library . Here the Caption of the Frame is important, not its contents .

<!-- image -->

**◊ Glass Box Frame**

Creates a Frame that shows its contents toward the outside, but not its default graphic and its caption . As you insert a Glass Box Frame into your models, you want to see its contents which its default graphic and its caption are not important. This setting is only available for 3D Only models .

<!-- image -->

**◊ Black Box Frame**

Creates a Frame that does not show its contents and its caption toward the outside. You can use a Black Box Frame if you do not want to show its contents because it only contains information flow objects, for example, whose display is not important.

<!-- image -->

<!-- image -->

The graphic named default only becomes visible when you activate Show External Graphic Groups on the View ribbon tab.

<!-- image -->

- Plant Simulation assigns the name NewFolder/Frame/Toolbar , NewFolder1/Frame1/Toolbar1 , etc. to the respective item.
- To rename the item, click it with the right mouse button, select Rename , and type in the name of your choice.

Instead, you can also click the item with the left mouse button, press F2 , and over-type the existing name.

You can also save a folder, or a Frame , you created this way, as an object file, by clicking it with the right mouse button and selecting Save Object As . You can then load this object into the same or another simulation model by clicking the right mouse button into the Class Library and selecting Load Object .

SimTalk

createFolder [SimTalk]

createToolbar [SimTalk]

derive [SimTalk]

duplicate [SimTalk]

See also

Create the Classes of the Cells and the Lines

Work with Your Own Classes

**Paste [object class]**

#### Paste [object class]

Pastes the object on the clipboard as a new class object. SimTalk pasteClipboard [SimTalk] - class library

#### Open [object class]

Opens the dialog box of the selected object class. SimTalk \_3D.openWindow [SimTalk]

#### Open in 3D [object class]

Opens the dialog of the selected object class in a new 3D window.

When you open a folder , the 3D window shows a yellow border on the inside.

<!-- image -->

When you open a Frame , the 3D window does not show an additional border on the inside.

<!-- image -->

When you open a simulation object , the 3D window shows a green border on the inside.

**SimTalk**

\_3D.openWindow [SimTalk]

<!-- image -->

When you open an animatable object , the 3D window shows a purple border on the inside.

<!-- image -->

#### Duplicate

Copies the selected object or model and creates a new class. This cuts all inheritance relations to the origin of the duplicated object. Changes you make to the original object are not passed on to the copy you create.

Instead of selecting Duplicate , you can hold down Ctrl and click the object you want to duplicate with the left mouse button. Then, hold down the mouse button, drag the copy to the location of your choice, which as a rule will be another folder, in the Class Library , and release Ctrl and the mouse button.

**Note**

If at all possible, we recommend to not change the standard settings of the built-in objects. If you customize them and then merge models later on or if you update the Class Library later on, your customized settings are going to be discarded and replaced by the standard settings. You then have to make your customizations again.

If you need objects with your own settings, we recommend to duplicate the respective object in the Class Library and then work with this class. Plant Simulation places duplicated and derived objects in the folder UserObjects .

SimTalk

duplicate [SimTalk]

create [SimTalk] - MUs

See also

Inheritance [general description]

UserObjects

Create and Work with Your Own Classes

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=U55PD40fHdUEsOXQ&amp;t=286](https://youtu.be/BvHLQCIjGIA?si=U55PD40fHdUEsOXQ&t=286)

#### Derive

Derives the selected object or model and creates an instance of the active class. Any change you make to the class object is immediately reflected in your derived instance, as Plant Simulation established an inheritance relation. This saves time and trouble if you want a number of objects to be exactly alike.

When you create a new object and when the new name, that you entered, cannot be assigned, Plant Simulation shows an error message.

Instead of selecting Derive , you can hold down the Ctrl and Shift keys, and click the object you want to derive an instance from with the left mouse button. Then, hold down the mouse button, drag the object to the location of your choice, for example into another folder in the Class Library , and release both keys and the mouse button.

**Note**

If at all possible, we recommend to not change the standard settings of the built-in objects. If you customize them and then merge models later on or if you update the Class Library later on, your customized settings are going to be discarded and replaced by the standard settings. You then have to make your customizations again.

If you need objects with your own settings, we recommend to derive the respective object in the Class Library and then work with this class. Plant Simulation places duplicated and derived objects in the folder UserObjects .

SimTalk

derive [SimTalk]

See also

Cut Inheritance

Inheritance [general description]

Duplicate

UserObjects

Create and Work with Your Own Classes

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=FiGxTtkTZBzRrAh9&amp;t=280](https://youtu.be/DwZkGMxXJIA?si=FiGxTtkTZBzRrAh9&t=280)

**Cut Inheritance**

#### Cut Inheritance

Cuts inheritance relations of the selected object to the object from which it was derived. Then, the object inherits its settings from the origin of the origin. In case the origin does not have an origin, the object does not inherit settings at all.

See also

Inheritance [general description]

Using Inheritance

Introducing Classes

Model Hierarchically [general]

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=AhX4KVRwupz-sLTW&amp;t=340](https://youtu.be/DwZkGMxXJIA?si=AhX4KVRwupz-sLTW&t=340)

#### Delete [class library]

Deletes the selected object(s) from the Class Library . To delete an object, click it once with the left mouse button and select Delete or press the Delete key on the keyboard.

**Note**

You cannot undo a delete action! We recommend to save your model before deleting objects, so that you can return to the previous version of your simulation model file!

You cannot delete currently active objects, like Methods , which are executed at the moment. This also applies when you want to delete a Frame , which contains active Methods . For this reason you cannot delete a Frame in the constructor -Method , if the constructor -Method itself is located in the Frame .

The command opens a dialog box, asking you to confirm your action. You can deactivate this feature under File &gt; Preferences &gt; User Interface &gt; Delete Objects &gt; Confirm .

SimTalk

deleteObject [SimTalk]

#### Rename [model or object]

Changes the name of the selected model or of the selected object. This opens the dialog Rename .

Enter a new name. You can enter any combination of letters, digits, and underscore (\_) characters, for example MyStation , MyStation1 , My\_Station\_1 . The name of an object cannot start with a digit, i.e., you cannot enter 1Station .

Note

You cannot change the name of the EventController and of the Connector .

The text box Label can hold a tag, other than the name, that the object shows in the Frame . The context menu that opens, when you click an object with the right mouse button, also provides this command.

SimTalk

setName [SimTalk]

See also

Name [SimTalk] - general description

#### Show Origin [class library]

Shows the origin of the selected object in the Class Library .

This means, that Plant Simulation highlights the object in the Class Library from which the selected object was derived and from which it inherits its properties. If the highlight does not change, then the object was not derived, but duplicated!

SimTalk

Origin [SimTalk] - general description

See also

Inheritance [general description]

Duplicate

Show the Origin of an Object in the Class Library

#### Show Structure [class library]

Shows the structure, i.e., the contents of the selected Frame/Folder in the Structure window.

<!-- image -->

**Note**

This command only applies to the Frame and the Folder .

The dialog is described in detail under Show Structure [Home ribbon] .

<!-- image -->

Hold down Shift and select this to zoom so close as if you selected the object or the graphic and selected the command Zoom to Objects [context menu] .

**See also**

Regular expressions are described in detail under regex\_search [SimTalk]

Show the Contents of a Frame in the Class Library

#### Show 3D Graphic Structure [context menu]

Opens a dialog which shows the graphic structure of the 3D-counterpart of the selected object in 2D.

<!-- image -->

The dialog is described under Show Graphic Structure [3D button] .

#### Show Inheritance [object]

Shows the paths of the objects which were derived from the selected object in the window Inheritance .

The window is described in detail under Show Inheritance [Home ribbon] .

<!-- image -->

**See also**

Inheritance [general description]

Show Inheritance Relations in the Class Library

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&amp;t=22](https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&t=22)

#### Show MU Statistics

Shows statistics data for the selected class of MU objects.

Plant Simulation shows all data of all objects of this class, which you inserted into the model, in the Statistics Report [described] . If you did not select a MU class, Plant Simulation shows all statistical data of all MU classes in the current Class Library .

#### Show Attributes and Methods [Home ribbon]

Shows the attributes , read-only attributes , and methods of the selected object.

<!-- image -->

Instead, you can also right-click the object in the Frame and press the F8 key.

The window is described in detail under Show Attributes and Methods .

SimTalk

**attributeWatchable [SimTalk]**

See also

Show Attributes and Methods [described]

Working with the Window Show Attributes and Methods

#### Edit User-defined Attributes [Class Library]

Opens the dialog Edit User-defined Attributes . Here you can define your own attributes.

**SimTalk**

| createAttr [SimTalk]   | getAttrValue [SimTalk]   |
|------------------------|--------------------------|
| deleteAttr [SimTalk]   | NumAttr [SimTalk]        |
| getAttrName [SimTalk]  | setAttrType [SimTalk]    |
| getAttrNo [SimTalk]    | setAttrValue [SimTalk]   |
| getAttrType [SimTalk]  |                          |

See also

User-defined Attributes [general description]

Create a User-defined Attribute Manually

Create a User-defined Attribute During the Simulation

New [user-defined attribute]

Edit [user-defined attribute]

Delete [user-defined attribute]

#### Edit Controls [class library]

Opens one of the controls, which you entered on the tab Controls . Select the name of the control on the submenu.

The command also shows the controls you entered by selecting Tools &gt; Edit Controls in the dialog of an object.

The context menu only shows the menu item Edit Controls if you actually did enter one or several controls.

**See also**

Tab Controls [general description]

Edit Controls [material flow objects]

Edit Controls [MUs]

Edit Controls [Home ribbon]

<!-- image -->

#### Edit Icons [context menu]

Opens the Icon Editor . Here you edit, delete, and add new icons to objects and models. The context menu that opens, when you click an object with the right mouse button, also provides this command.

Note

The command also applies to 3D Only models.

See also

Icon Editor

#### Edit 3D Properties [Frame]

Opens the dialog Edit 3D Properties . Here you can edit the 3D properties of the object.

Only the context menu of the Frame provides this command.

See also

Edit 3D Properties [dialog]

#### Edit Display Panel [context menu]

Opens the Display Panel . Add a new display panel to the selected object or edit, or delete an existing display panel here.

**Note**

3D models do not provide this command as they do not show display panels .

See also

Display Panel [object]

#### Make Library

Make Library

Transforms the selected folder into an object library. A library is a collection of objects for which you specify a version .

You can maintain the library or enhance or extend it over time. When you do this and save the new version of the library ( Save a Folder as a Library ), you should also increment the version number of your library. You can use this library in different simulation models and you can share the library file (.pslib) with your colleagues. The version number enables you to either update your simulation models with a newer version of the library or to continue using the present dated version.

The command opens the dialog Library Information .

<!-- image -->

- Type in the Name of the library. You can type in any combination of letters, numbers, spaces, and special characters. The library name does not have to be the same as the name of the library folder.
- Type in the Version of the library. You can enter any number of numbers and letters separated by periods.
- Type in a meaningful Description of the library. The dialog Manage Class Library shows this description.

<!-- image -->

##### Make Library

- Type in one or more alternative paths for your library. As a rule, you will not enter an alternative path. Plant Simulation identifies a library by its absolute path to the library folder in the Class Library . When you type in an alternative path, this absolute path will also be assigned to this library.

This may be helpful for two reasons:

1. When you rename the library folder in a new version of your library or when you move the library into another folder, the absolute path of the library changes.

<!-- image -->

<!-- image -->

Plant Simulation will from then on treat the library as another library. If you do not want this, you can type in the previous path to the library as an alternative path. This way you can update a model, for which the library is still located under the previous path, with the new library. For this model, the library remains at its previous location in the Class Library .

<!-- image -->

2. You can use alternative paths to assign several names in different languages to the library folder. We, for example, also assigned the German path .Tools.EngpassAnalyse language to the library .Tools.BottleneckAnalyzer . For this reason Plant Simulation considers both folders as the same library and can thus update both folders with the same library file.

**Note**

When you type in the name of a language between $ signs in front of the alternative path, for example $German$ or $Japanese$ , Plant Simulation will automatically use this path, when you load this library into a model with this language, i.e., when the model did not already contain this library. The alternative path for the BottleneckAnalyzer is $German$.Tools.EngpassAnalyse for example.

**Note**

You can type in any number of alternative paths. Separate alternative paths with a line break.

- Select the check box Requires 3D to tell the user that the library requires 3D .
- Clear the check box Prohibit Access to the Computer [Make Library] to allow the methods of that library to access your computer.
- Select the check box Lock Library to lock the library.
- Click OK .

<!-- image -->

Plant Simulation saves the folder and all objects it contains as a library. The icon of a library in the Class Library looks like this .

To also use this library in other models, save the library as a file. To do so, click the library with right mouse button and select Save/Load &gt; Save Library As . If you want to change the information you typed in at a later point in time, right-click the library folder and select Edit Library Information .

SimTalk

writeObject [SimTalk]

getLibraryInfo [SimTalk]

setLibraryInfo [SimTalk]

See also

Save Library As

Save a Folder as a Library

Edit Library Information

Manage Class Library

##### Requires 3D

To set that this library requires 3D to display the objects it contains and to work correctly, select this check box.

When you load a library for which this setting is selected, and when 3D is not activated, Plant Simulation asks if you would like to activate 3D . If you click No , the library will not be loaded.

##### Prohibit Access to the Computer [Make Library]

To deny the methods of this library access your computer select this check box. This is the default setting. Clear the check box to allow the methods of the library access to your computer.

If an attempt is made to execute a potentially dangerous command, Plant Simulation checks from which Method the source code is inherited and if this Method is located within a library before it checks the Model Setting &gt; Prohibit Access to the Computer . In this case the library setting applies instead of the model setting.

**Note**

Models, which you created in previous versions of Plant Simulation , work as they did before without any access restriction. If you would like these models access to your computer, clear the check box.

SimTalk

isComputerAccessPermitted [SimTalk]

See also

Prohibit Access to the Computer [model settings]

Specifying Start Options , -TrustModel

Trust-ID to Permit Models Access to the Computer

getLibraryInfo [SimTalk]

**Lock Library**

##### Lock Library

To prevent that objects, which are located within the locked library, can be opened interactively, select this check box. You can still open instances of these objects, which are inserted in Frames located outside of the library as you normally would.

If you develop a library and pass it on and when you want to provide newer versions of the library later on, you should, as a rule, lock the library. This prevents users from inadvertently changing the library. When the user then updates the simulation model with a newer version of the library later on, these changes would be overwritten with the settings of the updated library.

If you select Lock library , Plant Simulation opens a dialog into which you can type in a Password . If you do not type in a password, the library can be unlocked again at any time. When you assign a password, the library can only be unlocked after typing in the correct password. This is helpful when you not only want to prevent inadvertent but also deliberate changes to the library.

A locked library can still be changed via information flow. This ensures that a locked library behaves the same as an unlocked library. Therefore, locking a library does not completely prevent inadvertent changes.

**Note**

Locking a library is not suited for protecting the know-how you invested in your library as instances of the library objects can be opened and viewed. To protect your know-how, you can encrypt your methods. In addition, you can reliably prevent an object and all of its instances from being opened by typing in an encrypted user-defined method attribute as the Open Control of an object. Then, only the encrypted Open Control can open the object.

**Note**

If you want to change a locked library and if you know the password, you can unlock the library to do so. Then lock the library again before saving it.

Instead of unlocking the library you can also temporarily allow changes to the library without unlocking it. Hold down Shift when you close the message window that opens when you try to open a locked library object. Plant Simulation asks for the password. When you type in the password, you can change the library until you close the model. When you then open the library, it will be locked again.

SimTalk

lockFolder [SimTalk]

IsLocked [SimTalk]

#### Edit Library Information

Opens the dialog Library Information . It shows the information you entered, when you saved a folder as a library with the command Make Library . You can edit this information to reflect changes you made.

<!-- image -->

<!-- image -->

**SimTalk**

writeObject [SimTalk]

getLibraryInfo [SimTalk]

setLibraryInfo [SimTalk]

isComputerAccessPermitted [SimTalk]

See also

Save a Folder as a Library

Manage Class Library

Make Library

#### Find Object

Find Object [context menu]

Opens the dialog Find Object . Specify what you want to find and specify search settings.

<!-- image -->

The Frame and the folder in 3D also provide the context menu command Find Object , compare Context Menu of the Background of the Scene .

**See also**

<!-- image -->

| Find Objects and Text in Your Simulation Model   | Ignore Inherited Name or Text               |
|--------------------------------------------------|---------------------------------------------|
| Drop-down list boxes                             | Look In                                     |
| Regular Expression Window                        | Include Subframes [Frame]                   |
| Match Whole Word Only [Find]                     | Find [button]                               |
| Match Case [Find]                                | List of Search Results                      |
| Regular Expression [Find]                        | Context Menu of the Background of the Scene |

##### Drop-down list boxes

Select what Plant Simulation finds from the left drop-down list.

<!-- image -->

Depending on what you select in the list to the left, you will enter into the right list:

- The Name of the object you want to find.
- A Condition . A condition can be a SimTalk expression whose attributes or methods are identical to the expression, which you type into the drop-down combo box. You might, for example, enter the name of an attribute or a method and the expression you are looking for, such as Proctime = 100 , or OpenCtrl = void , etc.
- An expression contained in any of the built-in or the user-defined Attributes of the objects within the search scope. To evaluate them, Plant Simulation converts the attribute values of the objects to be checked into strings. Plant Simulation shows the name of the attribute in which the text was found in parentheses after the object in the results list
- The Source Code which you typed into a Method object. This also finds source code in user-defined attributes of data type method .

To jump to the location of the source code in the Method Editor , double-click the source code in the results field. Double-click again to jump to the next occurrence of the source code. To jump to the previous occurrence of the source code, hold down Shift and double-click.

- An expression contained in a list or Table object within the search scope.

Depending on what you select, Plant Simulation selects or clears the check boxes Match Whole Word Only [Find] , Match Case [Find] , Regular Expression [Find] , and Ignore Inherited Name or Text .

See also

Find Objects and Text in Your Simulation Model

##### Regular Expression Window

To use regular expressions in your search, click the button. Select any of the displayed regular expressions in the window Regular Expression . Plant Simulation enters the special characters designating that expression into the right drop-down list. Enter the expression, which you want to find, after the special character.

<!-- image -->

| Select                           | To enter and to find   |
|----------------------------------|------------------------|
| Any single character             | .                      |
| Beginning of line                | ^                      |
| End of Line                      | $                      |
| Beginning of word                | \<                     |
| End of word                      | \>                     |
| Group                            | \(\)                   |
| Zero or one matches              | ?                      |
| Zero or more matches             | *                      |
| One or more matches              | +                      |
| Any one character in the set     | []                     |
| Any one character not in the set | [^]                    |
| Or                               | \&#124;                |

Searching with regular expressions enables you to use wild cards in the string you are searching for. The period character . for example, is a wild card for any character. When Plant Simulation searches for a.b , it will find all strings consisting of a sequence of the character a , followed by any character, and the character b . Compare Show Structure [class library] for examples.

**Note**

Plant Simulation only uses the regular expression you select, when you also select the check box Regular Expression [Find] !

**Match Whole Word Only [Find]**

##### Match Whole Word Only [Find]

To search for whole words only, select this check box. When you clear it, Plant Simulation also searches for parts of words.

##### Match Case [Find]

To match the case, upper or lower, of the expression you typed in, select this check box.

To find the expression regardless of the case, clear it.

**Regular Expression [Find]**

##### Regular Expression [Find]

To use regular expressions in your search, select this check box.

Plant Simulation then finds the regular expressions, which you selected in the Regular Expression Window .

##### Ignore Inherited Name or Text

To ignore the name or text that an object inherited in your search, select this check box.

Plant Simulation then only finds the original name or text, and not the name or text in derived or duplicated objects.

**Look In**

##### Look In

Type in the name of the folder or the Frame , in which Plant Simulation is going to start searching for the expression you typed into the text box.

<!-- image -->

Or click the button and select a folder or a Frame in the dialog Select Object .

- To search on the highest level of the structure, accept the default that Plant Simulation enters, namely the period (.).
- To search the entire Class Library , also select the check box Include Subframes [Frame] .

<!-- image -->

##### Include Subframes [Frame]

To also search all Frames located within the Frame in which the item you are searching for is located, select this check box.

**Find [button]**

##### Find [button]

To start searching for the term, which you entered, click Find .

##### List of Search Results

Plant Simulation shows the items that it found during the search in the list field. Double-click the name of an object or of the source code in the list field to open its dialog box. You can also right-click the object and select Open on the context menu. Double-clicking or selecting Open again jumps to the next occurrence of the found item.

<!-- image -->

When you searched for Source Code , you can right-click the Method(s) in the results list and select to replace the found source code with the source code, which you type into the dialog box Replace in Selected Methods .

<!-- image -->

#### Save Object As

Saves the selected object as a Plant Simulation object file (.psobj). Type a name into the dialog Save As and specify a location.

Plant Simulation saves the object, and all objects, which that object uses, together with their folders and paths. Objects which the object to be saved does not use, are deleted. This way you can store often-used objects outside of the model and integrate it into other simulation models or share it with your co-workers.

**Note**

If you want your saved object to also contain existing 3D data, 3D has to be running when you save the object.

To save a folder as an object file, right-click that folder and select Save Folder As .

SimTalk

writeObject [SimTalk]

replace [SimTalk]

ReplacementMode [SimTalk]

See also

Load Object

Replacement Mode

Save a Folder or an Object and Load it into Another Model

#### Save/Load

Save/Load

Provides submenu commands for saving and loading objects into the current simulation model.

Note

Plant Simulation only shows this command, when you select a folder .

<!-- image -->

The context menu command Save/Load provides submenu commands:

<!-- image -->

**Save Folder As**

##### Save Folder As

Saves the selected folder as a Plant Simulation object file (.psobj).

Enter a name into the dialog Save As and specify a location where the object file will be saved.

Plant Simulation saves the folder and all objects it contains to the object file.

You can then load this folder into other simulation models and share it with your co-workers.

SimTalk

**writeObject [SimTalk]**

##### Save Library As

Saves the selected library as a Plant Simulation library file (.pslib).

- Click the library folder with the right mouse button and select Save Library As .
- This opens the dialog Library Information . If necessary you can change information about the library here, you can, for example, increase the Library version number . Then click OK.
- Enter a name into the dialog Save As and specify a location where the object file will be saved. If you would like the library to be available in the dialog Manage Class Library later on, you have to select a location within the directory which you entered under File &gt; Preferences &gt; General &gt; Libraries Directories .

Plant Simulation saves the library to the specified library file. You can then load this library into other simulation models and share it with your co-workers.

**Note**

When you deactivate the 3D part of your model, by clicking Activate 3D and when you then make a library out of the model, the saved library does not contain the 3D part any longer.

When you then import this library into another model, Plant Simulation creates the 3D part from scratch and does not use the 3D part of the original library for which you deactivated 3D.

If you need the 3D part of the library in the future, 3D has to be active when you save the library.

SimTalk

writeObject [SimTalk]

getLibraryInfo [SimTalk]

setLibraryInfo [SimTalk]

See also

Make Library

Save a Folder as a Library

##### Load Object

Loads an object or a Frame , which you saved as an object file (.psobj) with the command Save Object As , into the simulation model.

Plant Simulation loads the object, with all of its existing paths and the folders, sub-folder and classes the objects inherit values from, into the Class Library at the Basis level. It does not matter on which of the built-in folders, such as MaterialFlow , MUs , etc. you clicked, when you selected Load Object .

- Right-click any folder in the Class Library and select Load Object on the context menu.
- Select the object in the dialog Open .
- If an object or a Frame with the same name as the object to be loaded already exists in your simulation model, Plant Simulation opens the dialog Replace or Rename Class .
- To Replace the Loaded Class With the One in the Class Library , select the radio button. Then, Plant Simulation does not load the new object, but replaces it with the existing object and merges all inheritance hierarchies into one.
- To replace all duplicate objects, click Replace All .
- To Rename and Keep the Duplicate Class , select this.

<!-- image -->

Enter a new name for the duplicate object into the text box.

**Note**

When the object to be replaced is a Frame , click Replacement Mode on the Frame ribbon tab of the Frame . Then, select if you want to Merge the contents of the new Frame with the existing one or if you want to Exchange the existing Frame with the new Frame .

Repeat this until all duplicate objects are renamed or replaced.

If you are unsure if both classes are identical, we recommend that you enter a new name and compare the classes. You can still replace the objects at a later point in time:

- Hold down Alt , click the replacing object and drag it over the object to be replaced while holding the left mouse button down.
- When replacing and merging is possible, a dialog opens where you can confirm that you want to replace the object or not replace it.

Instead of using Load Object , you can also drag a psobj file from the Windows Explorer to the Class Library , and drop it there.

**Note**

If the loaded object does not contain existing 3D data, 3D was not running when you saved the object. To also export 3D data, save the object again while 3D is running. 3D also has to be active in the model into which you load the object.

SimTalk

loadObjectAs [SimTalk]

autoexecLoadObj [SimTalk]

replace [SimTalk]

getNodeName [SimTalk]

See also

Save Object As

Replacement Mode

Load an Object or a Folder into Your Simulation Model

Save a Folder or an Object and Load it into Another Model

##### Load Object into Folder

Loads an object or a Frame that you saved as an object file (.psobj) with the command Save Object As into a folder in the Class Library .

It also loads a library, which you saved as a library file (.pslib) with the command Make Library , into the selected folder in the Class Library .

As a rule, you will first create a new folder. Then click this folder with the right mouse button and select Load Object into Folder to load the object, with its complete structure of objects it uses and used by it, into this new folder.

You will use Load Object into Folder , when you do not want to replace any of the existing objects and their hierarchical structure in your simulation model with the object/objects you are going to load.

The tools in the Tools folder in the Class Library , such as the BottleneckAnalyzer , use this technique and provide their own parametrized BasicObjects that are independent of the object classes in the built-in folders.

SimTalk

autoexecLoadObj [SimTalk]

See also

Save Object As

##### Update Class Library

Loads an object or an object library into the Class Library at the Basis level.

<!-- image -->

- You can load an object that you saved as an object file (.psobj) with the command Save Object As .
- You can load a folder that you saved as a library (.pslib) with the command Make Library .

You will use Update Class Library to update a library, you and your coworkers are working on, with the most up-to-date classes you developed.

When loading the object file, Plant Simulation supposes that the classes in the file it is loading are the most recent ones, and replaces any existing classes with the same name in your model file. This replaces the old class with the new class, but attaches any instances of the old class to the new class, and thus preserves the settings you made in these instances. This applies for classes that are located in the hierarchy directly below the newly saved class.

For classes that were saved through an inheritance relation, and that are located outside of this hierarchy below a class, Plant Simulation opens a dialog, in which you have to select to replace any duplicate classes or to rename them.

**Note**

Your license determines how you can update the Class Library : When you are running a Standard License or an Application License you can only update the Class Library with objects, which you saved in a Professional License . When loading an object you can only merge Frames , when the object to be loaded was saved in a Professional License .

**SimTalk**

autoexecLoadObj [SimTalk]

See also

Update the Class Library

Configure the Class Library

#### Convert all Methods to New Syntax

Converts the source code of all Methods in the Class Library or in the selected folder to the new syntax of SimTalk 2.0.

Plant Simulation shows Convert all Methods to New Syntax when you hold down Shift and click the object Basis or a folder in the Class Library with the right mouse button.

<!-- image -->

**See also**

New Syntax [command]

Update Arbitrary Old Models &gt; Convert the Source Code of All Methods to SimTalk 2.0

SimTalk 2.0 and SimTalk 1.0 Compared

Converting Data Types

#### Revert all Objects to Standard Graphics

Reverts the graphic of the class objects to the standard graphic of the Plant Simulation version you are using. The standard graphic is the graphic that Plant Simulation shows in the model, when you create a new model. It is located in the Plant Simulation installation folder &gt; BasicObjects . Standard graphics encompass the standard icons of the object in 2D as well as the 3D standard graphics.

Plant Simulation shows the context menu command Revert all Objects to Standard Graphics when you hold down Shift while clicking the object Basis or a folder in the Class Library with the right mouse button.

<!-- image -->

When you call the command for a folder, Plant Simulation reverts the graphics of all objects in that folder to the standard graphic, including the objects in subfolders. Plant Simulation skips library folders. Objects which inherit their graphics are not touched either. To prevent visibility settings from being lost, the command does not affect Frames either.

**Note**

Changes you made to the standard graphics will be lost.

The command deletes, for example, additional icons you created for the objects.

It also deletes 3D graphics with which you replaced the default graphics of the MUs , for example transport boxes instead of the pallets.

See also

Update Arbitrary Old Models &gt; Use the Standard Graphics of the 3D Simulation Objects

Update Arbitrary Old Models &gt; Use New Standard Graphics of the 2D Objects

