### Worker

**See also**

Travel Mode [drop-down list] &gt; Move freely within area

Travel Mode [drop-down list] &gt; Walk along footpaths

Travel Mode [drop-down list] &gt; Beam to workplace

**Worker**

#### Worker [object]

Use the Worker for doing a job on a Workplace at a station.

Icon

<!-- image -->

**Description**

The Worker -WorkerPool -Workplace -FootPath -concept refines the Broker -Importer -Exporter -concept.

As opposed to the Exporter , the Worker consumes time when walking to the Workplace at which he does his job. The Worker has the same statistics values as the Exporter , and in addition provides a statistics value for being En-route to the Job .

If your Worker does not walk, make sure that the importer on the tab Importer of the station is activated, on whose Workplace the Worker is to work.

In the WorkerPool you can select the Travel Mode with which the Worker gets to his work station:

<!-- image -->

**· Move freely within area**

The Worker walks freely within the area of the simulation model and walks around obstacles , which you defined in 3D .

Model a Worker Who Walks Freely Within the Model gives a short introduction to the topic.

- Walk along footpaths

The Worker walks on the Footpaths , which you inserted between the Stations / Workplaces , to the station at which he is going to work.

**· Beam to workplace**

The Worker is beamed (teleported) to the Workplace to which he was brokered and at which he is going to work instantly, without using up any time at all, provided he cannot get to this Workplace on any Footpath . In this case the Worker functions as an Exporter with a capacity of 1.

You can use Beam to workplace to build a model which does not contain any FootPaths . The Worker then always jumps between the WorkerPool and the Workplaces .

You can also set the Loading Time and the Unloading Time , which the Worker needs for manually loading and unloading the station, in the Workplace attached to the station.

The Workers are created in the WorkerPool and they stay there if they do not work and are waiting for a work order. As a rule you type in names of the Workers , which you want to use in your simulation model, into the Workers to Create table. You can also drag a single Worker or any number of Workers from the Class Library onto the icon of the WorkerPool and drop them there. The WorkerPool appends a row to the Workers to Create table for this Worker . If it already contains a line for this Worker , the WorkerPool increments the amount by 1.

You can also create individual Workers , which you do not want to generate via the Workers to Create table, with the method create for a single simulation run. This only works in the WorkerPool though. Be aware that Plant Simulation deletes this Worker when you reset the model and then only creates the Workers from the Workers to Create table at the next Init event that takes place.

The Broker brokers the Workers to the individual work stations. As soon as a Worker can provide a service, the Broker sends him from his WorkerPool to the work station that ordered him. As soon as the WorkerPool receives a request for one of its Workers , which it can fulfill, the Broker sends the Worker to the Workplace which ordered him:

- If the Worker walks freely within the area of the simulation model, he walks on the shortest route to the Workplace and walks around obstacles you designated.
- The Worker consumes time, when he walks freely within the area to the Workplace .
- If you modeled the work station using one of the material flow objects and the Workplace and connected the WorkerPool and the Workplace with a FootPath , Plant Simulation animates the Worker while he moves on the FootPath and while he works on the Workplace .

The Worker consumes time, when he walks on the FootPath .

- If you activated Beam to workplace , and you inserted a Workplace , and the Worker , who is supposed to work there, cannot reach it via a FootPath , Plant Simulation beams the Worker directly to the Workplace and animates him there.
- If you activated Workers can work remotely and if you did not insert a Workplace , if no Workplace exists that supports this service, or if all Workplaces that support this service are occupied, Plant Simulation seemingly beams the Worker to the work station itself, where he will perform his task. Then, the material flow object only shows with an LED in the LED area of its icon that a Worker is working . It does not animate him there, but continues to animate him in the WorkerPool .

If a Worker is brokered to an importer for performing set-up, repairing or processing services and if this Worker then is assigned a failure, then the importer immediately places a new request with the Broker . Consequently, the respective operation can also be finished by another Worker .

If the Worker pauses or if a failure occurs when he finishes his work at the same time Plant Simulation does not delete the DisruptionEnd , Out , and SetupEnd events from the event list and does not request the Worker again after the failure or pause. This applies to set up, processing, and repair jobs.

**Note**

A paused Worker always returns to the WorkerPool . A failed Worker stays at the Workplace .

**Note**

A Worker who is automatically brokered does not return to the WorkerPool when he becomes paused or unplanned while he stays at the Workplace .

**Note**

A Worker , who is not automatically brokered stays, at the Workplace to which he was sent, no matter if you activated Worker Stays Here After Completing the Job / WorkerStaysHere or not in the Workplace .

**Note**

A Worker walks to the closest Workplace if several Workplaces are assigned to the work station.

We offer alternative graphics for the Worker in 3D . Click Exchange Graphics in the 3D window of the Worker and select an alternative graphic.

<!-- image -->

On the Tab MU Animation you can set how the parts are distributed on the Animation Area of the Worker in 3D.

<!-- image -->

The SankeyDiagram visualizes the paths of the Worker who walk freely within the area.

To show a tooltip with information about the Worker , hover with the mouse over it.

<!-- image -->

To show statistics of the Workers managed by the WorkerPool , drag it over a Chart and drop it there. Select the settings that you need.

<!-- image -->

**Add the Object to the Simulation Model**

To add the Worker to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; Worker on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Model Workers and the Jobs They Do

Model a Worker Who Carries Parts Between Workplaces

Model Workers with Importer, Broker, and Exporter

How the Worker Finds the Shortest Route

How the Worker Decides Where to Work

How the Worker Carries Parts How Workers Queue Up in Front of the Workplace

