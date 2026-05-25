### Edit Ribbon Tab

#### Edit Ribbon Tab [3D]

The Edit ribbon tab of the 3D window provides commands to access its functions.

<!-- image -->

**Edit Ribbon Tab [3D]**

| Command                                                  | Looks like this   | Method or Attribute                                                                                                                  |
|----------------------------------------------------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Import Graphics                                          |                   | importGraphics [SimTalk]                                                                                                             |
| Exchange Graphics                                        |                   | _3D.exchangeGraphic [SimTalk]                                                                                                        |
| Export Scene Export Graphics Export Object Export Bitmap |                   | - _3D.exportAsJt [SimTalk] _3D.exportAsS3D [SimTalk] _3D.exportModelingViewBitma p [SimTalk] _3D.exportPlanningViewBitma p [SimTalk] |
| Print Scene Print Preview                                |                   | -                                                                                                                                    |
| Show Graphic Structure                                   |                   | -                                                                                                                                    |
| Optimize Selected Graphic                                |                   | optimizeByPruningTinyGraphic s [SimTalk] optimizeByStructureFlattening [SimTalk] optimizeByVisibilityFilter [SimTalk]                |
| Group Graphics                                           |                   | groupGraphics [SimTalk]                                                                                                              |
| Ungroup Group of Graphics                                |                   | ungroupGraphic [SimTalk]                                                                                                             |

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Command                | Looks like this   | Method or Attribute                                |
|------------------------|-------------------|----------------------------------------------------|
| Shape                  |                   | -                                                  |
| Barred Area            |                   | createBarredArea [SimTalk]                         |
| Box                    |                   | createBox [SimTalk]                                |
| Cone Frustum           |                   | createConeFrustum [SimTalk]                        |
| Cuboid                 |                   | createCuboid [SimTalk]                             |
| Cylinder               |                   | createConeFrustum [SimTalk]                        |
| Dimensioning           |                   | createDimensioning [SimTalk]                       |
| Factory Walls          |                   | createFactoryWalls [SimTalk]                       |
| Fence                  |                   | createFence [SimTalk]                              |
| Mezzanine              |                   | createMezzanine [SimTalk]                          |
| Rack                   |                   | createRack [SimTalk]                               |
| Sphere                 |                   | createSphere [SimTalk]                             |
| Stairs                 |                   | createRack [SimTalk]                               |
| Text                   |                   | createText [SimTalk]                               |
| Textured Plate         |                   | createPicture [SimTalk] createTiledPlate [SimTalk] |
| Make Animatable Object |                   | makeAnimatableObject                               |
| Make Simulation Object |                   | -                                                  |

**Edit Ribbon Tab [3D]**

<!-- image -->

| Command             | Looks like this   | Method or Attribute   |
|---------------------|-------------------|-----------------------|
| Undo                |                   | -                     |
| Redo                |                   | -                     |
| Show Manipulators   |                   | -                     |
| Align to Grid       |                   | -                     |
| Snap to Grid        |                   | -                     |
| Snap to Objects     |                   | -                     |
| Apply Changes       |                   | -                     |
| edddison            |                   | -                     |
| Omniverse Connector |                   |                       |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to 3D .

#### Import Graphics

Import Graphics

Import Graphics describes how to:

- Import Graphics [command]
- Place Imported Graphics in the 3D Window

##### Import Graphics [command]

Imports graphics into your simulation model.

<!-- image -->

It opens the dialog Import 3D Graphics . Select drive and folder from the drop-down list and select or type in the name of a 3D object or of a 3D graphic which you created in a 3D modeling program or of a 3D model file.

If you scroll to the top on the left-hand side in the dialog Open , Plant Simulation shows the folder in which the graphic files with the respective formats are saved.

<!-- image -->

**Note**

Import Graphics imports the file you select into the open scene into the displayed level of your model file, making the imported file part of your active model.

3D uses the file name of the graphic as the name of the graphic node.

When you import a 3D graphic with this command or with drag-and-drop from the Windows Explorer, Plant Simulation automatically zooms the view to this graphic.

To prevent zooming, hold down Shift before clicking OK in the dialog Insert Graphic . Zooming can, for example, be annoying if you want to import several JT graphics to certain positions and if Plant Simulation continuously changes the scene when doing so.

You can convert the 3D graphics formats to JT files using the programs xt2jt , wrltojt , and stltojt that are installed in the Plant Simulation installation folder.

3D can import these file formats:

- All 3D Graphic Files
- JT Files (*.jt)

**Note**

We recommend to use the JT format whenever possible.

- Parasolid Files (*.x\_b; *.x\_t, *.xmt\_bin, *.xmt\_txt)
- Catia V4 Files (*.exp; *.model)
- IGES Files (*.igs ; *.iges)
- STEP Files (*.stp; *.step)
- STL Files (*.stl)
- VRML Files (*.wrl)
- CAD Layout Files (*.dgn, *.dwg, *.dxf)

See also

importGraphics [SimTalk]

optimizeByPruningTinyGraphics [SimTalk]

optimizeByStructureFlattening [SimTalk]

optimizeByVisibilityFilter [SimTalk] Import JT Graphics Representing an Object Add a Layout File to Your Simulation Model Export Graphics

##### Place Imported Graphics in the 3D Window

After you selected the graphic that you want to import in the dialog Import Graphics , Plant Simulation attaches the graphic to the mouse pointer.

Drag the mouse to the position at which you would like to insert the graphic in the 3D window. When you release the left mouse button, you can:

- Select the Graphic Group to which you want to add the graphic, provided that the object has several graphics.
- Select the Positioning of the graphic:
- As Shown in the View : The graphic is positioned as shown in the preview when you drag the mouse with the attached graphic in the scene before you click the left mouse button.
- As Saved in the File : The graphic is positioned as it was saved in the imported file.

<!-- image -->

<!-- image -->

- Axes Origin : The graphic is positioned with the center of the floor of its bounding box onto the axes origin of the scene.

<!-- image -->

Plant Simulation places the center of the bounding box of the entire robot onto the axes origin. For this reason the center of the foot of the robot does not coincide with the 3D axes origin of the Frame .

- Select the Orientation of the Coordinate System of the imported graphic:
- Z-axis Points Up . This is the default setting

<!-- image -->

<!-- image -->

- Y-axis Points Up .
- Select Optimization settings when importing the graphic:

<!-- image -->

- Flatten Structure (keep Grouping) flattens the structure of the object and keeps its contents and the grouping information of the selected object.
- Remove Polylines and Point Sets removes partial graphics of types JtPolylineSet or JtPointSet . These are lines and point set graphics.
- The group box Graphic Complexity shows the following values for the complexity of the selected graphic.
- Nodes (CPU) shows the number of nodes of the selected graphic. The number of nodes affects the CPU (Central Processing Unit) of your computer. When you optimize your graphics, the values for nodes and for polygons should be as small as possible.
- Polygons (GPU) shows the number of polygons of the selected graphic. The number of polygons affects the graphics card of your computer. When you optimize your graphics, the values for nodes and for polygons should be as small as possible.
- Memory Usage shows the amount of memory which the selected graphic uses. This number is helpful if your model reacts sluggish after importing graphics files you received from your construction department. These construction graphics often contain a level of detail that your simulation model does not require. Deleting unnecessary graphics details for displaying the object will greatly increase performance of the simulation model.
- Click OK to insert the graphic at the selected position with the selected orientation.

To insert several instances of the graphic to be imported one after the other, click Import Graphics . Select the graphic in the dialog Open . Hold down Ctrl , click OK in the dialog of the shape, click at the position in the Frame in the 3D window at which you want to insert the first instance, and click the left mouse button. Continue holding down Ctrl and repeat this until you have inserted the desired number of instances.

To terminate multiple insert, click the right mouse button or press Esc or select another object or another graphic.

See also

Import Graphics [command]

importGraphics [SimTalk]

optimizeByPruningTinyGraphics [SimTalk]

optimizeByStructureFlattening [SimTalk]

optimizeByVisibilityFilter [SimTalk]

Import JT Graphics Representing an Object

Add a Layout File to Your Simulation Model

Export Graphics

#### Exchange Graphics

Assigns different graphic and animation data to the selected object by exchanging its default graphic with the s3D graphic that you select.

<!-- image -->

By default, it opens the dialog Exchange Graphics . By default, it opens to the folder where you installed Plant Simulation , namely C:\Program Files\Siemens\Tecnomatix Plant Simulation XX\3D\s3D-graphics .

If you scroll to the top on the left-hand side in the dialog Open , Plant Simulation shows the folder in which the graphic files with the respective formats are saved.

<!-- image -->

Select the .s3D graphics file that is to replace the current graphic groups and the graphic attributes of the object. s3D is a proprietary file format which stores all graphics and attributes of a Plant Simulation object which are required for its representation and animation.

To replace existing graphics in a model, which you created in a previous version of the program, with the new graphics, select the respective graphic and select Exchange Graphics . Navigate to the folder 3D &gt; BasicObjects and select the new graphic of the object. Alternatively you can also hold down Shift and select Revert all Objects to Standard Graphics on the context menu of the class object of the class.

<!-- image -->

When you call the command for a mobile object ( MU ), Plant Simulation shows this dialog:

<!-- image -->

Click Yes to use the dimensions of the loaded graphic as the new dimensions of the MU , in our case the Container , i.e., as the MU Size .

<!-- image -->

Click No to retain the existing dimensions of the MU despite its changed graphic.

**See also**

\_3D.exchangeGraphic [SimTalk]

Use a Different Graphic for an Object

Export Object

Video on YouTube

