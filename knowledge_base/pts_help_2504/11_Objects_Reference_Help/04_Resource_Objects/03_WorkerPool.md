### WorkerPool

Use the WorkerPool for modeling the lounge or the staff room of your plant.

**Icon**

<!-- image -->

**Description**

The Worker -WorkerPool -Workplace -FootPath -concept refines the Broker -Importer -Exporter-concept. The WorkerPool represents the lounge or the staff room of your plant. The Workers are created in the WorkerPool and they stay there when they do not work and are waiting for an order.

As a rule you type in the Names of the Workers , which you want to use in your simulation model, into the Workers to Create table. You can also drag the Worker from the Class Library onto the icon of the WorkerPool and drop him there. The WorkerPool appends a line to the Workers to Create table for this Worker . When it already contains a line for this Worker , the WorkerPool increments the amount by 1.

You can also create individual Workers , which you do not want to generate via the Workers to Create table, with the method create for a single simulation run. This only works in the WorkerPool though. Be aware that Plant Simulation deletes this Worker when you reset the model and then only creates the Workers from the Workers to Create table at the next Init event that takes place.

You can select the Travel Mode with which the Worker gets to his work station:

<!-- image -->

The Broker brokers the Worker to the individual work stations.

**Note**

If no Broker exists when creating the Workers , Plant Simulation sets the attribute AutomaticMediation of the Workers to false .

As soon as a Worker can provide a service, the Broker sends him from his WorkerPool to the work station that ordered him:

- When the Worker walks freely within the area of the simulation model, he walks on the shortest route to the WorkPlace and walks around obstacles you designated.

The Worker consumes time, when he walks freely within the area to the Workplace .

- When you modeled the work station using one of the material flow objects and the Workplace and connected the WorkerPool and the Workplace with a FootPath , Plant Simulation animates the Worker while he moves on the FootPath and while he works on the Workplace .

The Worker consumes time, when he walks on the FootPath .

- If you activated Beam to workplace and you inserted a Workplace , and the Worker , who is supposed to work there, cannot reach it via a FootPath , Plant Simulation transports the Worker directly to the Workplace and animates him there.
- If you activated Workers can work remotely and if you did not insert a Workplace , if no Workplace exists that supports this service, or if all Workplaces that support this service are occupied, Plant Simulation seemingly beams the Worker to the work station itself, where he will perform his task. Then, the material flow object only shows with an LED in the LED area of its icon that a Worker is working . It does not animate him there, but continues to animate him in the WorkerPool .

If your plant works in shifts, the Worker walks back to his WorkerPool at the end of his shift. He then deposits the parts he could not deliver into the Parts Buffer , which you assigned to the WorkerPool . The parts buffer can be any one of the material flow objects, which accepts parts. When you did not assign a parts buffer to the WorkerPool , Plant Simulation shows a warning and stops the simulation.

If you activated the transport importer in the parts buffer , one of the available Workers carries the parts in the parts buffer to the destination object, after the next shift has started. If you did not activate the transport importer , the parts in the parts buffer are moved on according to the Exit Strategy which you selected for the parts buffer .

The WorkerPool in 3D looks like this:

<!-- image -->

As opposed to 2D the WorkerPool initially does not show any Worker at all in 3D. To see the Workers in 3D, select the check box Show Content on the tab Graphics of the WorkerPool Then click Start Simulation .

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

On the tab MU-Animation you can select to show the Workers in the WorkerPool on an animation path or on an animation area distributed along the Y-dimension .

<!-- image -->

To show a tooltip with information about the WorkerPool , hover with the mouse over it.

To change the length of the graphic and the anchor points of the WorkerPool , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Showing Statistics of the Workers in a Chart

To show statistics of the Workers managed by the WorkerPool , drag it over a Chart and drop it there. Select the settings that you need.

<!-- image -->

Add the Object to the Simulation Model

To add the WorkerPool to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

Resources &gt; WorkerPool on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Show Worker Statistics in a Chart

Model Workers and the Jobs They Do

Worker -WorkerPool -Workplace -FootPath -concept

Broker -Importer -Exporter -concept

#### Dialog Box of the WorkerPool

Dialog Box of the WorkerPool

Double-click the icon of the WorkerPool to open its dialog box.

###### Tab Attributes

**Edit Simulation Properties**

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Workers to Create

To open the table, into which you type information pertaining to the Workers to be created and inserted into your model, click this button.

<!-- image -->

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

This also applies to the Home Location .

- Click the button to deactivate Inheritance . Only then you can enter data into the table.
- Type the class of the Worker , which the WorkerPool uses as a template for the Workers to be created, into the cells below Worker . You might, for example, type in .Resources.Worker or .UserObjects.MyWorker .
- Type the number of the Workers to be created into the cells below Amount .
- Type in the name of a Shift which you defined in the associated Shift calendar .
- If you want the Worker to walk with a different Speed than the one defined in its class, type this speed into the cell below Speed . This deactivates inheritance for the speed, i.e., speed changes in the class will not affect the Workers defined in this row. If you do not type in anything, the Worker walks with the speed specified in the class, meaning he inherits that value from the class.
- Type in the Efficiency of the Workers to be created into the cells below Efficiency . You might, for example, enter 80 for an efficiency of 80 percent.
- Type in the Home Location , i.e., the path to the Workplace to which the Worker walks, once he has finished his current job.
- Type in the Scope , i.e., the path to the material flow objects to which the Worker can be brokered. The scope also encompasses sub-Frames .

<!-- image -->

Proceed as follows:

- Click in the cell Scope of the Worker whose scope you want to set.

- This opens a table with one empty cell.
- Select the object in the Frame to which the Worker can be brokered and drop it into the cell of the table.

