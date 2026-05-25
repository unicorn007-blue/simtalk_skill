### TransferStation

Use the TransferStation for loading, unloading, and reloading parts.

**Icon**

<!-- image -->

To add the TransferStation to the Class Library , click Transfer Station on the Home ribbon tab.

<!-- image -->

Manage Class Library &gt; Libraries &gt; Tools &gt;

<!-- image -->

**Description**

You can use the TransferStation to:

- Load parts: In this constellation the TransferStation gets the parts from the parts station and loads them onto a means of transport ( Container or Transporter ), which has to be located on the target station. Loading starts as soon as part and means of transport are ready.

The means of transport ( Container or Transporter ), which is located on the target station, only stops if it has sufficient capacity and if parts (in case of type-specific loading) are present that can be loaded/ moved. If the means of transport is to stop to wait for parts, you have to select the check box Always stop container on the tab Advanced Attributes .

- Unload parts: In this constellation the TransferStation unloads the parts from a means of transport ( Container or Transporter ), which is located on the parts station, and places them onto the target station. Unloading starts as soon as a means of transport is ready on the parts station.

The means of transport ( Container or Transporter ) which is located on the part station only stops if it transports at least one part. For type-specific or blockwise loading/unloading, the means of transport has to transport sufficient parts of the correct type so that it stops.

- Reload parts: In this constellation the TransferStation unloads the parts from a means of transport ( Container or Transporter ), which is located on the parts station, and places them onto a means of transport ( Container or Transporter ), which is located on the target station. Reloading starts as soon as both means of transport are ready.

The means of transport ( Container or Transporter ), which is located on the target station, only stops if it has sufficient capacity and if parts (of the correct type in case of type-specific loading) are present that can be loaded/moved. If the means of transport is to stop to wait for parts, you have to select the check box Always stop container on the tab Advanced Attributes.

The means of transport ( Container or Transporter ) which is located on the part station only stops if it transports at least one part. For type-specific or block-wise loading/unloading, the means of transport has to transport sufficient parts of the correct type so that it stops.

- Move parts: In this constellation the TransferStation moves the parts from the parts station onto the target station. Moving starts as soon as a part on the parts station is ready.

<!-- image -->

The parts station can be any one of these material flow objects: Source , Conveyor , TwoLaneTrack , Track , ParallelStation , Station , TransferStation , DismantleStation , Buffer , PlaceBuffer , and Portioner .

The target station can be any one of these material flow objects: Conveyor , TwoLaneTrack , Track , ParallelStation , Station , DismantleStation , Buffer , and PlaceBuffer .

For unloading and moving the target station can also be the Store , the Drain , and the DePortioner .

**Note**

You can only type in a Block size greater than 1, when the parts station is a ParallelStation for modeling a Loading and a Moving process.

For an Unloading and Reloading process, you can use any of the permitted stations as the block is not removed directly from the station but from a skid or from a Transporter on the station.

The TransferStation must be notified when the parts or means of transport are ready. When you use a Conveyor , a Track or a TwoLaneTrack this will be accomplished by a sensor control. For all other objects this notification is achieved via an exit control. For Conveyor , Track or TwoLaneTrack , the TransferStation creates a sensor and inserts PartSensorControl or TargetSensorControl respectively as sensor control. For any of the other objects the TransferStation inserts the methods PartExitControl , or TargetExitControl respectively as exit control. When you need your own exit control, you can type in it as a user-defined exit control into the dialog of the TransferStation . The TransferStation applies the settings you chose, when you close the dialog with OK.

The TransferStation is based on a ParallelStation whose properties we modified and enhanced. To open this ParallelStation , click Open Station on the tab Advanced Controls.

**Note**

We modeled the TransferStation as an application object. For this reason opening Help with F1 and What's This Help in the dialogs of the objects do not work. To open help for the object, select Help &gt; Help on TransferStation in its dialog.

We modeled the dialog of the TransferStation with the object Dialog . The window of the TransferStation does not use the standard Siemens PLM theme, but your Windows theme.

To assign the object another name or a label, click it with the right mouse button and select Rename .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

SimTalk

setPartStation

setStationtype

setTargetStation

See also

