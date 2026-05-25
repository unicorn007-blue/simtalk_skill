#### Dialog Box of the Objects

Dialog Items of the Objects

The Plant Simulation objects share a number of dialog items and menus. Not all objects provide all settings though. To open the dialog box of an object, double-click its icon.

The open dialog shows the current settings and values on the tabs. Click OK or Apply to accept all settings and to update the dialog wit the current settings. You can also press F5 to update the dialog. Plant Simulation overwrites changes, which you made by assigning values to the respective attributes in SimTalk without any feedback!

**Edit Simulation Properties**

You can change the simulation properties with the text boxes, check boxes and the drop-down lists of the dialog.

- To change the simulation properties of the Class of the object, double-click the object in the respective folder in the Class Library or on the respective tab in the Toolbox . Then select the settings in the dialog which Plant Simulation uses for all instances which you insert into your models hereafter.
- To change the simulation properties of the Instance of the object, double-click the object in the Frame into which you inserted the instance. Then select the settings in the dialog which Plant Simulation uses for this instance .

In 3D, you can manipulate the graphic of the object by clicking Show Manipulators on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

You can use the Inheritance check box to the right of the settings to cut or restore the respective setting.

You can also change the simulation properties in the window Show Attributes and Methods ( F8 ).

<!-- image -->

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

<!-- image -->

