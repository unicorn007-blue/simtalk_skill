### Model a Complex Receiving Department

This sample model demonstrates how to model a complex receiving department in a Frame . Here three Sources produce three different parts , namely bricks , glass bricks , and brick carriers . The bricks and the glass bricks are then loaded onto brick carriers and moved to a ParallelStation that stores them before a TransferStation loads them onto a truck that is produced by a fourth Source .

We will demonstrate how to:

- Insert the Objects Required for Modeling the Source
- Configure the Individual Stations
- Animate Bricks on the Animation Area of the Brick Carrier
- Animate Brick Carriers on the Animation Area of the Truck
- Show the Content of the Frame

Back to Visualizing the Material Flow in 3D

Insert the Objects Required for Modeling the Source First, we will insert the objects, which we need to model our receiving department, into a Frame . In the second step, we are going to configure the individual objects.

- Create a new Frame in the Class Library of your simulation model. We named our Frame MySourceTruckLoadedWithBricks .
- Insert three Sources at the left-hand side of the Frame . We use our own class, named MySource , with a modified 3D graphic. We named our Sources SourceGlassBricks , SourceBricksCarrier , and SourceBricks . They will produce glass bricks, brick carriers, and normal bricks.
- Insert two AssemblyStations to the right of the Sources . We named them AssemblyGlassBricks and AssemblyBricks . Each of them places 50 glass bricks or 50 normal bricks onto a pallet each.
- Insert a TransferStation , a short Track , and another Source . This Source , which we named SourceTrucks , produces the trucks onto which the commissioned pallets are loaded.
- Insert an Interface that connects our receiving department with the other objects in the simulation model.
- Connect the objects so that they match the screenshot below. Our finished model looks like this:

<!-- image -->

**Note**

As the AssemblyStation is connected to two stations, the order in which you connect it with the predecessors is important. If the assembly process does not work as expected, check the numbering

of the predecessors by activating More View Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D model.

3D shows the predecessors and the successors of an object in a tooltip when you drag the mouse over the respective Connector .

Then, enter the correct number of the predecessor into the text box Main MU from predecessor of the AssemblyStation .

Back to Model a Complex Receiving Department

<!-- image -->

#### Configure the Individual Stations

Now that we have inserted the objects we need to model our receiving department, we are going to configure the individual stations.

First, we are going to configure the MUs :

- To create the MU representing the truck , duplicate the class .MUs.Transporter and rename it to Truck . We deleted its graphic and imported the JT file Truck.jt , which we received from a colleague. Position the graphic in its 3D window as shown below. We changed its size to 6.3 by 2.2 by 1.6 meters.

<!-- image -->

<!-- image -->

- To create the MU representing the brick carrier , duplicate the class .MUs.Container and rename it to BricksCarrier . We deleted its graphic and imported the JT file BricksCarrier.jt . We changed its size to 1.1 by 1.1 by 0.15 meters and gave it a capacity of 50 parts ( X-Dimension of 5 times Y-Dimension of 10 ).
- To create the MU representing the normal brick and the glass brick , duplicate the class .MUs.Part twice. We renamed them to Brick and GlassBrick respectively. Both have a size of 0.2 by 0.1 by 0.05 meters.

<!-- image -->

<!-- image -->

For the bricks we are going to use automatically generated graphics instead of importing JT files.

- Open their class in a new 3D window and open the dialog Edit 3D Properties .
- Change to the Tab Transformation and activate the check box Scale Automatically .
- For the GlassBrick , also activate Material Active , select a blueish gray as the Diffuse Color , and select a Transparency factor of 0.6 to make the glass brick semi-transparent.
- Activate Material Active for the GlassBrick . Select orange as the Diffuse Color The automatically created graphics look like this:

<!-- image -->

<!-- image -->

Then, we are going to configure the other objects in our Receiving department .

- Start with the Sources producing the Brick , the GlassBrick , and the BricksCarrier . Select the respective MU according to the name of the Source . We did not change any other settings. Compare the example below.

<!-- image -->

**Note**

Make sure that you use the absolute path for the MUs , denoted by an asterisk * at the beginning of the path. The relative path starts with a tilde ~.

- Configure the AssemblyStations to attach the MUs and to make the Main MU exit the station. We also want them to load 50 parts, namely the bricks or glass bricks , onto the brick carrier . Click Open next to Assembly table and enter 50 into the column Number .

<!-- image -->

**Note**

As the AssemblyStation is connected to two stations, the order in which you connect it with the predecessors is important. If the assembly process does not work as expected, check the numbering

