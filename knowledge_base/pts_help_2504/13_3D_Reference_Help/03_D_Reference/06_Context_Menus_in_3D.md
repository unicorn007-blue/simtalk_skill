### Context Menus in 3D

3D provides context menus with commands referring to your current location in 3D and to your modeling situation.

- Context Menu of the Selected Simulation Object
- Context Menu of Several Selected Objects
- Context Menu of a Sub-Frame [Show Content on]
- Context Menu of the Selected Graphic
- Context Menu of an Object in the Graphic Structure
- Context Menu of a Graphic in the Graphic Structure
- Context Menu of a Graphic Group
- Context Menu of a Simulation Object
- Context Menu of Anchor Points of a Path
- Context Menu of the Background of the Scene

#### Context Menu of the Selected Simulation Object

Context Menu of the Selected Simulation Object

Click an object with the right mouse button in the 3D scene to select it. 3D then shows a context menu with the commands pertaining to the selected simulation object.

You can also close the context menu and leave the mini toolbar open clicking the border of the mini toolbar with the left mouse button.

<!-- image -->

Normal animatable objects and animatable length-oriented objects provide different context menu commands.

<!-- image -->

Don't confuse the selected object in 3D with the selected graphic of the object in 3D!

Green denotes that an object is selected . A yellowish green denotes that a graphic is selected , meaning that you can use the + key to contract the selection along the graphic structure.

Except for the Frame , Plant Simulation shows a selected simulation object with a green border on the inside in the 3D window.

<!-- image -->

| Open Origin           | Show Inheritance             |
|-----------------------|------------------------------|
| Open Class            | Show Statistics Report       |
| Cut                   | Show Attributes and Methods  |
| Copy                  | Edit User-defined Attributes |
| Delete                | Stop at Next Event           |
| Open                  | Controls [in Frame]          |
| Open in New 3D Window | Hide                         |
| Edit 3D Properties    | Align to Grid                |
| Rename                | Exchange Graphics            |

| Reorder Successors        | Use as Animation Object   |
|---------------------------|---------------------------|
| Show Structure            | Show Manipulators         |
| Show 3D Graphic Structure | Segments                  |

**Cut [simulation object]**

##### Cut [simulation object]

To cut the object you selected with the right mouse button from the scene and places it onto the clipboard, select this command.

You can then paste it from there, provided that in the meantime you did not cut or copy anything else to the clipboard.

**Note**

If the object you cut has derivatives, i.e., objects that were derived and inherit settings from it, 3D opens a dialog asking you to confirm that these derivatives will be deleted.

##### Copy [simulation object]

To copy the selected object to the clipboard, select this command. You can then paste it from there into the currently active scene.

Instead of using the Copy button or the command Copy on the Home ribbon tab, you can also use drag-and-drop to copy an object and insert it either into the same scene or into another one. Click the object with the left mouse button, hold the mouse button down, drag the object to a location of your choice and drop it there.

**Delete [simulation object]**

##### Delete [simulation object]

To delete the selected simulation object from the scene for good, select this command.

3D opens a dialog asking you to confirm that you are going to delete the simulation object and its derivatives.

##### Open [simulation object]

To open the selected object in 3D in the active 3D window, select this command.

See also

Open in 3D [object class]

Open in New 3D Window [simulation object]

To open the selected object in 3D in a new 3D window, select this command.

Instead, you can also hold down Shift and double-click the object in the Frame window .

##### Hide [simulation object]

To hide the object which you clicked with the right mouse button from view in the scene window, select this command.

To show a hidden object again in the scene window, click Unhide Objects on the View ribbon tab.

**Stop at Next Event**

##### Stop at Next Event

To set a breakpoint in the Event Debugger at the next scheduled event of the selected object, select this command.

<!-- image -->

This makes debugging your model easier.

<!-- image -->

##### Use as Animation Object

To set the selected object as the animation object that animates MUs for its simulation object, select this command.

<!-- image -->

