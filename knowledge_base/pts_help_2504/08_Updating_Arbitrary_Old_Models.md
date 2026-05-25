# 8. Updating Arbitrary Old Models

## Update Arbitrary Old Models

When you created a model in any previous version of Plant Simulation , you will want to open this model in a newer or the current version and continue working with it. You'll naturally also want to use the new functions of the newer or the current version.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to and including the respective current version.

Compare Open the Dismantle Model in 3D

Also consult the Plant Simulation Step-by-Step Help

Getting to Know Plant Simulation

Modeling the Material Flow

Visualizing the Material Flow in 3D

Animate the Simulation Model in 2D and View the Results

Import Data for the Simulation

Set Parameters in the Model

Also consult the Plant Simulation Reference Help

What's New

The Objects Reference Help

The SimTalk Reference

Outdated SimTalk Names

The 3D Help

SimTalk Access to 3D

The Quick Reference Cards The Add-Ins Reference Help The Libraries Reference

## Open an Old Model in a Newer Version

When you created a model in a previous version of Plant Simulation , you will want to open this model in a newer or the current version and continue working with it. You'll naturally also want to use the new functions of the newer version.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

**Note**

In old models 3D &gt; Create In 3D is deactivated for non-simulation-relevant objects, for example for the Method , the DataTable , etc. The model then does not show these objects in the current version. To show these objects, select the class of the object in the Class Library , press F8 , and double-click the attribute CreateIn3D so that it shows true .

Some of the adjustments you have to do manually, while Plant Simulation provides built-in functions for others:

- To convert the source code of the methods, which you programmed in SimTalk 1.0 syntax , to SimTalk 2.0 syntax , use the command Convert all Methods to New Syntax .

<!-- image -->

- To use the current built-in graphics in your model, use the command Revert all Objects to Standard Graphics .
- To use the built-in names of the current version of Plant Simulation when opening a model you created a previous version, first select the command Revert all Objects to Standard Graphics . This replaces the old icon with the new icon. Let's illustrate this with the object Conveyor which was called Line in previous English versions.

If you open such a model in the current version of Plant Simulation , and select Revert all Objects to Standard Graphics , it automatically replaces the old icon of the Conveyor with its current icon. If the model contains instances of the object though, Plant Simulation does not replace the old name with the current name. To use the current name, select the object in the Class Library and rename it manually. This changes the name in the Class Library , in the Toolbox , and in all inserted instances in Frames . You then still have to replace the old name of the object with the new name in the source code of Methods .

- To replace instances of objects from previous versions of Plant Simulation with the new class of this object, with another 2D icon, hold down Alt and drag-and-drop the class object from the Class Library to the instance of the object which you want to replace in the Frame .

In this example we open an old model, which we created in Plant Simulation 12. The model contains derived and duplicated objects and shows the 3D objects with the graphics of version 12. The model looks like this in 2D and in 3D in version 12:

<!-- image -->

We used the object Method as an instance, as a duplicated Method , and as a derived Method . The labels of the objects show this. We programmed the source code in SimTalk 1.0 syntax .

- The object MyMethod is an instance of the class Method in the folder InformationFlow .
- The object Method1 is a duplicate of the class Method .
- The object Method2 is a derivation of the class Method .

<!-- image -->

- 3D does not show the Methods in the Frame in Version 12.

**Note**

To show the Methods in version 15 and higher, open their class, press F8 , scroll to the attribute CreateIn3D , and double-click it so that it shows true .

<!-- image -->

The graphics of the 3D objects in version 12 look considerably different from the graphics in higher versions.

<!-- image -->

Now we open the model in Plant Simulation 16.1 and save it with the name MyWarehouseVersion161.spp . It looks then like this.

<!-- image -->

Then we update all libraries by clicking Manage Libraries to prevent Plant Simulation from repeatedly displaying the message bar .

If we want to continue modeling in 3D Only , we can:

- Use the Standard Graphics of the 3D Simulation Objects
- Use New Standard Graphics of the 2D Objects
- Open an Old Model in a Newer Version

