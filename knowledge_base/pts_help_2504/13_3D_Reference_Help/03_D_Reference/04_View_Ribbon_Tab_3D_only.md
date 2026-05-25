### View Ribbon Tab [3D only]

The View ribbon tab provides commands to access its functions.

The View ribbon tab in 3D provides these commands.

**Note**

The View ribbon tab is only available in a 3D Only and in a 2D and 3D model.

<!-- image -->

<!-- image -->

<!-- image -->

| Command                                                           | Looks like this   | Method or Attribute                                                             |
|-------------------------------------------------------------------|-------------------|---------------------------------------------------------------------------------|
| Use Planning View                                                 |                   | _3D.PlanningView [SimTalk]                                                      |
| Show Connections                                                  |                   | _3D.ShowConnections [SimTalk]                                                   |
| Show Object Names Show Object Labels Show User-defined Attributes |                   | _3D.ShowNames [SimTalk] _3D.ShowLabels [SimTalk] _3D.ShowUserDefinedAttribute s |
| Show Grid                                                         |                   | _3D.ShowGrid [SimTalk]                                                          |
| Show Base Plate                                                   |                   | _3D.ShowBasePlate [SimTalk]                                                     |
| Show External Graphic Groups                                      |                   | _3D.ShowExternalGraphics [SimTalk]                                              |
| Show Point Clouds                                                 |                   | _3D.ShowPointClouds [SimTalk]                                                   |
| Show Shadows                                                      |                   | _3D.ShowShadows [SimTalk]                                                       |
| Show Sky                                                          |                   | _3D.ShowSky [SimTalk]                                                           |
| Inherit View Options                                              |                   | _3D.inheritAttribute [SimTalk]                                                  |
| Hide Object                                                       |                   | -                                                                               |
| Unhide Objects                                                    |                   | -                                                                               |
| Draw Wireframe                                                    |                   | -                                                                               |

<!-- image -->

| Command         | Looks like this   | Method or Attribute   |
|-----------------|-------------------|-----------------------|
| Show Obstacles  |                   | -                     |
| Virtual Reality |                   | -                     |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to 3D .

#### View All

Adjusts the zoom factor and the position of the main camera, so that all objects in the active scene are visible.

<!-- image -->

When computing the area to be shown, Plant Simulation uses the size of the base plate of the grid that we set.

You can show or hide the base plate by clicking Show Base Plate .

#### Zoom to Objects [button]

Centers and zooms the selected object in the scene window. Then you can closely inspect and manipulate the objects.

<!-- image -->

To show all objects in the scene again, click Show All .

**Left View**

#### Left View

Shows the entire scene from the left , i.e., along the x-axis.

<!-- image -->

<!-- image -->

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

#### Front View

Shows the entire scene from the front , i.e., along the y-axis.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

#### Top View

Shows the entire scene from the top looking down, i.e., along the z-axis.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

#### Right View

Shows the entire scene from the right -hand side, i.e., along the negative x-axis.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

#### Back View

Shows the entire scene from the rear looking to the front , i.e., along the negative y-axis.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

#### Bottom View

Shows the entire scene from the bottom looking up , i.e., along negative the z-axis.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

If Show Grid is activated, Plant Simulation shows the grid below the object that you want to see from below.

If Show Base Plate is activated, Plant Simulation shows the base plate below the object that you want to see from below. The base plate then hides the object as such.

If you selected anything in the scene, the command adjusts the scene so that the selections is visible instead of the entire scene.

#### Grid Position and Orientation

Grid Position and Orientation

Changes the position and the orientation of the grid.

<!-- image -->

**Note**

The command Grid Position and Orientation is only active when Show Grid is active.

The command applies to the 3D window for which you opened the dialog. You can open the dialog once for each opened 3D window.

##### Grid Position and Orientation

**Note**

Plant Simulation does not save the settings you select in this dialog. They only apply as long as the dialog is open.

When you close the dialog, grid position and grid orientation will be reset.

**See also**

Position [grid]

Orientation [grid in 3D]

Position the Grid on Different Planes

<!-- image -->

##### Position [grid]

Type a value into the text box, or roll the mouse wheel up or down to move the position of the origin of the grid on the x-axis, the y-axis and the z-axis. The settings for the three axes are independent of each other.

**Note**

Plant Simulation does not save the settings you select in this dialog. They only apply as long as the dialog is open.

- To set the Position of the Grid to the Origin of the Scene , click this button. The values for the x-axis, the y-axis and the z-axis are then reset to their default values of 0, 0, 0 . This sets the grid to that position, and enters the corresponding values into the text boxes for the x-axis, the y-axis, and the z-axis.
- To set the Position of the Grid to the Origin of the selected Object , click this button. The values for the x-axis, the y-axis and the z-axis are then set to the position of the selected object you selected. This resets the grid to that position, and enters the corresponding values into the text boxes for the x-axis, the y-axis, and the z-axis.

<!-- image -->

**Note**

This button does not have any effect if you did either not select any object at all or selected more than one objects.

<!-- image -->

**Note**

We use a left-handed coordinate system for displaying models in the scene window. In a left-handed coordinate system the thumb of the left hand points to the left in the X-Direction , the left forefinger points forward in the Y-Direction , and the left middle finger points up in the Z-Direction .

Three-dimensional Space, Dimensions and Origin of the Coordinate System

Because we live on a mostly flat surface, we usually think in two dimensions: Left and right, which are the horizontal directions, and front and back. 3D space, on the other hand adds up and down, i.e., the vertical directions.