If the simulation object offers MU animations or can use a MU animation area in principle, even if it is not currently used, Plant Simulation asks if you want to copy the MU animations to the selected animatable object.

<!-- image -->

If you click Yes , Plant Simulation copies the Animation Area (including the setting that specifies whether to use it) from the simulation object to the animatable object. If the simulation object does have any MU animation paths , the command copies these and overwrites all animation paths which the animatable object had beforehand. This includes animation paths with names that the simulation object did not have.

The command enters the name of the animation object into the text box Animation object .

<!-- image -->

**See also**

Animation Object

Add Animatable Object

Make Animatable Object

MUAnimations.copyFromSimulationObject [SimTalk]

Create a Simulation Object with Animation

##### Show Manipulators [context menu]

To show or hide the manipulators of objects and graphics, select this command.

Instead, you can also press M on the keyboard.

Compare the detailed description of command under Show Manipulators .

See also

Button Show Manipulators [button]

Segments

Segments [3D]

Provides submenu commands pertaining to Segments .

Append

Edit

Reverse

Split Up

See also

Show Manipulators [button]

Segments [2D]

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

**Append [segment 3D]**

###### Append [segment 3D]

To append one or more anchor points to the end of the length-oriented curved object, right-click the object. Then select Append and click in the Frame window on the positions at which you would like to add the new points/segments one after the other.

You can select additional settings in the dialog Line/Arc Parameters .

Hold down Ctrl to append a curved segment. Plant Simulation then connects the last anchor point with the one you just appended.

Click the right mouse button or press Esc to terminate append mode.

See also

Tab Curve [general description]

Segments [2D] &gt; Append [segment, 2D]

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Work with Length-oriented Objects in 2D and 3D

Video on YouTube