Back to Update Arbitrary Old Models

## Show Non-Simulation-Relevant Objects

Describes how to show non-simulation-relevant objects in your simulation model.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In previous versions Plant Simulation by default only showed objects in 3D, which were relevant for the flow of materials. For this reason most of the Resource Objects , the Information Flow Objects , and the User Interface Objects were not shown when you opened such a model in a higher version.

In this example we opened a model in Plant Simulation 16.1 which we created in Plant Simulation 11 .

Plant Simulation 16.1 then only shows the Material Flow Objects and the Chart .

<!-- image -->

To also show the Resource Objects , the Information Flow Objects , and the User Interface Objects :

- Click the respective object in the Class Library with the left mouse button and press the F8 key.
- Press the C key and scroll to CreateIn3D .
- Double-click CreateIn3D so that it shows true .

<!-- image -->

- Repeat this for all objects that you want to show. After we reverted the default graphics of all objects, the model looks like this.

Back to Update Arbitrary Old Models

<!-- image -->

## Convert the Source Code of All Methods to SimTalk 2.0

Describes how to convert the source code of the used Methods from SimTalk 1.0 syntax to SimTalk 2.0 syntax to make use of the enhanced functions.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In this example we are going to convert the source code of all Methods in the model from SimTalk 1.0 syntax to SimTalk 2.0 syntax .

- To convert the source code of all Methods in the model to SimTalk 2.0 syntax , hold down Shift and click the right mouse button on Basis in the Class Library . Then, select the command Convert all Methods to New Syntax .

<!-- image -->

The source code of our Methods then looks like this as compared to the model from the previous version:

<!-- image -->

- To only convert the Methods in a certain folder in the model to SimTalk 2.0 syntax , hold down Shift and click the right mouse button on the respective folder in the Class Library . Then, select the command Convert all Methods to the New Syntax .

Back to Update Arbitrary Old Models

## Replace Outdated Functions in the Source Code

When you open a model that was created in a previous version of Plant Simulation , it is likely that Plant Simulation detects that it contains no longer supported SimTalk functions.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

When you run the Method , Plant Simulation shows this in the status bar. In our example the function promptMessage is no longer supported.

Consult Outdated SimTalk Names to see which new function replaced the outdated function promptMessage . This is the function messageBox in our example.

<!-- image -->

You can now just replace promptMessage with messageBox in the current Method by pressing Ctrl+H and then running the Method again to make sure that it is executed without errors.

Plant Simulation shows outdated functions in the source code with this color .

<!-- image -->

To replace all occurrences in all Methods in the model, click Find Outdated Functions on the Debugger ribbon tab. This opens a dialog that shows all Outdated Methods, Attributes, and Functions .

<!-- image -->

When you double-click promptMessage , the dialog Find and Replace shows all occurrences in the model and enters promptMessage into the text box Find what .

Then type messageBox into the text box Replace with , click Find Next , and replace the individual occurrences in the Methods which Plant Simulation opens one after the other.

<!-- image -->

Back to Update Arbitrary Old Models

## Use the Standard Graphics of the 3D Simulation Objects

Describes how to use changed standard graphics of the 3D simulation objects.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In this example we want to use the built-in standard graphics of version 15 or higher for the 3D simulation objects. We changed the default depictions (icons, 3D-graphics) of a number of objects in version 14.

- To use the new standard graphics of all 3D simulation objects, hold down Shift , and click the right mouse button on Basis in the Class Library . Then, select the command Revert all Objects to Standard Graphics .

**Note**

The command only affects object classes, not instances whose graphics you changed. The command only replaces the standard graphics of the object, it does not replace the previous simulation settings with the new settings!

<!-- image -->

The new 3D standard graphics in the model look like this as compared to the model from the previous version:

<!-- image -->

- To only use the standard graphics in a certain folder, hold down Shift and click the right mouse button on the respective folder in the Class Library .

Then, select the command Revert all Objects to Standard Graphics .

Back to Update Arbitrary Old Models

## Adjust Color and Sizes of Objects

