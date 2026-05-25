### Workplace

Use the Workplace for modeling the actual place at the station, where the Worker performs his job.

Icon

<!-- image -->

**Description**

The Worker -WorkerPool -Workplace -FootPath -concept refines the Broker -Importer -Exporter -concept. You

<!-- image -->

can assign a Workplace to the material flow objects that support an Importer . In this case, the importers are processing or repairing importers .

For the transport importer , who controls how the Workers carry parts, you can assign a Workplace to the Buffer , the PlaceBuffer , the Source , the Sorter , and the Store in addition.

The Workplace is the actual place at the station where the Worker performs his job.

**Note**

You can, but you do not have to assign a Workplace to a station, i.e., a material flow object.

If you do not use a FootPath , Plant Simulation transports the Worker directly to the Workplace . Here the Worker functions as an Exporter with a capacity of 1.

#### Workplace

The Workers are created in the WorkerPool and they stay there when they do not work and are waiting for a job order.

The Broker procures the Worker for the individual work stations. As soon as a Worker can provide a service, the Broker sends him from his WorkerPool to the work station that ordered him:

- If the Worker walks freely within the area of the simulation model, he walks on the shortest route to the Workplace and walks around any obstacles you designated.

The Worker consumes time, when he walks freely within the area to the Workplace .

- If you modeled the work station using one of the material flow objects and the Workplace and connected the WorkerPool and the Workplace with a FootPath , Plant Simulation animates the Worker while he moves on the FootPath and while he works on the Workplace .

The Worker consumes time when he walks on the FootPath .

If several Workers walk to the same Workplace and have to wait their turn before they can step onto it, you can define how they queue up in front of the workplace .

- If you activated Beam to workplace and if you inserted a Workplace , and the Worker , who is supposed to work there, cannot reach it via a FootPath , Plant Simulation beams the Worker directly to the Workplace and animates him there.
- If you activated Workers can work remotely , if you did not insert a Workplace , if no Workplace exists that supports this service, or if all Workplaces that support this service are occupied, Plant Simulation seemingly transports the Worker to the work station itself. He then does his job at the work station. Plant Simulation does not animate him at the work station though, but continues to animate him in the WorkerPool . The material flow object only shows an LED in the LED area of its icon to denote that a Worker is working.

To show a tooltip with information about the Workplace , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Workplace , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the Workplace to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; Workplace on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

See also Model Workers and the Jobs They Do How Workers Queue Up in Front of the Workplace Model a Worker Who Waits in Line Tab Importer Worker -WorkerPool -Workplace -FootPath -concept Broker -Importer -Exporter -concept Video on YouTube https://youtu.be/HiPziA8kxc0?si=Ft4r3\_Sq9xlzt9DU&amp;t=45

#### How Workers Queue Up in Front of the Workplace

You can set how arriving Workers , who cannot step onto the Workplace , wait in the queue in front of it.

**Note**

We only show the queue in a 3D Only model .

Plant Simulation queues these Workers , without using additional FootPaths , in the queue at their waiting position . The waiting position is determined according to the position in the Forward Blocking List of the Workplace . Let's say the Worker is located at the third position in the Forward Blocking List , then he also waits at the third place in the queue.

The waiting position is the position at which the Worker waits until it is his turn to step onto the Workplace . The waiting position depends on his position in the Forward Blocking List and the distance between the Workers in the queue. Once a waiting Worker moves up in the Forward Blocking List , he also moves up in the queue.

In new models Plant Simulation visualizes the queue on the MU Animation Path named Queue of the Workplace . If the queue is longer than the pre-defined MU Animation Path , Plant Simulation elongates it toward the end of the queue.

You can set the Distance between the Workers in the queue on the animation path.

<!-- image -->

If you do not want the Worker to walk to the Workplace , but to the end of the MU Animation Path , select Walk Along the Animation Path of the Queue .

After the Worker has reached the end of the MU Animation Path , Plant Simulation computes the direct way to the waiting position or to the Workplace respectively.

**Working with the Worker Queue**

- If the Worker is to Model Workers Who Walk to the End of the Queue , the end of the animation path has to be positioned at the same height ( Z-position ) as the Workplace .

If this is not the case, Plant Simulation might not be able to compute a route to the end of the animation path.

Once the Worker arrived at the end of the animation path and provided the Workplace is still available while computing the route, Plant Simulation sets the Workplace as the target, even if other Workers might already be on their way to the Workplace on the animation path.

If the Worker arrives at a Workplace or at a waiting position that is occupied, Plant Simulation moves him directly to the correct waiting position .

If the end of the animation path is located after the actual waiting position , the Worker walks along the animation path to this waiting position .

If the queue is longer, so that the Worker stands in the queue once he has reached the end of the animation path, he walks through the already waiting Workers to his waiting position .

- Activating Walk Along the Animation Path of the Queue and reaching the waiting position or the Workplace via a Footpath is relevant for the simulation as the times during which the Worker is on his way do change.

Plant Simulation does not use up any time for reaching the waiting position if the Worker walks directly to the Workplace . Plant Simulation then shows him at the respective waiting position in the queue.

The same is true when the Worker moves up within the queue as these movements are executed by the respective animation of the Worker .

**See also**

Model a Worker Who Waits in Line

Distance in Queue

Walk to the End of the Animation Path of the Queue

Walk Along the Animation Path of the Queue

MU Animation on Animation Paths on the Workplace

MU Animation on Point-Oriented Objects Holding Several Parts

Video on YouTube

[https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&amp;t=775](https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&t=775)

#### Dialog Box of the Workplace

Dialog Box of the Workplace

Double-click the icon of the Workplace to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

##### Tab Attributes

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Station [Workplace]

