### Working with the Grid

#### Work with the Grid

3D uses the grid as the surface onto which it inserts objects.

Be aware that showing or hiding the grid affects how objects behave:

- When you show the grid, manipulating objects always refers to the grid plane .
- When you hide the grid, manipulating objects refers to your view plane , i.e., the plane perpendicular to the direction in which you look at the scene.

To change and define grid settings for the current simulation model and to open the dialog Edit Grid and

Base Plate Settings , click Settings on the View ribbon tab.

<!-- image -->

To change the grid settings for new models, select File &gt; Preferences &gt; 3D .

- When you open the 3D window , the grid in the scene window for a model that you initially created in 2D only and for which you then activated 3D, looks like this in the scene. The origin of the grid, i. e. the lines, which by default are red, are always part of the grid. In the figure below the origin of the grid is designated by the red lines at the top left border of the scene window.
- For a 3D only model the grid in the scene window looks like this. The origin of the grid is located in the top left corner of the 3D window offset by one grid unit to the right and down each.

<!-- image -->

<!-- image -->

<!-- image -->

3D re-creates the grid after each change you make in the model when it redraws the scene.

So, when you insert and move an object toward the borders of the grid, it automatically extends in that direction. The grid always expands or shrinks to show all objects in the scene.

As the grid is intended to be a modeling help when creating the model, you will usually hide it when presenting your model. To do so, press the Ins key on the keyboard.

Plant Simulation adjusts the dimensions and the borders of the grid to the position of the objects shown in the scene.

<!-- image -->

The origin of the grid, i. e., the lines that are red by default, always are part of the grid.

The grid size always is a multiple of the smallest visible grid distance.

**You can:**

- Show and Hide the Grid
- Set Grid Properties

- Edit Grid Lines
- Position the Grid on Different Planes
- Move the Grid in the Scene

After you inserted objects into your simulation model, you can align them to the grid

them snap to the grid

, make them snap to other objects

<!-- image -->

<!-- image -->

To be able to do so, make sure that Show Grid is on.

Back to Visualizing the Material Flow in 3D

#### Show and Hide the Grid

To show or hide the grid, do one of the following:

<!-- image -->

- Click Show Grid on the View Ribbon Tab .
- Press the Ins key on your keyboard.

Compare Insert Objects into the Scene

Compare Simultaneously Paste Multiple Copies

Back to Work with the Grid

#### Set Grid Properties

To set the properties of the grid to meet your modeling needs, click Edit Grid and Base Plate Settings

<!-- image -->

on the View ribbon tab.

- To assign a material to the base plate below the grid lines in the Frame , click the color box. Then select individual components of the material in the dialog Material on the Tab Material .
- To assign a color to the coordinate axes, consisting of the x-axis and the y-axis, click the arrow in of the drop-down list Axes color and select a color.

<!-- image -->

<!-- image -->

<!-- image -->

, make

, or arrange them on the grid .

#### Edit Grid Lines

- To define the settings of the grid lines, edit them in the table on the tab.

<!-- image -->

Back to Work with the Grid

**Edit Grid Lines**

You can edit existing grid lines or add new grid lines in the group box Grid Lines [3D] .

- To add another grid line, click Add .

Enter the distance between two grid lines, which you want to add; we entered 2 meters. Select a color for the grid line, we selected a bright blue .

<!-- image -->

- To show this grid line in the grid in the scene, select Visible .
- Then, select if objects you insert snap to this grid line . Making objects snap to grid points enables you to precisely place objects with the mouse.
- To edit an existing grid line, select it in the list and edit the distance between the grid lines, their color , what objects, which you insert, snap to , and if this grid line is visible or not.

Back to Work with the Grid

#### Position the Grid on Different Planes

You can display the grid on the different planes in three-dimensional space. As you remember 3D uses a left-handed coordinate system:

The x-axis runs from left-to-right , the z-axis runs from bottom-to-top , and the y-axis runs from front-toback .

<!-- image -->

- To place the grid on the planes defined by the axes, click Transform on the View ribbon tab and select the respective radio button in the dialog Grid Position and Orientation .

<!-- image -->

<!-- image -->

**Note**

3D does not save the settings you select in this dialog. They only apply as long as the dialog is open.

To position the grid on the plane defined by the xaxis and the y-axis, select Orientation &gt; XY Plane .

To position the grid on the plane defined by the xaxis and the z-axis, select Orientation &gt; XZ Plane .

To position the grid on the plane defined by the yaxis and the z-axis, select Orientation &gt; YZ Plane .

Back to Work with the Grid

Move the Grid in the Scene To move the origin of the grid, click Transform on the View ribbon tab and roll the mouse wheel in the text boxes and click the buttons below Position in the dialog Grid Position and Orientation .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

**Note**

3D does not save the settings you select in this dialog. They only apply as long as the dialog is open.

<!-- image -->

**Note**

When moving the origin of the grid, Plant Simulation uses the length unit you selected under Model Settings &gt; Units &gt; Length .

- To move the position of the Origin of the grid on the x-axis by
- 0.01 length units to the right , click in the text box, hold down Ctrl , and roll the mouse wheel forward.
- 0.1 length units to the right , click in the text box and roll the mouse wheel forward.
- 1 length unit to the right , click in the text box, hold down Shift , and roll the mouse wheel forward.
- 0.01 length units to the left , click in the text box, hold down Ctrl , and roll the mouse wheel backward.
- 0.1 length units to the left , click in the text box and roll the mouse wheel backward.
- 1 length unit to the left , click in the text box, hold down Shift , and roll the mouse wheel backward.
- To move the position of the Origin of the grid on the y-axis by
- 0.01 length units to the back , click in the text box, hold down Ctrl , and roll the mouse wheel forward.
- 0.1 length units to the back , click in the text box and roll the mouse wheel forward.
- 1 length unit to the back , click in the text box, hold down Shift , and roll the mouse wheel forward.
- 0.01 length units to the front , click in the text box, hold down Ctrl , and roll the mouse wheel backward.
- 0.1 length units to the front , click in the text box and roll the mouse wheel backward.

#### Move the Grid in the Scene

- 1 length unit to the front , click in the text box, hold down Shift , and roll the mouse wheel backward.
- To move the position of the Origin of the grid on the z-axis by
- 0.01 length units up , click in the text box, hold down Ctrl , and roll the mouse wheel forward.
- 0.1 length units to the up , click in the text box and roll the mouse wheel forward.
- 1 length unit to the up , click in the text box, hold down Shift , and roll the mouse wheel forward.
- 0.01 length units to the down , click in the text box, hold down Ctrl , and roll the mouse wheel backward.
- 0.1 length units to the down , click in the text box and roll the mouse wheel backward.
- 1 length unit to the down , click in the text box, hold down Shift , and roll the mouse wheel backward.
- To reset the values for the x-axis, the y-axis and the z-axis to their predefined default values of 0, 0, 0, click Scene Origin .
- To set the values for the x-axis, the y-axis and the z-axis to the values of the position of a single object you selected, click Object Origin .

<!-- image -->

Back to Work with the Grid

<!-- image -->

