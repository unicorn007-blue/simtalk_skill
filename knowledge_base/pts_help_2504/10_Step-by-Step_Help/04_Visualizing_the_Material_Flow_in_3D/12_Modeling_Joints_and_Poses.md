### Modeling Joints and Poses

#### Model Joints and Poses

In our sample model we show how to model realistic kinematics with joints and poses. You find the respective settings on the tabs Joint and Poses in the dialog Edit 3D Properties .

You can use poses to animate the object itself. As opposed to the normal self animation, you only have to set the place to which the animation is to move when using the animation with poses. As Plant Simulation knows the previous position, it then internally creates self animations which ensure a smooth transition from the previous to the new state.

In our model the Source produces parts. The Conveyor transports the part to the processing station which processes it. A revolute joint rotates the ToolHead to the right and left and a prismatic joint moves the ToolHolder up and down. We could also attach the part to the ToolHolder and manipulate it there. This would go beyond the scope of this short demonstration though. The Station then passes the part on to the Drain , which removes it from the installation.

We will demonstrate how to:

- Configure the Simulation Objects
- Create the Animation Objects
- Configure the Joints
- Configure the Poses

The finished simulation model looks like this:

<!-- image -->

The sample model Factory 51 on the Start Page shows additional usages for revolute joints and for prismatic joints .

Compare Move Poses and Joints with Mouse and Keyboard Keys

Compare Create a Simulation Object with Animation

Back to Visualizing the Material Flow in 3D

#### Configure the Simulation Objects

In our first step we configure the simulation settings of the objects:

- For the Source we entered a constant Time of Creation of 10 seconds. Apart from that we use the default settings.

<!-- image -->

- For the Conveyor we entered a Capacity of 1 , so that it only transports a single part. Apart from that we use the default settings.

<!-- image -->

- For the Station we entered a Processing Time of 20 seconds and a Recovery Time of 5 seconds. Apart from that we use the default settings.
- For the Drain we use the default settings.

<!-- image -->

Back to Model Joints and Poses

#### Create the Animation Objects

When the part is located on the machine, the ToolHead rotates to the right and the ToolHolder moves up. Then ToolHead and ToolHolder remain at their new position while the processing time passes. After that they both return to their original pose.

Proceed as follows to create the animation object of our machine:

- Click the Station with the right mouse button and open it in a new 3D window.
- Click the part of the graphic called default.tool with the right mouse button.

<!-- image -->

- Select Make Animatable Object . Type in ToolHead as the Name . Click OK .

**Note**

The Object Position sets the origin of the rotation around which the tool head will be rotated. If the object does not rotate as expected, check the values for the individual axes of the origin of the rotation.

<!-- image -->

<!-- image -->

Then, set the joint settings on the Tab Joint . We describe this in the next topic.

<!-- image -->

- Click the ToolHead with the right mouse button and open it in a new 3D window.
- Click the ToolHead with the left mouse button. Press the + key, i. e., the square part with the telescopic holder, to select the ToolHolder . Enter ToolHolder as the Name . During the simulation the toolholder moves up and down.

<!-- image -->

Back to Model Joints and Poses

<!-- image -->

#### Configure the Joints

In the next step we configure the joints of the ToolHead and of the ToolHolder . We equip the ToolHead with a Revolute Joint and the ToolHolder with a Prismatic Joint .

- Click the ToolHead with the right mouse button and select Edit 3D Properties . Change to the Tab Joint . We selected the Joint Settings below for the Revolute Joint .
- Click the ToolHolder with the left mouse button and press the Spacebar . Change to the tab Joint . As the ToolHolder is to move up in the z-direction, we clicked on the button next to Z. This sets the z-direction as the Translation Direction . We then selected the Joint Settings below.

<!-- image -->

Back to Model Joints and Poses

<!-- image -->

#### Configure the Poses

In our last step we configure the Poses of our Station on the Tab Poses .

- Click into the background of the 3D window of the Station with the right mouse button. Add Pose1 and Pose2 .

<!-- image -->

- Click Pose1 with the left mouse button and click Edit . The dialog shows the settings which we selected on the tab Joint .
- Click Pose2 with the left mouse button and click Edit . The dialog shows the settings we selected on the tab Joint .
- Now that we configured joints and poses, we can program the movements in the respective controls. To do so, we return to the simulation object and change to the tab Controls . Here we create an Entrance Control and an Exit Control each.

<!-- image -->

<!-- image -->

<!-- image -->

Within the controls we define to which poses the ToolHead and the ToolHolder move.

For the Entrance Control we entered these instructions:

?._3D.Poses.moveTo("Pose2") // moves to Pose2

For the Exit Control we entered these instructions:

wait ?._3D.Poses.moveTo("Pose1") // returns to Pose1 @.move                           // and moves the part

When you now start the simulation, you can watch how the ToolHead rotates and how the ToolHolder moves up and then down again.

To better view the sequence, we selected the Real time factor x 3 .

<!-- image -->

<!-- image -->

You can show and hide poses with the toggle button . Plant Simulation only shows a single pose at a time. If you show a different pose, Plant Simulation first hides the pose that is already shown.

Plant Simulation moves the object to the state that corresponds to the pose. While the pose is shown and the dialog is open, you can change the state of the pose stepwise by clicking the left or right arrow key:

**Press one of the arrow keys to**

- rotate the pose by 1 ° of the range from the joint settings if both limits are defined.
- move the pose by 0.1 m if at least one limit is missing when a Prismatic Joint is selected, or
- rotate the pose by 1 ° if at least one limit is missing when a Revolute Joint is selected.

The left arrow key moves the pose toward the lower limit.

The right arrow key moves the pose toward the upper limit, independent of rotation axis or translation direction.

<!-- image -->

In the example below we showed Pose1 . It moves the Prismatic Joint of the ToolHolder up when you press the right arrow key .

<!-- image -->

Compare Tab Poses and Tab Joint

Compare Configuring the Robot in 3D

Back to Model Joints and Poses

##### Video on YouTube

[https://youtu.be/wfVN-mcWNsc?si=LepG6cgh0MDLKilQ&amp;t=22](https://youtu.be/wfVN-mcWNsc?si=LepG6cgh0MDLKilQ&t=22)

