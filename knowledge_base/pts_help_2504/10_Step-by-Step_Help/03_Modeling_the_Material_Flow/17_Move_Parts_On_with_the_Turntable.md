### Move Parts On with the Turntable

You can use the Turntable to model a rotating platform, which moves the part onto one of several connected material flow objects.

In the sample model the Source named PartsIn produces parts of type MyPart and moves a single part each on the feeder line of the Turntable . This in turn moves the parts cyclically on to its successors, i.e., to the feeder lines of the Drains , which we named OutA and OutB in our model.

You can insert the Turntable into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

The finished simulation model looks like this:

<!-- image -->

To create the simulation model, proceed as follows:

- First, configure the Source . Enter the interval during which it produces the parts and select the part it is to produce. We selected the negative exponential distribution, entered the parameters 0:10, 0, 1:40 , and selected the part MyPart , which we created in the folder UserObjects .

<!-- image -->

- Insert the conveyor that feeds the parts to the Turntable . You can make it as long as you like, but you do not have to change any of the other settings.
- Insert the Turntable and its direct successors in the sequence of stations and connect them. The Turntable needs the successors to configure its Entry Angle Table and its Exit Angle Table . In our model these successors are the feeder lines of the Drains .

<!-- image -->

- Our Turntable is 4 meters long and has its Rotation Point in the center, i.e., at 2 meters.
- To connect the Turntable with its successors, select the Connector in the Toolbox and click the end point of the Turntable . Drag the mouse to the starting point of the Conveyor and click the left mouse button. You'll notice that the starting point of the Connector jumps to the left on the rotation circle of

<!-- image -->

the Turntable . This is because Plant Simulation computes the angle at which the successor is located in the Frame in relation to the Turntable .

To view the exit angles, click Exit Angles Table .

<!-- image -->

- Configure the Drains and start the simulation. Watch how the part moves onto the Turntable . It first rotates to the line FeederPartA , and moves the part onto it. It then returns to its original position, picks up the next part, rotates to the line FeederPartA , and moves the part onto it, and so on.
- To make the Turntable turn the part around before moving it onto the top feeder line, open the Exit Angle Table and select Which Side &gt; MU leaves backward for the line FeederPartA . Start the simulation again and watch how the Turntable turns the part around.

<!-- image -->

By default the Turntable is positioned in the air in 3D if you do not define any legs for it. If you do define legs, the entire Turntable rotates, including the legs. As this is not realistic, we create a cylindrical base on which the Turntable proper then rotates.

- Open the Turntable in a new 3D window.
- Click the right mouse button and select Edit 3D Properties . Change to the tab Graphics . Click Add and create a new graphic group for the base of the Turntable . We named our graphic group base . Click OK .

<!-- image -->

- Change to the ribbon tab Edit . Click Cylinder to create and insert a cylinder as the base of the Turntable . We selected these measurements.

<!-- image -->

- Insert the base at the intersection of the grid line below the Turntable proper in its center.
- Click the base with the right mouse button and select Make Animatable Object . Type in base as the name . Click OK in the dialog.

<!-- image -->

<!-- image -->

- Plant Simulation opens the dialog Edit 3D Properties and selects the tab Joint . Select Revolute Joint and type in 0 as the Velocity . This prevents that the base below the Turntable also rotates when the Turntable proper rotates toward the feeder lines. Click OK .
- Run the simulation and watch what happens.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Back to Modeling the Material Flow

