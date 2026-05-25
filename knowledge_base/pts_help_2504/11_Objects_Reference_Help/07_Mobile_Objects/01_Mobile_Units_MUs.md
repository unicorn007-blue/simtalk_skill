### Mobile Units [MUs]

Plant Simulation provides the mobile units to model the materials that flow through a simulation model while being processed and transported by the material flow objects.

The mobile objects are abbreviated as MU , for M obile U nit, or MUs , for M obile U nit s in Plant Simulation .

<!-- image -->

- Use the Part for modeling parts being produced and transported. The Part represents a single workpiece, such as a cylinder head, a crankshaft, etc. that is going to be processed.
- Use the Container for modeling pallets, bins, boxes, etc. The Container transports other parts. It might represent pallets, bins, boxes, etc. in your plant into which parts are placed. You can assign it a Dimension , i.e., a Capacity .
- Use the Transporter for modeling self-propelled vehicles allowing it to drive on its own on Tracks , TwoLaneTracks or freely within the plant. The Transporter represents self-propelled vehicles allowing it to drive on its own on a Track / TwoLaneTrack and transporting Parts , Containers and other Transporters . It uses the Capacity , the Speed , and the Acceleration which you define, when driving forward or in reverse.

You can hitch up several Transporters to create Tugger Trains .

You can also model automatically guided vehicle-systems with the Transporter and with the Resource Objects AGVPool and Marker where the Transporter drives freely within the area of the simulation model.

We call a single mobile object MU and several mobile objects MUs in Plant Simulation and in the help.

Properties and behavior of the mobile objects are similar in many ways. They differ mainly in their ability to transport other MUs and in their ability to move under their own power or not.

As opposed to the stationary material flow objects, the mobile objects are not bound to a fixed location. During a simulation run they move from material flow object to material flow object through the model and represent discrete material flows.

Initially a Source creates the MU from a MU class in the Class Library . It is then moved to the different stations in the model along the material flow connections. The stations process the MU . The MU remains on the final station of its movement until it is removed from the plant, usually by a Drain .

**Note**

You can also place a MU onto a material flow object with drag-and-drop, either from the Class Library or the Toolbox .

During the simulation run the MU is either located on a material flow object, or on a MU with loading capabilities, such as a Container or a Transporter . The material flow objects either move the MU along the material flow connections, symbolized by the Connector , to the next object in line, or the flow of material is controlled by Method objects.

The length-oriented objects Conveyor , Turnplate , Turntable , Track , and TwoLaneTrack use the actual MU Length of the mobile objects, while all other material flow objects ignore the length of the MU . The AngularConverter and the Converter use the MU Length and the MU Width .

<!-- image -->

In 3D, you can set a material on the tab Appearance .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Shared Properties of the Mobile Objects

**Shared Properties of the Material Flow Objects**

#### Shared Properties of the Mobile Objects

