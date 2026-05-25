### Aligning and Shrink-Wrapping Parts with the Turnplate

#### Align and Shrink-Wrap Parts with the Turnplate

You can use the Turnplate to model a rotating platform, which rotates the loaded part and ensures the uniform orientation of the leaving parts. A typical example is parcel shipping where all parcels have to be rotated to a uniform direction so that a scanner can automatically read the bar-code holding the address information.

You can insert the Turnplate into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In our examples we will demonstrate how to:

- Align Parts with the Turnplate
- Model a Shrink Wrapper

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Modeling the Material Flow

#### Align Parts with the Turnplate

In this sample model the Source produces four parts of type MyPart and moves them onto the feeder line of the Turnplate . It in turn rotates each part by 90 degrees to the right and moves it on to its successor.

The finished simulation model looks like this:

<!-- image -->

To create our simulation model, proceed as follows:

- First, configure the Source . As we want it to produce four parts only, we selected Time of Creation &gt; Number Adjustable and entered 4 as the Amount . We then selected the part to be produced, namely MyPartColored , which we created in the folder UserObjects .

<!-- image -->

- Insert the Conveyor that feeds the parts to the Turnplate . You can make it as long as you like, you do not have to change any of the other settings though.
- Insert the Turnplate and the Conveyor that moves the parts on to the Drain .
- Configure the Turnplate . As we want it to rotate the part by an angle of 90 degrees, you can use the default setting, namely the Strategy &gt; Angle and a rotation Angle of 90 degrees.

<!-- image -->

- Start the simulation and watch how the Turnplate rotates the part. You will not be able to see anything with the default setting for the simulation speed , as the simulation runs too fast.
- To fix this, adjust the simulation time in the EventController .
- Start the simulation again and watch how the Turnplate rotates the part. You might want to further reduce the speed by dragging the slider in the EventController to the left.

Back to Align and Shrink-Wrap Parts with the Turnplate

<!-- image -->

#### Model a Shrink Wrapper

Model a Shrink Wrapper You can use the Turnplate to model a shrink wrapper. In our example we apply an overwrap around the parts on our pallet to stabilize the load.

In this sample model the SourceParts creates nine parts. It moves them onto Conveyor1 , which feeds them to the Turnplate . The Turnplate turns them by 90 degrees to the right. The successor line moves the parts onto the ParallelStation , which processes them for two minutes. It then moves them on to the TransferStation , which loads them onto a pallet. The ConveyorPallet moves the pallet back to the Turnplate , which shrink wraps it, and moves it on to shipping, i.e., to the Drain .

To create our simulation model, proceed as follows:

- Configure the Source and the Feeder Line
- Configure the Turnplate
- Configure the Conveyor Which Transfers the Parts
- Configure the Stations Which Handle the Pallet
- Adjust Shrinkwrapper and Parts in 3D

The finished simulation model looks like this in 2D:

Back to Align and Shrink-Wrap Parts with the Turnplate

<!-- image -->

##### Configure the Source and the Feeder Line

Insert and configure the Source . As we want it to produce nine parts only, we selected Time of creation &gt; Number Adjustable and entered 9 as the amount . We then selected the part MyPart , which we created in the folder UserObjects .

<!-- image -->

Next, insert the feeder line that moves the part on to the Turnplate . You can use the Conveyor with its default settings.

**Back to Model a Shrink Wrapper**

Configure the Turnplate

Insert the Turnplate and configure it. The Turnplate has two tasks in our example:

- It rotates the parts by 90 degrees to the right and then moves them on to Conveyor1 .
- It rotates the pallet after the parts have been stacked onto it to simulate the shrink wrapper.

To accomplish this, we have to use a method:

- Select the Strategy &gt; Method .

- Specify the name of the Strategy Method and program the actions it has to execute.

We decided to use a user-defined attribute of data type method . We right-clicked in the text box Strategy Method and selected Create Control . Plant Simulation then entered self.OnStrategy and opened the method.

<!-- image -->

We typed in the following source code, which first sets the rotation angle of the part itself and then of the pallet after the parts have been loaded onto it. The leading sign in the instruction -(4 * 360) designates the direction in which the Turnplate rotates; + stands for clockwise, -stands for counterclockwise. Our example rotates the pallet four times by 360 degrees counterclockwise.

```simtalk
var rotAngle: integer
if @.typeOf(.UserObjects.MyPart)           // rotates the part
	rotAngle := 90
else
	if @.typeOf(.UserObjects.MyPallet)      // rotates the pallet
		rotAngle := -(4 * 360)              // minus (-) designates counterclockwise rotation
	end
end
?.rotatePart(rotAngle)
```

**Back to Model a Shrink Wrapper**

Configure the Conveyor Which Transfers the Parts Insert and configure the Conveyor which receives the parts from the Turnplate .