Load, Unload, and Reload Parts with the TransferStation

Configuring the TransferStation

Dialog Box of the TransferStation

#### Configuring the TransferStation

After you inserted the TransferStation and the associated part and target station you can:

- Define settings with drag-and-drop: Drag the parts station and the target station onto the TransferStation and drop it there. In the dialog, which opens, you can:
- Select what you want the TransferStation to do:
- ◊ Load parts onto a Container or onto a Transporter .
- ◊ Unload parts from a Container or from a Transporter .
- ◊ Reload parts from one Container or Transporter located on the parts station onto a Container or Transporter located on the target station.
- ◊ Move parts from one station to another station.
- Select if the dropped object is the Parts station ( Parts from ) or the Target station ( Target is on ).
- If the dropped object is a Track , a TwoLaneTrack or a Conveyor , you have to type in the Sensor position .
- If the dropped object is a Track or a TwoLaneTrack , you have to select, when you want to Activate the sensor. For a TwoLaneTrack , you also have to select on which Lane you want to create the sensor.
- Define settings in the dialog of the TransferStation : Select the Station type , the Parts station and the Target station as well as sensor positions . If your modeling situation requires it, you can also define additional settings.

#### Dialog Box of the TransferStation

Dialog Box of the TransferStation

Double-click the icon of the TransferStation to open its dialog box.

Edit Simulation Properties

There you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties :

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the 3D model and press the spacebar .

##### Tab Attributes

See also

Tab Advanced Attributes

Tab Advanced Controls

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Station type

Select what you want the TransferStation to accomplish below Station type .

Depending on your selection, the TransferStation activates or deactivates options on the Tab Advanced Attributes .

<!-- image -->

- Load parts . The TransferStation gets the parts from the parts station and loads them onto a means of transport ( Container or Transporter ), which has to be located on the target station. Loading starts as soon as part and means of transport are ready.

To load the parts onto a means of transport, select this radio button.

- Unload parts . The TransferStation unloads the parts from a means of transport ( Container or Transporter ), which is located on the parts station, and places them onto the target station. Unloading starts as soon as a means of transport is ready at the parts station.

To unload the means of transport, select this radio button.

- Reload parts . The TransferStation unloads the parts from a means of transport ( Container or Transporter ), which is located on the parts station, and places them onto a means of transport ( Container or Transporter ), which is located on the target station. Reloading starts as soon as both means of transport are ready.

To reload parts, select this radio button.

- Move parts . The TransferStation unloads the parts from the parts station and loads them onto the target station. Transferring starts as soon as a part on the parts station is ready.

**Note**

A TransferStation , which you inserted into a Frame , shows the station type, the part station, and the target station in the Tooltip .

<!-- image -->

SimTalk

setStationtype

**Station type**

**getStationtype**

###### Parts from

Type in from which station the TransferStation gets the MUs .

The MUs can also be located on a means of transport on the parts station. You can also drag that object, i.e., the parts station, over the icon of the TransferStation and drop it there.

<!-- image -->

The parts station can be any one of these material flow objects: Source , Conveyor , TwoLaneTrack , Track , ParallelStation , Station , AssemblyStation , DismantleStation , Buffer , and PlaceBuffer .

**Note**

A TransferStation , which you inserted into a Frame , shows the station type, the part station, and the target station in the Tooltip .

<!-- image -->

**SimTalk**

setPartStation

getPartStation

**Sensor position [parts from]**

###### Sensor position [parts from]

Type in the position of the sensor on the object from which the TransferStation gets the MUs .

<!-- image -->

###### Lane [parts from]

When the parts station is a TwoLaneTrack , you also have to select on which lane you want to insert the sensor or the pair of sensors.

**On:**

- Lane A : Inserts the sensor only on lane A at the Sensor position .
- Lane B : Inserts the sensor only on lane B.
- Lane A and Lane B : Inserts the pair of sensors on lane A and lane B, starting at the 0-position of lane A.
- Lane B and Lane A : Inserts the pair of sensors on lane B and lane A, starting at the 0-position of lane B.

<!-- image -->

<!-- image -->

**Target is on**

###### Target is on

Type in onto which target the TransferStation places the MUs .

