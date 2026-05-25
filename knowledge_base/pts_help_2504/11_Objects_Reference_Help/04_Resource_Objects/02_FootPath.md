### FootPath

See also

Worker Stays Here After Completing the Job

Get Job Orders At Home Only

Home Location

**FootPath**

#### FootPath [object]

Use the FootPath for modeling a path on which the Worker walks from the WorkerPool to the Workplace .

**Icon**

<!-- image -->

**Description**

The Worker -WorkerPool -Workplace -FootPath -concept refines the Broker -Importer -Exporter-concept. In the WorkerPool you can select the Travel Mode with which the Worker gets to his work station:

<!-- image -->

- He can walk freely within the area of the simulation model, just like in the real world.
- He can be teleported to the Workplace you specify.
- He can walk along the FootPaths in the simulation model.

As a rule, the Worker functions as an Exporter with a capacity of 1. If you want to model and simulate walking distances between the WorkerPool and work stations or between work stations, use the FootPath . Plant Simulation animates the Workers on the FootPath if they move to the stations or in between the stations.

You can link several FootPaths with Connectors to create a network of FootPaths . The Worker walks within this network from his WorkerPool to the Workplace . Provided the WorkerPool and the Workplace are connected to the same network of FootPaths , the Worker walks from the WorkerPool to the Workplace and back on the shortest possible route.

A network of FootPaths consists of all FootPaths that are joined with Connectors , as well as the WorkerPools and the Workplaces that are joined with one of these FootPaths with a Connector .

The time it takes the Worker to walk from his WorkerPool to the Workplace depends on his Speed and the combined Lengths of the FootPaths he covers to reach his destination. Plant Simulation recognizes on which FootPaths the Worker walks if he exits a FootPath at another end than the one at which he entered it. If the Worker does not walk to his destination on a FootPath or if he is beamed directly to his destination, he does not consume any time at all.

The Workers are created in the WorkerPool and they stay there if they do not work and are waiting for a work order.

The Broker brokers the Worker to the individual work stations. As soon as a Worker can provide a service, the Broker sends him from his WorkerPool to the work station that ordered him:

- If you modeled the work station using one of the material flow objects and the Workplace and connected the WorkerPool and the Workplace with a FootPath , Plant Simulation animates the Worker while he walks on the FootPath and while he works on the Workplace .

**Note**

The Worker only consumes time if he walks on the FootPath .

- If you inserted a Workplace , and the Worker , who is supposed to work there, cannot reach it via a FootPath , Plant Simulation beams the Worker directly to the Workplace and animates him there.
- If you do not insert a Workplace , if no Workplace exists that supports this service, or if all Workplaces that support this service are occupied, Plant Simulation beams the Worker to the work station itself, where he will perform his task. Then, the material flow object only shows with an LED in the LED area of its icon that a Worker is working . It does not animate him there, but continues to animate him in the WorkerPool .

You can insert the FootPath into a Frame :

**· In a 3D Only Model**

As a curved object, which is the default setting.

By inserting any sequence of curved segments and straight segments, you can realistically model curved conveyor systems on which the Transporters move.

You can select different configurations for the FootPath on the tab Appearance .

<!-- image -->

**· In a 2D Only Model**

As a curved object, which is the default setting.

With its icon, if you deactivate Curve mode on the Tab Curve by clearing the check box . Then, it looks like this .

To change the Width/height of the icon, open the dialog of the object and type in the Curve width on the tab Curve .

You can control how often the part is shown on the FootPath with the setting Animate every x-th pixel . If you insert the Track with its icon , the Number of Animation Events controls these steps.

To show a tooltip with information about the FootPath , hover with the mouse over it.

Show Manipulators

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

The manipulator at the start and at the end of the length-oriented object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

**Add the Object to the Simulation Model**

To add the FootPath to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; FootPath on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Work with Length-oriented Objects in 2D and 3D

Work with Length-oriented Objects in 3D