Click the ellipsis button and select the Station to which you want to assign the Workplace , in the dialog Select Object .

<!-- image -->

The Station is a material flow object that supports an importer , for example the Source , the Drain , the Station , the ParallelStation , the AssemblyStation , the DismantleStation , or the Conveyor .

To automatically enter the Station , drag the Workplace close to a side of the material flow object which you want to use as the Station .

The icon of the Workplace , to which you did not assign a Station , looks like this . The icon of the Workplace , to which you did assign a Station , looks like this .

<!-- image -->

**At Entrance [check box]**

###### At Entrance [check box]

To attach the Workplace to the entrance of the Conveyor , select this check box.

<!-- image -->

For the place-oriented material flow objects Plant Simulation selects At Entrance and At Exit by default.

Attach a Workplace to the Entrance of a Conveyor with Drag-and-Drop

- Select the Workplace with the mouse and drag it to the entrance of the Conveyor . The icon of the Workplace shows a tooltip with Conveyor @ Entrance .
- Select the Conveyor , hold down Shift and drag it to the icon of the Workplace to attach it to its entrance.

<!-- image -->

Attach a Workplace to a Place-oriented Material Flow Object with Drag-and-Drop

- Select the Workplace with the mouse and drag it to the object, the Station in the example below. The icon of the Workplace shows a tooltip with Station @ Entrance &amp; Exit .
- Select the Station and drag it to the icon of the Workplace to attach it to its entrance and exit.

<!-- image -->

**Note**

Assigning a new station to a Workplace via SimTalk does not change the current assignment to the entrance or the exit.

**SimTalk**

AtEntrance [SimTalk]

**See also**

**Model a Worker Who Waits for a Free Target**

###### At Exit [check box]

At Exit [check box]

To attach the Workplace to the exit of the Conveyor , select this check box.

<!-- image -->

For the place-oriented material flow objects Plant Simulation selects At Entrance and At Exit by default.

Attach a Workplace to the Exit of a Conveyor with Drag-and-Drop

- Select the Workplace with the mouse and drag it to the exit of the Conveyor . The icon of the Workplace shows a tooltip with Conveyor @ Exit .
- Select the Conveyor and drag it to the icon of the Workplace to attach it to its exit.

<!-- image -->

Attach a Workplace to a Place-oriented Material Flow Object with Drag-and-Drop

- Select the Workplace with the mouse and drag it to the object, the Station in the example below. The icon of the Workplace shows a tooltip with Station @ Entrance &amp; Exit .
- Select the Station and drag it to the icon of the Workplace to attach it to its entrance and exit.

<!-- image -->

**Note**

Assigning a new station to a Workplace via SimTalk does not change the current assignment to the entrance or the exit.

**SimTalk**

AtExit [SimTalk]

See also

Model a Worker Who Waits for a Free Target

###### Capacity [text box] - Workplace

Type in the Capacity of the Workplace . The Capacity is the maximum number of Workers that can stay on this Workplace at any one time.

<!-- image -->

The Capacity is important if several tasks can be accomplished on this Workplace or if these tasks come together there.

Plant Simulation uses the coordinate of the Workplace to find the shortest route to it, meaning that the Worker walks to this coordinate and then jumps to the animation point of the Workplace .

By default, 3D shows the Workers on the Workplace distributed across an Animation Area .

<!-- image -->

**Note**

You can only change the Capacity if the Workplace is empty.

**Note**

You can define a Recovery Time for a Workplace that has a Capacity of 1 . It starts once a Worker leaves the Workplace .

**SimTalk**

Capacity [SimTalk] - Workplace

###### Supported Services [button]

To open the list into which you type the services, which the Workplace supports, click this button.

<!-- image -->

- Before you can type in data, click the Inheritance check box so that it looks like this .
- Type in an expression of your choice into the cell, and click Apply . You might, for example, specify different names for the different services, such as drilling , milling , turning , etc. or group them by name.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

<!-- image -->

- If you do not type any Services into the list, the Worker can execute any service on this Workplace .
- If you did not insert a Workplace , if no Workplace exists that supports this service, or if all Workplaces that support this service are occupied, Plant Simulation seemingly transports the Worker to the work station itself. He then does his job at the work station.

**Note**

The Worker even works if he does not find a Workplace that supports the requested service. In this case, he will not be animated though.

Plant Simulation does not animate the Worker at the work station though, but continues to animate him in the WorkerPool . The material flow object only shows an LED in the LED area of its icon to denote that a Worker is Working .

**Supported Services [button]**

SimTalk

SupportedServices [SimTalk]

See also

Context Menu of Embedded Lists

###### Worker Stays Here After Completing the Job

To make the Worker stay on the Workplace after he completes his job, select this check box.

To make the Worker return to the WorkerPool or to the Home Location immediately after finishing his job, clear the check box.

You have to clear the check box if you activate the setting Get Job Orders At Home Only in the WorkerPool .

**Note**

A Worker , who is not automatically brokered, stays on the Workplace to which he was sent, no matter if you activated Worker Stays Here After Completing the Job / WorkerStaysHere or not in the Workplace .

**Note**

If a Worker stays on a Workplace while another Worker has to work on it, and if the Capacity of the Workplace is used up, Plant Simulation shoves the Worker aside who is not working. This Worker then exits the Workplace and returns to the WorkerPool or to the Home Location if you configured one.

SimTalk

WorkerStaysHere [SimTalk]

See also

Get Job Orders At Home Only

GetJobOrdersAtHomeOnly [SimTalk]

