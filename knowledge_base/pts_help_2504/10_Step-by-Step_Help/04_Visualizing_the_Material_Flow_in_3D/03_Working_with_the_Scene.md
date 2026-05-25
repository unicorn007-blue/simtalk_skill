### Working with the Scene

#### Work with the Scene

3D provides a number of ways for working with the active scene, as opposed to working with the objects you insert into that scene.

**You can:**

- Manipulate the Scene with the Mouse
- Align the View to the Main Directions
- Save a View with the Model and Return to It
- Fly on a Defined Path Through the Scene
- Map 2D Coordinates to 3D Coordinates in the Scene
- Show information about the open scene by pressing the F key on the keyboard. To hide the information, press the F key again. The scene window shows:
- The Frames per Second (FPS).
- The summed up Number of Nodes of the scene window.
- The summed up Number of Polygons of the scene window.
- The summed up Memory usage of the scene window.
- The OpenGL Version used.
- Information about the Display Driver of your computer.

<!-- image -->

Compare Graphic Complexity of a graphic

Compare Work with Objects in 3D

Compare Control Your View

Compare Work with the Grid

Back to Visualizing the Material Flow in 3D

#### Manipulate the Scene with the Mouse

You can manipulate the scene itself and the objects within that scene with the mouse. You can move within the scene and change your view of the scene.

Instead of using a normal mouse, you can also navigate in the scene with a Space Navigator mouse.

**Note**

If you have a three-button mouse, click the middle mouse button where the description calls for clicking the mouse wheel.

If manipulating the scene with the mouse does not work, check the Mouse Properties for the Wheel in the Mouse Control Panel under Start &gt; Control Panel .

- To rotate the scene , hold down the left and the right mouse buttons and drag the mouse, or hold down Ctrl and the right mouse button and drag the mouse.

<!-- image -->

| Mouse pointer, rotate around center of the scene   | Mouse pointer, rotate around object   |
|----------------------------------------------------|---------------------------------------|

<!-- image -->

When you start rotating a view with the mouse and remain at the position for at least 400ms and if an object or a graphic is located under the mouse pointer, Plant Simulation rotates around the position under the mouse pointer on the object or the graphic.

In all other cases Plant Simulation rotates around the projection of the center of the window on the insertion plane, or around a matching orthogonal of this plane if the view is rotated by 90°. Here it does not matter where the mouse pointer is positioned.

<!-- image -->

- To pan the scene , hold down the right mouse button and drag the mouse. The pan mouse pointer looks like this . If you have a three-button mouse, you can also hold down the middle mouse key and drag the mouse.
- To move the camera forward and backward, roll the mouse wheel, or hold down Shift and the right mouse button and drag the mouse.
- To move the scene with a tenth of the speed , hold down Ctrl and roll the mouse wheel.
- To move the scene with ten times the speed , hold down Shift and roll the mouse wheel.

In Planning View you can navigate like this:

- To move the scene on the plane , hold down the right mouse button and drag the mouse.
- To zoom the scene , roll the mouse wheel, or hold down Shift and the right mouse button and drag the mouse.
- To zoom the scene with a tenth of the speed , hold down Ctrl and roll the mouse wheel.

To zoom the scene with ten times the speed , hold down Shift and roll the mouse wheel.

Compare Mouse Wheel Behavior

Compare Move an Object With the Mouse

Back to Work with the Scene

#### Align the View to the Main Directions

You can select from which predefined direction you look at the scene using the commands on the View ribbon tab:

From the Right , from the Left , from the Back , from the Front , from the Top , or from the Bottom .

<!-- image -->

- To view the entire scene from the top looking down, click on the View ribbon tab.
- To view the entire scene from the front , click
- To view the entire scene from the left side , click

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

.

<!-- image -->

<!-- image -->

- To view the entire scene from the bottom , click . This shows the entire scene from the bottom
- looking upward, i. e., along the negative z-axis.

If Show Grid is activated, Plant Simulation shows the grid below the object that you want to see from below.

If Show Base Plate is activated, Plant Simulation shows the base plate below the object that you want to see from below. The base plate then hides the object as such.