<!-- image -->

Press Enter to add another cell and drag the next object to this new cell.

Repeat this as often as necessary.

- Click OK in the table. Plant Simulation then inserts the objects you added to the table into the cell Scope of the Workers to Create table and separates them with a semicolon.
- Click OK in the window of the Workers to Create table.
- Type the services which the Worker can provide, in addition to those you entered into the Services list, into the cells below Additional Services .

<!-- image -->

You can type different types of additional services into the columns to the right of Additional Services . You can also leave gaps between the services in the table. This way you can type in identical services one below the other, even if you want some Workers to not provide these services.

**Note**

The names of the services are not case-sensitive. The WorkerPool attempts to export the services in the order in which you entered them into the table.

**Note**

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators . The change in the Workers to Create table only affects the simulation run if the change takes place before the initialization.

Plant Simulation enters the services you defined here into the list of offered services of the Broker : To view them, select View &gt; Offered Services .

You can also change the Workers to Create table within the Init Control of the WorkerPool for the upcoming simulation run. This is not possible in an init method, as the method is executed too late in time.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

SimTalk AdditionalServices [SimTalk] Amount [SimTalk] - WorkerPool Efficiency [SimTalk] - WorkerPool getWorkersToCreateTable [SimTalk] setWorkersToCreateTable [SimTalk] setServices [SimTalk] - importer Shift [SimTalk] - WorkerPool Speed [SimTalk] - WorkerPool Worker [SimTalk] - WorkerPool See also How the Worker Decides Where to Work Set Home Location and Scope for the Worker Choose the Nearest Worker [check box] Tab Scope Set How Many Workers Are Created During Initialization Init Control [WorkerPool] Context Menu of Embedded Lists GetJobOrdersAtHomeOnly [SimTalk] Video on YouTube https://youtu.be/HiPziA8kxc0?si=qYFCTtAc7V4GzXjQ&amp;t=178

###### Get Job Orders At Home Only

To make the Worker get new job orders for performing a service at a station in the WorkerPool or at his Home Location only, select this check box.

A Worker , who is staying on a Workplace , for which the setting Worker Stays Here After Completing the Job is activated, cannot be brokered in this case. You thus have to clear Worker Stays Here After Completing the Job in all Workplaces so that brokering of the Workers works correctly.

Clear the check box, to allow the Worker to get his job orders anywhere, no matter if he walks freely in the area or if he walks on a FootPath .

SimTalk

GetJobOrdersAtHomeOnly [SimTalk]

See also

Home Location

Worker Stays Here After Completing the Job

WorkerStaysHere [SimTalk]

###### Workers Can Work Remotely [check box]

To make the Worker do his job from his current location, when there is no free Workplace available at the station, to which he was assigned, select this check box.

<!-- image -->

**Note**

You can use this feature to build a model, which does not contain any Workplaces . The Worker will then stay in the WorkerPool the entire time and work from there.

**Note**

When a free Workplace is available, the Worker will use this Workplace , even if you select Workers Can Work Remotely . If you want to prevent a certain service from using a Workplace , you can either use an Exporter or restrict the Workplaces to certain services.

**SimTalk**

**WorkersCanWorkRemotely [SimTalk]**

###### Travel Mode

Travel Mode [drop-down list]

Select the Travel Mode of the Worker from the dropdown list.

<!-- image -->

**· Move freely within area**

The Worker walks freely within the area of the simulation model and walks around Obstacles , which you defined in 3D .

Model a Worker Who Walks Freely Within the Model gives a short introduction to the topic.

- Walk along footpaths

The Worker walks on the Footpaths , which you inserted between the Stations / Workplaces , to the station at which he is going to work.

- Beam to workplace

The Worker is beamed (teleported) to the Workplace to which he was brokered and at which he is going to work instantly, without using up any time at all, provided he cannot get to this Workplace on any Footpath . In this case the Worker functions as an Exporter with a capacity of 1.

You can use Beam to workplace to build a model which does not contain any FootPaths . The Worker then always jumps between the WorkerPool and the Workplaces .

**Note**

The Travel Mode is only transmitted from the WorkerPool to the Workers when they are created. The Travel Mode will not be changed after the Workers are created.

SimTalk

WorkersTravelMode [SimTalk]

See also

Set How Many Workers Are Created During Initialization

Model a Worker Who Walks Freely Within the Model

Edit 3D Properties [dialog] &gt; Graphics [tab, 3D] &gt; Obstacle for the Worker [drop-down list] in 3D

Edit 3D Properties [dialog] &gt; Graphic Settings in 3D

Barred Area in 3D

**Move freely within area**

**Move freely within area**

Makes the Worker walk freely within the area of the simulation model and walks around the obstacles , which you defined in 3D .

<!-- image -->

Plant Simulation automatically computes the shortest route between the WorkPlaces and between the WorkerPool and the WorkPlaces . It uses the layout of the 3D model to compute the shortest route to a WorkPlace . The 2D layout is irrelevant. Once you activate the freely walking Worker , Plant Simulation prompts you to start 3D .

**Note**

We use the 3D layout to compute the route as the 3D model normally represents the looks of your facility more closely, meaning that the position, the dimensions, and the orientation of the machines and the fixtures of the building closely match the real plant. Although the 2D objects normally are located at the same coordinates as the simulation objects, they normally do not have the same orientation and size as the 2D model uses object icons to represent the simulation objects.