When loading or reloading parts, the MUs will be located on a means of transport on the target station. You can also drag that object, i.e., the target station, over the icon of the TransferStation and drop it there.

<!-- image -->

The target station can be any one of these material flow objects: Drain , Conveyor , TwoLaneTrack , Track , ParallelStation , Station , DismantleStation , Buffer , and PlaceBuffer .

**Note**

A TransferStation , which you inserted into a Frame , shows the station type, the part station, and the target station in the Tooltip .

<!-- image -->

**SimTalk**

**setTargetStation**

getTargetStation

###### Sensor position (target is on)

Type in the position of the sensor on the object onto which the TransferStation places the MUs .

To successfully transfer the MU onto the target station, you have to make sure that the target station provides enough space to accommodate the incoming MU .

<!-- image -->

The sensor position 0.0 is an exception: Although the target station theoretically does not provide enough space, the MU can still move onto the target station.

<!-- image -->

**Lane (target on)**

###### Lane (target on)

When the parts station is a TwoLaneTrack , you also have to select on which lane you want to insert the sensor or the pair of sensors.

**On:**

- Lane A : Inserts the sensor only on lane A at the Sensor position .
- Lane B : Inserts the sensor only on lane B.
- Lane A and Lane B : Inserts the pair of sensors on lane A and lane B, starting at the 0-position of lane A.
- Lane B and Lane A : Inserts the pair of sensors on lane B and lane A, starting at the 0-position of lane B.

<!-- image -->

<!-- image -->

Tab Times

Tab Times

The tab Times provides these settings:

Processing time [TransferStation]

Recovery time [TransferStation]

<!-- image -->

**Processing time [TransferStation]**

###### Processing time [TransferStation]

Type the constant processing time, which the TransferStation uses.

<!-- image -->

If you want to use one of the other distributions, click Open Station on the tab Advanced Controls , select the distribution and type in the parameters, which define it, in the dialog of the ParallelStation .

**SimTalk**

Processing time

###### Recovery time [TransferStation]

Type the constant recovery time, which the TransferStation uses.

<!-- image -->

If you want to use one of the other distributions, click Open Station on the tab Advanced Controls , select the distribution and type the parameters, which define it, in the dialog of the ParallelStation .

**SimTalk**

**Recovery time**

Tab Failures

Tab Failures

The tab Failures of the TransferStation provides these settings:

<!-- image -->

**Availability**

**MTTR**

If you do not want to work with the Availability , but want to type in the Interval and the Duration , click Open Station on the tab Advanced Controls and clear the check box Availability on the tab Failures of the ParallelStation . Plant Simulation propagates any changes you make to the respective other object.

By default, the Availability of the TransferStation is activated. If you do not want to use the default settings, type in the values of your choice.

**Availability [TransferStation]**

###### Availability [TransferStation]

Type the availability of the TransferStation .

<!-- image -->

This is a number between 0 and 100 percent. Availability is the proportion of time during which a machine is in an operable state. Availability is based on a combination of MTBF and MTTR .

You can type in the availability here or on the tab Failures of the ParallelStation . Plant Simulation propagates any changes you make to the respective other object.

###### MTTR [TransferStation]

Type the M ean T ime T o R epair (MTTR) of the TransferStation . The mean time to repair is a measure of maintainability. It is the average time required to repair it.

<!-- image -->

You can type in the MTTR here or on the tab Failures of the ParallelStation . Plant Simulation propagates any changes you make to the respective other object.

Tab Advanced Attributes

##### Tab Advanced Attributes

The tab Advanced Attributes provides the settings listed in the table of contents to the left.

<!-- image -->

**Load/unload all blocks**

###### Load/unload all blocks

To load or unload each and every part from the means of transport, select the check box all . To only load or unload a certain amount of parts, clear the check box.

Then, type the number of parts into the text box Load/unload x blocks .

<!-- image -->

###### Load/unload x blocks

If you clear the check box Load/unload all blocks , you have to type in the number of parts to be loaded or unloaded into the text box.

<!-- image -->

**Note**

The means of transport, onto which the parts are reloaded or loaded , drives on as soon as the number of parts, which you type in here, is reached. The means of transport, from which the parts are unloaded or reloaded only drives on, when the means of transport is Empty or when you selected the setting Specific type , and when no more compatible parts are located on it.

