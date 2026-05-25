### Home Ribbon Tab

The Home ribbon tab of the Frame provides a number of commands to access its functions.

<!-- image -->

#### Home Ribbon Tab

<!-- image -->

| Command                                                      | Looks like this   | Method or Attribute                                                                                  |
|--------------------------------------------------------------|-------------------|------------------------------------------------------------------------------------------------------|
| Open Class [Home ribbon]                                     |                   | -                                                                                                    |
| Paste Contents of the Clipboard [Home ribbon] Multiple Paste |                   | pasteClipboard [SimTalk] - Frame                                                                     |
| Cut [Home ribbon]                                            |                   | cutColumn [SimTalk] cutRow [SimTalk] - DataTable Lists                                               |
| Copy [Home ribbon]                                           |                   | selectionToClipboard [SimTalk] for the Frame copyObjectsToClipboard [SimTalk] copy [SimTalk] - lists |
| Delete [Home ribbon]                                         |                   | deleteObject [SimTalk]                                                                               |
| Select All [Home ribbon]                                     |                   | selectContents [SimTalk]                                                                             |
| Rename [Home ribbon]                                         |                   | -                                                                                                    |
| Delete MUs [Home ribbon]                                     |                   | -                                                                                                    |
| Edit Icons [Home ribbon]                                     |                   | openImg [SimTalk]                                                                                    |
| Edit Display Panel [Home ribbon]                             |                   | -                                                                                                    |

<!-- image -->

| Command                                    | Looks like this   | Method or Attribute                                                                                      |
|--------------------------------------------|-------------------|----------------------------------------------------------------------------------------------------------|
| Edit 3D Properties [dialog] Create in 3D   |                   | - CreateIn3D [SimTalk]                                                                                   |
| Edit Controls [Home ribbon]                |                   | various                                                                                                  |
| Edit Observers [Home ribbon]               |                   | addObserver [SimTalk] attributeWatchable [SimTalk] removeAllObservers [SimTalk] removeObserver [SimTalk] |
| Edit User-defined Attributes [Home ribbon] |                   | createAttr [SimTalk]                                                                                     |
| Show Attributes and Methods [described]    |                   | attributeWatchable [SimTalk]                                                                             |
| Show Statistics Report [Home ribbon]       |                   | showStatisticsReport                                                                                     |
| Show Structure [Home ribbon]               |                   | -                                                                                                        |
| Show Inheritance [Home ribbon]             |                   | -                                                                                                        |

**Home Ribbon Tab**

<!-- image -->