In the dialog Edit 3D Properties you can change back to the dialog of the simulation properties by clicking .

Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=bkTaMm3-qCms2zJK&amp;t=413](https://youtu.be/FNpiAaUK8iM?si=bkTaMm3-qCms2zJK&t=413)

##### Inheritance [general description]

Inheritance bases one class or object on another class or object and thus incorporates data or behavior of that class or object.

<!-- image -->

The check box to the right of many settings in the object dialogs turns inheritance of the respective setting off or on.

- A green check box means that inheritance is turned on.

Then the object inherits, i.e., uses, the value from the parent object from which it was derived. When you change the value of the parent object, Plant Simulation also changes the value of the child object.

Let us illustrate this with an example. We derive the ParallelStation in the Class Library and insert it from the Class Library into the Frame Model1 . Then, we derive Model2 from Model1 . The origin of the ParallelStation in Model2 is the ParallelStation in Model1 . When we now change the value of an attribute that inherits its value in the ParallelStation in Model1 , the ParallelStation in Model2 also applies this value.

- An orange check box with a minus means that inheritance is turned off.

Values you select or enter only apply to the selected object, meaning that they do not have any connection with the origin of the object.

**Note**

The object might display the current value only after you click the Apply button.

To terminate inheritance relations of the selected object to the object from which it was derived, right-click it and select Cut Inheritance on the context menu. Then, the object inherits its settings from the origin of the origin. In case the origin does not have an origin, the object does not inherit settings at all.

**See also**

| Cut Inheritance                           | Update Arbitrary Old Models                                              |
|-------------------------------------------|--------------------------------------------------------------------------|
| Using Inheritance                         | Change inheritance in the window Show Attributes and Methods [described] |
| Working with Classes in the Class Library | New Check Box in the user-defined Dialog                                 |
| Model Hierarchically [general]            |                                                                          |

**Class [general description]**

A class provides the template for an Instance of this class, which you insert into a Frame . All objects in the Class Library , those we built in as well as those you yourself define, are class objects. You can add more detail to these classes and thus create new classes that inherit properties from the original classes.

By changing a property in the class object, you change that property for all derivatives of this class. This is much less error-prone than having to change the same property for each and every individual object.

- A class passes all of its properties on to an Instance you derive from it.
- A class passes those of its properties on to a Subclass you derive from it, for which you do not deactivate inheritance.

**Note**

Inheritance only works from class to subclass or instance , not the other way around!

**SimTalk**

**Class [SimTalk] - read-only attribute**

**See also**

| Introducing Classes                                 | Go to Class [described] in the dialog of the objects   |
|-----------------------------------------------------|--------------------------------------------------------|
| Classes, Subclasses, and Instances                  | Show Inheritance [Home ribbon]                         |
| Open Class [described] in the dialog of the objects | Duplicate                                              |

**Subclass [general description]**

A subclass is an object in the Class Library , which inherits some, but not all, of its properties from another Class .

By deactivating Inheritance for certain dialog items, you can define properties that only apply to this subclass.

**Note**

Inheritance only works from class to subclass or instance , not the other way around!

**Instance [general description]**

An instance of a class is an object you insert into your simulation model from the Class Library or the Toolbox .

An instance inherits all of its properties from its class .

**Note**

Inheritance only works from class to subclass / instance , not the other way around!

**SimTalk**

childNo [SimTalk]

NumChildren [SimTalk]

getAttribute [SimTalk] - object

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&amp;t=22](https://youtu.be/DwZkGMxXJIA?si=FAz76pLhEAR2X9Tv&t=22)

##### Name [general description]

Shows the Name of the object, either the predefined name or a name that you specify. To change the name, double-click and type over it.

You can type in any combination of letters, digits, and underscore (\_) characters, for example MyStation , MyStation1 , My\_Station\_1 . The name of an object cannot start with a digit, i.e., you can not enter 1Station .

<!-- image -->

If you use an underscore in the Name of an object and show this object in a 3D window with activated Captions , Plant Simulation shows the underscore as a blank space.

<!-- image -->

In addition, you can type in a Label to which these restrictions do not apply.

Plant Simulation shows the name in the Frame when you click Show Object Names on the View ribbon tab of the Frame . You can change the default setting under File &gt; Preferences &gt; Modeling &gt; Show Object Names .

<!-- image -->

See also Name [text box] - 3D Captions in 3D User-defined Names in Methods in SimTalk Rename [model or object] Rename Control

Change the Settings of the Objects in the Step-by-Step Help

##### Label [general description]

Type in an expression of your choice as the label of the object. You can type in letters, numbers, blanks, and special characters.

You can, for example, use the label to display objects with the same functionality with the same identifier in the Frame . The Name of the object, on the other hand, has to be unique!

<!-- image -->

Plant Simulation shows the label in the Frame when you click Names &gt; Labels on the View ribbon tab of the Frame . You can change the default setting under File &gt; Preferences &gt; 2D &gt; Show Object Labels .

Plant Simulation shows the label which you type in for the objects Report , Dialog , AttributeExplorer , and Chart in the title bar of their display windows. If you do not type in a label, the title bar shows the name of the object.

The same applies to a toolbar you add to the Toolbox . Select New &gt; Toolbar , then select the toolbar in the structure, press F2 , and enter a Label into the dialog Rename .

SimTalk

Label [SimTalk]

See also

Name [text box] - 3D

Captions in 3D

User-defined Names in Methods

Relabel Control

Change the Settings of the Objects in the Step-by-Step Help

##### Failed [check box] - material flow objects

To fail the object, select this check box. To remove the failure, clear the check box.

From then on, a failed object will not receive any parts . Parts can exit the object though, when you program this in a Method .

**Note**

The object is failed when you activate this check box or when you activate one of its failure profiles on the Tab Failures .

<!-- image -->

Plant Simulation stops processing and set-up processes until the end of the failure, i.e., it adds the duration of the failure to these times.

If you manually fail a station, it remains failed while any of the failure profiles you defined is Active . It will change to not failed once the last failure ( DisruptionEnd event) of the last failure profile ends or when you clear the check box .

**Note**

When a station fails, and a pause takes place during the failure, the failure time of the station will still be consumed, although the station is paused.

Statistics counts the times during which these two states overlap as pause time.

**Note**

When a Worker/Exporter is brokered to the failed station, it remains brokered to the station while it is failed. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

When you click Reset Simulation , Plant Simulation resets the check box Failed .

When a failure occurs during the simulation run, Plant Simulation resets the check box Failed as well.

<!-- image -->

Click OK or Apply to accept and apply your changes.

2D shows a failed station with a red LED on the upper border of the icon

<!-- image -->

.

<!-- image -->

The length-oriented objects do not display LEDs. Plant Simulation shows the border of a failed lengthoriented object red .

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

Failed [SimTalk] - material flow objects

See also

Model Failures

Failed [state - material flow objects]

Fail Control [material flow objects]

Fail Control [Transporter]

LEDs and States of the Material Flow Objects in 2D

##### Paused/Planned/Unplanned [material flow objects]

To pause the object while it is processing parts, select Paused .

To not schedule it to work, select Unplanned . These are the times that are located outside of the Working hours of the shifts, controlled by the ShiftCalendar , which apply to your plant.

To schedule it to work, select Planned . This is the processing time without counting the breaks during the shifts that apply to your plant.

<!-- image -->

When the object is Paused or Unplanned , it will not receive any MUs . MUs can exit the object, when you type &lt;MUPath &gt;.move into a Method . Plant Simulation stops processing and set-up processes until the end of the pause or of the unplanned time. During the planned time, the object receives and processes MUs .

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused.

Statistics counts the times during which these two states overlap as pause time.

Plant Simulation only increments the counter for pauses and unplanned times when the duration of the pause or shift pause is not 0.

**Note**

When a Worker/Exporter is brokered to the paused station, it remains brokered to the station while it is paused. Statistics of the Worker/Exporter does not count this time as waiting .

**Note**

When you click Reset Simulation , Plant Simulation resets the drop-down list box to Planned .

Plant Simulation resets the pause, when you reset the EventController .

Click OK or Apply to accept your changes.

2D shows a paused station with a light blue LED .

<!-- image -->

<!-- image -->

2D shows an unplanned station with a light blue LED .

The length-oriented objects do not display LEDs. Plant Simulation shows the border of a paused length- oriented object blue .

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

Pause [SimTalk] - material flow objects

Unplanned [state, material flow objects]

See also

Paused [state, material flow objects]

Pause Control [material flow objects]

Pause Control [Transporter]

Unplanned Control

Paused Material Flow Objects

Paused Frames

LEDs and States of the Material Flow Objects in 2D

##### Entrance Locked [material flow objects]

To prevent that MUs enter the material flow object, select this check box. As long as the entrance is locked , Plant Simulation cannot move a MU to the object.

The object will finish processing the MUs already located on it, but does not accept any additional MUs .

<!-- image -->

MUs which cannot enter the object, are entered into the blocking list :

- If the MU wants to enter the object at its entrance, the MU is entered into the Forward Blocking List .
- If the MU is moving backward and want to enter a length-oriented object at its exit, the MU is entered into the Exit Blocking List .

As soon as you unlock the entrance, the MUs in the blocking list move up.

2D shows a station whose entrance is locked with a cyan-colored LED .

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

EntranceLocked [SimTalk] - material flow objects

See also

LEDs and States of the Material Flow Objects in 2D

Inherit 'Entrance/Exit Locked' On Reset

InheritEntranceExitLockedOnReset [SimTalk]

EntranceFree [SimTalk]

##### Exit Locked [material flow objects]

To prevent that MUs exit the object, select this check box. Plant Simulation enters those MUs into the Exit Blocking List of this object.

**Note**

The MU does not trigger the Exit Control , when you selected the check box Exit Locked .

When the exit is unlocked again, the object moves the first MU in the Exit Blocking List to a successor.

<!-- image -->

OK

To accept the changes you made to the settings and to close the dialog box, click OK .

<!-- image -->

If you did not change any settings, we recommend to not click OK , but to click Cancel to close the dialog box.

SimTalk

closeDialog [SimTalk] - all objects

**Cancel**

##### Cancel

To close the dialog box and to discard any changes you made to the settings, click Cancel .

<!-- image -->

SimTalk

closeDialog [SimTalk] - all objects

##### Apply

To apply the changes you made to the settings and to leave the dialog box open, click Apply .

<!-- image -->

**Edit 3D Properties [button]**

##### Edit 3D Properties [button]

To open the dialog Edit 3D Properties of the object, click the 3D button. Then, edit the 3D properties of the object in the dialog.

**Note**

Plant Simulation only shows the button after you started 3D.

Instead, you can also select the command Edit 3D Properties in the Navigate menu of the object.

<!-- image -->

To close the opened 2D dialog after the respective 3D dialog has been opened, hold down Shift while you click . Plant Simulation does not apply changes you made in the 2D dialog. It closes the dialog as if you clicked Cancel .

<!-- image -->

<!-- image -->

You can change back to the simulation properties dialog from the dialog Edit 3D Properties by clicking Open Simulation Settings .

**See also**

**Edit 3D Properties [dialog]**

Edit 3D Properties [on Navigate menu]

Context Menu of Text Boxes in Dialogs

Context Menu of Text Boxes in Dialogs

The most important commands for text boxes of material flow objects are also available on the context menus that a click with the right mouse button opens.

<!-- image -->

**Open Object [context menu]**

###### Open Object [context menu]

To open the dialog of the object, the name of which you type into the text box, select this command or click in the text box and press F2 .

Instead, you can also hold down Shift and double-click into the text box.

###### Create Control [context menu]

To create a control, select this command.

Proceed as follows to create a control as a user-defined attribute of data type method of the selected object:

- Type in a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .

<!-- image -->

Type in the source code of this control into the Method that opens.

Or

- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

<!-- image -->

Type in the source code of this control into the Method that opens.

**Note**

If the Method expects parameters, Plant Simulation automatically formats it correctly.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute itself is retained.

**Create Control [context menu]**

<!-- image -->

**See also**

**Edit Controls [material flow objects]**

###### Cut [from text box]

To cut the contents of the text box to the clipboard, select this command.

###### Copy [contents of text box]

Copy [contents of text box]

To copy the contents of the text box to the clipboard, select this command.

###### Paste [to text box]

To paste the contents of the clipboard into the selected text box, select this command.

**Delete [contents of text box]**

###### Delete [contents of text box]

To delete the contents of the text box, select this command.

###### Select All [in text box]

To select the entire contents of the text box, select this command.

Or double-click into the text box to select the entire contents.

##### Scroll to Tabs

Some objects have more tabs than they can show at the same time next to each other.

<!-- image -->

Click the buttons to scroll to the tab of your choice.

Use Tab Page Icons

Instead of scrolling to the tabs, you can also Use Tab Page Icons in Object Dialogs .

<!-- image -->

##### Tab Attributes [general description]

Type in or select the settings controlling the behavior of the object on the tab Attributes .

The attributes depend on the class of the object, and are described in the subchapters of the respective objects.

<!-- image -->

In 3D, you can manipulate the graphic of the objects by clicking Show Manipulators on the Edit ribbon tab or by pressing ui M on the keyboard.

##### Tab Times

Tab Times [general description]

Select a distribution from the drop-down list and type in the values that the distribution requires on the tab Times .

You can set the Processing Time , the Set-up Time , the Recovery Time , when the Recovery Time Starts , and the Cycle Time .

Plant Simulation shows the parameters along the upper border of the tab. You can also select Const and type in a constant time.

<!-- image -->

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Define Processing Times

Format of Time and Date

Times and Distributions

Probability Distributions

Empirical Distributions

User-defined Distributions

Bounding Probability Distribution Functions

Distribution Functions, z\_ functions in SimTalk

###### Processing time

Processing Time [general description]

The Processing Time is the time during which the MU is located on the material flow object to be processed.

The Processing Time designates the interval between the point in time at which the material flow object was set up for processing this part type and the point in time at which the object moves the processed part on to its successor.

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the simulation model.

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

<!-- image -->

You can also select Const and type in a constant time. Or select to process the MU depending on its type ( List(Type) ). For the ParallelStation you can select to process the MU depending on the station on which it is located ( List(Place) ). For the Buffer and the PlaceBuffer you can only enter a constant Processing Time.

When you select Formula , you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the Processing Time applies.

For the objects Station , ParallelStation , AssemblyStation , DismantleStation , and Drain you can also select if these objects automatically process an entering MU immediately or not.

For a Processing Time of 0 , Plant Simulation does not request a Worker . For this reason the Processing Time will be computed when the MU enters the station or when set-up is done. To request a Worker in spite of a Processing Time of 0 type in a processing time that is slightly greater than 0, for example 0.001 .

If an empty Workpiece Carrier enters the Station , it exits it again immediately without being processed.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

MyStation.ProcTime.setTypeAndAttr("Normal", 30, 10) MyStation.SetupTime.setTypeAndAttr("Erlang", 0:05, 0:01, 0:01, 0:20)

MyStation.RecoveryTime.setTypeAndAttr("cEmp", cEmpTable) MyStation.CycleTime.setTypeAndAttr("Formula","Variable2/20")

**SimTalk**

ProcTime [SimTalk] - material flow objects

LowerBound [SimTalk] - distribution parameter

Type [SimTalk] - distribution parameter

UpperBound [SimTalk] - distribution parameter

AutomaticProcessing [SimTalk]

**See also**

| Define Processing Times                            | Probability Distributions                          |
|----------------------------------------------------|----------------------------------------------------|
| Change the Processing Time in the Entrance Control | Empirical Distributions                            |
| Parameters of the Distributions                    | User-defined Distributions                         |
| Methods of the Distributions                       | Bounding Probability Distribution Functions        |
| Format of Time and Date                            | Distribution Functions, z_ functions               |
| Times and Distributions                            | LEDs and States of the Material Flow Objects in 2D |

**Automatic Processing**

To automatically start processing parts immediately after they enter the object, select this check box.

<!-- image -->

To deactivate automatic processing, clear the check box. In this case you have to start the processing of entering parts with the method startProcessing . Only then the station requests Workers .

If you deactivate Automatic Processing the part is not ready to exit without being processed, compare Finished .

**Note**

This only applies for the objects Station , ParallelStation , AssemblyStation , DismantleStation , and Drain .

For the ParallelStation you can only deactivate automatic processing if you selected the check box Start processing when full .

**SimTalk**

AutomaticProcessing [SimTalk]

**See also startProcessing [SimTalk] - material flow objects**

**Finished [SimTalk]**

###### Set-up Time [general description]

The Set-up Time is the time it takes to set the object up for processing a different type of MU . An identical name means that parts are of the same type.

How to actually set the object up is described under the Tab Set-Up .

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

<!-- image -->

You can also select Const and type in a constant time. Or you can use the Matrix(Type) distribution as the Set-up Time .

If you select the Formula distribution, you can type in a numeric expression or the name of a Method .

You can use the anonymous identifier @ to access the MU for which the set-up time applies.

If a Set-up Time of 0 results, for example from a distribution or from a formula , Plant Simulation sets the station up without using up any time at all and does not request any Workers . Plant Simulation counts this as a setup process for statistical purposes and the part type , for which the station is being set up, is set to this new part type immediately. If you typed in a constant set-up time , the object never sets up.

If an empty workpiece carrier enters the Station , it exits it again immediately without the Station being set up for it.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

MyStation.ProcTime.setTypeAndAttr("Normal", 30, 10) MyStation.SetupTime.setTypeAndAttr("Erlang", 0:05, 0:01, 0:01, 0:20) MyStation.RecoveryTime.setTypeAndAttr("cEmp", cEmpTable) MyStation.CycleTime.setTypeAndAttr("Formula","Variable2/20")

<!-- image -->

2D shows a station that is setting-up with a brown LED on the upper border of the icon

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

SetupTime [SimTalk] - material flow objects

LowerBound [SimTalk] - distribution parameter

Type [SimTalk] - distribution parameter

UpperBound [SimTalk] - distribution parameter

RemainingSetUpTime [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

See also

| Select the Set-Up Time          | Empirical Distributions                            |
|---------------------------------|----------------------------------------------------|
| Parameters of the Distributions | User-defined Distributions                         |
| Methods of the Distributions    | Bounding Probability Distribution Functions        |
| Format of Time and Date         | Distribution Functions, z_ functions               |
| Times and Distributions         | LEDs and States of the Material Flow Objects in 2D |
| Show Objects With               |                                                    |

.

###### Recovery Time [general description]

The Recovery Time is the time which is required to set a station into a defined state before it can start processing the next part.

The Recovery Time is the time, which is required to put a station into a defined state before it can start processing the next part. The Recovery Time is, for example, useful to model materials handling equipment, such as a robot, which requires a certain time to insert work pieces into or remove them from processing places.

You can use the attribute EntranceOpen to check if the entrance is currently open. The entrance is not open, if the Entrance is Locked or the material flow object is waiting for its Recovery Time to be completed.

You can use the attribute TimeUntilEntranceOpen to query the time at which the entrance will be open again.

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

<!-- image -->

You can also select Const and type in a constant time.

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the MU for which the Recovery Time applies.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

MyStation.ProcTime.setTypeAndAttr("Normal", 30, 10) MyStation.SetupTime.setTypeAndAttr("Erlang", 0:05, 0:01, 0:01, 0:20) MyStation.RecoveryTime.setTypeAndAttr("cEmp", cEmpTable) MyStation.CycleTime.setTypeAndAttr("Formula","Variable2/20")

For some stations you can also select, when the Recovery time starts .

2D shows a station that is recovering with a cyan LED on the upper border of the icon .

3D shows the state of the object as a colored ring on a pole by default.

SimTalk

RecoveryTime [SimTalk] - material flow objects

RecoveryTime.LowerBound

RecoveryTime.Type

RecoveryTime.UpperBound

EntranceLocked [SimTalk] - material flow objects

EntranceOpen [SimTalk] - material flow objects

EntranceFree [SimTalk]

putAttributeNamesIntoTable [SimTalk] - distributions

See also

Entrance Locked [material flow objects]

Recovery Time/Cycle Time [PlaceBuffer]

RecoveryTime [SimTalk] - DePortioner

RecoveryTime [SimTalk] - Mixer Recovery Time [Workplace]

**Recovery time [TransferStation]**

**Additional Related Topics**

| Parameters of the Distributions   | Empirical Distributions                            |
|-----------------------------------|----------------------------------------------------|
| Methods of the Distributions      | User-defined Distributions                         |
| Format of Time and Date           | Bounding Probability Distribution Functions        |
| Times and Distributions           | Distribution Functions, z_ functions               |
| Probability Distributions         | LEDs and States of the Material Flow Objects in 2D |

###### Recovery Time Starts

The Recovery Time is the time which is required to return a station into a defined state before it can start processing the next part. All other material flow objects just show this setting, you cannot select it.

For the Station , the AssemblyStation , the DismantleStation , the PickAndPlace robot, and the ParallelStation in Start processing when full mode you can select when the Recovery Time starts.

<!-- image -->

Select when the Recovery Time of the station starts:

- When the part enters the station. When part enters is the default setting.
- When processing of the part is finished : The recovery time elapses after the part is processed, no matter if the part is still located on the station or has left it.
- When the part exits the station: The recovery time elapses after the part is processed and has left the station.

**SimTalk**

RecoveryTimeMode [SimTalk]

###### Cycle Time [general description]

The Cycle Time is the time that passes between the points in time where parts can enter the object.

The Cycle Time is, for example, useful to model chain conveyors with a fixed chain interval that only transport materials when a free hook is available.

Plant Simulation only opens the entrance of the object for a moment. When a MU is Waiting to enter at that time, it may enter, if not, another cycle has to pass before it can enter.

You can use the attribute EntranceOpen to check if the entrance is currently open.

You can use the attribute TimeUntilEntranceOpen to query the time at which the entrance will be open again.

Select a distribution, and type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab.

If you define the Cycle Time with a distribution, Plant Simulation rolls the dice each time after the Cycle Time elapsed.

The Cycle Time starts anew at the start of a shift.

<!-- image -->

You can also select Const and enter a constant time.

If you select the Formula distribution, you can type in a numeric expression or the name of a Method .

If you type in 0 the entrance is always open. A value greater than 0, 10 seconds for example, means that the entrance opens every 10 seconds (compare Recovery Time ). The value 34 , for example, means that MUs can enter at the simulation times 0, 34, 68, 102, …

**Note**

If you define the Cycle Time with a distribution, Plant Simulation rolls the dice each time after the Cycle time elapsed.

Note

The Cycle Time starts anew at the start of a shift.

**Note**

Recovery Time and Cycle Time can overlap. Then, MUs may only enter the work stations if both entrances are open.

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

MyStation.ProcTime.setTypeAndAttr("Normal", 30, 10) MyStation.SetupTime.setTypeAndAttr("Erlang", 0:05, 0:01, 0:01, 0:20) MyStation.RecoveryTime.setTypeAndAttr("cEmp", cEmpTable) MyStation.CycleTime.setTypeAndAttr("Formula","Variable2/20")

SimTalk

CycleTime [SimTalk]

CycleTime.LowerBound

CycleTime.Type

CycleTime.UpperBound

putAttributeNamesIntoTable [SimTalk] - distributions

restartCycle [SimTalk]

**See also**

| Parameters of the Distributions   | Empirical Distributions                            |
|-----------------------------------|----------------------------------------------------|
| Methods of the Distributions      | User-defined Distributions                         |
| Format of Time and Date           | Bounding Probability Distribution Functions        |
| Times and Distributions           | Distribution Functions, z_ functions               |
| Probability Distributions         | LEDs and States of the Material Flow Objects in 2D |

##### Tab Set-Up

Tab Set-Up [general description]

Define how Plant Simulation sets objects up for processing a part type on the tab Set-Up .

Set-Up applies to the objects Station , ParallelStation , AssemblyStation , DismantleStation , Drain , and DePortioner .

<!-- image -->

You can specify the Set-up Time on the tab Times .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also Methods for Setting-Up \_Attributes for Setting-Up Setting-Up [state, material flow objects] Set a Station Up

###### Set-up For

Set-up For

The text box Set-up For shows for which type of MU the object is set up or is going to be set up for.

If the object has not been set up yet, Plant Simulation shows a hyphen -.

To tell one type of MU from the other, Plant Simulation uses the name of the MU or a user-defined attribute of the MU , compare Set-up Depends On .

SimTalk

IsSetupFor [SimTalk]

ResSetup [SimTalk] - material flow objects

setupFor [SimTalk]

See also

Set-up Depends On

###### Automatic Set-up

To automatically set the object up, select this check box.

<!-- image -->

When you activate Automatic Set-up , Plant Simulation triggers the set-up process of objects as soon as the respective differing MU class intends to move onto the object.

When you clear Automatic Set-up , you have to define the set-up process yourself, for example with the method setUpFor .

**Note**

If the object cannot be set up at the current point in time, for example because it is failed, Plant Simulation does not attempt to set the object up anew.

**SimTalk**

setupFor [SimTalk]

AutomaticSetup [SimTalk]

**Set-up Only When Empty**

###### Set-up Only When Empty

To only start setting-up the material flow object for the next class of MU when it is empty , select this check box.

<!-- image -->

- When you select Set-up Only When Empty setting-up only starts when the object is empty. MUs of the type for which the object is setting-up can only enter the object, after the set-up process is finished.
- When you clear Set-up Only When Empty , the MUs for whose part type the object still has to set up can enter the object. The set-up time for these MUs only starts when all set-up processes which you specified are finished. MUs that are already located on the object will be processed with the settings for the MU class for which the object was set up before.

**SimTalk**

SetUpOnlyWhenEmpty [SimTalk]

See also

Empty [state, material flow objects]

###### Set-up After n Parts

To set the material flow object up after a certain number of parts has been processed, select this check box. Then, type the number of parts after which you want the object to set up into the text box.

<!-- image -->

- Select Before Next Part to set the object up after the n-plus-first part wants to move onto the station.
- Select After Last Part to set the object up immediately after the n-th part was processed.

The object also sets up and starts counting anew, starting from 1, when the part type changes before the number you enter is reached. For this reason it may happen that the object does not reach the number of parts of a certain type for which it is to set up.

When the value 0 was determined when setting the Set-up Time , for example resulting from a distribution or from a formula , Plant Simulation treats this as if a setup process has taken place. This means that the counter also is reset for a setup process of time 0.

If you do not want this, select the setting Set-up Depends On &gt; Off . Then the station only sets up after the selected number of parts.

**Note**

The number of parts is the number of parts entering the station. These parts do not necessarily have to be processed. Statistics also counts parts, which are removed from the station before they have been processed, for example during the set-up process or while the station is waiting for a service to be performed.

**SimTalk**

SetupAfterNumParts [SimTalk]

SetupAfterNPartsMode [SimTalk]

NumPartsSinceSetup [SimTalk]

**See also Set-up Time [general description] Set-up Depends On**

###### Set-up Depends On

Select if the object has to be set up according to the name of the MU or to a user-defined attribute.

<!-- image -->

- The MU Name , meaning that the object sets up, when the name of the part changes.

**Note**

To change setting-up via information flow to MU Name , assign an empty string ( "" ).

- A User-defined Attribute , meaning that the object sets up, when the value of this user-defined attribute of the part changes. This user-defined attribute has to be of data type string , integer , boolean , or object .

Plant Simulation converts values of data type integer and boolean to strings .

For values of data type object Plant Simulation always sets up for the object name.

For .Models.Model.Conveyor5.Packstation2 Plant Simulation sets up for the object Packstation2.

Type in the name of a user-defined attribute of the part into the text box.. The material flow object sets up, when a part , whose user-defined attribute has a different value, moves onto the station.

The MUs might, for example, have a user-defined attribute named Color . Let us assume that the station is set up for red . Now, a part with the user-defined attribute value blue moves on to the station. For this reason it sets up for blue .

<!-- image -->

- Off : Deactivates setting the object up after changing the type to another MU . This means that the station will only be set up after the number of parts that you selected.

SimTalk

SetupAttrName [SimTalk]

SetupForType [SimTalk]

See also

Set-up After n Parts

Tab Failures

Tab Failures [general description]

Type in or select the settings for failures of the object on the tab Failures .

In a real-world plant machines do fail for unforeseeable reasons. Any current processing operations on the machines are interrupted for the duration of the failure. Any upcoming production order can only be processed after the failure is removed, i.e., the machine is repaired.

For planning production processes the description of the availability of machines or common production resources, such as Station , ParallelStation , Transporter , and Worker , is critical. The on-schedule completion of customer orders does, for example, strongly depend on unexpected interruptions of the manufacturing process by failures of machines and by unavailable personnel.

The time interval between the end of the last failure and the beginning of the next failure is called the MTBF ( M ean T ime B etween F ailures). The duration of a failure is called the MTTR ( M ean T ime T o R epair) although the duration of a failure does, generally speaking, not only contain the repair time. In practice both times, MTBF and MTBF , are random numbers.

In a real-world plant production resources may fail for a number of reasons, which differ in their frequency and in the required repair time.

Failures might be

- the breakage of a tool
- the loss of a part of a machine through corrosion
- a power outage of the entire factory
- structural damages to the buildings caused by a thunderstorm.

The different failure reasons lead to different time intervals between failures ( MTBF ), while the duration of the failure naturally depends on its cause.

For simulating different failure causes you can define several failure profiles for a production resource. For some failure reasons the MTBF is extended because the machine is not used during pauses or during repair times. A tool does not wear out for example, when the machine is not Working . The machine still corrodes though, even if it is not working.

Failures caused by power outages or by thunderstorms naturally relate to the simulation time. These failures also occur, when the machine is not working, they take place independent of each other. A failure reason based on the simulation time do not allow us to draw a conclusion about the occurrence of additional failure reasons based on the simulation time.

If a machine has two failure reasons based on the operating time or the processing time, the time between two failures of the first reason is extended by the repair time for a failure of the second reason. Beginning and end of the failures caused by different reasons are no longer independent of each other. Thus, the repair times of failure reasons based on the operating time or the processing time can not overlap.

When we compare a machine with two Simulation Time or the Operating Time -based failure reasons, which will not be paused, we'll detect that each failure reason has an availability of 50 percent.

- In the first case the resulting availability is 25 percent as both failure reasons occur independent of each other.
- In the second case the resulting availability is 33.3 percent:

The mean times to repair ( MTTR ) and failure intervals ( MTBF ) of both failure reasons are four identical time values. While the times of the failure durations never can overlap, the time of the failure intervals, namely of the Operating Time , of both failure profiles passes simultaneously. For this reason the resource is ready for use during a third of the time.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

<!-- image -->

<!-- image -->

To create a new failure profile , click New

.

<!-- image -->

To edit the failure profile , which you selected in the List of Failure Profiles , click Edit . Instead, you can also double-click the name of the failure profile in the list.

To delete the failure profile , which you selected in the list of failure profiles, click Delete .

**Note**

You can fail a failure profile by assigning true to the attribute Failed [SimTalk] - failure profile .

The object is failed when you activate one of its failure profiles or when you activate the check box Failed [check box] - material flow objects .

**See also**

| Model Failures                   | _Attributes of the Failure Profiles                 |
|----------------------------------|-----------------------------------------------------|
| _Methods for Defining Failures   | _Attributes for Failures in the Simplified Notation |
| Methods of the Failure Profiles  | Active [check box] - failures                       |
| Attributes for Defining Failures | Distribution Functions, z_ functions in SimTalk     |

Additional Methods Relating to Failures

Some of the \_Methods for the State also relate to failures:

| endFailure [SimTalk] - material flow objects         | GetDisruptionEndTime [SimTalk]                   |
|------------------------------------------------------|--------------------------------------------------|
| endFailureIn [SimTalk] - material flow objects       | startFailure [SimTalk] - material flow objects   |
| eraseFailureEvents [SimTalk] - material flow objects | startFailureIn [SimTalk] - material flow objects |
| GetDisruptionBeginTime [SimTalk]                     |                                                  |

###### Active [check box] - failures

To activate failures of the object in general, select this check box. To deactivate them, clear the check box.

<!-- image -->

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again.

This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

<!-- image -->

**Example**

```simtalk
MyStation.Failures.MyFailureProfile1.Active := false
MyStation.Failures.MyFailureProfile1.Availability := 85
MyStation.Failures.MyFailureProfile1.Active := true
```

**SimTalk**

FailureActive [SimTalk] - material flow objects New Failure New [failure]

To create a new failure profile and to open a dialog, click New .

<!-- image -->

Type in the Name of the failure profile and select if it is Failed and if it is Active or not. You can define the Start time and the Stop time, the Interval and the Duration of this failure profile . You can also select the time which the Failure relates to .

The Lognormal distribution , the Erlang distribution and the Negative exponential distribution are especially suited for modeling failures.

<!-- image -->

If you select the check box Availability , Plant Simulation dims the dialog item Interval , and you can type in the Availability and the MTTR instead. You can also select if the failure relates to the Simulation Time , the Operating Time or the Processing Time .

**SimTalk**

Failures. getTable [SimTalk] - failure profile Failures. setTable [SimTalk] - failure profile Failures. createFailure [SimTalk] Failures. deleteFailure [SimTalk] Failures. getFailure [SimTalk]

<!-- image -->

**Name [failure]**

Type in the name of this failure profile , for example the reason why the machine fails.

SimTalk

Failures.&lt;NameOfFailureProfile&gt;. Name [SimTalk] - failure profile

**Failed [check box] - failure profile**

**Failed [check box] - failure profile**

To fail this failure profile select this check box. To not fail this failure profile , clear the check box.

<!-- image -->

The setting/attribute is watchable and Plant Simulation can call a control. The row of a failed failure profile is shown in red in the List of Failure Profiles .

<!-- image -->

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Failed [SimTalk] - failure profile

Failures.&lt;NameOfFailureProfile&gt;. reset [SimTalk] - failure profile

**See also**

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

**Active [check box] - failure profile**

To activate this failure profile , select this check box. To deactivate it, clear the check box.

<!-- image -->

The failure of the object is only active when you activate this, i.e., the failure profile itself, and the check box Active on the tab Failures !

<!-- image -->

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Active [SimTalk] - failure profile

**See also**

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

**Start [failure]**

**Start [failure]**

Select a distribution for the time at which the fi rst failure of this failure profile will take place.

Type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a Formula in which you can access the anonymous identifier @ .

**Note**

When you type in 0 , Plant Simulation uses the failure Interval to set the point in time of the first failure.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

<!-- image -->

**Example**

```simtalk
MyStation.Failures.MyFailureProfile1.Active := false
MyStation.Failures.MyFailureProfile1.Availability := 85
MyStation.Failures.MyFailureProfile1.Active := true
```

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Start [SimTalk] - failure profile

**See also**

**\_Attributes of the Failure Profiles**

**\_Attributes for Failures in the Simplified Notation**

**Additional Related Topics**

| Times and Distributions              | Empirical Distributions                     |
|--------------------------------------|---------------------------------------------|
| Probability Distributions            | User-defined Distributions                  |
| Format of Time and Date              | Bounding Probability Distribution Functions |
| Distribution Functions, z_ functions |                                             |

**Stop [failure]**

**Stop [failure]**

Select a distribution for the time at which the last failure of this failure profile will take place.

Type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a Formula in which you can access the anonymous identifier @ .

When the object is still failed when Plant Simulation reaches the Stop time, the failure will last for the Duration you selected.

**Note**

When you type in 0 , Plant Simulation creates new failures infinitely.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

<!-- image -->

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Stop [SimTalk] - failure profile

**See also**

**\_Attributes of the Failure Profiles**

**\_Attributes for Failures in the Simplified Notation**

**Additional Related Topics**

| Format of Time and Date              | Empirical Distributions                     |
|--------------------------------------|---------------------------------------------|
| Times and Distributions              | User-defined Distributions                  |
| Probability Distributions            | Bounding Probability Distribution Functions |
| Distribution Functions, z_ functions |                                             |

**Interval [failure]**

**Interval [failure]**

Select a distribution for the time between the end of the last failure and the start of the next one of this failure profile .

<!-- image -->

**Remarks**

Type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a Formula in which you can access the anonymous identifier @ . The object is returned to the non-failed state after this time has passed.

**Note**

Typing in 0 for the Interval and a value greater than 0 for the Duration creates a single failure.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

If you select the check box Availability , Plant Simulation dims the dialog item Interval , and you can enter the Availability and the MTTR instead.

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Interval [SimTalk] - failure profile

**See also**

**\_Attributes of the Failure Profiles**

**\_Attributes for Failures in the Simplified Notation**

**Additional Related Topics**

| Format of Time and Date              | Empirical Distributions                     |
|--------------------------------------|---------------------------------------------|
| Times and Distributions              | User-defined Distributions                  |
| Probability Distributions            | Bounding Probability Distribution Functions |
| Distribution Functions, z_ functions |                                             |

**Duration [failure]**

**Duration [failure]**

Select a distribution for the duration of the failure of this failure profile .

<!-- image -->

**Remarks**

Type the values, which that distribution requires, into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a Formula in which you can access the anonymous identifier @ .

After the time you specified for the failure has elapsed, Plant Simulation returns the object to the not failed state. When you type in 0, no failures at all will take place.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

**Note**

If you select the check box Availability , Plant Simulation dims the dialog item Interval , and you can enter the Availability and the MTTR instead.

If you select any of the provided distributions, you have to type in the parameters that this distribution requires. Plant Simulation will enter the resulting value for the MTTR into the text box MTTR , you cannot edit it.

<!-- image -->

**Note**

When a station fails, and a pause occurs during the failure, the failure time of the station will still be consumed, although the station is paused.

Statistics counts the times during which these two states overlap as pause time.

**Example**

```simtalk
MyStation.Failures.MyFailureProfile1.Active := false
MyStation.Failures.MyFailureProfile1.Duration := 85
MyStation.Failures.MyFailureProfile1.Active := true
```

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. Duration [SimTalk] - failure profile

**See also**

**\_Attributes of the Failure Profiles**

\_Attributes for Failures in the Simplified Notation

Additional Related Topics

| Format of Time and Date   | Empirical Distributions    |
|---------------------------|----------------------------|
| Times and Distributions   | User-defined Distributions |

| Probability Distributions            | Bounding Probability Distribution Functions   |
|--------------------------------------|-----------------------------------------------|
| Distribution Functions, z_ functions |                                               |

**Availability [failure, check box]**

To activate the text boxes Availability % and MTTR , select this check box.

Then, type in the availability and the mean time to repair of the station instead of the Duration and the Interval of the failure.

<!-- image -->

Using Availability % in percent and MTTR is just another kind of displaying the values for the Duration and the Interval of a failure. If you enter values for Availability and MTTR and click Apply , Plant Simulation computes the values for the Duration and the Interval and enters them into the text boxes. It also selects the Erlang -distribution for the Duration and the NegExp -distribution for the Interval , Plant Simulation shows them in the dialog, when you clear the check box Availability .

An availability of 100 percent has an MTTR of 0, as the machine is available and does not have to be repaired. Plant Simulation uses the values in that view of the dialog where you clicked Apply . The object only inherits the values for the Availability (%) and the MTTR , when it also inherits the Availability as such from the parent dialog, i.e., if the inheritance check box next to the check box looks like this !

**Note**

When you set an availability of 100 percent, meaning that the station will never fail, and subsequently change the availability to a more realistic value, say 50 percent, Plant Simulation will not apply this new setting unless you clear the check box Active , click Apply , and then select Active again.

**Note**

When you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

For the standard Erlang distribution you can enter the value into the text box MTTR .

<!-- image -->

If you select any of the provided distributions, you have to enter the parameters that this distribution requires. Plant Simulation will enter the resulting value for the MTTR into the text box MTTR , you cannot edit it.

<!-- image -->

**SimTalk**

Failures.&lt;NameOfFailureProfile&gt;. AvailabilityOn [SimTalk]

Failures.&lt;NameOfFailureProfile&gt;. Availability [SimTalk] - failure profile

Failures.&lt;NameOfFailureProfile&gt;. MTTR [SimTalk] - failure profile

See also

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation Availability [failure, text box]

Availability [failure, text box]

Type in the availability of the machine. This is a value between 0 and 100 percent.

<!-- image -->

The availability designates the proportion of time during which a machine is in an operable state. Availability is based on a combination of MTBF and MTTR .

MTBF is the M ean T ime B etween F ailures, a measure of reliability. It is the time in hours that represents the average amount of time that passes between random failures of a machine.

The object only inherits the values for the Availability (%) and the MTTR , if it also inherits the Availability as such from the parent dialog, i.e., if the inheritance check box next to the check box looks like this !

You cannot always set the availability and the MTTR independently of each other. If the availability is 100 percent, the MTTR has to be 0, as no failures can take place. On the other hand an MTTR of more than 0 automatically results in an availability of less than 100 percent.

If you set these two values via information flow with these attributes, the following assignments

```simtalk
MyStation.Failures.MyFailureProfile1.MTTR := 60
MyStation.Failures.MyFailureProfile1.Availability := 100
```

result in an MTTR of 0, i.e., the Station will not fail during the simulation.

The following sequence of assignments

```simtalk
MyStation.Failures.MyFailureProfile1.Availability := 100
MyStation.Failures.MyFailureProfile1.MTTR := 60
```

automatically result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

**Note**

If you set an availability of 100 percent, meaning that the station will never fail, and subsequently change the availability to a more realistic value, say 50 percent, Plant Simulation will not apply this new setting unless you clear the check box Active , click Apply , and then select Active again.

**Note**

If you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

SimTalk

Failures.&lt;NameOfFailureProfile&gt;. Availability [SimTalk] - failure profile

Failures.&lt;NameOfFailureProfile&gt;. AvailabilityOn [SimTalk]

Failures.&lt;NameOfFailureProfile&gt;. MTTR [material flow objects]

See also

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

Change Failure Settings During the Simulation Run

**MTTR [material flow objects]**

**MTTR [material flow objects]**

Type in the M ean T ime T o R epair (MTTR) of the machine.

Optionally you can type in the lower bound and upper bound for the Erlang -distribution. Plant Simulation then computes the Erlang -distribution and the negative exponential distribution from these values. When you type in the lower bound and the upper bound for the Erlang -distribution, Plant Simulation computes the MTTR.

<!-- image -->

The mean time to repair is a measure of maintainability. It is the average time required to repair this machine.

For simulating repair times during the duration of a failure Plant Simulation uses the Erlang -distribution. This Erlang -distribution is the sum of two independent exponentially distributed random numbers with

the same parameter β. The used Erlang -distribution also has the property .

<!-- image -->

The picture of the probability density function of this random number shows that very short and very long repair times occur very rarely. Repair times that are located around the value µ/2 are most common.

Figure 11-1: Density function of the distribution for repair times with a mean value of μ= 10

<!-- image -->

The object only inherits the values for the Availability and the MTTR if it also inherits the Availability as such from the parent dialog, i.e., if the inheritance check box next to the check box MTTR looks like this !

If you set these two values via information flow with these attributes, the following assignments

```simtalk
MyStation.Failures.MyFailureProfile1.MTTR := 60
MyStation.Failures.MyFailureProfile1.Availability := 100
```

result in an MTTR of 0, i.e., the Station will not fail during the simulation.

The following sequence of assignments

```simtalk
MyStation.Failures.MyFailureProfile1.Availability := 100
MyStation.Failures.MyFailureProfile1.MTTR := 60
```

result in an availability of the Station of 95 percent. This is a typical value for the availability of a machine. For these settings the Station will fail during the simulation.

**Note**

If you set the MTTR to 0, meaning that the station will never fail, and subsequently change the MTTR to a more realistic value, say 60 seconds, Plant Simulation will not apply this new setting unless you clear the check box Active , click Apply , and then select Active again.

**Note**

If you change failure settings, we recommend to first clear the check box Active and to then click Apply . Then, change your settings, apply them, and select the check box Active again. This ensures that the next failure event ( DisruptionBegin / DisruptionEnd ) will be computed with a complete valid set of parameters.

SimTalk

Failures.&lt;NameOfFailureProfile&gt;. MTTR [SimTalk] - failure profile

Failures.&lt;NameOfFailureProfile&gt;. Availability [SimTalk] - failure profile

See also

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

Change Failure Settings During the Simulation Run

**Failure Relates To**

Select the time to which the failures of this failure profile relate.

- The simulation time consumes the time you entered for the failure Interval , regardless of the state the object is in.

The SimulationTime is the time between the beginning of the simulation run ( Reset Simulation , Start/ Stop Simulation ) and its end.

- The operating time consumes the time you entered for the failure interval only when the object is operational.

The OperatingTime will be interrupted by pauses and failures .

- The processing time consumes the time you entered for the failure interval while the object is processing the part.

For point-oriented objects the ProcessingTime is the time during which a part is located on a material flow object and is being processed by it.

If you set the attribute EnforceProcessing to true , the processing time also elapses without a MU being located on the objects Station , ParallelStation , AssemblyStation , and DismantleStation .

For conveying objects, such as the Conveyor , the ProcessingTime is the time during which its speed is not 0. It can also be working , when the conveyor is moving and does not transport a part.

For additional information about the ProcessingTime , consult the topic Working .

For processing time based failures of a ParallelStation the simulated MTBF is reduced, when the number of parallel processing operations of parts on the ParallelStation increases. This means that the more parts are processed simultaneously, the sooner the failure occurs, and the smaller the availability becomes. This then prevents the availability you entered into the dialog from being reached. This does not apply if you activated the setting Start Processing When Full .

<!-- image -->

**Note**

If a station fails, and a pause takes place during the failure, the failure time of the station will still be consumed, although the station is paused. The DisruptionEnd event will not be changed.

If a station, which fails based on the processing time or the operating time and which is interrupted by a pause or failure, the processing time or the operating time of the station for simulating the MTBF will not be consumed. The points in time for the DisruptionBegin event will be moved forward into the future.

Statistics counts the times during which these two states overlap as pause time.

Compare the sample models for processing time related failures of the ParallelStation : Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection and click Open Model .

SimTalk

Failures.&lt;NameOfFailureProfile&gt;. Mode [SimTalk] - failure profile

See also

Working [state, material flow objects]

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

###### Edit [failure]

To edit the failure, which you selected in the list of failure profiles, click Edit .

<!-- image -->

Instead, you can also double-click the name of the failure in the list.

**See also**

List of Failure Profiles

<!-- image -->

###### List of Failure Profiles

The list shows all failure profiles , which you defined for the object, on the tab itself. Each row in the list contains the parameters of a specific failure profile .

The row of a failed failure profile is shown in red.

<!-- image -->

You can activate or deactivate a failure profile by checking or clearing the check box Active and by then clicking Apply or OK .

To edit any of its parameters, double-click the respective row and change them in the dialog that opens.

<!-- image -->

##### Tab Controls

You find the setting Failure Relates To on the tab itself in the cells of the column header Mode .

SimTalk

Failures. getTable [SimTalk] - failure profile

Failures. setTable [SimTalk] - failure profile

Failures. count [SimTalk]

Failures. createFailure [SimTalk]

Failures. deleteFailure [SimTalk]

Failures. getFailure [SimTalk]

Failures.&lt;NameOfFailureProfile&gt;. reset [SimTalk] - failure profile

See also

\_Attributes of the Failure Profiles

\_Attributes for Failures in the Simplified Notation

Methods of the Failure Profiles

Tab Controls

Tab Controls [general description]

Define controls which a MU triggers when it enters the station on the tab Controls .

When the MU triggers an internal sensor , the object triggers the Method object you entered as the control. You can then replace the built-in properties of the object with behavior that you need.

For the length-oriented objects you can, in addition, create user-defined Sensors anywhere on the object. They activate the Methods , which you assigned to the sensor, when a MU passes the sensor. You can define and delete sensors in the dialog of the Track , the TwoLaneTrack , the Conveyor , and the Transporter or with SimTalk commands.

You can use control methods in a number of ways. You might, for example, count the number of incoming MUs and then, after a specified number has been reached, move the following MUs to a different successor.

**Note**

You can only use Methods as controls. Either type in the name\_of\_the\_Method , to call a Method in the Frame into which you inserted the object or type in self. NameOfTheMethod , to call a user-defined attribute of data type method .

**On the tab Controls you can:**

- Select or type in the Entrance Control .
- Select or type in the Exit Control .
- Select or type in the Backward Entrance Control for the length-oriented objects Conveyor , Track , and TwoLaneTrack , and for the loading space of the Transporter .
- Select or type in the Backward Exit Control for the length-oriented objects Conveyor , Track , and TwoLaneTrack , and for the loading space of the Transporter .
- Select or type in the name of the Set-up Control .
- Select or type in the name of the Pull Control .
- Select or type in the name of the Shift Calendar , which controls the shifts during which the object works. Define the shifts in the object ShiftCalendar .
- Create and insert Sensors for the length-oriented objects Conveyor , Track , Turntable , and TwoLaneTrack , and for the loading space of the Transporter .

<!-- image -->

The ellipsis button in the text box of the control provides three commands.

You can:

- Click Select Object and select a Method object in the dialog. Type in the source code of the respective control.

<!-- image -->

- Click Create Control to create the control as a user-defined attribute of data type method of the object itself.
- Click Open Object after you created the controls as a user-defined attribute of the object to open this control.

<!-- image -->

<!-- image -->

To open the dialog of the object, whose name you entered into the text box, click in the text box, and press F2 .

Once you enter a control, either here or under Tools &gt; Edit Controls , the context menu of the object in the Frame shows the command Controls . You can then select the name of the control on the submenu to edit it.

<!-- image -->

**See also**

Select Object [for controls]

**Entrance Control**

###### Entrance Control

Entrance Control [general description]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the entrance control .

<!-- image -->

You can modify the built-in behavior of the material flow objects with an Entrance Control in which you can program the actions that you want to execute. The object calls the Method you typed in as soon as a MU intends to enter the object.

You can use control methods in a number of ways. You might, for example, count the number of incoming MUs and then, after a specified number has been reached, move the following MUs to a different successor.

- For the point-oriented objects , such as the Station , Plant Simulation executes the Entrance Control once the MU has entered it in its entirety. You can also select if the Entrance Control is called Before the Default Actions take place or not.
- For the length-oriented objects , such as the Conveyor , Plant Simulation executes the entrance control once the MU has entered it in its entirety. You can also select if the Entrance Control is triggered by the Front and the Rear of the MU or not.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

An Entrance Control might look like this:

```simtalk
switch
	@.Name
case "PartA"
	?.ProcTime := str_to_time("10:0") // process PartA for 10 minutes case "PartB"
	?.ProcTime := str_to_time("2:0")  // process PartB for 2 minutes
end
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type in the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

EntranceCtrl [SimTalk] - material flow objects

EntranceCtrlFront [SimTalk] - material flow objects

EntranceCtrlRear [SimTalk] - material flow objects

EntranceCtrlBeforeActions [SimTalk]

See also

Select Object [for controls]

Sensors [general description]

Create Entrance and Exit Controls

Change the Processing Time in the Entrance Control

Change the Importer Services in the Entrance Control

Change the Assembly Table in the Entrance Control

**Video on YouTube**

[https://youtu.be/pbOQD0p4hO4?si=t19x98J3TybZJxlw&amp;t=56](https://youtu.be/pbOQD0p4hO4?si=t19x98J3TybZJxlw&t=56)

**Before Actions**

For the point-oriented objects , such as the Station , the setting Before Actions sets if the Entrance Control is called before the Standard Actions are called when the part enters the object or not.

<!-- image -->

Standard Actions are, for example, starting the Processing Time or the Set-up Time , requesting services through the importer , or changing the Assembly Table of the AssemblyStation .

Select Before Actions if, for example, you would like to change the Processing Time in the Entrance Control , which then affects processing of entering parts.

Before Actions is deactivated by default.

<!-- image -->

**SimTalk**

**EntranceCtrlBeforeActions [SimTalk]**

Video on YouTube

[https://youtu.be/pbOQD0p4hO4?si=YsEEXTNAQ7deQhDU&amp;t=509](https://youtu.be/pbOQD0p4hO4?si=YsEEXTNAQ7deQhDU&t=509)

**Front and Rear [entrance control]**

For the length-oriented objects ( Conveyor , Track , TwoLaneTrack ) you can set if the Front and/or the Rear of the MU trigger the Entrance Control .

<!-- image -->

**Note**

A part , for which you entered a length, does not enter these objects all at once, but continually. Depending on the length and the speed of the part , there will be a delay between the time the front and the time the rear of the part enters the object.

- Select Front to activate the control as soon as the front of the part enters, i.e., is located on the object. This means that changing the processing time in the entrance control does not affect the part that already entered the object. To set the processing time depending on the part that arrives, enter a formula for the processing time and set the processing time in the formula.

**Note**

The Front of the part always moves toward the end of the length-oriented object in the direction with which you inserted it along the direction of motion of the material flow. When you insert a length-oriented object, for example a Conveyor , from left to right, the Front of the part is located on the right-hand side and moves toward the right. When you insert a length-oriented object from right to left, the Front of the part is located on the left-hand side and moves toward the left.

<!-- image -->

This also applies to parts which move backward when you select the check box Backward of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the lengthoriented object in the direction with which you inserted it along the direction of motion of the material flow.

- Select Rear to activate the control as soon as the rear of the part enters the object.
- You can also select both Front and Rear to call the entrance control as soon as the front and the rear of the part enters the object.

**SimTalk**

EntranceCtrlFront [SimTalk] - material flow objects

EntranceCtrlRear [SimTalk] - material flow objects

**Video on YouTube**

**[https://youtu.be/pbOQD0p4hO4?si=rE7o75NjHcO4gkB8&amp;t=856](https://youtu.be/pbOQD0p4hO4?si=rE7o75NjHcO4gkB8&t=856)**

###### Exit Control

**Exit Control [general description]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Exit Control , which is called as soon as a MU intends to exit the respective object. .

<!-- image -->

<!-- image -->

- For the point-oriented objects and the length-oriented objects Plant Simulation calls the Exit Control when the MU intends to exit the object. You can also select if the Exit Control is called once or repeatedly.
- For the length-oriented objects you can, in addition, select if the Front and the Rear of the MU trigger the Exit Control .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Example**

**An Exit Control might look like this:**

```simtalk
var n: integer
n := Station.StatNumIn
if n = 100
	@.move(Station1)
elseif n = 300
	@.move(Station2)
else
	@.move(Station3)
end
```

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type method of this object, for example.

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnExit .

Type in the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

The standard exit control as a user-defined attribute looks like this:

**Note**

The Exit Control can have an optional parameter of data type object . When the Method has this parameter, then the successor object, which pulls the part because the part was contained in the blocking list of the object, will be assigned to this parameter. The part will be pulled, for example, when the successor becomes available again or when its entrance is opened.

**Note**

A Front -triggered Exit Control is only called for the last station of the cycle defined by the object Cycle as the Destination for all other stations of the cycle is already set. Use a Rear -triggered Exit Control instead.

**Note**

The event CheckMUPosition (compare the List of Events ) is scheduled when the Exit Control is called and checks, after processing the Exit Control , if the MU has to be stopped. This is the case when neither the position of the front of the part in the direction of motion nor its Direction changed. This prevents that the MU is stopped before calling the Exit Control .

**Note**

If the MU is a Transporter that has a Destination Control , the Destination Control will not be called.

**Note**

When you programmed an Exit Control and an Importer Release Control , the Importer Release Control is called first, and then the Exit Control is called.

**SimTalk**

ExitCtrl [SimTalk] - material flow objects

ExitCtrlFront [SimTalk] - material flow objects

ExitCtrlRear [SimTalk] - material flow objects

ExitCtrlOnce [SimTalk]

<!-- image -->

move [SimTalk] - MUs FwDestList [SimTalk] See also Select Object [for controls] Create Entrance and Exit Controls Distribute Parts with an Exit Control Program the Exit Control Sensors [general description] Video on YouTube https://youtu.be/MY59lMy3UPM?si=rfvchoh5fKgqJsCo

**Exit Control Once**

To call the Exit Control only once when the part intends to exit the object, select the check box.

<!-- image -->

If the target station cannot receive the part, the part is entered into the Exit Blocking Lists of the target station. As soon as the target station becomes available again, the part is unblocked. To call the Exit Control again now, clear the check box.

**Note**

When the station is failed or paused , all transfer processes are canceled, and the parts are removed from the Entrance Blocking Lists of the succeeding stations. When the station becomes operational again, the fully processed parts get a new Out event and the Exit Control is called again independent of this setting.

**Note**

Exit Control Once does not mean that the Exit Control always is called once only. If the part is neither blocked nor stopped by the Exit Control it may happen that a new Out event is scheduled, for example when the Speed of Conveyor or Transporter has changed. In this case the Exit Control is called again independent of this setting.

**Note**

If you activate Exit Control Once for the ParallelStation and the parts are to be carried away, the Exit Control for the waiting parts will not be called a second time if the Worker carries a part away.

**SimTalk**

**ExitCtrlOnce [SimTalk]**

Video on YouTube

[https://youtu.be/MY59lMy3UPM?si=S7xxmv3uvrDkFAVs&amp;t=706](https://youtu.be/MY59lMy3UPM?si=S7xxmv3uvrDkFAVs&t=706)

**Front and Rear [exit control]**

For the length-oriented objects ( Conveyor , Track , TwoLaneTrack ) you can set if the Front and/or the Rear of the MU trigger the Exit Control .

<!-- image -->

- Select Front to activate the control as soon as the part is ready to exit the object. The exit control then has to move the part to another object, as the built-in behavior of the material flow object, i.e., moving the part onto the successors along the Connectors , has been overridden by the Exit Control . You can use the methods move or transfer for that.

**Note**

The same part can call the Front-triggered Exit Control more than once if that part could not exit the object and entered itself into the Blocking List (Forward, Backward or Exit) of the destination object. As soon as the destination object is ready to receive the part , the part is assigned a new Out event which triggers the Front-triggered Exit Control again. This only applies if you cleared the check box Exit Control Once .

**Note**

The Front of the part always moves toward the end of the length-oriented object in the direction with which you inserted it along the direction of motion of the material flow.

If you insert a length-oriented object, for example a Conveyor , from left to right, the Front of the part is located on the right-hand side and moves toward the right.

If you insert a length-oriented object from right to left, the Front of the part is located on the left-hand side and moves toward the left.

<!-- image -->

This also applies to parts which move backward if you select the check box Backwards of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the lengthoriented object in the direction with which you inserted it along the direction of motion of the material flow.

**Note**

A Front -triggered Exit Control is only called for the last station of the cycle defined by the object Cycle as the Destination for all other stations of the cycle is already set. Use a Rear-triggered Exit Control instead.

- Select Rear to activate the control as soon as the rear of the part has completely exited the object. This control does not override the built-in behavior of how MUs move to the successor of the current object.

**Note**

Please make sure that the source code of the Rear-triggered Exit Control does not contain an @.move instruction as the MU is already located on the succeeding object at this point in time.

**Note**

Compare the Out , OutEnd , and Reference events in the List of scheduled events.

- You can also select both Front and Rear . The part then triggers the control as soon as the front or the rear of the part exits the object.

SimTalk

ExitCtrlFront [SimTalk] - material flow objects

ExitCtrlRear [SimTalk] - material flow objects

Video on YouTube

[https://youtu.be/MY59lMy3UPM?si=R2mwAjuOdgTAKtjp&amp;t=327](https://youtu.be/MY59lMy3UPM?si=R2mwAjuOdgTAKtjp&t=327)

Backward Entrance Control

###### Backward Entrance Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Backward Entrance Control , which is called when the MU enters the length-oriented object at its entrance while it is being transported backward.

<!-- image -->

In addition to the Forward Entrance control , the Conveyor , the Track , and the TwoLaneTrack provide the Backward Entrance Control . In it, you can change the default behavior by programming the actions that you want to execute.

**Note**

The Transporter backs up on the Track/TwoLaneTrack , it does not turn around. This means that it drives in reverse with its front end still pointing in the direction of the material flow!

You can select if the Backward Entrance Control is triggered by the Front and the Rear of the MU or not.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type method of this object.

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnBwEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

SimTalk

BwEntranceCtrl [SimTalk] - material flow objects

See also

Select Object [for controls]

**Front and Rear [backward entrance control]**

For the length-oriented objects ( Conveyor , Track , TwoLaneTrack ) you can set if the Front and/or the Rear of the MU trigger the Backward Entrance Control .

<!-- image -->

**Note**

A part , for which you entered a length, does not enter these objects all at once, but continually. Depending on the length and the speed of the part , there will be a delay between the time the front and the time the rear of the part enters the object.

- Select Front to activate the control as soon as the front of the MU enters the object at its entrance while it is being transported backward.

<!-- image -->

This also applies to parts which move backward when you select the check box Backwards of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the length-

- oriented object into the direction with which you inserted it along the direction of motion of the material flow.
- Select Rear to activate the control as soon as the rear of the MU enters the object at its entrance while it is being transported backward.
- Select Front and Rear to activate the control as soon as the front and the rear of the MU has moved on the object at its entrance while it is being transported backward.

**SimTalk**

BwEntranceCtrlRear [SimTalk] - material flow objects

BwEntranceCtrlFront [SimTalk] - material flow objects

**Backward Exit Control**

###### Backward Exit Control

Click the ellipsis button and select a Method in the dialog Select Object . Type the source code of the Backward Exit Control , which is called when the MU exits the length-oriented objects Track/ TwoLaneTrack/Conveyor via their exit and/or when it moves backward toward their exit.

<!-- image -->

In addition, to the Forward exit control , the Conveyor , the Track , and the TwoLaneTrack provide a Backward Exit Control . In it, you can program the actions that you want to execute.

**Note**

The Transporter backs up on the Track/TwoLaneTrack , it does not turn around. This means that it drives in reverse with its front end still pointing in the direction of the material flow!

You can select if the backward exit control is triggered by the Front and the Rear of the MU or not.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnBwExit .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

The standard backward exit control looks like this:

<!-- image -->

**SimTalk**

BwExitCtrl [SimTalk] - material flow objects

BwExitCtrlRear [SimTalk] - material flow objects

BwExitCtrlFront [SimTalk] - material flow objects move [SimTalk] - MUs See also Select Object [for controls]

**Front and Rear [backward exit control]**

For the length-oriented objects ( Conveyor , Track/TwoLaneTrack ) you can set if the Front and/or the Rear of the MU trigger the Backward Exit Control .

<!-- image -->

- Select Front to activate the control as soon as the front of the MU exits the object at its entrance. The Exit Control then has to move the part to another object, as the built-in behavior of the material flow object, i.e., moving the part on to the successors along the Connectors , has been overridden by the Exit Control .

**Note**

The same part can call the Front-triggered exit control more than once, if that part could not exit the object and entered itself into the Blocking List (Forward, Backward or Exit) of the destination object. As soon as the destination object is ready to receive the part , the part is assigned a new Out event which triggers the Front-triggered exit control again. This only applies if you cleared the check box Exit Control Once .

**Note**

The Front of the part always moves toward the end of the length-oriented object into the direction with which you inserted it along the direction of motion of the material flow.

If you insert a length-oriented object, for example a Conveyor , from left to right, the Front of the part is located on the right-hand side and moves toward the right.

If you insert a length-oriented object from right to left, the Front of the part is located on the left-hand side and moves toward the left.

**Front and Rear [backward exit control]**

<!-- image -->

This also applies to parts which move backward if you select the check box Backward of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the length-oriented object into the direction with which you inserted it along the direction of motion of the material flow.

- Select Rear to activate the control as soon as the back of the MU exits the object at its entrance and/or when it moves toward the entrance of the object once it moved onto the object.
- Select Front and Rear to activate the backward exit control as soon as the front and the rear of the MU has moved on the object at its exit while it is being transported backward.

**SimTalk**

BwExitCtrlRear [SimTalk] - material flow objects

BwExitCtrlFront [SimTalk] - material flow objects

###### Set-up Control

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the set-up control , which is called whenever a set-up process starts or ends or is interrupted.

<!-- image -->

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

You can query if a set-up process starts or ends with the read-only attribute ResSetUp . If the instruction ?.ResSetUp returns the value true, setting-up just started.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard set-up control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The optional parameter SetupStart of data type boolean shows the user if setting-up starts or ends.

**SimTalk**

SetupCtrl [SimTalk] - material flow objects

ResSetup [SimTalk] - material flow objects

See also

Select Object [for controls]

**Pull Control [general description]**

###### Pull Control [general description]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Pull Control , which is called whenever the object is ready to accept a new part or when it is ready, when a new part is waiting at its entrance.

<!-- image -->

You can change the default behavior of an object with a Pull Control in which you program the actions that you want to execute.

In the Pull Control you can set which of the MUs , which intend to move onto the object, the object will actually accept. For this you have to get the forward blocking list of the object with the method fwBlockList and unblock a part in that list with the method unblock .

Let us assume that red parts are especially important and thus have a high priority for being processed. Then you can always pull red parts first from the predecessors in the Pull Control and only then pull parts in other colors.

**Note**

The Pull Control does not set if a MU is to be moved to this or to another successor. Instead, it selects one of the parts which have already determined to move on to this successor.

**Note**

The AssemblyStation does not provide the Pull Control .

**Note**

A Pull Control will not be called for the stations of the object Cycle .

**Note**

For the objects Conveyor , Track , and TwoLaneTrack the Pull Control only applies to MUs moving in the forward direction, i.e., to objects, which move onto them at their entrance and exit them at their exit . It does not apply to MUs moving onto them backward at their exit and not to MUs that have been moved to a certain position.

**Note**

For the Converter the Pull Control also applies for parts that move onto it backward at its exit .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard pull control as a user-defined attribute looks like this:

<!-- image -->

**Note**

If you only need the first entry of the Forward Blocking List , you can use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

PullCtrl [SimTalk] - material flow objects

unblock [SimTalk]

fwBlockList [SimTalk] - material flow objects

See also

Waiting [state, material flow objects]

Pull Control [PickAndPlace]

Select Object [for controls]

###### Shift Calendar [tab Controls]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the object works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Instead of clicking the ellipsis button, you can also select the ShiftCalendar in a Frame , drag it to the text box, and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

ShiftCalendarObject [SimTalk] - material flow objects

See also

ShiftCalendar [object]

Associated Shift Calendar

###### Sensors

**Sensors [general description]**

Define sensors for the length-oriented objects Conveyor , Turntable , Track , TwoLaneTrack , and for the Transporter . The sensor can be located at any point on the length-oriented object. Plant Simulation calls the control methods assigned to the sensors as soon as a MU passes the sensor.

<!-- image -->

**Note**

The Transporter shows the button Sensors on the tab Load Bay , when you select the Type Line or Track . Here you have to click Apply to activate the button.

To create a new sensor, click the position at which you would like to insert the sensor with the right mouse button and select Create Sensor on the context menu. Enter the data defining to the sensor into the dialog that opens.

<!-- image -->

<!-- image -->

Or, you can right-click the sensor in the Frame and select Open Sensor on the context menu.

<!-- image -->

<!-- image -->

To open the Sensor List , click Sensors . Instead, you can also double-click the name of a sensor in the open sensor list. A Sensor is defined by its Sensor-ID , its Position , its length unit, and the Method object triggering it. You can set the position in relation to the length of the object or as an absolute length.

The list shows all sensors which you already defined. You can edit or delete existing sensors and add new sensors. The list shows the ID , the position on the length-oriented object, if it is triggered by the front , the rear , the booking point or a light barrier of the MU , the path of the control that is executed, and if the sensor was created in the active instance of the object.

<!-- image -->

In our example 1 is the Sensor-ID and 0.5m stands for the Position of the sensor on the object. The x in the column Front shows that the front of the MU triggers the Method shown in the column Path , which the sensor activates. The Rear or the Booking point do not trigger the sensor. The asterisk * in the column Created here shows that the sensor was created in the selected instance of the object. If the sensor inherits its values from a parent object, the cell is empty.

Plant Simulation places a question mark ? after the invalid position in the cell. That sensor will be inactive during a simulation run.

To create a new sensor, click New

<!-- image -->

.

To edit the sensor, which you selected in the list, click Edit

<!-- image -->

To delete the sensor, which you selected in the list, click Delete

.

<!-- image -->

.

To open the sensor that Plant Simulation inserts as a red line into the icon of the object, Alt +double-click the red line and change the settings in the dialog that opens.

**Note**

In 3D the sensor sometimes might be hard to see depending on the zoom factor of the Frame . Zoom the Frame to show the red line more clearly.

To show a tooltip with vital information about the sensor, drag the mouse over the red line designating the sensor on the object.

<!-- image -->

When you click the Close button, Plant Simulation updates and shows the Number of Sensors on the button Sensors .

You will make extensive use of sensors when we Model Transport Systems . We used them in our sample applications for loading and unloading a cross sliding car and a tugger train .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

createSensor [SimTalk] - material flow objects

deleteSensor [SimTalk] - material flow objects

See also

| _Methods of Sensors                                 | existsSensorID [SimTalk] - material flow objects   |
|-----------------------------------------------------|----------------------------------------------------|
| _Attributes of Sensors                              | NumSensors [SimTalk] - material flow objects       |
| _Read-Only Attributes of Sensors                    | sensors.id [SimTalk] - material flow objects       |
| Create a Sensor [material flow objects]             | sensorNo [SimTalk] - material flow objects         |
| Configure the Track on Which the Transporters Drive | _3D.ShowSensors [SimTalk]                          |
| Configure the Track on Which the Transporters Drive | Undo [3D]                                          |
| Sensors [Transporter]                               | Redo [3D]                                          |

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=\_9TPz12ec8f-ReqA&amp;t=529](https://youtu.be/K-NEPvShU10?si=_9TPz12ec8f-ReqA&t=529)

New Sensor

New [sensor]

To create a new sensor and open the dialog Sensor , click New .

<!-- image -->

The settings for activating the sensor and for the destination are only available, when you define a sensor for the objects Track and TwoLaneTrack .

<!-- image -->

You can select the settings listed in the table of contents to the left.

Once you specify a sensor control, the context menu of the object in the Frame shows the command Controls . You can then select the name of the sensor control on the submenu to edit it.

**SimTalk**

BookPos [SimTalk] of the MUs

Booking Point Length [general description]

Booking Point Width [general description]

MU Height [general description]

**Sensor-ID**

Shows the number that Plant Simulation automatically assigns to the sensor, when it creates it. You can use the ID, which is a unique identifier, to access that sensor from within Methods .

<!-- image -->

<!-- image -->

**sensorID [SimTalk] - material flow objects createSensor [SimTalk] - material flow objects**

**Position [sensor]**

Select the type of the position of the sensor from the drop-down list. Then, type in the position of the sensor.

<!-- image -->

- Relative : Type in a value between 0 and 1 , i.e., between 0 percent and 100 percent. Plant Simulation then shows 0..1 to the right of the text box.

The value sets how far along the length of the object, starting from the beginning of the Conveyor , the Track , the Turntable or on Lane A of the TwoLaneTrack , the sensor is located.

- Length : Type in a value between 0 and the length of the object.

Plant Simulation uses the length unit you selected under File &gt; Model Settings/Preferences &gt; Units &gt; Length . When you specify an invalid value, Plant Simulation changes the color of the text box to red.

The value sets how far along the length of the object, starting from the beginning of the Conveyor , the Track , the Turntable or on Lane A of the TwoLaneTrack , the sensor is located.

Type in how far along the length of Lane B of the TwoLaneTrack the sensor is located. If you select Lanes &gt; Both Lanes , Plant Simulation computes the position of the sensor on Lane B according to the position, which you entered for Lane A .

- Relative from end : Type in a value between 0 and 1 , i.e., between 0 percent and 100 percent. Plant Simulation then shows 0..1 to the right of the text box.

The value sets how far along the length of the object, starting from the end of the Conveyor , the Track , the Turntable or on Lane A of the TwoLaneTrack , the sensor is located.

- Length from end : Type in a value between 0 and the length of the object.

The value sets how far along the length of the object, starting from the end of the Conveyor , the Track , the Turntable or on Lane A of the TwoLaneTrack , the sensor is located.

**SimTalk**

PositionType [SimTalk]

**Position [SimTalk] - sensors**

**createSensor [SimTalk] - material flow objects**

**Front [sensor]**

To make the Front of the part activate the sensor on the Conveyor , the Track or on lane A of the TwoLaneTrack , select this check box.

<!-- image -->

You can also select Front and Rear . Then both the front and the rear of the part activate the Method .

To make the Front of the part activate the sensor/ Method on Lane B , select this. You can also select Front and Rear . Then both the front and the rear of the part activate the Method .

<!-- image -->

This also applies to parts which move backward when you select the check box Backward of the Conveyor or the Transporter ! The Front of the part keeps on pointing toward the end of the length-oriented object into the direction with which you inserted it along the direction of motion of the material flow.

**SimTalk**

**Front [SimTalk]**

createSensor [SimTalk] - material flow objects

**Rear [sensor]**

<!-- image -->

Rear [sensor]

To make the Rear of the part activate the sensor on Lane A , select this check box.

You can also select Front and Rear . Then both the front and the rear of the part activate the Method .

To make the Rear of the part activate the sensor/ Method on Lane B , select this. You can also select Front and Rear . Then both the front and the rear of the part activate the Method .

SimTalk

Rear [SimTalk]

createSensor [SimTalk] - material flow objects

Booking Point [sensor]

To make the Booking Point of the part activate the sensor, select this check box.

When you only activate Booking Point , Light Barrier Mode is automatically deactivated.

SimTalk

BookPosition [SimTalk]

createSensor [SimTalk] - material flow objects

Light Barrier Mode

To activate Light Barrier Mode , select this check box. The sensor will then be triggered as a light barrier .

The light barrier sensor is also triggered when you drop a part on the sensor or when you remove it from it.

If Light Barrier Mode is activated the following applies: When you activate Front , the front end of the part in the direction of motion triggers the sensor. When you activate Rear , the rear end of the part in the direction of motion triggers the sensor.

<!-- image -->

If Light Barrier Mode is not activated the following applies: When you activate Front , the front end of the part triggers the sensor. When you activate Rear , the rear end of the part triggers the sensor. Here the direction of motion of the part is irrelevant.

When you activate Booking Point , Light Barrier Mode is automatically deactivated.

SimTalk

Lightbarriermode [SimTalk]

createSensor [SimTalk] - material flow objects

**Lanes [sensor]**

Select on which lane of the TwoLaneTrack you want to insert the sensor.

<!-- image -->

On Both Lanes , or on Lane A only, or on Lane B only.

SimTalk

Lanes [SimTalk]

createSensor [SimTalk] - material flow objects

**Activate [sensor]**

Select under which conditions a MU triggers the sensor:

<!-- image -->

- Always , independent of the destination of the MU .
- Or Only when the MU has the same Destination as the one, which you typed into the sensor.

Automatic Routing [Transporter] / Automatic Routing [Part, Container] also includes this destination object. When you assign a Destination to the MU while automatic routing is active, it drives to the sensor. Once there it activates the sensor Control . For the Transporter it also activates the Destination Control . The same destination object can be defined in several sensors. It may also be directly reached via different routes . Even if a direct route leads to the destination object, the MU drives to the nearest sensor, when this sensor can be reached on a shorter route than the destination object itself.

**SimTalk**

Activate [SimTalk] - sensors

createSensor [SimTalk] - material flow objects

**Destination [sensor]**

Type in the name of the destination object to which the Transporter drives.

<!-- image -->

Automatic Routing [Transporter] / Automatic Routing [Part, Container] also includes this destination object. When you assign a Destination to the MU while automatic routing is active, it drives to the sensor. Once there it activates the sensor Control . For the Transporter it also activates the Destination Control .

The same destination object can be defined in several sensors. It may also be directly reached via different routes . Even if a direct route leads to the destination object, the MU drives to the nearest sensor, when this sensor can be reached on a shorter route than the destination object itself.

**SimTalk**

Destination [SimTalk] - sensors

DestinationWasReached [SimTalk]

createSensor [SimTalk] - material flow objects

**Control [sensor]**

Click the ellipsis button and select a Method in the dialog Select Object .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**Parameters**

- As soon as the sensor calls this Method , it passes the Sensor-ID as an optional parameter. When the Method expects a parameter of data type integer , the sensor passes the Sensor-ID to the Method ; if you do not specify an integer parameter, the Method will be called without a parameter.
- The optional parameter Front of data type boolean shows the user if the Front (true) or the Rear (false) of the part triggered the control.
- The optional parameter BookPos of data type boolean shows the user if the Booking Point of the part triggered the control (true) or not (false).

**Control [sensor]**

- If the parameters Front and BookPos are both false, the rear of the part triggered the control.

**Note**

When deleting parts, Plant Simulation calls the Sensor Control of a sensor which is triggered by a Light Barrier .

The Sensor Control is not called when parts are deleted when resetting the model with reset .

SimTalk

Control [SimTalk] - sensors

createSensor [SimTalk] - material flow objects

See also

Select Object [for controls]

**Edit [sensor]**

To edit the settings of the sensor and to open the dialog Sensor , click this button or double-click the name of the sensor in the sensor list.

<!-- image -->

**Delete [sensor]**

Delete [sensor]

To delete the sensor, which you selected in the list of sensors, click this button.

<!-- image -->

SimTalk

deleteSensor [SimTalk] - material flow objects

Tab Exit

Tab Exit [general description]

Select the exit strategy according to which the object moves the MU on to one of its successors on the tab Exit .

As a rule you will use an exit strategy, which distributes the flow of materials, when the sequence of operations does not uniquely designate the next object that processes the part . Your objective will be to make a choice that is close to optimal in some respect, say cost or time.

**Note**

To show the items belonging to the new strategy, click Apply after you selected another strategy.

**Note**

Plant Simulation only takes the Exit Strategy for length-oriented objects into account, when the part moves in the forward direction.

See also

Strategy [material flow objects]

Use the Standard Transfer Behavior

Select an Exit Strategy

\_Attributes for Setting the Exit Strategy

Data Held in Tabular Form in Attributes [material flow objects]

###### Blocking [exit strategy]

Select if the exit strategy you selected is Blocking or not blocking .

- Select Blocking to always move the part to the designated successor. If that successor is not ready to receive it, the part will be blocked.
- If moving the part fails, Plant Simulation enters the part into the Forward Blocking List of the designated successor.
- Leave the check box as it is to move the part on when any of its successors can receive it. If none of the successors can receive the part , Plant Simulation enters it into the Forward Blocking List of all successors.

**Note**

The non-blocking Exit Strategy &gt; MU Attribute moves the part on when any of the desired successors can receive it.

In both cases Plant Simulation schedules an Out event when a successor is ready to receive the part in whose Forward Blocking List the part is entered.

**Note**

If you use a non-blocking exit strategy when the Worker is to carry parts away from an object, and if that object only has a single successor that cannot accept the part , the Worker starts walking toward that successor (his destination).

SimTalk

ExitStrategyBlocking [SimTalk]

Strategy

Strategy [material flow objects]

Select the Strategy according to which the material flow object determines the successor in the material flow that processes the MU .

**Note**

Plant Simulation only takes the exit strategy for length-oriented objects into account, when the MU moves in the forward direction.

**Note**

Click Apply to apply your settings and to show additional dialog elements which certain types of exit behavior provide.

**Note**

If you activated the Transport Importer on the tab Importer and if you neither enter a MU Target here nor a Destination in the MU , the object uses the Strategy which you selected on the tab Exit . This means that the MU is not moved on directly along the Connectors when the transport importer is active, but that the Worker carries the MU to the destination.

If the carrying capacity of the Worker is exhausted, the destination is determined according to the selected exit strategy. For a capacity of greater than 1 only for the first MU a destination is determined. Once he places the first MU , a destination is determined for the next MU . If the strategy is non-blocking and if no successor can take on the MU , the Worker remains at the loading station or at the last unloading station and the MU is entered into the blocking list of all possible destinations. As soon as a destination is available, the Worker walks to this station.

- To move the MUs cyclically to the next successor in line, select Cyclic .
- To cyclically move the MUs to the object's successor according to the sequence of successors, which you typed into the list, select Cyclic Sequence .

You can also set the number of the succeeding object with the attribute ExitStrategySequence .

<!-- image -->

- To move the MUs on to the successor that has been Waiting the longest for a MU , select Least recent demand .
- To move the MUs on to the material flow object's successor linearly, according to the sequence of successors, which you typed into the list, select Linear sequence .

You can also set the number of the succeeding object with the attribute ExitStrategySequence .

- To move the MUs on to the successor that contains the greatest number of MUs , select Max. contents .
- To move the MUs on to the successor that received the most MUs , select Max. num. in .
- To move the MUs on to the successor with the longest processing time, select Max. proc. time .
- To move the MUs on to the successor with the highest relative occupancy, select Max. rel. occu. .
- To move the MUs on to the successor with the longest set-up time, select Max. set-up time .
- To move the MUs on to the successor that contains the smallest number of MUs , select Min. contents .
- To move the MUs on to the successor that received the smallest number of MUs , select Min. num. in .
- To move the MUs on to the successor with the shortest processing time, select Min. proc. time .
- To move the MUs on to the successor with the lowest relative occupancy, select Min. rel. occu.
- To move the MUs on to the successor with the shortest set-up time, select Min. set-up time .
- To move the MUs on to the successor that has been Waiting the least amount of time for a MU , select Most recent demand .
- To move the MUs on to the successor according to an attribute of the MU , select MU Attribute . You can also set the names of the user-defined or the built-in attributes, their values, and the numbers

of the successors with the attribute ExitStrategyMUAttributeList .

- To move the MUs on to the successors according to a percentage distribution, select Percentage . You can also set the with the attribute ExitStrategyPercentageValues .
- To move the MUs on to the successors randomly, select Random . You can also set the with the attribute ExitStrategyPercentageValues .
- To always move the MUs to the object's successor with the number 1, select Start at successor 1 .

SimTalk

ExitStrategy [SimTalk] - material flow objects

See also

Select an Exit Strategy

\_Attributes for Setting the Exit Strategy

Data Held in Tabular Form in Attributes [material flow objects]

**Video on YouTube**

[https://youtu.be/PQhEriOzVzU?si=gUp4fKa-WYTqcG95&amp;t=278](https://youtu.be/PQhEriOzVzU?si=gUp4fKa-WYTqcG95&t=278)

**Cyclic [described]**

To move the MUs cyclically to the next successor in line, select Cyclic from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU onto the object, which in sequence of successors immediately follows on the object onto which a MU was last transferred.
- If you clear Blocking , the object moves the MU to the next object in the sequence of successors, which can receive a part.

Once the object reaches the end of the sequence of successors, it continues the search for the successor at the beginning of the sequence and terminates the search when it reaches the successor from the previous search.

**SimTalk**

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Select an Exit Strategy

**Cyclic Sequence [described]**

To cyclically move the MUs to the material flow object's successor according to the sequence of successors, which you typed into the list, select Cyclic Sequence from the drop-down list.

<!-- image -->

**Note**

Click Apply , to apply your settings, and to display the button Open List .

Click Open List and type the number of the succeeding object into the corresponding cell of the list. Typing 3 into the cell in row 1, first moves the MU to the successor with the number 3.

<!-- image -->

The successor to which the object moves the MU is the next one in line that can receive it in the sequence, which you typed into the list. When the object arrives at the last entry in the list (last object in the sequence), it returns to the first entry and processes the list again.

The same successor object may be contained several times, one after the other, in the list. Then the object attempts to move the MU to this same successor as often as it is contained in the list.

- If you select Blocking , the object only moves the MU , when the designated successor is ready to receive it.
- If you clear Blocking , the object attempts to move the MU to the corresponding successor, beginning with the active entry of the list. When the object arrives at the last entry in the list (last object in the sequence), it returns to the first entry and processes the list again.

If the strategy is non-blocking , only parts that are contained in the list receive parts

SimTalk

ExitStrategy [SimTalk] - material flow objects

ExitStrategyBlocking [SimTalk]

ExitStrategySequence [SimTalk]

See also

Select an Exit Strategy

**Least Recent Demand [described]**

To move the MUs to the successor, which has been Waiting the longest time for a MU , select Least Recent Demand from the drop-down list. This means that the successor receives the next MU onto which no part moved for the longest time.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**SimTalk**

ExitStrategy [SimTalk] - material flow objects

ExitStrategyBlocking [SimTalk]

See also

Waiting [state, material flow objects]

Select an Exit Strategy

**Linear Sequence [described]**

To move the MUs on to the successor linearly, according to the sequence of successors, which you typed into the list, select Linear Sequence from the drop-down list.

<!-- image -->

**Note**

Click Apply , to apply your settings, and to display the button Open List .

Click Open List and type the number of the succeeding object into the corresponding cell of the list. Entering 3 into the cell in row 1, first moves the MU to the successor with the number 3.

<!-- image -->

The successor to which the object moves the MU is the first one in line that can receive it in the sequence, which you typed into the list.

**Linear Sequence [described]**

- If you select Blocking , the object only moves the MU to the first successor in the list of successors.
- If you clear Blocking , the object moves the MU to the first available successor in the list of successors.

If the strategy is non-blocking , only objects that are contained in the list receive MUs .

**SimTalk**

ExitStrategy [SimTalk] - material flow objects

ExitStrategySequence [SimTalk]

ExitStrategyBlocking [SimTalk]

See also

Select an Exit Strategy

**Max. Contents**

To move the MUs on to the successor that contains the greatest number of MUs , select Max. Contents from the drop-down list.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

**See also**

**Select an Exit Strategy**

**Max. Num. In**

To move the MUs on to the successor that received the most MUs , select Max. Num. In from the drop-down list.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

**See also**

**Select an Exit Strategy**

**Max. Proc. Time**

To move the MUs on to the successor with the longest processing time, select Max. Proc. Time from the drop-down list. This only works if the processing time is not set with a distribution.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**SimTalk**

ExitStrategy [SimTalk] - material flow objects

ExitStrategyBlocking [SimTalk]

See also

Select an Exit Strategy

Processing Time [general description]

**Max. Rel. Occu.**

Max. Rel. Occu.

To move the MUs on to the successor with the highest relative occupancy, select Max. Rel. Occu. from the drop-down list. This is the capacity-based ratio of the time during which the object was occupied, not paused and not failed to the time the object was not paused and not failed.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

**See also**

**Select an Exit Strategy**

**Max. Set-up Time**

**Max. Set-up Time**

To move the MUs on to the successor with the longest set-up time, select Max. Set-up Time from the drop-down list. This only works if the Set-up Time is not set with a distribution.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

For successors, which are already set up for the part, Plant Simulation assumes 0 as the set-up time .

SimTalk

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Set-up Time [general description]

Select an Exit Strategy

**Min. Contents**

To move the MUs on to the successor that contains the smallest number of MUs , select Min. Contents from the drop-down list.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

**See also**

**Select an Exit Strategy**

**Min. Num. In**

To move the MUs on to the successor that received the smallest number of MUs , select Min. Num. In from the drop-down list.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

**See also**

**Select an Exit Strategy**

**Min. Proc. Time**

To move the MUs on to the successor with the shortest processing time, select Min. Proc. Time from the drop-down list. This only works if the Processing Time is not set with a distribution.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

**SimTalk**

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Processing Time [general description]

Select an Exit Strategy

Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=5mvRYqZHYFJyThX8&amp;t=418](https://youtu.be/PQhEriOzVzU?si=5mvRYqZHYFJyThX8&t=418)

**Min. Rel. Occu.**

Min. Rel. Occu.

To move the MUs on to the successor with the lowest relative occupancy, select Min. Rel. Occu. from the drop-down list.

The minimal relative occupancy is the capacity-based ratio of the time during which the object was occupied, not paused and not failed to the time the object was not paused and not failed.

<!-- image -->

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

<!-- image -->

###### ExitStrategy [SimTalk] - material flow objects

See also

**Select an Exit Strategy**

**Min. Set-up Time**

**Min. Set-up Time**

To move the MUs on to the successor with the shortest set-up time, select Min. Set-up Time from the drop-down list. This only works if the Set-up Time is not set with a distribution.

<!-- image -->

- If you select Blocking , the object moves the MU to the next successor.
- If you clear Blocking , the object moves the MU to the next successor, which can receive the MU .

For successors, which are already set up for the part, Plant Simulation assumes 0 as the set-up time .

SimTalk

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Set-up Time [general description]

Select an Exit Strategy

**Most Recent Demand [described]**

To move the MUs to the successor that has been waiting the least amount of time for a MU , select Most Recent Demand from the drop-down list. This means that the successor, onto which a MUs was moved last, receives the next MU .

<!-- image -->

- If you select Blocking , the object moves the MU to the successor with the Most Recent Demand.
- If you clear Blocking , the object moves the MU to the successor with the Most Recent Demand, which can receive the MU .

**SimTalk**

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Waiting [state, material flow objects]

Select an Exit Strategy

**MU Attribute [described]**

To move the MUs on to a successor according to the value of an attribute of the MU , select MU Attribute from the drop-down list. You can enter several numbers of the desired successors into the Attribute List for the Attribute Value .

**Note**

Click Apply to display the dialog items of this strategy.

- If you select Blocking , the object always moves the MU to the designated successor. If that successor is not ready to receive it, the part will be blocked.

<!-- image -->

If you clear Blocking , Plant Simulation checks which of the desired successors can receive the MU . If none of the desired successors can receive the MU , Plant Simulation inserts the MU into the Blocking List of these successors.

**Open List**

Click Open List to open a table, into which you can type the names of the user-defined or the built-in Attributes , their Values , and the number of the respective Successor . The object searches the table from top to bottom until it finds an attribute with the value you typed in. It then moves the MU on to that successor.

<!-- image -->

If the strategy is non-blocking , the object continues searching if the first found object cannot accept the MU . If the strategy is non-blocking and none of the objects can accept the MU , it will be entered into the Forward Blocking List of the objects which meet one of the criteria.

<!-- image -->

**Default Successor**

Type in the number of the default successor. This is the successor to which the object moves the MU , when this MU does not have an attribute with the Value you typed into the DataTable .

To show a message, when a part is to be moved which does not meet any of the conditions in the DataTable , enter 0 .

Attribute Type

Select the data type of the attribute from this drop-down list, compare Data Types .

SimTalk

AttributeType [SimTalk] - material flow objects

DefaultSuccessor [SimTalk] - material flow objects

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

ExitStrategyMUAttributeList [SimTalk]

See also Select an Exit Strategy Data Held in Tabular Form in Attributes [material flow objects] Video on YouTube

[https://youtu.be/PQhEriOzVzU?si=rB6pUl7icKnIr0Yj&amp;t=472](https://youtu.be/PQhEriOzVzU?si=rB6pUl7icKnIr0Yj&t=472)

**Percentage [described]**

To move the MUs on to the successors according to a percentage distribution, select Percentage from the drop-down list.

<!-- image -->

Click Open List and type the percentages in the list that opens. The n-th row on the table defines the n-th successor's portion: Typing 20 in row 1, for example, moves 20 percent of the MUs which the object received to the successor with the number 1, etc.

<!-- image -->

**Note**

When you type 0 into the table, the successor of the material flow object will not receive a MU .

The object always moves the MU to the successor with the greatest difference between the rated value and the current value.

- If you select Blocking , it moves the MU to the successor with the highest deviation from the nominal percentage.

**Percentage [described]**

- If you clear Blocking , it moves the MU to the successor, which can receive the MU and which has the highest deviation from the nominal percentage.

If the strategy is non-blocking and if the list contains an entry that sets that a successor is to receive 0 % of the received parts, this successor receives parts anyway if all other successors cannot receive parts.

The actual percentages reached may differ from the nominal ones due to a low number of total transfers and to the Blocking -state of successors. Any previous transfers of MUs affect the Percentage strategy, as they alter the deviation from the nominal transfer frequencies.

Plant Simulation sums up the values you entered into the list of nominal percentages to obtain the value that corresponds to 100 percent. The distribution pattern only depends on the relative size of the values, not on their magnitude. This way you can, for example, either enter [1;2] or [0.3333…; 0.6666…] , the result will be the same.

If the distribution pattern is periodic, then it is so right from the beginning. This means that the distribution pattern at the start of a simulation run does not differ from the distribution pattern at a later point in time. These examples demonstrate, how nicely the values are balanced:

- If you assign the values 1 and 2 to the exits 1 and 2 respectively; Plant Simulation generates this sequence of exits:

2 1 2 2 1 2 2 1 2 2 1 2 2 1 2

- If you assign 2 and 3 to the exits 1 and 2, Plant Simulation generates this sequence of exits:

2 1 2 1 2 2 1 2 1 2 2 1 2 1 2

- If you assign the values 1 , 2 , 4 and 8 to the exits 1, 2, 3, and 4, Plant Simulation generates this sequence of exits:

4 3 4 2 4 3 4 1 4 3 4 2 4 3 4 4 3 4 2 4 3 4 1 4 3 4 2 4 3 4

SimTalk

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

ExitStrategyPercentageValues [SimTalk] - material flow objects

See also

Select an Exit Strategy

Data Held in Tabular Form in Attributes [material flow objects]

**Random [described]**

To move the MUs on to the successors randomly, select Random from the drop-down list.

<!-- image -->

**Open List**

Click Open List and enter the percentages in the list that opens. The n-th row on the table defines the n-th successor's portion: Typing 20 in row 1, for example, moves 20 percent of the MUs which the object received to the successor with the number 1, etc.

- If you select Blocking , the object determines the successor using the random-number generator.
- If you clear Blocking , the object determines the successor using the random-number generator until it either computes a successor, which can receive the MU , or the object has iterated through all successors.

If the strategy is non-blocking and if the list contains an entry that sets that a successor is to receive 0 % of the received parts, this successor receives parts anyway if all other successors cannot receive parts.

A previous call to the random number generator does affect the Random strategy. The order in which the successors are iterated through is not predictable.

**Random [described]**

SimTalk ExitStrategyBlocking [SimTalk] ExitStrategy [SimTalk] - material flow objects ExitStrategyPercentageValues [SimTalk] - material flow objects See also Select an Exit Strategy

Data Held in Tabular Form in Attributes [material flow objects]

**Start at Successor 1 [described]**

To always move the MU to the material flow object's successor with the number 1, select Start at Successor 1 from the drop-down list.

<!-- image -->

- If you select Blocking , the object moves the MU to the first successor in the sequence of successors.
- If you clear Blocking , the object moves the MU to the first successor in the sequence of successors, which can receive the MU .

A previous search for a successor does not affect the strategy Start at Successor 1 .

<!-- image -->

##### Tab Statistics

SimTalk

ExitStrategyBlocking [SimTalk]

ExitStrategy [SimTalk] - material flow objects

See also

Select an Exit Strategy

Tab Statistics

Tab Statistics [material flow objects]

The tab Statistics shows the most important statistical data of the objects when you select the check box Resource Statistics and click Apply .

<!-- image -->

The values for Waiting , Working , Blocked , Setting-Up , Failed , Powering up/down , Stopped , Paused , and Unplanned should add up to 100 percent.

| Item English        | Description                                                                                                                                                                                                                                                   | Read-only attribute                                       | Item German                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|------------------------------|
| Working             | Shows the portion of the statistics collection period during which the object was Working                                                                                                                                                                     | StatWorkingPortion [SimTalk]                              | Arbeitend                    |
| Setting-up          | Shows the portion of the statistics collection period during which the object was Setting-Up                                                                                                                                                                  | StatSetUpPortion [SimTalk]                                | Rüstend                      |
| Waiting             | Shows the portion of the statistics collection period during which the object was Waiting                                                                                                                                                                     | StatWaitingPortion [SimTalk]                              | Wartend                      |
| Blocked             | Shows the portion of the statistics collection period during which the object was Blocked                                                                                                                                                                     | StatBlockingPortion [SimTalk]                             | Blockiert                    |
| Powering up/down    | Shows the portion of the statistics collection period during which the object was Powering up/down                                                                                                                                                            | StatPoweringUpDo wnPortion [SimTalk]                      | Hochfahrend / runterfahren d |
| Failed              | Shows the portion of the statistics collection period during which the object was Failed                                                                                                                                                                      | StatFailPortion [SimTalk]                                 | Gestört                      |
| Stopped             | Shows the portion of the statistics collection period during which the object was Stopped by a LockoutZone                                                                                                                                                    | StatStoppedPortion [SimTalk] - material flow objects      | Angehalten                   |
| Paused              | Shows the portion of the statistics collection period during which the object was Paused .                                                                                                                                                                    | StatPausingPortion [SimTalk]                              | Pausiert                     |
| Unplanned           | Shows the portion of the statistics collection period during which the object was Unplanned , i.e., is not scheduled to work to the statistics collection period                                                                                              | StatUnplannedPorti on [SimTalk]                           | Ungepant                     |
| Relative Occupation | Shows the sum of all dwell times of all MUs during the statistics collection period during which the object was not paused and not failed. This sum is then divided by the capacity and the entire statistics collection period without pauses and failures . | StatRelativeOccupat ion [SimTalk] - material flow objects | Relative Belegung            |
| Relatively Empty    | Shows the portion of the statistics collection period during which the object was Empty in relation to the time during which the object was available                                                                                                         | StatRelativeEmptyP ortion [SimTalk]                       | Relativ leer                 |
| Relatively Full     | Shows the portion of the statistics collection period during which all temporary storage places of the Buffer were occupied in relation to the time during which the object was available                                                                     | StatRelativeFullPorti on [SimTalk]                        | Relativ voll                 |

| Item English       | Description                                                                                                                                                                                                                                                                                                                  | Read-only attribute                                     | Item German          |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------|----------------------|
| Contents           | Shows the number of MUs , which are located on the object. When a MU enters the object, it only counts the MU itself, not its contents: When a Transporter/Container transporting several MUs enters the object, the number of entries increases by 1, not by the number of MUs located on the Transporter/Container !       | NumMU[SimTalk] - material flow objects                  | Inhalt               |
| Minimum Contents   | Shows the minimum number of MUs that was located on the object. When a MU enters the object, it only counts the MU itself, not its contents: When a Transporter/Container transporting several MUs enters the object, the number of entries increases by 1, not by the number of MUs located on the Transporter/ Container ! | StatMinNumMU [SimTalk] - material flow objects          | Minimaler Inhalt     |
| Maximum Contents   | Shows the maximum number of MUs that was located on the object. When a MU enters the object, it only counts the MU itself, not its contents: When a Transporter/Container transporting several MUs enters the object, the number of entries increases by 1, not by the number of MUs located on the Transporter/ Container ! | StatMaxNumMU [SimTalk] - material flow objects          | Maximaler Inhalt     |
| Entries            | Shows the number of MUs that entered the object. When a MU enters the object, it only counts the MU itself, not its contents: When a Transporter/Container transporting several MUs enters the object, the number of entries increases by 1, not by the number of MUs located on the Transporter/Container !                 | StatNumIn [SimTalk] - material flow objects             | Eingänge             |
| Exits              | Shows the number of MUs that exited the object. When a MU exits the object, it only counts the MU itself, not its contents: When a Transporter/ Container transporting several MUs leaves the object, the number of exits increases by 1, not by the number of MUs which the Transporter/ Container transports!              | StatNumOut [SimTalk] - material flow objects            | Ausgänge             |
| Average Dwell Time | Shows the average time of all MUs which stayed on the station. Plant Simulation only counts times during which the object was not paused and not unplanned.                                                                                                                                                                  | StatAverageDwellTi me [SimTalk] - material flow objects | Mittlere Verweilzeit |

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

To show energy statistics values, click Energy Statistics

**See also**

| View and Visualize Statistics           | Resource Type                                 |
|-----------------------------------------|-----------------------------------------------|
| Statistics of the Material Flow Objects | Entrance Blocked                              |
| Statistics Report [described]           | Exit Blocked                                  |
| Resource Statistics [check box]         | _Read-Only Attributes for Querying Statistics |

**Video on YouTube**

[https://youtu.be/BvHLQCIjGIA?si=-eOdaB0iYAngwuf1&amp;t=80](https://youtu.be/BvHLQCIjGIA?si=-eOdaB0iYAngwuf1&t=80)

.

###### Resource Statistics [check box]

To collect resource statistics data during a simulation run and to show the most important values on the tab, select this check box. To deactivate the collection of statistics data, clear the check box.

<!-- image -->

The statistics data is described under Resource Statistics .

**Note**

Statistics collection is active by default.

**Note**

In this context, resources are any of the material flow objects, for which you can select a Resource Type . Do not confuse them with the Resource Objects .

Plant Simulation does not dynamically update the values during a simulation run when the dialog box is open. To accomplish this, select Refresh on the View menu of the object or press F5 .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can select the object in the Frame and press F6 .

SimTalk

ResStatOn [SimTalk] - material flow objects

initStat [SimTalk] - material flow objects

statistics [SimTalk] - material flow objects

updateDialog [SimTalk]

###### Resource Type

Select the Resource Type of the material flow resource: Production , Transport , or Storage .

This only affects collecting statistics values of those MUs which are located on the material flow object.

- Production resources are Source , Drain , Station , ParallelStation , AssemblyStation , and DismantleStation , which produce and process parts.
- Transport resources are PlaceBuffer , Buffer , Sorter , Track , TwoLaneTrack , Conveyor , AngularConverter , Turntable , Transporter , and Container , which transport parts between stations.
- Storage is the default setting for the Store , which stores parts.

**Note**

Do not confuse the material flow resources with the Resource Objects .

<!-- image -->

**SimTalk**

ResourceType [SimTalk]

See also

\_Read-Only Attributes for Querying Statistics

Resource Statistics Values of the Container

###### Entrance Blocked

All material flow objects proper, except for Source , Track , TwoLaneTrack , FlowControl , and Cycle , and the fluid object DePortioner show the value Entrance Blocked .

<!-- image -->

This is the portion of the time in percent during which the entrance of the material flow object was blocked because it could not receive a MU from any of its predecessors.

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- That left a Conveyor at a sensor.
- That could not leave the predecessor because its exit was locked .

Plant Simulation also does not record times for which the Entrance of the material flow object was Locked .

The Entrance Blocked portion does not refer to the entire simulation time, but only to the time during which the material flow object was available , i.e, it was not paused , failed , or stopped .

SimTalk

StatEntranceBlockedPortion [SimTalk]

StatEntranceBlockedTime [SimTalk]

###### Exit Blocked

All material flow objects proper, except for the Drain , Store , Track , TwoLaneTrack , FlowControl , and Cycle , as well as the Portioner show the value Exit Blocked .

This is the portion of the time in percent during which the material flow object was blocked because a MU could not leave it and none of the successors could receive a MU .

Plant Simulation considers only MUs for which an Out event was scheduled.

It does, for example, not consider MUs :

- That were moved via SimTalk .
- Which left a Conveyor at a sensor.
- For which the Dwell Time of a Buffer has not passed yet.

<!-- image -->

Plant Simulation also does not record times for which the Exit of the material flow object was Locked .

The Exit Blocked portion does not refer to the entire simulation time, but only to the time during which the material flow object was available, i.e, it was not paused , failed , or stopped .

**Note**

Plant Simulation considers a Buffer/PlaceBuffer as starved if it cannot provide parts to a successor, no matter if a successor could currently take the part or not. The starved condition is the opposite of the Exit Blocked condition, i.e., a Buffer/PlaceBuffer is either in the state Exit Blocked or starved .

Therefore, the Exit Blocked portion plus the starved portion always add up to 100 %. We do not provide the starved portion as a separate statistics value.

SimTalk

StatExitBlockedPortion [SimTalk]

StatExitBlockedTime [SimTalk]

###### Energy Statistics [button]

To show the energy statistics values which the object collected, click this button.

<!-- image -->

**Note**

The energy states of the material flow objects differ from the resource states with the same name. The values for the resource states refer to the statistics collection period, while the values for the energy states refer to the total energy consumption.

| Item English       | Description                                                                                 | Read-only attribute                                | Item German      |
|--------------------|---------------------------------------------------------------------------------------------|----------------------------------------------------|------------------|
| Total consumpti on | Shows the sum of the total energy consumption.                                              | StatEnergyTotalConsumption [SimTalk]               | Gesamtver brauch |
| Working            | Shows the portion of the total energy consumption during which the object was working .     | StatEnergyWorkingConsumptionP ortion [SimTalk]     | Arbeitend        |
| Setting-up         | Shows the portion of the total energy consumption during which the object was setting-up .  | StatEnergySetupConsumptionPort ion [SimTalk]       | Rüstend          |
| Operationa l       | Shows the portion of the total energy consumption during which the object was operational . | StatEnergyOperationalConsumpti onPortion [SimTalk] | Betriebsbe reit  |
| Failed             | the portion of the total energy consumption during which the object was failed .            | StatEnergyFailConsumptionPortio n [SimTalk]        | Gestört          |

<!-- image -->

| Item English   | Description                                                                                | Read-only attribute                            | Item German   |
|----------------|--------------------------------------------------------------------------------------------|------------------------------------------------|---------------|
| Standby        | Shows the portion of the total energy consumption during which the object was on standby . | StatEnergyStandbyConsumptionP ortion [SimTalk] | Standby       |
| Off            | Shows the portion of the total energy consumption during which the object was off .        | StatEnergyOffConsumptionPortio n [SimTalk]     | Aus           |

To view Energy Statistics - Energy Statistics in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can select the object in the Frame and press F6 .

See also

Tab Energy [general description]

Simulate the Power Consumption in Your Facility

\_Read-Only Attributes for Energy Statistics

View Statistics in the Dialogs of the Objects

Tab Curve [2D]

Tab Curve [general description]

Define the settings of a curved length-oriented object in 2D on the tab Curve .

Note

Only a 2D Only model provides the tab Curve .

Curved length-oriented objects are the Conveyor , the Track , the TwoLaneTrack , the FootPath , and the Pipe . By inserting a sequence of curved (arc) segments and straight segments, you can realistically model conveyor systems and tracks with curves on which the mobile objects Part , Container , Transporter , and Worker move to their destination, either to the Workplace or directly to the material flow object.

The AngularConverter , the Converter , the Turnplate , and the Turntable also use curve settings.

<!-- image -->

Plant Simulation uses the length of polygonal and curved objects during the simulation. The Scaling Factor , which you select in the Frame , controls how Plant Simulation computes the length. Plant Simulation automatically animates and aligns mobile objects along the polygon or the curve.

<!-- image -->

To open a sensor that you defined and that Plant Simulation inserts as a red line into the icon of the object, Alt +double-click the red line . Then, change the settings in the dialog that opens.

The illustration shows the most important items of the curve that you can define:

<!-- image -->

When you start inserting curved objects, Plant Simulation opens the dialog below. Working with Curved Objects describes the setting you can select.

<!-- image -->

For straight and curved segments you can type in an Anchor Point Height . It determines the height, i.e., the distance from the floor, of the next anchor point. It is especially useful when you model material handling equipment with different elevations.

In 3D, you can also model differences in height between conveying objects .

<!-- image -->

The Anchor Point Height in 2D corresponds to the Base Height in 3D.

In 3D, you can access the segments on the context menu, and you can select additional settings on the tab Appearance of the length-oriented objects .

<!-- image -->

Number of Animation Events

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the material flow object during a simulation run.

- Click the icon of the length-oriented object with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Type a number into the text box.

<!-- image -->

**Note**

The number you can type in only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events and Animate Every X-th-pixel also apply for rotations.

**See also**

| Work with Length-oriented Objects in 2D and 3D   | Segments [curve] - 2D, described   |
|--------------------------------------------------|------------------------------------|
| Active [check box] - curve                       | Rotate Movables                    |
| Curve Width                                      | Transfer Length                    |
| Pen Width                                        | Transparent [curve]                |
| Color [curve]                                    | Base Height [curve]                |
| Pen Color                                        | _Methods of Curved Objects in 2D   |

| Midline Style            | _Attributes of the Curved Objects in 2D   |
|--------------------------|-------------------------------------------|
| Animate Every x-th Pixel | Segments [2D]                             |

###### Active [check box] - curve

To activate Curve mode, select this check box and click OK or Apply .

<!-- image -->

<!-- image -->

To insert the length-oriented object with its icon , clear the check box. Then Plant Simulation animates the MUs on them using the number of animation events, which you typed in the icon editor with the command Set Animation Events .

<!-- image -->

**SimTalk**

CurveActive [SimTalk]

###### Curve Width

Type in the Curve Width with which Plant Simulation shows the length-oriented curved object in the Frame .

This can be a number between 1 and 500 pixels.

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can type in the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**SimTalk**

CurveWidth [SimTalk] if you want to enter the width in pixels in 2D

###### Pen Width

Type in the pen width of the outline around the border of the length-oriented curved objects.

This can be a value between -1 and 100 .

<!-- image -->

- The value -1 makes the outline invisible.
- The value 0 stands for a pen width of 1 pixel. The width of the outline is not zoomed when you zoom the contents of the Frame .
- The value 1 stands for a pen width of 1 pixel as well. The width of the outline is also zoomed when you zoom the contents of the Frame .

<!-- image -->

| Pen width -1   | Pen width 0   | Pen width 1   | Pen width 2   |
|----------------|---------------|---------------|---------------|

3D does not use this setting.

SimTalk

PenWidth [SimTalk]

###### Color [curve]

To select the color of the length-oriented curved objects proper, click the field next to Color .

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

**SimTalk**

Color [SimTalk] - material flow objects

###### Pen Color

To select the color of the outline around the border of the picture of the curved object, click the field next to Color .

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

<!-- image -->

**SimTalk**

PenColor [SimTalk]

###### Midline Style

Select a style for the line in the middle of the curved object.

The icons of the MUs move on this line across your tracks , conveyors , or footpaths . By default, curved objects do not have a midline style.

<!-- image -->

**SimTalk**

MidLine [SimTalk]

###### Animate Every x-th Pixel

Select one of the predefined distances or enter a distance of your choice between two pixels on which Plant Simulation animates the part or the Transporter on the length-oriented curved objects.

<!-- image -->

For the Turntable this setting in addition controls the rotation steps with which the table rotates.

Select 1 to make the object animate the part/Transporter on every pixel.

Select 10 to animates it on every tenth pixel. The higher the number you select, the better the performance will be. When you select 1 , performance may suffer if your model contains many MUs .

SimTalk

AnimateOnEveryXthPixel [SimTalk]

**Segments [curve] - 2D, described**

###### Segments [curve] - 2D, described

To open the Segments table, which shows information about the starting point and the curved and straight segments of the curved object, which you inserted, click this button.

<!-- image -->

You can edit the Tangential angle , the Length , the Curve angle , the Radius , the Vertical curve , and the Z-difference of a segment, while Plant Simulation computes the remaining, unavailable values.

If the curved object is an animation polycurve in 3D, you can define a tangential angle and a length in addition to also place this starting point outside the zero point of the object in the x-direction and the y-direction.

**Note**

You can view how the table has to be formatted, which you can assign with the method setCurveSegments .

<!-- image -->

The definition of the segments table always shows the original orientation of the segments without a possible rotation or mirroring. The rotation is stored in the attribute ObjectAngle and mirroring is stored in the attribute ObjectMirrored . This enables retaining inheritance of the definition of the segments even when one or more segments are rotated or mirrored.

The first row shows the additional offset in the z-direction to the Base Height [curve] to define the starting point of the curved object. Enter a different value to increase the distance of the feet of a conveyor from the floor of the plant.

| Item                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tangential Angle                         | Sets the change of the tangential angle of a segment, relative to the previous direction of the segment. For the starting point it is relative to the horizontal. A positive number designates a clockwise angle, a negative number a counterclockwise angle. The tangential angle is located on the plane.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Length                                   | Sets the length of a straight segment, i.e., of the distance between the start and the end of the segment. When the straight segment contains an incline, i.e., when the z-heights of the starting point and of the end point differ, the length is the length that is projected onto the xy-plane. A curved segment does not show any value here.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Curve Angle                              | Sets the angle α that is formed by the radius between the start and the end point of a horizontal or a vertical arc segment. A positive number designates a clockwise angle, a negative number a counterclockwise angle.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Radius                                   | Sets the radius of a horizontal or a vertical arc segment. A straight segment does not show any value here.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Vertical Curve (only recognizable in 3D) | Sets the state of the segment. If the segment is a vertical curve segment, the check box is selected. If it is no vertical curve segment, it is cleared. For a straight segment and a horizontal curve segment, the check box is cleared. When you insert a vertical curve segment in 3D, the check box is selected. You can clear the check box to change the vertical curve segment to a horizontal curve segment. A vertical curve segment affects its neighboring segments more than it does other segments. For all other segments the tangential angle only affects the succeeding segment. A vertical curve segment, in addition, enforces that its own tangential angle and the tangential angle of the succeeding segment is 0 and that the preceding as well as the succeeding segment also tangentially connect in the vertical direction. This means that a succeeding vertical curve segment will be interpreted depending on its preceding segment and that Plant Simulation enforces a suitable relation of projected height and height offset for all other succeeding segments. |
| ΔZ                                       | Sets the additional offset to the base height to the predecessor segment.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| X                                        | Shows the x-coordinate of the anchor point of a segment in the Frame . Plant Simulation computes this value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |

| Item   | Description                                                                                                  |
|--------|--------------------------------------------------------------------------------------------------------------|
| Y      | Shows the y-coordinate of the anchor point of a segment in the Frame . Plant Simulation computes this value. |
| Z      | Shows the z-coordinate of the anchor point of a segment in the Frame . Plant Simulation computes this value. |
| ΔL     | Shows the length of the object up to this segment                                                            |

<!-- image -->

**Inheritance of the Segments Table**

A button that looks like this means that inheritance is active. Then, the object inherits, i.e., uses, the shape of the origin object from which you derived it. When you modify the value of the origin object, the program also modifies the value of the derived object.

A button that looks like this means that inheritance is not active. The values only apply to the selected object.

**Note**

The segments table shows absolute coordinates, while Plant Simulation stores the anchor points as relative coordinates, which relate to the first anchor point. The position of the curved object in the Frame is determined by the attributes XPos and YPos , which are the respective coordinates of the first anchor point. If the segments table is inherited this means that the relative coordinates of the anchor points are inherited.

For this reason it may happen that an inherited segments table shows other coordinates than the original curved object when the XPos and/or YPos of the curved object has changed. Inheritance relates to the shape of the curved object, not to the position at which it is inserted in the Frame !

SimTalk getCurveSegments [SimTalk] setCurveSegments [SimTalk] See also Segments [tab Appearance] - 3D Segments [2D] \_3D.getExtSegments [SimTalk] \_3D.setExtSegments [SimTalk] Base Height [curve] Model Differences in Height Between Conveying Elements Reuse the Segments of a Length-oriented Object

###### Rotate Movables

To rotate the part on the length-oriented curved objects in the direction of motion when the part turns in a curve, select this check box.

**Note**

We advise to not deactivate Rotate Movables as this setting does not affect the behavior in 3D .

<!-- image -->

**Note**

A rotation triggered by the setting Rotate MUs on a length-oriented object only has an effect as long as the MU is located on this object. When leaving the object the MU again assumes the rotation it had before. When entering a new object, the MU considers the rotation of this new object if Rotate MUs is active.

**Note**

When Plant Simulation shows a length-oriented object in curve mode, Plant Simulation evaluates the setting Rotate MUs .

**SimTalk**

RotateMovables [SimTalk]

###### Transfer Length

To use the length of the curve in the layout within the Frame as the length of the curved objects, select this check box. When the dialog of the object is open, Plant Simulation enters this value into the text box Length on the tab Attributes .

<!-- image -->

- When you select Transfer Length , Plant Simulation adapts the length of the graphic, when you change the Length if the object only consists of a single straight segment.
- When you clear Transfer Length , you can change the shape of the object in the Frame at will, while the object uses the length which you manually entered into the text box Length .

<!-- image -->

Automatically Connect Length-oriented Objects in 3D

The following applies for automatically connecting the length-oriented objects Turnplate , Turntable , AngularConverter , Conveyor , Converter , Track , and TwoLaneTrack in 3D:

If transfer length is cleared for one of these objects in 3D and if a suitable MU animation path exists, Plant Simulation uses the starting point and the end point of these animation paths for automatically connecting objects and for displaying the Connectors . Suitable MU animation paths are Default or Cross for the Converter , A or B for the TwoLaneTrack , and Default for all other objects. This applies for the setting Connect Objects Automatically and for the method connectAutomatically .

**SimTalk**

**TransferLengthToObject [SimTalk]**

**See also**

| Length [text box] - FootPath                    | Length [text box] - Track     |
|-------------------------------------------------|-------------------------------|
| Entry Length [text box] of the AngularConverter | Length [text box] - Turnplate |
| Exit Length [text box] of the AngularConverter  | Length [text box] - lane A    |
| Length [text box] - Conveyor                    | Length [text box] - lane B    |

**Transparent [curve]**

###### Transparent [curve]

To make the inside of the curved object transparent, so that the background color of the Frame shines through, select this check box.

<!-- image -->

The border of the object remains as it is, i.e. non-transparent. To completely hide the curved object, type in a value less than 0 for the Pen Width .

<!-- image -->

| Not transparent   | Transparent   |
|-------------------|---------------|

SimTalk

Transparent [SimTalk] - material flow objects

###### Base Height [curve]

Type in the Base Height of the curved object.

<!-- image -->

The Base Height sets the distance between the insertion height (z-coordinate) of the length-oriented object and the height of a segment whose ΔZ equals 0.

The Base Height can be inherited, meaning that you can define it once in the class instead of having to define it individually for each instance. It is mainly used in 3D . Here the z-coordinate defines the floor of the installation and the base height defines the distance of the legs from the floor. By changing the setting ΔZ in the Segments table, you can add an additional offset. The setting ΔZ also affects the simulation time in 2D .

<!-- image -->

SimTalk

BaseHeight [SimTalk] - material flow objects

See also

Segments [curve] - 2D, described

Base Height [tab Appearance]

Insert Curved and Straight Segments &gt; anchor point height

Segments Context Menu

Segments [2D]

Provides subcommands to work with the segments of length-oriented curved objects .

| Append [segment, 2D]   | Insert Point           |
|------------------------|------------------------|
| Edit [segment, 2D]     | Reverse [segment, 2D]  |
| Delete Point           | Split Up [segment, 2D] |

<!-- image -->

**Note**

You can create anchor points for Connectors with the mouse the same way as you create them for length-oriented objects.

3D also provides the context menu Segments .

**See also**

Segments [2D]

Segments [3D]

**Append [segment, 2D]**

To append one or more anchor points to the end of the length-oriented curved object, right-click the object. Then select this command and click in the Frame window on the positions at which you would like to add the new points/segments one after the other.

You can select additional settings in the dialog Line/Arc Parameters .

Hold down Ctrl to append a curved segment. Plant Simulation then connects the last anchor point with the one you just appended.

Click the right mouse button or press Esc to terminate append mode.

See also

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

Segments [3D] &gt; Append [segment 3D]

**Edit [segment, 2D]**

**Edit [segment, 2D]**

To edit the selected segment of the length-oriented curved object, right-click it and select this command.

Instead, you can also press the F7 key.

Then edit the settings of the object in the Segments Table that opens.

Click Apply or OK , to apply your changes.

<!-- image -->

**See also**

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Segments [3D] &gt; Append [segment 3D]

**Delete Point**

To delete an anchor point from a curved object, right-click it and select this command.

Plant Simulation then removes the anchor point and connects the point in front of the deleted anchor point with the anchor point, which follows the deleted point.

If you delete the last anchor point of a length-oriented object, Plant Simulation deletes this anchor point and the segment directly before it. The Segments table reflects this change.

See also

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

**Insert Point**

**Insert Point**

To insert an anchor point between two existing anchor points, right-click the location between those points and select this command.

The Segments Table then reflects this change.

See also

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

**Reverse [segment, 2D]**

To change the direction of motion of the length-oriented object, i.e., to make the last point of the object the first point, right-click the object and select this command.

<!-- image -->

<!-- image -->

This is especially handy if you want to mirror the layout of a production line by copying it and then reversing the direction of motion of the mirrored line to ensure a circular flow of materials.

In 2D the arrow on the object, in our case the Conveyor , shows the changed direction.

<!-- image -->

In 3D, you can see the reversed direction by looking at the Connector when you connect other objects.

<!-- image -->

**SimTalk**

reverse [SimTalk]

See also

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

Segments [3D] &gt; Reverse [segment, 3D]

**Split Up [segment, 2D]**

**Split Up [segment, 2D]**

To split the length-oriented objects FootPath , Conveyor , Track , and TwoLaneTrack into individual separate segments at the selected point, click the point where you would like to split it up and select this command.

<!-- image -->

Plant Simulation creates a copy of the object and splits the object up into two parts at the mouse position. Plant Simulation distributes Sensors according to their position to both objects. The same applies for the Entrance Controls , for the Exit Controls , and for Connectors .

This looks like this in 2D and in 3D:

<!-- image -->

**See also**

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

Segments [3D] &gt; Split Up [segment 3D]

##### Tab Importer

Tab Importer [general description]

Define the settings for importing services to be performed on certain material flow and fluid objects on the tab Importer .

These objects can import services:

- The Material Flow Objects Source , Drain , Station , ParallelStation , AssemblyStation , DismantleStation , PickAndPlace Robot , Store , Buffer , PlaceBuffer , Sorter and Conveyor .
- The Fluid Objects DePortioner , Mixer , Portioner , and Tank .

When the importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

The importer works together with the Broker and the Exporter / Worker to assign services to the individual stations.

On the tab Importer you can select and type in settings for requesting services for the importer types listed below.

- Services for processing parts on the Sub-tab Processing .

The Processing Importer requests Exporters/Workers from the start of the processing time to its end. Plant Simulation releases the Exporters/Workers after processing is finished, provided no additional MUs are located on the station which still require the Exporters/Workers .

- Services for setting up some of the Material Flow and Fluid objects on the Sub-tab Set-up .

When you select the check box Common Resources and click Apply , the requested Exporter/Worker sets the station up for the parts and processes these parts himself.

<!-- image -->

When you clear the check box and click Apply , the requests are placed by two different Importers . You can then define the services and the other settings on the Sub-tab Processing and on the Sub-tab Set-Up .

The Setup Importer requests Exporters/Workers when setting-up is pending. Plant Simulation releases the Exporters/Workers when setting-up is finished and when setting-up is not required for another MU Type .

<!-- image -->

- Services for repairing the failures of the station on the Sub-tab Failure .

- Services for transporting parts on the Sub-tab Transport .

When you place a Workplace close to the material flow object and click the left mouse button, Plant Simulation opens a window asking you Do you want to activate an importer? Select the respective importer and click the left mouse button to activate this importer. Not all objects provide all importer types.

<!-- image -->

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

**Note**

For Broker hierarchies , i.e., for several Brokers that are connected with Connectors , the brokered services are only considered for that Broker which you typed into the Importer . This also applies if the service is provided by sub-Brokers .

See also

Model Workers with Importer, Broker, and Exporter

Model Workers and the Jobs They Do

- \_Methods of the Importer
- \_Attributes of the Importer

Sub-tab Processing

Processing Importer

Select and type in settings for requesting services for processing parts on the sub-tab Processing .

<!-- image -->

You can edit the contents of the text boxes with the commands on the Context Menu of Embedded Lists .

To show Importer Statistics , select View &gt; Show Statistics Report in the dialog of the object. You can also click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies if the service is provided by sub-Brokers .

**See also**

Model Workers with Importer, Broker, and Exporter

Model Workers and the Jobs They Do

\_Methods of the Importer

\_Attributes of the Importer

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=Ft4r3\_Sq9xlzt9DU&amp;t=45](https://youtu.be/HiPziA8kxc0?si=Ft4r3_Sq9xlzt9DU&t=45)

<!-- image -->

**Active [check box] - processing importer**

To activate the importer , select this check box. Some of the Material Flow and Fluid objects can then request services for setting them up or for processing the parts on them respectively.

<!-- image -->

To deactivate the importer , clear the check box.

SimTalk

imp. Active [SimTalk] - importer

**Services for Processing**

**Services for Processing**

To specify groups of Services for Processing parts, click this button.

<!-- image -->

Each of these services represents an alternative.

To perform the set-up , processing , or repair jobs, the importer always needs all services of an Alternative . When, for example, the importer does not have all services of Alternative1 , he attempts to get all services of Alternative2 , etc. For successive services in the table, which all belong to the same alternative, the name of the alternative is only shown after the first service in the table.

The set-up-importer requests Exporters before setting-up. By default, the object releases the Exporters/ Workers when set-up is finished and when the object is not in the process of setting-up for a part.

The processing-importer requests Exporters/Workers from the beginning of the processing time to the end of the processing time. By default, the material flow object releases the Exporters/Workers when processing is finished.

- First, click the Inheritance check box so that it looks like this . Only then you can enter data into the list.
- Type the name of the service to be requested into the cells of the column Service .
- Type the amount, i.e., the number of services to be requested, into the cells of the column Amount .
- Type the name of the alternative service, which the importer provides if it cannot meet the previous service, into the cells of the column Alternative . If you want to add a service to an alternative at a later point in time, you can type this service and the name of the Alternative into the last row of the table. When you click Apply here, and in the dialog of the material flow object, Plant Simulation sorts the list anew and places this service below the respective alternative.

<!-- image -->

**Note**

This only applies when no MUs are located on the material flow object which still require one of the services that the Exporters/Workers provide.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Note**

When the importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

The importer works with the Broker and the Exporter / Worker to assign services to the individual stations.

You can edit the contents of the text boxes with the commands on the context menu of embedded lists .

SimTalk

imp. setServices [SimTalk] - importer

imp. getServices [SimTalk] - importer

See also

Context Menu of Embedded Lists

Change the Importer Services in the Entrance Control

**Can Be Interrupted and Drawn Off [processing importer]**

Can Be Interrupted and Drawn Off [processing importer]

To allow importers with a higher priority to withdraw resources, i.e., Exporters/Workers from this importer , select this check box.

When an importer with higher priority requests services, which the freely available resources cannot fulfill, and when sufficient interruptible importers with lower priority are available, to which the required services are brokered at the moment, then as many interruptible importers are interrupted as required to satisfy the importer with higher priority.

The tasks ( processing / setting-up / repair / transport ), which the interrupted importer performs, will then be interrupted, and the resources are brokered to the importer with higher priority.

SimTalk

imp. Interruptible [SimTalk]

setupImp. Interruptible [SimTalk]

**Priority [processing importer]**

Priority [processing importer]

Type in the Priority with which the importer of the object fulfills a request.

<!-- image -->

The Priority of an importer is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides a service with Priority 10 before providing a service with Priority 1.

If the importer is not assigned an Exporter immediately after a request, the importer will be entered in the list of unsatisfied requests of the Broker that is arranged according to priority.

SimTalk

imp. Priority [SimTalk] - importer

setupImp. Priority [SimTalk] - importer

**Broker [processing importer]**

Click the ellipsis button and select the Broker , which assigns the setup service or the processing service respectively.

<!-- image -->

Or select the Broker in a Frame , drag it to the text box and drop it there.

By default, Plant Simulation enters root.Broker . When Plant Simulation detects an invalid Broker during the simulation, it opens the dialog of the object with the respective sub-tab.

**Note**

For Broker hierarchies Plant Simulation only calls the control of this Broker , not the controls of any existing sub-Brokers .

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

SimTalk

imp. BrokerPath [SimTalk] - importer

setupImp. BrokerPath [SimTalk] - importer

**Request Control [processing importer]**

Click the ellipsis button and select a Method object in which you programmed how the material flow object requests Exporters/Workers , which is called when the importers would by default send a request to the Broker .

<!-- image -->

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

You can also create a control which is a user-defined attribute of data type method of this object. To do so, right-click in the text box and select Create Control . This might look like this:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control . Or
- Select Create Control . Plant Simulation then inserts self.On&lt;Name\_of\_the\_Control&gt; .

Type the source code of this control into the Method that opens. To edit the source code later on, press F2 . Or hold down Shift and double-click into the text box. Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

The standard request control looks like this:

<!-- image -->

**Parameter**

The Request Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to request the Exporters/Workers with the method import .

SimTalk

imp. RequestCtrl [SimTalk]

imp. import [SimTalk] - importer

import [SimTalk] - importer

**Receive Control [processing importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Receive Control , which is called when an Exporter/Worker was assigned to the importer .

<!-- image -->

The Receive Control sets how the material flow object receives Exporters/Workers .

The Receiving Control is called after the Entrance Control of the Workplace and after the Order Control of the Exporter/Worker .

<!-- image -->

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard receive control looks like this:

<!-- image -->

**Parameters**

The receive control has to define two parameters:

- The parameter Importer type of data type integer designates the type of the importer .
- The parameter Exporters is an array of data type object that contains all brokered Exporters/Workers . If Exporters/Workers were requested for a part, you have to start carrying away the part with the method startProcessing . You can also model travel times with a wait-instruction before calling the method startProcessing .

SimTalk

imp. ReceiveCtrl [SimTalk]

imp. startProcessing [SimTalk] - importer

See also

Select Object [for controls]

**Release Control [processing importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Release Control , which sets how the material flow object releases the Exporters/Workers .

<!-- image -->

Plant Simulation executes the Release Control , when the Exporters/Workers would be released again by default.

When you created an Exit Control and an Importer Release Control , the Importer Release Control is called first, and then the Exit Control is called.

<!-- image -->

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard release control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The release control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to release the Exporters/Workers with the method releaseExporters .

**SimTalk**

imp. ReleaseCtrl [SimTalk] - importer

imp. releaseExporters [SimTalk]

See also

Select Object [for controls]

###### Sub-tab Set-up

**Set-up Importer**

Select and type in settings for requesting services for setting up some of the Material Flow and Fluid objects on the sub-tab Set-up .

<!-- image -->

To show Importer Statistics , select View &gt; Show Statistics Report in the dialog of the object. You can also click the object with the right mouse button in the Frame and select Show Statistics Report on the context menu or press F6 .

<!-- image -->

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies if the service is provided by sub-Brokers .

See also

Model Workers with Importer, Broker, and Exporter

Model Workers and the Jobs They Do

- \_Methods of the Importer
- \_Attributes of the Importer

Active [check box] - set-up importer

To activate the importer , select this check box.

<!-- image -->

Some of the Material Flow and Fluid objects can then request services for setting them up.

To deactivate the importer , clear the check box.

SimTalk

setupImp. Active [SimTalk] - importer

**Common Resources [set-up importer]**

To use one set of services for setting the station up for a new part and for then processing these parts, select this check box.

The station then deactivates the settings for the set-up-importer .

- If you select the check box and click Apply , the requested Exporter/Worker sets the station up for the parts and processes these parts himself.
- If you clear the check box and click Apply , the requests are placed by two different Importers . You can then define the services and the other settings on the Sub-tab Processing and on the Sub-tab Set-Up .

<!-- image -->

<!-- image -->

If you do not need any services for setting-up or for processing, you have to delete the existing services from the services table.

The Processing Importer requests Exporters/Workers from the start of the processing time to its end. Plant Simulation releases the Exporters/Workers after processing is finished, provided no additional MUs are located on the station which still require the Exporters/Workers .

The Setup Importer requests Exporters/Workers when setting-up for a different part type is necessary. Plant Simulation releases the Exporters/Workers when setting-up is finished and when setting-up is not required for another part type.

SimTalk

imp. Common [SimTalk]

setUpImp. Common [SimTalk]

**Services for Setting-up**

**Services for Setting-up**

To type in groups of services for setting the station up for another part type , click this button.

<!-- image -->

Each of these services represents an alternative.

To perform the set-up job, the importer always needs all services of an Alternative . When, for example, the importer does not have all services of Alternative1 , he attempts to get all services of Alternative2 , etc. For successive services in the table, which all belong to the same alternative, the name of the alternative only shows the first service.

The set-up-importer requests Exporters/Workers before setting-up. By default, the object releases the Exporters/Workers when set-up is finished and when the object is not in the process of setting-up for a part.

The processing-importer requests Exporters/Workers from the beginning of the processing time to the end of the processing time. By default, the material flow object releases the Exporters/Workers when processing is finished.

- First, click the Inheritance check box so that it looks like this . Only then you can enter data into the list.
- Type the name of the service to be imported into the cells of the column Service .
- Type the amount, i.e., the number of services to be imported, into the cells of the column Amount .
- Type in the name of the alternative service, which the importer provides if it cannot meet the previous service, into the cells of the column Alternative . When you want to add a service to an alternative at a later point in time, you can type this service and the name of the Alternative into the last row of the table. When you click Apply here, and in the dialog of the material flow object, Plant Simulation sorts the list anew and places this service below the respective alternative.

<!-- image -->

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Note**

When the importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

The importer works with the Broker and the Exporter / Worker to assign services to the individual stations.

You can edit the contents of the text boxes with the commands on the Context Menu of Embedded Lists .

SimTalk

setUpImp. setServices [SimTalk] - importer

setUpImp. getServices [SimTalk] - importer

See also

Change the Importer Services in the Entrance Control

**Can Be Interrupted and Drawn Off [set-up importer]**

Can Be Interrupted and Drawn Off [set-up importer]

To allow importers with a higher priority to withdraw resources, i.e., Exporters/Workers from this importer , select this check box.

When an importer with higher priority requests services, which the freely available resources cannot fulfill, and when sufficient interruptible importers with lower priority are available, to which the required services are brokered at the moment, then as many interruptible importers are interrupted as required to satisfy the importer with higher priority. The tasks ( processing / setting-up / repair / transport ), which the interrupted importer performs, will then be interrupted, and the resources are brokered to the importer with higher priority.

SimTalk

imp. Interruptible [SimTalk]

setUpImp. Interruptible [SimTalk]

**Release All Services When One Of Them Is Failed [set-up importer]**

To make the material flow object release all set-up services or processing services , when one or more of these services is failed or paused, select this check box.

This also applies if a service was interrupted because it was requested by an importer with higher priority. To only release the failed services , clear it.

This only works, when you also select Fail Services in the dialog of the Exporter . For the Worker Fail services is always implicitly active.

SimTalk

imp. ReleaseAllServices [SimTalk]

setUpImp. ReleaseAllServices [SimTalk]

**Priority [set-up importer]**

Priority [set-up importer]

Type in the Priority with which the importer of the object fulfills a request.

<!-- image -->

<!-- image -->

The Priority of an importer is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides a service with Priority 10 before providing a service with Priority 1.

If the importer is not assigned an Exporter immediately after a request, the importer will be entered in the list of unsatisfied requests of the Broker that is arranged according to priority.

SimTalk

imp. Priority [SimTalk] - importer

setUpImp. Priority [SimTalk] - importer

**Broker [set-up importer]**

Click the ellipsis button and select the Broker , which assigns the setup services .

<!-- image -->

By default, Plant Simulation enters root.Broker . When Plant Simulation detects an invalid Broker during the simulation, it opens the dialog of the object with the respective sub-tab.

Or select the Broker in a Frame , drag it to the text box and drop it there.

**Note**

For Broker hierarchies Plant Simulation only calls the control of this Broker , not the controls of any existing sub-Brokers .

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

SimTalk

imp. BrokerPath [SimTalk] - importer

setUpImp. BrokerPath [SimTalk] - importer

**Request Control [set-up importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Request Control , which sets how the material flow object requests Exporters/Workers .

<!-- image -->

Plant Simulation executes the Request Control , when the importers by default send a request to the Broker .

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard request control as a user-defined attribute looks like this:

<!-- image -->

Parameter

The Request Control has to define two parameters:

- The parameter Importer type of data type integer , which designates the type of the importer . You have to request the Exporters/Workers with the method import .
- The parameter setupFor of data type string designates the type of MU for which the object is going set up.

**SimTalk**

setUpImp. RequestCtrl [SimTalk]

setUpImp. import [SimTalk] - importer

See also

Select Object [for controls]

**Receive Control [set-up importer]**

**Receive Control [set-up importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Receive Control , which sets how the material flow object receives Exporters/Workers .

<!-- image -->

Plant Simulation calls the Receive Control after the Entrance Control of the Workplace and after the Order Control of the Exporter/Worker .

Plant Simulation executes the Receiving Control , when an Exporter/Worker was assigned to an importer .

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard receive control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Receive Control has to define two parameters:

- The parameter Importer type of data type integer designates the type of the importer .
- The parameter Exporters is an array of data type object that contains all brokered Exporters/Workers .

If Exporters/Workers were requested for a part, you have to start carrying away the part with the method startProcessing . You can also model travel times with a wait-instruction before calling the method startProcessing .

SimTalk

setUpImp. ReceiveCtrl [SimTalk]

setUpImp. startSetup [SimTalk]

startProcessing [SimTalk] - importer

See also

Select Object [for controls]

**Release Control [set-up importer]**

**Release Control [set-up importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Release Control , sets how the material flow object releases the Exporters/Workers .

<!-- image -->

Plant Simulation executes the Release Control , when the Exporters/Workers would be released again by default.

When you created an Exit Control and an Importer Release Control , the Importer Release Control is called first, and then the Exit Control is called.

<!-- image -->

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard release control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The Release Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to release the Exporters/Workers with the method releaseExporters .

**SimTalk**

setUpImp. ReleaseCtrl [SimTalk] - importer

setUpImp. releaseExporters [SimTalk]

See also

Select Object [for controls]

###### Sub-tab Failure

**Sub-tab Failure**

**Failure Importer**

Select and enter settings for repairing failures of the machines on the sub-tab Failure .

Only some of the Material Flow and Fluid objects provide the failure importer .

<!-- image -->

To show Importer Statistics , select View &gt; Show Statistics Report in the dialog of the object. You can also click the object with the right mouse button in the Frame and select Show Statistics Report on the context menu or press F6 .

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies when the service is provided by sub-Brokers .

**See also**

Model a Worker Who Repairs a Machine

Model Workers with Importer, Broker, and Exporter

\_Methods of the Importer

\_Attributes of the Importer

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=FSHg8fadhO82vUCh&amp;t=1189](https://youtu.be/HiPziA8kxc0?si=FSHg8fadhO82vUCh&t=1189)

<!-- image -->

**Active [check box] - failure importer**

Active [check box] - failure importer

To activate the failure-importer , select this.

<!-- image -->

Only some of the Material Flow and Fluid objects can then request services for repairing failures.

To deactivate the failure-importer , clear the check box.

SimTalk

failImp. Active [SimTalk] - importer

**Services for Repairing**

To open a table into which you type the names of groups of the different repair services, click this button.

<!-- image -->

You might, for example, type in different names for the different services to group these names.

You can set groups of services which represent an Alternative each. To execute the task repairing , the importer always requires all services of an Alternative . When, for example, the importer does not have all services of Alternative1 , he attempts to get all services of Alternative2 , etc. For successive services in the table, which all belong to the same alternative, the name of the alternative only shows for the first service.

<!-- image -->

- First, click the Inheritance check box so that it looks like this . Only then you can enter data into the list.
- Type the name of the service to be imported into the cells of the column Service .
- Type the amount, i.e., the number of services to be imported, into the cells of the column Amount .
- Type the name of the alternative service, which the importer provides if it cannot meet the previous service, into the cells of the column Alternative . When you want to add a service to an alternative at a later point in time, you can type this service and the name of the Alternative into the last row of the table. When you click Apply , Plant Simulation sorts the list anew and places this service below the respective alternative.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Note**

When the importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

The importer works with the Broker and the Exporter / Worker to assign services to the individual stations.

You can edit the contents of the text boxes with the commands on the context menu of embedded lists.

SimTalk

failImp. getServices [SimTalk] - importer

failImp. setServices [SimTalk] - importer

See also

Context Menu of Embedded Lists

**Can Be Interrupted and Drawn Off [failure importer]**

To allow importers with a higher priority to withdraw Exporters/Workers from this importer , select this check box.

When an importer with higher priority requests services, which the freely available resources cannot fulfill, and when sufficient interruptible importers with lower priority are available, to which the required services are brokered at the moment, then as many interruptible importers are interrupted as required to satisfy the importer with higher priority. The tasks ( processing / setting-up / repairing / transporting ), which the interrupted importer performs, will then be interrupted, and the resources are brokered to the importer with higher priority.

SimTalk

failImp. Interruptible [SimTalk]

Release All Services When One Of Them Is Failed [failure importer]

To make the material flow object release all repair services , when one or more of the repair services is failed or paused, select this check box.

This also applies if a service was interrupted because it was requested by an importer with higher priority.

To only release the failed services , clear it.

This only works, when you also select Fail Services in the dialog of the Exporter . For the Worker Fail services is always implicitly active.

SimTalk

failImp. ReleaseAllServices [SimTalk]

**Priority [failure importer]**

Type in the Priority with which the importer of the object fulfills a request.

<!-- image -->

<!-- image -->

The Priority of an importer is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides a service with Priority 10 before providing a service with Priority 1.

If the importer is not assigned an Exporter immediately after a request, the importer will be entered in the list of unsatisfied requests of the Broker that is arranged according to priority.

SimTalk

failImp. Priority [SimTalk] - importer

**Broker [failure importer]**

**Broker [failure importer]**

Click the ellipsis button and select the Broker , which assigns the repair service .

<!-- image -->

By default, Plant Simulation enters root.Broker . If Plant Simulation detects an invalid Broker during the simulation, it opens the dialog of the object with the respective sub-tab.

**Note**

For Broker hierarchies Plant Simulation only calls the control of this Broker , not the controls of any existing sub-Brokers .

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

Or select the Broker in a Frame , drag it to the text box and drop it there.

SimTalk

failImp. BrokerPath [SimTalk] - importer

**Request Control [failure importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Request Control , which sets how the material flow object requests Exporters/Workers for repairing the machine.

<!-- image -->

Plant Simulation executes the Request Control , when the object changes to the Failed state. When you entered the control, you have to make sure that the required Exporters/Workers are requested within the control.

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard request control looks like this:

<!-- image -->

**Parameter**

The Request Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to request the Exporters/Workers with the method import .

SimTalk

failImp. RequestCtrl [SimTalk]

failImp. import [SimTalk] - importer

See also

Select Object [for controls]

**Receive Control [failure importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Receive Control , which sets how the material flow object receives Exporters/Workers for repairing the machine.

<!-- image -->

The Receive Control is called after the Entrance Control of the Workplace and after the Order Control of the Exporter/Worker .

Plant Simulation executes the Receiving Control , when an Exporter/Worker was assigned to the failureimporter .

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .

**Receive Control [failure importer]**

- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard receive control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Receive Control has to define two parameters:

- The parameter Importer type of data type integer designates the type of the importer .
- The parameter Exporters is an array of data type object that contains all brokered Exporters/Workers . If Exporters/Workers were requested for a part, you have to start carrying away the part with the method

startProcessing . You can also model travel times with a wait-instruction before calling the method startProcessing .

**SimTalk**

failImp. ReceiveCtrl [SimTalk]

failImp. startProcessing [SimTalk] - importer

failImp. stopProcessing [SimTalk]

See also

Select Object [for controls]

**Release Control [failure importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Release Control , which sets how the material flow object releases the Exporters/Workers .

<!-- image -->

Plant Simulation executes the Release Control , when the Exporters/Workers would be released again by default.

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

###### Sub-tab Transport

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard release control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The Release Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to release the Exporters/Workers with the method releaseExporters .

SimTalk

failImp. ReleaseCtrl [SimTalk] - importer

failImp. releaseExporters [SimTalk]

See also

Select Object [for controls]

Sub-tab Transport

Transport Importer

To make the Worker pick up and carry parts, which are ready to leave the station, to the destination object, activate the transport importer .

To define a Loading Time and/or an Unloading Time , type them into the Workplace attached to the station.

While the Worker picks up parts, he is brokered to the station. Mediation ends, as soon as the Worker leaves the Workplace to carry the part to the Destination . While the Worker carries parts, the service still is assigned, but no longer brokered.

<!-- image -->

Select the Broker , select if the Worker Can Be Interrupted and Drawn Off [transport importer] , type the required Services into the services list, and type in the Priority with which the importer requests these services. If a Worker can carry several parts, he waits for parts until his carrying capacity is reached. To prevent the Worker from waiting for too long for additional parts to arrive, type in the Maximum Dwell Time [transport importer] . After it has passed, he walks to the target station, the MU Target , and puts the part down. The Worker evaluates the Part Targets and walks to the closest one first. At the target station, he places all parts destined for this station. If he carries additional parts, he evaluates the next target and walks to the closest one, etc.

**Note**

If you neither type in a MU Target here nor a Destination in the MU , the object uses the Strategy which you selected on the tab Exit . This only works if you inserted Connectors to the possible destinations.

If the carrying capacity of the Worker is exhausted, the destination is determined according to the selected Exit Strategy . For a capacity of greater than 1 only for the first MU a destination is determined. Once he places the first MU , a destination is determined for the next MU . If the strategy is non-blocking and if no successor can take on the MU , the Worker remains at the loading station or at the last unloading station and the part is entered into the Blocking List of all possible destinations. As soon as a destination is available, the Worker walks to this station.

When the MU has a route to the destination, the Worker does not directly carry the MU to the destination, but to the next object on this route.

At the end of his shift the Worker walks back to his WorkerPool and deposits the parts he could not deliver into the Parts Buffer , which you assigned to the WorkerPool . If you did not assign a parts buffer to the WorkerPool , Plant Simulation shows a warning and stops the simulation.

If you activated the transport importer in the parts buffer , one of the available Workers carries the parts in the parts buffer to the destination object, after the next shift has started. If you did not activate the transport importer , the parts in the parts buffer are moved on according to the Exit Strategy which you selected for the parts buffer .

To send a Worker to a specific station, you can use the methods goTo and goToPool . To change the services for an available Worker , you can use the attribute Services .

To show Importer Statistics , select View &gt; Show Statistics Report in the dialog of the object. You can also click the object with the right mouse button in the Frame and select Show Statistics Report on the context menu or press F6 .

To make the Transport Importer request a Worker for a part that is ready to exit the object only if the destination object is ready to accept it, select Wait for Free Target [transport importer] . To make the Transport Importer request a Worker immediately, clear the check box.

<!-- image -->

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies when the service is provided by sub-Brokers .

See also Select Object [for controls] Active [check box] - transport importer Model Workers with Importer, Broker, and Exporter Model Workers and the Jobs They Do Configure the Objects that Produce and Process Parts \_Methods of the Importer \_Attributes of the Importer Video on YouTube https://youtu.be/HiPziA8kxc0?si=fCggWItWi0soTBxq&amp;t=314

**Active [check box] - transport importer**

Active [check box] - transport importer

To activate the transport importer , select this check box.

<!-- image -->

The Worker then picks up and carries parts, which are ready to leave the station, to the destination object.

To deactivate the transport importer , clear the check box.

Only some of the Material Flow and Fluid objects provide the transport importer .

SimTalk

transportImp. Active [SimTalk] - importer

**Services for Carrying Parts Away [transport importer]**

To open a list, into which you type the names of one or several services, click this button.

<!-- image -->

If a part it to be carried away from the station, it requests a Worker who provides this service or one of the services you typed in. If you typed in several services, the station searches for the Worker in the order in which you typed the services into the list.

<!-- image -->

If you want the Worker to provide additional services, you can type these services into the Workers to Create table of the WorkerPool .

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**Note**

First, click the Inheritance check box so that it looks like this . Only then you can type data into the list.

You can edit the contents of the text boxes with the commands on the context menu of embedded lists.

SimTalk transportImp. getServices [SimTalk] - importer transportImp. setServices [SimTalk] - importer See also Context Menu of Embedded Lists

Can Be Interrupted and Drawn Off [transport importer]

To allow importers with a higher priority to withdraw resources, i.e., Workers from this importer , select this check box.

The Worker then abandons the current task and takes care of the task that is more important.

When an importer with higher priority requests services, which the freely available resources cannot fulfill, and when sufficient interruptible importers with lower priority are available, to which the required services are brokered at the moment, then as many interruptible importers are interrupted as required to satisfy the importer with higher priority. The tasks ( processing / setting-up / repair / transport ), which the interrupted importer performs, will then be interrupted and the resources are brokered to the importer with higher priority.

SimTalk

transportImp. Interruptible [SimTalk]

**Wait for Free Target [transport importer]**

Wait for Free Target [transport importer]

To make the transport importer request a Worker for a part that is ready to exit the object only if the destination object is ready to accept it, select this check box.

To make the transport importer request a Worker immediately, clear the check box.

Activating Wait for Free Target prevents a Worker from carrying parts to a Station , Store or Buffer , that is already occupied or reserved. The Worker thus is available for jobs that can be done at the moment.

Plant Simulation enters the part that cannot be transported into the Forward Blocking List of the destination object.

SimTalk

WaitForFreeTarget [SimTalk] - transport importer

ReservedFor [SimTalk]

ReservedPlace [SimTalk] of the MUs

contentsAndReservedList [SimTalk]

See also

Model a Worker Who Waits for a Free Target

Video on YouTube

https://youtu.be/HiPziA8kxc0?si=fCggWItWi0soTBxq&amp;t=314

https://youtu.be/HiPziA8kxc0?si=T\_9OmpKGD36jFkY9&amp;t=788

**Priority [transport importer]**

Type in the Priority with which the importer of the object fulfills a request.

<!-- image -->

<!-- image -->

The Priority of an importer is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides a service with Priority 10 before providing a service with Priority 1.

If the importer is not assigned an Exporter immediately after a request, the importer will be entered in the list of unsatisfied requests of the Broker that is arranged according to priority.

SimTalk

transportImp. Priority [SimTalk] - importer

**Broker [transport importer]**

**Broker [transport importer]**

Click the ellipsis button and select the Broker , who assigns the transport services to the Worker , for example .Models.Model.MyBroker .

<!-- image -->

By default, Plant Simulation enters root.Broker . When Plant Simulation detects an invalid Broker during the simulation, it opens the dialog of the object with the respective sub-tab.

Or select the Broker in a Frame , drag it to the text box and drop it there.

**Note**

For Broker hierarchies Plant Simulation only calls the control of this Broker , not the controls of any existing sub-Brokers .

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

**SimTalk**

transportImp. BrokerPath [SimTalk] - importer

**Request Control [transport importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Request Control , which sets how the material flow object requests Workers for carrying away the MUs .

<!-- image -->

Plant Simulation executes the Request Control , when processing is finished and when the part is ready to be carried away. If you enter a control, you have to make sure within the control that the required Workers are requested.

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

**Request Control [transport importer]**

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard request control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The Request Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to request the Workers with the method import .

SimTalk

transportImp. RequestCtrl [SimTalk]

transportImp. import [SimTalk] - importer

See also

Select Object [for controls]

**Receive Control [transport importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Receive Control , which sets how the material flow object receives Workers .

<!-- image -->

The Receive Control is called after the entrance control of the Workplace and after the order control of the Exporter/Worker .

Plant Simulation executes the Receiving Control , when a Worker was assigned to the transport importer .

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

**Receive Control [transport importer]**

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard receive control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Receive Control has to define two parameters:

- The parameter Importer type of data type integer designates the type of the importer .
- The parameter Exporters is an array of data type object that contains all brokered Exporters/Workers .

If Exporters/Workers were requested for a part, you have to start carrying away the part with the method startProcessing . You can also model travel times with a wait-instruction before calling the method startProcessing .

**SimTalk**

transportImp. ReceiveCtrl [SimTalk]

transportImp. startProcessing [SimTalk] - importer

startProcessing [SimTalk] - importer

See also

Select Object [for controls]

**Release Control [transport importer]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Release Control , which sets how the material flow object releases the Workers .

<!-- image -->

Plant Simulation executes the Release Control , when the Workers would be released again by default.

**Note**

The Request Control , the Receive Control , and the Release Control are not called when you reset the simulation .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard release control looks like this:

<!-- image -->

**Parameters**

The Release Control has to define the parameter Importer type of data type integer , which designates the type of the importer . You have to release the Workers with the method releaseExporters .

SimTalk

transportImp. ReleaseCtrl [SimTalk] - importer

transportImp. releaseExporters [SimTalk]

releaseExporters [SimTalk]

See also

Select Object [for controls]

**MU Target**

Click the ellipsis button and select the MU Target to which the Worker carries the part in the dialog Select Object .

<!-- image -->

The MU Target is either the Workplace attached to the work station, which processes the part next and to which the Worker carries the part, or the work station itself.

**Note**

If you neither type in a MU Target here nor a Destination in the part, the object uses the Strategy which you selected on the tab Exit for determining the target of the part.

**Note**

If you type in a MU target the Worker carries all parts to this target.

If you do not type in a MU target , the Dismantle Table or the setting Main MU to Successor with Number determine it.

SimTalk

MUTarget [SimTalk]

See also

Worker [object]

Select Object [for controls]

**Maximum Dwell Time [transport importer]**

Maximum Dwell Time [transport importer]

Select a distribution, and enter the values, which that distribution requires, into the text box. Plant Simulation shows these values below the text box.

<!-- image -->

You can also type in a constant time ( Const ).

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the Worker for whom the Maximum Dwelling Time applies.

The Maximum Dwelling Time is the time during which the Worker waits for the parts which he is to carry to the target station. Once this time has passed, he walks to the target station, no matter if his carrying capacity is reached or not. The Worker picks up the parts which the station finished processing within the Maximum Dwelling Time .

**Note**

If you want the Worker to wait until he can pick up all parts up to his carrying capacity, enter a very long time.

SimTalk

MaxDwellTime [SimTalk]

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=tx1MOqgt0BsmOuxB&amp;t=693](https://youtu.be/HiPziA8kxc0?si=tx1MOqgt0BsmOuxB&t=693)

Tab Energy

Tab Energy [general description]

Type in the settings pertaining to the power input and to the transition times from one energy state to another on the tab Energy .

Only the active material flow objects offer energy settings and that the length-oriented objects do not provide the states setting-up and standby .

<!-- image -->

**Note**

If a machine changes to the state Failed a powering up/down process will be canceled and the machine changes to the state Failed without using any time at all. At the end of the failure the machine instantaneously changes to the energy state Operational .

**Note**

The states of a machine are not always directly comparable to the resource states of the machine. The values of the resource states refer to the statistics collection period while the values for the energy states refer to the total energy consumption.

To check the statistics values of the energy states, click Energy Statistics on the Tab

Statistics .

###### Tab Energy [general description]

<!-- image -->

To view Energy Statistics - Energy Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or select View &gt; Show Statistics Report .

See also

Simulate the Power Consumption in Your Facility

\_Read-Only Attributes for Energy Statistics

\_Attributes for the Energy Simulation

**Active [check box] - energy**

To activate the energy features, select this check box.

<!-- image -->

Then you can type in values and/or select the available settings.

Click Apply to activate the settings.

To deactivate the energy features, clear the check box.

SimTalk

EnergyActive [SimTalk]

Power Input

Power Input

Plant Simulation provides the following Power Input options:

<!-- image -->

They are listed in the table of contents to the left.

**Working [energy]**

**Working [energy]**

Type in the power input in kilowatts for the machine while it is working.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

PowerInputWorking [SimTalk]

**Setting-up [energy]**

Type in the power input in kilowatts for the machine when it is setting-up for a part type.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

PowerInputSettingUp [SimTalk]

**Operational [energy]**

**Operational [energy]**

Type in the power input in kilowatts for the machine when it is operational, for example, when it is waiting for a part.

You can type in a value of data type real or a formula.

SimTalk

PowerInputOperational [SimTalk]

**Failed [text box] - energy**

Type in the power input in kilowatts for the machine when it is failed.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

PowerInputFailed [SimTalk]

**Standby**

**Standby**

Type in the power input in kilowatts for the machine when it is on standby.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

PowerInputStandby [SimTalk]

Off Type in the power input in kilowatts for the machine when it is off.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

PowerInputOff [SimTalk]

Transition Times

Transition Times

Plant Simulation provides the following options for Transition Times :

<!-- image -->

They are listed in the table of contents to the left.

All other energy transitions are instantaneous, i.e., they are executed without taking up any time at all. The station immediately switches to the energy state Operational at the end of a failure.

**Operational to Off**

**Operational to Off**

Type in the transition time which passes when the object changes its energy state from operational to off.

You can type in a value of data type real or a formula.

SimTalk

TransitionTimeOperationalToOff [SimTalk]

**Off to Operational**

Type in the transition time which passes when the object changes its energy state from off to operational.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

TransitionTimeOffToOperational [SimTalk]

**Operational to Standby**

**Operational to Standby**

Type in the transition time which passes when the object changes its energy state from operational to standby.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

TransitionTimeOperationalToStandby [SimTalk]

**Standby to Operational**

Type in the transition time which passes when the object changes its energy state from standby to operational.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

TransitionTimeStandbyToOperational [SimTalk]

**Standby to Off**

**Standby to Off**

Type in the transition time which passes when the object changes its energy state from standby to off.

<!-- image -->

You can type in a value of data type real or a formula.

SimTalk

TransitionTimeStandbyToOff [SimTalk]

**Off to Standby**

Type in the transition time which passes when the object changes its energy state from off to standby.

<!-- image -->

You can specify a value of data type real or a formula.

SimTalk

**TransitionTimeOffToStandby [SimTalk]**

State Transition

###### State Transition

To open the dialog in which you can select the state transition settings at the Start and the End of a Pause and if you want to Power Up Early [energy pause] or not.

You can also select the state transition settings at the Start and the End of the Unplanned state and if you want to Power Up Early [energy unplanned] or not.

<!-- image -->

Pause

**Pause [energy]**

Select the state transition settings at the Start and the End of a pause and if you want to Power Up Early [energy pause] or not.

<!-- image -->

**Start [energy pause]**

Select the energy state transition at the start of a pause of the object.

You can select Standby , No change , or Off

<!-- image -->

**SimTalk**

EnergyPauseStartState [SimTalk]

**End [energy pause]**

**End [energy pause]**

Select the energy state transition at the end of a pause of the object.

You can select Previous state , Operational , Standby , or No change .

The previous state is the state the object was in before the pause.

<!-- image -->

**SimTalk**

EnergyPauseEndState [SimTalk]

**Power Up Early [energy pause]**

To power the object up early during a pause so that the machine has the correct energy state at the end of the pause, select this check box.

<!-- image -->

Clear the check box to start powering up at the end of the pause.

**Note**

If you select the check box, the machine powers up/down while the machine is paused. Therefore, the powering up/down time is part of the paused time .

**SimTalk**

EnergyPausePowerUpEarly [SimTalk]

**Unplanned**

**Unplanned [energy]**

Select the state transition settings at the Start and the End of the Unplanned state and if you want to Power Up Early [energy unplanned] or not.

<!-- image -->

**Start [energy unplanned]**

**Start [energy unplanned]**

Select the energy state transition at the start of the unplanned state of the object.

You can select Standby , No change , or Off .

<!-- image -->

**SimTalk**

EnergyUnplannedStartState [SimTalk]

**End [energy unplanned]**

Select the energy state transition at the end of the unplanned phase of the object.

You can select Previous state , Operational , Standby , or No change .

The previous state is the state the object was in before the unplanned phase.

<!-- image -->

**SimTalk**

EnergyUnplannedEndState [SimTalk]

**Power Up Early [energy unplanned]**

**Power Up Early [energy unplanned]**

To power the object up early during an unplanned phase so that the machine has the correct energy state at the end of that phase, select this check box. Clear the check box to start powering up at the end of the unplanned phase.

<!-- image -->

**Note**

If you select the check box, the machine powers up/down while the machine is unplanned. Therefore, the powering up/down time is part of the unplanned time .

**SimTalk**

EnergyUnplannedPowerUpEarly [SimTalk]

###### State

The drop-down list shows the current energy state of the object. When the object is powering up or down, Plant Simulation shows the start state and the end state.

You can also select the target energy state of the object, provided it is not failed .

- If the current energy state is Operational , Standby , or Off , the list shows the states Operational , Standby , and Off .

After you select another state, the energy transition uses the time, which you set under Transition Times .

- If the current energy state is Setting-up or Working , the list shows the current energy state, plus Standby and Off .
- After you select another state, the current state is interrupted, resulting in the state Operational . (This process does not use up any time.) Then the power transition uses the time which you entered under Transition Times .

After you select another state and click Apply , the display changes accordingly, compare the example below.

<!-- image -->

**SimTalk**

EnergyCurrentState [SimTalk]

EnergyTargetState [SimTalk]

###### LEDs and States of the Energy Features

During the simulation runs Plant Simulation shows the energy states in 2D as a colored dot in the LED display along the upper border of the icon in the Frame .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Energy State                                    | LED        | Looks like this   |
|-------------------------------------------------|------------|-------------------|
| The material flow object is failed .            | red        |                   |
| The material flow object is working .           | green      |                   |
| The material flow object is setting up .        | brown      |                   |
| The material flow object is powering up/ down . | purple     |                   |
| The material flow object is on standby .        | light gray |                   |
| The material flow object is off .               | dark gray  |                   |

3D shows the states, that correspond to the LEDs in 2D, in the State Graphic .

See also

States &gt; State Graphic

States &gt; Orientation [state graphic] &gt; Color in the dialog Edit 3D Properties of the object

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Exporter

LEDs and States of the Method

Tab Costs

Tab Costs [material flow objects]

Type in the settings for costs, which accrue for the active material flow objects and for Part and Container on the tab Costs .

You can define costs settings for these objects:

- The active material flow objects AngularConverter , AssemblyStation , Buffer , Converter , Conveyor , DismantleStation , ParallelStation , PickAndPlace -robot, PlaceBuffer , Sorter , Station , Store , Turnplate , and Turntable .
- The moving objects Part and Container .

<!-- image -->

The CostAnalyzer runs the actual cost analysis.

See also

Active and Passive Objects

Simulate the Accrued Costs of the Machines

\_Attributes for Simulating Costs

Tab Costs [MUs]

###### Active [check box] - costs, material flow objects

Active [check box] - costs, material flow objects

To turn costs settings of the active material flow objects on, select this check box.

<!-- image -->

To turn them off, clear the check box.

The inheritance check box also turns inheritance of the other settings on the tab off or on.

SimTalk

CostingActive [SimTalk] - material flow objects

###### Depreciation Period [text box]

Type in the Depreciation Period in years over which the depreciation amount is distributed with write-offs.

<!-- image -->

Note

The total investment costs are the sum of the Investment Costs [text box] and the Investment Costs per Length [text box] which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period and then do not accrue anymore.

SimTalk

DepreciationPeriod [SimTalk]

**Investment Costs [text box]**

###### Investment Costs [text box]

Type in the Investment Costs of the machine which accrue for purchasing the machine.

<!-- image -->

The Investment Costs include the purchasing price of the machine, transporting costs, sales tax, etc.

**Note**

The total investment costs are the sum of the Investment Costs and the Investment Costs per Length [text box] which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period [text box] and then do not accrue anymore.

SimTalk

InvestmentCosts [SimTalk]

###### Investment Costs per Length [text box]

Type in the Investment Costs per Length of the Conveyor .

The Investment Costs per Length designate the investment costs per meter of the Conveyor . A conveyor system usually consists of several segments for which costs per length accrue.

**Note**

The total investment costs are the sum of the Investment Costs [text box] and the Investment Costs per Length which result from the actual length of an inserted instance of the Conveyor .

The total investment costs are distributed across the Depreciation Period [text box] and then do not accrue anymore.

SimTalk

InvestmentCostsPerLength [SimTalk]

**Operating Costs [text box]**

###### Operating Costs [text box]

Type in the Operating Costs of the machine per year.

<!-- image -->

Operating costs are, among others, electricity, maintenance, building rent, etc.

**Note**

The total operating costs are the sum of the Operating Costs and the Operating Costs per Length [text box] which result from the actual length of an inserted instance of the Conveyor .

SimTalk

OperatingCosts [SimTalk]

Operating Costs per Length [text box]

Type in the Operational Costs per Length of the Conveyor .

They designate the operating costs per meter of the Conveyor and are entered in € per year times meter. Operating Costs are, among others, electricity, maintenance, building rent, etc.

Note

The total operating costs are the sum of the Operating Costs [text box] and the Operational Costs per Length which result from the actual length of an inserted instance of the Conveyor .

Note

Operational Costs per Length only apply to the Conveyor .

SimTalk

OperatingCostsPerLength [SimTalk]

Tab User-defined

User-defined Attributes [general description]

Add user-defined attributes that meet your modeling needs and edit or delete them on the Tab Userdefined Attributes .

These user-defined attributes , also called attribute methods , do not affect the built-in properties of the Plant Simulation objects.

The list field shows the Name , the Value , and the Data Type of the user-defined attributes you are going to define or already did define.

If you add the value of the user-defined attribute to the instance of the object you inserted into a Frame , it shows an asterisk * in the column Created Here .

If the user-defined attribute inherits its value from the class, it shows an asterisk * in the column Inherited .

<!-- image -->

- To create a user-defined attribute , click New .
- To edit a user-defined attribute , select it in the list field and click Edit or double-click it in the cell Name the list field.
- To delete a user-defined attribute , select it in the list field, and click Delete .
- To show a user-defined attribute in a 3D Only model , select View &gt; Show Object Names &gt; Show User-defined Attributes .

For user-defined attributes of data types method , list , queue , stack , and table you can:

- Double-click the respective cell in the column Name to open the user-defined attribute .

<!-- image -->

**Show User-defined Attributes in 3D**

To show a user-defined attribute in your 3D Only model :

- Select Show in 3D to show the user-defined attribute in your 3D model.
- Double-click the respective cell in the column Value to open the object instead of the user-defined attribute . In the figure above you can double-click the local variables in the first three rows to open the respective local variable.

<!-- image -->

Double-click Method or DataTable in the column Value to open the window of the Method or DataTable that you inserted into the model frame.

<!-- image -->

Hold down Ctrl and double-click Method or DataTable in the column Value to select the Method or DataTable in the model frame. If the model frame is closed, Plant Simulation opens it.

<!-- image -->

In a 3D Only model you can double-click the Type Graphic on the left side of the label to open the window of the Method or of the list object . Then select Transformation and Display settings.

<!-- image -->

Double-click the label with the name of the Method/list object to open the dialog of the object to which the user-defined attribute belongs. Then, change to the Tab User-defined . It is faster though to right-click the label and select Edit User-defined Attributes . This opens the settings directly.

<!-- image -->

Keyboard Keys in the List of User-defined Attributes

You can use these keyboard keys in the list of user-defined attributes:

- Press Return to open the dialog User-defined Attributes . Here you can then change the settings.

###### New User-defined Attribute

- Press Insert to create a new user-defined attribute.
- Press Delete to delete the selected user-defined attribute . Clear the check box Confirm under File &gt; Preferences &gt; Modeling &gt; Delete objects to delete the attribute without prompting you to confirm.
- Press F2 to open the window of a user-defined attribute of data type object , method , table , list , stack , or queue after you clicked in the text box of the user-defined attribute .

You can also create user-defined attributes with SimTalk commands.

See also

New [user-defined attribute]

Create a User-defined Attribute Manually

Create a User-defined Attribute During the Simulation

Show in 3D [user-defined attribute]

Create a Tooltip as a User-defined Attribute in 3D

Undo [3D]

Redo [3D]

\_Methods of User-defined Attributes

Miscellaneous Methods of User-defined Attributes

\_Attributes of User-defined Attributes

New User-defined Attribute

New [user-defined attribute]

To create a user-defined attribute , click New .

<!-- image -->

Define the settings for your user-defined attribute on the Tab Value , the Tab Transformation , the Tab Display , and on the Tab Statistics .

**Note**

The tabs Transformation and Display are only available in a 3D Only model .

- Type in the Name of the user-defined attribute . The name has to be unique, i.e., no other built-in or user-defined attribute or method may have the same name!
- Select if you want to Show the user-defined attribute in 3D . Plant Simulation shows it in the Inside Representation of the object. If you select Show Externally on

the Tab Display it also shows it in the Outside Representation of the object.

- Select the Data Type of the user-defined attribute / Variable , compare Data Types .
- Type in a Value that is compatible with this data type you selected. For certain data types you can select a value from a drop-down list.

When using the data type time with a random distribution, select the data type randtime . You have to initialize the value for randtime with the method rollDice before accessing it. For user-defined attributes of data type time you can only enter a constant value.

- Select settings for the Transformation of the user-defined attribute in 3D Select Display Settings for the user-defined attribute in 3D .
- .
- Create a user-defined attribute of data type method which will be part of the object. Compare Entrance Control and self .

Click Open and enter your source code into the Method that opens. When you selected one of the list data types, enter data into the list or table that opens.

To open a user-defined attribute of data type Method or Table , add it to the list of Favorites and double-click it in the list on the tab.

- Create a user-defined attribute of data type string and name it Tooltip to create a tooltip for the object. Select Show in 3D to show this tooltip in 3D .
- To insert the user-defined attribute and close the dialog, click OK . Plant Simulation places the attribute at the correct alphabetical order in the list.

To apply the settings you entered and leave the dialog open, click Apply .

To discard your actions so far, click Cancel .

This table lists where the relative path starts for the different objects:

| Object                                                                           | Relative path starts in                                              |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Built-in or user-defined attribute of data type object in a material flow object | the Frame which contains the material flow object.                   |
| Built-in or user-defined attribute of data type object in a MU                   | the parent Frame of the material flow object which contains the MU . |

**New [user-defined attribute]**

| Object                                                                                    | Relative path starts in                                                                 |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Built-in or user-defined attribute of data type object in a Frame                         | the Frame itself.                                                                       |
| Source code of a Method or of a user-defined attribute of data type method                | the Frame which contains the Method or the object which has the attribute.              |
| DataTable or user-defined attribute of data type table , with columns of data type object | the Frame which contains the DataTable or in the parent object which has the attribute. |
| User-defined attribute of data type table of a MU , with columns of data type object      | the Frame in which the MU is located.                                                   |
| WorkerPool                                                                                | the Frame in which the Worker is located.                                               |

**SimTalk**

createAttr [SimTalk]

deleteAttr [SimTalk]

getAttrName [SimTalk]

getAttrNo [SimTalk]

getAttrType [SimTalk]

getAttrValue [SimTalk]

setAttrValue [SimTalk]

See also

Create a User-defined Attribute Manually

Create a Tooltip as a User-defined Attribute in 3D

Create a User-defined Attribute During the Simulation

Create User-defined Attribute

\_Methods of User-defined Attributes

Miscellaneous Methods of User-defined Attributes

\_Attributes of User-defined Attributes

<!-- image -->

Name [user-defined attribute]

Type in the Name of the user-defined attribute .

The name has to be unique, i.e., no other built-in or user-defined attribute or method may have the same name!

SimTalk

Name [SimTalk] - user-defined attribute

**Show in 3D [user-defined attribute]**

To show the user-defined attribute of the object in 3D , select this check box. To hide the user-defined attribute in 3D , clear the check box.

<!-- image -->

To show the user-defined attributes in 3D , make sure that is selected as well.

Plant Simulation inserts and shows the user-defined attributes in the order in which you create them.

Select where and how Plant Simulation shows them in 3D on the tabs Transformation and Display .

User-defined attributes of the data types table , list , stack , queue , and method show a type graphic resembling their icon to the left of their name in 3D . Plant Simulation always shows user-defined attributes that have type graphics , even if Show Externally is cleared.

<!-- image -->

Click the Station with the right mouse button and select Open in 3D to open the Station in its own 3D window.

<!-- image -->

**In this window you can:**

- Double-click the Label of a user-defined attribute that does not have a Type Graphic to open its dialog.

<!-- image -->

Instead, you can also right-click the user-defined attribute and select Open Dialog on the context menu.

<!-- image -->

- Double-click the Label of a user-defined attribute that does have a Type Graphic to open its dialog.

<!-- image -->

Instead, you can also right-click the user-defined attribute and select Open Dialog on the context menu.

<!-- image -->

- You can also select Open Dialog or Open Window on the sub-context menu of the object.
- Double-click the Type Graphic of a user-defined attribute that does have a Type Graphic to open the window of the list object or of the Method .

<!-- image -->

<!-- image -->

Instead, you can also right-click the user-defined attribute and select Open Window on the context menu.

- Double-click the Type Graphic of a user-defined attribute of data type boolean to switch it on and off.
- Select Run on the context menu of a user-defined attribute of data type method to run the source code of the Method .

<!-- image -->

<!-- image -->

If the Method is being executed at the moment, you can also select Open Debugger .

SimTalk

ShowIn3D [SimTalk] - user-defined attribute

**Tab Value**

Tab Value [user-defined attribute]

**On the Tab Value you can:**

- Select the Data Type of the user-defined attribute .
- Select or enter the Value of the attribute, depending on the data type.
- Type in the Initial Value of the attribute for some data types.

**Data Type [user-defined attribute]**

Select the data type of the user-defined attribute from the drop-down list Data Type .

You can use any of the supported Data Types .

<!-- image -->

User-defined Attribute of Data Type randtime

For the data type time with random numbers, we recommend to use the data type randtime . For the data type time you can only type in constant values!

You can then, depending on the data type, select the Value from the drop-down list or type it into the text box.

For the Data Types &gt; real , length , weight , time , speed , and acceleration you can type in the number of Decimal Places and Integer Places .

Random Seed Value for User-defined Attributes of Data Type method and randtime

Plant Simulation keeps a common seed value in the object. Plant Simulation automatically assigns the random number value when inserting an object, but only if the object can create random numbers. This is then the case when the object itself can create random numbers, for example a Station for its Processing Time , or when the object has a user-defined attribute of data type Method or RandTime . If both is not the case, Plant Simulation assigns the value 0 to the attribute RandomSeed when inserting the object. If the value of the attribute RandomSeed is 0, the attribute will not be shown in the window Show Attributes and Methods and will not be written to the folder model. When you create a user-defined attribute of data

type Method or RandTime for such an object, Plant Simulation sets a random number value automatically as well.

SimTalk

DataType [SimTalk] - user-defined attribute

setAttrType [SimTalk]

getAttrValue [SimTalk]

See also

Methods of the Distributions

RandomSeed [SimTalk] - Method/User-defined Attribute

**Value [user-defined attribute]**

**Value [user-defined attribute]**

After you selected the data type, you can set the value, depending on the data type.

- Select a value from the drop-down list Value .
- Type the value into the text box.
- Type in values into the list which the Open button opens.

<!-- image -->

Unshare a User-defined Attribute

If the user-defined attribute points to a list which is referenced from additional places/objects, the dialog shows the button Unshare .

Click Unshare to make Plant Simulation assign its own copy of the list to the user-defined attribute instead of the shared contents of the list. This corresponds to the method unshare .

<!-- image -->

**SimTalk**

DataType [SimTalk] - user-defined attribute

setAttrValue [SimTalk]

getAttrValue [SimTalk]

See also

Data Type [user-defined attribute]

Value [Variable] &gt; Unshare, Variable

unshare [SimTalk]

Unshare a List or Data Table

**Initial Value [user-defined attribute]**

**Initial Value [user-defined attribute]**

To reset a value, which the user-defined attribute recorded during the simulation run, to an Initial Value , select this check box.

<!-- image -->

Plant Simulation resets the value during the reset and the init phase of the next simulation run.

After you selected the check box, the user-defined attribute shows a text box.

Type in the Initial Value for the next simulation run.

**Note**

For the data types table , list , stack , queue , randtime , and method you cannot specify an initial value .

**SimTalk**

HasInitValue [SimTalk] - user-defined attribute

getAttribute [SimTalk] - user-defined attribute

InitValue [SimTalk] - user-defined attribute

**Tab Transformation**

Transformation [user-defined attribute]

Define the following for the user-defined attribute which it shows in 3D on the Tab Transformation .

- Settings for the Position
- Settings for the Rotation
- Settings for the Scale

**Note**

The Tab Transformation is only available in a 3D Only model .

To define the settings, you can type a value into the text boxes or click in them and roll the mouse wheel. The settings here allow you exact control, as compared to modifying the position, the angle of rotation, and the scale of the object in the scene window with the mouse.

<!-- image -->

- To apply and show your changes of the settings to the selected user-defined attribute , click Apply .
- To apply your changes of the settings to the selected user-defined attribute and to close the dialog, click OK .
- To close the dialog without applying any of the settings you modified, click Cancel .

**See also**

Move an Object Precisely

**Settings for the Position [user-defined attribute]**

To move the position of the selected user-defined attribute on the x-axis, the y-axis, and the z-axis within the coordinate system of the object to which it belongs type in the respective values.

- To move the user-defined attribute by 0.1 meters, hover over the respective text box and roll the mouse wheel.
- To move the user-defined attribute by 0.01 meters, hover over the respective text box, hold down Ctrl , and roll the mouse wheel.
- Type in a value into the respective text box.

<!-- image -->

The inheritance check box turns inheritance of the Position Settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you enter only applies to the attribute of this object.

**SimTalk**

Position [SimTalk] - user-defined attribute

**Settings for the Rotation**

Settings for the Rotation [user-defined attribute]

To set the axis around which to rotate the user-defined attribute , type in a value for each of the three components (x-y-z) that define the rotation axis.

<!-- image -->

Instead, you can also click this button to the right of the axis to set the respective rotation axis. Plant Simulation then enters the respective values into the text boxes.

<!-- image -->

**Angle of Rotation**

Type the angle of rotation in degrees into the text box.

Add Rotation

To add a rotation angle to the axis that you select, click Add Rotation .

Inheritance

<!-- image -->

The inheritance check box turns inheritance of the Rotation Settings off or on.

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you enter only applies to the attribute of this object.

SimTalk

Rotation [SimTalk] - user-defined attribute

See also

Rotate an Object with Keyboard Keys

**Add Rotation**

To add a rotation angle to the axis that you select, click this button.

<!-- image -->

<!-- image -->

Type in the Angle which you would like to add to the Axis that you select.

Select the Axis to which you would like to add the Angle .

Click OK to accept the values and to add the angle to the existing Angle .

Click Cancel to cancel your changes and to close the dialog.

**Settings for the Scale [user-defined attribute]**

Settings for the Scale [user-defined attribute]

To apply uniform scaling of the user-defined attribute , accept the default setting.

This setting automatically enters the value which you typed into one text box into the remaining two text boxes for scaling the object.

This way you do not have to manually type the same value into each text box over again.

<!-- image -->

To Scale the object on each axis separately, clear Uniform .

<!-- image -->

You can set the three components (x,y,z) with which the object is going to be scaled as follows:

- To scale the object by 0.1 meters, hover over the respective text box and roll the mouse wheel.
- To scale the object by 0.01 meters, hover over the respective text box, hold down Ctrl , and roll the mouse wheel.
- Type in a value into the respective text box.

You can only type in values. Typing in 0.5 , for example, halves the size of the object on the respective axis, entering 2.0 doubles its size on the respective axis.

Inheritance The inheritance check box turns inheritance of the Scale Settings off or on.

<!-- image -->

- A green check box means that inheritance is turned on. Then the object inherits, i.e., uses, settings of the parent object from which it was derived. When you change the settings of the parent object, Plant Simulation also changes the respective settings of the child object.
- An orange check box with a minus means that inheritance is turned off. The value you enter only applies to the attribute of this object.

SimTalk

Scale [SimTalk] - user-defined attribute

Tab Display

Tab Display [user-defined attribute]

On the tab Display you can select how Plant Simulation shows the user-defined attribute in 3D .

Note

The Tab Display is only available in a 3D Only model .

It provides the settings listed in the table of contents to the left.

**Font Size [user-defined attribute]**

Select the Font Size for displaying the user-defined attribute in 3D .

<!-- image -->

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. Font [SimTalk] - user-defined attribute

**Font Color [user-defined attribute]**

To select the color with which Plant Simulation shows the user-defined attribute in 3D , click the dropdown arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

&lt;UserDefinedAttribute&gt;. Color [SimTalk] - user-defined attribute

**Background Color [user-defined attribute]**

**Background Color [user-defined attribute]**

To select the color of the background of the user-defined attribute which you inserted into a Frame , click the drop-down arrow.

<!-- image -->

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

SimTalk

&lt;UserDefinedAttribute&gt;. BackgroundColor [SimTalk] - user-defined attribute

**Alignment [user-defined attribute]**

Select the Alignment of the display of the user-defined attribute with its insertion point in 3D .

<!-- image -->

- Left aligns the user-defined attribute with the left border of its entire graphic.
- Name places the right border of the displayed Type Graphic or the left border of the displayed Name onto the insertion point of the user-defined attribute .
- Value places the right border of the displayed Name or the left border of the displayed Value onto the insertion point of the user-defined attribute .
- Right aligns the user-defined attribute with the right border of its entire graphic.

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. Alignment [SimTalk] - user-defined attribute

**Decimal Places [text box] - user-defined attribute**

Type in the number of Decimal Places which the user-defined attribute of the object to which it belongs shows in 3D .

<!-- image -->

**Remarks**

The user-defined attribute can show up to 15 decimal places. The default setting -1 shows all existing places. If you type in a positive value, the user-defined attribute shows the number of decimal places, which you entered.

<!-- image -->

**Note**

This setting only applies to the Data Type [user-defined attribute] &gt; real , length , money , weight , time , speed , and acceleration .

The number of decimal places for the data type time affects values differently than for the data type real . The value -1 for the data type time means that the default time display format is displayed with four decimal places. A positive value means that Plant Simulation shows the number of decimal places that you entered at most.

**SimTalk**

&lt;UserDefinedAttribute&gt;. DecimalPlaces [SimTalk] - user-defined attribute

**Integer Places [text box] - user-defined attribute**

Type in the number of Integer Places which the user-defined attribute of the object to which it belongs shows in 3D .

<!-- image -->

The user-defined attribute can show up to 15 integer places. The default setting -1 means that Plant Simulation applies no minimum on the number of integer places. Enter a positive value to fill up the space before the decimal point with blank spaces until the specified number of places has been reached if the user-defined attribute is shown in 3D.

<!-- image -->

**Note**

This setting only applies to the Data Types &gt; integer , real , length , money , weight , time , speed , acceleration , and randtime .

**SimTalk**

&lt;UserDefinedAttribute&gt;. IntegerPlaces [SimTalk] - user-defined attribute

**Transparent [user-defined attribute]**

**Transparent [user-defined attribute]**

To make the background of the user defined attribute Transparent in 3D , select this check box.

<!-- image -->

<!-- image -->

Then, the user defined attribute shows the space around the text in the color of the background of the 3D window .

To show the space around the text in white, clear the check box.

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. Transparent [SimTalk] - user-defined attribute

**Show Units [user-defined attribute]**

To show the unit of the physical size of the user-defined attribute in 3D , select this check box.

<!-- image -->

Select the unit under File &gt; Model Settings/Preferences &gt; Units .

<!-- image -->

To hide the units, clear the check box.

For the data type randtime the check box Show Units also sets if Plant Simulation shows the distribution parameters or not.

If you clear Show Units , you can also enter the number of Decimal Places .

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. ShowUnit [SimTalk] - user-defined attribute

**Show Data Type [user-defined attribute]**

To show the data type in addition to the name and the value of the user-defined attribute in the 3D Frame , into which you inserted the object to which it belongs, select this check box. To hide the Data Type , clear the check box.

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. ShowDataType [SimTalk] - user-defined attribute

**Show Name [user-defined attribute]**

To show the name of the user-defined attribute in the 3D Frame , into which you inserted the object to which it belongs, select this check box.

<!-- image -->

<!-- image -->

To hide the Name , clear the check box.

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. ShowName [SimTalk] - user-defined attribute

**Show Externally**

To show the user-defined attribute in the Outside Representation of the object to which it belongs in 3D , select this check box.

<!-- image -->

To show the user-defined attribute in the Inside Representation of the object to which it belongs in 3D , clear the check box. Inside Representation is the view that Plant Simulation shows when you open the object with the command Open in 3D .

<!-- image -->

**SimTalk**

&lt;UserDefinedAttribute&gt;. ShowExternally [SimTalk] - user-defined attribute

**Tab Statistics**

Tab Statistics [user-defined attribute]

On the Tab Statistics you can Activate Statistics , and show the Statistics Table , Charts and a Frequency Histogram .

**Active [check box] - user-defined attribute**

**Active [check box] - user-defined attribute**

To collect statistics data during a simulation run and to show the top five frequencies and the top five durations on the tab, select this check box. Click Apply to apply the changed setting.

<!-- image -->

The user-defined attribute only records statistics values for a value of Data Type string or integer .

To not collect statistics, leave the check box cleared.

SimTalk

StatisticsActive [SimTalk] - user-defined attribute

**Statistics Table [user-defined attribute]**

To open the statistics table, click this button.

<!-- image -->

| Item English       | Description                                                                                                                  | Item German         |
|--------------------|------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Value              | Shows the name of the value of the User-defined Attribute .                                                                  | Wert                |
| Frequency          | Shows the number of occurrences of the value from the column Value .                                                         | Häufigkeit          |
| Duration           | Shows the duration of the occurrences, which is the complete duration the Value had during the statistics collection period. | Dauer               |
| %_Frequency        | Shows the portion of the individual frequencies of the sum of all values in the column Frequency .                           | %_Häufigkeit        |
| %_Duration         | Shows the portion of the individual durations to the sum of all values in the column Duration .                              | %_Dauer             |
| Mean Duration      | Shows the mean duration of the individual durations.                                                                         | Mittlere Dauer      |
| Standard Deviation | Shows the standard deviation of the duration.                                                                                | Standardabwei chung |

**SimTalk**

getStatisticsTable [SimTalk] - user-defined attribute

**Charts [user-defined attribute]**

**Charts [user-defined attribute]**

To open a pie chart each showing the frequency and the duration of the value, click this button.

<!-- image -->

**Frequency Histogram [user-defined attribute]**

To open a histogram showing the frequency, i.e., the number of occurrences of the value, click this button.

**Edit [user-defined attribute]**

###### Edit [user-defined attribute]

To edit the selected user-defined attribute , click Edit .

<!-- image -->

This opens the dialog User-defined Attributes where you can change the settings. You can also turn inheritance on or off for each instance individually.

Instead, you can also double-click the name of the user-defined attribute in the list field.

**Delete [user-defined attribute]**

To delete a user-defined attribute , select it in the list field, and click this button.

<!-- image -->

SimTalk

deleteAttr [SimTalk]

Navigate Menu

Navigate Menu [general description]

The Navigate menu provides the commands listed in the table of contents to the left.

**Note**

Some of the commands are available only after you insert the object into a Frame , i.e., they are deactivated when you open the object in the Class Library !

The Context Menu of the Selected Object in the Frame and the Home Ribbon Tab also provide some of these commands.

**Open Location [described]**

###### Open Location [described]

Opens the Frame window in which the selected object is located.

SimTalk

Location [SimTalk] - material flow objects

~ [SimTalk] (tilde) - material flow objects

###### Open Origin [described]

Opens the object from which the selected object was derived most recently.

<!-- image -->

Or you can right-click the object in the Frame and click Open Origin on the context menu.

<!-- image -->

**SimTalk**

Origin [SimTalk] - general description

Video on YouTube

[https://youtu.be/DwZkGMxXJIA?si=wmxLozi02YyXoZFU&amp;t=230](https://youtu.be/DwZkGMxXJIA?si=wmxLozi02YyXoZFU&t=230)

###### Go to Origin [described]

Go to Origin [described]

Closes the open dialog box of the selected object and opens the object from which it was derived most recently.

SimTalk

Origin [SimTalk] - general description

###### Open Class [described]

Opens the dialog of the class of the selected object in the Class Library .

When you select the command Open Class for an instance of an object, Plant Simulation moves up in the inheritance structure until it reaches an object in the Class Library . It then opens the dialog of this object.

SimTalk

Class [SimTalk] - read-only attribute

**Go to Class [described]**

###### Go to Class [described]

Closes the open dialog box of the selected object and opens the class of the object in the Class Library . SimTalk

Class [SimTalk] - read-only attribute

###### Open 3D Location [described]

Changes to the respective Frame window in which the selected object is located in 3D .

You can then change the 3D properties of the object.

**Note**

Plant Simulation only shows this command when you created or opened the model in 3D Only mode or in 2D/3D mode .

See also

Edit 3D Properties [dialog]

###### Edit 3D Properties [on Navigate menu]

Edit 3D Properties [on Navigate menu]

Opens the Edit 3D Properties window of the selected object in 3D .

You can then change the 3D properties of the object.

<!-- image -->

Note

Plant Simulation only shows this command when you created or opened the model in 3D Only mode or in 2D/3D mode .

See also

Edit 3D Properties [dialog]

Open [simulation settings dialog]

Open Simulation Settings

- [x] in 3D

View Menu [general description]

The View menu provides commands to access its functions.

The commands listed in the table of contents to the left.

Some objects do not provide all of the commands, while others provide additional commands, which are described in the topics of these objects.

The View menu of the objects offering a Transport Importer provides these commands in addition:

Exporters [on View menu]

Services [on View menu]

Unavailable Services [on View menu]

Associated Workplaces [on View menu]

The Context Menu of the Selected Object in the Frame and the Home Ribbon Tab also provide some of these commands.

View Menu

**SimTalk**

**updateDialog [SimTalk]**

###### Refresh [on View menu]

Refresh [on View menu] Updates the open dialog box of the object with the current values of attributes . Plant Simulation does not automatically do this, when you assign new attributes using methods . Instead, you can also press F5 . SimTalk updateDialog [SimTalk]

Show Statistics Report [on View menu]

Opens the Statistics Report and shows resource statistics data of the selected object.

SimTalk

Statistics Report [described]

Show Statistics Report [in Frame]

showStatisticsReport [SimTalk]

Viewing the Statistics Report

Resource Statistics [material flow objects]

Show Attributes and Methods [on View menu]

Shows the attributes and the methods of the selected object in the window Show Attributes and Methods .

Instead, you can also right-click the object in the Frame and select Show Attributes and Methods on the context menu or press the F8 key.

<!-- image -->

**See also**

Show Attributes and Methods [described]

###### Contents [material flow objects]

Opens a list or table showing all MUs , which are located on the selected object at any one point in time:

- The point-oriented objects with a capacity of 1 part show the path of the current part in the list.
- The point-oriented objects with a capacity of more than 1 part show the path of the part in the list that are located on it. The capacity determines how many parts it shows.
- The ParallelStation shows the path of the current parts in the list. The position of the part in the table matches the position of the part in its x-y coordinate system. The data type of the columns is object .
- The Buffer shows the path of the current parts in the list. The position of the part in the table matches the position of the part in its x-y coordinate system.
- The Sorter shows the path of the parts in the list. The capacity or the number of parts that are located on the Sorter determine how many parts it shows.

<!-- image -->

<!-- image -->

<!-- image -->

**Note**

Plant Simulation shows the parts on the Sorter in reverse order, meaning that the part that exits last is located on the first occupied place. The part that is going to exit next is located on the last place.

- The objects Store , Container , and Transporter that can stack several parts, show the stacked parts in subtables. The identifier of the subtable contains the number of stacked parts after the underscore. To show the individual stacked parts in the subtable, double-click the respective row in the contents list.

<!-- image -->

- The length-oriented objects Conveyor , Track , and Transporter show the path in the contents table, i.e., the names and the numbers of the current parts. In addition, it shows the position of the MUs on the object.

The column Object shows the path to the part , the column From shows the start position of the MU , and the column To shows the end position in the length unit you selected under File &gt; Model Settings/ Preferences &gt; Units &gt; Length . The number of rows matches the number of MU parts located on the object. The data type of column 1 is object , of the second and third column it is length .

<!-- image -->

- The length-oriented object TwoLaneTrack shows the path the current part, in the contents table for lane A and lane B separately. In addition, it shows the position of the MUs on the object.
- The fluid objects DePortioner and Portioner show the path of the MU , which is emptied or filled in the list.

<!-- image -->

<!-- image -->

- The fluid objects FluidSource , FluidDrain , Pipe , and Tank show the material that flows through them. The column has the data type string .
- The fluid object Mixer shows the material in column 1 and the contained amount in column 2, while the starting materials flow into it. Column 1 has the data type string , column 2 has the data type real . As soon as the Mixer starts the mixing process, the contents list only shows the product in column 1.
- The resource object Workplace shows the path of the Worker in the list. The column has the data type object .
- The resource object Worker , who carries stacked parts, shows the stacked parts in subtables. The identifier of the subtable contains the number of stacked parts. To show the individual stacked parts in the subtable, double-click the respective cell in the contents list.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

**SimTalk**

Cont [SimTalk] - material flow objects

contentsList [SimTalk] - material flow objects

deleteMovables [SimTalk] - material flow objects mu [SimTalk] - material flow objects muPart [SimTalk] NumMU [SimTalk] - material flow objects NumMUParts [SimTalk] - material flow objects See also Check the Contents List of the Stations Print the Contents List to the Console as an Array

###### Contents and Reserved Places

Opens a list or table showing all MUs which are located on the selected object at any one point in time or for which a place is reserved on the object.

<!-- image -->

**Note**

Contents and Reserved Places applies to the stationary material flow objects which can accept parts, to the Workplace , and to the Conveyor .

Plant Simulation considers a place as being reserved if, for example, a Worker was requested to carry a part to the target object as this object is available to accept this part.

Plant Simulation also considers a place as being reserved if, for example, a PickAndPlace robot to rotate to the part to pick it up and to transport it to the target object as it can now receive it.

Plant Simulation highlights the reservation in the table in color.

A Store with a z-dimension greater than 1 highlights the sub-tables containing reserved places with the same color. In addition, the name of the subtable contains the number of the contained objects and the reserved place in the title bar of the window.

<!-- image -->

**SimTalk**

contentsAndReservedList [SimTalk]

ReservedFor [SimTalk]

**ReservedPlace [SimTalk] of the MUs**

See also

Model a Worker Who Waits for a Free Target

###### Forward Blocking List

Opens a table showing all MUs that wanted to move onto the selected object at its entrance, i.e., moving in the forward direction from the predecessor, but could not.

When a MU cannot be moved on, Plant Simulation stops it and enters it into the Forward Blocking List .

The table shows the name of the MU and the time at which the MU attempted to leave the preceding object.

<!-- image -->

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

**Note**

The TwoLaneTrack provides a Forward Blocking List each for each of its two lanes, i.e., for Lane A and for Lane B .

**Note**

If you enter a certain position on the destination object using the parameter of data type length , the MU does not enter itself into the Forward/Backward Blocking List as Plant Simulation cannot watch at which point in time this position is available again.

In addition, Plant Simulation does not enter a MU into the Forward/Backward Blocking List when it is located on a moving Transporter .

Plant Simulation removes a MU , which is located on the loading space of a Container/Transporter , from the Forward/Backward Blocking List if the Container/Transporter itself is moved.

**Note**

If you only need the first entry of the Forward Blocking List , you can use the read-only-attribute FwBlockListEntry1 for those objects which have a Forward Blocking List . Access is much faster than with the method fwBlockList .

**Note**

If the predecessor is a FlowControl or a Sorter , the Forward Blocking List contains this FlowControl or Sorter instead of the MU .

SimTalk fwBlockList [SimTalk] - material flow objects fwBlockList [SimTalk] - lane A or B See also FwBlockListEntry1 [SimTalk] Entrance Locked [material flow objects] Check the Contents List of the Stations Video on YouTube https://youtu.be/MY59lMy3UPM?si=zPuUALwOxiJasw65&amp;t=906

[https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&amp;t=269](https://youtu.be/wfVN-mcWNsc?si=StxMHuDgvZerba9g&t=269)

###### Exit Blocking List

Opens a list, which contains all MUs that wanted to exit the selected object at its exit, but could not. If a MU cannot be moved on, Plant Simulation stops it and enters it into the exit blocking list.

The table shows the name of the MU and the time at which the MU attempted to exit the object.

<!-- image -->

**Note**

The TwoLaneTrack provides an Exit Blocking List each for each of its two lanes, i.e., for Lane A and for Lane B .

**Note**

The object only enters the MUs into the Exit Blocking List , if you activated the check box Exit locked .

**SimTalk**

exitBlockList [SimTalk] - material flow objects

exitBlockList [SimTalk] - lane A or B

See also

Exit Locked [material flow objects]

Check the Contents List of the Stations

###### Backward Blocking List

Opens a table that contains all MUs that wanted to move onto the selected Conveyor , Track , and TwoLaneTrack at its exit, i.e., were moving in a backward direction from the successor, but could not.

When a MU cannot be moved on, Plant Simulation stops it and enters it into the Backward Blocking List .

The table shows the name of the MU and the time at which the MU attempted to leave the succeeding object and enter the selected object.

If the MU moves backward , the successor is the object that is connected to the selected object with a Connector and precedes it in the sequence of stations in the simulation model. This approach assumes that normally the flow of materials moves in the forward direction.

**Note**

The TwoLaneTrack provides a Backward Blocking List each for each of its two lanes, i.e., for Lane A and for Lane B .

**Note**

If you enter a certain position on the destination object using the parameter of data type length , the MU does not enter itself into the Forward/Backward Blocking List as Plant Simulation cannot watch at which point in time this position is available again.

In addition, Plant Simulation does not enter a MU into the Forward/Backward Blocking List when it is located on a moving Transporter .

Plant Simulation removes a MU , which is located on the loading space of a Container/Transporter , from the Forward/Backward Blocking List if the Container/Transporter itself is moved.

SimTalk

bwBlockList [SimTalk] - material flow objects

bwBlockList [SimTalk] - lane A or B

See also

Check the Contents List of the Stations

###### Exporters [on View menu]

Opens a table showing the names of all Exporters providing services.

<!-- image -->

<!-- image -->

**Services [on View menu]**

###### Services [on View menu]

Opens a table showing the names of all imported services of the selected object. The name of the failure service is identical with the name of the subtable.

Double-click the name of the service to open the subtable. Column 1 of the subtable shows the Name of the Exporter , the column Amount the number of services provided.

<!-- image -->

###### Unavailable Services [on View menu]

Opens a table showing the names of the four service types (failure, set-up, processing, and transport) that are unavailable at the moment for the selected object.

<!-- image -->

The table shows the name of the unavailable service white on a red background in the respective cell.

Double-click the name of the service to open the subtable. Its columns show the Name of the Exporter , the Amount of services defined, the Amount of services missing, and the Name of the associated Alternative .

**See also**

Start/Stop Simulation [EventDebugger]

Associated Workplaces [on View menu]

Opens a list showing the names of all the Workplaces which are assigned to the selected object.

<!-- image -->

See also

Workplace

assignedWorkplaces [SimTalk]

Station [Workplace]

###### Associated Lockout Zones

Opens a list, which contains the LockoutZone objects that are assigned to the selected object.

<!-- image -->

###### Associated Shift Calendar

Opens a table, which contains the ShiftCalendar object that is assigned to the selected object.

<!-- image -->

**SimTalk**

ShiftCalendarObject [SimTalk] - material flow objects

See also

ShiftCalendar [object]

Tools Menu

Tools Menu [general description]

The Tools menu provides the menu commands listed in the table of contents to the left.

###### Edit Controls

Edit Controls [material flow objects]

Opens a dialog in which you can select controls, which Plant Simulation activates for the action you want to execute.

To create controls, also called interaction controls or interaction methods, for the selected object, select this command. Controls make objects react to a number of user actions, such as inserting and deleting objects, etc. You can also assign Methods from within other Methods .

<!-- image -->

The respective attributes are described under Attributes for Controls of All Objects .

Depending on their functions, the objects provide different controls. The EventController , for example, does not have a Rename Control , as you cannot rename it. Control methods which are available only for certain objects are explained in the respective sections. Controls that are not available for the object are deactivated, i.e., unavailable.

Select a Method to be activated, when Plant Simulation performs a certain action:

- Click next to the name of the control. In the dialog Select Object , navigate to the folder in which the Method object is located and select it.
- Or right-click in the text box. Then, select Create Control on the context menu to create a control method , which is a user-defined attribute of data type method of this object. This might, for example, look like this:

<!-- image -->

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To open and modify this Method :

- ◊ Press F2 .
- ◊ Or hold down Shift and double-click into the text box.
- ◊ Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute ; deleting the name from the text box just deletes the name, but keeps the user-defined attribute .

Once you specify a control, either here or on the Tab Controls , the context menu of the object in the Frame shows the command Controls . You can then select the name of the control on the submenu to edit it.

The controls are listed in the table of contents to the left.

<!-- image -->

Compare Edit Controls [class library] Edit Controls [MUs]

Edit Controls [Home ribbon]

**Select Object [for controls]**

Click the ellipsis button to the right of the text box and select an object , an attribute , or a method in the dialog Select Object .

- The list shows the names of all Objects and Attributes and Methods in the Frame in which the object is located from which you selected the menu command Edit Controls . Select the name of an Attribute or a Method .
- Click Back , to change to the next higher level in the hierarchy of objects when the Attribute or the Method you want to select is located there.
- To use the absolute path to the object or Method , select the check box Absolute Path . Plant Simulation then enters *.MUs.MyPart for example.

**Note**

When you select Absolute path for a user-defined attribute of data type Method , Plant Simulation does not insert a leading asterisk in front of the user-defined attribute of data type Method .

By default, Plant Simulation uses the relative path, which, for example, looks like this ~.MUs.MyPart .

The difference between absolute and relative paths is described under Object Paths in SimTalk .

Plant Simulation shows the path to the object or Method in the box.

<!-- image -->

- When you add an observer to an object, the dialog looks slightly different.

Select the watchable attribute or the read-only attribute to which you would like to add the observer.

**Select Object [for controls]**

<!-- image -->

SimTalk

openObjectSelectBox [SimTalk]

See also

Object Paths in SimTalk

Create Entrance and Exit Controls

Create and Delete an Observer

Edit Observers [general description]

Compare

Edit Controls [class library]

Edit Controls [material flow objects]

Edit Controls [MUs]

**Change Path Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Change Path Control , which is called when the name of the selected Folder or Frame changes or when you move them.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Plant Simulation executes the Change Path Control :

- When the name of a Folder or a Frame changes. The control is called for all objects contained in the Folder or Frame . The anonymous identifier @ points to the renamed object.
- When you move a Folder or a Frame . The control is called for all objects contained in the Folder or Frame .

Within the Method you can access the moved object with the anonymous identifier question mark ? .

**Note**

Not each move action actually moves the object. When you move an object from one Frame to another, Plant Simulation deletes the object from its source Frame and creates a new object in the target Frame . Specify an empty string "" as location to interpret it as the top level in the hierarchy of objects, as the object basis .

**Example**

A Change Path Control might look like this:

```simtalk
param oldPath,newPath: string, manually: boolean
print oldPath
print newPath
print manually
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard change path control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Change Path Control has to define three parameters:

- The parameter PreviousLocation of data type string designates the previous location of the object.
- The parameter NewLocation of data type string designates the new location of the object.
- The parameter ManualChange of data type boolean indicates if you change the path of the object manually ( true ) or with a Method ( false ).

**SimTalk**

ChangePathCtrl [SimTalk]

**See also Select Object [for controls]**

**Create Control [context menu]**

**Close Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Close Control , which is called when you close the respective object window .

<!-- image -->

For list objects Plant Simulation passes a parameter, of data type boolean , to the Method that is called. This parameter shows if the contents of the list window has changed or not.

<!-- image -->

Plant Simulation executes the Plausibility Control for lists and tables only, when you close the list or table after making a change . Plant Simulation also considers loading a file into a table as a change. This way Plant Simulation can check the entry and display an error message if the entry was wrong. When you specify a Close Control and a Plausibility Control , Plant Simulation always calls the Plausibility Control first, before it calls the Close Control .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .

- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard close control as a user-defined attribute looks like this:

<!-- image -->

**Parameter**

The parameter Changed of data type boolean shows if the contents of the list object has changed (true) or not (false).

**SimTalk**

CloseCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

**Connect Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Connect Control , which is called when you connect two objects with a Connector and when you delete the connection between two objects.

<!-- image -->

**Note**

When you insert a Connector , Plant Simulation first calls the Connect Control for the Connector before calling the Connect controls for the objects you are connecting.

When you delete a Connector , Plant Simulation first calls the Connect Control for the connected objects before calling the Destructor Control .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard connect control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The method has to define three parameters:

- The parameter predecessor of data type object designates the source object where the connection starts.
- The parameter successor of data type object designates the destination object where the connection ends.
- The parameter connector of data type object indicates if the connection is going to be created or deleted. If the Connector is going to be created, it is assigned to the parameter. If the Connector is going to be deleted, VOID is assigned.

**Note**

If you externally connect an Interface of a Frame , the Interface is passed to the parameter predecessor/ successor .

**SimTalk**

ConnectCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

**Constructor Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Constructor Control , which is called when you duplicate, derive, or instantiate the selected object (i.e., insert it into a Frame or model).

<!-- image -->

**Note**

The object already exists, when Plant Simulation calls the Constructor Control .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard constructor control as a user-defined attribute looks like this:

**Parameter**

If you declare the Constructor Control with the optional parameter onCreate3D of data type boolean , the Constructor Control will not only be called for the events described above with false , but a second time when the 3D part of an object is created. In this case the parameter is true .

<!-- image -->

<!-- image -->

**Destructor Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Destructor Control , which is called when you delete the selected object.

<!-- image -->

When a Frame contains sub-Frames and objects, Plant Simulation will call Destructor Control in these Frames as well. When the Destructor Control of the object is called, the object still exists.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

DestructorCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

**Drag-and-Drop Control**

**Drag-and-Drop Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Drag-and-Drop Control , which is called for the selected object, which you drag onto another object and drop there.

<!-- image -->

The dropped object can be an object of data type object or text of data type string .

**Note**

You cannot use the Drag-and-Drop Control in the Class Library by dragging and dropping an object onto another object. The Drag-and-Drop Control only works when you drag an object onto another object in a Frame and drop it onto another object there.

**Note**

You can assign the method a Label , which Plant Simulation shows in the status bar, when you drag an object onto the object for which you created the Drag-and-Drop Control . This way you can tell the user which actions the control executes.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Parameter for Point-oriented Objects

The standard drag-and-drop control for point-oriented objects looks like this:

<!-- image -->

The parameter draggedObjects is an array of data type object that designates the path of the dragged and dropped objects.

**A Drag-and-Drop Control might look like this:**

```simtalk
param draggedObjects: object[] // one-dimensional array with n objects // the size of which can change
var obj: object // @,?: drop target
for var i := 1 to draggedObjects.dim
	obj := draggedObjects[i] // enter your source code here
	print i, ": ", draggedObjects[i] // prints the dragged objects to the Console
next
```

Parameters for Length-oriented Objects

The standard drag-and-drop control for length-oriented objects looks like this:

<!-- image -->

- The parameter draggedObjects is an array of data type object and designates the path of the dragged and dropped objects.
- Plant Simulation sets the data types of the optional parameters for length-oriented objects when the Drag-and-Drop Control is called.
- For a length-oriented object the optional parameter dropPosition of data type length designates the position starting at the beginning of the length-oriented object at which the object was dropped.
- For the TwoLaneTrack the optional parameter dropLane of data type string designates the lane on the TwoLaneTrack on which the mouse button was released when dropping the object.

A Drag-and-Drop Control for creating sensors on a length-oriented object and on a TwoLaneTrack might look like this:

```simtalk
param droppedObjects: object[], dropPosition: any := void, lane: any := void // @,?: drop target
if lane = void
	if dropPosition /= void // length-oriented object
```

?.createSensor(dropPosition, "Length", void, true, false) end else                       // TwoLaneTrack if lane = "A" ?.A.createSensor(dropPosition, "Length", void, true, false) else ?.B.createSensor(dropPosition, "Length", void, true, false) end end

Create a Control that is a Method of the Object

You can also create a control method , which is a user-defined attribute of data type method of this object. Right-click in the text box and select Create Control . This might, for example, look like this:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control . Or
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute ; deleting the name from the text box just deletes the name, but keeps the user-defined attribute .

SimTalk

DragDropCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

**Use a Drag-and-Drop Control for Several Objects**

**Fail Control [material flow objects]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Fail Control , which is called whenever the Failed state of the selected object changes.

<!-- image -->

You can change the state in the dialog box of the object by selecting Failed or by assigning the value true or false to the attribute Failed . Within the control you can use the anonymous identifier question mark ? to access the object which triggered the control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard fail control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The method can define two optional parameters:

- The parameter FailureIsStarting of data type boolean indicates if the failures starts (true) or ends (false).
- The parameter FailureProfileName of data type string is the name of the failure profile that caused the failure.

**Note**

Provided the Fail Control declares both parameters, it will not only be called when the object changes to the failed -state or when the failed -state ends, but also each time when a failure profile is failed or when the failure is removed.

Let's say failure profile 1 is already failed, and then you also fail failure profile 2 in addition, then the Fail Control will still be called, although the object remains in the failed -state.

**Note**

A Fail Control , which does not expect a parameter or only expects a single parameter, will only be called if the state of the object actually changes, meaning it will not be called when another failure profile is already failed. A Fail Control , which expects the name of the failure profile as the second parameter, will, by contrast, always be called when a failure profile is failed or when the failure is removed.

**SimTalk**

**FailCtrl [SimTalk]**

See also

Select Object [for controls]

Create Control [context menu]

**Init Control [general description]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Init Control , which is called at the start of the simulation run during the init phase.

<!-- image -->

The Init Control is called before the events are computed. The normal init methods on the other hand are executed after the initial events have been computed.

In the Init Control you can, for example, initialize the Transporter with suitable values and assign userdefined attributes or change the Worker Creation Table of the WorkerPool for the next simulation run. This cannot be accomplished in an init method as this method would be called too late in time.

You can also initialize attributes which affect event generation, for example the Availability . Here the Init Control are executed before events are computed. The normal init methods are executed after the initial events have been computed.

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
- To delete this control, delete the user-defined attribute ; deleting the name from the text box just deletes the name, but keeps the user-defined attribute .

SimTalk

**InitCtrl [SimTalk] - general description**

See also

Select Object [for controls]

Create Control [context menu]

init [SimTalk] - predefined name

Init Control [EventController]

Init Control [Transporter]

Init Control [WorkerPool]

**Move in Frame Control**

**Move in Frame Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Move in Frame control , which is called when the selected object actually changes the position in the Frame into which you inserted it, meaning that it is moved within its Frame .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

A Move in Frame control might look like this:

```simtalk
param previous, new: length[3]
print "xv:",previous[1]," yv:",previous[2]," zv:",previous[3], "xn:",new[1]," yn:",new[2]," zn:",new[3]
```

Create a Control that is Part of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.

- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard move-in-frame control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Move in Frame control has to define two parameters:

- The parameter old is an array of data type length with three parameters. They designate the xcoordinate, the y-coordinate, and the z-coordinate of the previous position of the object in the Frame .
- The parameter new is an array of data type length with three parameters. They designate the xcoordinate, the y-coordinate, and the z-coordinate of the new position of the object in the Frame .

Within the Method you can access the moved object with the anonymous identifier question mark ? .

SimTalk

MoveInFrameCtrl [SimTalk]

setPosition [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

**Move to Folder Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Move-to-Folder Control , which is called when you move the selected object from a folder or a Frame to a different folder.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard move-to-folder control as a user-defined attribute looks like this:

**Parameters**

The Move-to-Folder Control has to define three parameters:

- The parameter oldFolder of data type string designates the previous location ( Frame or folder) of the object.
- The parameter newFolder of data type string designates the new location of the object.
- The parameter manually of data type boolean shows the user if the object is manually moved to a folder (true) or with a Method (false).

Within the Method you can access the moved object with the anonymous identifier question mark ? , and the new location with the anonymous identifier @ .

SimTalk

moveToFolder [SimTalk]

MoveToFolderCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

<!-- image -->

**Open Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Open Control , which is called when you double-click the selected object to open it.

<!-- image -->

Plant Simulation does not open the dialog of the object though, but calls and runs the source code of the Open Control . Opening the dialog box is now completely controlled by the source code you entered.

**Note**

If Plant Simulation cannot open the dialog of the object any longer because of a faulty Method , create another Method and open the object from there with the method openDialog [SimTalk] - all objects .

If you type in a user-defined attribute of data type method as the Open Control , and if this Method is encrypted, you cannot open the respective object any longer. Only the Open Control itself, and any other Method that has been encrypted with the same password as the Open Control , can open the object.

If you entered an Open Control for a subtable, and when you then try to open this subtable, Plant Simulation executes the control without opening the subtable. This also applies to tables that are part of the object Variable . This also applies to an object of data type table which you inserted into a Frame .

To prevent the Open Control from being executed, hold down Alt while double-clicking the icon of the object. Instead, you can also select the command Open Without Control on the context menu of the object in the Frame .

<!-- image -->

<!-- image -->

When you click the button Open Location or Open Origin on the Home Ribbon Tab , you can hold down Alt while you click the button to prevent the Open Control of the class or of the origin to be executed respectively.

**Note**

To prevent the Open Control from being bypassed by holding down the Alt key, you can use an encrypted user-defined attribute of data type method as the Open Control .

If you want to remove the Open Control , you have to decrypt the Method beforehand. As you cannot open the object in the regular way, you can accomplish this with one of these procedures:

- Decrypt the model as a whole, this also decrypts all Open Controls .
- Click Stop on Controls on the Debugger ribbon tab and then double-click the object. This opens the Debugger for the Open Control . Select the command Tools &gt; Decrypt .

- Call the method decrypt [SimTalk] . You might, for example, enter

Frame5.OnOpen.decrypt("MyPassword123")

**Note**

If you specify a user-defined attribute of data type method which you encrypted, you cannot delete or rename the attribute any longer. You have to decrypt the Method beforehand.

**Note**

If you open an object from the Method Debugger window, Plant Simulation will not execute the Open Control . This applies, for example, when you select Open Object [Method Debugger] on the context

menu, or when you click Open Location or Open Origin

.

<!-- image -->

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

An Open Control might look like this:

```simtalk
param from3D: boolean
var passwordHash:string := computeSHA1Hash(prompt("Password:"))
if passwordHash = "686483805ac47ca14e03514f7481a7973b401762" // password "abc" entered? if from3D
	?._3D.openWindow
else
	?.openDialog
end
param from3D, inLockedFolder: boolean
if inLockedFolder
	if messageBox("The object is inside a locked folder."+strChr(10)+"Do you want to open the object anyway?", 48, 2) = 32 // "No"?
		return
	end
end
?.openDialog
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard open control as a user-defined attribute looks like this:

<!-- image -->

Parameters for all Objects Except for DataList and DataTable

- If you declare the Open Control with the parameter from3D of data type boolean , the value of the parameter will be set to true, if the object is opened from within a 3D window.
- If you declare the Open Control with the parameter inLockedFolder of data type boolean , the value of the parameter will be set to true, if the object is located within a locked library or a locked folder. If you do not declare the parameter, i.e., the Open Control expects none or only one parameter, and if the object to be opened is located within a locked library or a locked folder, the Open Control will not be called. Instead, Plant Simulation shows an error message pointing out that you are not allowed to modify the object.

SimTalk

OpenCtrl [SimTalk]

**See also Select Object [for controls]**

**Create Control [context menu]**

**Pause Control [material flow objects]**

**Pause Control [material flow objects]**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Pause Control , which is called whenever the state of the selected object changes.

<!-- image -->

You can change the Paused state by selecting an entry in the drop-down list Paused/Planned/Unplanned or by assigning another value to the attribute Pause . When you query the paused state within the Method , it shows the state after the change.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

A Pause Control might look like this:

```simtalk
print "Current pause ", current.pause
MyStation.pause := current.pause
var shift := root.ShiftCalendar.GetCurrShift
print "Current shift: ", shift
if not current.unplanned
	if current.pause
		current.currIcon := "pause"
	else
		current.currIcon := "working"
	end
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_user-defined attribute\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard pause control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Pause Control has to define two parameters:

- The parameter Duration of data type real sets the length of the pause . If the length of the pause is unknown, Plant Simulation passes -1. The same happens when the control is called at the end of the pause .
- The parameter NewValue of data type boolean sets that the control will only be called if the ShiftCalendar changes the state of the object.

In addition, the object will not be put in the desired state. The Pause Control has to do this. The desired value is passed in the parameter NewValue .

The part still can be processed in its entirety before the object changes to the state paused .

**Note**

If the Pause Control has the parameters listed above, then the ShiftCalendar will not automatically change the state paused . This is useful to complete processing of a part and then pause the shift manually by setting the attribute Pause of the object to true .

```simtalk
Compare this example:
param Duration: real, NewValue: boolean
if ?.Cont /= void
	wait ?.Cont.RemainingProcTime
end
?.Pause := NewValue
```

**Note**

If the Pause Control does not have any parameters, Plant Simulation always calls the Pause Control when the state paused changes.

If the Pause Control has the parameters listed above, Plant Simulation only calls the Pause Control when the state paused is changed by the ShiftCalendar . This prevents that the Pause Control calls itself when the state paused is set manually.

Within the control you can access the paused object with the anonymous identifier question mark ? .

SimTalk

PauseCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

Paused Frames

**Permit Delete Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Permit Delete Control , which is called for the Frame or the Folder , when you attempt to delete the object for which you programmed the control.

<!-- image -->

Plant Simulation reacts to the return value of the control:

- If the method returns true, Plant Simulation deletes the object and calls a Destructor Control method, provided you specified it.
- If the method returns false, Plant Simulation does not delete the object.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.

- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard permit-delete control as a user-defined attribute looks like this:

<!-- image -->

**Plausibility Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Plausibility Control , which is called when you click OK or Apply in the dialog of the selected object or in the windows of list objects to apply the changes you made there.

<!-- image -->

When you click OK or Apply , the Method checks if the entries are plausible, or it interprets them.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**Parameters for List Objects**

- If the Plausibility Control has no parameters Plant Simulation only calls it, when you close the list or table after making a change . Plant Simulation also considers loading a file into a table as a change. This way Plant Simulation can check the entry and display an error message if the entry was wrong.
- If the plausibility control has two optional parameters of data type integer , Plant Simulation also calls the Plausibility Control after you edited a cell.
- The parameter ColumnNumber of data type integer designates the column number of the edited cell.
- The parameter RowNumber of data type integer designates the row number of the edited cell.

When you close the list or table, which you changed, or when you make any changes in any cell, Plant Simulation calls the Plausibility Control with the values-1 for the column and -1 for the row.

**A Plausibility Control might look like this:**

```simtalk
param column,row: integer
switch column
case 1 // column-specific action
end
```

SimTalk

**PlausibilityCtrl [SimTalk]**

See also

Select Object [for controls]

Create Control [context menu]

**Relabel Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Relabel Control , which is called when you modify the Label of the selected object.

<!-- image -->

Plant Simulation calls the Relabel Control first for the relabeled object and then for the inheriting objects.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

A relabeling control might look like this:

```simtalk
param CurrentLabel, NewLabel: string, ManualRename: boolean
print CurrentLabel
print NewLabel
print ManualRename
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.

- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard relabel control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Relabel Control has to define three parameters:

- The parameter oldLabel of data type string designates the current label of the object.
- The parameter newLabel of data type string designates the new label.
- The parameter manually of data type boolean indicates if the object is relabeled by the user (true) or by assigning a value to the attribute Label (false).

SimTalk

RelabelCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

Label [general description]

**Rename Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Rename Control , which is called when you change the Name of the selected object.

<!-- image -->

Plant Simulation calls the Rename Control first for the renamed object and then for the inheriting objects.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Note**

The Rename Control will not be called when you insert the object into a Frame and then assign it a different name.

**Example**

A Rename Control might look like this:

```simtalk
param CurrentName, NewName: string, ManualRename: boolean
print CurrentName
print NewName
print ManualRename
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard rename control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Rename Control has to define three parameters:

- The parameter oldName of data type string designates the current name of the object.
- The parameter newName of data type string designates the new name of the object.
- The parameter manually of data type boolean indicates if the object is renamed by the user (true) or by assigning a value to the attribute Name (false).

**SimTalk**

RenameCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

Rename [model or object]

Name [general description]

**Select Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Select Control , which is called when you click the selected object with the left mouse button.

<!-- image -->

Plant Simulation does not select the object. Instead, the Method you entered has to take the appropriate actions, for example by opening the object, or by confirming the selection with the attribute Selected , etc.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

A Select Control might look like this:

```simtalk
print @.Selected
@.Selected := true
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

**Select Control**

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

SelectCtrl [SimTalk]

Selected [SimTalk] - 2D

See also

Select Object [for controls]

Create Control [context menu]

**Unplanned Control**

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Unplanned Control , whenever the unplanned state of the selected object changes.

<!-- image -->

The Unplanned state of the object sets whether the object is not scheduled to work during the time, which you typed into the ShiftCalendar or whether it is scheduled to work.

You can change the state in the dialog of the object by selecting an entry in the drop-down list Paused/

<!-- image -->

Planned/Unplanned or by assigning another value to the attribute Unplanned . Within the control you can access the object with the anonymous identifier question mark ? .

**Note**

The ShiftCalendar uses the attribute Unplanned do designate the time span during which the object is not planned to work during a shift.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Example

An Unplanned Control might look like this:

```simtalk
print "Frame unplanned: ", current.unplanned
MyStation.unplanned := current.unplanned
if current.unplanned
	current.currIcon := "unplanned"
else
	if current.pause
		current.currIcon := "pause"
	else
		current.currIcon := "working"
	end
```

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard unplanned control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Unplanned Control has to define two parameters:

- The parameter Duration of data type real sets the length of the shift pause . If the length of the shift pause is unknown, Plant Simulation passes -1, as well as when the control is called at the end of the shift pause .
- The parameter NewValue of data type boolean sets that controls will only be called if the ShiftCalendar changes the state of the object.

In addition, the object will not be put in the desired state. The unplanned control has to do this. The desired value is passed in the parameter NewValue .

The part still can be processed in its entirety before the object changes to the state unplanned .

**Note**

If the Unplanned Control has the parameters listed above, then the ShiftCalendar will not automatically change the state unplanned . This is useful to complete processing of a part and then end the shift manually by setting the attribute Unplanned of the object to true .

Compare this example:

```simtalk
param Duration: real, NewValue: boolean
if ?.Cont /= void
	wait ?.Cont.RemainingProcTime
end
?.Unplanned := NewValue
```

**Note**

If the Unplanned Control does not have any parameters, Plant Simulation always calls the Unplanned Control when the state unplanned changes.

If the Unplanned Control has the parameters listed above, Plant Simulation only calls the Unplanned Control when the state unplanned is changed by the ShiftCalendar . This prevents that the Unplanned Control calls itself when the state unplanned is set manually.

SimTalk

UnplannedCtrl [SimTalk]

See also

Select Object [for controls]

Create Control [context menu]

Paused Frames

Edit Observers

Edit Observers [general description]

To create observers, which watch the values of watchable attributes and read-only attributes and which allow you to react to changed values, select this command.

<!-- image -->

When you create your simulation model, it will often become necessary to trigger certain actions if the values of watchable attributes or watchable read-only attributes of objects change. The column Watchable in the window Show Attributes and Methods shows this.

<!-- image -->

To accomplish this, you can create observers for most of the built-in objects.

This observer watches the value of an attribute or a read-only attribute and then executes one or several methods when the value of the attribute or read-only attribute changes.

This method can either be a Method object, which you insert into a Frame , or a user-defined attribute of data type method . Right-click into the text box Method and select Create Control . In this case Plant Simulation automatically formats the Method correctly.

An observer of a user-defined attribute of data types table/list/stack/queue is not going to be called when the contents of the list changes, but only when a new list is assigned. In addition, the old list will not be passed to the second parameter of the observer method , but this parameter is always VOID for lists.

Within the Method , you can use the anonymous identifiers ? , and @ to address the object, whose attribute changed, i.e., the caller of the Method .

**Parameters**

Plant Simulation passes one, two, or three parameters to the Method , which will be executed:

```simtalk
param attribute: string, oldValue, newValue: any
```

1. The name of the watchable attribute or the watchable read-only attribute whose value changed. This way you can use a single Method as the called Method for several attributes/methods .
2. The previous value of the watched attribute or the watched read-only attribute . This way you can still access the previous value after the Method changed it to the new value.
3. The new value of the watched attribute or the watched read-only attribute .

You can either omit the first two parameters or the last parameter. Thus, you can declare observer methods with one, two, or three parameters:

```simtalk
// one parameter, without parameter 1 and 2
param newValue: any // two parameters, without parameter 3
param attribute: string, oldValue: any // three parameters
param attribute: string, oldValue, newValue: any
```

**Note**

As a rule observer methods are called after all other controls. If you want to react to state changes before other controls, you have to use the stopuntil-instruction or the waituntil-instruction instead of an observer .

Proceed as follows to work with observer methods :

- To create a new observer, click New

.

<!-- image -->

- To edit an existing observer, select it in the list field and click Edit or double-click it in
- the list field.
- To delete an observer, select it in the list field and click Delete

You can use these keyboard keys in the list:

- Return to open the dialog Select Observing Method of the selected observer. Here you can then change the settings.
- Insert to create a new observer.

<!-- image -->

<!-- image -->

.

- Delete to delete the selected observer. Clear the check box Confirm under File &gt; Preferences &gt; Modeling &gt; Delete objects to delete the observer without prompting you to confirm.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

addObserver [SimTalk]

attributeWatchable [SimTalk]

getObservers [SimTalk]

removeObserver [SimTalk]

removeAllObservers [SimTalk]

See also

Create and Delete an Observer

Watchable Values

**New [observer]**

To create a new observer, click New . This only works if the attribute or the method of the object is watchable.

<!-- image -->

**Observed value**

Select the watchable attribute or read-only attribute , whose value you want to watch.

<!-- image -->

To check which attributes and read-only attributes of an object are watchable, select the object and press F8 . Watchable attributes and read-only attribute are marked with an asterisk ( * ) in the column Watchable in the window Show Attributes and Methods .

<!-- image -->

**Executed method**

Select the Method , which is going to be executed, when the value of the Attribute or of the Read-only attribute changes. The name of the attribute / method and the previous value of the attribute / method are passed to the executed Method as parameters.

To use a user-defined attribute of data type method as the Method , click the right mouse button in the field Method and select the command Create Control . Then, Plant Simulation automatically formats the Method correctly.

If the watched value changes several times while an event is processed, the executed method is only called once.

Click OK to add the observer.

The list field shows the name of the Attribute or the Method , the name of the Method that is going to be executed, and if the object inherits the observer from its class.

When you add the observer to the instance of the object, which you inserted into a Frame , it shows an asterisk * in the column Created here .

<!-- image -->

To execute several Methods for the same attribute or read-only attribute , click New again, select the same attribute and add an additional method .

SimTalk

addObserver [SimTalk]

attributeWatchable [SimTalk]

See also

Create and Delete an Observer

Watchable Values

**Edit [observer]**

To change the watchable attribute or read-only attribute , which the selected observer watches, and the Method , which is going to be executed, click Edit .

<!-- image -->

<!-- image -->

To open the dialog for selecting the watched value, you can also click the button in the text box Observed Value in the dialog Observers .

<!-- image -->

To open the window of the Method , which will be executed, you can also click the button in the text box Method .

<!-- image -->

**See also**

Watchable Values

**Delete [observer]**

Delete [observer]

To remove the selected observer, click

<!-- image -->

SimTalk

removeObserver [SimTalk]

removeAllObservers [SimTalk]

attributeWatchable [SimTalk]

getObservers [SimTalk]

See also

Create and Delete an Observer Delete

.

###### 3D [create object]

To create the selected object in 3D when you start 3D , select the check box.

To not create it, for example because you do not need it in your 3D model, clear the check box

<!-- image -->

By default, we activated this feature for all simulation-relevant objects, such as the material flow objects , the fl uid objects , the moving objects , the resources , and the tools .

3D can also show the icons of most of the objects, which are not relevant for 3D, such as the information flow objects , in the 3D scene. To do so, double-click the icon of the respective object in the Toolbox and select Tools &gt; 3D . Then, select the check box Create in 3D .

Instead, you can also select the class of the object in the Class Library , press F8 , and double-click the attribute CreateIn3D so that it shows true .

<!-- image -->

If you then insert an instance of this object into the 3D Scene , it shows the icon of the object. You can then right-click the icon and select Open 2D Counterpart to open the dialog of the object in 2D.

**Note**

If you clear the check box for an object class and then select it again, Plant Simulation restores the built-in state of the object. It discards all changes that you made to the class of the simulation object.

**Note**

If Create in 3D is deactivated in the origin of an object, then Create in 3D is deactivated in the object itself as well and cannot be activated.

SimTalk

**CreateIn3D [SimTalk]**

See also

Home ribbon tab &gt; Edit 3D Properties &gt; Create in 3D

###### Inherit 'Entrance/Exit Locked' On Reset

Reactivates inheritance of the settings Entrance Locked and Exit Locked when resetting the model. The command shows it with a check mark to the left.

For new models the command is activated by default.

In models, which you created in previous versions of Plant Simulation , the command is deactivated.

<!-- image -->

<!-- image -->

**SimTalk**

InheritEntranceExitLockedOnReset [SimTalk]

inheritAttribute [SimTalk] - object

EntranceLocked [SimTalk] - material flow objects

###### ExitLocked [SimTalk] - material flow objects

See also

Exit Locked [material flow objects]

Entrance Locked [material flow objects]

Reset Simulation [EventController]

###### Random Seed Value

Shows the random seed value of the selected object.

<!-- image -->

**Note**

Only the material flow objects and the fl uid objects , which can create random numbers, provide this command.

To change the random seed value, select the command and type in another value into the dialog.

<!-- image -->

**Remarks**

Plant Simulation keeps a common seed value in the object. Plant Simulation automatically assigns the random number value when inserting an object, but only if the object can create random numbers. This is then the case when the object itself can create random numbers, for example a Station for its Processing Time , or when the object has a user-defined attribute of data type Method or RandTime . If both is not the case, Plant Simulation assigns the value 0 to the attribute RandomSeed when inserting the object. If the value of the attribute RandomSeed is 0, the attribute will not be shown in the window Show Attributes and Methods and will not be written to the folder model. When you create a user-defined attribute of data type Method or RandTime for such an object, Plant Simulation sets a random number value automatically as well.

**SimTalk**

RandomSeed [SimTalk] - material flow objects RandomSeed [SimTalk] - fluid objects RandomSeed [SimTalk] - Method/User-defined Attribute Video on YouTube https://youtu.be/HKDhTbohV6M?si=aHiNrXBQoamJuMCI&amp;t=292

Tabs Menu

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

Help Menu

Help Menu [in object dialogs]

The Help menu provides the commands Contents , Help on Object , and Help on Dialog .

Contents

The command Contents opens the table of contents of the Plant Simulation help.

Help on Object

The command Help on Object opens the help topic pertaining to the selected object.

Help on Dialog

The command Help on Dialog opens the help topic pertaining to the dialog Edit 3D Properties if this dialog is open.

Using Online Help

Using Online Help describes the different ways of using and searching in the help.