SimTalk

Partnumber

See also

Load/unload all blocks

**Block size**

###### Block size

Type the number of parts, which you want to load or unload en bloc into this text box.

When you type in 4 , for example, the TransferStation handles four parts in a single step.

A block is the number of parts, which is loaded or unloaded all at once, and which you type into the text box Block size . This means that Plant Simulation does not compute the time or loading and unloading per part, but for the block as a whole.

<!-- image -->

**Note**

You can only type in a Block size greater than 1, when the parts station is a ParallelStation for modeling a Loading and a Moving process.

For an Unloading and Reloading process, you can use any of the permitted stations as the block is not removed directly from the station but from a pallet or from a Transporter on the station.

SimTalk

setBlocksize

getBlocksize

###### Specific type

To only load or unload parts of a certain type from the means of transport, select this check box.

<!-- image -->

Then, click Open Table and type these types of parts into the table.

SimTalk

TypeSpecific

**Open Table [TransferStation]**

###### Open Table [TransferStation]

When you only want to load/unload parts of a certain type onto/from a means of transport, click Open Table . Then, type the Part Type into the cells of column 1 of the table, enter the Container Type into the cells of column 2.

<!-- image -->

The TransferStation only takes parts from the column Part Type from the parts station; when loading and moving it takes them directly from the parts station, when unloading and reloading it takes them from the means of transport. When loading and reloading parts, you have to type in the type of means of transport into the cells of the column Container Type , onto which you want to load the part. Remember that you define the names of the parts in the column Name of the Sequence Table in the object Source .

<!-- image -->

**SimTalk**

TypeTable

###### Homogeneous loading

To only load parts of a single type, select this check box.

<!-- image -->

The first loaded part determines, which part type will be loaded onto the means of transport. If you use type-specific loading, this check box only has an effect, when several part types will be loaded onto a single type of means of transport.

SimTalk

HomogeneousTarget

**Always stop container**

###### Always stop container

To always stop the target Container or Transporter at the station, no matter if there are enough parts of the right type to be loaded or not, select this check box.

<!-- image -->

**SimTalk**

AlwaysStopTarget

###### Behavior for failures

The setting Behavior for failures sets if the parts or targets stop, when the TransferStation is failed.

- To stop the part, select Stop container on part station .
- To stop the target, select Stop container on target station .

Tab Advanced Controls

Tab Advanced Controls

The tab Advanced Controls provides the settings listed in the table of contents to the left.

**Part sensor**

###### Part sensor

The TransferStation shows the sensor ID of the sensor on the parts station, where the parts stop.

<!-- image -->

###### Activate [TransferStation, part sensor]

When you define a sensor for a Track , you can select when a Transporter passing over it triggers the sensor.

- Always , independent of the destination of the Transporter .
- Or only when the Transporter has the same destination , as the one which you typed into the sensor.

<!-- image -->

**Target sensor**

###### Target sensor

The TransferStation shows the sensor ID of the sensor on the target station.

<!-- image -->

###### Activate [TransferStation, target sensor]

When you define a sensor for a Track , you can select when a Transporter passing over it triggers the sensor.

- Always , independent of the destination of the Transporter .
- Or only when the Transporter has the same destination , as the one which you typed into the sensor.

<!-- image -->

###### User-defined control for the parts

Type in the name of the Method in which you defined the conditions when a part exits a point-oriented station, which provides the parts for the TransferStation .

For the length-oriented objects the control will be called, when the part continues its way at the sensor. You might, for example, define conditions what will happen with the Empty container/transporter after the parts have been unloaded.

When you specify a boolean parameter in the user-defined control, Plant Simulation also calls the method , when a part arrives at the object.

User-defined controls might, for example, look like this:

```simtalk
// example for point-oriented objects (leavingPart : boolean) if leavingPart then
@.move
end
// example for the lenght-oriented object Conveyor (leavingPart : boolean) if leavingPart then
@.Stopped := false
else
	@.Stopped:= true
end
```

<!-- image -->

Or click , navigate to the Frame in which you stored the Method and select it there.

