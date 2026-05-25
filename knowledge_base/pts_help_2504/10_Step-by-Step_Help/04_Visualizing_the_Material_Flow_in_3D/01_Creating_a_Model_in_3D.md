### Creating a Model in 3D

Select the Visualization describes different visualizations that Plant Simulation offers. If a visually pleasing model is important to you, you will always create a 3D model.

To create a model in 3D , you will basically proceed as follows:

- To create a new Plant Simulation model, click Create New Model on the Start Page or select File &gt; New .

Select if you want to create a 2D model or a 3D model.

<!-- image -->

<!-- image -->

You can also set to create new models in 3D under Preferences &gt; General &gt; Visualization .

<!-- image -->

Plant Simulation then shows the 3D Frame named Model that by default only contains the EventController .

- To show the built-in simulation objects and their graphics, you can, for example, click the folder MaterialFlow in the Class Library with the right mouse button and select Open in 3D . This way you can also show the contents of the other folders.

To show the name of an object, drag the mouse over it.

To rotate the scene, hold down the left and the right mouse buttons and drag the mouse or hold down Ctrl and the right mouse button and drag the mouse. The rotate mouse pointer looks like this .

To pan the scene, hold down the right mouse button and drag the mouse. The pan mouse pointer looks like this .

To move the camera forward and backward, roll the mouse wheel.

To zoom the scene in or out, roll the mouse wheel or hold down Shift and the right mouse button and drag the mouse.

**Note**

If you have a three-button mouse, click the middle mouse button where the description calls for clicking the mouse wheel.

**Note**

If manipulating the scene with the mouse does not work, check the Mouse Properties for the Wheel in the Mouse Control Panel under Start &gt; Control Panel .

**Creating a Model in 3D**

- To open a new 3D window, change to the Class Library . Then, click the corresponding folder with the right mouse button and select Open in 3D .
- To insert an object into the 3D window:
- Make sure that Show Grid on the View ribbon tab is active, compare Show and Hide the Grid . We recommend to show the grid before you insert an object into the scene window. This way you can place the object at the exact position, where you want it to be.

<!-- image -->

If you insert an object without displaying the grid, you have little control over where Plant Simulation actually places the object. By default, it uses the same coordinates that the source object had, an effect you might not want.

- Select the object you want to insert in the Toolbox . Drag the mouse pointer to the position of your choice and click the left mouse button to insert it there.

As long as an object is selected in the Toolbox , Plant Simulation shows a preview of the object in the 3D window to make it easier for you to position it.

To cancel inserting objects, click the right mouse button.

- Insert a Source , a Conveyor , a Station and a Drain .
- Connect the inserted simulation objects:
- Make sure that Show Connections on the View ribbon tab is activated as 3D does not show the Connectors by default.
- Click the Connector in the Toolbox on the tab MaterialFlow .
- Click the source object, where the connection will start, once with the left mouse button. Plant Simulation attaches a line symbolizing the Connector to the mouse pointer.

<!-- image -->

<!-- image -->

- Drag the mouse to the destination object at which the connection will end, and click once with the left mouse button to establish the connection.

3D shows the Connector it inserted as a line between the connected internal interfaces of the source and destination objects. The pointed cone shows the direction of the Connector .

- To terminate connect mode before you click the destination object, click the right mouse button or press Esc .

To connect several objects one after the other, without interrupting the connecting process, hold down Ctrl .

- ◊ Attach the outgoing connection to the first object.
- ◊ Drag the mouse to the succeeding object.
- ◊ Click the left mouse button to attach the incoming Connector to the successor.
- ◊ You can also connect the objects in the 2D part of your model, which will simultaneously insert the connections into the 3D part, if you opened 3D .

Connect the Source , the Conveyor , the Station and the Drain you inserted above.

<!-- image -->

- Start the simulation:
- ◊ Control the simulation by clicking the buttons on the Home ribbon tab or
- ◊ Double-click the icon of the EventController and click its buttons.
- ◊ Watch how the produced parts move across the simulation objects.

**Modeling Hierarchically [in 3D]**

<!-- image -->

Compare Work with Objects in 3D

Compare Work with the Grid

Compare Control Your View

Compare Work with the Scene

Back to Visualizing the Material Flow in 3D

