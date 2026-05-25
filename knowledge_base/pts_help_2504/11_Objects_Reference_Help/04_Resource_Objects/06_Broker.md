### Broker

#### Broker [object]

Use the Broker for brokering offered services and required services. You might model the manager of a plant , the supervisor of a department, or the foreman of a shop with it.

**Icon**

<!-- image -->

**Remarks**

The Broker cooperates with the Exporter and the importers (see Tab Importer and Sub-tab Failure ) of the Station , the ParallelStation , the AssemblyStation , the DismantleStation , the DePortioner , the Mixer , the Portioner , and the Tank .

The Broker is the go-between for services offered and services required. You might model the manager of a plant , the supervisor of a department, or the foreman of a shop with it. Each Broker can manage several Exporters/Workers , which tender services, and it may receive requests from several importers that require services. A request consists of a list of the required services and the amount of required services. A service name is a string .

When a Broker receives a request from an importer , it immediately attempts to fulfill it using the Exporters/ Workers it manages. If the Broker does not succeed in doing this, it may also pass the request on to other Brokers with which it is connected with a Connector . The direction of the Connector determines the direction in which Plant Simulation passes the request on. If the Exporters/Workers of different Brokers are able to satisfy the request, those Exporters/Workers are assigned. If the request cannot be satisfied immediately, the Broker that received it first will save it.

The Broker then attempts to provide the service at a later point in time. To do this, he goes from requested service to requested service and attempts to find an Exporter/Worker for each. If an Exporter/Worker offers the service, it is going to reserve the maximum possible number or the necessary number. Then the Exporter/Worker cannot offer this reserved amount of services for other services. For this reason we recommend to request special services first and more general ones last.

**Note**

If the importer requests several services at the same time, all of these services have to be available at the same time, before the Broker assigns them to the station.

The Broker does not run any optimization! That way it may happen that the Broker cannot assign any Exporters/Workers , although the Exporters/Workers may theoretically be assigned.

Compare the following example:

The importer named MyImporter requires one service A and B each. There are two Exporters/Workers with a capacity of 1 each. Exporter1 exports services A and B, Exporter2 only exports service A. Both Exporters/ Workers are registered with the same Broker . If the importer named MyImporter requests the services in the order (A,B), then the Broker assigns Exporter1 for service A and realizes that Exporter2 cannot export the still missing service; thus it cannot fulfill the request.

If the importer named MyImporter puts in the request in the order (B,A), it will be fulfilled immediately: Exporter1 provides service B and Exporter2 provides service A. The sequence in which a Broker passes requests on is defined uniquely by the Connectors . The Broker first passes the request on to all of its direct successors, defined by the number of the Connector . After that it passes the request on to the successors of the successors. When an Exporter/Worker registers with its Broker as being available, the Broker attempts to find new importers for the Exporter/Worker . First, the Broker checks the unsatisfied requests it manages, and then it has its Broker successors check for any unsatisfied requests.

You can also show the Broker Statistics Table of a Broker in an HtmlReport , compare Display a Broker .

To show a tooltip with information about the Broker , hover with the mouse over it.

To change the length of the graphic and the anchor points of the Broker , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Broker to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Resources &gt; Broker on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

How the Worker Decides Where to Work

Model Workers and the Jobs They Do

Model Workers with Importer, Broker, and Exporter

#### Dialog Box of the Broker

Dialog Box of the Broker

Double-click the icon of the Broker to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

##### Tab Attributes

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes [Broker]

The tab Attributes provides these settings:

Choose the Nearest Worker [check box]

Importer Request Control [Broker]

Exporter Request Control [Broker]

###### Choose the Nearest Worker [check box]

To make the Broker prefer the Worker , who has to walk the shortest path to the Workplace , select this check box. Clear the check box to make the Broker select any Worker who can do this job, no matter where he is located at the moment.

Remarks

When the Broker receives an import request , it selects Workers , who can fulfill the requested services according to the following criteria:

- Highest Priority
- Already located at a Workplace of the requesting station
- Matching Scope

If you select the check box Choose the Nearest Worker the Broker uses an additional criterion for selecting Workers : Which of the Workers has a to walk a shorter distance to the Workplace than any of the other Workers .

Plant Simulation computes routes to the suitable Workplaces of the station for all eligible Workers while mediating them. For this reason, enabling Choose the Nearest Worker can slow down the simulation.

SimTalk

**ChooseNearestWorker [SimTalk]**

See also

Tab Scope

Priority [Worker]

Objects [Scope]

Workers to Create table

How the Worker Decides Where to Work

Video on YouTube