[https://youtu.be/K-NEPvShU10?si=ChF\_2xnoMuE1Fq7q&amp;t=730](https://youtu.be/K-NEPvShU10?si=ChF_2xnoMuE1Fq7q&t=730)

#### Export Scene Command

##### Export Scene

<!-- image -->

The command Export Scene provides the subcommands Export Graphics , Export Object , and Export Bitmap .

**Export Graphics**

##### Export Graphics

Exports the scene of the active 3D window as a graphics file in the format JT Files (*jt).

<!-- image -->

JT is used in many applications as the format for 3D graphics. You can re-import an exported JT file to use the graphics contained within in addition to representing another object. To do so, click Import Graphics

<!-- image -->

If you selected a single graphic or a single object of the scene, Plant Simulation only exports the selected graphic or all graphics visible in the selected graphic. If you did not select anything, Plant Simulation exports all graphics that are visible within the active 3D window.

Select drive and folder from the drop-down list and type the name into the text box next to File name .

<!-- image -->

**Optimize for CAD**

<!-- image -->

To optimize the structure of the graphic for CAD applications such as NX , select Optimize for CAD .

To optimize the structure of the graphic for other applications such as Plant Simulation or Teamcenter Visualization , clear the check box.

When you export a graphic as a Jt file and when you activate Optimize for CAD , captions and logical object are excluded.

**Logical objects are:**

- EventController

- FlowControl
- Cycle
- Exporter
- Broker
- ShiftCalendar
- LockoutZone
- All InformationFlow objects
- All UserInterface objects
- All GA objects

**SimTalk**

**\_3D.exportAsJt [SimTalk]**

##### Export Object

Exports the scene of the active 3D window as an object file in the format 3D Files (*.s3d).

<!-- image -->

s3d is a proprietary file format which stores all graphics and attributes of a Plant Simulation 3D object which are required for its representation and animation. You can use a s3d file to exchange the representation and the animation of another a Plant Simulation 3D object with the saved object in the active model with this file. To do so, click Exchange Graphics on the Edit ribbon tab.

This only applies to objects which do not have an origin. If an object is selected, Plant Simulation will export this object or otherwise the opened object.

<!-- image -->

The command opens the dialog Save as . Select drive and folder from the drop-down list and type the name into the text box next to File name .

**SimTalk**

\_3D.exportAsS3D [SimTalk]

See also

Exchange Graphics

##### Export Bitmap

Exports the scene of the active 3D window as a bitmap file in the format PNG (*.png).

<!-- image -->

The picture of the 3D scene is created with the best possible quality, i.e., the screen coverage threshold is ignored here.

The text box Width designates the width of the target file in pixels. The Height is computed according to the aspect ratio of the active 3D window.

<!-- image -->

The command opens the dialog Save As . Select drive and folder from the drop-down list and type the name into the text box next to File name .

SimTalk

\_3D.exportModelingViewBitmap [SimTalk]

\_3D.exportPlanningViewBitmap [SimTalk]

See also

Screen Coverage Threshold [model settings]

#### Print Scene

Opens the dialog Print . Select the printer, the print range, and the number of copies and click OK to print the active scene.

<!-- image -->

**Print Preview**

The command Print Preview shows the active scene on a full page allowing you to see how it will look on a printed sheet of paper.

#### Show Graphic Structure

Show Graphic Structure [3D button]

Opens a dialog which shows the graphic structure of the selected object in 3D or of the 3D-counterpart of the selected object in 2D.

<!-- image -->

3D differentiates between simulation objects , animatable objects , graphic groups , and 3D graphics of the selected object. The dialog Show Graphic Structure shows them in a tree.

<!-- image -->

To find an element in the structure, type its name into the text box next to the Find button, and click Find .

Plant Simulation searches the list and highlights the object it found. The found element is also selected in any 3D window in which it is visible. Click Find again to find additional instances of the search term.

The toolbar provides these buttons.

<!-- image -->

The dialog does not automatically update the graphic structure when you change the graphic outside of this dialog. To update the contents of the dialog, click on the toolbar or open any context menu.

The dialog shows this information for graphics:

- The number in brackets designates the number of the child graphic within the parent graphic or graphic group respectively, for example [1] , [2] , etc.
- The name of the graphic if the graphic has a name. The ComauScaraRobot has graphics named Barred Area , stand , etc.
- The type information in parentheses .
- ▲ designates a TriStripSet. This encompasses most graphics without sub-graphics, which are imported from a file.
- ■ designates a graphic node of graphic shapes, for example a cuboid, which you insert.
- ╬ designates a polyline node. These are created when importing graphics, which, for example, contain construction lines or when you call the method createIndexedLineSet .
- · designates a point set node. These are created when importing graphics, which, for example, contain construction lines.
- ♦ designates an instance node. These are special group nodes that only contain a single graphic.
- If no type is shown, the node is a normal group node.
- Graphics which are no group nodes, show P=123 . 123 designates the number of polygons, points, or line graphic shapes.
- Graphics which are no group nodes, show C if the graphic defines colors in its graphic shapes. This means that the graphic might not be shown gray, even though no material is defined for it or for a graphic it contains.

<!-- image -->

- All graphics show M when a material is defined for a graphic. If the M is followed by an asterisk * , the material does not overwrite the color in the graphic shapes. This is, for example, often the case for graphics exported from FactoryCAD .
- All graphics show a T if a texture is defined for the graphic.

Let us illustrate the notation using the example of a graphic of a Station :

<!-- image -->

- [1] means that it is the first graphic in the graphic group named default .
- workplace is the name of the graphic.
- ▲ means that the graphic is a TriStripSet, i.e., a graphic based on triangle sets.

P=349 means that it contains 349 polygons. Compare the number of polygons in the dialog Optimize Selected Graphic .

M means that it has a material.

You can use the following key combinations to execute these commands in the dialog Show Graphic Structure .

<!-- image -->

| Command            | Key Combination    |
|--------------------|--------------------|
| Edit 3D Properties | Ctrl+3 or Spacebar |
| Cut                | Ctrl+X             |
| Copy               | Ctrl+C             |
| Paste              | Ctrl+V             |
| Delete             | Del                |
| Ungroup            | Ctrl+U             |

| Command   | Key Combination   |
|-----------|-------------------|
| Refresh   | F5                |
| Rename    | F2                |

When you duplicate a graphic by holding down Ctrl+Shift and dragging and clicking the left mouse button, Plant Simulation does not create a copy of the graphic, but the new graphic references the duplicated graphic. This reduces memory consumption. Plant Simulation shows that the graphic is referenced by a diamond here.

<!-- image -->

We provide additional commands in the:

Context Menu of the Selected Graphic

Context Menu of a Graphic in the Graphic Structure

Context Menu of a Graphic Group

Context Menu of a Simulation Object

See also

Show Graphic Structure [3D context menu] on the context menu

##### Inherit Graphic Groups

Shows and sets if the simulation object inherits its graphic structure and the graphic group properties name, locked and internal from its origin or not.

<!-- image -->

If you select a single graphic, the button is unavailable.

<!-- image -->

Click the button to change graphic inheritance. To prevent you from inadvertently also duplicate the graphics and thus increase the model size, Plant Simulation asks you if really you want to cut graphic inheritance. Click Yes to cut graphic inheritance. Click No to leave the graphic as it is.

**Note**

You can only activate inheritance in derived simulation objects, i.e., in non-class objects.

SimTalk

\_3D.InheritGraphics [SimTalk]

See also

Graphics [tab, 3D] &gt; Graphic Groups [described]

##### Inherit Graphic Group Visibilities

Shows and sets if the simulation object inherits the visibilities of its graphic groups from the origin object or not.

<!-- image -->

If you do not select a graphic group, the button is unavailable.

Click the button to change inheritance of the visibilities of all graphic groups.

**Note**

You can only activate inheritance in derived, i.e., in non-class objects.

**SimTalk**

\_3D.VisibleGraphicGroups [SimTalk]

See also

Tab Graphics &gt; Graphic Groups [described] &gt; Visibilities

#### Optimize Selected Graphic

Optimize Selected Graphic

Optimizes the Graphic of the selected Object . During this process it discards information no longer required, such as unnecessary group objects.

<!-- image -->

**Note**

As you cannot restore discarded data, we advise to optimize the structure of the object after you are done modeling the object. Optimizing the 3D graphic improves performance.

We also recommend to save the model under a different name before optimizing it. This way you can return to the state the model had before optimizing it in case the optimized model reports errors or does not meet your expectations.

Proceed as follows to open the dialog Optimize Graphic :

- Select the graphic in the scene window and click Optimize Graphic .

To optimize an external graphic, click Show External Graphic Groups on the View ribbon tab to display the graphics in the scene window.

<!-- image -->

- Or click the object with the right mouse button and select Optimize Graphic on the context menu.

In the dialog you can optimize the selected graphic in three steps:

- Select Step 1: Prune Tiny Graphics to remove component graphics which individually fit within the defined bounding box.
- Select Step 2: Flatten Structure to flatten the structure of the object while preserving its contents.
- Select Step 3: Visibility Filter to remove graphic components which are not visible from the outside.
- Click Generate SimTalk Code and Copy to Clipboard [optimize graphic] to execute these actions. You can then directly paste this source code into a Method to automatically execute the defined optimizations as part of an automated process.
- Click Preview Result to preview your changes before accepting them.
- Click Revert to undo your changes and to revert to the settings before you made changes. The dialog then shows the number of nodes, polygons, and the memory usage before and after the

optimization.

- Click Accept Result to accept your changes.
- View information about the Graphic Complexity of the graphic.

Compare the number of nodes and the number of polygons before and after optimizing in our example below.

<!-- image -->

When you are done with optimizing the graphic, close the dialog by clicking in the title bar of the dialog.

<!-- image -->

##### Step 1: Prune Tiny Graphics

To remove all component graphics which individually fit within the bounding box, select Prune Tiny Graphics . It scans the graphic for sub-structures that fit into the Bounding Cube Side Length that you define. It then deletes everything that fits in this group.

Prune Tiny Graphics is useful for visible but unimportant details like screws. Graphics, however small they might be, will not be deleted if they are only part of a larger indivisible graphic node. This is often the case for automatically generated graphics.

Bounding Cube Side Length

Type in the side length of the cube that surrounds the graphic whose component graphics you would like to remove.

<!-- image -->

SimTalk

optimizeByPruningTinyGraphics [SimTalk]

Video on YouTube

[https://youtu.be/t7hBJgNZpHE?si=Z1PnjTrNZ5lkZK9P&amp;t=579](https://youtu.be/t7hBJgNZpHE?si=Z1PnjTrNZ5lkZK9P&t=579)

Step 2 Flatten Structure

Step 2: Flatten Structure

To flatten the structure of the object while preserving its content, select Flatten Structure .

<!-- image -->

Flatten Structure reduces the graphic structure to a minimal structure that only keeps the visualization running, i.e. the remaining structure levels are those that are needed to hold a material or a texture. If you want to keep grouping information of the selected graphic, select Keep Grouping .

**Note**

Be aware that the result of the optimization process might contain more than one graphic node, provided the graphic contained more than one material/texture combination.

You can select one or more of these settings:

- Keep Grouping
- Preserve Obstacles
- Preserve References
- Remove Polyline and Point Sets

SimTalk

optimizeByStructureFlattening [SimTalk]

Video on YouTube

[https://youtu.be/t7hBJgNZpHE?si=x3qQ3yUWneLnp7Ol&amp;t=730](https://youtu.be/t7hBJgNZpHE?si=x3qQ3yUWneLnp7Ol&t=730)

###### Keep Grouping

To keep grouping information of the selected graphic if more than a single graphic has been grouped, select this check box.

<!-- image -->

**SimTalk**

optimizeByStructureFlattening [SimTalk]

**Preserve Obstacles**

###### Preserve Obstacles

To preserve existing obstacles for the worker when flattening the structure, select this check box.

<!-- image -->

While doing so Plant Simulation only considers the directly optimized object and the obstacle settings of this object and its graphics. Preserve Obstacles is activated by default.

If Keep Grouping is activated, you cannot select Preserve Obstacles and Preserve References .

Plant Simulation warns that obstacles might have changed if:

- The object, whose graphics are optimized at the moment, can create obstacles.
- The obstacle setting of the object or of an object inheriting from this object and the obstacle settings of graphics, which are located on the path between the graphic group and of the graphic to be optimized (including the graphic itself), are set so that obstacles depending on graphics are actually computed. These are all obstacles, except for the obstacles that is being created for the polycurve of a length-oriented object for the setting Worker Obstacle &gt; Graphics . On the other hand obstacles from additional graphic groups of such an object are included again.
- One of the activated optimization settings is able to change obstacles. This is the case if:
- Prune Tiny Graphics is activated.
- Flatten Structure is activated and the obstacle setting of the object and the obstacle settings of graphics, which are located on the path between the graphic group and of the graphic to be optimized (including the graphic itself), are not set so that partial graphics of the graphics to be optimized create obstacles, which is the case for an object that inherits its settings from the object.
- Visibility Filter is activated and the obstacle setting of the object or of one of its inheriting objects, and, in addition, the obstacle settings of graphics, which are located on the path between the graphic group and of the graphic to be optimized (including the graphic itself), are set so that partial graphics of the graphic to be optimized create obstacles.

SimTalk

optimizeByStructureFlattening [SimTalk]

See also

Obstacle for the Worker [drop-down list]

###### Preserve References

To preserve multiple references to sub-graphics, select this check box.

<!-- image -->

**This prevents that:**

- Part graphics, that are contained several times in the graphic to be optimized, are going to be duplicated during the optimization.
- The model size increases through the graphic duplicates.

If Keep Grouping is active, you cannot select Preserve Obstacles and Preserve References .

SimTalk

optimizeByStructureFlattening [SimTalk]

###### Remove Polyline and Point Sets

To remove partial graphics of types JtPolylineSet or JtPointSet , select this check box. These are line graphics or point set graphics.

<!-- image -->

**SimTalk**

optimizeByStructureFlattening [SimTalk]

Step 3: Visibility filter

Step 3: Visibility Filter

To remove graphic components which are not visible from the outside, select Visibility Filter . You can select the Cull Granularity and the Reduction Level .

<!-- image -->

It scans the graphic for hidden parts which will then be deleted.

- The Cull Granularity sets the finest structure that Plant Simulation checks.
- The Reduction Level sets how closely Plant Simulation checks the graphic. The higher this setting, the more graphics are kept. When you need the optimized graphic to be as small as possible, select Low .

**SimTalk**

optimizeByVisibilityFilter [SimTalk]

Video on YouTube

[https://youtu.be/t7hBJgNZpHE?si=6U52PULurFIs2vU-&amp;t=1265](https://youtu.be/t7hBJgNZpHE?si=6U52PULurFIs2vU-&t=1265)

**Cull Granularity**

###### Cull Granularity

Select the Cull Granularity for deleting graphics.

<!-- image -->

- Shapes removes entire component graphics. The smallest considered sub-structure is an ungrouped graphic node.
- Faces removes entire graphic faces. The smallest considered sub-structure is a closed surface. For most purposes, there is no difference between Faces and Shapes .
- Triangle Strips removes parts of graphic faces. The smallest considered sub-structure is a surface part. Often, this will not be more than a simple polygon. This setting will typically produce the most desired result. The optimization will not be the maximally possible result, but the visual side effects will be low.
- Triangles removes triangles. The smallest considered sub-structure is a single triangle. While the optimized graphic will be smaller than for the other options, a side effect might be that the graphic shows small holes.

**SimTalk**

optimizeByVisibilityFilter [SimTalk]

###### Reduction Level

Select the Reduction Level , i.e., how close Plant Simulation looks at the graphic.

- Low designates a low reduction level and a high level of detail. This might cause holes in the resulting graphic.
- Super designates a great reduction level and a low level of detail. This setting takes longer to render.
- The settings Medium and High are located in between these extremes.

<!-- image -->

**SimTalk**

optimizeByVisibilityFilter [SimTalk]

##### Generate SimTalk Code and Copy to Clipboard [optimize graphic]

To translate your settings for optimizing the graphic into SimTalk source code and to copy that code to the clipboard, click this button.

You can then paste the source code into a Method and use it elsewhere while modeling.

<!-- image -->

The settings from the screenshot above generate the following source code:

.Models.Model._3D.getGraphic("deco", [2]).optimizeByPruningTinyGraphics(0.02) .Models.Model._3D.getGraphic("deco", [2]).optimizeByStructureFlattening(false, true, true, true) .Models.Model._3D.getGraphic("deco", [2]).optimizeByVisibilityFilter(2, 1)

See also optimizeByPruningTinyGraphics [SimTalk] optimizeByStructureFlattening [SimTalk]

**optimizeByVisibilityFilter [SimTalk]**

**Optimize a Graphic**

**Preview Result**

##### Preview Result

To preview the result of your changes to the settings in the 3D window , click this button.

<!-- image -->

You can then either Revert to the settings which the dialog had before you made changes or you can click Accept Result to apply your changes.

**Note**

You have to preview the result before you can revert to the previous settings or accept your changes.

##### Revert

<!-- image -->

To revert the graphic to the state it had before the last optimization step, click this button.

When you close the dialog by clicking in the title bar of the dialog, Plant Simulation also reverts to the last saved state of the graphic.

**Accept Result**

##### Accept Result

To apply your changed settings, click this button.

You can then close the dialog by clicking in the title bar of the dialog.

##### Graphic Complexity

The group box Graphic Complexity shows the following values for the complexity of the selected graphic.

- Nodes (CPU) shows the number of nodes of the selected graphic. The number of nodes affects the CPU (Central Processing Unit) of your computer. When you optimize your graphics, the values for nodes and for polygons should be as small as possible.
- Polygons (GPU) shows the number of polygons of the selected graphic. The number of polygons affects the graphics card of your computer. When you optimize your graphics, the values for nodes and for polygons should be as small as possible.
- Memory Usage shows the amount of memory which the selected graphic uses. This number is helpful if your model reacts sluggish after importing graphics files you received from your construction department. These construction graphics often contain a level of detail that your simulation model does not require. Deleting unnecessary graphics details for displaying the object will greatly increase performance of your simulation model.

Compare the number of nodes and the number of polygons before and after optimizing by clicking Preview Result in our example below.

<!-- image -->

#### Group Graphics

Groups the selected graphics and combines them into one object.

<!-- image -->

This combined graphic then contains the selected graphics, and you can manipulate the group as a whole.

To select several graphics, hold down Shift and click the objects. Then click Group Graphics or press Ctrl+G .

SimTalk

groupGraphics [SimTalk]

ungroupGraphic [SimTalk]

See also

Edit Grouped Graphics

Ungroup Group of Graphics

<!-- image -->

#### Ungroup Group of Graphics

Ungroups the selected group of graphics.

You can then manipulate each object individually again. Ungrouping only works for a single group!

When you group any number of graphics, 3D creates a single new graphic. When you ungroup this group, 3D replaces this group with the individual members of the group and restores the state of the individual graphics as it was before the grouping action.

SimTalk

ungroupGraphic [SimTalk]

groupGraphics [SimTalk]

See also

Edit Grouped Graphics

Group Graphics

Video on YouTube

https://youtu.be/h2cFAH46ESQ?si=e79tSSJ2ZkzMim78&amp;t=212

#### Insert Shape

Insert Shape

Select the shape that you want to create and to insert into your model.

Click the Down button to scroll down in the list. Click the More button to show all shapes in the list.

If the opened object has only generated graphic groups, you cannot select any shape. In this case you can add an additional graphic group in the dialog Show 3D Graphic Structure or on the tab Graphics in the dialog Edit 3D Properties . You can then add shapes to this graphic group and edit these.

<!-- image -->

<!-- image -->

| To do this                                                 | Click   | Command        | Method                       |
|------------------------------------------------------------|---------|----------------|------------------------------|
| Insert a barred area                                       |         | Barred Area    | createBarredArea [SimTalk]   |
| Insert a box                                               |         | Box            | createBox [SimTalk]          |
| Insert a conical frustum, i.e. a cone with the tip cut off |         | Cone Frustum   | createConeFrustum [SimTalk]  |
| Insert a cuboid                                            |         | Cuboid         | createCuboid [SimTalk]       |
| Insert a cylinder                                          |         | Cylinder       | createConeFrustum [SimTalk]  |
| Insert dimensionings                                       |         | Dimensioning   | createDimensioning [SimTalk] |
| Insert factory walls                                       |         | Factory Walls  | createFactoryWalls [SimTalk] |
| Insert a fence                                             |         | Fence          | createFence [SimTalk]        |
| Insert a mezzanine                                         |         | Mezzanine      | createMezzanine [SimTalk]    |
| Insert a rack                                              |         | Rack           | createRack [SimTalk]         |
| Insert a sphere                                            |         | Sphere         | createSphere [SimTalk]       |
| Insert stairs                                              |         | Stairs         | createStairs [SimTalk]       |
| Insert text                                                |         | Text           | createText [SimTalk]         |
| Insert a textured plate                                    |         | Textured Plate | createTiledPlate [SimTalk]   |

To insert several instances of a shape one after the other, click the shape on the tab Edit . Hold Ctrl down, click Create in the dialog of the shape, click at the position in the Frame in the 3D window at which you would like to insert the first instance and click the left mouse button. Continue holding down Ctrl and repeat this until you have inserted the needed number of instances. To terminate multiple insertion, click the right mouse button, press Esc , or select another object or another graphic.

Making a Graphic Group Visible While Inserting It

To allow you to check and edit the inserted shape, Plant Simulation automatically activates Show External Graphic Groups when you insert a shape into an external graphic group. When a graphic group was permanently invisible before, Plant Simulation makes the graphic group visible while inserting it. After inserting the shape, you can make all external graphic groups invisible again, by deactivating Show External Graphic Groups or make a graphic group permanently invisible again in the dialog Show 3D Graphic Structure or on the tab Graphics in the dialog Edit 3D-Properties .

Plant Simulation automatically shows external graphics as soon as inserting the newly created shape into an external graphic group starts, i.e., as soon as the shape is attached to the mouse pointer and the insertion position still has to be determined. When you cancel inserting the shape by pressing Esc or by clicking the right mouse button, Plant Simulation hides external graphics again, provided they were invisible before as well.

See also

Model Your Own 3D Graphic

\_Accessing Methods of Graphic Shapes

\_Detailed Access To Graphics

Undo [3D]

Redo [3D]

##### Graphic Group [for shape]

When you insert a shape, you can first select the graphic group to which you want to add the shape, and then the settings of the shape itself.

When you insert one of the shapes, for example a Fence , into the Frame , the dialog Create Shape looks like this.

<!-- image -->

If the object has more than one graphic group, which you can edit, select the graphic group from the dropdown list to which you want to attach the new shape. The dropdown list shows the name and the display properties of the non-generated graphic group:

- default (external) : Each object has a graphic group named default , which is external by default. External graphic groups represent the object toward the outside. When you insert a shape, Plant Simulation automatically activates Show External Graphic Groups , so that you can check and edit the inserted shape.
- deco (internal) : Frames by default contain an internal graphic group named deco . Only Frames can contain internal graphic groups to decorate their internal view. Internal graphic groups are visible toward the outside, together with the objects contained in the Frame when you select Show Content in the Frame . In the class of the built-in Frame the internal graphic group deco is predefined.
- Invisible graphic groups are graphic groups whose check box Visible on the Tab Graphics is cleared. When you insert a shape, Plant Simulation automatically activates the visibility of the selected graphic group, so that you can check and edit the inserted shape.

In our example we use the fence as a safety fence around a PickAndPlace Robot which prevents the robot from hurting people within its swiveling range.

<!-- image -->

- If you create the fence in the visible internal graphic group named deco of the Frame named Model , then the fence is always visible inside the Frame named Model and outside the Frame only when you activated the check box Show Content for the Frame named Model . In the latter case the robot also is visible outside the Frame named Model if you clear Exclude from "Show content" of the Location .
- If you create the fence in the visible external graphic group named default of the Frame named Model , then the fence is visible in the Frame named Model immediately after creating, but only because Show External Graphic Groups was activated while inserting the fence. When you clear Show External Graphic Groups in the 3D window, which the Frame named Model opened, so that the default window settings for Frames is restored, the fence in this window will be hidden again, as the Frame named Model is only displayed toward the outside. The fence is always visible in the folder named Models while the robot is only visible there if you activate the check box Show Content in the Frame named Model and clear the check box Exclude from Show Content of the Location .
- When you create the fence directly in the window of the PickAndPlace Robot in its single visible graphic group default then the fence becomes an additional part of the external object graphic which represents the robot toward the outside. The fence is visible everywhere where the robot graphic is visible: Always in the Frame named Model , in the folder Models only if you select the check box Show Content in the Frame named Model and cleared the check box Exclude from Show Content of the Location for the robot.

**Graphic Group [for shape]**

<!-- image -->

<!-- image -->

##### Barred Area

Create a barred area and insert it into the Frame .

<!-- image -->

You can use the barred area to set an Obstacle for the Worker . An example would be an area, which the Worker can enter but should not, for example the pivoting range of a crane.

The Worker can enter a barred area when you insert a Footpath . You might, for example use this to allow the Worker to walk through doors in your plant. Model a Worker Who Walks Freely Within the Model demonstrates this.

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Select the Form of the barred area:

<!-- image -->

Our barred area with an X-Dimension of 2 meters and a Y-Dimension of 1 meter looks like this:

<!-- image -->

| Name                      | Settings                                                                                                                                                                                                                                               | Looks like this   |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| Round                     | Dimension X Dimension Y Material                                                                                                                                                                                                                       |                   |
| Rectangular               | Dimension X Dimension Y Material                                                                                                                                                                                                                       |                   |
| Rectangular with hatching | Dimension X Dimension Y Material                                                                                                                                                                                                                       |                   |
| One-sided delimitation    | Length/Dimension X Material A Worker can cross the line on the side with the dashed line but not on the side with the solid line. Depending on the insertion direction of the barred area, he can walk from left to right, but not from right to left. |                   |

- Enter the Dimension in the X -direction and the Dimension in the Y -direction of the barred area.
- Click into the color box next to Material and select the material of the barred area.
- To create the barred area, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the barred area to the location of your choice, click it and drag the mouse.
- To assign a material or a color to the barred area, click the tab Material .

<!-- image -->

To show the barred areas/obstacles for workers in your model, press the o key on the keyboard or click Obstacles on the View tab of the 3D window.

**Note**

When you view the Obstacles for the Worker , you will notice that there is a gap of 40 cm between the obstacles and the objects/graphics. This is because we supposed the width which a Worker needs to pass through to be 80 cm. As our Workers do not have a width as such, you see this distance between the obstacles instead.

To change the Barred Area Settings , click the box with the right mouse button and select 3D Properties &gt; Barred Area Settings .

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The barred area settings reflect this change.

<!-- image -->

**SimTalk**

createBarredArea [SimTalk]

Form [SimTalk]

See also Barred Area Settings Model Your Own 3D Graphic Model a Worker Who Walks Freely Within the Model Model a Worker Who Walks Through Doors Model a Worker Who Walks One-Way Model a Worker Who Climbs Stairs \_Accessing Attributes of Graphic Shapes \_Detailed Access To Graphics Graphic Settings &gt; Obstacle for the Worker [drop-down list] Worker [object] WorkerPool &gt; Travel Mode [drop-down list] of the Worker Video on YouTube https://youtu.be/Rj5eYZu8pl4?si=Njn3RHQlo1ggOEe6&amp;t=516 https://youtu.be/gU1pqu7sWA8?si=dwjpduaBZavnvxN\_&amp;t=544

##### Box

Create and insert a box into the selected Frame .

<!-- image -->

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Box .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Dimension in the X -direction, the Dimension in the Y -direction, and the Dimension in the Z -direction of the box you want to create.

**Note**

To create a flat plate, type in a very small value, for example 0.01 , for the respective Dimension of the box.

- Type in the Wall Thickness of the box. Specify 0 to create the walls of the box without a thickness. Specify a positive value to create the box with the wall thickness you entered.
- Click into the color box next to Material , to assign a material and a color to the box on the Tab Material .
- To create the box, click Create . Plant Simulation attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the box to the location of your choice, click it and drag the mouse.

To change the Box Settings , click the box with the right mouse button and select 3D Properties &gt; Box Settings .

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The box settings reflect this change.

<!-- image -->

SimTalk

createBox [SimTalk]

ObstacleForWorker [SimTalk]

See also

Box Settings

Model Your Own 3D Graphic

\_Detailed Access To Graphics

##### Cone Frustum

Create and insert a cone or a conical frustum into the selected Frame .

<!-- image -->

You can use it to create a Cone Frustum . You can, for example, model a bottle with two cone frustums capped at the top and the bottom.

You can select these settings in the dialog Create Cone Frustum .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Top Radius of the cone frustum you want to create.

A Top Radius of 0 creates the cone frustum with a tip.

<!-- image -->

<!-- image -->

A Top Radius of greater than 0 cuts off the tip of the cone frustum. This way you can, for example, model a bottle quickly and easily.

<!-- image -->

<!-- image -->

- Type in the Bottom Radius of the cone frustum you want to create.

Type in a greater bottom radius than the top radius to create a funnel-type truncated cone frustum.

<!-- image -->

<!-- image -->

- Type in the Height of the cone frustum you want to create.
- Type in the Wall Thickness of the cone frustum.

Do not specify the wall thickness to create a closed cone frustum.

Specify a positive value to create the cone frustum with that wall thickness.

<!-- image -->

- Select Create Covers to create the frustum with a top and a bottom. Clear Create Covers to leave the top and the bottom of the frustum open.

<!-- image -->

<!-- image -->

**Cone Frustum**

- To create the cone frustum, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the cone frustum to the location of your choice, click it and drag the mouse.
- To change the size of the cone frustum, select it and select 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To set if the cone frustum is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Graphic Settings on the Home ribbon tab.
- To assign a material and a color, select the cone frustum and click 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

SimTalk

createConeFrustum [SimTalk]

See also

Model Your Own 3D Graphic

Model a Bottle

##### Cuboid

Create and insert a cuboid into the selected Frame .

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Cuboid .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type the Dimension in the X -direction, the Dimension in the Y -direction, and the Dimension in the Z -direction of the cuboid which you want to create.
- Select the check box Edging to add colored lines to the edges of the cuboid.
- Type in the Width of the borderlines.

Select the Color of the borderlines.

<!-- image -->

- To create a flat, non-textured plate, enter 0 into the respective text box:

<!-- image -->

- To create the cuboid, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the cuboid to the location of your choice, click it and drag the mouse.

- To change the size of the cuboid, select it and click 3D Properties &gt; Tab Transformation on the Home ribbon tab. Then change the size under Scale .
- To set if the cuboid is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Graphic Settings on the Home ribbon tab.
- To assign a material and a color, select the cuboid and click 3D Properties &gt; Tab Material on the Home ribbon tab.

SimTalk

createCuboid [SimTalk]

See also

\_Detailed Access To Graphics

Model Your Own 3D Graphic

Model a Bottle

Internal [check box]

**Cylinder**

##### Cylinder

Create and insert a cylinder into the selected Frame .

<!-- image -->

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Cylinder .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Radius and the Height of the cylinder which you want to create.
- Type in the Wall Thickness of the cylinder.

Do not specify the wall thickness to create a closed cylinder.

Specify a positive value to create the cylinder with that wall thickness.

<!-- image -->

<!-- image -->

- To create an open cylinder with the shell only, select Create Shell .
- To create the cylinder with shell and lid, select Create Top Cover .

<!-- image -->

<!-- image -->

<!-- image -->

- To create the cylinder with shell and bottom, select Create Bottom Cover .

<!-- image -->

<!-- image -->

For special effect you can just create the lid or the bottom of the cylinder.

<!-- image -->

- To create the cylinder, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the cylinder to the location of your choice, click it and drag the mouse.

- To change the size of the cylinder, select it and select 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To set if the cylinder is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Graphic Settings on the Home ribbon tab.
- To assign a material and a color, select the cylinder and click 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

<!-- image -->

**Dimensioning**

##### Dimensioning

Create and insert measurements into the selected Frame .

<!-- image -->

You can use dimensionings to measure the distance between objects as well as the physical dimensions of individual objects.

You can select these settings in the dialog Create Dimensioning .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Select the Dimensioning Space , i.e., the pane on which you would like to show the dimensioning in the 3D window.
- Click Create and select two points by clicking them on the grid. Plant Simulation then shows a line between these points plus the measured value.
- Or click Create , then on a point on an object and then on a point on the second object, to measure the distance between these two points.

<!-- image -->

<!-- image -->

<!-- image -->

- Or click Create , then on a point on a manipulator/animation path anchor point and then on a point on the second manipulator/animation path anchor point, to measure the distance between these two points.

**Dimensioning**

<!-- image -->

- To measure the dimensions of an object, click the first measuring point and then on the second point on the object. Plant Simulation then measures the distance between these two points within the dimensioning space you set. Otherwise, the insertion point of the object is the measuring point.

<!-- image -->

<!-- image -->

You can also create the dimensionings of an object along the three axes one after the other to show them concurrently.

<!-- image -->

To change existing dimensionings, click it with the left mouse button. The dimensioning lines turn green. Press M on the keyboard. Plant Simulation then shows manipulators at the corner points of the dimensioning lines. Drag the respective manipulator to the position of your choice. Press M again when you are done.

<!-- image -->

<!-- image -->

The dimensionings are graphics named deco . They are not connected with the object. If you do not need them any longer, click the line and press Del .

You might want to create a separate graphics group for dimensionings to be able to show or hide it from view or to delete it as a whole.

<!-- image -->

**SimTalk**

createDimensioning [SimTalk]

DimensioningSpace [SimTalk]

MeasuredLength [SimTalk]

MeasuringPoint1 [SimTalk]

MeasuringPoint2 [SimTalk]

TextPosition [SimTalk]

See also

Dimensioning Settings

Undo [3D]

Redo [3D]

**Factory Walls**

##### Factory Walls

Create four walls around your installation and insert them into the Frame .

<!-- image -->

<!-- image -->

You can either create the entire hall with four walls our you can only create a single wall ( Dimension Y or Dimension X of 0). The walls have predefined windows.

You can select these settings in the dialog Create Factory Walls .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Dimension X of the rectangle, which forms the walls of the installation as a whole.
- Type in the Dimension Y of the rectangle, which forms the walls of the installation as a whole.

**Note**

To only create a single wall instead of a set of four walls, enter 0 as the Dimension Y or the Dimension X .

<!-- image -->

- Type in the Dimension Z of the rectangle, which forms the walls of the installation as a whole.
- Type in the Element Width of the individual segments of the wall.
- Type in the Thickness of the individual walls of the rectangle, which forms the walls of the installation as a whole.
- Click into the color box next to Wall Material and select the color for all walls of the installation.
- Click into the color box next to Pane Material and select the color for all window panes of all walls of the installation. You can thus create tinted or mirrored window panes.

Click in the color box next to material to assign a material to the window panes of the walls on the tab Material .

<!-- image -->

- Click to Copy the Current Material Settings you selected. You can then paste these settings into the graphic of another object.

<!-- image -->

The command also copies the corresponding SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic. The syntax is described under Generate SimTalk Code and Copy to Clipboard .

**Factory Walls**

- Click to Paste the Material Settings that you copied to the graphic of the object.
- Click into the color box next to Frame Material and select the color for all window frames in all walls of the installation.
- Select where to Place the Remainder of the elements of the walls. The remainder is the difference between the length of the wall and the next lower multiple of the element width. In the picture below the remainder is the gray part next to the last window on the right-hand side.

<!-- image -->

<!-- image -->

<!-- image -->

| Setting           | Remainder is located                                                           | Looks like this   |
|-------------------|--------------------------------------------------------------------------------|-------------------|
| Clockwise         | clockwise at the end of the wall                                               |                   |
| Counter-clockwise | counter-clockwise at the end of the wall                                       |                   |
| Top and left      | at the top and the left end of the wall depends on the orientation of the wall |                   |

<!-- image -->

<!-- image -->

<!-- image -->

| Setting          | Remainder is located                                                               | Looks like this   |
|------------------|------------------------------------------------------------------------------------|-------------------|
| Top and right    | at the top and the right end of the wall depends on the orientation of the wall    |                   |
| Bottom and left  | at the bottom and the left end of the wall depends on the orientation of the wall  |                   |
| Bottom and right | at the bottom and the right end of the wall depends on the orientation of the wall |                   |

**Note**

When you change the setting for placing the remainder , Plant Simulation resets the cutouts .

- To create the factory walls, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the factory walls to the location of your choice, click it and drag the mouse.
- To assign a material or a color, select the factory walls and click 3D Properties &gt; Tab Material on the Home ribbon tab.
- If you did cut out a piece of a wall, you can click Restore Cutouts . This restores the state of the wall before cutting out a piece of it. To cut out a piece of a graphic, press the + key on the keyboard until only the piece of the graphic is selected that you want to cut out. Press Del on the keyboard to cut the piece out.

To change the settings of the factory walls, click it with the right mouse button and select Edit 3D Properties &gt; Factory Wall Settings .

**Factory Walls**

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The factory walls settings reflect this change.

<!-- image -->

SimTalk

createFactoryWalls [SimTalk]

restoreCutouts [SimTalk]

HasCutouts [SimTalk]

ObstacleForWorker [SimTalk]

PlaceRemainder [SimTalk]

WallElementWidth [SimTalk]

See also

Factory Walls Settings

Insert Factory Walls and Create Passageways

Create a Passageway and a Gate

Model Your Own 3D Graphic

Accessing Attributes of Graphic Shapes &gt; \_Factory Walls Attributes

\_Detailed Access To Graphics

##### Fence

Create and insert a fence into the selected Frame .

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Fence .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Dimension X of the rectangle, which forms the fence.
- Type in the Dimension Y of the rectangle, which forms the fence.
- Type in the Dimension Z of the rectangle, which forms the walls of the fence.
- Type in the Element Width of the individual segments of the fence.
- Select Mesh to insert a wire mesh between the posts of the fence. Or

<!-- image -->

<!-- image -->

<!-- image -->

- Select Panes to insert window panes between the posts of the fence. You can thus create tinted or mirrored window panes.

<!-- image -->

<!-- image -->

Click in the color box next to Material to assign a material to the window panes of the fence in the tab Material .

<!-- image -->

<!-- image -->

- Click to Copy the Current Material Settings you selected. You can then paste these settings into the graphic of another object.

The command also copies the corresponding SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic. The syntax is described under Generate SimTalk Code and Copy to Clipboard .

◦

Click to Paste the Material Settings that you copied to the graphic of the object.

**Note**

You can also create the fence without wire mesh and without window panes, or you can combine both.

<!-- image -->

<!-- image -->

- Click the color box next to Profile Material to assign a material to the profiles of the fence.
- Click in the color box next to Post Material to assign a material to the posts of the fence, which hold the mesh panels.
- Select where to Place the Remainder of the elements of the walls. The remainder is the difference between the length of the wall and the next lower multiple of the element width. In the picture below the remainder is the gray part next to the last window on the right-hand side.

**Note**

As the same settings apply to the factory walls and to the fence , we use one set of screenshots.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Setting           | Remainder is located                                                            | Looks like this   |
|-------------------|---------------------------------------------------------------------------------|-------------------|
| Clockwise         | clockwise at the end of the wall                                                |                   |
| Counter-clockwise | counter-clockwise at the end of the wall                                        |                   |
| Top and left      | at the top and the left end of the wall depends on the orientation of the wall  |                   |
| Top and right     | at the top and the right end of the wall depends on the orientation of the wall |                   |

<!-- image -->

<!-- image -->

| Setting          | Remainder is located                                                               | Looks like this   |
|------------------|------------------------------------------------------------------------------------|-------------------|
| Bottom and left  | at the bottom and the left end of the wall depends on the orientation of the wall  |                   |
| Bottom and right | at the bottom and the right end of the wall depends on the orientation of the wall |                   |

**Note**

When you change the setting for placing the remainder , Plant Simulation resets the cutouts .

- To create the fence, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the fence to the location of your choice, click it and drag the mouse.

To change the settings of the fence, click it with the right mouse button and select Edit 3D Properties &gt; Fence Settings .

Show Manipulators

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The fence settings reflect this change.

<!-- image -->

SimTalk createFence [SimTalk] restoreCutouts [SimTalk] HasCutouts [SimTalk] ObstacleForWorker [SimTalk] PlaceRemainder [SimTalk] FenceElementWidth [SimTalk] See also Fence Settings Model a Worker Who Walks One-Way Model a Worker Who Climbs Stairs Model Your Own 3D Graphic Accessing Attributes of Graphic Shapes &gt; \_Fence Attributes Accessing Attributes of Graphic Shapes &gt; \_Pane Material Attributes \_Detailed Access To Graphics

**Mezzanine**

##### Mezzanine

Create and insert a mezzanine into the selected Frame .

<!-- image -->

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Mezzanine .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Dimension X , the Dimension Y , and the Dimension Z of the mezzanine that you want to create into the dialog Create Mezzanine .
- Type in the Thickness of the floor of the mezzanine.
- Click the color box next to Floor Material to assign a color/material to the floor.
- Type in the post diameter of the Posts on which the mezzanine rests.
- Click the color box next to Post Material to assign a color/material to the posts on which the mezzanine rests.
- Click to Copy the Current Material Settings you selected. You can then paste these settings into the graphic of another object.

<!-- image -->

The command also copies the corresponding SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic. The syntax is described under Generate SimTalk Code and Copy to Clipboard .

<!-- image -->

- Click to Paste the Material Settings that you copied to the graphic of the object.
- Select Border Line to add a boundary line around the platform of the mezzanine.
- Click the color box next to Material to assign a color/material to the borderline around the floor of the mezzanine on the tab Material .
- Select Railing to create railings around the platform of the mezzanine.
- Type in the Segment Width of the individual segments of the railing. The Segment Width is the distance between the individual posts that hold the railing.
- Click the color box next to Material to assign a color/material to the railing around the floor of the mezzanine.
- To create the mezzanine, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .

<!-- image -->

Select the graphic group to which you would like to append the mezzanine and click OK .

- To move the mezzanine to the location of your choice, click it and drag the mouse.

To change the settings of the mezzanine, click it with the right mouse button and select Edit 3D Properties &gt; Mezzanine Settings .

**Mezzanine**

SimTalk createMezzanine [SimTalk] restoreCutouts [SimTalk] HasCutouts [SimTalk] RailingSegmentWidth [SimTalk] ObstacleForWorker [SimTalk] See also Mezzanine Settings Model a Worker Who Climbs Stairs Model Your Own 3D Graphic \_Mezzanine Attributes \_Detailed Access To Graphics

##### Rack

Create and insert a storage rack into the selected Frame .

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Rack .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Bay Dimension X , the Bay Dimension Y , and the Bay Dimension Z of the rack that you want to create into the dialog Create Rack .
- Type in the Thickness of the individual boards of the rack. This is the thickness of a single board. The thickness is not part of the height of the storage bin.
- Type in the Diameter of the Posts of the rack. Plant Simulation adds the post diameter to the bay width. If you do not specify the Post Diameter , the posts have a diameter of 4 cm.
- Type in the Ground Clearance , i.e., the distance between the lower edge of the lowest board and the floor on which the rack sits. Type in 0 that the bottom board sits flat on the ground.
- Type in the number of Storage Bays per Board of the rack.
- Type in the Number of boards (board Count) that form the rack. The topmost shelf is now included in the amount of shelves ( board count ). In the example below the rack has four shelves.
- Click the color box next to Board Material to assign a material to the material of the storage boards.
- Click to copy the current material settings you selected. You can then paste these settings into the graphic of another object.

<!-- image -->

The command also copies the corresponding SimTalk code to the clipboard. You can then paste this code into a Method object to set the material of another graphic. The syntax is described under Generate SimTalk Code and Copy to Clipboard .

<!-- image -->

- Click to paste the material settings that you copied to the graphic of the object.
- Click the color box next to Post Material to assign a material to the posts of the rack.
- Select the Post Form , i.e., if the posts are to be round or square .
- Select how you would like to optimize the graphic of the rack:
- For Post-processing Capability : This setting creates a highly granular structure of the graphic.
- For Performance : This setting creates a particularly flat structure of the graphic.
- To create the rack, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the rack and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the rack to the location of your choice, click it and drag the mouse.
- To change the size of the rack, select it and select 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To change the rack settings of an existing rack, click it with the right mouse button and select Edit 3D Properties &gt; Rack Settings .

<!-- image -->

The Cranes and More library makes extensive use of the rack. Check the high bay warehouse named HBW in our Factory51 example model.

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab or press M on the keyboard. The rack settings reflect this change.

<!-- image -->

SimTalk createRack [SimTalk] BoardThickness [SimTalk] GroundClearance [SimTalk] ObstacleForWorker [SimTalk] See also Rack Settings Model Your Own 3D Graphic Store [object] Appearance of the Store Accessing Attributes of Graphic Shapes &gt; \_Rack Attributes \_Detailed Access To Graphics

**Sphere**

##### Sphere

Create and insert a sphere into the selected Frame .

<!-- image -->

You can select these settings in the dialog Create Sphere .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Enter the Radius of the sphere you want to create into the dialog Create Sphere .
- To create the sphere, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the sphere to the location of your choice, click it and drag the mouse.
- To change the size of the sphere, select it and select 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To set if the sphere is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Graphic Settings on the Home ribbon tab.
- To assign a material and a color, select the sphere and click 3D Properties &gt; Tab Material on the Home ribbon tab.

SimTalk

createSphere [SimTalk]

See also

Model Your Own 3D Graphic

##### Stairs

Create and insert a staircase into the selected Frame .

<!-- image -->

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Stairs .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type in the Tread Width . This is the width of the steps and thus the width of the entire stairway.
- Type in the Rise . This is the height of the entire stairway from the floor of one floor to the ceiling of the next floor.
- Select the check box Start at First Tread to make the stairway start at the first tread without the stringer extending onto the floor on which the stairway rests.

<!-- image -->

<!-- image -->

**Stairs**

- Click into the color box next to Stringer Material and select the material of the stringer. The stringer borders the steps and the handrail laterally.
- Click into the color box next to Tread Material and select the material of the steps between the stringers.
- To create the stairway, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the stairway to the location of your choice, click it and drag the mouse.
- To change settings of the stairway, select it and click it with the right mouse button and select Edit 3D Properties &gt; Stair Settings .

<!-- image -->

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab.

<!-- image -->

SimTalk createStairs [SimTalk] ObstacleForWorker [SimTalk] See also Stairs Settings Model a Worker Who Climbs Stairs Model Your Own 3D Graphic Accessing Attributes of Graphic Shapes &gt; \_Rack Attributes \_Detailed Access To Graphics Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&amp;t=625](https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&t=625)

**Text [graphic shape]**

##### Text [graphic shape]

Creates and inserts any text into the selected Frame .

<!-- image -->

You can select these settings in the dialog Create Text .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.
- Type the text which you would like to add to the scene into the text box Text in the dialog Create Text .
- Select the Text Color , the Background Color , and the Alignment of the text in the 3D window.
- To create the text, click Create . Plant Simulation attaches the text to the mouse pointer. Drag the mouse to the position at which you would like to insert the shape and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the text box to the location of your choice, click it and drag the mouse.
- To change the size of the text, select it and select 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To set if the text is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Graphic Settings on the Home ribbon tab.
- To assign a material, select the text and click 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

Plant Simulation determines which text will be shown via the object type:

- Folder : Plant Simulation shows the name of the folder.
- Comment : Plant Simulation shows the text you enter on the tab Display .
- Variable : Plant Simulation shows the Name and the Value of the Variable .

**Note**

You cannot edit text once you have inserted it into the scene window. If the text does not meet your needs anymore, you have to delete it and create and insert new text.

<!-- image -->

**Textured Plate**

##### Textured Plate

Create and insert a textured plate into the selected Frame . It gives your simulation model a more realistic look.

<!-- image -->

<!-- image -->

You can select these settings in the dialog Create Textured Plate .

- Select the Graphic Group to which you want to add the new graphic if the object has more than one graphic group that you can edit.

###### Textured Plate

- Select the Image which you want to use for the textured plate.
- Define settings for the Plate .
- Define settings for the Texture .
- To create the textured plate, click Create . 3D attaches the shape to the mouse pointer. Drag the mouse to the position at which you would like to insert the textured plate and click the left mouse button. To cancel inserting, you can click the right mouse button or press Esc .
- To move the plate to the location of your choice, click it and drag the mouse.
- To change the size of the textured plate, select it and click 3D Properties &gt; Tab Transformation . Then change the size under Scale .
- To set if the textured plate is an Obstacle for the Worker , select it and then click Edit 3D Properties &gt; Tab Graphic Settings on the Home ribbon tab.
- To assign a material or a color, select the textured plate and click 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

**SimTalk**

createPicture [SimTalk]

createTiledPlate [SimTalk]

See also

Create a Textured Plate

Create a non-textured plate: Insert a Cuboid with the setting 0

###### Image [textured plate]

Click Browse , navigate to the location of, and select the graphic file, which you want to use for the textured plate, in the dialog Select Bitmap . The text box then shows the path to the and the name of the image file.

<!-- image -->

Instead, you can also enter the path to the and the name of the image file into the text box.

SimTalk

createPicture [SimTalk]

**Plate [settings]**

###### Plate [settings]

Define the settings for the plate .

<!-- image -->

<!-- image -->

- Select the Orientation of the plate in the 3D window. You can place it flat on the Floor of the window, as a Front Wall , or as a Side wall .
- Type in the Size X of the plate. You can enter a maximum Width of 32767 pixels.
- Type in the Size Y of the plate. You can enter a maximum Height of 32767 pixels.

If you leave one of the settings for Size X or Size Y empty, the respective other value is computed from the Size X to Size Y ratio.

- Type in the Thickness of the plate.

**SimTalk**

createTiledPlate [SimTalk]

###### Texture

Define the settings for the Texture .

<!-- image -->

**Note**

If your model contains several partially or fully transparent graphics behind each other from your current view point, it can happen that some or all of these graphics look wrong or seem to be missing.

This is due to heuristics without which the rendering performance would drastically decrease.

- To show the texture on both sides of the plate, i.e., on the top and the bottom or on the front and the back, select Show on Both Sides .
- To show transparent or partially transparent pixels in the texture transparent, select Use Transparency . To enforce opacity, clear the check box.

If the image file does not contain transparent pixels, Use Transparency has no effect.

- To fit the picture of the texture to the size of the plate, select Fit Texture to Plate . Depending on the dimensions of your picture you type in under Plate , the texture might be distorted.
- To activate tiling, select Tiling .
- Type in the Tile size X of the individual tiles .
- Type in the Tile size Y of the individual tiles .

If you leave one of the settings for Tile Size X or Tile Size Y empty, the respective other value is computed from the width to height ratio.

#### Make Animatable Object

Converts the selected graphic or several selected graphics into an animatable object which does not have a counterpart in 2D.

<!-- image -->

The command is available for graphics, animatable objects, and for all simulation objects, except for folders and for Connectors .

**Note**

If the graphic, from which the animatable object is created, is not part of the default graphics group, the command creates a graphics group with the name of the graphics group where the graphic to be extracted is located.

- Type in a Name for the newly created animatable object .
- Type in or select the x-, y-, and z-coordinates of the position of the animatable object that will be created.

The lines show a preview of the Object Position which you specified.

**Note**

The Object Position will also be used as the origin of the rotation for poses, around which the object will be rotated. If the object does not rotate as expected, check the values for the individual axes of the origin of the rotation.

<!-- image -->

- Click one of the buttons to set the object position to values which result from the bounding box of the graphic to be converted.

The buttons set the respective partial coordinate which is contained in the combination box to the left.

**X Object Position**

- The down arrow uses the lower value for the X object position. When you click it, the x position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the x position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the x position corresponds to the left border of the bounding box.

**Y Object Position**

- The down arrow uses the lower value for the Y object position. When you click it, the y position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the y position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the y position corresponds to the left border of the bounding box.

**Z Object Position**

- The down arrow uses the lower value for the Z object position. When you click it, the z position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the z position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the z position corresponds to the left border of the bounding box.

◦

<!-- image -->

**Make Animatable Object**

**· Swap X and Z Axis**

To rotate the animatable object around the Y-axis by 90° and thus swap the internal X-axis and the Z-axis of the new animatable object, select this. The animatable object looks the same from the outside.

To use the default setting for the X-axis and the Z-axis, clear the check box.

- Click OK .

**Note**

If the command Lock Structure for one of the involved Frames is active, the command Create Animatable Object will not be executed if you select the command in a 3D window.

If you select the command in the dialog Show 3D Graphic Structure , you can create the animatable object.

After you created the animatable object, Plant Simulation opens the dialog Edit 3D Properties with the tab Joint .

Plant Simulation shows a violet frame in the 3D window of animatable objects.

<!-- image -->

**SimTalk**

- \_3D.getGraphic(…).makeAnimatableObject
- \_3D.addObject [SimTalk]

See also Add Animatable Object Use as Animation Object Create a Simulation Object with Animation Make Simulation Object Create a Simulation Object with Animation Tab Joint &gt; Joint Settings for the Animation Video on YouTube https://youtu.be/rQi5oRyZckQ?si=nMR11EjzeM\_xxh1N&amp;t=850 https://youtu.be/h2cFAH46ESQ?si=ZgXj23RzNDMNVdLf&amp;t=270

#### Make Simulation Object

Converts the selected graphic or several selected graphics into a simulation object . A simulation object is a 3D object that has a counterpart in 2D .

<!-- image -->

**Note**

If the graphic, from which animatable object is created, is not part of the default graphics group, the command creates a graphics group with the name of the graphics group where the graphic to be extracted is located. In previous versions Plant Simulation created the graphics group within the default graphics group.

- Type in a Name for the newly created simulation object .
- Select the 2D object Class that is to be used when creating the simulation object.
- Type in or select the x-, y-, and z-coordinates of the position of the animatable simulation object that will be created.

<!-- image -->

The lines show a preview of the Object Position which you specified.

<!-- image -->

<!-- image -->

- Click one of the buttons to set the object position to values which result from the bounding box of the graphic to be converted.

The buttons set the respective partial coordinate which is contained in the combination box to the left.

**X Object Position**

- The down arrow uses the lower value for the X object position. When you click it, the x position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the x position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the x position corresponds to the left border of the bounding box.

**Y Object Position**

- The down arrow uses the lower value for the Y object position. When you click it, the y position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the y position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the y position corresponds to the left border of the bounding box.

**Z Object Position**

- The down arrow uses the lower value for the Z object position. When you click it, the z position corresponds to the right border of the bounding box.
- The circle with the dot in the middle uses the median value. When you click it, the z position corresponds to the middle of the floor of the bounding box.
- The up arrow uses the upper value. When you click it, the z position corresponds to the left border of the bounding box.

<!-- image -->

**· Click OK .**

The object will always be created in 2D as well and will always be derived from the selected class.

**Note**

If the command Lock Structure for one of the involved Frames is active, the command Create Simulation Object will not be executed when you call the command in a 3D window.

If you call the command in the dialog Show 3D Graphic Structure , you can create the simulation object though.

Plant Simulation shows a green frame in the 3D window of simulation objects.

See also

Create a Simulation Object with Animation

Animatable Object

<!-- image -->

**Undo [3D]**

#### Undo [3D]

Undoes the last undoable 3D command that you changed manually to change the 3D content of your model.

<!-- image -->

**Undo applies to:**

- Any changes you make on the tabs of the Edit 3D Properties [dialog] of the respective object.
- Any changes you make to the dialog Edit Grid and Base Plate Settings .
- Transformations of one or more selected simulation objects , animatable objects , 3D graphics , state graphics , user-defined attributes , or sensors which you changed with the mouse or a keyboard key in the 3D window.
- Transformations of a Connector , a Store , an extrusion object , dimensionings , or of a shape which you changed by moving the selected manipulator , which is displayed for objects, which you can manipulate.
- Alignments of several selected objects , graphics , or user-defined attributes that you changed with the respective context menu command.

<!-- image -->

<!-- image -->

- Inheritance of transformations, anchor points of Connectors , and autoscaling of MUs that you reset with the respective context menu command.
- Move Transformations to Graphics in the dialog Show Graphic Structure .

<!-- image -->

<!-- image -->

- Appending , Editing , or Reversing the segments of a length-oriented object.

<!-- image -->

Deleting the last inserted anchor point of a segment by clicking Delete Last Point in the dialog Line/Arc Parameters when you Insert Curved and Straight Segments .

<!-- image -->

- Creating and deleting of Sensors on length-oriented objects in 3D.
- Changing the View Options of a Frame in these cases: When you explicitly click one of the view options on the View Ribbon tab or when you select the

respective shortcut.

<!-- image -->

By an implicit change that can, but does not have to occur

- When you select the command Open Class
- When you select the command Open Origin
- When you select the command Open Location
- When you activate a Camera Mark
- When you press Backspace for the previous scene or Shift+Backspace for the next scene
- Creating and deleting of 3D graphics , graphic groups , Animatable Objects in the 3D window or in the dialog Show Graphic Structure .
- Grouping, ungrouping, cutting and duplicating of 3D graphics in the 3D window or in the dialog Show Graphic Structure .
- Turning Inherit Graphics in the dialog Show Graphic Structure on or off .
- Removing the Texture of a 3D graphic in the dialog Show Graphic Structure .
- Creating and deleting sensors in the 3D window.

- Actions relating to an Animatable Object :
- When you delete an animatable object via all interactive ways
- When you add an animatable object via Add Animatable Object in the dialog 3D Graphic Structure
- When you copy an animatable object

As soon as Plant Simulation has finished executing an undoable reversible command, it activates the Undo button and the downward arrow for opening a list of undoable commands that you executed before.

<!-- image -->

Each item in the list contains the description of the executed undoable command, followed by a colon, and the identification of the changed item in the scene of the model. These scene items can be objects , graphics , user-defined attributes , sensors , states , or manipulators .

**Compare these examples**

- Drag: MyObject denotes that you moved the selected object, MyObject in the example, with the mouse in the 3D scene.
- Move Left: States of MyObject denotes that you moved the selected state graphic of MyObject to the left with the left arrow key.
- Drag: Manipulator of MyObject denotes that you transformed MyObject by moving one of its displayed manipulators with the mouse in the 3D scene.
- Rotate Clockwise: deco.(1) denotes that you rotated the first graphic of the graphic group named deco.(1) with Ctrl+right arrow around the z-axis.
- Align X-Coordinate: Attribute myAttribute denotes that you aligned the user-defined attribute named myAttribute with the x-side of another selected scene item of the model.
- Reverse Segments: MyConveyor denotes that you reversed the segments of the length-oriented object named MyConveyor .
- Drag: 1 Object(s) + 2 Graphic(s) denotes that you moved one object and two graphics at the same time with the mouse in the 3D scene.

**Note**

For commands that require that you select more than one object ( Arrange Objects , Distribute in Direction , Inherit Positions , etc.) the list only shows the scene items that were actually changed, not necessarily all scene items that were selected while executing the commands.

Click the Undo button once or select the topmost command in the Undo list, or press Ctrl+Z to undo the selected command. This removes that command from the Undo list and adds it at the top of the Redo list. Open the Redo list by clicking the downward arrow below the Redo button.

Select a command of your choice at a lower position in the Undo list to undo all commands from the top of the Undo list up to and including the selected command in the sequence in which they are contained in the Undo list. This adds them in reverse order to the top of the Redo list.

Once the Undo list is empty, Plant Simulation deactivates the Undo button, as no command can be undone.

As soon as a command of yours makes it impossible to undo any command, Plant Simulation empties both the Undo and the Redo lists.

Examples of such commands that discard all remembered undoable 3D commands are:

- Starting or resetting the simulation
- Running a Method or a formula
- Editing the length , width , height , dimension , or booking point of a simulation object
- Creating, deleting or renaming a simulation object
- Creating, deleting or editing a user-defined attribute

**Note**

We strongly advise you to not modify object positions/rotations/polycurves in a 2D and 3D model or create/delete objects in 2D while you also work in 3D at the same time. Otherwise undoing changes in 3D might have unexpected side effects.

See also

Redo [3D]

#### Redo [3D]

Redoes the last undoable command that you undid with Undo .

<!-- image -->

Click the Redo button once or select the topmost command in the Redo list or press Ctrl+Y to redo the selected command.

<!-- image -->

This removes the selected command from the Redo list and adds it at the top of the Undo list.

Select a command of your choice at a lower position in the Redo list to redo all commands from the top of the Redo list up to and including the selected command in the sequence in which they are contained in the Redo list. This adds them in reverse order to the top of the Undo list.

Once the Redo list is empty, Plant Simulation deactivates the Redo button, as no command can be redone.

As soon as the simulation is running or any other action makes it impossible to undo any command, Plant Simulation empties the Undo list and the Redo list.

See also

Undo [3D]

#### Show Manipulators [button]

Shows or hides the manipulators of objects and graphics. Instead, you can also press M on the keyboard.

<!-- image -->

**Note**

Only the windows of Frames and Folders provide the command Show Manipulators .

- If you selected one or several objects, the command shows the manipulators of the selected objects.
- If you did not select anything at all, the command shows the manipulators of all objects and of all graphics, which are contained in the Frame , but not in sub-Frames . This does not encompass graphics which you select by pressing the + -key.

**Note**

When you save your model, Plant Simulation hides the manipulators.

During a path extension, for example when appending segments to a conveyor or when extending an animation path, you cannot hide manipulators.

You can use the manipulators to change the dimensions of an object or a graphic and to rotate it. These changes are reflected immediately in the dialog Edit 3D Properties .

You can move manipulators like you do any other object and you can open the dialog Edit 3D Properties for the manipulator. There Plant Simulation shows the position in coordinates of the owner object, which either is the object that you are editing or the graphic of the object that you are editing. You can change the values in the dialog.

If you use manipulators in 2D/3D models, the coordinate constrictions in 2D also apply for the changes of the object positions with manipulators.

<!-- image -->

The appearance of the manipulator differs from object to object. These objects and graphics provide manipulators:

**· Connectors**

With the manipulators of the start and end anchor points you can change the predecessor or the successor respectively of the Connector and attach it to another object. Drag the start or end anchor point from the current object to another object of your choice.

<!-- image -->

If you did not select anything in the scene, the command also shows the position manipulators of the Connectors in the scene if Connectors are shown in the scene.

You can edit the anchor points with the position manipulator, including the start and the end anchor point.

<!-- image -->

Plant Simulation shows the start and end anchor point of the Connectors cut in half. This clearly separates Connectors without a length of their own and allows to easily select each of the Connectors .

<!-- image -->

**· Length-oriented objects**

With the manipulators of the length-oriented objects ( Turnplate , Turntable , AngularConverter , Conveyor , Converter , Track , TwoLaneTrack , FootPath ) you can change the anchor points of the object and thus its appearance. The manipulator at the start and at the end of the object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

The height of the manipulators of the Pipe goes by the width of the Pipe .

<!-- image -->

Up until Plant Simulation 14.0 you could achieve this with the command Show Segments on the context menu of the length-oriented objects. This did not apply to the Converter , the AngularConverter , the Turnplate , and to the Turntable . These objects now also provide manipulators.

**· PickAndPlace-Robot**

With the manipulators of the bounding box of the PickAndPlace-Robot you can edit its appearance of the object.

<!-- image -->

With the rotation manipulator you can set the rotation of the object with the mouse and with keyboard keys:

**Note**

You cannot select a rotation manipulator together with anything else in a 3D window at the same time.

As soon as you select a rotation manipulator, Plant Simulation deselects the other selection.

As soon as you select anything else, Plant Simulation deselects the rotation manipulator.

This also applies when you hold down Ctrl or Shift when selecting.

- Drag the manipulator with the mouse to the right to rotate the object around the z-axis clockwise. Drag the manipulator to the left to rotate the object counter-clockwise.
- Click the rotation manipulator and press the left arrow key or the right arrow key to rotate the object by 1° at a time.

Hold down Shift and press the left arrow key or the right arrow key to rotate the object by 45° at a time.

**· Store , Chart , Drop-Down List , Button**

You can use the manipulators to change the dimensions of the object.

You can also edit the dimensions of the Store in the dialog Edit 3D Properties &gt; Appearance .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

For the other objects, you can edit the dimensions in their dialog.

<!-- image -->

<!-- image -->

<!-- image -->

With the rotation manipulator you can set the rotation of the object with the mouse and with keyboard keys:

- Drag the manipulator with the mouse to the right to rotate the object around the z-axis clockwise. Drag the manipulator to the left to rotate the object counter-clockwise.
- Click the rotation manipulator and press the left arrow key or the right arrow key to rotate the object by 1° at a time.

Hold down Shift and press the left arrow key or the right arrow key to rotate the object by 45° at a time.

- Simulation objects , such as the Station etc.

This does not apply to Interface , Tank , Mixer , Worker , MUs , Variable , Comment , Display , and Checkbox . You can use the manipulators to change the dimensions of the object by editing its position or its scaling.

<!-- image -->

<!-- image -->

<!-- image -->

With the rotation manipulator you can set the rotation of the object with the mouse and with keyboard keys:

- Drag the manipulator with the mouse to the right to rotate the object around the z-axis clockwise. Drag the manipulator to the left to rotate the object counter-clockwise.
- Click the rotation manipulator and press the left arrow key or the right arrow key to rotate the object by 1° at a time.

Hold down Shift and press the left arrow key or the right arrow key to rotate the object by 45° at a time.

- Parametrizable graphics Factory Walls , Fence , Box , Rack , Barred Area , and Stairs You can use the manipulators to change the dimensions of the graphic.
- .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

Depending on the type of the graphic, you can also change the dimensions in the dialog Edit 3D Properties on the tab Transformation or on the tab Settings .

For Factory Walls and for the Fence you can set one of the dimensions to 0 by dragging the respective manipulator.

<!-- image -->

<!-- image -->

<!-- image -->

With the rotation manipulator you can set the rotation of the object with the mouse and with keyboard keys:

- Drag the manipulator with the mouse to the right to rotate the object around the z-axis clockwise. Drag the manipulator to the left to rotate the object counter-clockwise.
- Click the rotation manipulator and press the left arrow key or the right arrow key to rotate the object by 1° at a time.

Hold down Shift and press the left arrow key or the right arrow key to rotate the object by 45° at a time.

The context menu also provides the command Show Manipulators .

See also

Work with Length-oriented Objects in 3D

**Change the Shape of a Segment**

Context Menu Command Show Manipulators [context menu]

Undo [3D]

Redo [3D]

#### Align to Grid [3D button]

Aligns the selected object or graphic to the grid points of the grid.

<!-- image -->

The command moves the selected objects to the next projected intersecting point of the grid lines. To move the selected objects on the grid level instead, hold down Ctrl .

You can also combine Align to Grid and Snap to Grid .

**Note**

For Align to Grid you can adjust the coordinate that falls perpendicular to the grid by holding down Ctrl while selecting the command.

The commands Align to Grid and Snap to Grid adjust the two coordinates that are placed along the grid plane, which normally are the X-Coordinate and the Y-Coordinate .

See also

Align to Grid [3D context menu]

Snap to Grid

Snap to Objects

Show Grid [View ribbon] - 3D

Arrange Objects

#### Snap to Grid

Snaps objects, which you insert, to the intersections of the grid line.

<!-- image -->

You can also combine Snap to Grid and Align to Grid .

**Note**

The command Snap to Grid does not generally force each and every coordinate onto the grid in 3D, but only then when the coordinate is less than 1/4 of the distance set as the snapping grid. This special function only applies when you move existing objects or graphics or manipulators in your model.

**Note**

The commands Align to Grid , Snap to Grid , and Snap to Objects adjust the two coordinates that are placed along the grid plane, which normally are the X-Coordinate and the Y-Coordinate .

See also

Align to Grid [3D context menu]

Snap to Objects

Show Grid [View ribbon] - 3D

Arrange Objects

Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=vP56IJL8G9FwwCyP&amp;t=271](https://youtu.be/FNpiAaUK8iM?si=vP56IJL8G9FwwCyP&t=271)

#### Snap to Objects

Snaps objects, which you insert into your simulation model, to already inserted and positioned objects. To do so, Plant Simulation uses the position and/or the orientation of the inserted objects.

<!-- image -->

To decide where to snap the object you are about to insert, 3D uses hotspots , which are characteristic positions of its graphic:

- For the normal 3D objects 3D creates a bounding box around the graphic, whose corners, center points of the vertices, and planes are the hotspots.
- The hotspot of Interface objects is their insertion position.
- The hotspots of the length-oriented objects are determined as follows:

Plant Simulation takes all anchor points and the centers of the straight segments and creates a bounding box in the direction of the animation line around them, so that they are the center points of the planes of the bounding box. The corners, the center points of the vertices, and the first and last anchor point are the hotspots of the object.

- Graphics do not have hotspots.

**Note**

The commands Align to Grid , Snap to Grid , and Snap to Objects adjust the two coordinates that are placed along the grid plane, which normally are the X-Coordinate and the Y-Coordinate .

See also

Align to Grid [3D button]

Snap to Grid

Show Grid [View ribbon] - 3D

Arrange Objects

Video on YouTube

[https://youtu.be/FNpiAaUK8iM?si=vP56IJL8G9FwwCyP&amp;t=271](https://youtu.be/FNpiAaUK8iM?si=vP56IJL8G9FwwCyP&t=271)

#### Apply Changes [MUs]

Immediately applies the changes you made to the size of the MU graphic in a 3D window. Plant Simulation then scales or positions MU classes and MU instances anew that inherit settings.

<!-- image -->

The command is not available if you opened the MU in more than one 3D window.

#### edddison

The edddison interface enables you to control the 3D scene via edddison.

<!-- image -->

To do so, you need to acquire the software from edddison , compare http://edddison.com .

**Start/Stop edddison**

The command Start/Stop edddison starts the edddison interface or stops it if it was started already. Plant Simulation will automatically add the objects marked in the 3D scene of the 3D model to the display in edddison if they are marked with a user-defined boolean attribute with the name edddisonObject that has the value true.

**Define Bounding Box**

The command Define Bounding Box sets the bounding box for displaying the 3D model in edddison .

You can type in the Name and the Height of the new bounding box. If a bounding box with this Name already exists in edddison , the existing bounding box will be overwritten.

**Add Marked Objects**

The command Add Marked Objects adds the objects marked in the 3D scene of the 3D model to the display in edddison . Marked objects are objects for which you created a user-defined boolean attribute with the name edddisonObject in Plant Simulation .

**Add Selected Objects**

The command Add Selected Objects adds the objects selected in the 3D scene of the 3D model to the display in edddison .

**Remove All Objects**

The command Remove All Objects removes all objects from the display in edddison .

**edddison**

Visit edddison

The command Visit edddison opens the web page for edddison for Plant Simulation .

#### Omniverse Connector

The Omniverse Connector is a powerful add-on application that helps you transfer your geometries and simulation studies from Plant Simulation into NVIDIA Omniverse to realize an industrial metaverse visualization, simulation, and collaboration experience.

<!-- image -->

**Note**

The Omniverse Connector uses the Tecnomatix Connector for NVIDIA Omniverse licensing mechanism.

The Omniverse Connector is only active if you have a subscription to the NVIDIA Omniverse.

Click the button to start Omniverse .

Click the down arrow to show the subcommands Live Connection and Show Window .

The command Show Window opens the LiveConnect window, where you can configure the connection to NVIDIA Omniverse.

<!-- image -->

See also

Visualize the Simulation Model in Omniverse

#### View Ribbon Tab [3D only]