Describes how to adjust the color and the size of objects in your simulation model.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In this example we are going to adjust the color and the sizes of the mobile objects ( MUs ) which changed between versions.

You have to do this manually, as the command Revert all Objects to Standard Graphics neither adjusts the color of the Connector nor the size of the MUs to the current settings.

- In previous versions of Plant Simulation the Connector was black, in the current version it is blue. To adjust the color of the Connector , open the dialog of the Connector in the Class Library . Click in the color field and then on the tab Custom in the dialog Color .

Select these settings and click OK :

<!-- image -->

| Hue   |   156 | Red   |   51 |
|-------|-------|-------|------|
| Sat   |   153 | Green |  102 |
| Lum   |   128 | Blue  |  204 |

- In previous versions of Plant Simulation the mobile objects Part , Container , and Transporter had different dimensions. In the current version they have the dimensions shown below. Open the class of the respective object and type in the new dimensions.

<!-- image -->

<!-- image -->

Back to Update Arbitrary Old Models

<!-- image -->

## Fix Animation Problems in 3D

Describes how to fix animation problems in 3D.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In this example we fix animation problems in 3D as MUs might not be animated at the correct position on the material flow object in rare cases.

Compare these examples:

- Here the Part is not displayed on the floor of the lattice box, but with an offset to the right and upward .

<!-- image -->

To fix this, show the animation path on which the Part is going to be animated. The red path marker shows the position at which the Part is going to be animated.

<!-- image -->

Click Edit and check the values of the X-position , the Y-position , and the Z-position in the dialog Path Anchor Points . The animation point is obviously located at the wrong position.

<!-- image -->

Double-click row 1 or click Edit Values and type in the default values for the animation point on the Drain .

<!-- image -->

- Here the Part is displayed with an offset to the left in the direction of motion on the Conveyor :

<!-- image -->

To fix this, check the booking point width of our square Part . It is located at the position 0.2 , which is wrong.

To animate the Part in the center of the Conveyor , booking point length and booking point width of our square Part have to be located in the center at the position 0.5

<!-- image -->

- Here the Part is displayed on the Conveyor with an offset toward the bottom . It seems to sink into the conveyor belt.

<!-- image -->

To fix this, check the setting MU Side to Attach on the tab MU Animation . In this case the booking point height has the value 0.5 and MU side to attach is the Booking Point . The booking point of the Part is located in the center of its bottom side, for this reason the Part seems to be sinking into the conveyor belt.

The default setting booking point height &gt; 0 and MU side to attach &gt; Bottom shows the part correctly.

<!-- image -->

- Here an empty pallet , which moves to the AssemblyStation , overlaps the loaded pallet that is still located there.

<!-- image -->

To fix this problem, we have to make the AssemblyStation wider. Click the AssemblyStation and press the M key to Show Manipulators . Click the left border of the AssemblyStation and press the left arrow key until the pallets do not overlap anymore.

Back to Update Arbitrary Old Models

<!-- image -->

## Use New Standard Graphics of the 2D Objects

Describes how to use changed standard graphics of the 2D objects.

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

In this example we are going to replace the outdated icon of the Track in our existing simulation model with the icon of the Track of version 15 and higher.

Our model from a previous version looks like this:

<!-- image -->

To use this icon in our model:

- Start the new version of Plant Simulation . Right-click the Track in the Class Library and select Save Object As . This saves the Track as an object file named Track.psobj .
- Open the existing model in the new version of Plant Simulation .
- Right-click the folder MaterialFlow in the Class Library and select Save/Load &gt; Object .
- Select the object file Track.psobj that you just saved. This replaces the existing class of the Track with the new class which has a different icon and a different width in our example.
- This only replaces the class in the Class Library though, not the instances in our simulation model.
- To replace the instances of the Track with the new class one by one, hold down Alt , right-click the Track in the Class Library , and drop the Track on the instance in the Frame .

<!-- image -->

Click Yes to keep the existing settings of the instances of the Track of the previous version. In our example it had a width of 1 meter.