SimTalk

UserPartExitCtrl

###### User-defined control for the targets

Type in the name of the Method in which you defined the conditions when a target ( Container or Transporter ) exits a point-oriented station, which provides the targets ( Container or Transporter ) for the TransferStation .

For the length-oriented objects the control will be called, when the target continues its way at the sensor. You might, for example, define conditions what will happen with the full container/transporter after the parts have been loaded.

When you type a boolean parameter into the user-defined control, Plant Simulation also calls the method , when a target arrives at the object.

User-defined controls might for example look like this:

```simtalk
// example for point-oriented objects (leavingPart:boolean) if leavingPart then
@.move
end
// example for the lenght-oriented object Conveyor (leavingPart:boolean) if leavingPart then
@.Stopped:=false
else
	@.Stopped:=true
end
```

Or click , navigate to the Frame in which you stored the Method and select it there.

SimTalk

**UserTargetExitCtrl**

**User-defined control**

###### User-defined control

Type in the name of the Method , which will be called before the parts are moved onto the TransferStation and before the parts leave the TransferStation again.

Or click , navigate to the Frame in which you stored the Method and select it there.

A user-defined control might look like this:

```simtalk
(i : integer)
if i = 1 then // before starting the transfer to the TransferStation // parts/target are ready
elseif i = 2 then // before parts leaving the TransferStation
end
```

**SimTalk**

**UserCtrl**

###### Open Station

To open the ParallelStation on which the TransferStation is based, click this button.

You can define the behavior of the TransferStation here, for example the Processing time and the Recovery time .

See also

Processing time of the TransferStation

Recovery time of the TransferStation

ParallelStation

##### Tab Statistics

Tab Statistics [TransferStation]

The tab Statistics provides the dialog item Statistics Table .

It also shows these statistics values on the tab.

| Item               | Description                                                                                                                                                                                                                                                                                                               |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Working            | Shows the portion of the statistics collection period during which the TransferStation was working.                                                                                                                                                                                                                       |
| Waiting            | Shows the portion of the statistics collection period during which the TransferStation was waiting.                                                                                                                                                                                                                       |
| Waiting for parts  | Shows the portion of the statistics collection period during which the TransferStation was waiting for parts. The TransferStation spent time waiting for parts, which it will load onto a Container or a Transporter .                                                                                                    |
| Waiting for target | Shows the portion of the statistics collection period during which the TransferStation was waiting for a target, i.e., a Container or a Transporter . The TransferStation spent time waiting for a target ( Container or Transporter ), i.e., the parts are present, but the Container or Transporter is not present yet. |
| Blocked            | Shows the portion of the statistics collection period during which the TransferStation was Blocked .                                                                                                                                                                                                                      |
| Failed             | Shows the portion of the statistics collection period during which the TransferStation was Failed .                                                                                                                                                                                                                       |

###### Tab Statistics [TransferStation]

| Item      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| Paused    | Shows the portion of the statistics collection period during which the TransferStation was Paused .    |
| Unplanned | Shows the portion of the statistics collection period during which the TransferStation was Unplanned . |
| Entries   | Shows the number of parts, which entered the TransferStation .                                         |

###### Statistics Table [TransferStation]

To open the table showing the different states, which the TransferStation was in, click Statistics Table .

| Item English       | Description                                                                                                                  | Item German         |
|--------------------|------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Value              | Shows the name of the value of the User-defined Attribute .                                                                  | Wert                |
| Frequency          | Shows the number of occurrences of the value from the column Value .                                                         | Häufigkeit          |
| Duration           | Shows the duration of the occurrences, which is the complete duration the Value had during the statistics collection period. | Dauer               |
| %_Frequency        | Shows the portion of the individual frequencies of the sum of all values in the column Frequency .                           | %_Häufigkeit        |
| %_Duration         | Shows the portion of the individual durations to the sum of all values in the column Duration .                              | %_Dauer             |
| Mean Duration      | Shows the mean duration of the individual durations.                                                                         | Mittlere Dauer      |
| Standard Deviation | Shows the standard deviation of the duration.                                                                                | Standardabweic hung |

**Navigate Menu**

##### Navigate Menu