[https://youtu.be/gU1pqu7sWA8?si=wA6ISMbfc9ZVvLme&amp;t=204](https://youtu.be/gU1pqu7sWA8?si=wA6ISMbfc9ZVvLme&t=204)

###### Controls of the Broker

**Controls of the Broker**

**Controls - Broker**

Define controls how the Broker handles importers.

**To create a control:**

<!-- image -->

- Click and select a Method in the dialog Select Object .
- Select the Method in a Frame , drag it to the text box and drop it there.

**Note**

F2 opens the dialog of the object, whose name you typed into the text box.

- Select Create Control and create the control as a Method of the object .

<!-- image -->

You can create an Importer Request Control and an Exporter Request Control .

<!-- image -->

The Importer Request Control and the Exporter Request Control are called in the following order:

- If you defined Exporter and Importer Request Controls , the Exporter Request Controls will be executed first. This way you can make the Worker follow the part when the part moves to the next

- station. This causes changed behavior as compared to modeling without controls. Without controls, the Worker is brokered for the new station in the WorkerPool .
- If several Importer Request Controls are executed at the same time, for example because an Exporter/ Worker is released and if several open Importers exist, the sequence of the controls matches the sequence of the Importers in the list Open Importers . This way brokering of Exporters/Workers behaves identical when you model with our without controls.

See also

Importer Request Control [Broker]

Exporter Request Control [Broker]

**Importer Request Control [Broker]**

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Importer Request Control , which sets how the Broker requests importers .

<!-- image -->

Plant Simulation executes the Importer Request Control whenever the Broker receives a request or when it would handle the request again, for example, when an Exporter/Worker registers as being available. In the source code of the Method you yourself have to make sure that the request is taken care of, for example with the method engage . With this control you can model your own assignment strategies.

If you defined Exporter and importer request controls , the Exporter Request Controls will be executed first. This way you can make the Worker follow the part when the part moves to the next station. This causes changed behavior as compared to modeling without controls. Without controls, the Worker is brokered for the new station in the WorkerPool .

If several Importer Request Controls are executed at the same time, for example because an Exporter/ Worker is released and if several open Importers exist, the sequence of the controls matches the sequence of the Importers in the list Open Importers . This way brokering of Exporters/Workers behaves identical when you model with our without controls.

The Importer Request Control does not interrupt methods that are executed at the moment. It will only be called after the current call chain has been executed. Importer requests can not overtake each other.

**Compare this example:**

- The Processing Importer of Station2 cannot be satisfied because the Worker is already working at Station1 .
- Station1 finishes process the part . The Worker is released and the Exit Control of Station1 is called. The Importer Request Control of Station2 is only called after the exit control has been executed.
- The Exit Control of Station1 moves the part to Station3 . The Importer Request Control does not interrupt the exit control . After the exit control has been executed, the Importer Request Control of Station2 is called and then the Importer Request Control of Station3 .

**Note**

For Broker hierarchies Plant Simulation does not call the controls of the sub-Brokers , i.e., of several Brokers that are connected with Connectors in addition. Plant Simulation only calls the control of the Broker which you typed into the object.

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

The standard importer request control as a user-defined attribute looks like this:

<!-- image -->

**SimTalk**

ImpRequestCtrl [SimTalk]

doStandardExport [SimTalk]

**See also**

**Select Object [for controls]**

**Exporter Request Control [Broker]**

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Exporter Request Control , which sets how the Broker requests Exporters/Workers .

<!-- image -->

Plant Simulation executes the Exporter Request Control whenever an Exporter/Worker registers as being available with its Broker , so that it maybe assigned a new importer . In the source code of the Method you yourself have to make sure that the request is taken care of, for example with the method engage . With this control you can assign a specific importer to the Exporter/Worker .

If you defined Exporter and Importer request controls , the Exporter Request Controls will be executed first. This way you can make the Worker follow the part when the part moves to the next station. This causes changed behavior as compared to modeling without controls. Without controls, the Worker is brokered for the new station in the WorkerPool .

If several Importer request controls are executed at the same time, for example because an Exporter/ Worker is released and if several open Importers exist, the sequence of the controls matches the sequence of the Importers in the list Open Importers . This way brokering of Exporters/Workers behaves identical when you model with our without controls.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

##### Tab Statistics

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard exporter request control as a user-defined attribute looks like this:

<!-- image -->

**SimTalk**

ExpRequestCtrl [SimTalk]

doStandardExport [SimTalk]

See also

Select Object [for controls]

Tab Statistics

Tab Statistics [Broker]

The tab Statistics shows the most important statistical data.

To collect statistics data, select the check box Broker statistics .

| Item English        | Description                               | Read-only attribute   | Item German            |
|---------------------|-------------------------------------------|-----------------------|------------------------|
| Open Requests       | Shows the actual number of open requests. | OpenRequests          | Offene Anfragen        |
| Open Requests (sum) | Shows the total number of open requests.  | StatOpenRequests      | Summe offener Anfragen |
| Satisfied Requests  | Shows the number of satisfied requests.   | SatisfiedRequests     | Befriedigte Anfragen   |

| Item English             | Description                                    | Read-only attribute   | Item German                 |
|--------------------------|------------------------------------------------|-----------------------|-----------------------------|
| Satisfied Requests (sum) | Shows the total number of satisfied requests.  | StatSatisfiedRequests | Summe befriedigter Anfragen |
| Open Capacity            | Shows the amount of available capacities.      | OpenCapacity          | Offene Kapazität            |
| Open Capacity (sum)      | Shows the total amount of open capacities.     | StatOpenCapacity      | Summe offener Kapazität     |
| Mediated Capacity        | Shows the amount of brokered capacities.       | MediatedCapacity      | Belegte Kapazität           |
| Mediated Capacity (sum)  | Shows the total amount of brokered capacities. | StatMediatedCapacity  | Summe belegte Kapazität     |

<!-- image -->

**Note**

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies if the service is provided by sub-Brokers .

To view Broker Statistics in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. The Statistics Report also shows the Dwelling Time and the Mediation Time per service of the Broker .

You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

###### Tab Statistics [Broker]

See also brokerStat [SimTalk] BrokerStatOn [SimTalk] serviceStat [SimTalk]

<!-- image -->

###### Broker Statistics [activate]

To collect statistics data of the Broker , select this check box.

<!-- image -->

To deactivate statistics collection, clear the checkbox.

SimTalk

**BrokerStatOn [SimTalk]**

See also

Show Statistics Report [on View menu]

Time to get single item

**Service Statistics [Broker]**

###### Service Statistics [Broker]

To open the service statistics table, which shows the Dwelling Time and the Mediation Time per service, click this button.

**Note**

If a service is fulfilled by several Workers or Exporters/Workers , Plant Simulation records this time interval only once. The same applies for the count . For the time during which the Worker was en-route to his job, statistics counts the time of the Worker who was en-route the longest.

| Item English          | Description                                                                                                                           | Read-only attribute   | Item German                |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------|----------------------------|
| Services              | Shows the services, which the Broker brokered.                                                                                        | -                     | Dienste                    |
| Dwelling Time: Count  | Shows how often the service in this row was brokered, i.e., how often the Exporter/Worker stayed at the importer/importers .          | -                     | Verweildauer : Anzahl      |
| Sum                   | Shows the sum of the times during which the service in this row was brokered.                                                         | StatStayTime          | Summe                      |
| Mean Value            | Shows the mean duration of the times during which the service in this row was brokered.                                               | StatStayTimeMu        | Mittelwert                 |
| Standard Deviation    | Shows the standard deviation from the mean value of the times during which the service in this row was brokered.                      | StatStayTimeDelta     | Standardabw eichung        |
| Min                   | Shows the minimum time during which the service in this row was brokered.                                                             | -                     | Min                        |
| Max                   | Shows the maximum time during which the service in this row was brokered.                                                             | -                     | Max                        |
| Mediation Time: Count | Shows how often the importer/importers were waiting for the procurement of the service in this row.                                   | -                     | Vermittlungs dauer: Anzahl |
| Sum                   | Shows the sum of the times during which the importer/importers were waiting for the procurement of the service in this row.           | StatMediationTime     | Summe                      |
| Mean Value            | Shows the mean duration of the times during which the importer/importers were waiting for the procurement of the service in this row. | StatMediationTime Mu  | Mittelwert                 |

| Item English       | Description                                                                                                                                                    | Read-only attribute     | Item German         |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------|---------------------|
| Standard Deviation | Shows the standard deviation from the mean value of the times during which the importer/importers were waiting for the procurement of the service in this row. | StatMediationTimeD elta | Standardabw eichung |
| Min                | Shows the minimum time during which the importer/importers were waiting for the procurement of the service in this row.                                        | -                       | Min                 |
| Max                | Shows the maximum time during which the importer/importers were waiting for the procurement of the service in this row.                                        | -                       | Max                 |

**SimTalk**

**serviceStat [SimTalk]**

See also

Broker Statistics [described]

Statistics report , Broker Statistics [described]

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

View Menu [Broker]

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Satisfied Importers [Broker]   |
|--------------------------------------------|--------------------------------|
| Show Statistics Report [on View menu]      | Exporters [Broker]             |
| Show Attributes and Methods [on View menu] | Offered Services [Broker]      |
| Open Importers [Broker]                    |                                |

**Open Importers [Broker]**

###### Open Importers [Broker]

Opens a table showing all objects whose importers registered an unsatisfied request with the Broker .

The table shows the Importers in column 1, and their Type in column 2: The number 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

An Importer , who is interrupted because another station with a higher priority requires the resource, is sorted at the first place in the list.

<!-- image -->

**See also**

getOpenImporters [SimTalk]

forgetOpenRequest [SimTalk]

###### Satisfied Importers [Broker]

Opens a table showing all objects whose importers were assigned Exporters/Workers .

The table shows the Importers in column 1, and their Type in column 2: The number 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

<!-- image -->

**See also**

getSatisfiedImporters [SimTalk]

###### Exporters [Broker]

Opens a list showing information about all Exporters registered with the Broker .

<!-- image -->

The column Exporters shows the names of the Exporters/Workers .

The column State shows the state of the respective Exporter/Worker .

The column Capacity shows the capacity of the respective Exporter/Worker .

The column Free Cap. shows the free capacity of the respective Exporter/Worker .

**See also**

AdministeredExporters [SimTalk]

###### Offered Services [Broker]

Opens a list showing information about the services offered by the Exporters/Workers which are managed by the Broker .

Services Offered by the Exporter

The column Services shows the name of the service which the Exporter offers.

The column Capacity shows the overall capacity which the Exporter offers.

The column Free Cap. shows the free capacity which the Exporter offers.

Double-click the name of a service to open a subtable, which shows the path of the Exporter .

<!-- image -->

The column State shows the state of the respective Exporter .

The column Capacity shows the capacity of the respective Exporter .

The column Free Cap. shows the free capacity of the respective Exporter .

Services Offered by the Worker

The column Services shows the name of the service which the Worker offers.

The column Capacity shows the overall capacity which the Worker offers.

The column Free Cap. shows the free capacity which the Worker offers.

Double-click the name of a service to open a subtable, which shows the path of the individual Worker .

<!-- image -->

The column State shows the state of the respective Worker .

The column Capacity shows the capacity of the respective Worker .

The column Free Cap. shows the free capacity of the respective Worker .

**See also**

getOfferedServices [SimTalk]

Tools Menu

The Tools Menu provides these menu commands: Edit Controls Edit Observers 3D

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Broker**

#### \_Methods of the Broker

The Broker provides:

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

##### brokerStat [SimTalk]

brokerStat [SimTalk]

Returns the statistics table of the Broker designated by &lt;Path&gt; and writes it into a table.

Remarks

For Broker hierarchies , i.e., for several Brokers connected with Connectors , the brokered services are only considered for the Broker which you typed into the Importer . This also applies when the service is provided by sub-Brokers .

Type

Method

Syntax

```simtalk
< Path >.brokerStat([BrokerStatisticsTable:table]) → boolean
```

Parameter

The optional parameter BrokerStatisticsTable of data type Table designates the name of the table.

Return Value

The return value has the data type boolean .

- true if statistics collection is activated. false if statistics collection is deactivated. Then the table remains unaltered.
- Is the table containing the statistics data if statistics collection is activated if you do not specify the optional parameter.

void if statistics collection is deactivated.

**Examples**

```simtalk
MyBroker.brokerStat(MyBrokerStatisticsTable) // Writes the statistics values to the table named MyBrokerStatisticsTable. // The
return value is true
if statistics collection is activated. // It is false if it is deactivated. Then the table remains unaltered.
MyBroker.brokerStat // Writes the statistics values to a table.
```

**See also**

**Tab Statistics [Broker]**

##### doStandardExport [SimTalk]

Makes the Broker designated by &lt;Path&gt; do a standard export of the specified Worker/Exporter .

Remarks

Use doStandardExport in the Exporter Request Control of the Broker .

If you do not want the Broker to assign a specific Worker/Exporter , then either set AutomaticMediation to false or do not call the methods doStandardImport or doStandardExport .

Type

Method

Syntax

&lt; Path &gt;.doStandardExport(Exporter:object)

Parameter

The parameter Exporter of data type object designates the Worker/Exporter .

Example

MyBroker.doStandardExport(MyExporter)

See also

Exporter Request Control [Broker]

AutomaticMediation [SimTalk] - Worker

AutomaticMediation [SimTalk] - Exporter

doStandardImport [SimTalk]

##### doStandardImport [SimTalk]

Makes the Broker designated by &lt;Path&gt; do a standard import of the specified importer .

Remarks

Use doStandardImport in the Importer Request Control of the Broker for those importers for which you do not need special treatment.

This way you do not have to call the methods testImportFor and engage for the designated importer .

Type

Method

Syntax

```simtalk
< Path >.doStandardImport(Importer:object, Type:integer)
```

Parameters

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type : 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**Examples**

MyBroker.doStandardImport(MyImporter, 2)

```simtalk
param obj: object, type: integer // Importer type (0=failure importer, 1=setup importer, 2=processing importer, 3=transport importer) // look for the worker in the attribute of the part
if @.worker /= void // a worker was already assigned to the part
	if @.worker.freeCapacity > 0 // worker is free, we can assign the worker to the station
		var workersToBeExported : table[object, string, integer]
		workersToBeExported.create
		workersToBeExported.writeRow( 1, workersToBeExported.YDIm+1, @.worker, "StandardService", 1 )
		?.engage( obj, type, workersToBeExported)
	end
else // there is no assignment between the part and any worker
	?.doStandardImport(obj, type)
end
```

SimTalk

testImportFor [SimTalk]

engage [SimTalk]

See also

Importer Request Control [Broker]

##### engage [SimTalk]

Makes the Broker designated by &lt;Path&gt; assign one or several Exporters/Workers to an importer .

Remarks

The Broker attempts to book the specified services and the amount required with the Exporters/Workers . The Exporters/Workers have to be registered with any Broker . Exporters/Workers and services may be contained multiple times.

Type

Method

Syntax

```simtalk
< Path >.engage(Importer:object, Type:integer, Data:table) → boolean
```

**Parameters**

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type: 0 designates the failure/remove failureimporter , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .
- The parameter Data of data type Table designates a table with the columns Exporter , Services , and Amount .

Return Value

The return value has the data type boolean .

true if all services were assigned with the required amount.

false if the services were not assigned. The Broker does not save and remember requests it cannot fulfill.

**Examples**

MyBroker.engage(importer1,1,tableTile)

```simtalk
param obj: object, type: integer // importer type (0 is the failure, 1 the setup, //2 the process, and 3 the transport importer)
var tab : table[object, string, integer]
var service : string
tab.create
tab.writeRow(1,1, .Resources.Worker:1, "myservice", 1 )
return MyBroker.engage(obj, type, tab)
```

##### forgetOpenRequest [SimTalk]

Cancels an open request with the Broker designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.forgetOpenRequest(Importer:object, Type:integer)

**Parameters**

- The parameter Importer of data type object designates the importer .
- The parameter Type of data type integer designates its type: 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

**Example**

MyBroker.forgetOpenRequest(Station,1)

See also

Open Importers [Broker]

##### getExportersForService [SimTalk]

getExportersForService [SimTalk]

Returns the Exporters/Workers who provide the desired service and who can be brokered by the Broker designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< Path >.getExportersForService(Service:string) → object[]
```

Parameter

The parameter Service of data type string designates the service.

Return Value

The return value is an array of data type object .

Example

MyBroker.getExportersForService('MyService')

##### getOfferedServices [SimTalk]

Returns all services which are offered by Exporters/Workers that are managed by the Broker designated by &lt;Path&gt;, and writes them into a table.

Type

Method

Syntax

```simtalk
< Path >.getOfferedServices([Services:table]) → table
```

**Parameter**

The optional parameter Services of data type table designates the name of the table. The subtable lists all Exporters/Workers offering the service.

**Examples**

```simtalk
MyBroker.getOfferedServices(MyOfferedServicesTable) // Writes the offered services to the table MyOfferedServicesTable.
MyBroker.getOfferedServices // Writes the offered services to a table which is the
return value.
```

**See also**

**Offered Services [Broker]**

##### getOpenImporters [SimTalk]

getOpenImporters [SimTalk]

Returns all open, i.e., unsatisfied importers managed by the Broker designated by &lt;Path&gt; and writes them into a table.

Type

Method

Syntax

```simtalk
< Path >.getOpenImporters([Importers:table]) → table
```

**Parameter**

The optional parameter Importers of data type table designates the name of the table.

- Column 1 of data type object lists all objects whose importers registered an unsatisfied request with the Broker .
- Column 2 of data type integer designates its type: 0 designates the failure/remove failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .

Return Value

The return value has the data type table .

Examples

```simtalk
MyBroker.getOpenImporters(MyOpenImportersTable) // Writes the open importers to the table MyOpenImportersTable.
MyBroker.getOpenImporters // Writes the open importers to a table which is the
return value.
```

**See also**

Open Importers [Broker]

##### getSatisfiedImporters [SimTalk]

Returns all importers , whose request for an Exporter/Worker the Broker designated by &lt;Path&gt; fulfilled, and writes them into a table.

Type

Method

Syntax

```simtalk
< Path >.getSatisfiedImporters([Importers:table]) → table
```

**Parameter**

The optional parameter Importers of data type table designates the name of the table.

- Column 1 of data type object of the table contains all objects whose importer registered a request with the Broker and who were assigned an Exporter/Worker .
- Column 2 of data type integer designates its type: 0 designates the failure-importer , 1 the set-upimporter , 2 the processing-importer , and 3 the transport-importer .

**Return Value**

The return value has the data type table .

**Examples**

```simtalk
MyBroker.getSatisfiedImporters(MySatisfiedImporterTable) // Writes the satisfied importers to the table MySatisfiedImporterTable.
MyBroker.getSatisfiedImporters // Writes the satisfied importers to a table which is the
return value.
```

**See also**

SetUpOnlyWhenEmpty [SimTalk]

##### globalOpenRequestsFor [SimTalk]

Finds all importers for which the Exporter/Worker exports services which are managed by the Broker designated by &lt;Path&gt;.

Remarks

globalOpenRequestsFor only works if the importers registered their request with a Broker in the Broker hierarchy.

As opposed to the method localOpenRequestsFor , which only checks the importers locally managed by the Broker, the method globalOpenRequestsFor checks the entire Broker hierarchy.

Type

Method

Syntax

&lt; Path &gt;.globalOpenRequestsFor(Exporter:object, Importers:table)

**Parameters**

- The parameter Exporter of data type object designates the Exporter/Worker .
- The parameter Importers of data type table contains those importers which require at least one service that is exported by the Exporter/Worker .

**Example**

MyBroker.globalOpenRequestsFor(Exporter,tab2) MyBroker.globalOpenRequestsFor(Worker ,tab2)

SimTalk

localTestImportFor [SimTalk]

##### globalTestImportFor [SimTalk]

Checks all Exporters/Workers that may be reached in the Broker hierarchy of the Broker designated by &lt;Path&gt; for the importer .

**Remarks**

As opposed to the method em localTestImportFor , which only checks the Exporters/Workers locally managed by the Broker, the method globalTestImportFor checks the entire Broker hierarchy, i.e., all Brokers linked with a Connector .

The methods localTestImportFor and globalTestImportFor return the same result for a single Broker !

Type

Method

Syntax

&lt; Path &gt;.globalTestImportFor(Importer:object, Type:integer, Exporters:table[, OnlyAvailable:boolean]) → boolean

**Parameters**

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type: 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .
- The parameter Exporters/Workers of data type table contains all Exporters/Workers directly managed by the Broker and able to provide any service the importer requires. However, the Broker does not check if the Exporters/Workers are able to export the service or are available.
- The optional parameter OnlyAvailable of data type boolean sets if all Exporters/Workers will be listed ( false ) or if only the actually available Exporters/Workers will be listed ( true ).

**Return Value**

The return value has the data type boolean .

The Broker does not check if the Exporters/Workers can export the service or are available.

**Example**

MyBroker.globalTestImportFor(sp2,2,tab1)

**SimTalk**

**localTestImportFor [SimTalk]**

##### localOpenRequestsFor [SimTalk]

Finds all importers for which the Exporter/Worker exports services which are managed by the Broker designated by &lt;Path&gt;.

Remarks

This only works if the importers registered their request with a Broker in the Broker hierarchy.

Type

Method

Syntax

&lt; Path &gt;.localOpenRequestsFor(Exporter:object, Importers:table)

**Parameters**

- The parameter Exporter of data type object designates the Exporter/Worker .
- The parameter Importers of data type table contains those importers which require at least one service that is exported by the Exporter/Worker .

**Example**

MyBroker.localOpenRequestsFor(Exporter,tab)

**SimTalk**

globalOpenRequestsFor [SimTalk]

**localTestImportFor [SimTalk]**

##### localTestImportFor [SimTalk]

Checks all Exporters/Workers directly managed by the Broker designated by &lt;Path&gt; for the Importer .

Type

Method

Syntax

```simtalk
< Path >.localTestImportFor(Importer:object, Type:integer, Exporters:table[, OnlyAvailable:boolean]) → boolean
```

**Parameters**

- The parameter Importer of data type object designates the Importer proper.
- The parameter Type of data type integer designates its type: 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .
- The parameter Exporters of data type table contains all Exporters/Workers directly managed by the Broker and able to provide any service the Importer requires. However, the Broker does not check if the Exporters/Workers are able to export the service or are available.
- The optional parameter OnlyAvailable of data type boolean sets if all Exporters/Workers will be listed ( false ) or if only the actually available Exporters/Workers will be listed ( true ). This parameter only prevents paused or failed Exporters/Workers from being returned.

Return Value

The return value has the data type boolean .

**Example**

MyBroker.localTestImportFor(ParallelStation3,0,tab3) MyBroker.localTestImportFor(pp3,0,tab3,true)

**SimTalk**

globalTestImportFor [SimTalk]

##### serviceStat [SimTalk]

Returns Service Statistics of the Broker designated by &lt;Path, and writes it into a table.

**Remarks**

If a service is fulfilled by several Workers/Exporters , Plant Simulation records this time interval only once. The same applies for the count.

For the time during which the Worker was en-route to his job, statistics counts the time of the Worker who was en-route the longest.

Type

Method

Syntax

```simtalk
< Path >.serviceStat([ServiceStatistics:table]) → boolean
```

**Parameter**

The optional parameter ServiceStatistics of data type table designates the name of the table.

| Item English         | Description                                                                                                                  | Read-only attribute         | Item German           |
|----------------------|------------------------------------------------------------------------------------------------------------------------------|-----------------------------|-----------------------|
| Services             | Shows the services, which the Broker brokered.                                                                               | -                           | Dienste               |
| Dwelling Time: Count | Shows how often the service in this row was brokered, i.e., how often the Exporter/Worker stayed at the importer/importers . | -                           | Verweildau er: Anzahl |
| Sum                  | Shows the sum of the times during which the service in this row was brokered.                                                | StatStayTime [SimTalk]      | Summe                 |
| Mean Value           | Shows the mean duration of the times during which the service in this row was brokered.                                      | StatStayTimeMu [SimTalk]    | Mittelwert            |
| Standard Deviation   | Shows the standard deviation from the mean value of the times during which the service in this row was brokered.             | StatStayTimeDelta [SimTalk] | Standardab weichung   |
| Min                  | Shows the minimum time during which the service in this row was brokered.                                                    | -                           | Min                   |
| Max                  | Shows the maximum time during which the service in this row was brokered.                                                    | -                           | Max                   |

| Item English          | Description                                                                                                                                                    | Read-only attribute               | Item German                |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------|----------------------------|
| Mediation Time: Count | Shows how often the importer/importers were waiting for the procurement of the service in this row.                                                            | -                                 | Vermittlung sdauer: Anzahl |
| Sum                   | Shows the sum of the times during which the importer/importers were waiting for the procurement of the service in this row.                                    | StatMediationTime [SimTalk]       | Summe                      |
| Mean Value            | Shows the mean duration of the times during which the importer/importers were waiting for the procurement of the service in this row.                          | StatMediationTimeM u [SimTalk]    | Mittelwert                 |
| Standard Deviation    | Shows the standard deviation from the mean value of the times during which the importer/importers were waiting for the procurement of the service in this row. | StatMediationTimeD elta [SimTalk] | Standardab weichung        |
| Min                   | Shows the minimum time during which the importer/importers were waiting for the procurement of the service in this row.                                        | -                                 | Min                        |
| Max                   | Shows the maximum time during which the importer/importers were waiting for the procurement of the service in this row.                                        | -                                 | Max                        |

**Return Value**

The return value has the data type boolean .

- true if statistics collection is activated. false if statistics collection is deactivated. Then the table remains unaltered.
- Is the table containing the statistics data if statistics collection is activated if you do not specify the optional parameter.

void if statistics collection is deactivated.

**Examples**

```simtalk
MyBroker.serviceStat(MyServicesTable) // Writes the statistics values of the Broker to the table named MyServicesTable.
```

**serviceStat [SimTalk]**

```simtalk
// The
return value is true
if statistics collection is activated. // It is false if it is deactivated. The table then remains unchanged.
MyBroker.serviceStat // Writes the statistics values to a table. // The
return value is the statistics table
if statistics collection is activated. // It is void if statistics collection is deactivated.
```

**See also**

**Service Statistics [Broker]**

Statistics report , Dwelling Time

Statistics report , Mediation Time

**testImportFor [SimTalk]**

##### testImportFor [SimTalk]

Executes a test request for the Importer . The return value shows if the Broker designated by &lt;Path&gt; is able to satisfy the request (true) or not (false).

Remarks

Use testImportFor to find out how the Broker will treat the request of the importer .

Type

Method

Syntax

&lt; Path &gt;.testImportFor(Importer:object, Type:integer, Exporter:table) → boolean

**Parameters**

- The parameter Importer of data type object designates the importer proper.
- The parameter Type of data type integer designates its type: 0 designates the failure-importer , 1 the set-up-importer , 2 the processing-importer , and 3 the transport-importer .
- The parameter Exporter of data type table passes a table containing all Exporters/Workers that may be assigned after the call.

Return Value

The return value has the data type boolean .

**Example**

MyBroker.testImportFor(sp1,1,Tab)

SimTalk

globalTestImportFor [SimTalk]

localOpenRequestsFor [SimTalk]

#### Read-Only Attributes of the Broker

\_Read-Only Attributes of the Broker

The Broker provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyBroker.OpenCapacity

**AdministeredExporters [SimTalk]**

##### AdministeredExporters [SimTalk]

Returns all Exporters/Workers which are registered with the Broker designated by &lt;Path&gt;.

Remarks

The array does not contain all Exporters/Workers that may be reached via the Broker -hierarchy, but only those that are registered directly with the Broker .

Type

Read-only attribute

Syntax

< Path >.AdministeredExporters → array

Return Value

The return value has the data type array .

Examples

```simtalk
print MyBroker.AdministeredExporters
var t :object[] := MyBroker.AdministeredExporters
```

See also

Exporters [Broker]

MediatedCapacity [SimTalk] - Broker

Returns the capacity which the Broker designated by &lt;Path&gt; brokered.

Type

Read-only attribute

Syntax

&lt; Path &gt;.MediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.MediatedCapacity

See also

Tab Statistics [Broker]

##### OpenCapacity [SimTalk]

OpenCapacity [SimTalk]

Returns the total amount of open capacities which the Broker designated by &lt;Path&gt; could not fulfill.

Type

Read-only attribute

Syntax

&lt; Path &gt;.OpenCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.OpenCapacity

See also

Tab Statistics [Broker]

##### OpenRequests [SimTalk]

Returns the actual number of open requests which the Broker designated by &lt;Path&gt; manages.

Type

Read-only attribute

Syntax

&lt; Path &gt;.OpenRequests → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.OpenRequests

See also

Tab Statistics [Broker]

##### SatisfiedRequests [SimTalk]

SatisfiedRequests [SimTalk]

Returns the number requests which the Broker designated by &lt;Path&gt; fulfilled.

Type

Read-only attribute

Syntax

&lt; Path &gt;.SatisfiedRequests → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.SatisfiedRequests

See also

Tab Statistics [Broker]

##### StatMediatedCapacity [SimTalk]

Returns the total amount of brokered capacities which the Broker designated by &lt;Path&gt; manages.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMediatedCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.StatMediatedCapacity

See also

Tab Statistics [Broker]

Statistics report , Broker Statistics [described]

**StatMediationTime [SimTalk]**

##### StatMediationTime [SimTalk]

Returns the sum of the times which the Broker designated by &lt;Path&gt; required to meet all satisfied requests.

Remarks

This is the time during which the importer/importers were waiting for the services.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMediationTime → time

Return Value

The return value has the data type time .

Example

print MyBroker.StatMediationTime

See also

Statistics report , Broker Statistics [described]

##### StatMediationTimeDelta [SimTalk]

Returns the standard deviation of the medium procurement time which the Broker designated by &lt;Path&gt; required to meet all satisfied requests.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMediationTimeDelta → time

Return Value

The return value has the data type time .

Example

print MyBroker.StatMediationTimeDelta

See also

Statistics report , Broker Statistics [described]

StatMediationTimeMu [SimTalk]

Returns the medium duration of the time which the Broker designated by &lt;Path&gt; required to meet a single request.

Type

Read-only attribute

Syntax

< Path >.StatMediationTimeMu → time

Return Value

The return value has the data type time .

Example

print MyBroker.StatMediationTimeMu

See also

Statistics report , Broker Statistics [described]

<!-- image -->

StatOpenCapacity [SimTalk]

Returns the total amount of open capacities which the Broker designated by &lt;Path&gt; manages.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatOpenCapacity → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.StatOpenCapacity

See also

Tab Statistics [Broker]

Statistics report , Broker Statistics [described]

StatOpenRequests [SimTalk]

Returns the total number of open requests which the Broker designated by &lt;Path&gt; manages.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatOpenRequests → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.StatOpenRequests

See also

Tab Statistics [Broker]

Statistics report , Broker Statistics [described]

##### StatSatisfiedRequests [SimTalk]

Returns the total number of requests which the Broker designated by &lt;Path&gt; satisfied.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatSatisfiedRequests → integer

Return Value

The return value has the data type integer .

Example

print MyBroker.StatSatisfiedRequests

See also

Tab Statistics [Broker]

Statistics report , Broker Statistics [described]

**StatStayTime [SimTalk]**

##### StatStayTime [SimTalk]

Returns the sum of the times during which Exporters/Workers stayed at importers .

Remarks

These are the times during which the services managed by the Broker designated by &lt;Path&gt; were brokered.

Type

Read-only attribute

Syntax

< Path >.StatStayTime → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyBroker.StatStayTime
```

See also

Statistics report , Broker Statistics [described]

##### StatStayTimeDelta [SimTalk]

Returns the standard deviation of the time during which Exporters/Workers stayed at importers who are managed by the Broker designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStayTimeDelta → time

Return Value

The return value has the data type time .

Example

print MyBroker.StatStayTimeDelta

See also

Statistics report , Broker Statistics [described]

##### StatStayTimeMu [SimTalk]

StatStayTimeMu [SimTalk]

Returns the medium duration of the time during which Exporters/Workers stayed at a single importer who is managed by the Broker designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

< Path >.StatStayTimeMu → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyBroker.StatStayTimeMu
```

See also

Statistics report , Broker Statistics [described]

##### Attributes of the Broker

\_Attributes of the Broker

The Broker provides:

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

```simtalk
MyBroker.BrokerStatOn := true
print MyBroker.ExpRequestCtrl
posit := Station.Cont.XPos
```

##### BrokerStatOn [SimTalk]

BrokerStatOn [SimTalk]

Activates ( true ) or deactivates ( false ) statistics collection of the Broker designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.BrokerStatOn:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyBroker.BrokerStatOn := true

See also

Broker Statistics [activate]

##### ChooseNearestWorker [SimTalk]

Makes the Broker designated by &lt;Path&gt; prefer the Worker , who has to walk the shortest path to the Workplace ( true ). Specify false to make the Broker select any Worker who can do this job, no matter where he is located at the moment.

**Remarks**

When the Broker receives an import request , it selects Workers , who can fulfill the requested services according to the following criteria:

- Highest Priority
- Already located at a Workplace of the requesting station
- Matching Scope

When you specify true to ChooseNearestWorker , the Broker uses an additional criterion for selecting Workers : Which of the Workers. has a to walk a shorter distance to the Workplace than any of the other Workers .

Specify false to make the Broker select any Worker who can do this job, no matter where he is located at the moment.

Plant Simulation computes routes to the suitable Workplaces of the station for all eligible Workers while mediating them. For this reason, enabling ChooseNearestWorker can slow down the simulation.

Type

Attribute

Syntax

&lt; Path &gt;.ChooseNearestWorker:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyBroker.ChooseNearestWorker := true

SimTalk

Scope [SimTalk] - Worker Priority [SimTalk] - Worker See also Choose the Nearest Worker [check box] Priority [Worker] Objects [Scope] Workers to Create How the Worker Decides Where to Work

##### ExpRequestCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Use the Exporter Request Control to assign a certain importer to the Exporter/Worker .

In the source code of the method you yourself have to make sure that the request is taken care of (for example with the method engage ).

Plant Simulation runs the Method whenever an Exporter/Worker registers as available with its Broker so that it may be assigned a new importer .

Type

Attribute

Syntax

&lt; Path &gt;.ExpRequestCtrl:method

Assignment Value

You can assign a value of data type method .

Example

MyBroker.ExpRequestCtrl := &amp;myExporterRequestCtrl

SimTalk

engage [SimTalk]

See also

Exporter Request Control [Broker]

**ImpRequestCtrl [SimTalk]**

##### ImpRequestCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Use the Importer Request Control to model assignment strategies of your own.

In the source code of the method you yourself have to make sure that the request is taken care of (for example with the method engage ).

Plant Simulation runs the Method whenever any Broker receives a request or when it would handle the request again, for example when an Exporter/Worker registers as available.

**Note**

For Broker hierarchies Plant Simulation does not call the controls of the sub-Brokers , i.e., of several Brokers that are connected with Connectors in addition. Plant Simulation only calls the control of the Broker which you typed into the object.

Type

Attribute

Syntax

< Path >.ImpRequestCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
MyBroker.ImpRequestCtrl := &myImporterRequestCtrl
-- The Broker tries to satisfy a request. -- It can be an old open request -- or a new request from an arriving part at the importer. -- called by: control of the broker
param obj : object,  -- Importer type : integer -- Importer type (0=failure, 1=setup, 2=work)
var tab    :table[object, string, integer];var t:table
var service    : string;var j:integer
var part,expObj,allWorker: object
t.create
obj.imp.getAlternativeServices(t)
service := t[1,1][1,1]
part := @ --if part.id = 4 then debug end; tab.create;
allWorker := WorkerPartAssignment
if part /= void
	j := allWorker.getRowNo(part)
	if j = -1
		j := 1
		while j<= allWorker.yDim AND allWorker[0,j]/=void
			j := j + 1
		end
		if j<= allWorker.yDim
			allWorker[0,j] := part
			expObj := allWorker[1,j]
			tab.writeRow(1,1, expObj, service, 1 )
			broker.engage( obj, type, tab )
		end
	else
		expObj := allWorker[1,j]
		tab.writeRow(1,1, expObj, service, 1 )
		broker.engage( obj, type, tab )
	end
end
```

SimTalk

**engage [SimTalk]**

See also

Importer Request Control [Broker]

#### AGVPool