All you have to do here is to define the sensor which triggers moving the parts to the ParallelStation .

- Click the tab Controls .
- Click and define a length -oriented sensor that is front triggered.
- Right-click into the text box Control and select Create Control .
- Copy the following source code and paste it. It determines how to move on the part or the pallet.

<!-- image -->

```simtalk
param sensorID: integer, front: boolean
if @.typeOf(.UserObjects.MyPart)
	@.move(ParallelStation)
end
```

<!-- image -->

<!-- image -->

**Back to Model a Shrink Wrapper**

##### Configure the Stations Which Handle the Pallet

Finally, insert and configure the stations which create and handle the pallet onto which the parts will be loaded.

- First, insert and configure the Source which produces the pallet. To produce a single pallet after 10 minutes, select Time of Creation &gt; Number adjustable and enter an Amount of 1 . Enter 10:00 as the Creation Times .

<!-- image -->

Then, select MyPallet as the MU to be produced.

- Next, insert the ParallelStation onto which Conveyor1 moves the parts. You do not have to change any of its settings. The TransferStation will enter the Exit Control of the ParallelStation automatically once we configure the TransferStation .
- Finally, insert and configure the TransferStation .
- Drag the station from which the parts arrive, the ParallelStation in our case, onto the TransferStation . This enters the Exit Control into the ParallelStation .
- Drag the station on which the Target of the loading action (the pallet), the ConveyorPallet in our case, is located onto the TransferStation . Select the station type Load and enter the position of the

<!-- image -->

sensor on the ConveyorPallet and click Apply . Adjust the position until it is located at the position where it needs to be and click OK .

<!-- image -->

<!-- image -->

- Start the simulation and watch how the Turnplate rotates the part. You will not be able to see anything with the default setting for the simulation speed , as the simulation runs too fast.
- To fix this, you can reduce the simulation speed in a reset method .
- Start the simulation again and watch how the parts are first rotated to the right, moved to the ParallelStation , and moved on to the TransferStation , which loads them onto the pallet. The loaded pallet is then fed back to the Turnplate , which rotates it four times around its center to the left and them moves it on to Shipping .

```simtalk
EventController.Speed := 60
```

<!-- image -->

Back to Model a Shrink Wrapper

Adjust Shrinkwrapper and Parts in 3D

As we originally created the model in 2D, we now open it in 3D by clicking Open Frame in 2D/3D on the Window ribbon tab.

When we run the simulation model in 3D, we see that we have to adapt some settings:

- The parts look strange.

<!-- image -->

As we created the model in a previous version, it uses the size of the part of that version:

<!-- image -->

In the current version the part has these dimensions:

<!-- image -->

**Note**

If the parts are shown with an offset on the ParallelStation and on the pallet , check the position of the booking point of the part, compare Booking Point Length and Booking Point Width .

<!-- image -->

When we enter 0.1 meters as the height of our part, MyPart , and leave length and width at 0.8 meters, it looks much better:

<!-- image -->

<!-- image -->

- The pallet is still too big in 3D though. To fix this, we replace its graphic in 3D, by opening MyPallet in 3D in the Class Library and selecting the context menu command Exchange Graphics in the 3D window. We use this EUR-pallet:
- The pallet now fits the width of the conveyor, the parts are much too big, they protrude the pallet and they overlap.

<!-- image -->

This is easy to fix though:

- Right-click MyPart in the Class Library and select Edit 3D Properties .
- Change to the tab Transformation and reduce the scaling. You might have to clear Scale automatically to show the settings. We selected a uniform scaling factor of 0.5 . This then looks like this:
- Then, we select a different color for the part in 3D to better see it in the model and adjust the positions of the objects in the model. To prevent the parts from breaking through the glass plates at the back and the front of the ParallelStation , we rotate it by 90 degrees.

<!-- image -->

<!-- image -->

<!-- image -->

- We finally save the model as a 3D only model with a different name and run the simulation again. As we'd expect the part parts are produced, conveyed, and loaded onto the pallet. The last part is

proceeding so fast though that we cannot follow the animation with our eyes. The simulation in 3D is faster as in 2D in principle as Plant Simulation does not have to compute the animation events for 2D.

Proceed as follows to fix this:

- Open the EventController and select a Real-time factor of 10.

<!-- image -->

This also makes our reset method redundant and we can delete it.

- We then would have to wait too long for the simulation to continue with the original Time of Creation for the pallet of 10 minutes. For this reason we shorten the Time of Creation to 1 minute. We also adjusted the processing time of the ParallelStation . Now we can follow the simulation and the animation with our naked eye again.

We can also increase the capacity of the pallet in the Z-Dimension from 1 to 3 to stack the parts on it.

<!-- image -->

To facilitate this we also have to triple the number of parts that the Source named SourceParts produces.

<!-- image -->

Back to Model a Shrink Wrapper

