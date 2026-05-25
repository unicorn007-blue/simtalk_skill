### Exporter

#### Exporter [object]

Use the Exporter for providing and exporting services. It represents a group of people, whose individual members you cannot distinguish and whom you cannot address as individuals.

Icon

<!-- image -->

**Description**

The Exporter works together with the Broker and the Importers (see Tab Importer and Sub-tab Failure ) of the Station , the ParallelStation , the AssemblyStation , and the DismantleStation . The Exporter offers services and provides them for Importers .

A single Broker manages the Exporter and assigns it to an Importer . After the Exporter has finished providing its service, it registers as being available with its Broker which will assign it to other Importers as soon as its services are required.

**Note**

If the Importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

Think of the Exporter as a group of people, whose individual members you cannot distinguish and whom you cannot address as individuals. To distinguish individual staff members, you have to model them with individual Exporters or Workers . An Exporter with a capacity greater than 1 can simultaneously provide services at several Importers . You can use the Exporter if transit times for traveled distances are not important for the simulation.

**Note**

An Exporter may provide services for several Importers at the same time.

To show a tooltip with information about the Exporter , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Exporter , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Exporter to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; Exporter on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

See also

Model Workers and the Jobs They Do

Model Workers with Importer, Broker, and Exporter

#### Dialog Box of the Exporter

Dialog Box of the Exporter

Double-click the icon of the Exporter to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Failed [check box] - material flow objects

Paused/Planned/Unplanned [material flow objects]

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Services [Exporter]

To open a list, into which you type the names of the services, which the Exporter exports, click this button.

<!-- image -->

- Before you can type in data, click the Inheritance check box so that it looks like this .
- Type the name of the service into the cell, and click Apply . The Exporter attempts to export the services in the order in which you type them into the list.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

Plant Simulation inserts these services into the list of offered services of the Broker : To view them, select View &gt; Offered Services .

You can use the commands on the Context Menu of Embedded Lists to edit the contents of the cells.

SimTalk

Services [SimTalk] - Exporter

hasService [SimTalk]

See also

Context Menu of Embedded Lists

Offered Services [Broker]

**Fail Services [text box]**

###### Fail Services [text box]

To interrupt the respective process for the duration of the failure if the Exporter provides services for an importer , select this check box.

If Plant Simulation interrupts processing, for example because of a failure of the Exporter , Plant Simulation deletes the respective Out event and adds it anew at the end of the failure according to the remaining processing time.

To not interrupt the respective process of the importer at the beginning of a failure if the Exporter provides services for an importer , clear Fail Services . The respective event thus persists. During a failure new requests to the Exporter remain unsatisfied.

SimTalk

##### FailServices [SimTalk]

See also

Sub-tab Processing &gt; Release All Services When One Of Them Is Failed [set-up importer]

Sub-tab Failure &gt; Release All Services When One Of Them Is Failed [failure importer]

###### Priority [Exporter]

Type in the Priority with which the Exporter carries out a work order.

<!-- image -->

The Priority of an Exporter is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. Plant Simulation provides an Exporter with Priority 10 before providing an Exporter with Priority 1.

Exporters with a higher priority will be brokered earlier by the Broker for identical services than Exporters with a lower priority. The Priority only applies to Exporters who are registered with the same Broker .

If several qualified Exporters with the same priority exist, who can provide the requested service, Plant Simulation first brokers the Exporters , who already stay on a suitable Workplace at the station. After that Exporters are brokered who already are at the station, but stay on the wrong Workplace . Then Exporters are brokered who are not staying on a Workplace . Finally, those Exporters are brokered who stay on a Workplace that is assigned to another station.

SimTalk

Priority [SimTalk] - Exporter

###### Capacity [text box] - Exporter

Capacity [text box] - Exporter

Type in the Capacity of the Exporter .

<!-- image -->

The capacity is a value greater than or equal to zero and designates the maximum number of services it can export.

**Note**

You can only reduce the capacity if the capacity provided to the importers is not fallen short of. If you increase the capacity, the Broker will immediately attempt to find new importers .

SimTalk

Capacity [SimTalk] - Exporter

###### Broker [Exporter]

Click the ellipsis button and select the Broker , who assigns the services to the Exporter , in the dialog Select Object .

<!-- image -->

Or type in the path to and the name of the Broker . You might, for example, type in .Models.Model.MyBroker .

Or select the Broker in a Frame , drag it to the text box and drop it there.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

Plant Simulation enters the Exporter into the list of administered Exporters which this Broker manages.

To view them, select View &gt; Exporters .