To compute the shortest route, Plant Simulation uses information about those areas of the model, which the Worker cannot walk on or cross. These areas encompass all kinds of obstacles, for example walls, pillars, machines, conveyors, safety fences, etc. Plant Simulation automatically detects these areas. By default, we marked the material flow objects , the animatable objects , and the graphics , which belong to the Frame , as Barred Areas . Information flow objects and user interface objects by default are not Barred Areas . You can set if an object as an obstacle for the Worker under Edit 3D Properties &gt; Tab Graphics &gt; Obstacle for the Worker . For graphics, you can do this under Edit 3D Properties &gt; Tab Graphic Settings , for example to allow the Worker to cross a Track . MUs do not provide this setting.

<!-- image -->

All settings, except for None automatically create a barred area.

To designate an area in the plant, which the Worker can enter, but should not, for example the pivoting area of a crane, you can manually create a Barred Area in 3D .

To allow the Worker to walk around or through obstacles, use a FootPath . Let's say that you want your Worker to walk through a door which in part of a wall that you defined as an obstacle. Then you can lay a FootPath through the door on which he can walk through it. The FootPath always has to be a little longer than the depth of the wall.

For the FootPath not the length, which you type in on the tab Attributes is decisive, but the Length of the FootPath in the 3D scene. The distance covered of the Worker is determined by the starting point and the end point of the FootPath as well by the anchor points.

If the FootPath includes an incline , the Worker moves slower on the incline than on a flat surface. Plant Simulation achieves this by extending the imagined distance for the incline segments. When computing the length of an inclined segment, Plant Simulation triples the height difference.

Compare this example : A segment of a FootPath has a dimension of 1 m in the x-direction and 1 m in the z-direction, thus actually is 1.414 m long. The imagined dimension however is 1 m in the x-direction and 3 m in z-direction, so that Plant Simulation computes an effective length of 3.162 m.

The Worker always walks on the route, which has the shortest effective length and which he can thus cover in the shortest time. This can cause the Worker to take an actually longer but flatter route to the destination instead of a shorter route which contains inclines and gradients.

For computing the effective route length Plant Simulation triples the height difference. The resulting speeds of the Worker are realistic in general. The speed of the Worker decreases to a third, when the Worker moves vertically up or down, for example when climbing a ladder . The speed decreases to about half, when the Worker negotiates an incline of 38 degrees, for example a when walking on a stairway .

**Note**

The Worker walks slower on an incline than he walks on a flat surface.

**Note**

When the Worker walks freely within the area , he can only get to a different floor in the building by walking up or down a ramp on a Footpath or walking up and down Stairs .

The example model Factory 51 demonstrates how you can use Stairways .

**Move freely within area**

<!-- image -->

SimTalk

WorkersTravelMode [SimTalk]

See also

Obstacle for the Worker [drop-down list]

Model a Worker Who Waits in Line

Model a Worker Who Walks Freely Within the Model

Set How Many Workers Are Created During Initialization

How the Worker Decides Where to Work

Set Home Location and Scope for the Worker

Choose the Nearest Worker [check box]

Edit 3D Properties &gt; Tab Graphics &gt; Obstacle for the Worker in 3D

Edit 3D Properties &gt; Tab Graphic Settings in 3D

Barred Area in 3D

**Back to**

**Travel Mode [drop-down list]**

**Walk along footpaths**

**Walk along footpaths**

Makes the Worker walk on the Footpaths , which you inserted between the Stations/Workplaces , to the station at which he is going to work.

To model and to simulate the distances between the WorkerPool and the work stations or between the work stations, insert FootPaths . Plant Simulation animates the Workers on the FootPaths when they walk toward the work stations or when they walk between the stations.

<!-- image -->

You can link several FootPaths with Connectors to create a network of FootPaths . The Worker walks within this network from his WorkerPool to the Workplace . Provided the WorkerPool and the Workplace are connected to the same network of FootPaths , the Worker walks from the WorkerPool to the Workplace and back on the shortest possible route.

A network of FootPaths consists of all FootPaths that are joined with Connectors , as well as the WorkerPools and the Workplaces that are joined with one of these FootPaths with a Connector .

The time it takes the Worker to walk from his WorkerPool to the Workplace depends on his Speed and the combined Lengths of the FootPaths he covers to reach his destination. Plant Simulation recognizes on which FootPaths the Worker walks if he exits a FootPath at another end than the one at which he entered it. If the Worker does not walk to his destination on a FootPath or if he is beamed to his destination, he does not consume any time at all.

SimTalk

WorkersTravelMode [SimTalk]

See also

Set How Many Workers Are Created During Initialization

Edit 3D Properties &gt; Tab Graphics &gt; Obstacle for the Worker in 3D

Edit 3D Properties &gt; Tab Graphic Settings in 3D

Barred Area in 3D

Back to

Travel Mode [drop-down list]

**Beam to workplace**

Beams (teleports) the Worker to the Workplace to which he was brokered and at which he is going to work instantly, without using up any time at all, provided he cannot get to this Workplace on any Footpath .

<!-- image -->

For this setting the Worker functions as an Exporter with a capacity of 1.

You can use Beam to workplace to build a model which does not contain any FootPaths . The Worker then always jumps between the WorkerPool and the Workplaces .

**SimTalk**

WorkersTravelMode [SimTalk]

teleportTo [SimTalk]

teleportToHome [SimTalk]

teleportToPool [SimTalk]

See also

Exporter [object]

Set How Many Workers Are Created During Initialization

Model a Worker Who Walks Freely Within the Model

Edit 3D Properties &gt; Tab Graphics &gt; Obstacle for the Worker in 3D

Edit 3D Properties &gt; Tab Graphic Settings in 3D

Barred Area in 3D

Back to

Travel Mode [drop-down list]

###### Broker [WorkerPool]

Broker [WorkerPool]

Click the ellipsis button and select the Broker , who assigns the services to the Worker , in the dialog Select Object .

<!-- image -->