Home Location

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=fCggWItWi0soTBxq&amp;t=314](https://youtu.be/HiPziA8kxc0?si=fCggWItWi0soTBxq&t=314)

**Distance in Queue**

###### Distance in Queue

Type in the Distance between the Workers in the queue on the animation path of the Workplace .

<!-- image -->

The Workers attempt to keep this distance while they wait in line to step onto the Workplace and do their job.

Note

We only show the queue in a 3D Only model .

SimTalk

DistanceInQueue [SimTalk]

See also

How Workers Queue Up in Front of the Workplace

Model a Worker Who Waits in Line

Walk to the End of the Animation Path of the Queue

Walk Along the Animation Path of the Queue

MU Animation on Animation Paths on the Workplace

###### Walk to the End of the Animation Path of the Queue

To make the Worker first Walk to the End of the Animation Path of the Queue and then on to his destination , select this check box.

<!-- image -->

Note

We only show the queue in a 3D Only model .

SimTalk

WalkToQueuePathEnd [SimTalk]

See also

How Workers Queue Up in Front of the Workplace

Model a Worker Who Waits in Line

Walk Along the Animation Path of the Queue

MU Animation on Animation Paths on the Workplace

###### Walk Along the Animation Path of the Queue

To make the Worker Walk Along the Animation Path of the Queue to his waiting position or to the Workplace once he has reached the MU Animation Path , select this check box.

<!-- image -->

Walk Along the Animation Path of the Queue only takes effect, if you also select Walk to the End of the Animation Path of the Queue as the Worker first walks to the end of the animation path of the queue and then along the animation path to the Workplace or to the waiting position .

Once the Worker has reached the end of the MU Animation Path , Plant Simulation computes the route to the target, the waiting position , or to the Workplace along the MU Animation Path .

**Note**

Plant Simulation does not take obstacles into account when the Worker walks along the MU Animation Path .

SimTalk

WalkAlongQueuePath [SimTalk]

See also

How Workers Queue Up in Front of the Workplace

Model a Worker Who Waits in Line

MU Animation on Animation Paths on the Workplace

MU Animation on Animation Paths on the Workplace

Video on YouTube

[https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&amp;t=775](https://youtu.be/gU1pqu7sWA8?si=HgdhN-JsmsY7HQSH&t=775)

###### Pick/Drop at Store

Sets what the Worker does when he walks to a Workplace attached to a Store , when picking up or dropping parts at this Store . The Workplace only shows this setting if 3D is active and if the Station is a Store .

Select how the Worker proceeds when he has to pick parts up at the Store or when he places parts in the Store .

- Walk to Workplace : Is the default setting that previous versions of Plant Simulation implicitly provided. The Worker walks to the Workplace to pick up parts or to drop parts.

For this setting, all settings of the Workplace are available.

<!-- image -->

**Note**

Plant Simulation only considers route computations with the methods getRouteLength and getRouteCoordinates for the setting Pick/Drop at Store &gt; Walk to Workplace .

For the other settings of Pick/Drop at Store the method getRouteLength will return the value -1 and getRouteCoordinates will return an empty array.

- Walk to Store Column : The Worker walks to the store column to pick up or to drop parts. The Worker can walk to the store column without any restrictions.

<!-- image -->

For this setting the following features are not available:

- You cannot enter a Capacity .

We assume the Capacity to be infinite.

- You cannot select Worker Stays Here After Completing the Job .
- You cannot enter the Distance in Queue .
- You cannot select Walk to the End of the Animation Path of the Queue .
- You cannot select Walk Along the Animation Path of the Queue .

Plant Simulation determines the locations to which the Worker walks by the dimensions of the side of the Store at which the Workplace is placed, by the number of columns at that side, and by the distance of the center point of the Workplace to the Store itself.

In addition, Plant Simulation uses the distance of the center point of the Workplace to the store front to place the pick or drop locations in front of the store column.

Walk to Store Column uses all pick or drop locations in front of the Store for computing the routes of the Workers . Be aware that large Stores with many columns will increase the complexity of the route computations and will impact performance.

- Walk Along Store to Store Column : The Worker walks to the first or last column at the side of the Store where the Workplace is placed. Then the Worker extends his route and continues to walk along the Store to the store column to drop a part or pick up a part. Thus the routes to the store columns are restricted and each store column can only be reached from the previous or next store columns, except for the first and last store column. The Worker can walk to the first and last store columns without any restrictions.

When the Worker extends his route from the first or last store column, he ignores all obstacles within his route.

<!-- image -->

For this setting the following features are not available:

- You cannot enter a Capacity .

We assume the Capacity to be infinite.

- You cannot select Worker Stays Here After Completing the Job .
- You cannot enter the Distance in Queue .
- You cannot select Walk to the End of the Animation Path of the Queue .
- You cannot select Walk Along the Animation Path of the Queue .
- Plant Simulation determines the locations to which the Worker walks by the dimensions of the side of the Store at which the Workplace is placed, by the number of columns at that side, and by the distance of the center point of the Workplace to the Store itself.

The diagram of the location to which the Worker walks looks like this:

<!-- image -->

Walk Along Store to Store Column does not increase the number of commonly reachable locations for the route calculation in the same way as the setting Walk to Store Column does. Thus, performance impact should be smaller.

**SimTalk**

PickDropAtStore [SimTalk]

getRouteLength [SimTalk] - Workplace getRouteCoordinates [SimTalk]

See also

Model a Worker Picking Parts Up at/Placing Parts in a Store

Capacity [text box] - Workplace

Worker Stays Here After Completing the Job

Distance in Queue

Walk to the End of the Animation Path of the Queue

Walk Along the Animation Path of the Queue

Tab Times

Tab Times [Workplace]

The tab Times provides these settings:

Loading Time [Workplace]

Unloading Time [Workplace]

Recovery Time [Workplace]

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

###### Loading Time [Workplace]

Select a distribution, and type the values which that distribution requires into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a constant time ( Const ).

<!-- image -->

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the part for which the loading time applies. The anonymous identifier ? points to the Workplace . You can access the Worker with ?.Cont .

**Loading Time**

The Loading Time is the time it takes the Worker for picking up a single part at a station. After the Loading Time has elapsed, the Worker waits for the Maximum Dwell Time to pass if he still has carrying capacity. If not, he immediately carries the part to the target station and places it there. If the Worker is to load more than one part , the Maximum Dwell Time should at least be as long the carrying capacity times the Loading Time .

The part is booked on the Worker while he picks it up. The processing station is locked until the Loading Time has elapsed.

**Note**

The entrance of the Workplace is closed while its Loading Time is running as the Worker functions with reservations for the Workplace .

Behavior During Interruptions of the Worker

Plant Simulation extends the Loading Time by failure times of the Worker . The processing station remains locked during the failure.

If the Worker pauses during the Loading Time , Plant Simulation cancels the Loading Time and considers it as completely elapsed. This means that the Worker carries at least one part to the WorkerPool .

If the shift ends during the Loading Time , Plant Simulation cancels the Loading Time and considers it as completely elapsed. This means that the Worker carries at least one part to the parts buffer .

**Loading Time [Workplace]**

Behavior During Interruptions of the Processing Station

Failures of the processing station do not affect loading the part by the Worker . The part is already located at the Worker and loading takes place during the failure.

The same applies for processing stations which are stopped , paused , or unplanned .

SimTalk

LoadingTime [SimTalk] - Workplace

LoadingTime [SimTalk] - Workplace . Type [SimTalk] - distribution parameter

###### Unloading Time [Workplace]

Select a distribution, and type the values which that distribution requires into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a constant time ( Const ).

<!-- image -->

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the part for which the unloading time applies. The anonymous identifier ? points to the Workplace . You can access the Worker with ?.Cont .

**Unloading Time**

The Unloading Time is the time it takes the Worker for placing the part he picked up at another station onto the target station. If he is to unload several parts , the Unloading Time accrues for each part .

The part is booked on the Worker while he places it on the target station. The target processing station is locked until the Unloading Time has elapsed.

Behavior During Interruptions of the Worker

Plant Simulation extends the Unloading Time by failure times of the Worker . The target processing station remains locked during the failure .

If the Worker pauses during the Unloading Time , Plant Simulation cancels the unloading time . The target processing station does not remain locked, and the Worker takes the parts to the WorkerPool with him. After the pause is over, unloading starts anew.

If the shift ends during the Unloading Time , Plant Simulation cancels the Unloading Time and the Worker carries the part to the parts buffer . The target processing station does not remain locked.

Behavior During Interruptions of the Processing Station Through a Failure, Pause, etc.

The Worker only starts unloading when the target processing station can take on the part for processing. If this is not the case, Plant Simulation enters the part to be unloaded into the Forward Blocking List . The Unloading Time starts after the interruption is over.

The Worker continues unloading the part when the target processing station is being interrupted during the Unloading Time . Plant Simulation also enters the part to be unloaded into Forward Blocking List if the target processing station cannot accept a part at the time of the actual unloading process (after the unloading time has elapsed). The part stays with the Worker . After the interruption has been removed, the Worker deposits the part onto the target processing station without any time delay.

SimTalk

UnloadingTime [SimTalk] - Workplace

UnloadingTime [SimTalk] - Workplace . Type [SimTalk] - distribution parameter

###### Recovery Time [Workplace]

Select a distribution, and type in the values which that distribution requires into the text box. Plant Simulation shows these values along the upper border of the tab. You can also type in a constant time ( Const ).

<!-- image -->

The predefined Recovery Time in the class of the Workplace prevents that a Worker steps onto the Workplace while the Worker who is already located on it has not left it all the way.

**Note**

You can only define the Recovery Time for a Workplace that has a Capacity of 1 . The Recovery Time starts once a Worker leaves the Workplace .

**Note**

The Recovery Time will not take effect, if you set the Workplace as the Home Location of a Worker and if the Worker wants to step onto this Home Location / Workplace .

If you select the Formula distribution, you can type in a numeric expression or the name of a Method . You can use the anonymous identifier @ to access the part for which the unloading time applies. The anonymous identifier ? points to the Workplace . You can access the Worker with ?.Cont .

SimTalk

RecoveryTime [SimTalk]- Workplace

See also

Recovery Time [general description]

HomeLocation [SimTalk] - Worker

Capacity [SimTalk] - Workplace

##### Tab Controls

Tab Controls

Tab Controls [Workplace]

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

**See also**

Entrance Control [Workplace]

Exit Control [Workplace]

Load Control

**Unload Control**

**Entrance Control [Workplace]**

###### Entrance Control [Workplace]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Entrance Control , which is called once the Worker has entered the Workplace .

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

EntranceCtrl [SimTalk] - Workplace

**See also**

**Select Object [for controls]**

Video on YouTube

[https://youtu.be/HiPziA8kxc0?si=QuDu7iePtML5x7De&amp;t=908](https://youtu.be/HiPziA8kxc0?si=QuDu7iePtML5x7De&t=908)

**Exit Control [Workplace]**

###### Exit Control [Workplace]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Exit Control , which is called once the Worker has left the Workplace .

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

ExitCtrl [SimTalk] - Workplace

**See also**

**Select Object [for controls]**

###### Load Control

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Load Control , which is called as soon as the Worker steps onto the Workplace .

<!-- image -->

The Load Control sets how the part is transferred from the work station to the Worker staying on the attached Workplace . After picking the part up, the Worker carries it to the target object.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

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

The standard load control as a user-defined attribute looks like this:

```simtalk
// workplace load control ... // ... to transfer MUs from the associated station to the worker on the workplace // @: worker // ?: workplace
if @.failed = false and @.pause = false // get the first MU to exit and repeat this until no MU is about to exit
	var mu:object := ?.station.cont
	while mu /= void and @.full = false // transfer the exiting MU to the worker
		mu.move(@) // with configured load time on workplace, wait for EndOfTime event causing the transfer to worker waituntil mu.~ = @
		mu := ?.station.cont
	end
end
```

SimTalk

**LoadCtrl [SimTalk]**

See also

Select Object [for controls]

###### Unload Control

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Unload Control , which is called as soon as the Worker enters the Workplace attached to the target station..

<!-- image -->

The Unload Control sets how the Worker places the part, which he carried to the Workplace , onto the attached work station .

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

The standard unload control as a user-defined attribute looks like this:

```simtalk
// workplace unload control ... // ... to transfer all MUs from a worker on the workplace to the associated station // @: worker // ?: workplace
if @.failed = false and @.Pause = false // remember the station associated to the workplace
	var station:object := ?.station // get the first MU about to exit to repeat this until no MU wants to exit anymore
	var mu:object := @.cont
	while mu /= void and station.full = false // wait until the entrance is free (for example for conveyors)
		waituntil station.EntranceFree // transfer the MU from the carrying worker to the station
		mu.move(station) // with configured unload time on workplace, wait for EndOfTime event causing the transfer from worker to station waituntil mu.~ = station
		mu := @.cont
	end
end
```

SimTalk

**UnloadCtrl [SimTalk]**

See also

Select Object [for controls]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Contents [Workplace]         |
|--------------------------------------------|------------------------------|
| Show Statistics Report [on View menu]      | Contents and Reserved Places |
| Show Attributes and Methods [on View menu] | Forward Blocking List        |

**Contents [Workplace]**

###### Contents [Workplace]

Opens a list of all Workers that stay on the Workplace .

<!-- image -->

A Workplace with a Capacity greater than 1 shows the names and the numbers of the Workers that stay on it.

**SimTalk**

contentsList [SimTalk] - Workplace Tools Menu The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Workplace**

#### \_Methods of the Workplace

The Workplace provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .
- The Methods of the Material Flow Objects .

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

contentsList [SimTalk] - Workplace

contentsList [SimTalk] - Workplace

Returns an array containing the entire contents, i.e., all Workers located in the Contents List of the Workplace designated by &lt;Path&gt;.

Syntax

```simtalk
< Path >.contentsList([ContentsList:table]) → any
```

Parameter

The optional parameter ContentsList of data type table designates the name of the table (a DataTable or a local variable) into which the method writes the values. Plant Simulation automatically generates the format of this table, and deletes any existing format and contents of the table.

Return Value

The return value has the data type any .

Example

```simtalk
Workplace2.contentsList(MyContentsList)
print Workplace2.contentsList
```

See also

Contents [material flow objects]

Contents [Workplace]

getRouteCoordinates [SimTalk]

Returns the 3D-coordinates of the waypoints of the route which a Worker would have to cover to get from the Workplace designated by &lt;Path&gt; to another Workplace or to the WorkerPool .

Type

Method

Syntax

```simtalk
< Path >.getRouteCoordinates(ToWorkplace:path[, FreelyWithinArea:boolean:=false]) → array
```

**Parameters**

- The parameter ToWorkplace of data type path designates the Workplace which is the destination Workplace of the route.
- The optional parameter FreelyWithinArea of data type boolean sets if the Worker gets to the Workplace by walking freely within the area or not.

Specify false or do not specify the parameter to compute the waypoints of the route between the two Workplaces via Footpaths which are connected with Connectors .

Specify true to compute the waypoints of the route in the area, i.e., the route of the Worker , who is walking freely within the area, would take.

**Default Value of the Parameter**

The default value is false.

**Return Value**

The return value is a two-dimensional array .

It contains the X-Coordinate , the Y-Coordinate , and the Z-Coordinate of the waypoints.

**Example**

```simtalk
var coords:any := Workplace1.getRouteCoordinates(Workplace2)
print coords // outputs [[6.59, -6.0, 0.0] [6.60, -7.40, 0.0] [9.40, -7.40, 0.0] [13.690, -6.0, 0.0]]
```

##### getRouteLength [SimTalk] - Workplace

Returns the length of the route which a Worker would have to cover to get from the Workplace designated by &lt;Path&gt; to another Workplace or to the WorkerPool .

Type

Method

Syntax

```simtalk
< Path >.getRouteLength(ToWorkplace:path[, FreelyWithinArea:boolean:=false]) → length
```

**Parameters**

- The parameter ToWorkplace of data type path designates the Workplace which is the destination Workplace .
- The optional parameter FreelyWithinArea of data type boolean sets if the Worker gets to the Workplace by walking freely within the area or not.

Accept the default value false or do not specify the parameter to compute the route length between the two Workplaces via Footpaths which are connected with Connectors .

Specify true to compute the route length in the area, i.e., the route of the Worker , who is walking freely within the area, would take.

**Default Value of the Parameter**

The default value is false.

**Return Value**

The return value has the data type length .

If Plant Simulation did not find a route, the return value is -1.

**Example**

```simtalk
var len:length := Workplace1.getRouteLength(Workplace2)
```

#### Read-Only Attributes of the Workplace

Read-Only Attributes of the Workplace

The Workplace provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyWorkplace.UUID
```

#### Attributes of the Workplace

\_Attributes of the Workplace

The Workplace provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:
- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyWorkplace.Station := MyStation
print MyWorkplace.Station
posit := Station.Cont.XPos
print MyPythonModule.Origin
```

##### AtEntrance [SimTalk]

Attaches the Workplace designated by &lt;Path&gt; to the entrance of the assigned material flow object ( true ) or not ( false ).

Remarks

Assigning a new station to a Workplace via SimTalk does not change the current assignment to the entrance or the exit.

Type

Attribute

Syntax

&lt; Path &gt;.AtEntrance:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyWorkplace.AtEntrance := true

See also

At Entrance [check box]

Model a Worker Who Waits for a Free Target

##### AtExit [SimTalk]

AtExit [SimTalk]

Attaches the Workplace designated by &lt;Path&gt; to the exit of the assigned material flow object ( true ) or not ( false ).

Remarks

Assigning a new station to a Workplace via SimTalk does not change the current assignment to the entrance or the exit.

Type

Attribute

Syntax

&lt; Path &gt;.AtExit:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyWorkplace.AtExit := true
```

See also

At Exit [check box]

Model a Worker Who Waits for a Free Target

##### Capacity [SimTalk] - Workplace

Sets the Capacity , i.e., the number of Workers that can stay on the Workplace designated by &lt;Path&gt; at any one time.

Remarks

The Capacity is an integer value greater than 0. The Capacity is important if several tasks can be accomplished on this Workplace or if these tasks come together there.

Plant Simulation uses the coordinate of the Workplace to find the shortest route to it, meaning that the Worker walks to this coordinate and then jumps to its animation point.

**Note**

You can only change the Capacity if the Workplace is empty.

Type

Attribute

Syntax

```simtalk
< Path >.Capacity:integer
```

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyWorkplace.Capacity := 4
```

See also

Capacity [text box] - Workplace DistanceInQueue [SimTalk]

Sets the distance between the Workers in the queue on the animation path of the Workplace designated by &lt;Path&gt;.

Remarks

The Workers attempt to keep this distance while they wait in line to step onto the Workplace and do their job.

Type

Attribute

Syntax

&lt; Path &gt;.DistanceInQueue:length

Assignment Value

You can assign a value of data type length .

Example

.Resources.Worker:1.DistanceInQueue := 1 // 1 meter

See also

Distance in Queue

How Workers Queue Up in Front of the Workplace

##### EntranceCtrl [SimTalk] - Workplace

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation run the Method when the Worker has entered the object.

Type

Attribute

Syntax

< Path >.EntranceCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
MyWorkplace.EntranceCtrl := &myEntranceCtrl
// Entrance control of the workplace WP_Arrival if (NOT Arrival.WorkerWasOrdered) AND Arrival.occupied AND Arrival.cont.finished
var WorkerTab:object := AssignedWorkers
for var j := 1 to WorkerTab.yDim
	if WorkerTab[1,j] = @
		WorkerTab[2,j] := true // assigned Arrival.cont.move(@)
		waituntil Arrival.succ.~.WP_buffer.entranceFree
		@.goto(Arrival.succ.~.WP_buffer)
		return
	end
next
end
// Entrance control of the Workplace WP_Shipping
for var j := 1 to AssignedWorkers.yDim
	var Worker:object := AssignedWorkers[1,j]
	if Worker = @
		waituntil Shipping.empty
		AssignedWorkers[2,j] := false // unassigned
		@.cont.move(Shipping)
		waituntil WP_Arrival.entranceFree
```

**EntranceCtrl [SimTalk] - Workplace**

Worker.goto(WP_Arrival)

exitloop end next

**See also**

**Entrance Control [Workplace]**

ExitCtrl [SimTalk] - Workplace

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method as soon as the Worker exits the Workplace .

Type

Attribute

Syntax

&lt; Path &gt;.ExitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyWorkplace.ExitCtrl := &amp;myExitControl

See also

Exit Control [Workplace]

**LoadCtrl [SimTalk]**

##### LoadCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

The Load Control sets how the part is transferred from the work station , the source object, to the Worker staying on the attached Workplace . After picking the part up, the Worker carries it to the target object.

Plant Simulation runs the Load Control as soon as the Worker enters the Workplace .

The standard load control as a user-defined attribute looks like this:

```simtalk
// workplace load control ... // ... to transfer MUs from the associated station to the worker on the workplace // @: worker // ?: workplace
if @.failed = false and @.pause = false // get the first MU to exit and repeat this until no MU is about to exit
	var mu:object := ?.station.cont
	while mu /= void and @.full = false // transfer the exiting MU to the worker
		mu.move(@) // with configured load time on workplace, wait for EndOfTime event causing the transfer to worker waituntil mu.~ = @
		mu := ?.station.cont
	end
end
```

Type

Attribute

Syntax

< Path >.LoadCtrl:method

Assignment Value

You can assign a value of data type method .

**Example**

```simtalk
MyWorkplace.LoadCtrl := &myLoadControl
```

**See also**

Load Control LoadingTime [SimTalk] - Workplace Sets the Loading Time of the Workplace designated by &lt;Path&gt;.

**Remarks**

The Loading Time is the time it takes the Worker for picking up a part at the Workplace . After the Loading Time has elapsed, the Worker waits for the Maximum Dwell Time to pass if he still has carrying capacity. If not, he immediately carries the part to the target station and places it there. If the Worker is to load more than one part , the Maximum Dwell Time should at least be as long as the carrying capacity times the Loading Time .

Use the anonymous identifier @ to access the part for which the loading time applies.

**Note**

During the Loading Time no part can be placed onto the delivering station.

**Note**

Behavior during interruptions of the Worker

Plant Simulation extends the Loading Time by Failure Times of the Worker . The processing station remains locked during the failure.

If the Worker pauses during the Loading Time , Plant Simulation cancels loading and considers it as completely elapsed. This means that the Worker carries at least one part to the WorkerPool . When the shift ends during the Loading Time , Plant Simulation cancels the Loading Time and considers it as completely elapsed. This means that the Worker carries at least one part to the parts buffer .

**Note**

The entrance of the Workplace is closed while its Loading Time is running as the Worker functions with reservations for the Workplace .

**Note**

Behavior during interruptions of the processing station

Failures of the processing station do not affect loading the part by the Worker . The part is already located at the Worker and loading takes place during the failure.

The same applies for processing stations which are stopped , paused , or unplanned .

Type

Attribute

Syntax

&lt; Path &gt;.LoadingTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyWorkplace.LoadingTime := 10:00
```

SimTalk

UnloadingTime [SimTalk] - Workplace

See also

Loading Time [Workplace]

Maximum Dwell Time [transport importer]

**PickDropAtStore [SimTalk]**

##### PickDropAtStore [SimTalk]

Sets what the Worker does when he walks to a Workplace attached to a Store , when picking up or dropping parts at this Store .

Type

Attribute

Syntax

&lt; Path &gt;.PickDropAtStore:string

**Assignment Value**

You can assign a value of data type string .

**You can specify:**

- "Walk to Workplace" : Is the default setting that previous versions of Plant Simulation implicitly provided. The Worker walks to the Workplace to pick up parts or to drop parts.

For this setting, all settings of the Workplace are available.

<!-- image -->

**Note**

Plant Simulation only considers route computations with the methods getRouteLength and getRouteCoordinates for the setting Pick/Drop at Store &gt; Walk to Workplace .

For the other settings of Pick/Drop at Store the method getRouteLength will return -1 and getRouteCoordinates will return an empty array.

- "Walk to Store Column" : The Worker walks to the store column to pick up or to drop parts. The Worker can walk to the store column without any restrictions.

<!-- image -->

For this setting the following features are not available:

- You cannot enter a Capacity .

We assume the Capacity to be infinite.

- You cannot select Worker Stays Here After Completing the Job .
- You cannot enter the Distance in Queue .
- You cannot select Walk to the End of the Animation Path of the Queue .
- You cannot select Walk Along the Animation Path of the Queue .

Plant Simulation determines the locations to which the Worker walks by the dimensions of the side of the Store at which the Workplace is placed, by the number of columns at that side, and by the distance of the center point of the Workplace to the Store itself.

In addition, Plant Simulation uses the distance of the center point of the Workplace to the store front to place the pick or drop locations in front of the store column.

Walk to Store Column uses all pick or drop locations in front of the Store for computing the routes of the Workers . Be aware that large Stores with many columns will increase the complexity of the route computations and will impact performance.

- "Walk Along Store to Store Column" : The Worker walks to the first or last column at the side of the Store where the Workplace is placed. Then the Worker extends his route and continues to walk along the Store to the store column to drop a part or pick up a part. Thus the routes to the store columns are restricted and each store column can only be reached from the previous or next store columns, except for the first and last store column. The Worker can walk to the first and last store columns without any restrictions.

When the Worker extends his route from the first or last store column, he ignores all obstacles within his route.

<!-- image -->

For this setting the following features are not available:

- You cannot enter a Capacity .

We assume the capacity to be infinite.

- You cannot select Worker Stays Here After Completing the Job .
- You cannot enter the Distance in Queue .
- You cannot select Walk to the End of the Animation Path of the Queue .
- You cannot select Walk Along the Animation Path of the Queue .
- Plant Simulation determines the locations to which the Worker walks by the dimensions of the side of the Store at which the Workplace is placed, by the number of columns at that side, and by the distance of the center point of the Workplace to the Store itself.

The diagram of the location to which the Worker walks looks like this:

<!-- image -->

Walk Along Store to Store Column does not increase the number of commonly reachable locations for the route calculation in the same way as the setting Walk to Store Column does. Thus, performance impact should be smaller.

**Example**

```simtalk
MyWorkplace.PickDropAtStore := "Walk to Store Column"
var behavior:string := MyWorkplace.PickDropAtStore // -> "Walk to Store Column"
```

SimTalk DistanceInQueue [SimTalk] WalkAlongQueuePath [SimTalk] WalkToQueuePathEnd [SimTalk] WorkerStaysHere [SimTalk] See also Pick/Drop at Store

Model a Worker Picking Parts Up at/Placing Parts in a Store RecoveryTime [SimTalk]- Workplace Sets the duration of the Recovery Time of the Workplace designated by &lt;Path&gt;.

Remarks

You can only define a Recovery Time for a Workplace that has a Capacity of 1 . The Recovery Time starts when a Worker leaves the Workplace .

The Recovery Time will not take effect, if you set the Workplace as the Home Location of a Worker and if the Worker wants to step onto this Home Location / Workplace .

Type

Attribute

Syntax

&lt; Path &gt;.RecoveryTime:time

Assignment Value

You can assign a value of data type time .

Example

MyWorkplace.RecoveryTime := 0.10

SimTalk

HomeLocation [SimTalk] - Worker

See also

Home Location

Recovery Time [Workplace]

Capacity [SimTalk] - Workplace

##### Station [SimTalk]

Sets the name of the Station , i.e., the material flow object, to which you want to assign the Workplace designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Station:path

Assignment Value

You can assign a value of data type path .

Example

MyWorkplace.Station := MyStation

See also

Station [Workplace]

**SupportedServices [SimTalk]**

##### SupportedServices [SimTalk]

Sets or returns the list of the Supported Services of the Workplace designated by &lt;Path&gt;.

Remarks

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

Type

Attribute

Syntax

```simtalk
< Path >.SupportedServices
-> string[]
```

**Assignment Value**

You can assign an array of data type string that contains the supported services.

Examples

```simtalk
var a :
string[] := ["standard service", "drill"]
Workplace.SupportedServices := a
print MyWorkplace.SupportedServices
```

See also

Supported Services [button]

Relational Operators

##### UnloadCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

The Unload Control sets how the Worker places the part , which he carried to the Workplace , onto the attached work station .

Plant Simulation runs the Method as soon as the Worker enters the Workplace attached to the target station.

The standard unload control as a user-defined attribute looks like this:

```simtalk
// workplace unload control ... // ... to transfer all MUs from a worker on the workplace to the associated station // @: worker // ?: workplace
if @.failed = false and @.Pause = false // remember the station associated to the workplace
	var station:object := ?.station // get the first MU about to exit to repeat this until no MU wants to exit anymore
	var mu:object := @.cont
	while mu /= void and station.full = false // wait until the entrance is free (for example for conveyors)
		waituntil station.EntranceFree // transfer the MU from the carrying worker to the station
		mu.move(station) // with configured unload time on workplace, wait for EndOfTime event causing the transfer from worker to station waituntil mu.~ = station
		mu := @.cont
	end
end
```

**Type**

Attribute

Syntax

< Path >.UnloadCtrl:method

**UnloadCtrl [SimTalk]**

**Assignment Value**

You can assign a value of data type method .

**Example**

MyWorkplace.UnloadCtrl := &amp;myUnloadControl

See also

Unload Control UnloadingTime [SimTalk] - Workplace Sets the Unloading Time at the Workplace designated by &lt;Path&gt;.

Remarks

The Unloading Time is the time it takes the Worker for placing the part, which he picked up at another station, onto target station.

If the Worker is to unload several parts , the Unloading Time accrues for each part .

You can use the anonymous identifier @ to access the part for which the unloading time applies.

**Note**

Behavior during interruptions of the Worker

Plant Simulation extends the Unloading Time by failure times of the Worker . The target processing station remains locked during the failure .

If the Worker pauses during the Unloading Time , Plant Simulation cancels unloading. The target processing station does not remain locked, and the Worker takes the parts to the WorkerPool with him. After the pause is over, unloading starts anew.

If the shift ends during the Unloading Time , Plant Simulation cancels the Unloading Time and the Worker carries the part to the parts buffer . The target processing station does not remain locked.

**Note**

Behavior during interruptions of the processing station through a failure, pause, etc.

The Worker only starts unloading when the target processing station can take on the part for processing. If this is not the case, Plant Simulation enters the part to be unloaded into the Forward Blocking List . The Unloading Time starts after the interruption is over.

The Worker continues unloading the part if the target processing station is being interrupted during the Unloading Time . Plant Simulation also enters the part to be unloaded into the Forward Blocking List if the target processing station cannot accept a part at the time of the actual unloading process (after the Unloading Time has elapsed). The part stays with the Worker . After the interruption has been removed, the Worker deposits the part at the target processing station without any time delay.

Type

Attribute

**Syntax**

&lt; Path &gt;.UnloadingTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyWorkplace.UnloadingTime := 10:00
```

SimTalk

LoadingTime [SimTalk] - Workplace

See also

Unloading Time [Workplace]

##### WalkAlongQueuePath [SimTalk]

Sets if the Worker walks along the animation path of the queue to the end of the animation path of the queue of the Workplace designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

When the Worker has reached the end of the MU Animation Path , Plant Simulation computes the route to the target, the waiting position , or to the Workplace along the MU Animation Path .

This setting is only relevant, if you also set WalkToQueuePathEnd to true .

Type

Attribute

Syntax

```simtalk
< Path >.WalkAlongQueuePath:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyWorkplace.WalkToQueuePathEnd := true
MyWorkplace.WalkAlongQueuePath := true
```

SimTalk

WalkToQueuePathEnd [SimTalk]

See also

Walk to the End of the Animation Path of the Queue WalkToQueuePathEnd [SimTalk]

Sets if the Worker walks along the animation path of the queue to the end of the animation path of the queue of the Workplace designated by &lt;Path&gt; ( true ) or not ( false ).

Remarks

WalkToQueuePathEnd is relevant, if you also set WalkAlongQueuePath to true .

Type

Attribute

Syntax

```simtalk
< Path >.WalkToQueuePathEnd:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyWorkplace.WalkToQueuePathEnd := true
MyWorkplace.WalkAlongQueuePath := true
```

SimTalk

WalkAlongQueuePath [SimTalk]

See also

Walk Along the Animation Path of the Queue

##### WorkerStaysHere [SimTalk]

Sets if the Worker stays at the Workplace designated by &lt;Path&gt; after completing his job ( true ), or if he returns to the WorkerPool or to the Home Location if you configured one ( false ).

Remarks

You have to set the attribute to false if you activate the setting GetJobOrdersAtHomeOnly in the WorkerPool .

**Note**

A Worker who is not automatically brokered stays at the Workplace to which he was sent, no matter if you activated Worker Stays Here After Completing the Job / WorkerStaysHere or not in the Workplace .

**Note**

If a Worker stays on a Workplace while another Worker has to work on it, and if the Capacity of the Workplace is used up, Plant Simulation shoves the Worker aside who is not working. This Worker then exits the Workplace and returns to the WorkerPool or to the Home Location if you configured one.

Attribute

Type

Attribute

Syntax

&lt; Path &gt;.WorkerStaysHere:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyWorkplace.WorkerStaysHere := true

SimTalk

GetJobOrdersAtHomeOnly [SimTalk]