of the predecessors by activating More View Options &gt; Show Predecessors on the View ribbon tab of the Frame in a 2D model.

3D shows the predecessors and the successors of an object in a tooltip when you drag the mouse over the respective Connector .

Then, enter the correct the number of the predecessor into the text box Main MU from predecessor of the AssemblyStation .

<!-- image -->

- Drag the ParallelStation onto the TransferStation to load parts and to use it as the Part Source . We use the default settings of the ParallelStation .

Drag the Track onto the TransferStation to use it as the Target Station . Accept 0 is the Sensor Position .

<!-- image -->

To make the Truck stop and wait for parts until it is fully loaded, select the check box Always Stop Container on the tab Advanced Attributes .

<!-- image -->

- Open the dialog Edit 3D Properties of the Frame MySourceTruckLoadedWithBricks . Change to the tab Graphics and make sure that Show content is cleared.

Now we are ready to test our receiving station MySourceTruckLoadedWithBricks . Insert it into our simulation model, connect it with a Track and a Drain , and run the simulation. You'll notice that it creates trucks that transport two types of carriers , one loaded with normal bricks and one loaded with glass bricks each.

<!-- image -->

Back to Model a Complex Receiving Department

Animate Bricks on the Animation Area of the Brick Carrier When 3D places objects onto other objects, in our example bricks and glass bricks on the brick carrier , it automatically distributes them evenly across the animation area of the brick carrier according to their size and to the size and dimension of the brick carrier .

<!-- image -->

In our example the brick carrier can accommodate 50 bricks , each of which is 20 centimeters long and 10 centimeters wide. The brick carrier is 110 centimeters long and wide. According to its x-dimension 5 bricks fit in a row side by side in the x-direction. According to its y-dimension 10 bricks fit in a row in the y-direction.

<!-- image -->

We used the default settings of the brick carrier / container .

**Back to Model a Complex Receiving Department**

#### Animate Brick Carriers on the Animation Area of the Truck

When 3D places objects onto other objects, in our case brick carriers onto the loading space, i.e., the animation area of the truck, we would like to determine where on the bed it places the brick carriers .

We defined animation areas for the objects with matrix loading space ParallelStation , Sorter , Store , Transporter , and Container . These should cover your basic modeling needs.

In our case we changed the graphic of the truck, which we derived from the Transporter . We thus have to change the animation area settings.

<!-- image -->

**Proceed as follows:**

- Change to the Class Library and click MUs &gt; Truck with the right mouse button.
- Click Open In 3D .
- Click the right mouse button in the window .MUs.Truck and select Edit 3D Properties &gt; MU Animation .
- You can now adjust the area settings under animation area so that the brick carriers are evenly distributed across the loading space of the truck. 3D computes the animation area of the object as soon as you click Apply in the dialog Edit 3D Properties . The window of our partial model then also shows these changes.

<!-- image -->

- We selected the settings above. Now everything is correct.

<!-- image -->

We can also replace the simple graphic of the truck with the graphic of the new version of Plant Simulation . To do so:

- Duplicate the Transporter , rename it to TruckDumper , and exchange its graphic .

<!-- image -->

- Enter the dumper as the MU to be created into the SourceTruck .
- Now only 6 brick carriers are loaded instead of the intended 8.

<!-- image -->

<!-- image -->

To fix this, increase the X-Dimension of the loading space from 3 to 4 .

<!-- image -->

- We finally adjust the animation area settings of the bed.
- Open the TruckDumper in a new 3D window, click in the background, and press the spacebar .
- Activate the animation area on the tab MU Animation and Show it.

<!-- image -->

- Click in the text boxes and roll the mouse wheel until the animation area has the correct size.

<!-- image -->

Back to Model a Complex Receiving Department

#### Show the Content of the Frame

We can also show the content of the Frame named MySourceTruckLoadedWithBricks in the Frame named MyPlant instead of the icon of the Frame :

- Select the Frame named MySourceTruckLoadedWithBricks . Press the spacebar .
- Select Show Content . This then looks like this:

<!-- image -->

<!-- image -->

- Adjust the content of the Frame named MySourceTruckLoadedWithBricks :
- Clear the check box Visible for the graphic group named default , so that the default graphic of the Frame is not shown over the content of the Frame .

<!-- image -->

- Delete the Interface of type Exit . We do not need it as our sub-Frame only contains a single material flow object that will be connected externally. Connect the sub-Frame with the Track .
- We finally adjust the positions of the objects and run the simulation:

<!-- image -->

Back to Model a Complex Receiving Department