Or type in the path to and the name of the Broker . You might, for example, type in .Models.Model.MyBroker .

Or select the Broker in a Frame , drag it to the text box and drop it there.

**Note**

To open the dialog of the object, whose name you typed into the text box, press F2 .

SimTalk

BrokerPath [SimTalk] - WorkerPool

See also

Broker [object]

Select Object [for controls]

###### Shift Calendar [WorkerPool]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the WorkerPool works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the objects into the list of the objects on the tab Resources of the ShiftCalendar .

If the Workers , which the WorkerPool manages, works in shifts, you also have to select the Parts Buffer . The Worker deposits the parts, which he could not deliver, onto this object, when he walks back to the WorkerPool at the end of his shift.

SimTalk

ShiftCalendarObject [SimTalk] - material flow objects

See also

ShiftCalendar [object]

Select Object [for controls]

**Parts Buffer [text box]**

###### Parts Buffer [text box]

Click the ellipsis button and select the Parts Buffer into which the Worker deposits the parts he could not deliver, when he walks back to the WorkerPool at the end of his shift.

You can also drag a material flow object onto the picture of the WorkerPool in your model Frame and drop it there to use it as the Parts Buffer .

The Parts Buffer can be any one of the material flow objects, which accepts parts. If you did not assign a parts buffer to the WorkerPool , and a Worker arrives with parts at the end of its shift in the WorkerPool , Plant Simulation shows a warning and stops the simulation.

If you activated the transport importer of the Parts Buffer , one of the available Workers carries the parts in the Parts Buffer to the destination object, after the next shift has started. If you did not activate the transport importer , the parts in the Parts Buffer are moved on according to the Exit Strategy which you selected for the Parts Buffer .

**Note**

This setting only applies, when you control the shifts worked in your facility with the Shift Calendar [WorkerPool] .

SimTalk

PartsBuffer [SimTalk]

##### Tab Statistics [WorkerPool]

Plant Simulation shows the most important statistics values on the tab Statistics .

| Item English              | Description                                                                                                                                                         | Read-only attribute                                 | Item German                               |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------|
| Paused                    | Shows the portion of the statistics collection period during which the WorkerPool was paused                                                                        | StatPausingCount [SimTalk]                          | Pausiert                                  |
| Unplanned                 | Shows the portion of the statistics collection period during which the WorkerPool was unplanned, i.e., is not scheduled to work to the statistics collection period | StatUnplannedPortion [SimTalk]                      | Ungeplant                                 |
| Average Traveled Distance | Shows the average distance in meters which the Worker traveled from the WorkerPool to the Workplaces attached to the stations and between the stations              | StatAverageTraveledD istance [SimTalk] - WorkerPool | Durchschnittlich zurückgelegte Wegstrecke |

For information about the other values on this tab, compare the Tab Statistics of the Worker .

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object.

You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Resource Statistics [check box]

**Resource Type**

###### Tab Statistics [Worker]

Tab Controls

Tab Controls [WorkerPool]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , and a Set-up Control .

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**See also Entrance Control [WorkerPool]**

**Exit Control [WorkerPool]**

###### Entrance Control [WorkerPool]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Entrance Control , which is called as soon as the Worker has entered the WorkerPool .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

EntranceCtrl [SimTalk] - WorkerPool

**See also**

**Select Object [for controls]**

**Exit Control [WorkerPool]**

###### Exit Control [WorkerPool]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Exit Control , which is called once the Worker has left the WorkerPool .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

ExitCtrl [SimTalk] - WorkerPool

See also

Select Object [for controls]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu [WorkerPool]

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Working Workers [WorkerPool]   |
|--------------------------------------------|--------------------------------|
| Show Statistics Report [on View menu]      | Associated Lockout Zones       |
| Show Attributes and Methods [on View menu] | Associated Shift Calendar      |
| Assigned Workers [WorkerPool]              | Working Workers [WorkerPool]   |
| Refresh [on View menu]                     |                                |

See also

View Menu [general description]

**Assigned Workers [WorkerPool]**

###### Assigned Workers [WorkerPool]

Opens a list, which shows all Workers for which the WorkerPool provides services.

<!-- image -->

###### Working Workers [WorkerPool]

Opens a list, which shows information pertaining to the working workers.

- The Worker who provides a service or carries parts.
- The Location , i.e., the object on which the Worker is located at the moment. For a Worker walking freely in the area, the WorkerPool is shown here.
- The Target station at which the Worker is to provide the service or carry the part to.
- The Service which the Worker currently provides. If the Worker carries parts, this is the service that was provided while loading the part.

<!-- image -->

**SimTalk**

getWorkingWorkersTable [SimTalk]

Tools Menu

Tools Menu

The Tools Menu provides these menu commands:

Edit Controls &gt; Init control

Edit Observers

3D

**Init Control [WorkerPool]**

###### Init Control [WorkerPool]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Init Control , which is called at the start of the simulation run during the init phase.

<!-- image -->

The Init Controls are called before the events are computed. The normal init methods on the other hand are executed after the initial events have been computed.

Within the Init Control you can, for example, change the Workers to Create table of the WorkerPool for the next simulation run. This cannot be accomplished in an init method as this method would be called too late in time.

You can also initialize attributes which affect event generation, for example the availability. Here the Init Controls are executed before events are computed. The normal init methods are executed after the initial events have been computed.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

You can also create a control which is a user-defined attribute of data type Method . To do so, right-click in the text box and select Create Control . This might look like this:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.ExitControlEnginePlant .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .

- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute; deleting the name from the text box just deletes the name, but keeps the user-defined attribute.

**SimTalk**

InitCtrl [SimTalk] - WorkerPool

See also

Select Object [for controls]

##### Help Menu