The Navigate Menu provides the command Open Location .

##### View Menu

The View Menu provides the command Refresh [on View menu] . SimTalk updateDialog [SimTalk]

**Help Menu**

##### Help Menu

The Help Menu provides these menu commands:

**Contents**

Help on Object

**Methods of the TransferStation**

#### Methods of the TransferStation

The TransferStation provides:

- The methods listed in the table of contents to the left.
- The Methods of the Material Flow Objects .
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

##### finishLoading [SimTalk]

Cancels the loading process of the TransferStation designated by &lt;Path&gt;.

Remarks

Use this method to send the target, for example a pallet, which is only loaded in part, on to its destination because some station along the way is failed.

Type

Method

Syntax

&lt; Path &gt;.finishLoading

**Example**

MyTransferStation.finishLoading

**finishLoading [SimTalk]**

##### getBlocksize [SimTalk]

Returns the block size, i.e., the number of parts, which the TransferStation designated by &lt;Path&gt; loads or unloads en bloc.

Remarks

A block is the number of parts, which is loaded or unloaded all at once, and which you type into the text box block size . This means that Plant Simulation does not compute the time or loading and unloading per part, but for the block as a whole.

**Note**

You can only type in a Block size greater than 1, when the parts station is a ParallelStation for modeling a Loading and a Moving process.

For an Unloading and Reloading process, you can use any of the permitted stations as the block is not removed directly from the station but from a pallet or from a Transporter on the station.

Type

Method

Syntax

```simtalk
< Path >.getBlocksize → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
var b : integer
b := MyTransferStation.getBlocksize
```

See also

Block size

setBlocksize

**getPartStation [SimTalk]**

##### getPartStation [SimTalk]

Returns the parts station and the parameters of the parts station of the TransferStation designated by &lt;Path&gt; and writes them to the designated parameters.

Type

Method

Syntax

```simtalk
< Path >.getPartStation(SensorPosition:length, Activate:string, Lane:string, Control:string) → object
```

**Parameters**

- When the parts station is a Conveyor , Track or TwoLaneTrack the parameter SensorPosition of data type length designates the position of the sensor.
- When the parts station is a Track or TwoLaneTrack , the parameter Activate of data type string designates when the sensor is to be activated.
- When the parts station is a TwoLaneTrack , the parameter Lane of data type string designates on which Lane the sensor will be inserted.
- For any type of parts station, the parameter Control of data type string designates the user-defined control.

Return Value

The return value has the data type object .

Example

```simtalk
var p : object
var pos1 : length
var act,ctrl,lane: string
p := MyTransferStation.getPartStation(pos1,act,ctrl,lane)
```

See also

Parts from

setPartStation getStationtype [SimTalk]

Returns the type of the TransferStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getStationtype → string
```

Return Value

The return value has the data type string .

Load, Unload, Reload, or Move.

Example

```simtalk
var type : string
type := MyTransferStation.getStationtype
```

See also

Station type

setStationtype

##### getTargetStation [SimTalk]

getTargetStation [SimTalk]

Returns the target station and the parameters of the target station of the TransferStation designated by &lt;Path&gt; and writes them to the designated parameters.

Type

Method

Syntax

```simtalk
< >.getTargetStation(SensorPosition:length, Activate:string,
Path Lane:string, Control:string) → object
```

**Parameters**

- When the target station is a Conveyor , Track , or TwoLaneTrack the parameter SensorPosition of data type length designates the position of the sensor.
- When the target station is a Track or TwoLaneTrack , the parameter Activate of data type string designates when the sensor is to be activated.
- When the target station is of type TwoLaneTrack , the parameter Lane of data type string designates on which Lane the sensor will be inserted.
- For any type of target station, the parameter Control of data type string designates the user-defined control.

Return Value

The return value has the data type object .

Example

```simtalk
var p : object
var pos1 : length
var act,ctrl,lane : string
p := MyTransferStation.getTargetStation(pos1,act,ctrl,lane)
```

See also

Target is on

setTargetStation setBlocksize [SimTalk]

Sets the block size of the TransferStation designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setBlocksize(Blocksize:integer) → integer

Parameter

The parameter Blocksize of data type integer designates the number of parts, which you want the TransferStation to load or to unload en bloc

A block is the number of parts, which is loaded or unloaded all at once, and which you type into the text box block size . This means that Plant Simulation does not compute the time or loading and unloading per part, but for the block as a whole.

The default setting is 1.

For an Unloading and Reloading process, you can use any of the permitted stations as the block is not removed directly from the station but from a pallet or from a Transporter on the station.

**Note**

You can only type in a Block size greater than 1, when the parts station is a ParallelStation for modeling a Loading and a Moving process.

Return Value

The return value has the data type integer .

Example

MyTransferStation.setBlocksize(3)

See also

Block size

getBlocksize

##### setPartStation [SimTalk]

Sets the parts station of the TransferStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setPartStation(PartsStation:object,SensorPosition:length, ActivateSensor:string, Lane:string,UserControl:string) → boolean
```