[https://youtu.be/Kznlnw5BJGc?si=DP96dl1vsmdS\_BsA&amp;t=218](https://youtu.be/Kznlnw5BJGc?si=DP96dl1vsmdS_BsA&t=218)

###### Edit [segment 3D]

To edit the selected segment of the length-oriented curved object, right-click it and select Edit . Instead, you can also press the F7 key.

Then edit the settings of the object in the Segments table that opens.

Click Apply or OK , to apply your changes.

<!-- image -->

**See also**

Segments [2D] &gt; Edit [segment, 2D]

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Show Manipulators [context menu]

Video on YouTube

[https://youtu.be/Kznlnw5BJGc?si=XgDbN5GwLrNOkuBS&amp;t=296](https://youtu.be/Kznlnw5BJGc?si=XgDbN5GwLrNOkuBS&t=296)

**Reverse [segment, 3D]**

###### Reverse [segment, 3D]

To change the direction of motion of the curved object, i.e., to make the last point of the object the first point, right-click the object and select Revert .

This is especially handy if you want to mirror the layout of a production line by copying it and then reversing the direction of motion of the mirrored line to ensure a circular flow of materials.

<!-- image -->

SimTalk

**reverse [SimTalk]**

See also

Segments [2D] &gt; Reverse [segment, 2D]

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Show Manipulators [context menu]

Context Menu of the Selected Object in the Frame

Change the Shape of a Segment

###### Split Up [segment 3D]

To split the length-oriented objects FootPath , Pipe , Conveyor , Track , or TwoLaneTrack into individual separate segments at the selected point, click the point where you would like to split it up and select Split Up .

Plant Simulation creates a copy of the object and splits the object up into two parts at the mouse position. Plant Simulation distributes Sensors according to their position to both objects. The same applies for the Entrance Controls , for the Exit Controls , and for Connectors .

This looks like this in 2D and in 3D:

<!-- image -->

3D shows the point at which the segments were split up on the split segments. If necessary 3D also adds additional pairs of legs to the Conveyors .

See also

Segments [2D] &gt; Split Up [segment, 2D]

Segments [curve] - 2D, described

Segments [tab Appearance] - 3D

Show Manipulators [context menu]

Change the Shape of a Segment

Context Menu of the Selected Object in the Frame

##### Context Menu of Several Selected Objects

#### Context Menu of Several Selected Objects

Select several objects by dragging a marquee around them. Instead, you can also hold down Shift or Ctrl and click the objects one after the other with the left mouse button. Then click one of the selected objects with the right mouse button to open the context menu.

You can also close the context menu and leave the mini toolbar open clicking the border of the mini toolbar with the left mouse button.

<!-- image -->

<!-- image -->

<!-- image -->

Hide Objects [context menu] To hide the selected objects from view, select this command. Instead, you can also click Hide Objects on the View ribbon tab

To show them again, click Unhide Objects on the View ribbon tab.

**Zoom to Objects [context menu]**

##### Zoom to Objects [context menu]

To center and zoom the selected object in the scene window, select this command. Then you can closely inspect and manipulate the objects.

Instead, you can also click Zoom to Objects on the View ribbon tab. To show all objects in the scene again, click Show All .

##### Group Graphics [context menu]

To group the selected graphics and combines them into one object, select this command. This combined graphic then contains the selected graphics.

To break the group down into the individual graphics again, click the group with the right mouse button and select Ungroup .

Instead, you can also click Group Graphics on the Edit ribbon tab .

To break the group down into the individual graphics again, select Ungroup Group of Graphics .

**Create Tugger Train [3D]**

##### Create Tugger Train [3D]

To create a tugger train , right-click the first and the last Transporter , which you would like to hitch to each other, and select this command.

The tractor and all trailers do not have to touch, as long as all Transporters are located all the way on the same Track . If necessary Plant Simulation moves the other Transporters up to the frontmost Transporter or tractor .

<!-- image -->

**See also**

Model Tugger Trains

Arrange Objects

##### Arrange Objects

To arrange simulation objects or graphics along the selected coordinates or distribute them in the selected direction, select this command.

<!-- image -->

You might, for example, use the Align commands to correct misaligned Markers . This might occur if you insert Markers into your model while Show Grid is off.

2D provides similar functions under Arrange Icons .

The command provides these sub-commands:

| Align X-Coordinates       | Distribute in Y-Direction       |
|---------------------------|---------------------------------|
| Align Y-Coordinates       | Distribute in Z-Direction       |
| Align Z-Coordinates       | Align to Grid [3D context menu] |
| Distribute in X-Direction | Undo [3D] , Redo [3D]           |

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=EDEUAQkBcAolWYPB&amp;t=1404](https://youtu.be/jHOZhlwGhkQ?si=EDEUAQkBcAolWYPB&t=1404)

###### Align X-Coordinates

To align the x-coordinates of the selected objects, select this command.

The command sets the x-coordinate of the selected objects to the x-coordinate of the object under the mouse pointer.

<!-- image -->

See also

Undo [3D]

Redo [3D]

###### Align Y-Coordinates

To align the y-coordinates of the selected objects, select this command.

The command sets the y-coordinate of the selected objects to the y-coordinate of the object under the mouse pointer.

<!-- image -->

See also

Undo [3D]

Redo [3D]

###### Align Z-Coordinates

To align the z-coordinates of the selected objects, select this command.

The command sets the z-coordinate of the selected objects to the z-coordinate of the object under the mouse pointer.

<!-- image -->

See also

Undo [3D]

Redo [3D]

###### Distribute in X-Direction

To distribute the selected objects in equal distances to each other in the x-direction, select this command.

<!-- image -->

See also

Undo [3D]

Redo [3D]

###### Distribute in Y-Direction

To distribute the selected objects in equal distances to each other in the y-direction, select this command.

<!-- image -->

See also

Undo [3D]

Redo [3D]

###### Distribute in Z-Direction

To distribute the selected objects in equal distances to each other in the z-direction, select this command.

<!-- image -->

See also

Undo [3D]

Redo [3D]

**Align to Grid [3D context menu]**

###### Align to Grid [3D context menu]

To move the selected objects to the next projected intersecting point of the grid lines, select this command.

To move the selected objects to the grid level, hold down Ctrl while selecting the command.

Instead, you can also click Align to Grid on the Edit ribbon tab.

###### Transformation Inheritance

##### Transformation Inheritance

To set inheritance of the settings shown on the submenu, select the respective command on the submenu.

| Inherit Positions   | Inherit Scalings   |
|---------------------|--------------------|
| Inherit Rotations   | Inherit All        |
| Inherit Mirrorings  | Undo , Redo        |

The submenu commands only apply to several selected simulation objects, not to graphics as they do not provide individual inheritance.

###### Inherit Positions

To activate inheritance of the positions of the selected simulation objects and of the anchor points of the Connectors , select this command.

See also

Undo [3D]

Redo [3D]

**Inherit Rotations**

###### Inherit Rotations

To activate inheritance of the rotations of the selected simulation objects, select this command.

See also

Undo [3D]

Redo [3D]

###### Inherit Mirrorings

To activate inheritance of the mirrorings of the selected simulation objects, select this command.

The Frame in 2D provides the command Inherit Size and Orientation as counterpart.

See also

Undo [3D]

Redo [3D]

###### Inherit Scalings

Inherit Scalings

To activate inheritance of the scalings of the selected simulation objects, select this command.

See also

Undo [3D]

Redo [3D]

###### Inherit All

To activate inheritance of the positions, the rotations, the mirrorings, and the scalings the selected simulation objects, select this command.

##### Show Statistics Report [3D]

Show Statistics Report [3D]

To open the Statistics Report of the selected objects, select this command.

SimTalk

showStatisticsReport [SimTalk]

See also

Statistics Report [described]

Show Statistics Report [in Frame]

Viewing the Statistics Report

#### Context Menu of a Sub-Frame [Show content on]

Context Menu of a Sub-Frame [Show Content on]

The context menu of an object, which you selected in a sub-Frame and for which Show content is activated, shows a number of commands.

<!-- image -->

**See also**

| Open [simulation object]                  | Show Statistics Report [3D]                |
|-------------------------------------------|--------------------------------------------|
| Open in New 3D Window [simulation object] | Show Attributes and Methods [described]    |
| Edit 3D Properties [selected graphic]     | Edit User-defined Attributes [Home ribbon] |
| Set How 3D Shows an Object                |                                            |

#### Context Menu of the Selected Graphic

Context Menu of the Selected Graphic

Click a graphic with the right mouse button in the 3D scene to select it. 3D then shows a context menu.

<!-- image -->

<!-- image -->

| Cut [3D graphic]                         | Make Animatable Object      |
|------------------------------------------|-----------------------------|
| Copy [3D graphic]                        | Make Simulation Object      |
| Delete [3D graphic]                      | Optimize Selected Graphic   |
| Paste [3D graphic]                       | Ungroup [3D graphic]        |
| Edit 3D Properties [selected graphic]    | Remove Texture [3D graphic] |
| Show Graphic Structure [3D context menu] |                             |

You can also close the context menu and leave the mini toolbar open clicking the border of the mini toolbar with the left mouse button.

<!-- image -->

Don't confuse the selected graphic of the object with the selected object in 3D!

A yellowish green denotes that a graphic is selected , meaning that you can use the + key to contract the selection along the graphic structure.

Green denotes that a simulation object is selected .

<!-- image -->

**Cut [3D graphic]**

##### Cut [3D graphic]

To cut the selected objects and graphics to the clipboard, select this command.

You can copy and paste graphics that are contained within other graphics. When doing so the copy retains the settings of the transformation and material of the original, including all transformations and materials which are not defined for the graphic itself, but for the graphics contained within this graphic.

Not included are transformations and materials, which are defined for the object, for example scaling (or the attribute \_3D.Scale ) or the object material of a MU .

##### Copy [3D graphic]

To copy the selected objects and graphics to the clipboard, select this command.

You can copy and paste graphics that are contained within other graphics. When doing so the copy retains the settings of the transformation and material of the original, including all transformations and materials which are not defined for the graphic itself, but for the graphics contained within this graphic.

Not included are transformations and materials, which are defined for the object, for example scaling (or the attribute \_3D.Scale ) or the object material of a MU .

**Paste [3D graphic]**

##### Paste [3D graphic]

To insert the graphic from the clipboard into the selected graphic group, select this command.

When you paste a graphic into a graphic group of a 3D object which inherits its graphics, Plant Simulation asks if you want to cut graphic inheritance for this object or not. Plant Simulation only pastes the graphic if you cut graphic inheritance by clicking Yes .

##### Delete [3D graphic]

To delete the selected graphic, select this command.

##### Edit 3D Properties [selected graphic]

Depending on the type of graphic and the context it shows the Tab Transformation , the Tab Material , and the Tab Graphic Settings . A number of shapes show their settings on shape-specific tabs.

See also

Edit 3D Properties [dialog]

Show Graphic Structure [3D context menu]

To open the window Show Graphic Structure , select this command. It shows the graphic structure of the simulation object.

See also

Show Graphic Structure [3D button]

##### Ungroup [3D graphic]

Ungroup [3D graphic]

To ungroup the selected JT group node which has to contain at least one child node, select this command.

Ungroup also ungroups grouped graphics.

See also

Group Graphics [context menu]

##### Remove Texture [3D graphic]

To remove an existing texture from the selected 3D graphic, select this command.

<!-- image -->

#### Context Menu of an Object in the Graphic Structure

Context Menu of an Object in the Graphic Structure

Click with the right mouse button on a graphic and select Show Graphic Structure to display the structure of the graphic. Then click an object with the right mouse button to show its context menu:

<!-- image -->

#### Context Menu of a Graphic in the Graphic Structure

Context Menu of a Graphic in the Graphic Structure

Click with the right mouse button on a graphic and select Show Graphic Structure to display the structure of the graphic. Then click a graphic node with the right mouse button to show its context menu:

<!-- image -->

##### Show [graphic]

To show the selected graphic of the object in its own 3D window, select this command.

<!-- image -->

**Paste [graphic]**

##### Paste [graphic]

To insert the graphic from the clipboard into the graphic of the object if this is a group node, select this command.

##### Optimize [graphic]

Opens the dialog Optimize Selected Graphic of non-automatically generated graphic groups opens a suitable window, highlights the graphic, and . Select the settings for optimizing the graphic group there.

See also

Generated and Non-Generated Graphics

Optimize Selected Graphic

**Remove Texture [graphic]**

##### Remove Texture [graphic]

To remove an existing texture from the selected graphic, select this command.

See also

removeTexture [SimTalk]

##### Move Transformations to Graphics

To move transformations as far as possible to the lowest child graphics in the structure, select this command.

The command is unavailable if the current entry does not contain any transformation. If you want to process all nodes below the current node, hold down Shift while opening the context menu.

Moving the transformation to the child graphics is canceled when

- the child graphic of the instance node, designated by the diamond ♦ , has more than one parent nodes or
- a graphic has a texture, designated by a T

Plant Simulation only moves the transformation to the raw data of a non-grouped graphic for graphics of type TriStripSet and Polyline.

Note

This deactivates graphic inheritance.

See also

Show Graphic Structure [3D button]

Undo [3D]

Redo [3D]

Video on YouTube

[https://youtu.be/h2cFAH46ESQ?si=GUpvOnON-o8CuXP1&amp;t=512](https://youtu.be/h2cFAH46ESQ?si=GUpvOnON-o8CuXP1&t=512)

#### Context Menu of a Graphic Group

Context Menu of a Graphic Group

The context menu of a graphic group in the structure window of the dialog Show Graphic Structure provides the commands listed in the table of contents to the left.

<!-- image -->

The dialog Show Graphic Structure shows graphic groups with cubes in different colors.

<!-- image -->

##### Visible [context menu]

To determine if the selected graphic group is currently a part of the three-dimensional representation of the object for which it will be created, select this command.

Once you activate the command, the graphic group is immediately shown alternatively or additively to the other graphic groups of the object. The graphic group will only be shown in all 3D window after you activated the command.

If a graphic group, which you marked as visible, will actually be shown in a certain 3D window or not, depends on additional object and window settings and which object is opened in the respective 3D window.

If you deactivate the command, the graphic group will not be visible in any 3D window at the moment. This setting makes sense if you only want to use the graphic group temporarily for the visual representation of the object.

You can change the setting Visible at any time:

- With the context menu command described here.
- With the check box in the table on the tab Graphics .
- With the attribute \_3D.VisibleGraphics .

The icon of a visible or not visible graphic group, MyGraphic in the example below, looks like this:

<!-- image -->

**SimTalk**

Locked [SimTalk] - graphic group

See also

Graphics [tab, 3D] &gt; Visible [check box]

<!-- image -->

**Internal [context menu]**

##### Internal [context menu]

To make the graphic group only visible within the Frame and only use it for the internal decoration of the Frame , select this command.

<!-- image -->

External graphic groups on the other hand represent its Frame toward the outside.

<!-- image -->

The dialog Show Graphic Structure shows graphic groups with cubes in different colors.

SimTalk

Internal [SimTalk] - graphic group

See also

Graphics [tab, 3D] &gt; Internal [check box]

##### Locked [context menu]

To lock the graphic group, select this command.

This prevents you from selecting this graphic group in the 3D windows which are opened for this object. This makes, for example, sense for the graphic of a factory building which might otherwise be selected inadvertently.

SimTalk

Locked [SimTalk] - graphic group

See also

Graphics [tab, 3D] &gt; Locked [graphic group]

**Generated [context menu]**

##### Generated [context menu]

To show if the graphics of the graphic group will be generated automatically all over again or not, select this command.

You can neither edit, nor delete nor add to it nor delete generated graphics. You can edit some of its appearance properties though.

SimTalk

Generated [SimTalk] - graphic group

See also

Auto Graphics Active

Generated and Non-Generated Graphics

##### Rename [graphic group]

To rename the selected graphic group, select this command.

SimTalk

Name [SimTalk] - graphic

**Copy [graphic group]**

##### Copy [graphic group]

To copy the selected graphic group, select this command.

##### Delete [graphic group]

To delete the selected graphic group, select this command.

#### Context Menu of a Simulation Object

Context Menu of a Simulation Object

The context menu of a simulation object in the structure window of the dialog Show Graphic Structure provides the commands listed in the table of contents to the left.

**Open [3D object]**

##### Open [3D object]

To open the selected object in the currently active 3D window, select this command.

##### Open in New 3D Window [3D object]

To open the selected object in a new 3D window, select this command.

**Note**

If the new 3D window is empty, click External Graphics on the View ribbon tab in the 3D window .

**Rename [3D object]**

##### Rename [3D object]

To rename the selected object, select this command.

Edit 3D Properties [3D object]

To open the dialog Edit 3D Properties for the selected object, select this command.

See also

Edit 3D Properties [dialog]

**Paste [graphic group]**

##### Paste [graphic group]

To insert the graphic group from the clipboard into the selected object, select this command.

When you paste a graphic into a 3D object which inherits its graphics, Plant Simulation asks if you want to cut graphic inheritance for this object or not. Plant Simulation only pastes the graphic group if you cut graphic inheritance by clicking Yes .

##### Delete [3D object]

To delete the selected object, select this command.

**Add Animatable Object**

##### Add Animatable Object

To create a new animatable object and adds it to the selected simulation object, select this command.

For object nodes the animatable object is named AnimatableObject . For Frames it is named AnimatableObject1 , etc if the name is already taken.

Specify a name, which corresponds to the name of an animatable object in the origin of the object, in which the new animatable object is going to be created, to create an object that inherits from the animatable object in the origin of the respective object.

This way you can restore a deleted animatable object, which inherits from another object, in a way that is inherits again from the original object.

<!-- image -->

**Length-oriented**

To make the new animatable object length-oriented, select this.

If you select the check box and the object would be created with an origin, the newly created object will only have an origin if this origin is length-oriented as well. If the check box is selected the new object is going to be length-oriented if it has an origin and if this origin is length-oriented as well.

If an animatable object exists in the origin of the object to which you would like to add an animatable object, which does not exist within the object itself, Plant Simulation suggests the name of the object and its being length-oriented.

**SimTalk**

\_3D.addObject [SimTalk]

See also

Make Animatable Object

##### Add Graphic Group

To create a new graphic group for the selected object, select this command.

- Type in the Name of the new graphic group into the dialog box that opens. This name has to be unique for the object.
- Select Internal to make the graphic only visible within its object and only use it for its internal decoration.
- Select Visible to set that this graphic group visually represents the object from now on.
- Select Locked to prevent this graphic group from being selected inadvertently.

<!-- image -->

**SimTalk**

\_3D.addGraphicGroup [SimTalk]

See also

Graphics [tab, 3D] &gt; Add [graphic group]

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP\_cAs66V&amp;t=700](https://youtu.be/jHOZhlwGhkQ?si=LIBTEB2GP_cAs66V&t=700)

#### Context Menu of Anchor Points of a Path

Context Menu of Anchor Points of a Path

Click an anchor point with the right mouse button to show a context menu with the commands listed in the table of contents to the left.

##### Context Menu of Anchor Points of a Path

<!-- image -->

##### Look at Object

To rotate the selected anchor point of the path so that it points toward another object, select this command.

The command is only active when the anchor point belongs to a camera path of type Lines .

If you select the command, the mouse pointer changes into an eye. Then, you can select the object at which the anchor point is to look by clicking the object with the left mouse.

Click the right mouse button or press Esc to cancel the command.

See also

Define View Direction

##### Delete Anchor Point

To delete the selected anchor point of the path, select this command.

##### Context Menu of the Background of the Scene

#### Context Menu of the Background of the Scene

Click in an empty area in the scene window with the right mouse button to show a context menu with these commands.

You can also close the context menu and leave the mini toolbar open

<!-- image -->

button.

<!-- image -->

<!-- image -->

| Reset Simulation [Home ribbon]              | Show Structure [Home ribbon]               |
|---------------------------------------------|--------------------------------------------|
| Start/Stop Simulation [Home ribbon]         | Show 3D Graphic Structure [context menu]   |
| Start Fast Forward Simulation [Home ribbon] | Show Inheritance [Home ribbon]             |
| Open Location [Home ribbon]                 | Show Attributes and Methods [Home ribbon]  |
| Open Origin [Home ribbon]                   | Edit User-defined Attributes [Home ribbon] |
| Open Class [Home ribbon]                    | Create User-defined Attribute              |

by clicking the border of the mini toolbar with the left mouse Do not confuse the selected object in 3D with the selected graphic of the object!

<!-- image -->

<!-- image -->

##### Create User-defined Attribute

To create a user-defined attribute for a simulation object, which you opened in a 3D window of its own, select this command.

Plant Simulation creates the user-defined attribute at the position, where you click the mouse button.

**Note**

This does not apply to a Frame or a folder.

<!-- image -->

Plant Simulation opens the dialog User-defined Attribute with the Transformation and Display Settings that the dialog had when you last created a user-defined attribute . Show in 3D is selected by default.

Enter and select the settings you need and click OK to create the user-defined attribute .

<!-- image -->

##### Previous Scene

To return to the level in the hierarchy of objects or the camera mark that was active before the current level, select this command.

Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=dYxqIjwYquKYheWo&amp;t=571](https://youtu.be/FNpiAaUK8iM?si=dYxqIjwYquKYheWo&t=571)