SimTalk

BrokerPath [SimTalk] - Exporter

See also

Broker [object]

Select Object

##### Tab Failures

Tab Failures

Define failures as described under the Tab Failures .

Tab Controls

Tab Controls [Exporter]

Define controls that set how the Exporter handles orders.

To create a control:

- Click and select a Method in the dialog Select Object .
- Select the Method in a Frame , drag it to the text box and drop it there.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

- Select Create Control and create the control as a Method of the object .

<!-- image -->

In addition, you can select the Shift Calendar , which controls the shifts during which the object works.

**See also**

Order Control [Exporter]

Release Control [Exporter]

###### Order Control [Exporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Order Control , which is called whenever the Exporter is assigned to an importer .

<!-- image -->

The Order Control sets how the Exporter/Worker handles the order

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

The Order Control has two parameters, which define the importer :

- The parameter Importer of data type object designates the importer .
- The parameter Type of data type integer designates its type: 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**SimTalk**

OrderCtrl [SimTalk] - Exporter

See also

Select Object [for controls]

###### Release Control [Exporter]

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

The Release Control has two parameters, which define the importer :

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type:
- 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**SimTalk**

ReleaseCtrl [SimTalk] - Exporter

See also

Select Object [for controls]

<!-- image -->

###### Shift Calendar [Exporter]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the Exporter works.

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

**ShiftCalendarObject [SimTalk] - material flow objects**

See also

ShiftCalendar [object]

Select Object [for controls]

Tab Statistics

Tab Statistics [Exporter]

The tab Statistics shows the most important statistical data.

It shows the values for the services and for the Exporter . For each of these blocks, adding up the individual values results in a value 100 percent.

**Note**

To show the statistics values for the services in a Chart , drag the Exporter over a Chart and drop it there. To show the statistics values for the Services and for the Exporter in a Chart , hold down Shift , drag the Exporter over a Chart and drop it there.

To collect the failure times of the services and of the Exporter , select the check box Fail Services .

To only collect the failure times of the Exporter , clear the check box Fail Services .

To collect Exporter statistics data, select the check box Exporter Statistics .

The Exporter only collects failed times that accrue during the processing and setup time, i.e., times that are located outside of the paused and of the unplanned time.

Waiting times only accrue during the times when the Exporter is available, i.e., when these times are located outside of the paused , the unplanned , and the failed times.

**Note**

The Exporter stays at the station, to which he is brokered, while this station is failed , paused , or stopped . Statistics does not count this time as waiting .

<!-- image -->

| Item English        | Description                                                                                                                                                                                                                                            | Read-only attribute                                | Item German         |
|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------|---------------------|
| Services Processing | Shows the portion of the processing time of the services of the overall statistics time of the Exporter , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time . | StatServicesWorking Portion [SimTalk] - Exporter   | Dienste arbeitend   |
| Services Setting-up | Shows the portion of set-up time of the services of the overall statistics time of the Exporter , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .         | StatServicesSetupPor tion [SimTalk] - Exporter     | Dienste rüstend     |
| Services Repairing  | Shows the portion of the repairing time of the overall statistics time of the Exporter , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .                  | StatServicesRepairin gPortion [SimTalk] - Exporter | Dienste reparierend |
| Services Waiting    | Shows the portion of the waiting time of the services for an importer of the overall                                                                                                                                                                   | StatServicesWaitingP ortion [SimTalk] -            | Dienste wartend     |