**Parameters**

- The parameter PartsStation of data type object designates the parts station as such.
- The parameter SensorPosition of data type length designates the position of the sensor, when the parts station is a Conveyor , a Track or a TwoLaneTrack .
- The parameter ActivateSensor of data type string designates when the TransferStation activates the sensor, when the parts station is a Track or a TwoLaneTrack .
- The parameter Lane of data type string designates the Lane on which the sensor will be inserted, when the target station is a TwoLaneTrack .
- The parameter UserControl of data type string designates the name of the user-defined control, which you can enter for all objects serving as parts station.

**Return Value**

The return value has the data type boolean .

false if the parts station does not exist at all or if you entered an object, which is not accepted.

**Example**

```simtalk
var obj : object
obj := .ApplicationObjects.TransferStation.derive(.Models.MyFrame)
obj.setStationtype("Load")
obj.setPartStation(MyTwolaneTrack,4,"","","B+A")
obj.setTargetStation(MyStation,0,"","","")
obj.setBlocksize(1)
```

**See also**

**Parts from**

getPartStation setStationtype [SimTalk]

Sets the type of the TransferStation designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setStationtype(StationType:string)

Parameter

The parameter StationType of data type string designates the station type: Load , Unload , Reload or Move .

Example

MyTransferStation.setStationtype("Load")

See also

Station type

getStationtype

##### setTargetStation [SimTalk]

setTargetStation [SimTalk]