Click No to apply the settings of the new class. The width of the new class is 0.3 meters.

<!-- image -->

<!-- image -->

- Repeat this until all classes are replaced.

<!-- image -->

If you just have to change a few settings, you can proceed as described below. The model contains inserted instances of the object Track , inserted instances of the derived class of the Track , and inserted instances of the duplicated class of the Track .

- The model in version 14 looks like this:

<!-- image -->

- When you open the model in the newer version and select Revert all Objects to Standard Graphics , Plant Simulation replaces the previous icon of the Track in the Toolbar with the new icon.
- To replace the previous settings of the Track with the new settings of the Track , proceed as follows:
- Open the class of the Track in the Toolbox .
- Type in the new Width of 0.3 meters of the class on the tab Attributes .

<!-- image -->

Click Apply to show the inserted instances of the Track and the derived Track with this changed Width .

<!-- image -->

- Then, set the new color and the new midline style of the class on the tab Curve in 2D.

Click Apply to show the inserted instances of the Track and of the derived Track with this color and with this midline style.

<!-- image -->

<!-- image -->

- As Plant Simulation created a new class from the duplicated class of the Track , which has no inheritance relations with the original class, you have to also execute the last two steps for our class TrackDuplicated . This then looks like this:

Back to Update Arbitrary Old Models

<!-- image -->

## Add Missing Objects to the Model

Describes how to add missing objects to your simulation model, for example objects we added to a new version of Plant Simulation .

**Note**

The techniques we describe apply to updating arbitrary old models to any of the newer versions up to the respective current version.

The simulation model from an old version might not show objects, for example the Fluid Objects , that we added in newer versions of Plant Simulation .

Proceed as follows to add missing objects to your model:

- Click the Start ribbon tab.
- Click Manage Class Library all the way to the right on the tab.
- Select the check boxes for the objects you would like to add and click OK .

<!-- image -->

<!-- image -->

Back to Update Arbitrary Old Models

## Save a Model as a 3D Only model

Describes what you need to do when saving a simulation model as a 3D only model.

Let's say you have an old model using the 2D and 3D visualization. You now want to save this model as a 3D only model and continue working with it.

We recommend to always create your models in 3D only mode . This also applies if you are only interested in the 2D view. You can model in Planning View in 3D, which corresponds to the top view in 2D. In addition, you can continuously zoom in the 3D window and 3D has better performance than 2D.

Proceed as follows to save the 2D and 3D model as a 3D only model :

- Open the model in the Plant Simulation version you are working with.
- Select File &gt; Save As and save the model with a new name. We entered MyWarehouseVersion2201\_3DOnly.spp in our example.
- Select File &gt; Model Settings and click 3D only under Visualization . Click OK .

<!-- image -->

<!-- image -->

- Close the model and reopen it. Plant Simulation discarded the 2D part of the model and only shows it in 3D.

<!-- image -->

- Then, hold down Shift , right-click .Basis and select Revert all Objects to Standard Graphics to show the objects with their current depiction.

<!-- image -->

You can use the same procedure to create a 2D model from a 2D and 3D model or from a 3D model .

**Note**

We strongly recommend to create your models either in 3D only or in 2D only mode.

We strongly advise against creating your models in 2D and 3D mode. The setting 2D and 3D is intended to convert a 2D model to a 3D model.

Back to Update Arbitrary Old Models

## Create a 3D Model from a 2D Model

These topics show how we adapted a simulation model that we originally created in 2D to 3D:

- Model Transitions Between Frames
- Create a User-defined Attribute During the Simulation
- Model a Worker Who Carries Several Parts in 3D
- Modeling a Lockout Zone &gt; Specify the Stations Which the LockoutZone Stops
- Assemble Parts with the AssemblyStation
- Remove Parts with the Dismantle Station
- Convert the Production Line Model to a 3D Model
- Open the Robot Model in 3D
- Change the Conveying Direction with the AngularConverter
- Adjust Shrinkwrapper and Parts in 3D
- Change the Shape of a Segment

Back to Update Arbitrary Old Models