The commands are described under the Help Menu .

**Methods of the WorkerPool**

#### \_Methods of the WorkerPool

The WorkerPool provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

```simtalk
< Path >.openDialog([CallOpenControl:boolean:=false]) → boolean
```

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

getAssignedWorker [SimTalk]

Returns the assigned Worker designated by the number in the WorkerPool designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getAssignedWorker(No:integer)
-> object
```

Parameter

The parameter No of data type integer designates the number of the Worker that is assigned.

Return Value

The return value has the data type object .

Example

```simtalk
print MyWorkerPool.getAssignedWorker(2) -- might, for example,
return .Resources.John:2
```

See also

Assigned Workers [WorkerPool]

##### getAssignedWorkersTable [SimTalk]

Returns the table that contains the assigned Workers of the WorkerPool designated by &lt;Path&gt;.

Syntax

&lt; Path &gt;.getAssignedWorkersTable([AssignedWorkers:table]) -&gt; any

Type

Method

Parameter

The optional parameter AssignedWorkers of data type table designates the name of the table into which the Workers will be written.

If you do not specify the optional parameter, Plant Simulation returns an array with the assigned Workers .

Return Value

The return value has the data type any .

Example

MyWorkerPool.getAssignedWorkersTable(MyAssignedWorkersTable) MyWorkerPool.getAssignedWorkersTable

See also

Assigned Workers [WorkerPool]

##### getIdleWorker [SimTalk]

Returns the first idle Worker in the WorkerPool designated by &lt;Path&gt;.

Remarks

getIdleWorker returns the first idle Worker for whom the attribute IsIdle is to true and sets it to false. When you no longer need the Worker , you can send the Worker to the WorkerPool and set IsIdle to true .

Type

Method

Syntax

&lt; Path &gt;.getIdleWorker -&gt; object

Return Value

The return value has the data type object .

Is the first idle Worker in the WorkerPool .

VOID if no Worker is idle.

Example

.Resources.WorkerPool.getIdleWorker

SimTalk

IsIdle [SimTalk] - Worker

NumIdleWorkers [SimTalk]

##### getWorkersToCreateTable [SimTalk]

Returns the Workers to Create table of the WorkerPool designated by &lt;Path&gt; and writes it into a table.

Remarks

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

This also applies to the Home Location .

Type

Method

Syntax

```simtalk
< Path >.getWorkersToCreateTable(WorkersToCreateTable:table/void[, byref Inherited:boolean])
```

**Parameters**

- The parameter WorkersToCreateTable of data type table designates the name of the table that contains the Workers to be created. The column of the table has to have the data type table .

If the optional parameter Inherited is passed, you can specify VOID for the parameter WorkersToCreateTable . In this case WorkersToCreateTable is ignored.

- The optional parameter Inherited designates a local variable of data type boolean which is set to true if the WorkersToCreateTable of the WorkerPool is inherited. It is set to false if it is not inherited.

**Example**

```simtalk
var rt: table                             // read the Workers to Create table
MyWorkerPool.getWorkersToCreateTable(rt)  // set the new amount rt [2,1]:= AmountOfWorkers                // name of a Variable // assign the Workers to Create table to the WorkerPool
MyWorkerPool.setWorkersToCreateTable(rt)
```

**SimTalk**

setWorkersToCreateTable [SimTalk]

getWorkersToCreateTableRow [SimTalk] - WorkerPool See also Workers to Create Home Location Tab Scope The Relative Path

##### getWorkersToCreateTableRow [SimTalk] - WorkerPool

The sub-attributes of the method getWorkersToCreateTableRow set and get the individual settings of the Workers to Create table of the WorkerPool designated by &lt;Path&gt;.

**Remarks**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

This also applies to the Home Location .

Type

Method

Syntax

```simtalk
< Path >.getWorkersToCreateTableRow(row:integer).AdditionalServices:string[] < Path >.getWorkersToCreateTableRow(row:integer).Amount:integer < Path >.getWorkersToCreateTableRow(row:integer).Efficiency:real < Path >.getWorkersToCreateTableRow(row:integer).HomeLocation:path < Path >.getWorkersToCreateTableRow(row:integer).Scope:array < Path >.getWorkersToCreateTableRow(row:integer).Shift:string < Path >.getWorkersToCreateTableRow(row:integer).Speed:speed < Path >.getWorkersToCreateTableRow(row:integer).Worker:object
```

**Parameters**

- The parameter row of data type integer designates the row in the Workers to Create table in which you would like to set the attribute.
- The parameter AdditionalServices is an array of data type string containing the additional services that the Worker can provide.
- The parameter Amount of data type integer designates the number of Workers that are going to be created.
- The parameter Efficiency of data type real designates the efficiency of the Worker .

<!-- image -->

- The parameter HomeLocation of data type path designates the path to the Workplace to which the Worker walks once he has finished his current job.
- The parameter Scope of data type array designates the path to the material flow objects to which the Worker can be brokered. The scope also encompasses sub-Frames .
- The parameter Shift of data type string designates the shift during which the Worker works. You define the shift itself in the assigned ShiftCalendar .
- The parameter Speed of data type speed designates the speed with which the Worker walks.
- The parameter Worker of data type object sets the class of the Worker which the WorkerPool uses as the template for the Workers to be created.

**Example**

```simtalk
MyWorkerPool.getWorkersToCreateTableRow(1).AdditionalServices := ["drill1", "drill2", "drill3"]
```

**SimTalk**

getWorkersToCreateTableRow. AdditionalServices [SimTalk]

getWorkersToCreateTableRow. Amount [SimTalk] - WorkerPool

getWorkersToCreateTableRow. Efficiency [SimTalk] - WorkerPool

getWorkersToCreateTableRow. HomeLocation [SimTalk] - WorkerPool

getWorkersToCreateTableRow. Scope [SimTalk] - WorkerPool

getWorkersToCreateTableRow. Shift [SimTalk] - WorkerPool

getWorkersToCreateTableRow. Speed [SimTalk] - WorkerPool

getWorkersToCreateTableRow. Worker [SimTalk] - WorkerPool

getWorkersToCreateTable [SimTalk]

setWorkersToCreateTable [SimTalk]

See also

Workers to Create

Tab Scope

Home Location

**The Relative Path**

getWorkingWorkersTable [SimTalk]

Returns the table that contains the working Workers of the WorkerPool designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.getWorkingWorkersTable(WorkingWorkers:table)

Parameter

The parameter WorkingWorkers of data type table designates the name of the table into which the working Workers will be written.

Example

MyWorkerPool.getWorkingWorkersTable(MyWorkingWorkers)

See also

Working Workers [WorkerPool]

##### setWorkersToCreateTable [SimTalk]

Sets the name of the Workers to Create table for the Workers of the WorkerPool designated by &lt;Path&gt;.

**Remarks**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

This also applies to the Home Location .

Type

Method

Syntax

&lt; Path &gt;.setWorkersToCreateTable(WorkersToCreateTable:table/void)

**Parameter**

Specify void for the parameter to activate inheritance of the Workers to Create table in the WorkerPool instead of filling the table with the Workers that you entered into the table.

**Note**

To apply the changes to the Workers to Create table to the simulation run, the change has to occur before the model is initialized.

The parameter WorkersToCreateTable of data type table designates the Workers to Create table . Enter the Names of the Workers to be created, the name of the Shift , their Amount , their Speed , their Efficiency , their Home Location , their Scope , and Additional Services into the table.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

**Examples**

MyWorkerPool.setWorkersToCreateTable(MyWorkersToCreateTable)

```simtalk
var rt: table                                // read the Workers to Create table
MyWorkerPool.getWorkersToCreateTableRow(rt)  // set the new amount rt [2,1]:= AmountOfWorkers                   // name of a Variable // assign the Workers to Create table // to the WorkerPool
MyWorkerPool.setWorkersToCreateTable(rt)
```

SimTalk

getWorkersToCreateTable [SimTalk]

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create

Tab Scope

Home Location

The Relative Path

Relational Operators

#### Read-Only Attributes of the WorkerPool

\_Read-Only Attributes of the WorkerPool

The WorkerPool provides these read-only attributes:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyWorkerPool.StatAverageTraveledDistance NumAssignedWorkers [SimTalk]

Returns the amount of Workers which the WorkerPool designated by &lt;Path&gt; assigned.

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumAssignedWorkers -&gt; integer

Return Value

The return value has the data type integer .

Example

print MyWorkerPool.NumAssignedWorkers

SimTalk

getAssignedWorkersTable [SimTalk]

getAssignedWorker [SimTalk]

##### NumIdleWorkers [SimTalk]

Returns the number of Workers in the WorkerPool designated by &lt;Path&gt; who are idle, i.e., not working.

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumIdleWorkers -&gt; integer

Watchable

The attribute is watchable .

Return Value

The return value has the data type integer .

Example

```simtalk
waituntil WorkerPool.NumidleWorkers > 0
var worker:object := WorkerPool.getIdleWorker
```

SimTalk

IsIdle [SimTalk] - Worker

getIdleWorker [SimTalk]

##### StatAverageTraveledDistance [SimTalk] - WorkerPool

Returns the average distance in meters which the Worker traveled from the WorkerPool designated by &lt;Path&gt; to the Workplaces attached to the stations and between the stations .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatAverageTraveledDistance → length

Return Value

The return value has the data type length .

Example

print MyWorkerPool.StatAverageTraveledDistance

#### Attributes of the WorkerPool

\_Attributes of the WorkerPool

The WorkerPool provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyWorkerPool.BrokerPath := mybroker
print MyWorkerPool.BrokerPath
posit := Station.Cont.XPos
```