Model Workers and the Jobs They Do

Worker -WorkerPool -Workplace -FootPath -concept

Broker - Importer - Exporter -concept

##### Dialog Box of the FootPath

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=eMS1tM55tJ4k9\_ee&amp;t=420](https://youtu.be/Rj5eYZu8pl4?si=eMS1tM55tJ4k9_ee&t=420)

[https://youtu.be/Rj5eYZu8pl4?si=zfQFRHZgC336hXB7&amp;t=1040](https://youtu.be/Rj5eYZu8pl4?si=zfQFRHZgC336hXB7&t=1040)

#### Dialog Box of the FootPath

Dialog Box of the FootPath

Double-click the icon of the FootPath to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides these settings:

Length [text box] - FootPath

Width [text box] - FootPath

###### Length [text box] - FootPath

Type in the Length of the FootPath .

<!-- image -->

After you inserted it, Plant Simulation shows its length here.

The FootPath can accommodate any number of Workers , as they themselves do not have a length. A Worker enters the FootPath at position 0 and exits it after covering the Length you type in.

If TransferLengthToObject is active, Plant Simulation adjusts the graphic if you change the Length of a FootPath which only consists of a single straight segment.

**Note**

You can only type in the Length in pixels in 2D if you deactivate TransferLengthToObject in 2D or if the FootPath consists of a single straight segment.

In 3D, you can change the length of the graphic and the anchor points of the Footpath by clicking Show

Manipulators on the Edit ribbon tab or by clicking M on the keyboard.

<!-- image -->

SimTalk

Length [SimTalk] - FootPath

Width [text box] - FootPath

Type in the Width of the FootPath in meters.

**Note**

You can only type in the Curve Width in pixels in 2D if you deactivate TransferLengthToObject . If you activate it, Plant Simulation computes the Width in meters.

SimTalk

Width [SimTalk] - FootPath

###### Width [text box] - FootPath

##### Tab Curve [FootPath]

Define curved FootPaths for your simulation model as described under the tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Tab Curve [FootPath]**

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object FootPath during a simulation run.

- Click the icon of the FootPath with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] Help Menu [in object dialogs] SimTalk updateDialog [SimTalk] See also View Menu [general description]

##### Tools Menu

Tools Menu provides these menu commands:

The Tools Menu Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the Footpath

Methods of the FootPath

The FootPath provides the Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

#### Read-Only Attributes of the FootPath

Read-Only Attributes of the FootPath

The Exporter provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .

- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyFootPath.UUID
```

**Attributes of the FootPath**

#### \_Attributes of the FootPath

The FootPath provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Curved Objects in 2D .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyFootPath.length := 5
print MyFootPath.length
posit := Station.Cont.XPos
```

##### Length [SimTalk] - FootPath

Sets the physical Length of the Footpath designated by &lt;Path&gt;.

Remarks

A Worker enters the FootPath at position 0 and exits it after covering the length you specify.

Type

Attribute

Syntax

&lt; Path &gt;.Length:length

**Assignment Value**

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

MyFootPath.Length := 44m

See also

Length [text box] - FootPath

##### Width [SimTalk] - FootPath

Width [SimTalk] - FootPath

Sets the Width of the Footpath designated by &lt;Path&gt;.

Remarks

If you deactivate TransferLengthToObject , the Width does not affect how the Footpath is shown in the Frame .

Type

Attribute

Syntax

< Path >.Width:length

Assignment Value

You can assign a value of data type length .

**Note**

In SimTalk 2.0 you can specify the length units m , mm , km , cm , yd , ft , and in .

Type in the unit directly after the values, without a separating blank space, for example 10m or 10.2m .

You can enter the unit for fl oating point values and for integer values .

**Example**

```simtalk
MyFootPath.Width := 2 // meters
```

SimTalk

CurveWidth [SimTalk]

TransferLengthToObject [SimTalk]

See also

Width [text box] - FootPath

Curve Width

#### WorkerPool

