### Accessing the Worker

#### \_\_Accessing the Worker

SimTalk provides the attributes listed in the table of contents to the left for the Graphic Sequences of the Worker in 3D .

See also

Edit 3D Properties [dialog] &gt; Graphic Sequences

#### \_3D.GraphicsWhenCarrying [SimTalk]

Sets a sequence of graphic groups of the Worker designated by &lt;Path&gt;.

Remarks

The Worker cycles through the graphic groups in the sequence which you enter here, when he walks on a FootPath , or he walks freely within the model, while he carries a part.

If this sequence is empty, 3D uses the visible graphic groups as defined in the attribute \_3D.VisibleGraphics , i. e., the default behavior.

Type

Attribute

Syntax

```simtalk
< Path >._3D.GraphicsWhenCarrying:string[]
```

Assignment Value

You can assign an array of data type string .

Example

```simtalk
.Resources.MyWorker._3D.GraphicsWhenCarrying := ["Pose1", "Pose2"]
```

See also

Edit 3D Properties [dialog] &gt; Graphic Sequences &gt; Walk and Carry Part

\_3D.VisibleGraphicGroups [SimTalk]

#### \_3D.GraphicsWhenEmpty [SimTalk]

Sets a sequence of graphic groups of the Worker designated by &lt;Path&gt;.

Remarks

The Worker cycles through the graphic groups in the sequence which you enter here, when he walks on a FootPath , or when he freely within the model, while he does not carry a part.

If this sequence is empty, 3D uses the visible graphic groups as defined in the attribute \_3D.VisibleGraphics , i. e., the default behavior.

Type

Attribute

Syntax

```simtalk
< Path >._3D.GraphicsWhenEmpty:string[]
```

Assignment Value

You can assign an array of data type string .

Example

```simtalk
.Resources.MyWorker._3D.GraphicsWhenEmpty := ["Pose1", "Pose2"]
```

See also

Edit 3D Properties [dialog] &gt; Graphic Sequences &gt; Walk Without Part

\_3D.VisibleGraphicGroups [SimTalk]

#### \_3D.ObstacleForWorker [SimTalk]

Sets which part of the object designated by &lt;Path&gt; is an obstacle for the Worker when he is walking freely within the area of the model.

Remarks

**Note**

To show the Barred Areas/Obstacles for the Worker in your model, press the o key on your keyboard or

<!-- image -->

click on the tab View of the 3D window.

**Note**

When you view the Obstacles for the Worker , you will notice that there is a gap of 40 cm between the obstacles and the objects/graphics. This is because we supposed the width which a Worker needs to pass through to be 80 cm. As our Workers do not have width as such, you see this distance between the obstacles instead.

Type

Attribute

Syntax

&lt; Path &gt;.\_3D.ObstacleForWorker:string

Assignment Value

You can assign a value of data type string .

You can specify one of the following settings:

| Setting        | Description                                                                                                                                                                                                                                                                                                                                             | Looks like this   |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
| "Bounding box" | The bounding box of the entire object is an Obstacle for the Worker around which he has to walk. This applies for example for the material flow objects , such as the Station , etc., and for graphics. For the Workplace Plant Simulation shows two bounding boxes with a gap in between. This ensures that the Worker only stays on the middle of the |                   |

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Setting                            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Looks like this   |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|                                    | Workplace . The Worker first has to leave the Workplace before he can change his walking direction forward the next destination object. Bounding box is the most performant setting.                                                                                                                                                                                                                                                                                                                                                 |                   |
| "Bounding box of visible graphics" | The bounding box of the entire object is an Obstacle for the Worker around which he has to walk. Graphic groups, which are hidden at the moment, are not considered. Length-oriented objects and Frames do not provide this setting.                                                                                                                                                                                                                                                                                                 |                   |
| "Graphics"                         | The individual graphics of the object are an Obstacle for the Worker around which he has to walk. In the example to the right the Worker can walk through the pillars and the Station without having to walk around the overall obstacle. This applies for example for the length-oriented material flow objects , such as the Conveyor . For the object Conveyor Plant Simulation approximates the display of the bounding box only roughly to the curve, i.e., it does not show the curve of the conveyor as a smooth curved line. |                   |

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Setting            | Description                                                                                                                                                                                                                                                                                                                                                              | Looks like this   |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|
|                    | The setting Graphics can have negative effects on the performance when you switch the display often.                                                                                                                                                                                                                                                                     |                   |
| "Visible graphics" | The graphics of the object are an Obstacle for the Worker around which he has to walk. Graphic groups, which are hidden at the moment, are not considered. This applies for example for the length- oriented material flow objects , such as the Conveyor . The setting Visible graphics can have negative effects on the performance when you switch the display often. |                   |
| "None"             | The object is no obstacle for the Worker . He can walk through the object or across it. This applies for example for the information flow objects , such as the Method , etc.                                                                                                                                                                                            |                   |

**Example**

Station.\_3D.ObstacleForWorker := "Graphics"

**SimTalk**

\_3D.getGraphic(…).ObstacleForWorker

See also

Edit 3D Properties &gt; Graphics [tab, 3D] &gt; Obstacle for the Worker [drop-down list]

Edit 3D Properties &gt; Graphic Settings &gt; Obstacle for the Worker

Barred Area

Model a Worker Who Walks Freely Within the Model Worker [object] in 2D

WorkerPool &gt; Travel Mode [drop-down list]

**Accessing Methods of Graphic Shapes**