**AdditionalServices [SimTalk]**

##### AdditionalServices [SimTalk]

Sets the additional services, which the Worker provides, in the Workers to Create table of the WorkerPool designated by &lt;Path&gt;.

Remarks

Plant Simulation addresses the attribute AdditionalServices as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

```simtalk
< Path >.getWorkersToCreateTableRow(Row:integer).AdditionalServices:string[]
```

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter AdditionalServices is an array of data type string which contains the additional services that the Worker can execute.

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyWorkerPool.getWorkersToCreateTableRow(1).AdditionalServices := ["drill1", "drill2", "drill3"]
```

**SimTalk**

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create

##### Amount [SimTalk] - WorkerPool

Sets how many Workers the Workers to Create table of the WorkerPool designated by &lt;Path&gt; creates.

**Remarks**

Plant Simulation addresses the attribute Amount as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Amount:integer

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Amount of data type integer sets the number of Workers that is going to be created.

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyWorkerPool.getWorkersToCreateTableRow(1).Amount := 2
```

**SimTalk**

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create BrokerPath [SimTalk] - WorkerPool Sets the path to the Broker , which the WorkerPool designated by &lt;Path&gt; uses to provide the services.

Type

Attribute

Syntax

&lt; Path &gt;.BrokerPath:object

Assignment Value

You can assign a value of data type object .

Example

```simtalk
print MyWorkerPool.BrokerPath
MyWorkerPool.BrokerPath := myBroker
MyWorkerPool.BrokerPath := Broker3
```

See also

Broker [WorkerPool]

**Efficiency [SimTalk] - WorkerPool**

