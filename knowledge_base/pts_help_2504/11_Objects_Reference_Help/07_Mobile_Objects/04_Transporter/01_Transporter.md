#### Transporter

- Represent automatically guided vehicle-systems with the Resource Objects AGVPool and Marker where the Transporter drives freely within the area. The AGV in the AGVPool is a Transporter by default. For this reason the methods, attributes, and read-only attributes of the Transporter apply to the AGV .

With the distance settings Length Zone 1 , ΔWidth Zone 1 , Length Zone 2 , and ΔWidth Zone 2 of the Distance control you can prevent AGVs from colliding.

The Transporter provides three different Types of loading space.

- Store designates a matrix-oriented loading space consisting of loading places along the X-Dimension , the Y-Dimension , and Z-Dimension onto which the Transporter places the parts it loads.
- Track designates a passive length-oriented loading space onto which the Transporter loads and unloads parts. This is especially handy for modeling a cross-sliding car and other types of materials handling equipment. You can also specify Controls and Sensors .

<!-- image -->

**Note**

The animation on the length-oriented loading space requires an animation line in 2D. As Plant Simulation does not create the animation line automatically, you have to create it in the icon of the object. For vector graphics we defined the animation line, you cannot change it.

**Note**

The Length of the loading space is independent of the MU Length of the Transporter as such in 2D and in 3D.

<!-- image -->

- Line provides an active length-oriented loading space similar to a conveyor being part of the loading space, which transports the loaded parts forward or backward .

<!-- image -->

**Note**

The window Show Attributes and Methods ( F8 ) only shows the attributes and methods pertaining to the selected type of loading space. If you select Track for example, the window only shows the attributes and methods pertaining to the loading space of type Track , not those pertaining to the loading space of type Store or Line .

On point-oriented objects, such as the Station , ParallelStation , etc. and on the Conveyor , the Transporter behaves passively, i.e., the set-up time and the processing time of these objects determine how long it is going to stay on these objects. These material flow objects also determine the Exit Behavior of the MUs .

On objects of type Track and TwoLaneTrack , the Transporter itself behaves actively, i.e., it determines on which Track/TwoLaneTrack it will drive to get to its Destination object. To do so, it uses the Forward Destination List or the Backward Destination List of the Track/TwoLaneTrack en-route to the destination.

You have to make sure that the Transporter is stopped when it is going to be loaded or unloaded and that the pallets it transports are completely loaded or unloaded.

**Note**

By default, the Transporter is the AGV of the Automated Guided Vehicle System . For this reason the methods, attributes, and read-only attributes of the Transporter apply to the AGV as well.

Appearance of the Transporter in 3D

- You can set how Plant Simulation distributes the parts on the Animation Area on the tab MU Animation of the Container .
- You can set a material on the tab Appearance .

<!-- image -->

- You can select alternative graphics for the Transporter . Click Exchange Graphics in the 3D window of the Transporter and select one of the alternative graphics in the Plant Simulation Installation folder &gt; s3d-graphics &gt; Transporters .

<!-- image -->

To show a tooltip with information about the Transporter , hover with the mouse over it.

<!-- image -->

Add the Object to the Simulation Model

To add the Transporter to your simulation model, click Manage Class Library &gt; Basic Objects &gt; MUs &gt; Transporter on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Shared Properties of the Mobile Objects

Model Tugger Trains &gt; Model a Tugger Train

Model a Battery-powered Transporter, Extended

Model a Battery-powered Transporter, Extended

Model an Automated Guided Vehicle System (AGVS)

Routing and Driving Properties

How the Transporter Gets to Its Destination

Video on YouTube

[https://youtu.be/9g6Uou-8eMc?si=-Nr7toF8a5AOQ8rg](https://youtu.be/9g6Uou-8eMc?si=-Nr7toF8a5AOQ8rg)

<!-- image -->