Sets the target station of the TransferStation designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.setTargetStation(TargetStation:object, SensorPosition:length, ActivateSensor:string, UserControl:string, Lane:string)
-> boolean
```

**Parameters**

- The parameter TargetStation of data type object designates the target station as such.
- The parameter SensorPosition of data type length designates the position of the sensor, when the target station is a Conveyor , a Track or a TwoLaneTrack .
- The parameter ActivateSensor of data type string designates when the TransferStation activates the sensor, when the target station is a Track or a TwoLaneTrack . You can enter "Always" or "Only when Destination" .
- The parameter Lane of data type string designates the Lane on which the sensor will be inserted, when the target station is a TwoLaneTrack . You can enter "A" , "B" , "A+B" , or "B+A" .
- The parameter UserControl of data type string designates the name of the user-defined control, which you can enter for all objects serving as target station.

When entering the sensor position you have to make sure that the target station provides enough space to accommodate the incoming MU so that it can be transferred. The sensor position 0.0 is an exception: Although the target station theoretically does not provide enough space, the MU can still move onto the target station.

**Return Value**

The return value has the data type boolean .

false if the target station does not exist at all or if you entered an object, which is not accepted, the method .

**Example**

```simtalk
var obj : object
obj := .Tools.TransferStation.derive(.Models.MyFrame)
obj.setTargetStation(MyTwoLaneTrack,4,"","","B+A")
```

See also

getTargetStation

Target is on

##### Attributes of the TransferStation

Attributes of the TransferStation

The TransferStation provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .
- The Attributes of the Material Flow Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:

```simtalk
MyTransferStation.mttr := 100
```

- To get the value of an attribute, you might, for example, type:

```simtalk
print MyTransferStation.mttr
posit := Station.Cont.XPos
```

##### AlwaysStopTarget [SimTalk]

Sets if the means of transport of the TransferStation designated by &lt;Path&gt; always stops ( true ) if no parts or not the correct type of part are present.

Type

Attribute

Syntax

&lt; Path &gt;.AlwaysStopTarget:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTransferStation.AlwaysStopTarget:=true

See also

Always stop container

##### HomogeneousTarget [SimTalk]

Sets if the means of transport of the TransferStation designated by &lt;Path&gt; only loads parts of a single type ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.HomogenousTarget:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTransferStation.HomogenousTarget:=true

See also

Homogeneous loading

##### Partnumber [SimTalk]

Sets the number of blocks, which the TransferStation designated by &lt;Path&gt; is to load or unload.

Remarks

Specify -1 to load/unload all parts.

**Note**

The means of transport, onto which the parts are reloaded or loaded , drives on as soon as the number of parts, which you enter here, is reached. The means of transport, from which the parts are unloaded or reloaded only drives on, when the means of transport is empty or when you selected the setting specific type , and when no more compatible parts are located on it.

Type

Attribute

Syntax

&lt; Path &gt;.Partnumber:integer

Assignment Value

You can assign a value of data type integer .

Example

MyTransferStation.Partnumber:=15

See also

Block size

Empty , state

Specific type TypeSpecific [SimTalk]

Activates ( true ) or deactivates ( false ) if the TransferStation designated by &lt;Path&gt; loads or unloads a certain type of part only.

Type

Attribute

Syntax

&lt; Path &gt;.TypeSpecific:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyTransferStation.TypeSpecific := true

See also

Specific type TypeTable [SimTalk]

Sets the table in which you define, which parts the TransferStation designated by &lt;Path&gt; is to load or unload.

Remarks

Enter the part type in column 1 of the table, enter the container type in column 2. The TransferStation only takes parts from the column part type from the parts station when loading and moving it takes them directly from the parts station, when unloading and reloading it takes them from the means of transport. When loading and reloading parts, you have to enter the type of means of transport onto which you want to load the part.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.TypeTable:table

Assignment Value

You can assign a value of data type table .

Example

```simtalk
MyTransferStation.TypeTable := MyUnloadTable
```

See also

Open Table

**UserCtrl [SimTalk]**

##### UserCtrl [SimTalk]

Sets the name of the user-defined control , which will be called before the parts are moved onto the TransferStation designated by &lt;Path&gt; and before the parts leave the TransferStation again.

Type

Attribute

Syntax

&lt; Path &gt;.UserCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyTransferStation.UserCtrl := "myControl"

See also

User-defined control

##### UserPartExitCtrl [SimTalk]

Sets the name of the user-defined control for parts .

Remarks

In the control you can define the conditions when a part exits a point-oriented station, which provides the parts for the TransferStation . For the length-oriented objects the control will be called, when the part continues its way at the sensor. You might, for example, define conditions what will happen with the empty container/transporter after the parts have been unloaded.

Type

Attribute

Syntax

&lt; Path &gt;.UserPartExitCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyTransferStation.UserPartExitCtrl := "myPartExitControl"

See also

User-defined control for the parts

Empty , state

##### UserTargetExitCtrl [SimTalk]

Sets the name of the user-defined control for parts , i.e., the means of transport. In it you can define the conditions when a target ( Container or Transporter ) exits a point-oriented station, which provides the targets ( Container or Transporter ) for the TransferStation .

Remarks

For the length-oriented objects the control will be called, when the target continues its way at the sensor. You might, for example, define conditions what will happen with the full container/transporter after the parts have been loaded.

In the control you can define the conditions when a target ( Container or Transporter ) exits a point-oriented station, which provides the targets ( Container or Transporter ) for the TransferStation . For the lengthoriented objects the control will be called, when the target continues its way at the sensor. You might, for example, define conditions what will happen with the full container/transporter after the parts have been loaded.

Type

Attribute

Syntax

&lt; Path &gt;.UserTargetExitCtrl:method

Parameter

When you specify a boolean parameter in the user-defined control, Plant Simulation also calls the method, when a target arrives at the object.

Assignment Value

You can assign a value of data type method .

Example

MyTransferStation.UserTargetExitCtrl:="myTargetExitControl"

See also

User-defined control for the targets

