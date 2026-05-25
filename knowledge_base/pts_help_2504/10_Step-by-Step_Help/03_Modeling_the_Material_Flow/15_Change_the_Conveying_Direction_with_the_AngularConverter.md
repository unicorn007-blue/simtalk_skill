### Change the Conveying Direction with the AngularConverter

You can use the AngularConverter to change the conveying direction of the mobile objects from lengthwise to crosswise conveyance or from crosswise to lengthwise conveyance. The AngularConverter can contain a single part at any one time.

You can insert the AngularConverter into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In the sample model the Source named PartsIn produces parts of type MyCarbody and moves them to the AngularConverter . It in turn changes their conveying direction . The length, which the part takes up on the AngularConverter , then changes from MU length to MU width . This process uses up the moving time . Once the part has exited the AngularConverter , it returns to its original position. It then is ready for the next MU .

The finished simulation model looks like this in 2D:

<!-- image -->

To create the simulation model, proceed as follows:

- First, insert and configure the Source . Select the part which it is to produce. We named our Source PartsIn and selected the part MyCarbody , which we created in the folder UserObjects .

<!-- image -->

- Insert the Conveyor that feeds the parts to the AngularConverter . You can make it as long as you like, but you do not have to change any of the other settings. We made our feeder line 10 meters long. We also changed some curve settings for display reasons to better accommodate our part named MyCarbody on the Conveyor .
- Insert the first AngularConverter and configure it. We entered an Entry Length and an Exit Length of 5 meters each.

<!-- image -->

<!-- image -->

We also changed some curve settings for display reasons to better accommodate our part named MyCarbody on the AngularConverter . To show the text box Curve Width , we cleared the check box Transfer Length .

<!-- image -->

- Insert the ProcessingConveyor into which the AngularConverter moves the parts and configure it.
- We entered a Length of 2.5 meters.
- We entered a Speed of 0.001 meters per second to make the part stay on the processing line instead of being moved on continually.

Plant Simulation also recomputes the time when you click Apply and/or OK . In our case a time of Speed of 0.001 meters per second over a Length of 2.5 meters corresponds to a Time of 41 minutes and 40 seconds and vice versa.

<!-- image -->

- We also changed some curve settings for display reasons to better accommodate our part named MyCarbody on the AngularConverter .

<!-- image -->

- To finish the simulation model, insert the second AngularConverter , another Conveyor , and the Drain , which removes the parts from the plant. For the AngularConverter and the Conveyor you can use the same settings as for the Conveyor and the AngularConverter , which you inserted above. Finally, connect all objects with Connectors .
- To make the model visually more pleasing, move the objects closer to each other so that the Connectors are not visible. Then, reduce the simulation speed by dragging the speed slider to the left, start the simulation, and watch how the car bodies move over the stations.

<!-- image -->

Double-click a part when it has reached the point at which the conveying direction changes on the AngularConverter at the top. Up to this point the Conveying Direction is forward .

<!-- image -->

After this point the Conveying Direction is lateral right until the part reaches the point at which the conveying direction changes again.

<!-- image -->

After this point the Conveying Direction changes to backward until the part reaches the Drain .

<!-- image -->

We can also open the model in 3D and select other appearances than the default settings for the Conveyors and the AngularConverter . As we do not have any 3D graphic for the car-bodies, we use the pallet with the same dimensions.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Modeling the Material Flow