The three dimensions are called X , Y , and Z . The origin of this 3D space is the location where X is 0, Y is 0, and Z is 0, the point of origin is thus designated as (0,0,0) . When we run three axes right through this point, where the X, Y, and Z axes intersect, each perpendicular to the other two, we can designate the exact location of any point in space relative to the origin. For example, to reach a point at (3,2,1), we start at the origin (0,0,0) move 3 length units in the X-direction, then move 2 units in the Y-direction, and finally move 1 unit in the Z-direction. The numbers are called coordinates and therefore the defined space is called a 3D coordinate space. The coordinates can be negative as well as positive. For example, to find the point located at (-3,2,1), we move down along the x-axis in the opposite direction as we did before. If the positive direction is left, the negative is right, and so forth.

<!-- image -->

##### Orientation [grid in 3D]

To place the grid on the respective plane, select the respective check box.

**Note**

Plant Simulation does not save the settings you select in this dialog. They only apply as long as the dialog is open.

- To place the grid on the XY Plane and to insert objects on this plane, select XY Plane . Here the X and Y axes define the plane of the grid.
- To place the grid on the YZ Plane and to insert objects on this plane, select YZ Plane . Here the Y and Z axes define the plane of the grid.
- To place the grid on the XZ Plane and to insert objects on this plane, select XZ Plane . Here the X and Z axes define the plane of the grid.

<!-- image -->

<!-- image -->

<!-- image -->

#### Edit Grid and Base Plate Settings

Edit Grid and Base Plate Settings

Edits the grid settings.

<!-- image -->

<!-- image -->

**You can:**

- Select the Base Plate Material .

##### Edit Grid and Base Plate Settings

- Select the color of the x- and of the yAxes in the scene window.
- Select settings for the Grid Lines [3D] .
- To apply and display your changes of the grid settings in the scene window, click Apply .
- To apply your changes to the settings and close the dialog, click OK .
- To close the dialog without applying any of the settings you modified, click Cancel .

See also

File &gt; Preferences &gt; 3D &gt; Grid Settings [3D]

Work with the Grid

##### Base Plate Material

To assign a material to the base plate underneath the grid lines in the Frame window, click the color box. Then select the individual components in the dialog Material on the tab Material .

<!-- image -->

You can show or hide the base plate by clicking Show Base Plate on the View ribbon tab.

**Note**

The base plate is not intended to be used as the floor of the factory as you cannot set the size of the base plate.

Use the Same Base Plate Material in Different Models

Proceed as follows to use the same base plate color in different models:

<!-- image -->

- Click into the color box to open the dialog Material in the simulation model whose base plate color you want to copy.
- Click the drop-down arrow in the color box next to Diffuse Color and select More Colors .

<!-- image -->

<!-- image -->

<!-- image -->

- Change to the tab Custom in the dialog Colors and take a screenshot of the color settings.
- Open the simulation model in which you want to use the color settings you just looked up.

<!-- image -->

Click Edit Grid and Base Plate Settings on the View ribbon tab. Follow the steps above and select/type in the settings of the screenshot you just took.

See also

Set Grid Properties

Material [tab]

**Axes Color [3D]**

##### Axes Color [3D]

Click the arrow of the drop-down list Color and select the color of the x-axis and of the y-axis along the bottom and the right-hand side of the scene window.

<!-- image -->

Or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color. Or you can click Custom and select a color in the color matrix. Move the mouse in the color matrix over the area that is similar to the color you want. You can set the attributes of the color with the scrollbar on the right hand side. Click OK to make this color the active color in the program.

##### Grid Lines [3D]

Edit and delete existing grid lines or add new ones in the group box Grid Lines .

<!-- image -->

Each row in the list filed designates a single grid line:

- Double-click in the cell Color and select the color of the grid line in the dialog Colors .

You can select one of the predefined colors, or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation shows this color next to More Colors and uses it as the active color.

- Type a positive value into the cell Interval to set the spacing of the selected grid line.
- Select the check box in the cell Visible to show the grid line. Clear it to hide the grid line.
- Select the check box in the cell Select for Snapping to make an object, which you insert, snap to the grid line. Clear it to not make the object snap to that grid line.
- When you insert a new object, Snap to places the object at the snapping point closest to the point where you position the mouse and click the left mouse button.
- When you move an already inserted object with the mouse, Snap to places the object closest to the snapping point to which you dragged the object and released the mouse button.
- To add a new grid line, click . Then, enter the settings described above into the list field.
- To delete the selected grid line, select it in the list field and click .

<!-- image -->

<!-- image -->

<!-- image -->

Clicking Show Grid on the View ribbon tab of the 3D window shows the grid lines spaced at of 0.2 meters and the other default grid lines.

**Camera Marks**

See also

**Edit Grid Lines**

##### Camera Marks

#### Camera Marks

Saves the active view of the scene in modeling view or in planning view . The command opens the dialog Mark Current Camera Settings , where you type in a name for your camera mark.

<!-- image -->

You can define and activate camera marks, which save the position and the orientation of the camera together with the object displayed in the scene. The button and list Camera Marks allow you to return to these camera marks at any point in time later on.

To return to a saved camera mark, click Camera Marks on the View ribbon tab and select the respective camera mark. You can activate the first nine camera marks by pressing the 1 to 9 keys on the keyboard.

<!-- image -->

- Type a name for the current camera setting into the text box Name or accept the name which 3D suggests.

- 3D shows the path of the scene in the field Scene Path . Click OK to set the name. Plant Simulation then saves this setting together with the active root object of the scene in the model file. This way you can easily return to this saved view after you changed the scene or reopened the model.
- Then, 3D shows the name in the list, when you click the small down arrow at the bottom of the button

<!-- image -->

Plant Simulation enters the camera mark you defined last at the top of the list. Select the camera mark you would like to use there. You can define as many camera marks as you like.

The command Camera Marks opens the dialog Camera Marks . You can activate , rename , move up or move down , or delete the selected camera mark in the list.

