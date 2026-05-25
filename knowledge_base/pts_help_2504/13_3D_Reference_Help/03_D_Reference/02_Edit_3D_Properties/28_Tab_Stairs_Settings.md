#### Tab Stairs Settings

Stairs Settings

Change the settings of the selected Staircase in your simulation model.

<!-- image -->

- To set if the stairway is an Obstacle for the Worker , select the respective entry in the list. In addition to the settings that apply to all graphics, you can also select Sides as the obstacle. It computes the obstacle for the stairway so that:
- An additional entrance or exit from or to which the stairway leads will not be covered by the obstacle.
- The obstacle is being limited to the relevant area for the respective simulation-relevant height.
- To assign a material or a color, select the barred area and click 3D Properties &gt; Tab Material on the Home ribbon tab.

<!-- image -->

**Note**

The Worker walks slower on an incline than he walks on a flat surface.

**Note**

If the Worker walks freely within the area , he can only get to a different floor in the building by walking up or down a ramp on a Footpath or walking up and down Stairs .

The example model Factory 51 demonstrates how you can use Stairways .

<!-- image -->

**Show Manipulators**

You can edit the dimensions of the object by clicking Show Manipulators on the Edit ribbon tab.

<!-- image -->

**Tab States**

SimTalk

createStairs [SimTalk]

ObstacleForWorker [SimTalk]

See also

Stairs

Model Your Own 3D Graphic

Accessing Attributes of Graphic Shapes &gt; \_Rack Attributes

\_Detailed Access To Graphics