| Command                    | Looks like this   | Method or Attribute   |
|----------------------------|-------------------|-----------------------|
| Context Help [Home ribbon] |                   | -                     |
| Optimize Model             |                   | -                     |
| Manage Class Library       |                   | -                     |

Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=fE-zocnAUmqFlP3J&amp;t=140](https://youtu.be/FNpiAaUK8iM?si=fE-zocnAUmqFlP3J&t=140)

#### Open Event Controller

Opens the dialog box of the EventController .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

To open the Dialog Box of the Event Debugger hold down Shift and click the button

.

<!-- image -->

See also

EventController

#### Event Controller

Event Controller [Home ribbon]

Provides a number of commands for controlling the simulation.

<!-- image -->

The command Event Controller provides these commands:

- Reset Simulation [Home ribbon]
- Start/Stop Simulation [Home ribbon]
- Start Full Speed Simulation [Home ribbon]
- Start Fast Forward Simulation [Home ribbon]
- Single Step Simulation [Home ribbon]
- Slower/Faster

Instead of clicking the buttons, you can also click the respective buttons in the dialog of the EventController .

<!-- image -->

<!-- image -->

<!-- image -->

When you are running the simulation with the EventController buttons on the Home ribbon tab, Plant Simulation shows the time as it progresses in the status bar . When the simulation is finished, the status bar shows the end time .

**Reset Simulation [Home ribbon]**

##### Reset Simulation [Home ribbon]

Resets your simulation model. Plant Simulation then calls all Methods named reset in your simulation model.

<!-- image -->

Clicking the button has the same effect as clicking Reset Simulation in the EventController .

SimTalk

reset [SimTalk] - EventController

See also

Reset Simulation [EventController]

##### Start/Stop Simulation [Home ribbon]

Starts the simulation. To stop the simulation after the active simulation event has been processed, click the button again.

<!-- image -->

Clicking the button has the same effect as clicking Start/Stop Simulation in the EventController .

SimTalk

start [SimTalk] - EventController

stop [SimTalk] - EventController

See also

Start/Stop Simulation [EventController]

##### Start Full Speed Simulation [Home ribbon]

Starts the simulation run with the animation of MUs and States and with maximum speed. This makes the simulation run as fast as possible.

<!-- image -->

Start Full Speed Simulation updates a number of values, for example of objects of type Variable or Display , etc.

When you click Start Full Speed Simulation , Plant Simulation ignores the Real Time scaling factor .

SimTalk

Realtime [SimTalk]

RealtimeScale [SimTalk]

start [SimTalk] - EventController

See also

MUs and States [Home ribbon]

Real-time x [EventController]

<!-- image -->

##### Start Fast Forward Simulation [Home ribbon]

Starts the simulation run without the animation of MUs and States and with maximum speed. This makes the simulation considerably faster.

<!-- image -->

Start Fast Forward Simulation prevents updating a number of values, for example of objects of type Variable or Display , etc.

When you click Start Fast Forward Simulation Plant Simulation ignores the real time scaling factor.

This has the same effect as clicking Start Fast Forward Simulation in the EventController .

See also

MUs and States [Home ribbon]

<!-- image -->

Real-time x [EventController]

Start Fast Forward Simulation [EventController]

Single Step Simulation [Home ribbon]

Processes the next simulation event in line, stops the simulation afterward, and thus proceeds through your model step-by-step.

<!-- image -->

When you hold down Shift while clicking Step , Plant Simulation opens the Method Debugger for all methods and formulas, which are executed while the event is being processed. This means that the debugger opens for all executed controls, formulas and for suspended methods , which were woken up.

This has the same effect as clicking Single Step Simulation in the EventController .

See also

Single Step Simulation [EventController]

Method Debugger

##### Simulation Speed [Home ribbon]

The slower and faster buttons control the speed of the simulation.

<!-- image -->

- To increase the speed of the simulation, drag the slider to the right or press the right arrow key.
- To decrease the speed of the simulation, drag it to the left or press the left arrow key.

Decreasing the speed enables you to better follow the movements of MUs , as Plant Simulation shows their icons for a longer time on the same station.

This has the same effect as dragging the Slower/Faster slider of the EventController .

<!-- image -->

See also

Slower/Faster

#### MUs and States [Home ribbon]

Deactivates or activates the animation of Mobile Objects , Variables , states, and graphics changes in your simulation model. During the simulation run the Animation shows the state of the objects and the positions and movements of the MUs .

<!-- image -->

The button not only deactivates the animation of mobile objects during the simulation but also prevents updating a number of values, for example of objects of type Variable or Display .

- When you activate MUs and States , you immediately detect the flow of the MUs and are able to detect blocked stations, where the MUs pile up.

<!-- image -->

If MUs and States and State Icons/LEDs &gt; Use LEDs are active, the objects always show their current state as one or more colored dots in the LED display along the upper border of the icon. This way you can detect which object obstructs the flow of materials.

If you activated MUs and States and activated State Icons/LEDs &gt; Use State Icons , the objects always show their current state with the respective icon.

- When you do not need to view animated MUs , deactivate MUs and States , as this improves the simulation speed. The result of the simulation is the same either way. When you deactivated the animation while an object intends to change its state, Plant Simulation delays its display on screen until you activate the animation again or until the object is selected.

Clicking Start Fast Forward Simulation in the EventController deactivates MUs and States .

<!-- image -->

**SimTalk**

**animation [SimTalk]**

**See also**

| _Methods for Animating Objects                     | LEDs and States of the Mobile Objects                   |
|----------------------------------------------------|---------------------------------------------------------|
| _Attributes for Animating Objects in 2D            | MUAnimation [3D] in 3D                                  |
| Attributes for Animating MUs in 2D                 | Debugger > View Menu > MUs and States [Method Debugger] |
| LEDs and States of the Material Flow Objects in 2D |                                                         |

#### Open Location [Home ribbon]

Opens the Frame , in which the selected object is located. It also scrolls the Frame window so that the selected objects will be displayed.

<!-- image -->

- When you are working with a Frame , the command opens the Frame in which this Frame is located.
- When you are working with a Method , the command opens the Frame in which the Method is located, or the object for which you defined the user-defined attribute of data type method .
- When you are working with a List , the command opens the Frame in which the List is located, or the object for which you defined the user-defined attribute of data type method .
- When you are working with icons , the command opens the Frame in which the object is located whose icon you are editing.

**SimTalk**

Location [SimTalk] - material flow objects

#### Open Origin [Home ribbon]

Opens the object from which the selected object was derived.

<!-- image -->

- When you are working with a Frame , the command opens the window of the Frame from which the selected Frame was derived. This Frame is the origin of the selected Frame . Suppose that FrameB was derived from FrameA , which in turn was derived from the root frame named Frame in the Class Library . Then FrameA is the origin of FrameB and the Frame is the origin of FrameA .
- When you are working with a Method , the command opens the window of the Method from which the selected Method was derived.
- When you are working with a List , the command opens the window of the List from which the selected List was derived.
- When you are working with a user-defined attribute in 3D , the command opens the window of the user-defined attribute from which the selected user-defined attribute was derived.
- When you are editing icons , the command opens the icon of the class of the selected object in the Icon Editor . You can then edit the icon of the class. Your changes to the icon will then be propagated to the instances of object.

Instead, you can also click the object with the right mouse button and click the button on the mini toolbar

<!-- image -->

above the context menu.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

When you hold down Shift while clicking the button, Plant Simulation shows the location of the origin of the object.

<!-- image -->

When you hold down Shift in a Method or in the Method-Debugger while clicking the button, Plant Simulation shows the Method from which the current Method inherits its source code.

SimTalk

Origin [SimTalk] - general description

#### Open Class [Home ribbon]

Opens the dialog of the class of the selected object in the Class Library from which you derived the selected object.

<!-- image -->

Suppose that we derived FrameB from FrameA , which we derived from the root Frame in the Class Library . Then the Frame is the class of FrameA and of FrameB .

When you apply the command Open Class for an instance of an object, Plant Simulation moves up in the inheritance structure until it reaches an object in the Class Library . It then opens that object.

- When you are working with a Frame , the command opens the window of the Frame class in the Class Library .
- When you are working with a Method , the command opens the window of the Method class in the Class Library .
- When you are working with a List , the command opens the window of the respective List class in the Class Library .

Instead, you can also click the object with the right mouse button and click the button on the mini toolbar

<!-- image -->

above the context menu.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

When you hold down Shift while clicking the button, Plant Simulation shows the location of the class of the object.

See also

Derive

#### Paste Contents of the Clipboard

Paste Contents of the Clipboard [Home ribbon]

Pastes the contents of the clipboard into the designated object.

<!-- image -->

- When you are working with a Frame , the command Paste pastes the contents of the clipboard into the Frame at the position of the mouse pointer.
- When you are working with a List , the command Paste pastes the contents of the clipboard into the list/table. Provided both lists have the same structure, you can insert part of a copied list into another list. Plant Simulation pastes entire rows or columns as a whole and does not touch adjacent rows or columns.
- When you are working with a Method , the command Paste pastes the contents of the clipboard at the position of the cursor.
- When you are working with the Icon Editor , the command Paste pastes the copied icon from the clipboard.

When you selected an object in 3D , the subcommand Multiple Paste is activated.

When you click the Paste button or select the menu command Paste on the context menu, 3D pastes the object to the coordinates retrieved from the object in the clipboard. The command pastes the object into the opened object, regardless of the selection.

For animatable objects 3D might change the position, i.e., the coordinates, at which the object from the clipboard will be pasted, depending on the position at which other objects are located at:

- When any other object is already located at the destination coordinates of the object on the clipboard, 3D pastes the copy using the offset you enter under Offset in the dialog Multiple Paste .
- When another object is located at the position determined by the offset, 3D repeats the offset until no object is located at the destination. To move the object to the location of your choice, click it and drag the mouse.

Instead, you can also click the object with the right mouse button and click the button on the mini toolbar

<!-- image -->

<!-- image -->

<!-- image -->

SimTalk

pasteClipboard [SimTalk] - Frame

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

above the context menu.

**Multiple Paste**

##### Multiple Paste

Opens the dialog with settings for pasting multiple copies of the object you copied.

<!-- image -->

<!-- image -->

<!-- image -->

**Number of Copies**

Type the number of objects you would like to paste into the active scene, including the first copy, here. You can also roll the mouse wheel up or down to increase or decrease the number.

<!-- image -->

When you type in the number 5 , for example, 3D pastes 5 objects. Type in an integer greater than zero. Type in 1 to have 3D perform the default paste operation, i.e., paste the object from the clipboard once.

**Offset**

Type the offsets on the X, Y, and Z axes into the text boxes below X-Offset , Y-Offset , and Z-Offset . 3D inserts objects you paste using the offset(s) on the axis or axes you set. 3D places the first pasted object at the position defined by the distance of the offset from the original location!

Paste

To paste multiple copies of the object and to close the dialog, click Paste . 3D uses the Number of copies and the Offset you selected.

<!-- image -->

**See also**

Simultaneously Paste Multiple Copies

<!-- image -->

#### Cut [Home ribbon]

Cuts the selection to the clipboard.

<!-- image -->

- When you are working with a Frame , the command Cut cuts the selected object from the Frame and places it onto the clipboard.
- When you are working with a List , the command Cut cuts the selected cell or range of cells of the list/table to the clipboard. From there you can insert it anywhere into the same or into other lists.

Click into the cell at which the range you want to cut starts and drag the mouse to the cell at which the range ends. The list dims the range of cells, and you may then Cut it to the clipboard. Plant Simulation removes the cells you cut from the list and moves the following cells up. Click the row index to select an entire row of cells, click the column header to select an entire column of cells, which you want to cut, i.e., to delete from the list.

- When you are working with a Method , the command Cut Text cuts the selected source code to the clipboard.

Instead, you can also click the object with the right mouse button and click the button on the mini toolbar

<!-- image -->

<!-- image -->

**Note**

If the object you cut has derivatives, i.e., objects that were derived and inherit settings from it, Plant Simulation opens a dialog asking you to confirm that these derivatives will be deleted.

**SimTalk**

cutColumn [SimTalk] for Lists

cutRow [SimTalk] - DataTable for Lists

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

above the context menu.

#### Copy [Home ribbon]

Copies the selection and places it onto the clipboard.

<!-- image -->

- When you are working with a Frame , the command Copy copies the selected objects to the clipboard.
- When you are working with a List , the command Copy copies the selected cell or range of cells to the clipboard.

**Note**

To copy comments, which you typed into the text box Show Comment , click the right mouse button and select Copy on the context menu!

- When you are working with a Method , the command Copy Text copies the selected source code to the clipboard.
- When you are working with an animatable object which you copy in a window in 3D , the command copies the path of the object. You can then paste that path, for example, .Models.Model.Station into a Method or a Comment .
- When you are working with an animatable object which you copy in a window in 3D , the command copies the following statement. You can then paste that statement, for example, .Models.Model.\_3D.getObject("MyAnimatableObject") , into a Method or a Comment .
- When you are working with a graphics object which you copy in a window in 3D , the command copies the following statement. You can then paste that statement, for example, .Models.Model.\_3D. «method»([0], «Parameters»), .Models.Model.\_3D.«method»([0], «Parameters», "Group2"), .MaterialFlow.Robot.\_3D.getObject("ZAxis").«method»([0], «Parameters») , into a Method or a Comment .

Instead, you can also click the object with the right mouse button and click the button on the mini toolbar

<!-- image -->

<!-- image -->

<!-- image -->

SimTalk

selectionToClipboard [SimTalk] for the Frame

copy [SimTalk] - lists

copyObjectsToClipboard [SimTalk]

See also

Insert Objects into the Scene above the context menu.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

#### Delete [Home ribbon]

Deletes the objects you selected in the Frame . Be aware that you cannot undo a delete action!

<!-- image -->

Plant Simulation opens a dialog in which you can confirm that you want to delete the selected object(s)

- Click Yes to delete the object. Hold down Shift and click Yes to delete all selected objects.
- Click No to not delete the object.
- Click Cancel to cancel deleting.

You can deactivate the confirmation query by selecting the check box Confirm under File &gt; Preferences &gt; User Interface &gt; Confirm Deleting Objects [preferences] .

You can also press Del to delete the selected objects.

SimTalk

deleteObject [SimTalk]

#### Select All [Home ribbon]

Selects all objects that are located in the Frame window .

<!-- image -->

- When you are working with a Frame , the command Select All selects all objects located in the Frame . Instead, you can also press Ctrl+A .
- When you are working with a list , the command Select All selects the entire list, i.e., all cells containing an entry.
- When you are working with a Method , the command Select All selects the entire source code.

SimTalk

selectContents [SimTalk]

#### Delete MUs [Home ribbon]

Deletes all mobile objects on all objects in all Frames , which the EventController controls, to which the active Frame belongs.

<!-- image -->

**Note**

If your simulation model still contains parts after selecting the command, meaning that Plant Simulation does not start counting parts with 1, for example MUs.Part:1 , for a new simulation run, check if the model contains additional Frames with inserted EventControllers . Reset the EventControllers there as well.

See also

Delete Parts with the Mouse or when Resetting the Model

Mobile Units [MUs]

#### Rename Object or User-defined Attribute

Rename [Home ribbon]

Opens the dialog box Rename . Then, change the name and the label of the selected model or of the selected object.

<!-- image -->

- Type in a new Name for the simulation model or object.
- Type in a new Label .
- To accept the new name and close the dialog box, click OK .
- To accept the changes, and keep the dialog box open, click Apply .
- To close the dialog discarding the changes, click Cancel .

Instead, you can also right-click the object in the Frame and select Rename on the context menu.

<!-- image -->

If you rename an object or a user-defined attribute and the current name is used in the source code of a Method , Plant Simulation asks if you want to replace the current name with the new name in local methods .

<!-- image -->

**See also**

Replace Only in Local Methods

##### Replace Only in Local Methods

If you rename an object or a user-defined attribute and the current name is used in the source code of a Method , Plant Simulation asks if you want to replace the current name with the new name.

<!-- image -->

The query for the current name shows the number of occurrences in Methods in the local Frame and in Frames derived from it as well as in the entire simulation model.

Plant Simulation only searches in Methods whose source code is not inherited and is not encrypted.

Replace only in local methods

Select Replace Only in Local Methods to only replace the name in local occurrences in the source code.

Clear the check box to replace the name in all occurrences in the entire simulation model.

Plant Simulation does not replace the name in a library unless the renamed object is contained in the library. If this is the case, it replaces the current name with the new name.

<!-- image -->

Create the value below one of the following registry keys. The second value disables the setting for all users:

HKEY\_CURRENT\_USER\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504 HKEY\_LOCAL\_MACHINE\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504

See also

Rename [Home ribbon]

#### Edit Icons [Home ribbon]

Opens the Icon Editor for the selected object. Edit, add or delete icons of the object there.

<!-- image -->

Note

The command also applies to 3D Only models.

SimTalk

openImg [SimTalk]

See also

Icon Editor

#### Edit Display Panel [Home ribbon]

Opens the Display Panel of the selected object. Add a new display panel to the selected object or edit or delete an existing display panel there.

<!-- image -->

Note

3D Only models do not provide this command as they do not show display panel .

See also

Display Panel [object]

#### Create in 3D

Opens the dialog 3D . Select the check box to create the counterpart of the selected object in 3D .

<!-- image -->

<!-- image -->

By default, we activated this function for all simulation-relevant objects, such as the Material Flow Objects , the Mobile Units , the Resources , and the Tools .

**Note**

If you clear the check box for an object class and then select it again, Plant Simulation restores the built-in state of the object. It discards all changes that you made to the class of the simulation object.

**Note**

If Create in 3D is deactivated in the origin of an object, then Create in 3D is deactivated in the object itself as well and cannot be activated.

**SimTalk**

**CreateIn3D [SimTalk]**

See also

Object dialog &gt; Tools &gt; 3D [create object]

#### Edit Controls [Home ribbon]

Opens a dialog in which you can select controls, which Plant Simulation activates for the action you want to execute.

Opens the dialog Edit Controls . Select the respective control and type in the source code that specify the actions you want to execute.

<!-- image -->

- Click the button . Navigate to the folder or Frame , in which the Method or the object is located In the dialog Select Object , select it, and click OK .
- Or you can select Create Control on the context menu of the text box to create a user-defined attribute of data type method , called self.OnBuilt\_in\_name\_of\_control , for example self.OnCreate . Then type in your source code.

Plant Simulation calls the Methods described under Edit Controls , when the user performs the actions which you programmed in the Method .

See also

| Constructor Control   | Relabel Control                       |
|-----------------------|---------------------------------------|
| Destructor Control    | Change Path Control                   |
| Select Control        | Move to Folder Control                |
| Move in Frame Control | Fail Control [material flow objects]  |
| Open Control          | Pause Control [material flow objects] |
| Drag-and-Drop Control | Close Control                         |
| Connect Control       | Permit Delete Control                 |
| Plausibility Control  | _Attributes of the Controls           |
| Rename Control        |                                       |

**Compare**

Edit Controls [class library]

Edit Controls [material flow objects]

Edit Controls [MUs]

#### Edit Observers [Home ribbon]

Opens the dialog Edit Observers . Edit the observer there.

<!-- image -->

SimTalk

addObserver [SimTalk]

removeObserver [SimTalk]

attributeWatchable [SimTalk]

See also

Edit Observers [general description]

Create and Delete an Observer

#### Edit User-defined Attributes [Home ribbon]

Opens the dialog User-defined . Create and edit your own attributes here.

<!-- image -->

**Note**

In a Method , which you defined as a user-defined attribute for a Frame , the keyword current refers to the Frame itself. In previous versions it referred to the Frame into which the Frame was inserted for which you defined the user-defined attribute or to the folder in which the Frame was located.

This table shows where the relative path for a user-defined attribute you define for a Frame starts.

| Object                                | User-defined attribute defined for a Frame        |
|---------------------------------------|---------------------------------------------------|
| Object variable                       | Within that Frame .                               |
| Method (current)                      | Within that Frame .                               |
| Table with column of data type object | In the Frame into which you inserted that Frame . |

**SimTalk**

| current [SimTalk] - anonymous identifier   | getAttrType [SimTalk]   |
|--------------------------------------------|-------------------------|
| createAttr [SimTalk]                       | getAttrValue [SimTalk]  |
| deleteAttr [SimTalk]                       | NumAttr [SimTalk]       |
| getAttrName [SimTalk]                      | setAttrType [SimTalk]   |
| getAttrNo [SimTalk]                        | setAttrValue [SimTalk]  |

**See also**

User-defined Attributes [general description]

Create a User-defined Attribute Manually

Create a User-defined Attribute During the Simulation

New [user-defined attribute]

Edit [user-defined attribute]

Delete [user-defined attribute]

#### Show Attributes and Methods

Show Attributes and Methods [described]

Shows the attributes , read-only attributes , and methods of the selected object.

<!-- image -->

Instead, you can also right-click the object in the Frame and select Show Attributes and Methods on the context menu or press the F8 key.

**Note**

The window Show Attributes and Methods only lists those attributes , read-only attributes , and methods which the respective Visualization ( 2D Only , 3D Only , or 2D and 3D ) provides.

<!-- image -->

**Note**

Plant Simulation only shows the column with the German names of the SimTalk functions in an English model if:

The computer runs the German version of Windows .

You selected German as the model language of your simulation model.

Working with the Window Show Attributes and Methods shows how you can use the information to work even more efficiently.

The window lists the following:

- The Name of the attribute , of the read-only attribute , or of the method in the leftmost column. Click the arrow to sort the column Name alphabetically.
- The current Value of the attribute , of the read-only attribute , or of the method .
- If the value is inherited ✔ or not inherited - or neither inherited nor not inherited (no entry).
- If a waituntil-instruction or a stopuntil-instruction can watch the attribute or the read-only attribute (asterisk, * ) or not (no asterisk). Click the arrow to sort the column Watchable .
- The Signature , i.e., the data type or data types of its parameters. Click the arrow to sort the column Signature according to the signature.
- For attributes the data type of the value, which you can assign, and the data type of the return value is shown after the arrow → .
- For methods the data type of the value of the parameter, which you can assign and the data type of the return value is shown after the arrow → .

If a parameter has a default value set by us, the signature shows it after the assignment operator := . The signature shows optional parameters in brackets, for example [PredNo].

<!-- image -->

- For the TwoLaneTrack the window shows A and B for the respective lane but not the SimTalk functions proper for these lanes.

<!-- image -->

- In a German model the rightmost column shows the English name of the attribute , the read-only attribute , or the method .

**Note**

You can copy a user-defined attribute , which you defined for an object, with Ctrl+C and paste this user-defined attribute with all of its settings into the dialog Show Attributes and Methods of another object.

Let us demonstrate how to interpret the information the dialog presents:

- Show Attributes
- Show Read-Only Attributes
- Show Methods
- Simultaneously Show and Change Attributes of Several Objects

**SimTalk**

**attributeWatchable [SimTalk]**

See also

SimTalk Attributes, Read-only Attributes, Methods, and Functions

Working with the Window Show Attributes and Methods

Watchable Values

Array [SimTalk] - data type

**Video on YouTube**

[https://youtu.be/MXDcx2yplxc?si=ga\_5vmDVVDPg7VP4&amp;t=651](https://youtu.be/MXDcx2yplxc?si=ga_5vmDVVDPg7VP4&t=651)

##### Show Attributes

To only show the attributes of the object, we click the yellow button with a:= on the toolbar of the window.

<!-- image -->

In our example the Name of the attribute is Name .

It expects the value to be passed as a string .

Its current value is Station .

This value is inherited and a waituntil-instruction in Plant Simulation can watch it.

<!-- image -->

The respective SimTalk command for setting the name looks like this:

```simtalk
Station.Name := "Station"
```

The respective SimTalk command for getting the name looks like this:

```simtalk
print Station.Name
```

**Note**

In the description of the Plant Simulation Help the names of attributes and read-only attributes begin with an upper-case letter. Each new term after that begins with an upper-case letter. Attributes and read-only attributes are italicized, for example CreationTableActive , ReferenceTime , etc. In the Plant Simulation Help , the italicized term sometimes is a link to an attribute, for example CreationTableActive . Click the link to open that topic in the Plant Simulation Help .

These spelling conventions apply to the Plant Simulation Help .

SimTalk normally does not distinguish between upper- and lower-casing for the names of methods , attributes , and read-only attributes which you type into the source code of your Method objects. You do not have to use the spelling which the window Show Attributes and Methods shows. You can, for example, type in CreationTableActive , creationtableactive , or CREATIONTABLEACTIVE .

- To edit the value , double-click the name of the attribute. The title bar of the dialog that opens shows the entire path to the object.

Type in the new value into the text box or select the new value from the drop-down list.

You can also change Inheritance of the value of the attribute by clicking the inheritance check box. The column Inherited then shows the changed state of inheritance.

<!-- image -->

- To change the value of a boolean attribute from true to false and vice versa, double-click the row in the list. A boolean attribute shows ✔ for inherited or -for not inherited in the column Inherited .

To turn inheritance on again if it has been turned off, double-click into the respective cell in the column Inherited .

- To change the value of an attribute of data type string , first sort the column Signature according to the data type and scroll to the data type string . Then, double-click the respective attribute and select another value in the drop-down list.

<!-- image -->

Examples for such attributes are the values of the drop-down lists in the dialogs of the objects.

<!-- image -->

- Let's now take a look at the attribute ConnectCtrl . It expects to be passed the path to the method to be executed; its current value is VOID , its value is inherited and a waituntil instruction in Plant Simulation cannot watch (no asterisk) it.

<!-- image -->

The type method in the Signature usually is the path to an object of type Method . In most cases it will be the same as the type object. In some cases you will have to type &amp; in front of the name of the Method within SimTalk statements to prevent the Method from being executed.

SimTalk attributeWatchable [SimTalk] See also SimTalk Attributes, Read-only Attributes, Methods, and Functions Working with the Window Show Attributes and Methods Array [SimTalk] - data type Back to Show Attributes and Methods [described]

##### Show Read-Only Attributes

To only show the read-only-attributes of the object, we click the light green button = a on the toolbar of the dialog.

<!-- image -->

In our example the Name of the read-only attribute is NumSucc .

It has the value 2 at the point-in-time of our query.

The return value has the data type integer .

<!-- image -->

The respective SimTalk command for getting the number of successors looks like this:

<!-- image -->

**Note**

In the description of the Plant Simulation Help the names of attributes and read-only attributes begin with an upper-case letter. Each new term after that begins with an upper-case letter. Attributes and read-only attributes are italicized, for example CreationTableActive , ReferenceTime , etc. In the Plant Simulation Help , the italicized term sometimes is a link to an attribute, for example CreationTableActive . Click the link to open that topic in the Plant Simulation Help .

These spelling conventions apply to the Plant Simulation Help .

SimTalk normally does not distinguish between upper- and lower-casing for the names of methods , attributes and read-only attributes , which you type into the source code of your Method objects. You do not have to use the spelling which the window Show Attributes and Methods shows. You can, for example, type in CreationTableActive , creationtableactive , or CREATIONTABLEACTIVE .

SimTalk attributeWatchable [SimTalk] See also SimTalk Attributes, Read-only Attributes, Methods, and Functions Working with the Window Show Attributes and Methods Array [SimTalk] - data type Back to Show Attributes and Methods [described]

##### Show Methods

To only show the methods of the object, we click the button with the M on the toolbar of the dialog.

<!-- image -->

In our example the Name of the method is deleteAttr .

The cell Signature shows the data type of the parameter you have to type in parentheses, string in this case.

If the Method has optional parameters, they are listed within brackets.

The value to the right of the keyword → designated the data type of the return value, boolean in this case.

<!-- image -->

The respective SimTalk command for deleting the user-definded attribute named MyUserdefinedAttribute looks like this:

<!-- image -->

**Note**

In the description of the Plant Simulation Help the names of the methods begin with a lower-case letter. Each new term after that begins with an upper-case letter. Methods are italicized, for example derive , updateDialog , etc. In the Plant Simulation Help , the italicized term sometimes is a link to a method , for example derive .

These spelling conventions apply to the Plant Simulation Help .

SimTalk normally does not distinguish between upper- and lower-casing for the names of methods , attributes , and read-only attributes which you type into the source code of your Method objects. You do not have to use the spelling which the window Show Attributes and Methods shows. You can, for example, type in deleteAttr , deleteattr , or DELETEATTR .

Let's take a look at the method muPart . The cell Signature shows the data type of the optional parameter in brackets. The parameter itself you have to enter within parenthesis, integer in this case. The value after the assignment operator := designates the default value of the parameter, 1 in this case. The value to the right of the keyword → designated the data type of the return value, object in this case.

<!-- image -->

The Auto Complete window in the Method Editor provides the same functions.

SimTalk

attributeWatchable [SimTalk]

See also

SimTalk Attributes, Read-only Attributes, Methods, and Functions

Working with the Window Show Attributes and Methods

Array [SimTalk] - data type

Back to

Show Attributes and Methods [described]

##### Working with the Window Show Attributes and Methods

In the window Show Attributes and Methods you can access the settings of the attributes , read-only attributes , and methods .

- Filter the attributes and methods of the object according to one or several of the criteria described below. Click the respective buttons on the toolbar to show the attributes and methods of that category.

<!-- image -->

The first group of features is exclusive and additive, i.e., you click one button.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| To show                                                                                                                                             | Click   |
|-----------------------------------------------------------------------------------------------------------------------------------------------------|---------|
| Attributes/Methods for Standard Users                                                                                                               |         |
| Attributes/Methods for Expert Users                                                                                                                 |         |
| General Attributes/Methods                                                                                                                          |         |
| User Interface/Animation Attributes/Methods                                                                                                         |         |
| Control Attributes/Methods                                                                                                                          |         |
| Simulation Attributes/Methods                                                                                                                       |         |
| Energy-related Attributes/Methods                                                                                                                   |         |
| 3D-related Attributes/Methods                                                                                                                       |         |
| Statistics Attributes/Methods                                                                                                                       |         |
| Attributes                                                                                                                                          |         |
| Read-Only Attributes . These are attributes and methods , which do not expect parameters, which do not have side effects, and which return a value. |         |
| Methods . Methods as a rule have parameters, have side effects, and return a value.                                                                 |         |

- Attributes/Methods for Standard Users just shows the attributes and methods for the
- standard user.
- Attributes/Methods for Expert Users shows attributes and methods for the standard user
- and for the expert user.

To just show the items of a single category of the three groups of features, when all items/buttons are active, click the button of the respective category. This automatically deactivates all other items of that group. To show all items of the group again, click the active button again.

To just show the items of a single category of the three groups of features, you can also hold down Shift , while you click the button of that category on the toolbar.

To just show or hide a single category of the three groups of features, you can also hold down Alt , while you click the button of that category on the toolbar. This deactivates the default behavior, namely showing or hiding all items of a group simultaneously.

The default setting with all items of all categories activated shows all attributes, read-only attributes, and methods of all categories.

<!-- image -->

<!-- image -->

To just show the attributes , read-only attributes , and methods of the category Energy , we click its button . This automatically deactivates all other categories of the group.

<!-- image -->

<!-- image -->

To show attributes of all categories for the standard user :

- We first click as this command displays items for the standard user .
- To show all items of all categories , make sure that these buttons are all selected.
- Then we click , as we just want to see the attributes of the object. The result looks like this.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- To show the methods of the object in addition, we click . The result looks like this.

<!-- image -->

- To just display the read-only attributes of the object, we click . This activates all three categories as we viewed the attributes and methods before . Clicking then just shows the read-only attributes . The result looks like this.

<!-- image -->

You will have noticed that some of the read-only attributes use our notation for attributes and some of our notation for methods . Both have in common that you can read the value, but that you cannot set it because Plant Simulation computes that value for the point in time at which you query it. These attributes/methods do not expect parameters and do not have any side effects, i.e., they do not change the behavior of the simulation model.

To just show the items of a single category , click the button of that category on the toolbar.

- Arrange the order of the columns according to your requirements. To do so, click the respective column header so that it is marked and drag the column to its new position.
- Sort the contents of a column alphabetically starting with A and ending with Z or vice versa. To do so, click the arrow in the column header. The direction of the arrow shows the sort order, up or down  .

<!-- image -->

Note

We do not sort the columns Value and Inherited .

- Copy the Name of the selected attribute , read-only attribute , or method . To do so, press Ctrl+C or Ctrl+Ins .

Copy the Value of the selected attribute , read-only attribute , or method . To do so, press Ctrl+Shift+C or Ctrl+Shift+Ins .

You can then paste the copied item into the source code of your Method .

- Open help for an attribute or method . To do so, select the attribute or the method for which you need help, and press F1 . Plant Simulation searches for the name of the attribute or of the method in the help. Click its name on the results page of the search.

The Auto Complete window in the Method Editor provides the same functions.

SimTalk

attributeWatchable [SimTalk]

See also

Show Attributes and Methods [described]

Simultaneously Show and Change Attributes of Several Objects

SimTalk Attributes, Read-only Attributes, Methods, and Functions

Array [SimTalk] - data type

Back to

Show Attributes and Methods [described]

##### Simultaneously Show and Change Attributes of Several Objects

Select several objects at the same time and press F8 to open a single dialog, which shows the attributes which the selected objects share. You can change any of the shared attributes for all of the selected objects.

To show the shared attributes of several objects:

- Select the objects whose shared objects you want to show by dragging a marquee over them.
- Press F8 or click the Show Attributes and Methods button on the Home ribbon tab. You will notice that the dialog only shows the attributes of the selected objects.
- Change any of the editable attributes for all of the selected objects. In our example above, we changed the CycleTime to 5 minutes and we activated EnergyActive .

<!-- image -->

<!-- image -->

<!-- image -->

- Press Shift+F8 to open an separate Show Attributes and Methods dialog for each of the selected objects to check your changes.

<!-- image -->

See also

Show Attributes and Methods [described]

Working with the Window Show Attributes and Methods

Back to

Show Attributes and Methods [described]

<!-- image -->

#### Show Statistics Report [Home ribbon]

Shows the statistics of the selected material flow object in the Statistics Report . Instead, you can also press F6 .

<!-- image -->

Instead, you can also right-click the object in the Frame and select Show Statistics Report on the context menu.

<!-- image -->

**SimTalk**

showStatisticsReport [SimTalk]

See also

Statistics Report [described]

Show Statistics Report [in Frame]

Viewing the Statistics Report

#### Show Structure [Home ribbon]

Opens the dialog Structure , which shows the structure of your simulation model and all inserted objects.

<!-- image -->

**Note**

This command only applies to the Frame and the Folder .

The window shows the structure of the selected Frame or Folder , listing the names of all objects contained within in alphabetical order.

<!-- image -->

<!-- image -->

The toolbar enables to filter the displayed information.

<!-- image -->

<!-- image -->

| To do this                                                                                | Click   |
|-------------------------------------------------------------------------------------------|---------|
| Is off by default as showing MUs in models containing numerous them can take a long time. |         |
| Expand all levels of the structure in the structure window.                               |         |
| Collapse all levels of the structure in the structure window.                             |         |
| Refresh the structure in the structure window.                                            |         |

You can do the following with the commands on the context menu:

<!-- image -->

- To open the dialog of the selected object, select Open .

·

To show the selected object in the

Frame that contains your simulation model, select Show

.

- To show the attributes and methods of the selected object, select Show Attributes and Methods .
- To edit the user-defined attributes of the selected object, select Edit User-Defined Attributes .
- To delete the selected object from the model, select Delete .

- To open the window of the selected object class in a new window in 3D and select it, select Open in 3D .
- To show the graphic structure of the selected object in 3D , select Show 3D Graphic Structure .
- To edit the 3D properties of the selected object in 3D , select Edit 3D Properties .

Showing the Number of Graphic Nodes and Polygons in a 3D Model

- To show the number of graphic nodes of the selected object in a 3D model, click Show Graphic Node Count .
- To show the number of polygons of the selected object, click Show Polygon Count .

<!-- image -->

<!-- image -->

The number of graphic nodes and polygons of your imported graphics might blow up the size of your simulation model. They indicate where optimizing and reducing the respective number of graphic nodes and polygons might significantly increase the performance of your model.

The number of nodes and polygons which the 3D window shows for the selected object when you press the F key is slightly lower, as Plant Simulation only counts the visible nodes here.

<!-- image -->

**Searching in the Structure Window**

**In the Structure window you can:**

- Search for an object : Enter a search term, which, in the simplest case, consists of the name of the object and click Find . Plant Simulation searches the list and highlights the object it found. Click Find again to find additional instances of the search term.

If you are searching for several objects and do not remember their exact names, you can use regular expressions in your search, such as ^ , $ , | , . , * , [ , ] , to confine your search by exactly putting together the term you want to find. Plant Simulation does not distinguish between upper and lower case in searches.

- Search for the entire object path : Enter the search term and click Find . Plant Simulation searches the list and highlights the object it found.

**Compare these examples:**

- The search term Station8C searches for a name that contains Station8C . Plant Simulation finds Packstation8CX for example.
- The search term Station.*C searches for a name that contains the regular expression Station.*C . Plant Simulation finds Packstation8CX and Parallelstation42C for example.
- The search term .Models.Model.Zone5.Station8C searches for the object with the absolute path .Models.Model.Zone5.Station8C . Plant Simulation exactly finds .Models.Model.Zone5.Station8C .

**See also**

Regular expressions are described in detail under regex\_search [SimTalk] .

Show the Contents of a Frame in the Class Library

#### Show Inheritance [Home ribbon]

Opens the dialog Inheritance , which shows the paths of the objects that are derived from the selected object.

<!-- image -->

<!-- image -->

- To expand or collapse one level of the structure at a time, click or .
- To expand or collapse all levels of the structure, click Expand All or Collapse All on the toolbar in the Structure window.
- To show how much memory the individual objects consume, click Show Memory Usage on the toolbar in the Structure window.

- To show the number of graphic nodes of the selected object in a 3D model, click Show Graphic Node Count .
- To show the number of polygons of the selected object, click Show Polygon Count .
- To show all attributes which are not inherited, i.e., which you changed in an instance, click Show Changed Attributes on the toolbar in the Structure window.
- To open the dialog of the selected object, double-click it or select Open on the context menu.
- To display the attributes and methods of the selected object, click Show Attributes and Methods
- To edit the user-defined attributes of the selected object, select Edit User-Defined Attributes .
- To delete the selected object from the model, select Delete on the context menu.
- To find an object, enter its name into the text box next to the Find button, and click Find . Plant Simulation searches the list and highlights the object it found. Click Find again to find additional instances of the search term.

<!-- image -->

Hold down Shift and select this to zoom so close as if you selected the object or the graphic and selected the command Zoom to Objects [context menu] .

See also

Inheritance [general description]

Show Inheritance Relations in the Class Library

Show Structure [Home ribbon]

Regular expressions are described in detail under regex\_search [SimTalk]

#### Context Help [Home ribbon]

Opens the help topic pertaining to the object which you selected in Frame . When you did not select any object in the Frame window, pressing F1 opens help for the Frame .

<!-- image -->

#### Optimize Model

Opens the dialog Optimize Model , which provides settings for optimizing your simulation model.

<!-- image -->

**Note**

As you cannot restore discarded data, we advise to optimize the model only after you finished creating it. Optimizing the model improves performance.

We also recommend to save the model under a different name before optimizing it. This way you can return to the state the model had before optimizing it in case the optimized model reports errors or does not meet you expectations.

Select one or several of the following optimization options:

<!-- image -->

**· Clean up Class Library**

This option is always available and looks for classes that are not used in the model file.

The option looks for these classes and does not delete them:

- Each MU class .
- Worker classes if a used Frame with an inserted WorkerPool exists.
- Frame classes if they either contain an EventController and at least another object or if an instance thereof is located in a used Frame .
- Other classes if an instance thereof is inserted in a used Frame .
- Optimize 3D Attribute Inheritance

This option is only available in a 2D/3D model or in a 3D Only model . It attempts to:

- Activate inheritance of 3D attributes whose values uniquely match the corresponding value of its origin. Graphics inheritance is never activated.
- Replace MU animation paths for individual matrix places, with names such as #0#0 , etc., with an animation area if this change is possible without a position change of the animation.

**· Optimize 3D Graphic Structure**

This option is only available in a 2D/3D model or in a 3D Only model . It applies the optimization setting Flatten structure without applying the setting Keep grouping to all editable graphics.

When you select Optimize 3D graphic structure , Plant Simulation optimizes the model with activated setting Preserve References . This is intended to prevent that the model size increases after optimizing the model. In some cases it might prevent an optimal optimization result for the graphic structure.

<!-- image -->

**Note**

If you want to work with your model later on and would like to be able to edit your graphics, we recommend to not activate Optimize 3D graphic structure .

Then click Optimize to optimize the model with the selected settings.

The command Optimize Model also optimizes a library according to the selected options provided the library is not locked.

<!-- image -->

SimTalk

\_3D.optimizeObject [SimTalk]

See also

Optimize the Model

Optimize a Graphic

Optimize Selected Graphic

#### Manage Class Library

Opens the dialog Manage Class Library . Add objects and libraries to the Class Library of your simulation model here.

<!-- image -->

You can add the following items to the Class Library and to the Toolbox or remove them from it:

- Any of the built-in objects .
- Add-in Products , which extend the functionality of Plant Simulation . For some of the add-in products you have to purchase a license from Siemens to use them.
- Tools , libraries , and additional libraries , which you and your colleagues develop, or which you purchase from a third-party vendor.

If the object or the library requires a license, Plant Simulation shows the name and the version number of the required license in the right column.

You can only add objects or libraries to an open simulation model.

<!-- image -->

**Manage Class Library**

To update all libraries, which are not current, to the most current state, click Update All Libraries . Plant Simulation only shows the button when you opened a model. It does not show it when the dialog is opened while creating a new model. When you click the button, Plant Simulation selects the most recent available version number of all loaded libraries. It only actually updates the libraries when you click the OK or the Apply button.

To show this dialog, when you open a new model, select this .

To apply the settings you selected in the dialog to all new models, which you create hereafter, click Apply

<!-- image -->

to New Models .

To always show the dialog Manage Class Library , when you open a new model, select the check box Always Show This Dialog When You Open a New Model . Then you can configure each simulation model to your liking. If you want to use the same settings for all new simulation models, clear the check box.

To show a description of an object below the list of objects, click that object in the list.

To resize the dialog, grab one of its corners or sides and drag the mouse.

**Note**

When you hold down Alt while you click Manage Class Library the dialog shows:

<!-- image -->

The file and the directory in which the libraries are stored. This information is especially helpful when several versions of the same library are located on your computer's hard drive.

The category Libraries &gt; Deprecated . Deprecated libraries are libraries that were part of previous versions of Plant Simulation and which are now obsolete and are not supported anymore. The dialog Manage Class Library shows deprecated libraries that are part of your simulation model.

<!-- image -->

The dialog shows libraries which you or your colleagues develop under Libraries &gt; Additional Libraries .

Plant Simulation opens this dialog, when you select the command File &gt; New Model for the first time.

**Note**

Plant Simulation checks about every half hour if a newer version of any of the loaded libraries exists.

**See also**

| Configure the Class Library   | Edit Library Information    |
|-------------------------------|-----------------------------|
| Update Class Library          | Edit 3D Properties [dialog] |
| Make Library                  | Update a Library            |

**Debugger Ribbon Tab**

