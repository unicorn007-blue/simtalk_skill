### Optimize a Graphic

Optimizing the graphic, i.e., flattening the hierarchy of an object, deletes unnecessary information from the object, allowing for faster rendering, and a quicker display of the object.

Whenever you import graphics, it is useful to optimize them. This is not because the graphics you import are badly designed, but because they are typically designed for another kind of use in the originating program. The engineer who designs a component, such as an engine, will naturally include every detail of that engine in the graphic that he creates, because it is imperative to provide these details for producing the engine.

For us as users these details of the engine are of no interest at all. Our main concern is that the simulation runs fast and that the animation looks good and runs smoothly.

We therefore advise to optimize every graphic you import. Do this as soon as possible, but not before you extracted all the structural information from the graphic that you need, compare Create a Simulation Object with Animation .

Before you can do this, you have to make an animatable object from the graphic, compare Make Animatable Object .

To optimize a 3D graphic, click the animatable object, whose graphic you would like to optimize, in the

<!-- image -->

scene window, and click Optimize Selected Graphic on the Edit ribbon tab of the 3D window . Experiment with the settings described under Step 1: Prune Tiny Graphics , Step 2: Flatten Structure , and Step 3: Visibility Filter .

<!-- image -->

<!-- image -->

Plant Simulation shows two characteristics of the graphic under Graphic complexity , namely the number of nodes and the number of polygons. The optimization strategies mainly affect the number of nodes and the number of polygons.

Watch the effects of optimizing the hierarchy of the animatable object in the dialog Show 3D Graphic Structure .

**Note**

As you cannot restore discarded data, only flatten the structure after you are done with modeling the object! You will not detect any difference in the appearance of the object; you will see a difference though in its graphic structure, which Plant Simulation flattened for better performance at runtime.

Only accept the result, when the optimized graphic meets your intentions in its looks and in its structure.

Back to Visualizing the Material Flow in 3D

