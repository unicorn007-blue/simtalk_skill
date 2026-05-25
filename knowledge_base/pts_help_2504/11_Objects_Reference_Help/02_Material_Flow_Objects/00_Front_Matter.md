## Material Flow Objects

Plant Simulation provides a number of objects for simulating the flow of materials through a plant.

<!-- image -->

<!-- image -->

<!-- image -->

- Objects for modeling the plant and for controlling the simulation:
- Use the Frame as the container for creating your simulation models. It might, for example, represent a complex machine, a part of an plant, or the entire plant. The Frame is the principal object facilitating hierarchic modeling.
- Use the Connector for establishing material flow connections between objects along which the parts move.
- Use the EventController for coordinating and synchronizing the events taking place during a simulation run.
- Use the Interface for modeling transitions between Frames , i.e., from one part of the model to another. It also facilitates hierarchic modeling.
- The material flow objects proper:
- Use the AngularConverter for changing the conveying direction of the parts from lengthwise to crosswise conveyance and vice versa.
- Use the AssemblyStation for adding mounting parts to a main part, for example doors to a car body.
- Use the Buffer for temporarily holding a large number of parts and then pass them on.
- Use the Converter for conveying a part either straight through or for lifting it onto a laterally moving transport level and then conveying it to the left or right-hand side.