<!-- image -->

The command Generate SimTalk Code and Copy to Clipboard generates SimTalk code for the currently defined camera parameters and for the object of interest and copies that code to the clipboard.

The command Generate HtmlReport Code and Copy to Clipboard generates a reference to the 3D object of the scene of the current view for the HtmlReport and copies this code to the clipboard. You can then paste this code into the HtmlReport .

**See also**

Save a View with the Model and Return to It

F3DactivateCameraMark [SimTalk]

F3DconfigurePlanningView [SimTalk]

\_3D.exportPlanningViewBitmap [SimTalk]

**\_3D.exportModelingViewBitmap [SimTalk]**

##### Generate SimTalk Code and Copy to Clipboard [camera mark]

Generates SimTalk code for the currently defined camera parameters and for the object of interest and copies that code to the clipboard.

<!-- image -->

<!-- image -->

For our camera mark called SimulationObjectCylinder the generated SimTalk code looks like this:

<!-- formula-not-decoded -->

**SimTalk**

F3DconfigureView [SimTalk]

\_3D.exportModelingViewBitmap [SimTalk]

\_3D.exportPlanningViewBitmap [SimTalk]

See also

Camera Marks

Display a Picture of a 3D Scene

##### Generate HtmlReport Code and Copy to Clipboard

Generates a reference to the 3D object of the scene of the current view for the HtmlReport and copies this code to the clipboard.

You can then paste this code into the HtmlReport and modify it to meet your needs.

- If Planning View is active, Plant Simulation generates the respective code.

The syntax of the generated code looks like this:

[Path of the object displayed in the scene, caption of the bitmap in the HtmlReport, size of the bitmpap in %, view is displayed in planning view]

<!-- image -->

For our 3D scene above the generated source code looks like this:

[.Models.Model._3D, "caption", 100%, %planningview]

- If Planning View is not active, Plant Simulation uses the current camera position or camera rotation in the 3D scene respectively and copies it to the generated code. The bitmap does not contain the frame around the 3D scene but only the actual contents of the 3D scene.

**The syntax of the generated code looks like this:**

[Path of the object displayed in the scene, caption of the bitmap in the HtmlReport, size of the bitmpap in %, camera position X, camera position Y, camera position Z, camera rotation X, camera rotation Z]

<!-- image -->

For our 3D scene above the generated source code looks like this:

[.Models.Model.\_3D, "caption", 100%, 14.008, -45.346, 22.324, 56.730, -6.989]

**See also**

Display a Picture of a 3D Scene shows additional display options

#### Attach Camera

Attaches the camera to the object you selected, so that you can view the scene through the lens of that object.

<!-- image -->

The camera moves along with the object during a simulation run. 3D represents the attached camera with an object.

To attach a camera to an object:

- Select a single object.
- Click Attach Camera .

<!-- image -->

By default, the object camera faces on the positive x-axis using the positive z-axis as Up direction.

You can rotate the viewing direction of the camera by 0.2° with the arrow keys on the keyboard. To rotate the camera by 2°, hold down Shift while pressing the arrow keys. This applies until you delete the camera or the object.

To reset the viewing direction of the camera to the default setting, press the Home key. To remove the object camera, press Esc .

As soon as the object with the camera attached moves, the camera moves along with it automatically.

SimTalk

F3DattachCamera [SimTalk]

See also

Fly on a Defined Path Through the Scene

Attach a Camera to an Object

#### Detach Camera

Detaches the camera, you attached to an object, from it. Plant Simulation then returns to normal view. Removing an object camera automatically resets the view.

<!-- image -->

Plant Simulation also detaches an object camera:

- When you delete the object the camera is attached to.
- When you change the scene.

**See also**

Fly on a Defined Path Through the Scene

Detach the Camera from an Object

#### Add to Camera Path

Adds the current camera setting to the camera animation path of type Lines . Click Add Current View to add this view to the selected path.

<!-- image -->

You can add camera animation paths to the Frame on the tab Camera Animation .

<!-- image -->

<!-- image -->

#### Animate Camera

Moves the camera on a camera animation path, which you defined for the Frame on the tab Camera Animation . This creates the impression of flying through the scene.

<!-- image -->

To move the animation camera:

- Do not select any object.
- Select the command Animate or click Animate Camera . This opens the dialog Fly on Path of .
- Select the name of the path for the selected object or the root object of the scene from the drop-down list Path name .
- Select Backwards if you want the camera to move backward toward the starting point of the animation path, instead of forward toward the end point of the animation path. 3D automatically enters a negative velocity into the text box when you mark the check box.
- To start the animation, click Play in the dialog. Plant Simulation now shows the scene through the lens of the animation camera, which moves on the path you designated with a lens offset of (0, 0, 0.1).
- To pause or stop the animation of the camera, independent of the simulation, click Pause or Stop .

<!-- image -->

At the end of the animation Plant Simulation sets the main camera to the last point on which the animation camera was located and deletes the animation camera.

See also

Camera Animation [Frame]

Fly on a Defined Path Through the Scene

#### Use Planning View

Switches from the view of the scene as you adjusted it to your needs by rotating or zooming it to the view on the scene from above. This matches the view onto your model as 2D displays it.

<!-- image -->

Plant Simulation shows the background of the Frame without a color gradient and white by default. This is not the case if you set a color of its own for the opened Frame or the folder .

Plant Simulation shows the grid, independent of the grid settings, without a base plate.

Our example model looks like this in Planning View in 3D:

<!-- image -->

It looks like this in Icon View in 2D:

<!-- image -->

It looks like this in Perspective View in 3D:

<!-- image -->

3D hides the placeholders for state graphics by default. The state of an object with vertical state graphics is shown as a small colored dot. In the example below this is the small dot in the top left corner of the picture of the object. You can zoom this dot or move it by transforming the state graphic.