If you selected anything in the scene, the command adjusts the scene so that the selection is visible instead of the entire scene.

<!-- image -->

- To fit the entire scene into the scene window and to show all objects in the scene if you moved part of the scene out of view, click View All .

<!-- image -->

Back to Work with the Scene

#### Save a View with the Model and Return to It

To save the current position and orientation of the camera with the model file, click Camera Marks on the View ribbon tab in 3D.

<!-- image -->

<!-- image -->

- Enter a Name for the current camera setting into the dialog Mark Current Camera Settings .
- 3D shows the path of the scene in the field Scene path .
- Click OK to set the name. This saves this setting together with the active root object of the scene in the model file. Then, you can easily return to this saved view after you changed the scene or after you reopened the model.

<!-- image -->

To return to a view you saved later on, or to navigate to the different predefined folders:

- Click the down arrow on the Camera Marks button. Select the camera mark, i.e., the view for which you defined it, on the list.

<!-- image -->

Or

- Select the command Camera Marks .
- Select one of the saved scenes in the list and click Activate .

<!-- image -->

To rename or delete a camera mark, select it in the list, and click Rename or Delete .

<!-- image -->

.

<!-- image -->

To move the selected camera mark up in the list, click

To move the selected camera mark down in the list, click

Compare these examples:

- The total view of our model looks like this:

<!-- image -->

.

- The cafeteria of our model looks like this:

Back to Work with the Scene

<!-- image -->

#### Map 2D Coordinates to 3D Coordinates in the Scene

When you insert objects into your 3D scene, you will notice that 2D places them at roughly equal positions in the respective 2D Frame in a 2D and 3D model , and vice versa.

To accomplish this, Plant Simulation 2D converts the pixel-based coordinates of the 2D Frame into 3D coordinates, where, depending on the scaling factor, the unit 1 might correspond to 1 meter. In addition, it flips the y-axis, so that it points up.

<!-- image -->

To edit how Plant Simulation 2D maps 3D coordinates:

- Navigate to the 2D Frame that contains your model.
- Click Scaling Factor on the View ribbon tab.

**Enter the Scaling Factor .**

<!-- image -->

The Horizontal Grid Spacing shows the distance between two grid points on the x-axis using the Scaling Factor you entered.

The Vertical Grid Spacing shows the distance between two grid points on the y-axis.

The default settings Frame Grid Spacing 20 x 20 pixels, Length units m (meters) and a Scaling Factor of 0.05 result in a horizontal and vertical grid spacing of 1 meter each.

When you change the scaling factor, Plant Simulation shows the new horizontal and vertical grid spacing in the dialog.

The settings Frame Grid Spacing 20 x 20 pixels, Length unit m (meters) and a Scaling Factor of 0.5 result in a horizontal and vertical grid spacing of 10 meters each.

Back to Work with the Scene

#### Set the Background Color of the Scene

To set the Background Color of the selected Frame or the selected folder in the Class Library in the 3D window:

- Click Edit 3D Properties on the Home ribbon tab or click into the Frame window with the right mouse button and select Edit 3D Properties . Then, click the Tab Background .

**Note**

You can also open the dialog Edit 3D Properties for the selected object by clicking the spacebar .

- Select Assign a Background Color of Its Own . Once you select the check box, 3D activates the other settings on the tab.
- Select the Base Color . This is the base color of the background which you can change with the corner brightness settings.

You can select one of the predefined colors or you can click More Colors and click the Select button to select a color in the color matrix. Then click OK . Plant Simulation show this color next to More Colors and uses it as the active color.

- Select settings for the Corner Brightness of the four corners of the Frame window. The top left slider sets the settings of the top left corner of the Frame window, etc. Drag the sliders to make the respective corner darker or brighter. This way you can define a color gradient, i.e., the brightness of the background color.

<!-- image -->

**Note**

If you do not define a background color, 3D uses the background color of the parent object of the selected object.

Back to Work with the Scene

#### Flying on a Defined Path Through the Scene

Fly on a Defined Path Through the Scene