| Item English            | Description                                                                                                                                                                                                                                          | Read-only attribute                                                                                             | Item German             |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|-------------------------|
|                         | statistics time of the Exporter , plus the time the services spent waiting for a part at the importer , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time . | Exporter StatServicesWaitingI mpPortion [SimTalk] - Exporter StatServicesWaiting MUPortion [SimTalk] - Exporter |                         |
| Services Failed         | Shows the portion of the failed time of the services of the overall statistics time of the Exporter , weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .   | StatServicesFailedPo rtion [SimTalk] - Exporter                                                                 | Dienste gestört         |
| Exporter Operational    | Shows the portion of the statistics collection period during which the Exporter was operational, weighted with the capacity. The overall statistics time is the statistics collection period without the unplanned time and the paused time .        | StatExporterOperatio nalPortion [SimTalk]                                                                       | Exporter einsatzberei t |
| Exporter Paused         | Shows the portion of the statistics collection period during which the Exporter was paused.                                                                                                                                                          | StatExporterPausedP ortion [SimTalk]                                                                            | Exporter pausiert       |
| Exporter Unplanned      | Shows the portion of the statistics collection period during which the Exporter was unplanned.                                                                                                                                                       | StatExporterUnplann edPortion [SimTalk]                                                                         | Exporter ungeplant      |
| Exporter failed         | Shows the portion of the statistics collection period during which the Exporter was failed.                                                                                                                                                          | StatExporterFailedPo rtion [SimTalk]                                                                            | Exporter gestört        |
| Free Capacity           | Shows the capacity that is available at the moment.                                                                                                                                                                                                  | FreeCapacity [SimTalk]                                                                                          | Freie Kapazität         |
| Mediated Capacity       | Shows the capacity that is brokered at the moment.                                                                                                                                                                                                   | MediatedCapacity [SimTalk] - Exporter                                                                           | Belegte Kapazität       |
| Free Capacity (sum)     | Shows the sum of the released capacity that the Exporter placed with any importer .                                                                                                                                                                  | StatSumFreeCapacity [SimTalk]                                                                                   | Summe freie Kapazität   |
| Mediated capacity (sum) | Shows the sum of the capacities that are brokered at the moment                                                                                                                                                                                      | StatSumMediatedCa pacity [SimTalk]                                                                              | Summe belegte Kapazität |
| Minimum Free Capacity   | Shows the minimum capacity that is available. If the Exporter did not collect any valid value yet, the tab shows -1.                                                                                                                                 | StatMinFreeCapacity [SimTalk]                                                                                   | Minimum freie Kapazität |

<!-- image -->

| Item English              | Description                                                                                                          | Read-only attribute                | Item German               |
|---------------------------|----------------------------------------------------------------------------------------------------------------------|------------------------------------|---------------------------|
| Maximum Free Capacity     | Shows the maximum capacity that is available. If the Exporter did not collect any valid value yet, the tab shows -1. | StatMaxFreeCapacity [SimTalk]      | Maximum freie Kapazität   |
| Minimum Mediated Capacity | Shows the minimum occupied capacity. If the Exporter did not collect any valid value yet, the tab shows -1.          | StatMinMediatedCap acity [SimTalk] | Minimum belegte Kapazität |
| Maximum Mediated Capacity | Shows the maximum occupied capacity. If the Exporter did not collect any valid value yet, the tab shows -1.          | StatMaxMediatedCa pacity [SimTalk] | Maximum belegte Kapazität |

To view Exporter and Worker Statistics in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

###### Exporter Statistics [Exporter]

To collect statistics data of the Exporter , select this check box.

To deactivate statistics collection, clear the check box.

SimTalk

ExpStatOn [SimTalk]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu [Exporter]

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Importers [Exporter]         |
|--------------------------------------------|------------------------------|
| Show Statistics Report [on View menu]      | Exported Services [Exporter] |
| Show Attributes and Methods [on View menu] | Associated Shift Calendar    |

**See also**

View Menu [general description]

**Importers [Exporter]**

###### Importers [Exporter]

Opens a table which shows all importers for which the Exporter provides services.

The table shows the Importers in column 1, and their Type in column 2: The number 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

<!-- image -->

<!-- image -->

###### Exported Services [Exporter]

Opens a list which shows the names of all services which the Exporter exports at this time.

Double-click the name of a service to open a subtable, which shows the name of the Importer , its Type (0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer ) and the Amount of services provided.

<!-- image -->

Instead, you can also right-click the Exporter and select Show Exported Services on the context menu in the Frame .

<!-- image -->

**See also**

getExportedServices [SimTalk]

Services [SimTalk] - Exporter

Tools Menu

Tools Menu

The Tools Menu provides these menu commands:

Edit Controls &gt; Available control

Edit Controls &gt; Not-available control

Edit Observers

3D

###### Available Control [Exporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Available Control , which is called whenever the Exporter/Worker changes its state to available .

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

**AvailableCtrl [SimTalk]**

**See also**

**Select Object [for controls]**

###### Not Available Control [Exporter]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Not Available Control , which is called whenever the Exporter/Worker changes its state to not available .

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control which is a user-defined attribute of data type Method .

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

**NotAvailableCtrl [SimTalk]**

**See also**

**Select Object [for controls]**

##### Help Menu

The commands are described under the Help Menu .

##### LEDs and States of the Exporter

During the simulation runs Plant Simulation shows the state of the Exporter as one or more colored dots in the LED display along the upper border of the icon in the Frame .

3D shows the states as horizontally arranged cubes along the top of the picture of the object.

You can also create additional icons and have Plant Simulation use these icons to display the state of the object:

- Open the Icon Editor .
- Click State Icons/LEDs on the General ribbon tab of the Icon Editor .

The LED display can display several active states at the same time, while the state icon can only display the single state it represents.

<!-- image -->

| Description                    | LED   | Looks like this   | State icon   |
|--------------------------------|-------|-------------------|--------------|
| The Exporter is failed .       | red   |                   | Failed       |
| The Exporter exports services. | green |                   | Working      |
| The Exporter is paused .       | blue  |                   | Pause        |

See also

Tab States &gt; State Graphic in 3D

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Method

LEDs and States of the MQTT Interface

#### Methods of the Exporter

\_Methods of the Exporter

The Exporter provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

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

##### expStat [SimTalk]

Returns the statistics table of the Exporter designated by &lt;Path&gt; and writes it into a table.

Type

Method

Syntax

```simtalk
< Path >.expStat → boolean < Path >.expStat(StatisticsTable:table) → boolean
```

Parameter

The parameter StatisticsTable of data type table designates the name of the table.

Return Value

The return value has the data type boolean .

true if the call was successful.

false if the object does not collect any statistics data.

Example

```simtalk
var MyExporterStatisticsTable: table
MyExporter.expStat(MyExporterStatisticsTable)
```

**findNewImporter [SimTalk]**

##### findNewImporter [SimTalk]

Registers the Exporter designated by &lt;Path&gt; as being available with its Broker .

Remarks

The Broker then searches the list of all open requests and attempts to find new Exporters . The fact that the Exporter is available to fulfill new orders is passed along to all Brokers connected by Connectors .

Type

Method

Syntax

&lt; Path &gt;.findNewImporter

Example

MyExporter.findNewImporter

See also

Importers [Exporter]

Importers [Worker]

##### getExportedServices [SimTalk]

Returns all services which the Exporter/Worker designated by &lt;Path&gt; exports at the moment.

Type

Method

Syntax

```simtalk
< Path >.getExportedServices([Services:table])
-> any
```

Parameter

The optional parameter Services of data type table designates the name of the table into which Plant Simulation writes the services.

The table has one column. It contains all services that the Exporter/Worker exports at the moment. The subtable contains all importers importing that service and the number of services which the Exporter provides for the importer ( integer ).

Return Value

The return value is an array containing the services which the Exporter/Worker currently exports if you do not specify the optional parameter.

Example

```simtalk
MyExporter.getExportedServices(MyExportedServicesTable) MyExporter.getExportedServices // returns an array
print MyExporter.getExportedServices // might
return [Job1]
```

See also

Services [SimTalk] - Exporter

Services [Exporter]

Exported Services [Exporter]

Exported Services [Worker]

##### getImporters [SimTalk]

getImporters [SimTalk]

Returns all importers for which the Exporter/Worker designated by &lt;Path&gt; is fulfilling orders.

Type

Method

Syntax

```simtalk
< Path >.getImporters([Importers:table])
-> any
```

Parameter

The optional parameter Importers of data type table designates the name of the table into which Plant Simulation writes the importers.

It has two columns:

- Column 1 of data type object contains all importers for which the Exporter is fulfilling orders at the moment.
- Column 2 of data type integer designates its type: 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

If you do not specify the optional parameter, Plant Simulation returns an array with the assigned objects which currently import the Exporter/Worker .

Return Value

The return value has the data type any .

Example

```simtalk
MyExporter.getImporters(MyImportersTable) MyExporter.getImporters // returns an array
print MyExporter.getImporters // might
return [*.Models.MyProcessingAndSetupBroker.Station3]
```

See also

Importers [Exporter]

Importers [Worker]

hasService [SimTalk]

Returns if the Exporter/Worker designated by &lt;Path&gt; supports the designated service (true) or not (false).

Type

Method

Syntax

&lt; Path &gt;.hasService(ServiceName:string) → boolean

Parameter

The parameter ServiceName of data type string designates the name of the service.

Return Value

The return value has the data type boolean .

Example

MyExporter.hasService("drill")

SimTalk

Services [SimTalk] - Exporter

See also

Services [Exporter]

Exported Services [Exporter]

Exported Services [Worker]

#### Read-Only Attributes of the Exporter

\_Read-Only Attributes of the Exporter

The Exporter provides:

- The read-only attributes listed in the table of contents to the left.

- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print .Resources.myExporter:2.AvailableForMediation AvailableForMediation [SimTalk] - Exporter Returns if the Exporter designated by &lt;Path&gt; can be brokered (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.AvailableForMediation → boolean

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

true if the Exporter is not failed, not paused, and has available capacity.

Example

print .UserObjects.MyExporter:2.AvailableForMediation

##### FreeCapacity [SimTalk]

FreeCapacity [SimTalk]

Returns the capacity which the Exporter designated by &lt;Path&gt; can provide at the moment.

Type

Read-only attribute

Syntax

&lt; Path &gt;.FreeCapacity → integer

Return Value

The return value has the data type integer .

Example

```simtalk
print MyExporter.FreeCapacity
```

See also

Tab Statistics [Exporter]

MediatedCapacity [SimTalk] - Exporter

Returns the capacity which the Exporter designated by &lt;Path&gt; brokers at the moment.

Type

Read-only attribute

Syntax

&lt; Path &gt;.MediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.MediatedCapacity

See also

Tab Statistics [Exporter]

StatExporterFailedCount [SimTalk]

Returns how often the Exporter designated by &lt;Path&gt; was failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterFailedCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatExporterFailedCount

##### StatExporterFailedDelta [SimTalk]

Returns the standard deviation of the failure time of the Exporter designated by &lt;Path&gt; from the mean value.

Type

Read-only attribute

Syntax

< Path >.StatExporterFailedDelta → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterFailedDelta

##### StatExporterFailedMu [SimTalk]

StatExporterFailedMu [SimTalk]

Returns the mean duration of a failure of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatExporterFailedMu → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterFailedDelta

##### StatExporterFailedPortion [SimTalk]

Returns the ratio of the times during which the Exporter designated by &lt;Path&gt; was failed to the statistics collection period of the Exporter .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterFailedPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatExporterFailedPortion

See also

Tab Statistics [Exporter]

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatExporterFailedTime [SimTalk]

Returns the total time during which the Exporter designated by &lt;Path&gt; was failed.

Type

Read-only attribute

Syntax

< Path >.StatExporterFailedTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterFailedTime

##### StatExporterOperationalPortion [SimTalk]

Returns the ratio of the working time of the Exporter designated by &lt;Path&gt; to the statistics collection period of the Exporter .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterOperationalPortion → real

Return Value

The return value has the data type real .

**Note**

As the Exporter computes the values that apply to the state working , it only provides the read-only attributes StatExporterOperationalPortion and StatExporterOperationalTime .

**Example**

print MyExporter.StatExporterOperationalPortion

SimTalk

StatExporterOperationalTime

See also

Tab Statistics of the Exporter

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatExporterOperationalTime [SimTalk]

Returns the total time taken up by working processes of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatExporterOperationalTime → time

Return Value

The return value has the data type time .

**Note**

As the Exporter computes the values that apply to the state working , it only provides the read-only attributes StatExporterOperationalPortion and StatExporterOperationalTime .

**Example**

print MyExporter.StatExporterOperationalTime

**SimTalk**

StatExporterOperationalPortion [SimTalk]

##### StatExporterPausedCount [SimTalk]

Returns how often the Exporter designated by &lt;Path&gt; was paused.

Type

Read-only attribute

Syntax

< Path >.StatExporterPausedCount → time

Return Value

The return value has the data type integer .

Example

print MyExporter.StatExporterPausedCount StatExporterPausedDelta [SimTalk]

Returns the standard deviation of the paused time of the Exporter designated by &lt;Path&gt; from the mean value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterPausedDelta → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterPausedDelta

##### StatExporterPausedMu [SimTalk]

Returns the mean duration of a pause of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatExporterPausedMu → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterPausedMu StatExporterPausedPortion [SimTalk]

Returns the ratio of the paused time of the Exporter designated by &lt;Path&gt; to the statistics collection period of the Exporter .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterPausedPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatExporterPausedPortion

See also

Tab Statistics [Exporter]

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Capacities and States of the Exporters

##### StatExporterPausedTime [SimTalk]

Returns the total time during which the Exporter designated by &lt;Path&gt; was paused.

Type

Read-only attribute

Syntax

< Path >.StatExporterPausedTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterPausedTime StatExporterUnplannedCount [SimTalk]

Returns how often the Exporter designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterUnplannedCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatExporterUnplannedCount StatExporterUnplannedDelta [SimTalk]

Returns the standard deviation of the unplanned time of the Exporter designated by &lt;Path&gt; from the mean value.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterUnplannedDelta → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterUnplannedDelta

##### StatExporterUnplannedMu [SimTalk]

StatExporterUnplannedMu [SimTalk]

Returns the mean duration of the unplanned time of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatExporterUnplannedMu → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterUnplannedMu StatExporterUnplannedPortion [SimTalk]

Returns the ratio of the unplanned time to the statistics collection period of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterUnplannedPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatExporterUnplannedPortion

See also

Tab Statistics [Exporter]

Tab Statistics [Worker]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatExporterUnplannedTime [SimTalk]

Returns the total time during which the Exporter designated by &lt;Path&gt; was not planned to work.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatExporterUnplannedTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatExporterUnplannedTime

##### StatMaxFreeCapacity [SimTalk]

Returns the maximum capacity which the Exporter designated by &lt;Path&gt; can provide.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMaxFreeCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatMaxFreeCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatMaxMediatedCapacity [SimTalk]

Returns the maximum occupied capacity of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMaxMediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatMaxMediatedCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters

##### StatMinFreeCapacity [SimTalk]

Returns the minimum capacity which Exporter designated by &lt;Path&gt; can provide.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMinFreeCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatMinFreeCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatMinMediatedCapacity [SimTalk]

Returns the minimum occupied capacity of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMinMediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatMinMediatedCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatServicesFailedCount [SimTalk] - Exporter Returns how often the services of the Exporter designated by &lt;Path&gt; were failed.

Remarks

The Exporter only collects failure times for the services if you activate FailServices .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesFailedCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesFailedCount

SimTalk

FailServices [SimTalk]

StatServicesFailedPortion [SimTalk] - Exporter

Returns the portion of the failed times of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Note

The Exporter only collects failure times for the services if you activate FailServices .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesFailedPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesFailedPortion

SimTalk

FailServices [SimTalk]

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesFailedTime [SimTalk] - Exporter Returns the total time during which services of the Exporter designated by &lt;Path&gt; were failed.

Remarks

The Exporter only collects failure times for the services if you activate FailServices .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesFailedTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesFailedTime

SimTalk

FailServices [SimTalk]

StatServicesRepairingCount [SimTalk] - Exporter

Returns how often the services of the Exporter designated by &lt;Path&gt; worked on repairs.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesRepairingCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesRepairingCount StatServicesRepairingPortion [SimTalk] - Exporter Returns the portion of the repairing time of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesRepairingPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesRepairingPortion

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesRepairingTime [SimTalk] - Exporter Returns the total time which the services of the Exporter designated by &lt;Path&gt; spent for repairs.

Type

Read-only attribute

Syntax

< Path >.StatServicesRepairingTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesRepairingTime StatServicesSetupCount [SimTalk] - Exporter Returns how often the services of the Exporter designated by &lt;Path&gt; were setting the station up.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesSetupCount StatServicesSetupPortion [SimTalk] - Exporter Returns the portion of the set-up time of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the unplanned time and the paused time .

**Note**

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesSetupPortion

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Time Portions of the Exporters

##### StatServicesSetupTime [SimTalk] - Exporter

Returns the total time the services of the Exporter designated by &lt;Path&gt; were setting the station up.

Remarks

**Note**

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed.

**Note**

If a station changes to the state failed and services for setting-up or processing are brokered for this station, the services remain assigned. For this reason the set-up time and the processing time for the services carry on running while the station is failed. To avoid this, activate FailServices [SimTalk] .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesSetupTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesSetupTime

SimTalk

FailServices [SimTalk]

StatServicesWaitingImpCount [SimTalk] - Exporter

Returns how often the services of the Exporter designated by &lt;Path&gt; waited for an importer .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingImpCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesWaitingImpCount StatServicesWaitingImpPortion [SimTalk] - Exporter Returns the portion of the overall statistics time which the services of the Exporter designated by &lt;Path&gt; spent waiting for an importer , weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the unplanned time and the paused time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingImpPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesWaitingImpPortion

See also

Tab Statistics [Exporter] of the Exporter

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWaitingImpTime [SimTalk] - Exporter Returns the total waiting time of the services of the Exporter designated by &lt;Path&gt; for an importer .

Type

Read-only attribute

Syntax

< Path >.StatServicesWaitingImpTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesWaitingImpTime StatServicesWaitingMUCount [SimTalk] - Exporter Returns how often the services of the Exporter designated by &lt;Path&gt; spent waiting for a MU at the importer .

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatServicesWaitingMUCount → integer
```

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesWaitingMUCount StatServicesWaitingMUPortion [SimTalk] - Exporter Returns the waiting portion for a MU at the importer of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingMUPortion → real

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesWaitingMUPortion

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWaitingMUTime [SimTalk] - Exporter Returns the total time the services of the Exporter designated by &lt;Path&gt; were waiting at the importer for a MU .

Type

Read-only attribute

Syntax

< Path >.StatServicesWaitingMUTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesWaitingMUTime StatServicesWaitingPortion [SimTalk] - Exporter Returns the portion of the waiting time of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

Remarks

The overall statistics time is the statistics collection period without the Unplanned Time and the Paused Time .

**Note**

The value of StatServicesWaitingPortion is the sum of StatServicesWaitingImpPortion and StatServicesWaitingMUPortion .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingPortion → time

Return Value

The return value has the data type real .

Example

print MyExporter.StatServicesWaitingPortion

SimTalk

StatServicesWaitingImpPortion [SimTalk] - Exporter

StatServicesWaitingMUPortion [SimTalk] - Exporter StatServicesWaitingTime [SimTalk] - Exporter Returns the time which the services of the Exporter designated by &lt;Path&gt; were waiting in relation to the statistics collection period, weighted with the capacity.

Remarks

The value of StatServicesWaitingTime is the sum of StatServicesWaitingImpTime and StatServicesWaitingMUTime .

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWaitingTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesWaitingTime

SimTalk

StatServicesWaitingImpTime [SimTalk] - Exporter

StatServicesWaitingMUTime [SimTalk] - Exporter StatServicesWorkingCount [SimTalk] - Exporter Returns the number of working processes which the services of the Exporter designated by &lt;Path&gt; provided.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatServicesWorkingCount → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatServicesWorkingCount StatServicesWorkingPortion [SimTalk] - Exporter Returns the portion of the working time of the services of the overall statistics time of the Exporter designated by &lt;Path&gt;, weighted with the capacity.

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

print MyExporter.StatServicesWorkingPortion

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Time Portions of the Exporters StatServicesWorkingTime [SimTalk] - Exporter Returns the time taken up by working processes of the services of the Exporter designated by &lt;Path&gt;.

Remarks

If a station changes to the state failed and/or unplanned or paused and if then services for setting-up or processing are brokered, the services remain brokered. The set-up time and the processing time for the services thus continues while the station is failed. To avoid this, activate FailServices .

Type

Read-only attribute

Syntax

< Path >.StatServicesWorkingTime → time

Return Value

The return value has the data type time .

Example

print MyExporter.StatServicesWorkingTime

SimTalk

FailServices [SimTalk]

##### StatSumFreeCapacity [SimTalk]

Returns the sum of the free capacity of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSumFreeCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatSumFreeCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters StatSumMediatedCapacity [SimTalk]

Returns the sum of the brokered capacity of the Exporter designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSumMediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyExporter.StatSumMediatedCapacity

See also

Tab Statistics [Exporter]

Statistics report , Service Statistics - States - Capacities and States of the Exporters

#### Attributes of the Exporter

\_Attributes of the Exporter

The Exporter provides:

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
MyExporter.ExpStatOn := true
print MyExporter.ExpStatOn
posit := Station.Cont.XPos
```

AutomaticMediation [SimTalk] - Exporter

Prevents that the Exporter designated by &lt;Path&gt; is automatically assigned by the Broker .

Type

Attribute

Syntax

```simtalk
< Path >.AutomaticMediation:boolean
```

Assignment Value

You can assign a value of data type boolean .

Specify true to make the Broker assign the Exporter automatically.

Specify false to assign the Exporter yourself.

**Examples**

```simtalk
.Resources.myExporter:2.AutomaticMediation := true
param type: integer // Importer type (0=failure, 1=setup, 2=processing, 3=transport)
var t : table
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

SimTalk

importExporter [SimTalk]

##### BrokerPath [SimTalk] - Exporter

BrokerPath [SimTalk] - Exporter

Sets the path to the Broker which procures the services that the Exporter designated by &lt;Path&gt; provides.

Type

Attribute

Syntax

&lt; Path &gt;.BrokerPath:object

Assignment Value

You can assign a value of data type object .

Example

```simtalk
print MyExporter.BrokerPath
MyExporter.BrokerPath := myBroker
```

See also

Broker [Exporter]

Capacity [SimTalk] - Exporter

Sets the Capacity of the Exporter designated by &lt;Path&gt;.

Remarks

The Capacity is a value greater than or equal to zero.

**Note**

You can only reduce the capacity if the Capacity provided to the importers is not fallen short of. If you increase the capacity, the Broker will immediately attempt to find new importers .

Type

Attribute

Syntax

```simtalk
< Path >.Capacity:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
MyExporter.Capacity := 2
```

See also

Capacity [text box] - Exporter

##### ExpStatOn [SimTalk]

ExpStatOn [SimTalk]

Activates exporter statistics of the Exporter designated by &lt;Path&gt; ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.ExpStatOn:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyExporter.ExpStatOn := true
```

See also

Exporter Statistics [Exporter]

##### FailServices [SimTalk]

Fails the services ( true ) which the Exporter designated by &lt;Path&gt; provides ( true ) or does not fail them ( false ).

**Remarks**

If you set FailServices to false and the Exporter provides services for an importer , Plant Simulation does not interrupt the respective process of the importer at the beginning of a failure. The respective Out event thus persists. During a failure new requests to the Exporter remain unsatisfied.

If Plant Simulation interrupts processing, for example through a failure of the Exporter , Plant Simulation deletes the respective Out event and adds it anew at the end of the failure according to the remaining processing time.

If you set FailServices to true and the Exporter provides services for an importer , Plant Simulation interrupts the respective process for the duration of the failure.

**Note**

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

Type

Attribute

Syntax

&lt; Path &gt;.FailServices:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyExporter.FailServices := true See also Fail Services [text box] Relational Operators

##### OrderCtrl [SimTalk] - Exporter

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation runs the Method whenever the Exporter is assigned to an importer .

It determines how the Exporter handles the order.

Type

Attribute

Syntax

&lt; Path &gt;.OrderCtrl:method

Parameters

The Order Control has two parameters that define the importer :

- The parameter Importer of data type object designates the importer .
- The parameter Type of data type integer designates its type : 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

Reformatting the Method

If you manually enter an Order Control and click Apply or OK , Plant Simulation automatically checks if the Method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking if the Method shall be reformatted or not. Empty methods are reformatted automatically. You cannot suppress checking of the format of the Method .

Assignment Value

You can assign a value of data type method .

Example

MyExporter.OrderCtrl := &amp;myOrderCtrl

See also

Order Control [Exporter]

Priority [SimTalk] - Exporter

Sets the Priority with which the Exporter designated by &lt;Path&gt; exports services when fulfilling a request.

Remarks

The Priority of an Exporter is a criterion for the urgency of a request. The Priority is an integer value. The higher its value, the higher the urgency. The Priority only applies to Exporters who are registered with the same Broker .

If several qualified Exporters with the same priority exist, who can provide the requested service, Plant Simulation first brokers the Exporters , who already stay on a suitable Workplace at the station. After that Exporters are brokered who already are at the station, but stay on the wrong Workplace . Then Exporters are brokered who are not staying on a Workplace . Finally, those Exporters are brokered who stay on a Workplace that is assigned to another station.

Type

Attribute

Syntax

```simtalk
< Path >.Priority:integer
```

Assignment Value

You can assign a value of data type integer .

Exporters with a higher capacity will be brokered earlier by the Broker for identical services than Exporters with a lower priority.

Plant Simulation provides an Exporter with Priority 10 before providing an Exporter with Priority 1.

Example

```simtalk
MyExporter.Priority := 3
```

See also

Priority [Exporter]

ReleaseCtrl [SimTalk] - Exporter

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation executes the control as soon as any importer releases the Exporter .

Type

Attribute

Syntax

**&lt; Path &gt;.ReleaseCtrl:method**

Parameters

The Release Control has two parameters that characterize the importer :

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type : 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

When the control is called, the Exporter has already left its importer . If you entered a Method , you yourself have to take care that the Exporter is assigned new importers , for example with the method findNewImporter . In this case the Exporter will not automatically register as being available with its Broker .

Reformatting the Method

If you manually enter an Release Control and click Apply or OK , Plant Simulation automatically checks if the Method expects the correct parameters. If this is not the case, Plant Simulation shows a message asking if the Method shall be reformatted or not. Empty methods are reformatted automatically. You cannot suppress checking of the format of the Method .

Assignment Value

You can assign a value of data type method .

Example

MyExporter.ReleaseCtrl := &amp;myReleaseCtrl

**SimTalk**

**findNewImporter [SimTalk]**

See also

**Release Control [Exporter]**

Services [SimTalk] - Exporter

Services [SimTalk] - Exporter

Sets or returns the names of the Services that the Exporter designated by &lt;Path&gt; exports.

Remarks

The name of the service is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

Type

Attribute

Syntax

< Path >.Services:array[]

Assignment Value

You can assign an array of data type string .

Examples

```simtalk
var a :
string[] := ["Job1", "Job2", "Job3"]
Exporter2.Services := a
```

print MyExporter.Services

SimTalk

hasService [SimTalk]

See also

Services [Exporter]

Exported Services [Exporter]

**Relational Operators**

