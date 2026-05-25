### Create a Simulation Object with Animation

While you are creating your simulation model, you will also model simulation objects which animate a certain work process in 3D .

In our example we model our own station in a Frame . We will demonstrate how to:

- Create the Simulation Object
- Add Animations and Interactions to the Simulation Objects
- Test the Station in the Simulation Model
- Fine-tune the Station

Back to Visualizing the Material Flow in 3D

#### Create the Simulation Object

To create the simulation object that is required for our animatable object:

- Create a new Frame and open it in 3D . Open the dialog Edit 3D Properties . Change to the tab Graphics . Select the check box Show Content to show the objects contained within it.
- Click Show External Graphic Groups on the View ribbon tab to show the default graphic of the Frame . Delete the graphic named default .
- Click Import Graphics on the Edit ribbon tab to import an appropriate JT file into the graphic of the Frame . Our file is called Screwdriver.jt . We received it from a colleague.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

- Extract the first simulation object: Click the floor plate of the station by pressing the + key on your keyboard until only the floor plate, and nothing else, is marked as selected. 3D then shows the floor plate in a yellowish green.
- Click the graphic with the right mouse button and select Make Simulation Object .

<!-- image -->

- Select .MaterialFlow.Station as the class . Name the object PartCarrierStation and change the coordinates of the Object Position until they are located in the center of the screwdriver. Watch how the white cross lines change their position in the scene window as you change the position of the object in the dialog.
- Select the trestle that holds the actual screwdriver of our screwdriver station. Notice that when you select PartCarrierStation , 3D show it in a darker green while it shows the other graphics in a light yellowish green. Dark green denotes that an object is selected . Yellowish green denotes that a graphic is selected , meaning that you can use the + key to contract the selection along the graphic structure.

<!-- image -->

<!-- image -->

Create a second simulation object. Select .MaterialFlow.Station as the class . Name the object Trestle and change the coordinates of the Object Position until they are located in the center of the screwdriver.

<!-- image -->

Back to Create a Simulation Object with Animation

<!-- image -->

#### Add Animations and Interactions to the Simulation Objects

After creating the basic simulation part of our Screwdriver station, we are going to add the animation part and the interaction part to it.

- Click the trestle of the screwdriver with the right mouse button and select Open in New 3D Window . This opens the Frame .Models.MyScrewdriver.Trestle . Press the + key until only the graphic of the screw arm proper is selected, denoted by the lighter green.
- Click the graphic with the right mouse button and select the command Make Animatable Object . Name the object Arm and select the following coordinates as the Object Position until they are located in the center of the screw arm.
- Click the newly created animatable object with the right mouse button and select Use as Animation Object . This means that our trestle forwards the animation of the MUs to the animatable object named Arm .

<!-- image -->

<!-- image -->

<!-- image -->

Close the Frame .Models.MyScrewdriver.Trestle to return to the Frame .Models.MyScrewdriver .

Click the Trestle with the right mouse button, select Edit 3D Properties , and change to the Tab MU Animation . You'll notice that the command above entered the animation object Arm as the Animation object . Instead of using the command Use as Animation Object , you could also type the name of the animation object into the text box.

<!-- image -->

- Open the Trestle in a new 3D window. Click the Arm with the right mouse button and change to the Tab Self Animation .
- Add four animation paths of type Lines . We named our paths Setup , DownAdvance , Reset , and DownFinal .
- Select the respective path and click Edit to define two anchor points for each path. Click Add in the dialog Path Anchor Points , then select the new anchor point, and click Edit Values . Enter these values into the dialog that opens:
- 0 , 0 , 0 to 0 , 0 , 0.9 for Setup .
- 0 , 0 , 0.9 to 0 , 0 , - 0.1 for DownAdvance .
- 0 , 0 , -0.1 to 0 , 0 , -0.22 for DownFinal .
- 0 , 0 , -0.22 to 0 , 0 , 0 for Reset .

<!-- image -->

With these settings, the animation paths of the arm resemble components of a continuous smooth up and down movement of the arm.

<!-- image -->

- Change to the Tab MU Animation , add a new path, name it Default , and add a single animation point with the settings 0 , 0 , -0.38 .
- Finally, we are going to configure the simulation side of the stations, i. e. the stations we created as simulation objects above.

To do so:

- Double-click the PartCarrierStation and configure it. We entered a processing time of 10 seconds ( 0:10 ).

<!-- image -->

We also created the exit control called self.OnExit and entered this source code:

```simtalk
if ?.ExitCtrlFront self.~.~.Trestle.EntranceLocked := false
	@.move
end
```

In addition we added a user-defined attribute of data type method , named it init , and entered this source code:

```simtalk
self.~.EntranceLocked := true
```

- Double-click the Trestle and configure it. We entered a set-up time of 6 seconds ( 0:06 ) and selected these settings on the tab Set-Up .