<!-- image -->

You can also navigate with a 3D mouse . The axes correspond to those that are also used in modeling view.

In Planning View you cannot show the base plate below the grid in the scene.

When you select an object in Modeling View and then activate Planning View by clicking the button, Plant Simulation centers the view around the selected object.

Compare these examples:

<!-- image -->

SimTalk

\_3D.PlanningView [SimTalk]

See also

Manipulate the Scene with the Mouse

- \_3D.exportPlanningViewBitmap [SimTalk]
- \_3D.exportModelingViewBitmap [SimTalk]

#### Show Object Names

Show Object Names [3D]

The command Show Object Names provides these sub-commands:

- Show Object Names
- Show Object Labels
- Show User-defined Attributes

Show Object Names [View ribbon] - 3D

Shows or hides the Names of the objects in the Frame .

<!-- image -->

By default, Plant Simulation does not show the Names and the Labels of the objects in the Frame . To show them, you have to select Name/Label Activated under Home &gt; Edit 3D Properties &gt; Tab Captions .

<!-- image -->

**SimTalk**

**\_3D.ShowNames [SimTalk]**

See also

Captions

##### Show Object Labels [View ribbon] - 3D

Shows or hides the Labels of the objects in the Frame .

<!-- image -->

To show the command, click the small down triangle on the button Names and then Labels .

Captions , i.e. names and labels of the objects, are most useful for objects that are not simulationrelevant, like Methods , DataTables , etc

<!-- image -->

<!-- image -->

**SimTalk**

**\_3D.ShowLabels [SimTalk]**

See also

Captions Show User-defined Attributes [View ribbon] - 3D

Shows or hides the User-defined Attributes of the simulation object displayed in the 3D window .

<!-- image -->

To show the command, click the small down triangle on the button Names and then User-defined Attributes .

**Note**

Show User-defined Attributes is available for any 3D window displaying a simulation object, even if Show Object Names is not active. This enables you to show or hide the user-defined attributes of all stationary objects in the 3D window.

**Note**

Show User-defined Attributes shows/hides user-defined attributes of all stationary objects in the 3D window but not of movable objects. If they are shown externally, these are always visible.

<!-- image -->

SimTalk

\_3D.ShowUserDefinedAttributes [SimTalk]

See also

User-defined Attributes [general description]

Show in 3D [user-defined attribute]

**Captions**

#### Show Connections [View ribbon] - 3D

Shows or hides connecting objects, i.e., Connectors , Interfaces , and Markers in the active 3D window.

<!-- image -->

<!-- image -->

The command Show Connections also shows or hides material flow directions of the length-oriented objects the active 3D window for which you selected Show Material Flow Direction .

<!-- image -->

By default, 3D does not show Connections in the 3D windows. When you insert a Connector , an Interface , or a Marker into a Frame , Plant Simulation activates the button.

SimTalk

\_3D.ShowConnections [SimTalk]

See also

Show Material Flow Direction

\_3D.ShowMaterialFlowDirection [SimTalk]

#### Show Grid [View ribbon] - 3D

Shows or hides the grid.

<!-- image -->

It shows it with the spacing of the grid lines which you specified in the dialog Edit Grid and Base Plate Settings .

**Note**

As long as Show Shadows is active, grid lines will not be shown.

<!-- image -->

The 3D window creates the grid each time anew when you make a change to the model when it redraws the scene anew.

When you insert an object and move it to the borders of the grid, the grid is automatically enlarged in that direction. The grid will always grow or shrink to show all inserted objects in the scene.

As the grid serves as a modeling aid when creating the model, you will hide it as a rule when you are going to show or demonstrate the model. To do so, press Ins on the keyboard.

Plant Simulation then hides the area of the grid in which you did not model and thus shrinks the displayed area. It shows the inserted objects on the base plate below the grid.

<!-- image -->

The origin of the grid, i.e., the lines that are red by default, are always part of the grid.

The grid size is always a multiple of the smallest visible grid dimension.

<!-- image -->

When you scale the scene up or down, by moving objects to the left or to the right or to the top or to the bottom of the scene window, 3D automatically switches to the next spacing of the grid lines after reaching a pre-defined threshold value.

The zoom factor of the grid lines depends on the size of the grid in the scene. When you increase or decrease the grid in the scene, Plant Simulation increases or decreases the distance between the grid lines from a certain threshold on.

SimTalk

\_3D.ShowGrid [SimTalk] See also Edit Grid and Base Plate Settings Work with the Grid Edit &gt; Align to Grid [3D button] Edit &gt; Snap to Grid Edit &gt; Snap to Objects Context menu &gt; Arrange Objects

#### Show Base Plate

Shows or hides the base plate below the grid.

<!-- image -->

Note

As long as Show Shadows is active, the base plate will not be shown.

Set the Base Plate Material in the dialog Edit Grid and Base Plate Settings .

<!-- image -->

In Planning View you cannot show the base plate below the grid in the scene.

SimTalk

\_3D.ShowBasePlate [SimTalk]

See also

Edit Grid and Base Plate Settings

Work with the Grid

#### Show External Graphic Groups

Shows or hides all graphic groups of the object in the active 3D window that are not marked as Internal .

<!-- image -->

- For the Frame you can show or hide external graphics by clicking the button.
- For 3D windows of all other objects the button is permanently on .
- For the 3D window of a folder the button is permanently off .

<!-- image -->

<!-- image -->

Graphics are objects without parameters relevant to the simulation. Normally graphics are part of an object providing it with graphics data for displaying it. Displaying this graphic enables you to edit the graphic data of the object displayed in the scene. You can then edit, extend or replace an existing graphic to transform it, or you can create, import or copy another graphic.

