### Controlling the MU Animation

#### Control the MU Animation

On the tab MU Animation you can define how the mobile objects ( MUs ) are animated on the material flow objects. The Frame also counts as a material flow object.

The tab looks different for objects without loading space and for objects with loading space .

- On the Sub-tab Animation Paths you can define these MU Animations :

<!-- image -->

- The MU Animation on Length-Oriented Objects
- The MU Animation on Point-Oriented Objects
- The MU Animation on Point-Oriented Objects Holding Several Parts
- The MU Animation on Animation Paths on the Workplace
- On the Sub-tab Animation Area you can define the MU Animation on Objects with Loading Space by activating the Animation Area .

The objects with a loading space -AGVPool , Container , ParallelStation , PlaceBuffer , Store , Transporter , Worker , Workplace , and WorkerPool - use the animation area , provided you activated it. If it is not activated, the objects use animation paths . Except for the AGVPool you have to create the animation paths yourself though.

<!-- image -->

#### MU Animation on Length-Oriented Objects

The length-oriented objects animate the parts automatically. If a path named Default exists, the objects use that path.

<!-- image -->

- The length-oriented objects AngularConverter , FootPath , Turnplate , and Turntable can each hold and transport a single part.
- The length-oriented objects Conveyor , Track , and TwoLaneTrack can hold and transport several parts.

For all length-oriented objects you can add an Animation Offset and select or clear Gravity Mode . To do so, press the M key to show the manipulators in the scene.

- The Conveyor animates the parts on the blue line in the center of the conveyor. The standard setting looks like this:
- The FootPath animates the Workers on the blue line in the center.

<!-- image -->

<!-- image -->

- The Converter animates the parts automatically. If a path named Default exists for length-wise movements and Cross for cross-wise movements exits, it uses that path.
- The Track animates the Transporters in the center of the travel track.
- The TwoLaneTrack animates the Transporters automatically. If paths named A or B exist, depending on the lane and the setting for right-hand traffic or left-hand traffic exist on which the Transporter drives, it uses that.

<!-- image -->

<!-- image -->

Back to Control the MU Animation

<!-- image -->

##### Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=nQLvgpv7FieRe5mX&amp;t=455](https://youtu.be/rQi5oRyZckQ?si=nQLvgpv7FieRe5mX&t=455)

#### MU Animation on Point-Oriented Objects

For point-oriented objects, which can hold a single part , for example the Station , you can:

- Specify the Animation Object and the MU Side to Attach .
- Add , extend , edit , and delete an animation path.

The point-oriented objects, which hold a single part animate the parts as follows:

<!-- image -->

- The Station uses the path named Default for animating the parts.

Click Show to show the MU animation path of the Station in the model. As the Station can only process a single part, the animation path consists of a single point. The path tool, i. e., the red pyramid, shows where the part is going to be animated. You can click the path tool and move it with the arrow keys on the keyboard. The part will then be animated at the new position.

**Video on YouTube**

<!-- image -->

- The DePortioner uses the path named Default for animating the parts.
- The Portioner uses the path named Default for animating the parts.

<!-- image -->

<!-- image -->

**Back to Control the MU Animation**

##### Video on YouTube