Sets the efficiency of Workers which the Workers to Create table of the WorkerPool designated by &lt;Path&gt; creates.

**Remarks**

Plant Simulation addresses the attribute Efficiency as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Efficiency:real

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Efficiency of data type real sets how fast the Worker executes the jobs.
- With an Efficiency of 100 percent the Worker consumes the exact processing time which you specified.
- With an Efficiency of 200 percent he consumes half of the processing time which you specified.
- With an Efficiency of 50 percent he consumes twice the processing time which you specified.

**Assignment Value**

You can assign a value of data type real .

**Example**

MyWorkerPool.getWorkersToCreateTableRow(1).Efficiency := 75

**SimTalk**

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create

##### EntranceCtrl [SimTalk] - WorkerPool

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as the Worker has entered the WorkerPool designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.EntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyWorkerPool.EntranceCtrl := &amp;myEntranceCtrl

See also

Entrance Control [WorkerPool]

##### ExitCtrl [SimTalk] - WorkerPool

ExitCtrl [SimTalk] - WorkerPool

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as the Worker exits the WorkerPool

Type

Attribute

Syntax

&lt; Path &gt;.ExitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyWorkerPool.ExitCtrl := &amp;myExitControl

See also

Exit Control [WorkerPool]

##### GetJobOrdersAtHomeOnly [SimTalk]

Sets if the Worker gets new job orders for performing a service at a station in the WorkerPool designated by &lt;Path&gt; or at the Home Location only ( true ).

Remarks

Specify false if you want to assign new job orders to the Worker anywhere, no matter if he walks freely in the area or if he walks on a FootPath .

A Worker , who is staying on a Workplace , for which the setting Worker Stays Here After Completing the Job is activated, cannot be brokered in this case. You thus have to clear Worker Stays Here After Completing the Job in all Workplaces so that brokering the Workers works correctly.

Type

Attribute

Syntax

&lt; Path &gt;.GetJobOrdersAtHomeOnly:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyWorkerPool.GetJobOrdersAtHomeOnly := false

SimTalk

WorkerStaysHere [SimTalk]

HomeLocation [SimTalk] - Worker

See also

Get Job Orders At Home Only

Worker Stays Here After Completing the Job

##### HomeLocation [SimTalk] - WorkerPool

Sets the path to the Home Location , i.e., the Workplace to which the Worker walks, once he has finished his current job, in the Workers to Create table of the WorkerPool designated by &lt;Path&gt;.

**Remarks**

Plant Simulation transfers Workers , for whom you defined a Home Location and a Shift in the Workers to Create table of the WorkerPool , to the defined Home Location at the start of the Shift . They then start walking to the respective Workplace from there.

At the end of the shift Plant Simulation transfers all Workers of this shift directly to the WorkerPool , they do not walk back to the WorkerPool .

Plant Simulation transfers Workers , for whom you defined a Home Location but no Shift , to the defined Home Location at the start of the simulation.

**Note**

Plant Simulation addresses the attribute HomeLocation as sub-attribute of the method getWorkersToCreateTableRow .

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(row:integer).HomeLocation:path

Assignment Value

You can assign a value of data type object .

Example

WorkerPool.getWorkersToCreateTableRow(1).HomeLocation := HomeLocationWP print WorkerPool.getWorkersToCreateTableRow(1).HomeLocation // returns HomeLocationWP

SimTalk

**getWorkersToCreateTableRow [SimTalk] - WorkerPool See also Workers to Create The Relative Path**

InitCtrl [SimTalk] - WorkerPool

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method once at the beginning of the simulation run during the init phase for the WorkerPool designated by &lt;Path&gt; before the objects are initialized, and before init methods are executed.

You can also initialize attributes which affect the generation of events, such as the Availability . To accomplish this the init controls are executed before the events are computed. The normal init methods are executed after the initial events have been executed.

Within the Init Control you can, for example, change the Workers to Create table of the WorkerPool for the next simulation run. This cannot be accomplished in an init method as this method would be called too late in time.

Type

Attribute

Syntax

&lt; Path &gt;.InitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyWorkerPool.InitCtrl := &amp;myInitControl

SimTalk

init [SimTalk] - predefined name

See also

Init Control [WorkerPool]

Workers to Create

##### PartsBuffer [SimTalk]

Sets the path to the object into which the Worker deposits the parts he could not deliver, when he walks back to the WorkerPool designated by &lt;Path&gt; at the end of his shift.

Remarks

The parts buffer can be any one of the material flow objects, which accepts parts. If you did not assign a parts buffer to the WorkerPool , and a Worker arrives with parts at the end of its shift in the WorkerPool , Plant Simulation shows a warning and stops the simulation.

If you activated the transport importer in the parts buffer , one of the available Workers carries the parts in the parts buffer to the destination object, after the next shift has started. If you did not activate the transport importer , the parts in the parts buffer are moved on according to the Exit Strategy which you selected for the parts buffer .

Type

Attribute

Syntax

&lt; Path &gt;.PartsBuffer:object

Assignment Value

You can assign a value of data type object .

Example

print Myworkerpool.PartsBuffer MyWorkerPool.PartsBuffer := MyPartsBuffer

See also

Parts Buffer [text box]

##### Scope [SimTalk] - WorkerPool

##### Scope [SimTalk] - WorkerPool

Sets the path to the material flow objects to which the Worker can be brokered in the Workers to Create table of the WorkerPool designated by &lt;Path&gt;. The scope also encompasses sub-Frames .

Remarks

Plant Simulation addresses the attribute Scope as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Scope:string[]

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Scope is an array of data type string which contains the paths of the objects within the scope separated by semicolons.

Assignment Value

You can assign an array of data type string .

**Examples**