<!-- image -->

<!-- image -->

<!-- image -->

When you create and insert a 3D shape for the first time, 3D shows the graphic of the Frame in the center of the 3D window and attaches the shape you defined to the mouse pointer. The reason for this

is that 3D automatically activates Show External Graphic Groups to show the graphics in the scene window. If this would not be the case, the shape that we inserted, which is a graphic after all, would not be shown as well. To show the shape, just delete the graphic of the Frame .

**Note**

When you open a Frame or a folder in a 3D window, Show External Graphic Groups is cleared by default. When you open any other object, it is activated by default.

Plant Simulation does not save for the individual Frames if Show External Graphic Groups is cleared. When you open any other object, the command is activated by default.

Showing external graphic groups is useful to edit them:

You can transform and replace any displayed graphic group by selecting, moving, rotating, scaling, or deleting it in the 3D window. In addition, you can add new created 3D shapes or imported graphics into any graphic group of the opened object by inserting into the 3D scene.

When you start to insert a new created shape into an external graphic group, 3D automatically activates Show External Graphic Groups until you click the destination position so that you can align the input graphic at the mouse pointer with all other graphics of the destination graphic group.

When you imported or dropped graphics to an external graphic group, the Plant Simulation also automatically activates Show External Graphic Groups so that the inserted graphics do not disappear after inserting them.

SimTalk

\_3D.ShowExternalGraphics [SimTalk]

See also

Graphics [tab, 3D] &gt; Graphic Groups [described]

Internal [check box]

Video on YouTube