To view the scene through the lens of an object, you can attach a camera to it. This camera then moves along with the object through the scene during a simulation run. By turning or tilting the camera, you can control the direction and the angle at which you look at the scene.

3D visualizes the camera with a tool object as the icon of the camera. At present 3D provides three different cameras:

- The main camera through which you view the scene in normal view.
- The object camera , which you attach to a specific object and which moves with this object through the model. You might, for example, attach a camera to a part or a Worker to follow it or him on their way through the factory.
- The animation camera , which moves along an animation path you defined.

Proceed as follows to define a tracking shot through the scene:

- Click an object with the left mouse button to select it.
- Click Animate Camera on the View ribbon tab to open the dialog Fly on Path . If you did not select an object before, the dialog refers to the current root object of the scene.
- Select one of the camera paths you defined to move your view point along this path.

<!-- image -->

You can also define your own camera paths or edit any existing path in the dialog Edit 3D Properties &gt; Tab Camera Animation of the Frame to meet you specific modeling needs. Compare How 3D Animates the Camera in the Frame .

You can:

- Attach a Camera to an Object
- Detach the Camera from an Object
- Animate the Object Camera

Compare Ballhaus Kreisel

Compare Work with Animation Paths

Compare Tab Camera Animation &gt; How 3D Animates the Camera in the Frame

Back to Work with the Scene

Attach a Camera to an Object

To attach a camera, through the lens of which you look at the scene, to an object, proceed as follows:

- Select a single object.
- Click Attach Camera on the View ribbon tab of the 3D window .
- Plant Simulation attaches the camera at a defined position:

<!-- image -->

Plant Simulation uses the center of the top of the bounding box of the selected object as the position where it inserts the camera. Plant Simulation adds an offset of 0,0,0.1 to these makeshift points, so that your eyes will be located above the top plane.

By default the object camera looks along the positive x-axis using the positive z-axis as Up direction .

You might, for example, attach a camera to one of the boxes in our sample model Factory51 and track its way through the factory.

<!-- image -->

As soon as the object, with a camera attached to it, moves through the scene, the camera moves along with it automatically. Once the camera is attached, you see the scene through the lens of this object camera.

<!-- image -->

Or you can attach a camera to one of the Workers and track his way between the work stations.

<!-- image -->

You then see what the Worker sees while he walks and what he sees while he stands on the Workplaces and works at the machines.

<!-- image -->

Compare How 3D Animates the Camera in the Frame

Compare Move an Object Precisely

Compare Work with Animation Paths

Back to Fly on a Defined Path Through the Scene

Detach the Camera from an Object

To detach the camera, which you attached to an object, from it, click Detach Camera on the View ribbon tab of the 3D window . Plant Simulation then returns to normal view.

Plant Simulation also detaches an object camera:

- When you delete the object to which the camera is attached.
- When you change the scene.

Back to Fly on a Defined Path Through the Scene

Animate the Object Camera You can animate the camera on a camera animation path of the selected Frame , thus creating the impression of flying through the scene.

<!-- image -->

<!-- image -->

To move the animation camera:

- Change to the View ribbon tab and click Animate .
- Select the name of the animation path for the selected object in the dialog Fly on Path or for the root object of the scene from the list Path Name [MU animation] .
- Select Backwards if you want the camera to move backward toward the starting point of the animation path. Plant Simulation automatically enters a negative velocity into the text box when you select the check box.
- To start the animation, click Play . 3D now shows the scene through the lens of the animation camera, which moves on the path you
- designated with a lens offset of (0, 0, 0.1).

<!-- image -->

<!-- image -->

- To pause the animation of the camera, independent of the simulation, click Pause

.

<!-- image -->

- To stop the animation of the camera, independent of the simulation, click Stop

.

<!-- image -->

At the end of the animation 3D sets the main camera to the last point where the animation camera was located and deletes the animation camera.

To test the camera animation path you defined, click the tab Test in the dialog Edit Path , select an Animated graphic , and start the test animation.

Compare Work with Animation Paths

Back to Fly on a Defined Path Through the Scene