```simtalk
// gets the scope
var Scope:object[] := MyWorkerPool.getWorkersToCreateTableRow(1).Scope
// sets the scope
MyWorkerPool.getWorkersToCreateTableRow(1).Scope := [ path1, path2, … ] // assigns the scope
MyWorkerPool.getWorkersToCreateTableRow(1).Scope := []   // deletes the scope
MyWorkerPool.getWorkersToCreateTableRow(1).Scope := void // deletes the scope
MyWorkerPool.getWorkersToCreateTableRow(1).Scope := path // allows the scope to contain a path // Example 3, accesses a column in the Workers to Create table
var t:table := MyWorkerPool.getWorkersToCreateTableRow()print t["Scope",
1] //results in paths separated by semicolons
var Scope:
string[] := splitString(t["Scope", 1], ";") // gets and splits the paths containing semicolons
print Scope // prints an array of paths t["Scope", 1] =
Scope.join(";")
```

**SimTalk**

**getWorkersToCreateTableRow [SimTalk] - WorkerPool**

See also

Workers to Create

##### Shift [SimTalk] - WorkerPool

Sets the shift, during which the Workers work, in the Workers to Create table of the WorkerPool designated by &lt;Path&gt;.

Remarks

Plant Simulation addresses the attribute Shift as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Shift:string

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Shift of data type string designates the shift during which the Worker works. Define the shift in the assigned ShiftCalendar .

Assignment Value

You can assign a value of data type string .

Example

MyWorkerPool.getWorkersToCreateTableRow(1).Efficiency := "My Shift"

SimTalk

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create

##### Speed [SimTalk] - WorkerPool

Sets the speed, with which the Workers in the model walk, in the Workers to Create table of the WorkerPool designated by &lt;Path&gt;.

Remarks

Plant Simulation addresses the attribute Speed as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Speed:speed

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Speed of data type speed designates the speed with which the Workers walk on FootPaths .

Assignment Value

You can assign a value of data type speed .

**Note**

In SimTalk 2.0 you can specify the speed units mps , fps , kmh , and mph .

Type in the unit directly after the number, without a separating blank space, for example 100kmh or 100.5kmh .

```simtalk
var len := 1.0ft
var s : speed := 10.5m / 1:30
var x : length := 3m
```

**Note**

In SimTalk 2.0 you can enter the unit s for seconds . Enter the unit s directly after the number, without a separating blank space. Entering the unit sometimes is necessary to make sure that the computed expression has the correct data type.

```simtalk
var x : length := 10m
var s : speed := x / 2s   // Beware: x/2 would have the wrong unit, m instead of m/s
```

**Example**

```simtalk
MyWorkerPool.getWorkersToCreateTableRow(1).Speed := 3.14
```

SimTalk

**getWorkersToCreateTableRow [SimTalk] - WorkerPool**

See also

Workers to Create

##### Worker [SimTalk] - WorkerPool

Sets the class of the Workers which the Workers to Create table of the WorkerPool designated by &lt;Path&gt; creates.

**Remarks**

Plant Simulation addresses the attribute Worker as sub-attribute of the method getWorkersToCreateTableRow .

Type

Sub-attribute

Syntax

&lt; Path &gt;.getWorkersToCreateTableRow(Row:integer).Worker:object

**Parameters**

- The parameter Row of data type integer designates the row in the Workers to Create table in which you are going to set the attribute.
- The parameter Worker of data type object sets the class of the Workers which the WorkerPool uses as a template for creating Workers

Assignment Value

You can assign a value of data type object .

Example

MyWorkerPool.getWorkersToCreateTableRow(1).Worker := .UserObjects.MyWorker

SimTalk

getWorkersToCreateTableRow [SimTalk] - WorkerPool

See also

Workers to Create

##### WorkersCanWorkRemotely [SimTalk]

Sets if the Worker managed by the WorkerPool designated by &lt;Path&gt; will do the job from his current location, when no free Workplace is available at the station to which he was assigned ( true ) or not ( false ).

Remarks

**Note**

You can use WorkersCanWorkRemotely to build a model, which does not contain any Workplaces . The Worker will then stay in the WorkerPool the entire time and work from there.

**Note**

When a free Workplace is available, the Worker will use this Workplace , even if you set WorkersCanWorkRemotely to true . If you want to prevent a certain service from using a Workplace , you can either use an Exporter or restrict the Workplaces to certain services.

Type

Attribute

Syntax

&lt; Path &gt;.WorkersCanWorkRemotely:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyWorkerPool.WorkersCanWorkRemotely := false

See also

Workers Can Work Remotely [check box]

##### WorkersTravelMode [SimTalk]

Sets how the Worker who is managed by the WorkerPool designated by &lt;Path&gt; moves in the simulation model.

Remarks

The WorkersTravelMode will only be transmitted from the WorkerPool to the Workers when they are created, meaning that it will not be changed after the Workers are created.

Type

Attribute

Syntax

**&lt; Path &gt;.WorkersTravelMode:string**

Assignment Value

You can assign a value of data type string .

You can specify:

- "Move freely within area"

The Worker walks freely within the area of the simulation model and walks around obstacles, which you defined in 3D .

- "Walk along footpaths"

The Worker walks on the Footpaths , which you inserted between the Stations / Workplaces , to the station at which he is going to work.

- "Beam to workplace"

The Worker is beamed (teleported) to the Workplace to which he was brokered and at which he is going to work instantly, without using up any time, provided he cannot get to this Workplace on any FootPath .

**Note**

You can use the feature Beam to workplace to build a model, in which you do not want to simulate the Worker walking. The Worker then always jumps between the WorkerPool and the Workplaces .

**Example**

MyWorkerPool.WorkersTravelMode := "Move freely within area"