[https://youtu.be/rQi5oRyZckQ?si=GwvsYiXqtDPQHw-8&amp;t=76](https://youtu.be/rQi5oRyZckQ?si=GwvsYiXqtDPQHw-8&t=76)

#### MU Animation on Point-Oriented Objects Holding Several Parts

For point-oriented objects, which can hold several parts , you can:

- Specify the Animation Object and the MU Side to Attach .

- Add , extend , edit , and delete an animation path.

The point-oriented objects, which can hold several parts animate the parts as follows:

- The Buffer stacks the parts along the standard animation path upward one on top of the other. You can set the capacity of the Buffer in the dialog of the simulation properties on the tab Attributes .
- The PickAndPlace robot animates the parts automatically. If a path exists, it uses the first path for the first MU , the second path for the second MU , etc. If no suitable path exists, but if a path named Default exists, the robot uses that path.
- For the WorkerPool you can select if it shows the Workers in the WorkerPool on animation paths or on an animation area distributed along the Y-dimension .
- The WorkerPool in the Class Library only shows the created Workers when you activate Show Content on the tab Graphics . In our example we created four Workers .

<!-- image -->

<!-- image -->

<!-- image -->

For the setting Animation Path the WorkerPool uses the first path for the first MU for the animation, the second path for the second MU , etc. If no suitable path exists, but if a path named Default exists, the WorkerPool uses that path.

<!-- image -->

- For the Workplace you can select if it shows the Workers on it on animation paths or on an animation area distributed along the X-dimension . Our three Workers on an animation area look like this:

<!-- image -->

If you do not use an animation area this applies:

Plant Simulation animates the first Worker on the first animation path, the second Worker on the second animation path, and the third Worker on the third animation path. You have to define these animation paths yourself. If, for example, no third path exists for the third Worker , Plant Simulation uses the default animation path. If no default animation path exists, Plant Simulation does not animate the Worker at all.

CompareHow Workers Queue Up in Front of the Workplace

Back to Control the MU Animation

#### MU Animation on Objects with Loading Space

The objects with a loading space -AGVPool , Container , ParallelStation , PlaceBuffer , Store , Transporter , Worker , Workplace , and WorkerPool - use the animation area , provided you activated it. If it is not activated, the objects use animation paths .

**Note**

The indexes for paths start with 0, not with 1. The signature #0#0 designates the first animation point, #1#2 designates the position with the X-index 2 and the Y-index 3, etc.

As a rule you can use the factory settings for these objects unless these do not meet your requirements. Plant Simulation distributes the parts evenly across the animation area, which is defined by its length and its width.

**Note**

We recommend to use the animation area instead of animation paths as this means substantially less modeling effort on your side because you do not have to create the animation paths.

The objects with a loading space which use the animation area animate the parts as follows:

- The AGVPool only shows the created Transporters if you activate Show content on the tab Graphics . The AGVPool animates parts as follows:
- If the animation area is active, the AGVPool uses it. Here the index of the MU is the index of the area in the Y-direction; the capacity in the X-direction always is 1.
- If the animation area is not active, the AGVPool uses the first path for the first MU for the animation, the second path for the second MU , etc. If no suitable path exists, but if a path named Default exists, the AGVPool uses that path.

In our example we created four Transporters .

<!-- image -->

- The Container with the standard setting, two parts each in two rows, looks like this with four loaded parts.

<!-- image -->

- The ParallelStation has a Capacity of four parts by default. The standard setting distributes these parts as shown below across the animation area.

<!-- image -->

If we increase the Capacity in the X-Dimension to three parts, it looks like this.

<!-- image -->

You can also increase the length of the animation area, in our example to 3 meters. Plant Simulation then evenly distributes the parts across the changed animation area.

<!-- image -->

- The PlaceBuffer has a Capacity of four parts by default. It animates the parts as follows:
- If the Animation Area is active, the PlaceBuffer uses it. Here the index of the MU is the index of the area in the Y-direction; the capacity in the X-direction always is 1. It looks like this for the standard capacity of four parts:

<!-- image -->

- If a MU animation path named Default with more than one anchor point exists, the index of the MU is converted to a relative position. Plant Simulation then evenly distributes the MUs on this line.
- Otherwise the PlaceBuffer uses the first path for animating the first MU , the second path for the second MU , etc. If no suitable path exists, but if a path named Default consisting of a single point exists, the PlaceBuffer uses that path.
- The Store with the standard setting, three parts each in three rows, looks as shown below with nine parts placed in stock. The parts exactly fit the individual storage compartments.

<!-- image -->

You can change the Dimensions of the individual storage compartments and the Capacity of the Store in the Z-Dimension . In the example below we increased the height in the Z-Dimension and the number of parts in the Z-Dimension . This way Plant Simulation stacks several parts in the individual storage compartments.

<!-- image -->

The storage area is placed on the XZ plane and looks like this when it is shown.

<!-- image -->

- The Transporter with the standard settings Store and Animation Area , with three parts each in two rows, looks like this with six loaded parts.

<!-- image -->

The Transporter with an active loading space of type Line uses the animation path named Line .

<!-- image -->

The Transporter with a passive loading space of type Track uses the animation path named Track .

<!-- image -->

- The Worker with the standard settings has a Capacity of one part in the X-Dimension and in the Z-Dimension .

<!-- image -->

It looks like this when shown in the Frame .

<!-- image -->

If you want the Worker to carry two stacked parts, type in 2 as Z-Dimension . This then looks like this.

<!-- image -->

If you want the Worker to carry two parts in each hand, type in 2 as X-Dimension and clear Animation Area . The Worker then uses the Animation Paths which we defined. This then looks like this.

<!-- image -->

See also Model a Worker Who Carries Several Parts in 3D

Back to Control the MU Animation

#### MU Animation on Animation Paths on the Workplace

The Workplace provides a single MU animation path named Queue by default.

Plant Simulation animates the Workers , who are waiting in front a Workplace which they cannot enter, on this animation path that visualizes the queue.

<!-- image -->

**Note**

If a Workplace does not provide a MU animation path named Queue , all Workers wait at the same position until they can enter the Workplace .

You can set the Distance in Queue in the dialog of the Workplace .

<!-- image -->

Click Show to show the MU animation path . The path tool, i. e., the pyramid, shows where the Worker is going to be animated. You can click the path tool and move it with the arrow keys on the keyboard. The Worker will then be animated at the new position.

The predefined animation path looks like this.

<!-- image -->

You can also define a path of type Polycurve , Spline , or Rotation path . Before you do that though, rename the original, predefined path named Queue .

In this example we first renamed the default path to MyQueue and then created a spline path named Queue . 3D then animates the Workers waiting in line on this path.

<!-- image -->

If you want to use the default path again, rename your path and change the name of the original path back to Queue .

To animate the Worker on an animation area, select the check box Animation Area and define the respective settings. Our Workplace has a Capacity of 3 .

**Note**

If you do not use an animation area this applies:

Plant Simulation animates the first Worker on the first animation path, the second Worker on the second animation path, and the third Worker on the third animation path. You have to define these animation paths yourself. If, for example, no third path exists for the third Worker , Plant Simulation uses the default animation path. If no default animation path exists, Plant Simulation does not animate the Worker at all.

In most cases an animation path is the suitable way to animate the Workers on the Workplace . If you modeling situation requires it, you can also animate the Workers on an animation area though.

<!-- image -->

We animate it on an Animation Area with these settings:

<!-- image -->

This looks like this in our model:

**See also**

Model a Worker Who Waits in Line

How Workers Queue Up in Front of the Workplace

Back to Control the MU Animation

<!-- image -->

**Video on YouTube**

##### Video on YouTube

[https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&amp;t=775](https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&t=775)