<!-- image -->

- We also created the Entrance Control called self.OnEntrance , the exit control named self.OnExit , and the setup control called self.OnSetup .

We entered this source code into the Entrance Control :

```simtalk
var animations : any := self.~._3D.getObject("Arm").SelfAnimations
animations.resetAnimation
animations.DownAdvance.schedule
animations.startNextAnimationBlock
animations.DownFinal.schedule
animations.scheduleRotation(0, 360, 90)
@.outIn(animations.AnimationTimeTotal)
animations.playAnimation
```

We entered this source code into the Exit Control :

```simtalk
if ?.ExitCtrlFront
	@.deleteObject
	var animations : any := self.~._3D.getObject("Arm").SelfAnimations
	animations.resetAnimation
	animations.Reset.schedule
	animations.playAnimation self.~.EntranceLocked := true
end
```

We entered this source code into the Setup Control :

```simtalk
param setupStart: boolean
if setupStart
	var animations : any := self.~._3D.getObject("Arm").SelfAnimations
	animations.resetAnimation
```

**Test the Station in the Simulation Model**

```simtalk
animations.Setup.schedule
animations.playAnimation
else self.~.~.PartCarrierStation.EntranceLocked := false
end
```

In addition we added a user-defined attribute of data type method , named it init , and entered this source code:

```simtalk
self.~.EntranceLocked := false
```

Back to Create a Simulation Object with Animation

#### Test the Station in the Simulation Model

Now we are ready to test our screwdriver station in the simulation model.

- Insert a Source , which produces the pallets which we want to screw together. We named it SourcePallets .

Insert a second Source , which feeds the screws required for screwing together the pallets. We named it SourceScrews . We received the screw, including the JT file, from a colleague.

- Insert a Drain , which removes the finished pallets from the plant.
- Insert our Screwdriver station.
- Insert three Conveyors between the Sources , the Drain , and the Screwdriver station.
- Connect all objects with Connectors . Connect the SourcePallets , that produces the MU &gt; PartsCarrier , with the ConveyorPallets , and with the InterfaceInPallet of the Screwdriver . Connect the SourceScrews that produces the MU &gt; Screw , with the ConveyorScrews , and with the Interface named InScrew . Connect the ConveyorOut with the Interface named Out and then with the Drain . The simulation model should now look like this:

<!-- image -->

You might be wondering how we inserted the Conveyors with an inclination to smoothly connect to the Screwdriver station. We proceeded as follows:

- For the ConveyorPallets we entered an Anchor Point Height of 1 meter for the first anchor point and an anchor point height of 0.15 meters for the second anchor point into the dialog Line/Arc Parameters . This is the height of the object SourcePallets to which we connect it on the left-hand side.
- For the ConveyorOut we edited values in the dialog Edit 3D Properties &gt; Appearance . We entered a Base Height of 0.15 meters, which means that the left-hand side of the ConveyorOut is placed 15 centimeters above the floor. We then clicked Segments and entered 1 meter as the Z dimension so that the right-hand side connects smoothly to the Drain .
- When you run the simulation, you might want to run it with a low real-time factor to be able to watch how the screwdriver actually screws the screws in.

<!-- image -->

**Back to Create a Simulation Object with Animation**

#### Fine-tune the Station

While running the simulation, you'll notice that the pallet is not located at the bottom of the Screwdriver station, but at the top. Proceed as follows to fix this:

- Open the class of the Screwdriver in a new 3D window.
- Then, open the dialog Edit 3D Properties of the PartCarrierStation , change to the tab MU Animation , and show the Default path.
- Select the path marker, i, e., the wedge pointing downwards, hold down the Ctrl key, and move it down with the down arrow key until it is located flush on the PartCarrierStation .

<!-- image -->

You'll also notice that the screw is not attached to the tip of the arm. Proceed as follows to fix this:

- Open the class of the Screwdriver in a new 3D window.
- Open the Trestle of the Screwdriver in a new 3D window.
- Open the dialog Edit 3D Properties of the Arm , change to the tab MU Animation , and visualize the Default path.
- Select the path marker, hold down the Ctrl key, and move it down with the down arrow key until it was located flush at the tip of the Arm .

<!-- image -->

You'll finally notice that the wrong side of the screw is attached to the tip of the Screwdriver arm. Proceed as follows to fix this:

- Open the class of the Screwdriver in a new 3D window.
- Open the Trestle of the Screwdriver in a new 3D window.
- Open the dialog Edit 3D Properties of the Trestle , change to the tab MU Animation , and visualize the Default path.
- Select Top as the side to which the MU is to be attached .

<!-- image -->

Run the simulation again. Now our Screwdriver station does exactly what we designed it to do.

<!-- image -->

Back to Create a Simulation Object with Animation

**Modeling a Complex Receiving Department**