[https://youtu.be/jHOZhlwGhkQ?si=vIcZAB\_uNUMBNYp\_&amp;t=884](https://youtu.be/jHOZhlwGhkQ?si=vIcZAB_uNUMBNYp_&t=884)

#### Show Point Clouds

Shows or hides point clouds in the active 3D window.

<!-- image -->

**Note**

Point clouds are only available in the Professional , in the Research , and in the Educational License .

**Note**

Initially, your 3D window might only show small parts of the point cloud. When you start rotating the view, 3D shows additional parts of the graphic.

Plant Simulation will load the point cloud significantly faster if the point cloud file is located on an SSD storage device.

SimTalk

**\_3D.ShowPointClouds [SimTalk]**

See also

Point Cloud

- \_\_Accessing Point Clouds

Add a Point Cloud

#### Show Shadows

Shows or hides the shadows, which the objects throw, in the Frame . Showing shadows hides the grid lines.

<!-- image -->

Captions , manipulators , path visualizations , and some display objects, for example Variable , Comment , etc. will mostly not throw shadows.

**Note**

As long as Show Shadows is active, grid lines will not be shown. When you clear Show Shadows , the grid will be shown again.

<!-- image -->

**SimTalk**

\_3D.ShowShadows [SimTalk]

#### Show Sky

Shows or hides the sky around the 3D scene.

<!-- image -->

When you show the sky, Plant Simulation deactivates the Planning View . When you activate Planning View , Plant Simulation hides the sky. This also applies when you Show Shadows . This also applies when you activate Shadows with the attribute \_3D.ShowShadows .

You cannot activate the Sky if the file Sky.jt does not exist in the installation folder, by default C:\Program Files\Siemens\Tecnomatix Plant Simulation\XX\3D\ . This is the case for Pack-and-Go-models . The file has to be available continuously from the moment you start Plant Simulation . Let's suppose that you start Plant Simulation from an installation that is only available within your network. If the network is not available when you want to show the sky, the sky will not be available during the entire Plant Simulation session.

<!-- image -->

SimTalk

\_3D.ShowSky [SimTalk]

#### Inherit View Options [3D only]

Turns inheritance of the view settings of the active Frame from its class off or on.

<!-- image -->

<!-- image -->

- When you turn it on, the current Frame inherits all view settings from its class object.
- When you turn it off, the view settings you select only apply to the current Frame .

**SimTalk**

\_3D.inheritAttribute [SimTalk]

**Hide Objects [3D]**

#### Hide Objects [3D]

Hides the selected object or several objects, which you selected by Shift+clicking , from view in the active scene.

<!-- image -->

The object is displayed again as soon as you select the command Unhide Objects or you open the scene again.

#### Unhide Objects

Redisplays all objects which you temporarily hid in the current scene with the command Hide Object .

<!-- image -->

#### Draw Wireframe

Just draws the edges of the 3D objects in the 3D scene so that they appear as a wire-frame model of the object.

<!-- image -->

This representation is useful to get an idea about the number of polygons and thus the amount of graphic data.

Where the representation in the wireframe model is denser, i.e., looks more like the normal display, the graphic contains many and complex polygons.

Where the representation looks more hollow, it contains fewer and less complex polygons.

<!-- image -->

#### Show Obstacles

Shows or hides obstacles for the Worker in the model.

<!-- image -->

You can also press the o key on the keyboard to show or hide obstacles .

<!-- image -->

You can plan the routes, on which the Worker walks from the WorkerPool to the Workplaces , in a way that he walks around or over obstacles along the route.

For the Workplace Plant Simulation shows two bounding boxes with a gap in between. This ensures that the Worker only stays on the middle of the Workplace . The Worker first has to leave the Workplace before he can change his walking direction toward the next destination object.

For the object Conveyor Plant Simulation approximates the display of the bounding box only roughly to the curve, i.e., it does not show the curve of the conveyor as a smooth curved line.

**Note**

When you view the Obstacles for the Worker , you will notice that there is a gap of 40 cm between the obstacles and the objects/graphics. This is because we supposed the width which a Worker needs to pass through to be 80 cm. As our Workers do not have a width as such, you see this distance between the obstacles instead.

The command also shows the dialog Worker Walking Heights . It shows the walking heights of the Worker which Plant Simulation computed. The Worker Walking Height is the height on which the Worker walks if he moves through the plant on different elevations. You can show or hide the individual walking heights by checking or clearing the respective check box.

The dialog box Worker Walking Heights also shows the number of obstacles and the number of the resulting corner points . A default obstacle has four vertices. A Conveyor with several segments or a circular obstacle can have more vertices though.

The more vertices the obstacle has, the more complex the route network gets and the longer it takes to compute the shortest route.

In Planning View the 3D window shows the obstacles with a width of 10 cm.

<!-- image -->

<!-- image -->

**Note**

The Worker walks slower on an incline than he walks on a flat surface.

**Note**

If the Worker walks freely within the area , he can only get to a different floor in the building by walking up or down a ramp on a Footpath or walking up and down Stairs .

The example model Factory 51 demonstrates how you can use Stairways .

<!-- image -->

See also

Obstacle for the Worker [drop-down list]

Edit 3D Properties &gt; Graphic Settings &gt; Obstacle for the Worker

Barred Area

Model a Worker Who Walks Freely Within the Model

Model a Worker Who Climbs Stairs

Worker [object] in 2D

WorkerPool &gt; Travel Mode [drop-down list] of the Worker

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=Njn3RHQlo1ggOEe6&amp;t=516](https://youtu.be/Rj5eYZu8pl4?si=Njn3RHQlo1ggOEe6&t=516)

#### Go VR

##### Use a HTC Vive HMD

Go VR enables you to experience your 3D model in virtual reality (VR), i.e., to immerse into the model itself.

With suitable VR devices you can enjoy a stereoscopic view of the model through a head mounted display (HMD) and navigate in the model with hand controllers, thus you can easily look around in virtual reality and walk through the virtual scene as if you were part of it.

If you do not have your own VR devices, our partner more3D provides consulting services with the application moreViz and VR installations of different scope and by different suppliers. In Plant Simulation VR only a single user can experience virtual reality, while a group of people can simultaneously immerse into the same Plant Simulation model in moreViz . Consult http://www.more3d.com .

Our description of Plant Simulation VR covers these topics:

- Plant Simulation VR Requirements and Setup
- Start Plant Simulation VR with Go VR
- Troubleshoot Go VR
- Plant Simulation VR Controller Mappings
- Move in Plant Simulation VR
- Interact with the Virtual Scene
- Terminate Plant Simulation VR

##### Plant Simulation VR Requirements and Setup

Before you try out Plant Simulation VR , we recommend you check on a website if your computer and its graphics card support VR applications.

You can check the settings on https://store.steampowered.com .

According to our tests, you can also use Plant Simulation VR with components of a lower specification if the respective Plant Simulation model is not too large and if the simulation and animation do not require too much computing power.

We exclusively developed and tested Plant Simulation VR with a basic HTC Vive set. We assume though that all newer HTC Vive devices work in Plant Simulation as well, as customers confirmed the successful use of HTC Vive Pro sets. Plant Simulation might also work with the VR hardware of other manufacturers as Plant Simulation uses the interface software of the SteamVR virtual reality platform published by Valve . According to Valve SteamVR also supports Valve Index , Oculus Rift , and Windows Mixed Reality headsets in addition to the HTC Vive headset. We do not have any experience with these devices in Plant Simulation though.

Before you can start Plant Simulation VR :

1. Install Plant Simulation 2302 or higher on your computer.
2. Install SteamVR on your computer. You can download it for free on the Web. Make sure that you have the current version of SteamVR .
3. Place the two sensors at suitable positions in space in your room according to the device instructions. Make sure that they are placed at a sufficient height and distance from each other and that they can see each other.
4. Connect the HMD proper with the graphics card and with a USB port of your computer according to the device instructions.
5. Consult the HTC Vive help for additional installation instructions and troubleshooting measures.
5. Make sure that the sensors and the HMD are turned on. HTC Vive devices show that with a green LED.
6. Make sure that the VR set was calibrated correctly in SteamVR according to the device instructions. This encompasses the registration of the hardware components and setting the space within which you, as the real VR user, can move.
7. Turn on a VR hand controller by pressing its System button. The HTC Vive controller is ready when the LED is green. If the LED is red, the battery is weak or empty.
8. Start Plant Simulation and open the 3D simulation model into which you want to immerse.
9. Open or select the 3D window with the scene into which you want to immerse.

Go to Start Plant Simulation VR with Go VR

Go to Troubleshoot Go VR

Go to Plant Simulation VR Controller Mappings Go to Move in Plant Simulation VR Go to Interact with the Virtual Scene Go to Terminate Plant Simulation VR Back to Use a HTC Vive HMD

##### Start Plant Simulation VR with Go VR

To start Plant Simulation VR , click Go VR .

**Icon**

<!-- image -->

**Remarks**

Before you can immerse into your Plant Simulation model, i.e., before you can view the opened 3D scene with an HMD in virtual reality, Plant Simulation opens this dialog on your screen:

<!-- image -->

If you do not want to show this dialog each time you start Plant Simulation VR , select Do not show this dialog again . To show the dialog again, although you selected the check box, hold down Ctrl while clicking the Go VR button.

Click the Help button to open help about the Plant Simulation VR Controller Mappings .

<!-- image -->

Click OK to close the dialog and to set where you want to immerse into your 3D model.

Move the avatar, i.e., the manikin representing you in the 3D scene, with the mouse to the location in the 3D scene where you want to immerse into virtual reality and click the left mouse button .

<!-- image -->

After you have completed all the checks listed above, SteamVR starts automatically if it hasn't been started yet. If SteamVR is currently running, it shows a dialog. If not, it may take some minutes before the dialog is shown.

<!-- image -->

You should see the 3D scene of your Plant Simulation model from the position of the start avatar immediately after you started Plant Simulation VR :

**Note**

In general Plant Simulation views the virtual scene from the height at which the HMD is located above ground. If you are sitting down, this is considerably lower than the eye height of the standing avatar, which is 165 cm. To experience a walk-through of the virtual model from a realistic height, we recommend standing up when wearing the HMD. If you want to experience Plant Simulation VR while sitting down, create a registry key of type DWORD with the value 1 under Siemens/Tecnomatix Plant Simulation &lt;current version&gt;/Preferences/3D/VRPlayerIsSitting . This raises the viewing height by 50 cm.

<!-- image -->

- The 3D window in Plant Simulation shows the start view as a frozen 3D image.
- The HMD shows the start view stereoscopically as a virtual reality scene. Each movement of the HMD/ your head changes the VR view accordingly. The virtual scene additionally shows the hand controllers that you activated at the same position at which they are located in the real world relative to the HMD. This enables you to grab an active real controller with your hand without taking the HMD off. Plant Simulation VR shows the hand controller you turned on first blue and the hand controller you turn on second gray.
- To show the VR view on the computer screen in addition, select the menu command Show VR View in the dialog of SteamVR .

Back to Plant Simulation VR Requirements and Setup

Go to Troubleshoot Go VR

Go to Plant Simulation VR Controller Mappings

Go to Move in Plant Simulation VR

Go to Interact with the Virtual Scene

**Go to Terminate Plant Simulation VR Back to Use a HTC Vive HMD**

##### Troubleshoot Go VR

We provide detailed instructions to troubleshoot Go VR .

**Note**

Plant Simulation VR does not show point clouds.

If you do not see your Plant Simulation scene in the HMD, although you followed all of the steps described under Plant Simulation VR Requirements and Setup and Start Plant Simulation VR with Go VR , check the following:

1. Check your VR devices : Make sure that both sensors and the HMD are correctly installed, registered, and activated.
2. Close SteamVR and any other VR applications that are still running.
3. Update SteamVR to the latest version.
4. Check SteamVR messages and fix any errors described in the messages according to the SteamVR support.
5. Test Plant Simulation VR with the Plant Simulation demo model Factory51 .
6. Check debug information in the Plant Simulation Console .

To show debug information in the Plant Simulation Console , turn on the Debug Console Filter in Plant Simulation .

- Select File &gt; Preferences &gt; User Interface &gt; Console filter &gt; Debug .
- Click Console on the Window ribbon tab to open the Console .

When you start Plant Simulation VR it should at least show the following messages in the Console telling you that:

- The Navigator was activated, provided you activated the first-hand controller.
- The Selector was activated, provided you activated the second hand controller.
- SteamVR was closed if you terminated SteamVR .
- Plant Simulation VR was stopped when you terminated Go VR or pressed Esc or if you terminated SteamVR .

If none of the above hints solve your problem, provide the Plant Simulation team with the following information:

- The Plant Simulation version you use.
- The model type of the VR devices you use.
- Any VR messages that were printed to the Console .

- The Plant Simulation model for which VR does not work.

**Note**

In general Plant Simulation views the virtual scene from the height at which the HMD is located above ground. If you are sitting down, this is considerably lower than the eye height of the standing avatar, which is 165 cm. To experience a walk-through of the virtual model from a realistic height, we recommend standing up when wearing the HMD. If you want to experience Plant Simulation VR while sitting down, create a registry key of type DWORD with the value 1 under HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation &lt;current version&gt;\Preferences\3D\VRPlayerIsSitting . This raises the viewing height by 50 cm.

Back to Plant Simulation VR Requirements and Setup

Back to Start Plant Simulation VR with Go VR

Go to Plant Simulation VR Controller Mappings

Go to Move in Plant Simulation VR

Go to Interact with the Virtual Scene

Go to Terminate Plant Simulation VR

Back to Use a HTC Vive HMD

##### Plant Simulation VR Controller Mappings

The VR hand controller provides these controls:

<!-- image -->

You can use these controls in Plant Simulation to execute the described action.

<!-- image -->

Back to Plant Simulation VR Requirements and Setup

Back to Start Plant Simulation VR with Go VR

Back to Troubleshoot Go VR

Go to Move in Plant Simulation VR

Go to Interact with the Virtual Scene

Go to Terminate Plant Simulation VR

Back to Use a HTC Vive HMD

Moving in Plant Simulation VR

Move in Plant Simulation VR

After you start Plant Simulation VR , you immerse into the VR scene with the position and orientation of the avatar, which you placed in the 3D scene.

When wearing the HMD, you can change the VR view, i.e., the viewing direction and the position from which you view the virtual scene, by turning, raising, lowering, or moving your head or your entire body. The movement of the HMD in the real world is limited by its connection cable to the computer as well as by the space within which you move.

If you calibrated your HTC Vive HMD for room-scale VR, it shows the borders of the play area you set as blue grid walls in the virtual scene. Do not physically cross these borders to avoid colliding with real objects in your room in the real world.

To move in the VR scene across the borders of the HMD and the play area, you have to activate one of the hand controllers of the VR set that you registered while calibrating it.

The virtual scene shows the hand controller you turned on first in blue in the scene at the same position at which it is located in the real world relative to the HMD. This enables you to grab the real controller with your hand without taking the HMD off.

With the blue controller you can navigate, i.e., you can change your virtual position and view direction in the VR scene without the need to physically move, but you can, in addition, change your view direction by moving the HMD.

In Plant Simulation VR you can:

- Walk or Fly with the Hand Controller
- Turn Left or Right with the Hand Controller

###### Move in Plant Simulation VR

· Teleport with the Hand Controller Back to Plant Simulation VR Requirements and Setup Back to Start Plant Simulation VR with Go VR Back to Plant Simulation VR Controller Mappings Back to Start Plant Simulation VR with Go VR Go to Interact with the Virtual Scene Go to Terminate Plant Simulation VR Back to Use a HTC Vive HMD

###### Walk or Fly with the Hand Controller

You can walk in the VR scene with a constant speed in the direction in which the blue controller points. To do so, press and hold down its trigger on the underside of the controller. As long as you hold down the trigger, the controller shows the direction in which it points as a red beam.

<!-- image -->

While you hold down the trigger, Plant Simulation VR moves you forward at a constant height, parallel to the XY plane.

You can temporarily override the height fixation by holding down the grip button on the side of the blue controller in addition to the trigger. Plant Simulation VR then also moves you up or down when you point the blue controller up or down. This enables you to walk up and down stairs or fly up into the sky to get an overview of the virtual scene.

To double or halve the speed with which you walk forward, press the upper or lower border of the trackpad of the blue controller for a short time in addition to holding down the trigger.

The continuous autonomous camera movement may cause motion sickness for sensitive VR users. To avoid this, move by single strides through the virtual scene by pressing the upper or lower border of the trackpad of the blue controller for a short time. This moves you forward or backward immediately by one meter in the direction into which the blue controller points at a constant height.

You can temporarily override the height fixation by holding down the grip button on the side of the blue controller in addition to pressing the trackpad .

Go to Turn Left or Right with the Hand Controller

Go to Teleport with the Hand Controller

Back to Move in Plant Simulation VR

###### Turn Left or Right with the Hand Controller

To rotate your view direction around your vertical axis in the VR scene, i.e., to turn your VR view independent of the movement of the HMD, press the grip at the side of the blue controller while you rotate the blue controller to the left or the right. Your view orientation changes with the same speed and in the same direction as you move the blue controller.

To turn by single steps of 45 degrees to the left or the right, press the left or right border of the trackpad of the blue controller for a short time.

<!-- image -->

Back to Walk or Fly with the Hand Controller

Go to Teleport with the Hand Controller

Back to Move in Plant Simulation VR

###### Teleport with the Hand Controller

You can jump directly from one location to another in the VR scene, without having to take a series of strides or by physically walking. This does not cause any motion sickness.

**To teleport:**

1. Press and hold the trackpad center of the blue controller.

A trajectory stream , consisting of a series of red triangles, is emitted from the top of the blue controller, out in an ascending arc across the virtual scene.

<!-- image -->

2. Observe where the trajectory stream contacts the floor or an object in the virtual scene.

Plant Simulation VR marks the end point of the trajectory stream as a potential teleport destination by an avatar standing on this target position.

3. Move the trajectory stream in the virtual scene by turning, raising or lowering the blue controller. The inclination of the blue controller determines the length of the trajectory stream and thus your
2. distance to the target position. If the trajectory stream intersects an object in the virtual scene, Plant Simulation VR assumes this intersection point as the target position, otherwise it assumes the end point of the trajectory stream on the virtual floor, i.e., the XY plane, as the target position.
4. When the avatar stands at the desired target location, release the trackpad .

You are teleported to the target position, i.e., your virtual view changes to the view of the avatar shown before.

Back to Walk or Fly with the Hand Controller

Back to Turn Left or Right with the Hand Controller

Back to Move in Plant Simulation VR

**Interacting with the Virtual Scene**

##### Interact with the Virtual Scene

After you activate the second hand controller by pressing its System button, Plant Simulation VR displays it in the virtual scene in gray.

The gray hand controller serves for interacting with the simulation model in virtual reality.

The blue hand controller primarily serves for navigating in the virtual scene.

**You can:**

- Click a Button or Checkbox in Plant Simulation VR
- Start or Stop the Simulation in Plant Simulation VR

Back to Plant Simulation VR Requirements and Setup

Back to Start Plant Simulation VR with Go VR

Back to Troubleshoot Go VR

Back to Plant Simulation VR Controller Mappings

Back to Move in Plant Simulation VR

Go to Terminate Plant Simulation VR

Back to Use a HTC Vive HMD

###### Click a Button or Checkbox in Plant Simulation VR

While you press and hold down the trigger of the gray controller, the direction in which the gray controller points is shown as a red beam.

As soon as the beam hits an interaction object, currently a Plant Simulation object of type Button or Checkbox , the color of the beam changes to green.

In addition, a Button that is picked with the green beam is shown as pressed, just like in the 3D window when the button is selected with the mouse.

<!-- image -->

When you release the trigger of the gray controller while the beam is green, Plant Simulation VR toggles the Button or the Checkbox and executes the control you programmed for this action of the respective object.

Go to Start or Stop the Simulation in Plant Simulation VR

Back to Move in Plant Simulation VR

###### Start or Stop the Simulation in Plant Simulation VR

You can Start or Stop the Simulation in Plant Simulation VR by pressing the Menu button on either the blue or the gray hand controller.

<!-- image -->

Back to Click a Button or Checkbox in Plant Simulation VR

Back to Move in Plant Simulation VR

##### Terminate Plant Simulation VR

To terminate Plant Simulation VR , click Go VR again in Plant Simulation or press Esc .

Then, you can view the current 3D scene again on your computer screen and continue working with it there.

SteamVR stays open for your further use until you close the SteamVR dialog.

Back to Plant Simulation VR Requirements and Setup

Back to Start Plant Simulation VR with Go VR

Back to Troubleshoot Go VR

Back to Plant Simulation VR Controller Mappings

Back to Move in Plant Simulation VR

Back to Interact with the Virtual Scene

Back to Use a HTC Vive HMD

#### Video Ribbon Tab