**Show Worker Statistics in a Chart**

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=QnyvMaEQeVyaDoHo](https://youtu.be/HiPziA8kxc0?si=QnyvMaEQeVyaDoHo)

#### How the Worker Travels in the Plant

How the Worker Finds the Shortest Route

The travel mode determines how the Worker finds the shortest route from the WorkerPool and the Workplaces and between the Workplaces .

<!-- image -->

You can select to make the Worker :

- Move freely within area
- Walk along footpaths
- Beam to workplace

**See also**

How the Worker Decides Where to Work

**Move freely within area**

##### Move freely within area

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

##### Walk along footpaths

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

##### Beam to workplace

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

#### How the Worker Decides Where to Work

At times a Worker in the plant will have to decide if he continues working on a Workplace doing a job for which he has the correct skills or if he moves to another Workplace that requires his skills more urgently.

While brokering, the Broker and the Worker proceed as follows:

1. The Broker first checks the Priority of the current request in the dialog of the Worker . If the job has the highest priority , he stays on the current Workplace and finishes the current job.
2. The Worker then checks if the material flow object, to which the Workplace is assigned, has a Scope with the respective Objects in his dialog.

<!-- image -->

<!-- image -->

If the current material flow object is part of the correct Scope , he stays on the current Workplace and finishes his current job there.

3. The respective Broker also checks if Choose the Nearest Worker is selected.

<!-- image -->

4. If the Worker has the highest Priority , a matching or no Scope , and the shortest route to the Workplace , the Broker brokers him to the respective Workplace .

In doing so, Plant Simulation computes a route to the Workplace for all eligible Workers while brokering them. The more Workers can be brokered, the more time it takes to compute the route to the Workplace . If you configured additional services , this might use up even more time. This can, consequently, slow down the simulation.

**See also**

Set Home Location and Scope for the Worker

Tab Scope

Choose the Nearest Worker [check box]

#### How the Worker Carries Parts

The Worker can carry parts from one station to another station. This only works if you attach a Workplace to the work station at which the Worker picks the part up. Also attach a Workplace to the target station at which he places the part. You also have to insert a Broker and a WorkerPool .

<!-- image -->

The following applies depending on the Travel Mode you select in the WorkerPool :

<!-- image -->

- For the setting Move freely within area the Worker automatically finds his way to the destination of the part.
- For the setting Walk along Footpaths you have to connect the Workplaces with Footpaths . Also connect the WorkerPool and the Workplace at the station at which the Worker picks the part up, with a Footpath .

Activate the transport importer on the tab Importer &gt; sub-tab Transport the dialog of the material flow object at which the Worker is to pick the part up. In the example below this is the station named Station1 .

Then, specify the Broker who brokers the Worker . If the part itself does not have a destination, you also have to specify the MU Target to which he carries the part . The MU Target either is the Workplace attached to the work station , which processes the part next and to which the Worker carries the part , or the work station itself.

<!-- image -->

The part then requests a Worker . The parts wait at the station until the Worker arrives and picks them up:

- If the Worker can only carry a single part , if its capacity is 1 (X-Dimension = 1, Y-Dimension = 1, Z-Dimension = 1), he picks the part up and carries it to the destination.
- If the Worker can carry several parts , he will wait for parts until his capacity is reached. To prevent the Worker from waiting too long for additional parts to arrive, type in the Maximum Dwell Time . After it has passed, he moves to the target station, the MU Target , and places the part .

The Worker evaluates the MU Targets and moves to the closest one first. At the target station, he places all parts destined for this station. If he carries additional parts, he evaluates the next target and moves on to the closest one, until he has placed all parts .

If your plant works in shifts, the Worker walks back to his WorkerPool at the end of his shift. He then deposits the parts which he could not deliver into the Parts Buffer which you assigned to the WorkerPool . If you did not assign a parts buffer to the WorkerPool , Plant Simulation shows a warning and stops the simulation.

If you activated the transport importer in the parts buffer , one of the available Workers carries the parts in the parts buffer to the destination object after the next shift has started. If you did not activate the transport importer , the parts in the parts buffer are moved on according to the Exit Strategy which you selected for the parts buffer .

See also

Model a Worker Who Carries Parts Between Workplaces

Graphic Sequences

#### Dialog Box of the Worker

Dialog Box of the Worker

Double-click the icon of the Worker to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

See also

Stopped [check box] - Worker

Failed [check box] - material flow objects

Paused/Planned/Unplanned [material flow objects]

Number [of the MU]

States of the Worker in 3D

##### Stopped [check box] - Worker

To stop the Worker on his way to or from the destination, select this check box. If the Worker stays in the WorkerPool or on a Workplace , you cannot stop him.

To make the Worker continue on his way on the Footpath or if he is walking freely within the area, clear the check box.

SimTalk

Stopped [SimTalk] - Worker

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Priority [Worker]**

###### Priority [Worker]

Type in the Priority with which the Worker carries out a work order.

<!-- image -->

The Priority of a Worker is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides a Worker with Priority 10 before providing a Worker with Priority 1.

Workers with a higher Priority will be brokered earlier by the Broker for identical services than Workers with a lower priority. The Priority only applies to Workers who are registered with the same Broker .

If several qualified Workers with the same priority exist, who can provide the requested service, Plant Simulation first brokers the Workers , who already stay on a suitable Workplace at the station. After that Workers are brokered who already are at the station, but stay on the wrong Workplace . Then Workers are brokered who are not staying on a Workplace . Finally, those Workers are brokered who stay on a Workplace that is assigned to another station.

SimTalk

Priority [SimTalk] - Worker

###### Efficiency [text box]

Type in the Efficiency in percent with which the Worker works. It determines how fast the Worker performs the work assigned to him.

<!-- image -->

Compare these examples:

- With an Efficiency of 100 percent the Worker consumes the exact processing time which you specified.
- With an Efficiency of 200 percent he consumes half of the processing time which you specified.
- With an Efficiency of 50 percent he consumes twice the processing time which you specified.

**Note**

If more than one Worker performs jobs at the station, the efficiency of the slowest Worker determines the processing time of the MU .

SimTalk

Efficiency [SimTalk] - Worker

See also

Workers to Create

**Speed [Worker]**

###### Speed [Worker]

Type in the Speed with which the Worker walks on the FootPath or walks freely within the area to the designated Workplace at the work station .

SimTalk

Speed [SimTalk] - Worker

CurrentSpeed [SimTalk] - Worker

###### X-Dimension [Worker]

Type in how many parts the Worker can carry in the X-Dimension .

<!-- image -->

The carrying capacity of the Worker is X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

SimTalk

XDim [SimTalk] - Worker

See also

Y-Dimension [Worker]

Z-Dimension [Worker]

###### Y-Dimension [Worker]

Y-Dimension [Worker]

Type in how many parts the Worker can carry in the Y-Dimension .

<!-- image -->

The carrying capacity of the Worker is X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

SimTalk

YDim [SimTalk] - Worker

See also

X-Dimension [Worker]

Z-Dimension [Worker]

###### Z-Dimension [Worker]

Type in how many parts the Worker can carry in the Z-Dimension .

<!-- image -->

The carrying capacity of the Worker is X-Dimension times Y-Dimension times Z-Dimension . The greatest allowed value is one million.

The Z-Dimension enables to stack parts one onto the other.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

SimTalk

ZDim [SimTalk] - Worker

See also

X-Dimension [Worker]

Y-Dimension [Worker]

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=tx1MOqgt0BsmOuxB&amp;t=693](https://youtu.be/HiPziA8kxc0?si=tx1MOqgt0BsmOuxB&t=693)

**Shift [Worker]**

###### Shift [Worker]

Type in the name of the Shift during which the Worker works.

<!-- image -->

If you do not specify a specific shift on the Tab Shift Times of the ShiftCalendar , the Worker works during all shifts defined in this ShiftCalendar .

SimTalk

Shift [SimTalk] - Worker

See also

Tab Shift Times

###### Services [Worker]

To open a list, into which you enter the names of the services, which the Worker provides, click this button.

<!-- image -->

- Before you can type in data, click the Inheritance check box so that it looks like this . The Worker provides these services by default:
- Type the name of the service into the cell and click Apply . The Worker attempts to provide the services in the order in which you type them into the list. You might, for example, enter repair , drilling , milling , turning , carrying parts , etc.

<!-- image -->

**Note**

The name of the Service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

If you type in a Priority and an Efficiency for each individual service, Plant Simulation uses these values. By typing in a Priority and an Efficiency , you are better able to control the automatic assignment of the services, which the Worker provides for jobs to be done.

<!-- image -->

If you do not type in a Priority and an Efficiency for an individual service, Plant Simulation uses the values for the Priority and the Efficiency of the Worker .

<!-- image -->

Plant Simulation inserts these services into the list of offered services of the Broker : To view them, select View &gt; Offered Services .

You can use the commands on the Context Menu of Embedded Lists to edit the contents of the cells.

If you want the Worker to provide additional services, you can type in these services into the Workers to Create table.

<!-- image -->

See also Exported Services [Worker] Offered Services [Broker] Context Menu of Embedded Lists Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=qYFCTtAc7V4GzXjQ&amp;t=178](https://youtu.be/HiPziA8kxc0?si=qYFCTtAc7V4GzXjQ&t=178)

###### Service [text box]

Service [text box]

Shows the name of the brokered or of the assigned service for the Worker who carries a part.

If the Worker is brokered to an importer , the brokered service is shown.

If the Worker carries parts to a Destination , he is no longer brokered. While the Worker carries parts, the assigned service is shown which corresponds to the brokered service during loading. The service remains assigned until the Worker has unloaded all parts.

While he is loading, the Worker is brokered. For this reason you can query this service during the loading time with the method getExportedServices .

See also

Loading Time [Workplace]

getExportedServices [SimTalk]

###### Broker [Worker]

Click the ellipsis button and select the Broker , who assigns the services to the Worker , in the dialog Select Object .

<!-- image -->

Or type in the path to and the name of the Broker . You might, for example, type in .Models.Model.MyBroker .

Or select the Broker in a Frame , drag it to the text box and drop it there.

Note

F2 opens the dialog of the object, whose name you typed into the text box.

SimTalk

BrokerPath [SimTalk] - Worker

See also

Broker [object]

Select Object [for controls]

###### Home Location

The Home Location is the Workplace to which the Worker walks when he has finished his current job.

<!-- image -->

**Remarks**

Click the ellipsis button and select the Home Location of the Worker in the dialog Select Object .

The Home Location is the Workplace to which the Worker walks when he has finished his current job.

**Note**

Plant Simulation transfers Workers , for whom you defined a Home Location and a Shift in the Workers to Create table of the WorkerPool , to the defined Home Location at the start of the Shift . They then start walking to the respective Workplace from there.

At the end of the shift Plant Simulation transfers all Workers of this shift directly to the WorkerPool , they do not walk back to the WorkerPool .

**Note**

Plant Simulation transfers Workers , for whom you defined a Home Location but no Shift , to the defined Home Location at the start of the simulation.

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

Or type in the path to and the name of the Workplace . You might, for example, type in ~.Models.Model.Workplace .

Or select the Home Location in a Frame , drag it to the text box and drop it there.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

You can also enter the Home Location into the Workers to Create table. Plant Simulation then enters it into the text box Home Location .

<!-- image -->

##### Tab Failures

Tab Failures

Define failures as described under the Tab Failures .

Tab Scope

Tab Scope

Assign any of the built-in material flow objects , or a Frame , to which the Worker can be brokered to perform a job, on the tab Scope .

To add an object to the scope of the Worker to the tab Scope , drag it from the Frame window over the icon of the Worker class and drop it there. You can also select and then drag-and-drop multiple objects at the same time!

<!-- image -->

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

To manipulate the contents of the list, use the commands on the Context Menu of Embedded Lists .

You can also enter the Scope into the Workers to Create table.

<!-- image -->

Plant Simulation then enters the respective stations into the cells in the Objects table.

<!-- image -->

###### Objects [Scope]

Assign the material flow objects to which the Worker can be mediated to do a job on the tab Scope .

<!-- image -->

- Type in the path to and the name of the material flow object in a cell. Or
- Drag the material flow object to the icon of the Worker and drop it there.
- Select several material flow objects and drag them to the icon of the Worker and drop them there.

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

To allow the Worker to be mediated to a Frame , including all of the inserted objects and sub-Frames , specify that Frame .

You can also enter the Scope into the Workers to Create table.

<!-- image -->

Plant Simulation then enters the respective stations into the cells in the Objects table.

SimTalk

Scope [SimTalk] - Worker

setWorkersToCreateTable [SimTalk]

See also

How the Worker Decides Where to Work

Set Home Location and Scope for the Worker

Choose the Nearest Worker [check box]

Tab Controls

Tab Controls [Worker]

Define controls how the Worker handles the orders.

To create a control:

- Click and select a Method in the dialog Select Object .
- Select the Method in a Frame , drag it to the text box and drop it there.

**Note**

F2 opens the dialog of the object, whose name you entered into the text box.

- Select Create Control and create the control as a Method of the object .

<!-- image -->

**See also**

Order Control [Worker]

Release Control [Worker]

**Order Control [Worker]**

###### Order Control [Worker]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Order Control , which is called whenever the Worker is assigned to an importer .

<!-- image -->

The Order Control sets how the Worker handles the order.

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

The standard order control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Method has two parameters, which define the importer :

- The parameter Importer of data type object designates the importer .
- The parameter Type of data type integer designates its type: 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**SimTalk**

OrderCtrl [SimTalk] - Worker

See also

Select Object [for controls]

**Release Control [Worker]**

###### Release Control [Worker]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Release Control , which sets how the Exporter/Worker releases the order.

<!-- image -->

Plant Simulation executes the Release Control as soon as an importer releases the Exporter/Worker . When the control is called, the Exporter/Worker has already left its importer . You yourself have to make sure that the Exporter/Worker is assigned new importers , for example with the method fi ndNewImporter . In this case the Exporter/Worker will not automatically register as being available with its Broker .

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

The standard release control as a user-defined attribute looks like this:

<!-- image -->

**Parameters**

The Method has two parameters, which define the importer :

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type:

0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**Note**

Plant Simulation calls the release control , which you typed into the Worker for the transportimporter , when the Worker starts to carry parts away. This is then the case if either the Maximum Dwell Time [transport importer] has passed or if the Worker cannot pick up any more parts because his X-Dimension [Worker] , Y-Dimension [Worker] , and Z-Dimension [Worker] is used up.

**SimTalk**

ReleaseCtrl [SimTalk] - Worker

See also

Select Object [for controls]

##### Tab Statistics

Tab Statistics [Worker]

Plant Simulation shows the most important statistical data on the tab Statistics .

It shows the values for the Services and for the Worker . For each of these blocks, adding up the individual values results in 100 percent.

<!-- image -->

The Worker collects failed times of the services and of the Worker . The Worker only collects Failed times that accrue during the processing time, i.e., times that are located outside of the paused and of the unplanned time.

Waiting times only accumulate during the times if the Worker is available, i.e., if these times are located outside of the paused , the unplanned , and of the failed times.

| Item English           | Description                                                                                                                                                                                                                                            | Read-only attribute                              | Item German         |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|---------------------|
| Services Setting-up    | Shows the portion of the set-up time of the services of the overall statistics time of the Worker . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                   | StatServicesSetupPortio n [SimTalk] - Worker     | Dienste rüstend     |
| Services Processing    | Shows the portion of the working time of the services of the overall statistics time of the Worker . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                  | StatServicesWorkingPor tion [SimTalk] - Worker   | Dienste arbeitend   |
| Services Repairing     | Shows the portion of the repairing time of the services of the overall statistics time of the Worker . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                | StatServicesRepairingPo rtion [SimTalk] - Worker | Dienste reparierend |
| Services Transporti ng | Shows the portion of the transporting time from Workplace to Workplace of the services of the overall statistics time of the Worker . The overall statistics time is the statistics collection period without the unplanned time and the paused time . | StatServicesTransportin gPortion [SimTalk]       | Dienste tragend     |

| Item English             | Description                                                                                                                                                                                                                                                                                                                                                                                                 | Read-only attribute                                                                                                                                                                         | Item German                      |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
| Services En-route to Job | Shows the portion of the time of the services of the overall statistics of the Worker spent for getting to the Workplace or back to the WorkerPool to get the next job order. The latter only applies if you select Get job orders at home only . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                          | StatServicesEnRouteToJ obPortion [SimTalk]                                                                                                                                                  | Dienste unterwegs zu Auftrag     |
| Services Waiting         | Shows the portion of the waiting time of the services for an importer plus the time the services spent waiting for a MU at the importer of the overall statistics time of the Worker . The value of StatServicesEnRouteIdlePortion is part of the value of StatServicesWaitingImpPortion . The overall statistics time is the statistics collection period without the unplanned time and the paused time . | StatServicesWaitingPort ion [SimTalk] - Worker StatServicesWaitingImp Portion [SimTalk] - Worker StatServicesWaitingMU Portion [SimTalk] - Worker StatServicesEnRouteIdle Portion [SimTalk] | Dienste wartend                  |
| Services Failed          | Shows the portion of the failed time of the services of the overall statistics time of the Worker . The overall statistics time is the statistics collection period without the unplanned time and the paused time .                                                                                                                                                                                        | StatServicesFailedPortio n [SimTalk] - Worker                                                                                                                                               | Dienste gestört                  |
| Exporter Operationa l    | Shows the portion of the statistics collection period during which the Worker was operational.                                                                                                                                                                                                                                                                                                              | StatExporterOperational Portion [SimTalk]                                                                                                                                                   | Exporter einsatzberei t          |
| Exporter Paused          | Shows the portion of the statistics collection period during which the Worker was paused.                                                                                                                                                                                                                                                                                                                   | StatExporterPausedPorti on                                                                                                                                                                  | Exporter pausiert                |
| Exporter Unplanned       | Shows the portion of the statistics collection period during which the Worker was unplanned.                                                                                                                                                                                                                                                                                                                | StatExporterUnplanned Portion [SimTalk]                                                                                                                                                     | Exporter ungeplant               |
| Exporter Failed          | Shows the portion of the statistics collection period during which the Worker was failed.                                                                                                                                                                                                                                                                                                                   | StatExporterFailedPorti on [SimTalk]                                                                                                                                                        | Exporter gestört                 |
| Worker Traveled Distance | Shows the distance which the instance of the Worker traveled from the WorkerPool to the Workplaces attached to the stations and between the stations in meters.                                                                                                                                                                                                                                             | StatTraveledDistance [SimTalk] - Worker                                                                                                                                                     | Werker zurückgeleg te Wegstrecke |

To collect statistics data, select the check box Exporter Statistics .

To view Exporter and Worker Statistics in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

The individual states look like this:

<!-- image -->

**Note**

The Worker stays at the station, to which he is brokered, while this station is failed , paused , or stopped . Statistics does not count this time as waiting .

**See also**

Tab Statistics [WorkerPool]

Exporter Statistics [Worker]

To collect statistics data of the Worker , select this check box.

To deactivate statistics collection, clear the check box.

SimTalk

ExpStatOn [SimTalk]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu [Worker]

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Importers [Worker]            |
|--------------------------------------------|-------------------------------|
| Show Statistics Report [on View menu]      | Exported Services [Worker]    |
| Show Attributes and Methods [on View menu] | Route to Destination [Worker] |
| Contents [Worker]                          | Associated Shift Calendar     |
| Position [Worker]                          |                               |

See also

View Menu [general description]

**Contents [Worker]**

###### Contents [Worker]

Opens a table which shows all MUs which the Worker carries.

For a Worker with the capacity 1 the table has one column. It has as many columns as the capacity ( X-Dimension , the Y-Dimension , and the Z-Dimension ) you typed in.

<!-- image -->

###### Position [Worker]

Opens a table which shows the object on which the Worker is located at the moment.

<!-- image -->

**Importers [Worker]**

###### Importers [Worker]

Opens a table which shows all importers for which the Worker provides services.

<!-- image -->

The table shows the Importers in column 1, and their Type in column 2: The number 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

<!-- image -->

###### Exported Services [Worker]

Opens a list which shows the names of all services which the Worker provides at this time.

Double-click the name of a service to open a subtable, which shows the name of the Importer , the Type of the importer and the Amount of services provided.

The Type 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

<!-- image -->

**SimTalk**

getExportedServices [SimTalk]

Services [SimTalk] - Worker

###### Route to Destination [Worker]

Selects all objects along the route to the destination object of the selected instance of the Worker .

<!-- image -->

See also getRouteLength [SimTalk] - Worker getRouteCoordinates [SimTalk] getRouteLength [SimTalk] - Workplace

##### Tools Menu

The Tools Menu provides these menu commands:

Edit Controls

Edit Observers

3D

In addition, the Worker provides the Available control and the Not-available control .

**Help Menu**

##### Help Menu

The commands are described under the Help Menu .

##### States of the Worker in 3D

During your simulation runs a 3D Only model can show the state of the Worker . Select a setting on the Tab States &gt; States Orientation .

<!-- image -->

- The setting Horizontal shows the state as a horizontally arranged cube along the bottom of his picture.

<!-- image -->

For the setting Horizontal you can show all states which the Worker can take.

<!-- image -->

- The setting Color colors the entire picture of the Worker .

<!-- image -->

See also

Tab States &gt; State graphic

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Method

LEDs and States of the MQTT Interface

**Methods of the Worker**

#### \_Methods of the Worker

The Worker provides:

- The methods listed in the table of contents to the left.

**Note**

If you do not use a FootPath , Plant Simulation beams/teleports the Worker to the Workplace .

- The \_Methods of the Exporter as the Worker is an Exporter [object] with the capacity 1.
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

##### cancelTransportPart [SimTalk]

Cancels each and every transport of the parts, which you started with the method transportPart , and which are scheduled to be carried by the Worker designated by &lt;Path&gt;.

Remarks

If one part or several parts are scheduled to be transported, Plant Simulation deletes this reservation and the Worker either walks to the WorkerPool or to his base.

If you specified a Station at which the Worker picks up finished parts, Plant Simulation deletes this reservation as well. As soon as the Worker has picked up a part and transported it, the reservation cannot be canceled though.

**Note**

If you specified a Destination when ordering the Worker to transport parts, and the Destination was then saved in the parts to be transported, Plant Simulation does not undo this change. This means that the specified Destination is retained and you can still query it with the attribute Destination .

**Note**

cancelTransportPart only cancels each and every transport of the parts, which you started with the method transportPart .

It does not cancel automatically mediated transports initiated by a combination of the Transport Importer and the Broker .

Type

Method

Syntax

&lt; Path &gt;.cancelTransportPart -&gt; boolean

Return Value

The return value has the data type boolean .

true if all transport processes could be canceled.

false if they could not be canceled.

false might be returned if no orders exist to transport parts or if the Worker picked up at least one part to be transported.

**Example**

.Resources.MyWorker:1.cancelTransportPart

**SimTalk**

transportPart [SimTalk]

Destination [SimTalk] - MUs create [SimTalk] - Worker Creates an instance of the Worker designated by &lt;Path&gt; in the WorkerPool .

Type

Method

Syntax

&lt; Path &gt;.create(WorkerPool:object)

Parameter

The parameter WorkerPool of data type object designates the WorkerPool where the Worker will be created.

Example

.Resources.MyWorker.create(MyWorkerPool)

##### getRouteLength [SimTalk] - Worker

Returns the route of the Worker designated by &lt;Path&gt; from his present location to this destination object.

**Remarks**

If you enter a station as the destination object, the method returns the length of the route to the Workplace which can be reached on the shortest route.

If the Worker is exporting a service at the moment, it only takes those Workplaces into consideration, which support the service, including all Workplaces , which are not restricted to certain services.

If you enter a Workplace as destination object, Plant Simulation always computes the length to this Workplace , no matter if it supports the exported service or not.

Type

Method

Syntax

&lt; Path &gt;.getRouteLength(Target:path[, byref FoundWorkplace:object]) → length

**Parameters**

- The parameter Target of data type path designates the destination object. The destination object can be a Workplace , a WorkerPool , or a work station to which you attached Workplaces .
- The optional local variable FoundWorkplace of data type object is the variable into which Plant Simulation writes the Workplace which it found at the destination object.

This is helpful if you assign a work station to the parameter Target instead of a Workplace .

**Return Value**

The return value has the data type length .

Is -1 if Plant Simulation did not find a route.

**Examples**

```simtalk
print .Resources.Worker:1.getRouteLength(MyWorkplace1)
var FoundWorkplace: object .Resources.Worker:1.getRouteLength(MyStation, FoundWorkplace)
print FoundWorkplace
```

SimTalk

getRouteCoordinates [SimTalk]

getRouteLength [SimTalk] - Workplace

See also

Route to Destination [Worker]

getServices [SimTalk] - Worker

Returns all services of the Worker designated by &lt;Path&gt; and writes them into a table.

Type

Method

Syntax

&lt; Path &gt;.getServices(Services:table)

Parameter

The parameter Services of data type table designates the name of an unformatted table (a table in a Frame or a local table) with three columns:

- Column 1 has the data type string and contains the Name of the Service .
- Column 2 has the data type integer and contains the Priority .
- Column 3 has the data type integer and contains the Efficiency .

**Example**

print .Resources.Worker:1.getServices(MyServicesTable)

SimTalk

setServices [SimTalk] - Worker

Services [SimTalk] - Worker

See also

Services [Worker]

**goTo [SimTalk]**

Sends the Worker designated by &lt;Path&gt; to the designated Workplace .

Remarks

If the Worker is interrupted, but must teleport to reach the intended destination, the Worker does not accept the order and the method returns false.

If the specified object is not a Workplace but a work station , the Worker walks to the closest Workplace assigned to the work station instead.

Type

Method

Syntax

```simtalk
< Path >.goTo(Workplace:object[, ReserveExclusively:boolean:=true]) → boolean
```

**Parameters**

- The parameter Workplace of data type object designates the Workplace to which you want to send the Worker .
- The optional parameter ReserveExclusively of data type boolean sets if the Workplace will be reserved exclusively for the Worker until he leaves the Workplace ( true or no parameter). In this case the Workplace is not available any longer for another Worker , even while the designated Worker is on his way to the Workplace . If the Workplace is already occupied by another Worker , the Worker you sent stops and goTo returns false.

If you specify false , the Workplace is not going to be reserved. The Worker walks to the Workplace , and if the Workplace is occupied, he waits until it becomes available again.

**Note**

If AutomaticMediation is deactivated and goTo is called if the parameter ReserveExclusively is true , meaning that it reserves the Workplace , Plant Simulation checks if the Workplace still has available Capacity . If all places of the Workplace are either occupied or reserved, Plant Simulation shows an error message.

**Default Value of the Parameter**

The default value is true.

Return Value

The return value has the data type boolean .

false if the Worker is exporting a service at the moment. The Worker then stays where he is currently at.

**Examples**

- .Resources.MyWorker:1.goTo(MyWorkplace)

.Resources.MyWorker:1.goTo(MyWorkplace,false)

**SimTalk**

AutomaticMediation [SimTalk] - Worker

goToHome [SimTalk]

goToPool [SimTalk]

teleportTo [SimTalk]

teleportToPool [SimTalk]

goToHome [SimTalk]

Sends the Worker designated by &lt;Path&gt; back to his WorkerPool or to his Home Location if you defined a Home Location .

Remarks

If the Worker is interrupted, but must teleport to reach the intended destination, the Worker does not accept the order and the method returns false.

Type

Method

Syntax

```simtalk
< Path >.goToHome → boolean
```

Return Value

The return value has the data type boolean .

false if the Worker is exporting a service at the moment. The Worker then stays where he is currently at.

**Example**

.Resources.MyWorker:1.goToHome

**SimTalk**

goTo [SimTalk]

goToPool [SimTalk]

HomeLocation [SimTalk] - Worker

teleportTo [SimTalk]

teleportToPool [SimTalk]

See also

Home Location

##### goToPool [SimTalk]

goToPool [SimTalk]

Sends the Worker designated by &lt;Path&gt; back to the WorkerPool .

Remarks

If the Worker is interrupted, but must teleport to reach the intended destination, the Worker does not accept the order and the method returns false.

Syntax

```simtalk
< Path >.goToPool → boolean
```

Return Value

The return value has the data type boolean .

false if the Worker is exporting a service at the moment. The Worker then stays where he is currently at.

Example

.Resources.MyWorker:1.goToPool

SimTalk

goTo [SimTalk]

goToHome [SimTalk]

teleportTo [SimTalk]

teleportToHome [SimTalk]

##### setServices [SimTalk] - Worker

Sets the services that the Worker designated by &lt;Path&gt; provides.

Type

Method

Syntax

&lt; Path &gt;.setServices(Services:table)

**Parameter**

The parameter Services of data type table designates the name of an unformatted table (a DataTable in a Frame or a local table) with three columns:

<!-- image -->

- Column 1 has the data type string and contains the Name of the Service .
- Column 2 has the data type integer and contains the Priority .
- Column 3 has the data type integer and contains the Efficiency .

**Example**

- .Resources.Worker:1.setServices(MyServicesTable)
- .UserObjects.MyWorker.setServices(MyServicesTable)

**SimTalk**

getServices [SimTalk] - Worker

Services [SimTalk] - Worker

##### teleportTo [SimTalk]

See also

**Services [Worker]**

teleportTo [SimTalk]

Teleports the Worker designated by &lt;Path&gt; to the designated Workplace .

Type

Method

Syntax

```simtalk
< Path >.teleportTo(Workplace:object) → boolean
```

Parameter

The parameter Workplace of data type object designates the Workplace to which you want to teleport the Worker .

Return Value

The return value has the data type boolean .

true if the Worker was teleported.

false if the Worker was not teleported because the Worker is already located on the Workplace for example.

Examples

```simtalk
.Resources.MyWorker:1.teleportTo(MyStation) -- returns true if a workplace at the station is available and the Worker can be teleported there
.Resources.MyWorker:2.teleportTo(MyWorkplace1) -- returns true if the Worker can be teleported to this Workplace
```

SimTalk

teleportToHome [SimTalk]

teleportToPool [SimTalk]

goToHome [SimTalk]

goToPool [SimTalk]

teleportToHome [SimTalk]

Teleports the Worker designated by &lt;Path&gt; back to his WorkerPool or to his HomeLocation if you defined a Home Location .

Type

Method

Syntax

&lt; Path &gt;.teleportToHome → boolean

Return Value

The return value has the data type boolean .

true if the Worker could be teleported to his Home Location or to his WorkerPool .

false if the Worker could not be teleported because he is already located at his Home Location or in his WorkerPool for example.

Example

.Resources.MyWorker:1.teleportToHome

SimTalk

teleportTo [SimTalk]

teleportToPool [SimTalk]

goTo [SimTalk]

goToPool [SimTalk]

HomeLocation [SimTalk] - Worker

<!-- image -->

##### teleportToPool [SimTalk]

See also

Home Location

teleportToPool [SimTalk]

Teleports the Worker designated by &lt;Path&gt; back to the WorkerPool .

Syntax

&lt; Path &gt;.teleportToPool → boolean

Return Value

The return value has the data type boolean .

true if the Worker was teleported to his WorkerPool .

false if the Worker was not teleported to his WorkerPool because he was already located there for example.

Example

.Resources.MyWorker:1.teleportToPool

SimTalk

teleportTo [SimTalk]

teleportToHome [SimTalk]

goTo [SimTalk]

goToHome [SimTalk]

##### transportPart [SimTalk]

Makes the Worker designated by &lt;Path&gt; transport a single part from its current location to the specified destination. Transports several parts from the current location to their specified destination.

**Remarks**

Instead of one or several parts you can also specify a material flow object, which provides parts to be picked up. Then the Worker picks up all parts, which are ready to exit and carries them away when the Worker arrives at the specified Station until his Capacity is exhausted.

If no parts are ready to exit when the Worker arrives, Plant Simulation shows an error message.

If you do not specify a Destination , the part/the parts must already have a Destination . Plant Simulation saves the specified Destination in the part/the parts. You can query it with the attribute Destination .

**Note**

The Worker can only transport several parts if he can pick all parts up at the same location.

Type

Method

Syntax

```simtalk
< Path >.transportPart(PartOrStationOrParts:object/object[ ][, Destination:object])
-> void < Path >.transportPart(Part:object[, Destination:object])
-> void < Path >.transportPart(Parts:object[ ][, Destination:object])
-> void < Path >.transportPart(Station:object[, Destination:object])
-> void
```

**Parameters**

- The parameter Part of data type object designates the part that is to be transported.
- The parameter Parts of data type object designates an array of parts that are to be transported.
- The parameter Station of data type object designates the Station at which the Worker picks up the parts that are ready to exit and carries them away.

The Station can be any material flow object that provide parts to be picked up.

- The optional parameter Destination of data type object designates the destination object to which the Worker transports the part. If you do not specify the destination , you have to define a destination for each part to be transported.

**Return Value**

The method does not have a return value.

It outputs error messages, which might cause the method to fail, because:

- The specified Worker is a class object.
- The specified Worker is brokered automatically.
- The specified Worker cannot transport parts.
- The specified Worker already carries a part.
- The number of parts to be carried is greater than the current Capacity of the Worker .
- The part does not exist or does not have the correct object type.
- The Destination does not exist or does not have the correct object type.
- You did not specify a Destination and the part/the parts do not have a Destination of their own.
- The part itself, that is to be transported, has a defined Destination , which differs from the specified Destination .
- The parts to be transported have to be picked up at different locations.
- The part or one of the parts is already being transported by a Worker .
- No parts are to be picked up and carried away at the Station by the Worker .
- An error occurred while sending the Worker for picking up or transporting the parts.

**Examples**

```simtalk
waituntil .Resources.Worker:1.HasOrder = false .Resources.Worker:1.transportPart(Station.cont, Station1)
```

**SimTalk**

cancelTransportPart [SimTalk]

Destination [SimTalk] - MUs

#### Read-Only Attributes of the Worker

\_Read-Only Attributes of the Worker

The Worker provides:

- The read-only attributes listed in the table of contents to the left.

- All read-only attributes of the Exporter , as the Worker is an Exporter with the capacity of 1.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print .Resources.Worker:1.StatTraveledDistance AvailableForMediation [SimTalk] - Worker Returns if the Worker designated by &lt;Path&gt; can be brokered to do a job (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.AvailableForMediation → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

true if the Worker is not failed, not paused, does not carry parts, and if he is not brokered.

Example

print .Resources.MyWorker:2.AvailableForMediation CurrentSpeed [SimTalk] - Worker Returns the Current Speed with which the Worker designated by &gt;Path&gt; walks on the Footpath or freely within the area .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentSpeed → speed

Watchable

The read-only attribute is watchable .

By watching it, you might, for example detect the event when the speed of a Worker changes.

Return Value

The return value has the data type speed .

It is the Speed which you set.

0 if the Worker is failed or stopped or if he is located in the WorkerPool or on a Workplace .

Example

print .UserObjects.MyWorker:1.CurrentSpeed

See also

Speed [Worker]

HasOrder [SimTalk] - Worker Returns if the Worker designated by &lt;Path&gt; has the order to transport parts, currently transports parts, or just exports services. Type Read-only attribute Syntax &lt;MUPath &gt;.HasOrder -&gt; boolean Watchable The attribute is watchable . Return Value The return value has the data type boolean . Example HasOrder [SimTalk] - Worker

waituntil not Worker.HasOrder   // wait until the Worker is idle, has no order, or carries no parts mu.move                        // transfer the MU, which should place an order for the Worker to transport it

ResCurrentState [SimTalk] - Worker

Returns the Current State of the Worker designated by &lt;Path&gt;.

Remarks

During a simulation run the Worker can take on one of these states as described on the Tab Statistics :

Services Setting-up , Services Processing , Services Repairing , Services Transporting , Services Enroute to Job , Services Waiting , Exporter Paused , Exporter Unplanned , or Exporter failed .

**Note**

If two states occur at the same time, for example Paused and Failed , the read-only attribute returns the state that also has precedence for statistics collection. Paused for example for Paused and Failed .

Type

Read-only attribute

Syntax

```simtalk
< Path >.ResCurrentState → string
```

Watchable

The read-only attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record it in watch mode.

Return Value

The return value has the data type string .

VOID if Exporter statistics is turned off.

Example

```simtalk
print .Resources.John.ResCurrentState -- class print .Resources.John:1.ResCurrentState -- instance
```

See also

Resource Statistics [material flow objects]

**Tab Statistics [Worker]**

##### StatServicesEnRouteIdleCount [SimTalk]

Returns how often the Worker designated by &lt;Path&gt; was on his way without having an order.

Remarks

The overall statistics time is the statistics collection time without the Unplanned Time and the Paused Time .

This means that he was on his way, while he could be brokered. This occurs, for example, if you clear Get Job Orders at Home Only and also clear Worker Stays Here After Completing the Job at the Workplace . If you send the Worker to a Workplace with the method goTo , then this will also be added to the value StatServicesEnRouteIdleCount .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteIdleCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesEnRouteIdleCount

SimTalk

goTo [SimTalk]

See also

Get Job Orders At Home Only

Worker Stays Here After Completing the Job StatServicesEnRouteIdlePortion [SimTalk]

Returns the portion of the overall statistics time during which the Worker designated by &lt;Path&gt; was en-route without being assigned a job order.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

This means that he was on his way, while he could be brokered. This occurs, for example, if you clear Get Job Orders at Home Only and also clear Worker Stays Here After Completing the Job at the Workplace . If you send the Worker to a Workplace with the method goTo , then the time he was on this way will also be added to the value StatServicesEnRouteIdlePortion .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteIdlePortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesEnRouteIdlePortion

SimTalk

goTo [SimTalk]

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters

Get Job Orders At Home Only

Worker Stays Here After Completing the Job StatServicesEnRouteIdleTime [SimTalk]

Returns the total time during which the Worker designated by &lt;Path&gt; was en-route without having a job.

Remarks

This means that he was on his way, while he could be brokered. This occurs, for example, if you clear Get Job Orders at Home Only and also clear Worker Stays Here After Completing the Job at the Workplace . If you send the Worker to a Workplace with the method goTo , then the time he was on this way will also be added to the value StatServicesEnRouteIdlePortion .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteIdleTime →

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesEnRouteIdleTime

SimTalk

goTo [SimTalk]

See also

Get Job Orders At Home Only

Worker Stays Here After Completing the Job time

##### StatServicesEnRouteToJobCount [SimTalk]

Returns how often the Worker designated by &lt;Path&gt; was en-route to a Workplace , to which he was brokered for do a job at the associated station.

Remarks

If you select Get Job Orders at Home Only , Plant Simulation also counts how often the Worker walked back to the WorkerPool to get the next order.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteToJobCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesEnRouteToJobCount

See also

Get Job Orders At Home Only

##### StatServicesEnRouteToJobPortion [SimTalk]

Returns the portion of the overall statistics time during which the Worker designated by &lt;Path&gt; was en-route to a Workplace , to which he was brokered to do a job at the associated station.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

If you select Get Job Orders at Home Only , Plant Simulation also counts the time during which the Worker walked back to the WorkerPool to get the next order.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteToJobPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesEnRouteToJobPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters

Get Job Orders At Home Only

##### StatServicesEnRouteToJobTime [SimTalk]

Returns the total time during which the Worker designated by &lt;Path&gt; was en-route to a Workplace for which he was brokered to do a job at the associated station.

Remarks

If you select Get Job Orders at Home Only , Plant Simulation also counts the time during which the Worker walked back to the WorkerPool to get the next order.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesEnRouteToJobTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesEnRouteToJobTime

See also

Get Job Orders At Home Only StatServicesFailedCount [SimTalk] - Worker Returns how often the services of the Worker designated by &lt;Path&gt; were failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesFailedCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesFailedCount StatServicesFailedPortion [SimTalk] - Worker Returns the portion of the failed time of the services of the overall statistics time of the Worker designated by &lt;Path&gt;.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesFailedPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesFailedPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesFailedTime [SimTalk] - Worker Returns the total time during which services of the Worker designated by &lt;Path&gt; were failed.

Type

Read-only attribute

Syntax

< Path >.StatServicesFailedTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesFailedTime StatServicesRepairingCount [SimTalk] - Worker Returns how often the services of the Worker designated by &lt;Path&gt; worked on repairs.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesRepairingCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesRepairingCount StatServicesRepairingPortion [SimTalk] - Worker Returns the portion of the repairing time of the services of the overall statistics time of Worker designated by &lt;Path&gt;.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesRepairingPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesRepairingPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters

##### StatServicesRepairingTime [SimTalk] - Worker

Returns the total time which the services of the Worker designated by &lt;Path&gt; spent for repairs.

Type

Read-only attribute

Syntax

< Path >.StatServicesRepairingTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesRepairingTime StatServicesSetupCount [SimTalk] - Worker Returns how often the services of the Worker designated by &lt;Path&gt; were setting the station up.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesSetupCount StatServicesSetupPortion [SimTalk] - Worker Returns the portion of the set-up time of the services of the overall statistics time of the Worker designated by &lt;Path&gt;.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

**Note**

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesSetupPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesSetupTime [SimTalk] - Worker Returns the total time the services of the Worker designated by &lt;Path&gt; were setting the station up.

Remarks

If a station fails and/or is unplanned or paused and services for setting-up or processing are brokered for this station, the services remain assigned. For this reason the set-up time and the processing time for the services continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesSetupTime

##### StatServicesTransportingCount [SimTalk]

Returns how often the Worker designated by &lt;Path&gt; was carrying parts from Workplace to Workplace .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesTransportingCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesTransportingCount StatServicesTransportingPortion [SimTalk]

Returns the portion of the overall statistics time during which the Worker designated by &lt;Path&gt; was carrying parts from Workplace to Workplace .

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesTransportingPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesTransportingPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters

##### StatServicesTransportingTime [SimTalk]

Returns the total time during which the Worker designated by &lt;Path&gt; was carrying parts from Workplace to Workplace .

Type

Read-only attribute

Syntax

< Path >.StatServicesTransportingTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesTransportingTime StatServicesWaitingImpCount [SimTalk] - Worker Returns how often the services of the Worker designated by &lt;Path&gt; waited for an importer .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingImpCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:2.StatServicesWaitingImpCount StatServicesWaitingImpPortion [SimTalk] - Worker Returns the portion of the overall statistics time which the services of the Worker designated by &lt;Path&gt; spent waiting for an importer , weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingImpPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:2.StatServicesWaitingImpPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWaitingImpTime [SimTalk] - Worker Returns the total waiting time of the services of the Worker designated by &lt;Path&gt; for an importer .

Type

Read-only attribute

Syntax

< Path >.StatServicesWaitingImpPortion → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:2.StatServicesWaitingImpPortion StatServicesWaitingMUCount [SimTalk] - Worker Returns how often the services of the Worker designated by &lt;Path&gt; spent waiting for a MU at the importer .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatServicesWaitingMUCount → integer
```

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:2.StatServicesWaitingMUCount StatServicesWaitingMUPortion [SimTalk] - Worker Returns the portion of the overall statistics time during which the services of the Worker designated by &lt;Path&gt; were waiting for a MU at the importer .

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingMUPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:2.StatServicesWaitingMUPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWaitingMUTime [SimTalk] - Worker Returns the total time the services of the Worker designated by &lt;Path&gt; were waiting at the importer for a MU .

Type

Read-only attribute

Syntax

< Path >.StatServicesWaitingMUTime → time

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:2.StatServicesWaitingMUTime StatServicesWaitingPortion [SimTalk] - Worker Returns the portion of the waiting time of the services of the overall statistics time of the Worker designated by &lt;Path&gt;.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

**Note**

The value of StatServicesWaitingPortion is the sum of StatServicesWaitingImpPortion plus StatServicesWaitingMUPortion .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:2.StatServicesWaitingPortion

SimTalk

StatServicesWaitingImpPortion [SimTalk] - Worker

StatServicesWaitingMUPortion [SimTalk] - Worker StatServicesWaitingTime [SimTalk] - Worker Returns the time which the services of the Worker designated by &lt;Path&gt; were waiting in relation to the statistics collection period.

Remarks

The value of StatServicesWaitingTime is the sum of StatServicesWaitingImpTime and StatServicesWaitingMUTime .

Type

Read-only attribute

Syntax

< Path >.StatServicesWaitingTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print .Resources.MyWorker:2.StatServicesWaitingTime
```

SimTalk

StatServicesWaitingImpTime [SimTalk] - Exporter

StatServicesWaitingMUTime [SimTalk] - Exporter StatServicesWorkingCount [SimTalk] - Worker Returns the number of working processes which the services of the Worker designated by &lt;Path&gt; provided.

Remarks

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWorkingCount → integer

Return Value

The return value has the data type integer .

Example

print .Resources.MyWorker:1.StatServicesWorkingCount StatServicesWorkingPortion [SimTalk] - Worker Returns the working portion of the services of the overall statistics time of the Worker designated by &lt;Path&gt;.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

**Note**

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWorkingPortion → real

Return Value

The return value has the data type real .

Example

print .Resources.MyWorker:1.StatServicesWorkingPortion

See also

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWorkingTime [SimTalk] - Worker Returns the time taken up by working processes of the services of the Worker designated by &lt;Path&gt;.

Remarks

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWorkingTime → real

Return Value

The return value has the data type time .

Example

print .Resources.MyWorker:1.StatServicesWorkingTime

##### StatTraveledDistance [SimTalk] - Worker

Returns the distance which the instance of the Worker designated by &lt;Path&gt; covered while walking from the WorkerPool to the Workplaces attached to the stations and between the stations in meters.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTraveledDistance → length

Return Value

The return value has the data type length .

Example

print .Resources.MyWorker:2.StatTraveledDistance

See also

Tab Statistics [Worker]

Statistics report , Worker Statistics - Traveled Distance by Workers

#### Attributes of the Worker

\_Attributes of the Worker

The Worker provides:

- The attributes listed in the table of contents to the left.

Note

If you do not use a FootPath , Plant Simulation beams the Worker to the Workplace .

- The \_Attributes of the Exporter as the Worker is an Exporter [object] with the capacity of 1.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
.Resources.MyWorker:2.Efficiency := 90
print .Resources.Worker.MyWorker:2.Efficiency
posit := Station.Cont.XPos
```

##### AutomaticMediation [SimTalk] - Worker

Prevents that the Worker designated by &lt;Path&gt;, which you yourself want to assign, is automatically assigned by the Broker .

Remarks

If no Broker exists when creating the Workers , Plant Simulation sets the attribute AutomaticMediation of the Workers to false .

A Worker , who is not automatically brokered, does not return to the WorkerPool when his state changes to paused or unplanned.

**Note**

If AutomaticMediation is deactivated, and if the method goTo is called when the parameter ReserveExclusively has the value true , meaning that it reserves the Workplace , Plant Simulation checks if the Workplace still has available Capacity . If all places of the Workplace are either occupied or reserved, Plant Simulation shows an error message.

Type

Attribute

Syntax

```simtalk
< Path >.AutomaticMediation:boolean
```

Assignment Value

You can assign a value of data type boolean .

Specify true to make the Broker assign the Worker automatically.

Specify false to assign the Worker yourself.

Example

```simtalk
.Resources.MyWorker:2.AutomaticMediation := true
param type: integer // Importer type (0=failure, 1=setup, 2=processing, 3=transport)
var t: table
switch type
case 0
	?.failImp.releaseExporters
case 1
?.setupImp.getExporters(t)
if t.yDim > 0 t[1,1].AutomaticMediation := true
end
?.setupImp.releaseExporters
case 2
	?.imp.getExporters(t)
	if t.yDim > 0 t[1,1].AutomaticMediation := true
	end
	?.imp.releaseExporters
end
```

**SimTalk**

##### goTo [SimTalk]

importExporter [SimTalk]

##### BrokerPath [SimTalk] - Worker

Sets the path to the Broker who brokers the services that the Worker designated by &lt;Path&gt; provides.

Type

Attribute

Syntax

&lt; Path &gt;.BrokerPath:object

Assignment Value

You can assign a value of data type object .

Example

```simtalk
print .Resources.MyWorker:2.BrokerPath .Resources.MyWorker:2.BrokerPath := myBroker .Resources.MyWorker:2.BrokerPath := Broker3
```

See also

Broker [Worker]

Efficiency [SimTalk] - Worker

Sets the Efficiency of the Worker designated by &lt;Path&gt;, i.e., how fast he performs the job assigned to him.

Type

Attribute

Syntax

&lt; Path &gt;.Efficiency:integer

Assignment Value

You can assign a value of data type integer .

- With an Efficiency of 100 percent the Worker consumes the exact processing time which you specified.
- With an Efficiency of 200 percent he consumes half of the processing time which you specified.
- With an Efficiency of 50 percent he consumes twice the processing time which you specified.

**Note**

If more than one Worker performs jobs at the station, the efficiency of the slowest Worker determines the processing time of the MU .

**Example**

```simtalk
.Resources.MyWorker:2.Efficiency := 90
```

See also

Efficiency [text box]

Efficiency [SimTalk] - WorkerPool in the Workers to Create

##### HomeLocation [SimTalk] - Worker

Sets the path to the Home Location , i.e., the Workplace to which the Worker designated by &lt;Path&gt; walks, once he has finished his current job.

Remarks

Plant Simulation transfers Workers , for whom you defined a Home Location and a Shift in the Workers to Create table of the WorkerPool , to the defined Home Location at the start of the Shift . They then start walking to the respective Workplace from there.

At the end of the shift Plant Simulation transfers all Workers of this shift directly to the WorkerPool , they do not walk back to the WorkerPool .

Plant Simulation transfers Workers , for whom you defined a Home Location but no Shift , to the defined Home Location at the start of the simulation.

**Note**

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

Type

Attribute

Syntax

&lt; Path &gt;.HomeLocation:object

Assignment Value

You can assign a value of data type object .

Example

```simtalk
.Resources.MyWorker:2.HomeLocation := ~.Models.Model.Workplace
print .Resources.MyWorker:2.HomeLocation
```

SimTalk

setWorkersToCreateTable [SimTalk]

See also Home Location Workers to Create The Relative Path IsIdle [SimTalk] - Worker Sets if the Worker designated by &lt;Path&gt; is idle ( true ), i.e., does not work, or is not idle ( false ).

Remarks

IsIdle works together with the read-only attribute NumIdleWorkers of the WorkerPool .

NumIdleWorkers returns the number of Workers for which the attribute IsIdle returned true.

The method getIdleWorker of the WorkerPool returns the first idle Worker for whom IsIdle is to true and sets it to false. When you no longer need the Worker , you can send the Worker to the WorkerPool and set IsIdle to true .

Type

Attribute

Syntax

&lt; Path &gt;.IsIdle:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
.Resources.Worker:1.IsIdle := true
```

SimTalk

NumIdleWorkers [SimTalk]

getIdleWorker [SimTalk]

##### OrderCtrl [SimTalk] - Worker

OrderCtrl [SimTalk] - Worker

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever the Worker is assigned to an importer .

In the control you determine how the Worker handles an order.

Type

Attribute

Syntax

&lt; Path &gt;.OrderCtrl:method

Parameters

The order control has two parameters that define the importer :

- The parameter Importer of data type object designates the importer .
- The parameter Type of data type integer designates its type : 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

Reformatting the Method

If you manually enter an Order Control and click Apply or OK , Plant Simulation automatically checks if the Method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking if the Method shall be reformatted or not. Empty methods are reformatted automatically. You cannot suppress checking of the format of the Method .

Assignment Value

You can assign a value of data type method .

Example

```simtalk
.Resources.MyWorker:2.OrderCtrl := &myOrderCtrl
```

See also

Order Control [Worker]

##### Priority [SimTalk] - Worker

Priority [SimTalk] - Worker

Sets the priority with which the Worker designated by &lt;Path&gt; carries out a work order.

Remarks

The Priority of a Worker is a criterion for the urgency of a request. The Priority is an integer value.

Workers with a higher Priority will be brokered earlier by the Broker for identical services than Workers with a lower priority. The Priority only applies to Workers who are registered with the same Broker .

If several qualified Workers with the same priority exist, who can provide the requested service, Plant Simulation first brokers the Workers , who already stay on a suitable Workplace at the station. After that Workers are brokered who already are at the station, but stay on the wrong Workplace . Then Workers are brokered who are not staying on a Workplace . Finally, those Workers are brokered who stay on a Workplace that is assigned to another station.

Type

Attribute

Syntax

&lt; Path &gt;.Priority:integer

Assignment Value

You can assign a value of data type integer .

The higher the value that you enter, the higher is the priority. Plant Simulation provides a Worker with Priority 10 before providing a Worker with Priority 1 .

Example

```simtalk
.Resources.MyWorker:2.Priority := 6
```

See also

Priority [Worker]

##### ReleaseCtrl [SimTalk] - Worker

Designates a Method of the Worker designated by &lt;Path&gt;.

Remarks

The Worker executes the control as soon as an importer releases the Worker . When the control is called, the Worker has already left its importer . If you did enter a Method , the Worker will not be brokered for already waiting importers . To broker the Worker to already waiting importers nonetheless, you have to use the method fi ndNewImporter .

Syntax

&lt; Path &gt;.ReleaseCtrl:method

Parameters

The Release Control has two parameters that define the importer :

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type: 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**Note**

Plant Simulation calls the Release Control , which you typed into the Worker for the transportimporter , when the Worker starts to carry parts away. This is then the case if either the Maximum Dwell Time has passed or if the Worker cannot pick up any more parts because his X-Dimension , Y-Dimension , and Z-Dimension is used up.

**Reformatting the Method**

If you manually enter a Release Control and click Apply or OK , Plant Simulation automatically checks if the Method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking if the Method shall be reformatted or not. Empty methods are reformatted automatically. You cannot suppress checking of the format of the Method .

**Assignment Value**

You can assign a value of data type method .

**Example**

- .Resources.MyWorker:2.ReleaseCtrl := &amp;myWorkerReleaseCtrl

SimTalk findNewImporter [SimTalk] See also

Release Control [Worker]

##### Scope [SimTalk] - Worker

Sets the Scope of the Worker designated by &lt;Path&gt;. The Scope array contains all objects to which the Worker can be brokered to do a job.

Remarks

Plant Simulation always resolves relative paths in relation to the Frame in which the WorkerPool is inserted. If Plant Simulation cannot resolve a path in the Scope array during the simulation, it shows an error message and asks if you would like to stop the simulation.

To allow the Worker to be brokered to a Frame , including all of the inserted objects and sub-Frames , specify that Frame .

Type

Attribute

Syntax

< Path >.Scope:array[]

Assignment Value

You can assign an array of data type string .

Examples

```simtalk
// gets the scope
var Scope:
object[] := MyWorker.Scope // array of objects // deletes the list of objects of the scope
MyWorker.Scope := VOID // deletes the list of objects of the scope
MyWorker.Scope := [] // replaces the list of objects of the scope with an object
MyWorker.Scope := .Models.Model.Station // replaces the list of objects of the scope with a list of objects
MyWorker.Scope := [.Models.Model.Station, .Models.Model.ParallelStation]
```

See also

Tab Scope Services [SimTalk] - Worker Sets the names of the Services that the Worker designated by &lt;Path&gt; provides.

Remarks

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

Syntax

< Path >.Services:array[]

Assignment Value

You can assign an array of data type string .

**Examples**

```simtalk
var a :
string[] := ["Job1", "Job2", "Job3"] .Resources.MyWorker:1.Services := a
print .Resources.MyWorker:1.Services
```

**See also**

Services [Worker]

Relational Operators

##### Shift [SimTalk] - Worker

Shift [SimTalk] - Worker

Sets the name of the Shift during which the Worker designated by &lt;Path&gt; works.

Remarks

Specify an empty string "" to make the Worker work during all shifts which are defined in the associated ShiftCalendar .

Syntax

```simtalk
< Path >.Shift:string
```

Assignment Value

You can assign a value of data type string .

**Example**

```simtalk
.Resources.MyWorker:2.Shift := "Night shift" .Resources.MyWorker:3.Shift := "" // the worker works during all shifts
```

See also

Shift [Worker]

##### Speed [SimTalk] - Worker

Sets the Speed with which the Worker designated by &lt;Path&gt; walks on the FootPath or walks freely within the area to his Workplace .

Type

Attribute

Syntax

< Path >.Speed:speed

**Assignment Value**

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
var s : speed := x / 2s   // Beware: x/2 would have the wrong unit, m
```

instead of m/s

**Example**

```simtalk
.Resources.MyWorker:2.Speed := 0.5
```

**See also**

**Speed [Worker]**

##### Stopped [SimTalk] - Worker

Stops the Worker designated by &lt;Path&gt; on his way to or from the destination ( true ) or makes him continue on his way ( false ).

Remarks

If the Worker stays in the WorkerPool or on a Workplace , you cannot stop him.

Type

Attribute

Syntax

```simtalk
<MUPath >.Stopped:boolean
```

**Assignment Value**

You can assign a value of data type boolean .

**Example**

```simtalk
.UserObjects.MyWorker:2.Stopped := true   // Worker stops .UserObjects.MyWorker:2.Stopped := false  // Worker continues
```

**See also**

Stopped [check box] - Worker

**WorkerPool [SimTalk]**

##### WorkerPool [SimTalk]

Sets the WorkerPool to which the Worker designated by &lt;Path&gt; belongs.

Syntax

&lt; Path &gt;.WorkerPool:object

Assignment Value

You can assign a value of data type object .

Example

.Resources.MyWorker:2.WorkerPool := MyWorkerPool XDim [SimTalk] - Worker Sets the number of parts that the Worker designated by &lt;Path&gt; can carry in the X-Dimension .

Remarks

The carrying capacity of the Worker is the product of XDim times YDim times XDim . The greatest allowed value is one million.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

Type

Attribute

Syntax

&lt; Path &gt;.XDim:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

.Resources.Worker.XDim := 2

SimTalk

YDim [SimTalk] - Worker

ZDim [SimTalk] - Worker

See also

X-Dimension [Worker]

YDim [SimTalk] - Worker

YDim [SimTalk] - Worker

Sets the number of parts that the Worker designated by &lt;Path&gt; can carry in the Y-Dimension .

Remarks

The carrying capacity of the Worker is the product of XDim times YDim times XDim . The greatest allowed value is one million.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

Type

Attribute

Syntax

&lt; Path &gt;.YDim:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.Resources.Worker.YDim := 2
```

SimTalk

XDim [SimTalk] - Worker

ZDim [SimTalk] - Worker

See also

X-Dimension [Worker]

ZDim [SimTalk] - Worker

Sets the number of parts that the Worker designated by &lt;Path&gt; can carry in the Z-Dimension .

Remarks

The carrying capacity of the Worker is the product of XDim times YDim times XDim . The greatest allowed value is one million.

The Z-Dimension enables stacking parts one onto the other. The stacked parts are only visible in 3D.

If you decrease the carrying capacity of the Worker , make sure that no parts are located on the places that will be deleted by this action! Either delete these parts or move them to another place on the reduced carrying capacity area.

Type

Attribute

Syntax

&lt; Path &gt;.ZDim:integer

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
.Resources.Worker.YDim := 2
```

SimTalk

XDim [SimTalk] - Worker

YDim [SimTalk] - Worker

See also

X-Dimension [Worker]

