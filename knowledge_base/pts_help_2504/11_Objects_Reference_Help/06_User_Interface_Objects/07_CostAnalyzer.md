### CostAnalyzer

Use the CostAnalyzer for analyzing costs that the individual machines and the Worker cause. The CostAnalyzer computes the costs that accrue for the material flow objects while processing the parts in the facility.

Icon

<!-- image -->

**Description**

The CostAnalyzer also computes the summed up investment costs of the objects. You cannot configure the CostAnalyzer as such.

To show the results of the cost analysis, drag the CostAnalyzer from the Frame onto the icon of the HtmlReport and drop it there.

- If the Content of the HtmlReport is inherited, the data of the CostAnalyzer replaces the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.
- If the Content of the HtmlReport is not inherited, Plant Simulation appends the data of the CostAnalyzer to the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.

<!-- image -->

To show the results of the analysis, you can also drag the object CostAnalyzer into the open window of the HtmlReport and drop it there, for example below the heading Statistics . Then click Show Report .

<!-- image -->

Type in the respective costs on the tab Costs of the active material flow objects and the tab Costs of the Part and of the Container .

<!-- image -->

<!-- image -->

**Note**

At the moment you can only set if the CostAnalyzer collects data or not. We do not provide any other configuration settings.

To show a tooltip with information about the CostAnalyzer , hover with the mouse over it.

To change the length of the graphic and the anchor points of the CostAnalyzer , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the CostAnalyzer to your simulation model, click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

UserInterface &gt; CostAnalyzer on the Home ribbon tab.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Simulate the Accrued Costs of the Machines

How the CostAnalyzer Assigns Costs to Part Types

Costs Shown in the Costs Report

#### How the CostAnalyzer Assigns Costs to Part Types

The material flow objects generate costs during the simulation which result from the total investment costs and the total operating costs per time. These costs are distributed as accrued costs to the parts which the material flow objects process.

If no parts are located on the material flow objects, the costs are allocated to the respective material flow object as general costs.

If the CostAnalyzer computes the result, these general costs are distributed across the part types which the material flow object processed during the simulation. Parts with the same name are allocated to the same part type ( MU Type ). Plant Simulation uses the name that the part has when it arrives at the Drain .

**Note**

For the Work in process the final production costs are not known. For this reason they only contribute with 50 % to the production costs. The assumption is that the work in process parts have covered about half of their production process on average.

Costs for parts which are currently passing through the production process are not precise. Piece costs are only then meaningful if the Throughput is considerably higher than the Work in process .

Not all material flow objects proceed the same during this process.

- The AssemblyStation assigns the costs to the main part. Costs, which accrued for the mounting parts until then, are transferred to the main part.
- The Conveyor assigns the costs proportionately according to the length of the part.
- The DismantleStation assigns the costs to the main part.
- The ParallelStation distributes the costs evenly across its processing places.
- The Container distributes the accrued costs evenly across the storage places if Distribute costs is activated.

In addition, material costs accrue during the simulation when a new part enters the production process.

See also

Depreciation Period [text box]

Investment Costs [text box]

Investment Costs per Length [text box]

Operating Costs [text box]

Operating Costs per Length [text box] Material Costs per Piece [text box]

Distribute Costs [check box]

#### Costs Shown in the Costs Report

The HtmlReport shows the tables Investment Costs and Piece Costs of the cost analysis by default.

You cannot configure the object CostAnalyzer as such. To shows the results of the analysis, drag the object CostAnalyzer into the open window of the HtmlReport and drop it there, for example below the heading Statistics . Then click Show Report .

<!-- image -->

The result looks like this:

<!-- image -->

Compare View the Costs Report in the Step-by-Step help .

Investment Costs

The table Investment costs shows the investment costs , the depreciation period , and the operating costs of the material flow objects inserted into the model hierarchically structured.

**Note**

The HtmlReport shows the investment costs statically, i.e., the values do not change during the simulation run.

For Frames in the hierarchy the table shows the summed up investment costs. These costs are highlighted in light gray. The first row shows the summed up investment costs of the entire model.

For sub-Frames in the hierarchy the table shows the summed up investment costs as well. These costs are highlighted in light gray. The first row shows the summed up investment costs of this sub-Frame .

SimTalk

putInvestmentCostsIntoTable [SimTalk]

getInvestmentCostsTable [SimTalk]

Piece Costs

The table Piece costs shows the costs which accrued for the part types in the individual rows during the simulation.

The MU Type (part type) designates the name of the parts when they arrive in the Drain . When parts change their name during the simulation run, for example during the different production phases, the costs are assigned to the final product.

The Material costs designate the costs which accrue during the simulation when a new part enters the production.

The Accrued costs designate the costs which are assigned to the part while it is processed on the material flow object.

The General costs designate the costs which accrue when a material object is empty during the simulation. These costs are distributed across the part types which were processed by the material flow object.

The Piece costs is the sum of the material costs , the accrued costs , and the general costs .

The Throughput designates the number of parts which were processed and moved through the production line.

The Work in process designates the number of parts which are currently passing through production process. These parts only contribute by half for computing the piece costs.

All costs are averaged per piece.

**Note**

For the Work in process the final production costs are not known. For this reason they only contribute with 50 % to the production costs. The assumption is that the work in process parts have covered about half of their production process on average.

Costs for parts which are currently passing through the production process are not precise. Piece costs are only then meaningful if the Throughput is considerably higher than the Work in process .

SimTalk

getPieceCostsTable [SimTalk]

putPieceCostsIntoTable [SimTalk]

**Dialog Box of the Cost Analyzer**

See also

Depreciation Period [text box]

Investment Costs [text box]

Investment Costs per Length [text box]

Operating Costs [text box]

Operating Costs per Length [text box]

Material Costs per Piece [text box]

Distribute Costs [check box]

#### Dialog Box of the Cost Analyzer

Dialog Box of the CostAnalyzer

Double-click the icon of the CostAnalyzer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

See also

Collect Data [check box] - CostAnalyzer

Investment Costs [button]

**Piece Costs [button]**

**Collect Data [check box] - CostAnalyzer**

##### Collect Data [check box] - CostAnalyzer

To make the CostAnalyzer collect data during the simulation run, select this check box.

To deactivate data collection, clear the check box.

SimTalk

CollectData [SimTalk] - CostAnalyzer

##### Investment Costs [button]

To open a list, which contains the investment costs , which the CostAnalyzer computed, click this button.

<!-- image -->

<!-- image -->

**SimTalk**

getInvestmentCostsTable [SimTalk]

See also

View the Costs Report

##### Piece Costs [button]

Piece Costs [button]

To open a list, which contains the piece costs , which the CostAnalyzer computed, click this button.

<!-- image -->

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The commands are described under the View Menu .

SimTalk

updateDialog [SimTalk]

##### Tools Menu

Tools Menu

The Tools Menu provides commands to access its functions.

Edit Controls

Edit Observers

3D

See also

Tools Menu [general description]

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the CostAnalyzer

\_Methods of the CostAnalyzer

The CostAnalyzer provides;

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

##### getInvestmentCostsTable [SimTalk]

Returns the Investment costs table which the CostAnalyzer designated by &lt;Path&gt; computed.

<!-- image -->

Type

Method

Syntax

```simtalk
< Path >.getInvestmentCostsTable → table
```

Return Value

The return value has the data type table .

Example

```simtalk
CostAnalyzer.getInvestmentCostsTable.openDialog // open the table as a dialog
```

SimTalk

putInvestmentCostsIntoTable [SimTalk]

See also

Investment Costs [button]

**Costs Shown in the Costs Report**

##### getPieceCostsTable [SimTalk]

Returns the Piece costs table which the CostAnalyzer designated by &lt;Path&gt; computed.

<!-- image -->

Type

Method

Syntax

```simtalk
< Path >.getPieceCostsTable → table
```

Return Value

The return value has the data type table .

Example

```simtalk
CostAnalyzer.getPieceCostsTable.openDialog // open the table as a dialog
```

SimTalk

putPieceCostsIntoTable [SimTalk]

See also

Costs Shown in the Costs Report

Piece Costs [button]

putInvestmentCostsIntoTable [SimTalk]

Writes the Investment costs , the Depreciation period , and the Operating costs , which the CostAnalyzer designated by &lt;Path&gt; computed, into the specified DataTable .

For our example the table looks like this:

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.putInvestmentCostsIntoTable(DataTable:table)

Parameter

The parameter DataTable of data type table designates the DataTable into which Plant Simulation writes the investment costs.

Example

CostAnalyzer.putInvestmentCostsIntoTable(MyInvestmentCosts)

SimTalk

getInvestmentCostsTable [SimTalk]

**See also**

**Costs Shown in the Costs Report**

##### putPieceCostsIntoTable [SimTalk]

Writes the Piece costs , which the CostAnalyzer designated by &lt;Path&gt; computed, into the specified DataTable .

<!-- image -->

Type

Method

Syntax

&lt; Path &gt;.putPieceCostsIntoTable(DataTable:table)

Parameter

The parameter DataTable of data type table designates the DataTable into which Plant Simulation writes the piece costs.

**Example**

CostAnalyzer.putPieceCostsIntoTable(MyPieceCosts)

SimTalk

getPieceCostsTable [SimTalk]

See also

Costs Shown in the Costs Report

#### Read-Only Attributes of the CostAnalyzer

Read-Only Attributes of the CostAnalyzer

The CostAnalyzer provides the \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyCostAnalyzer.UUID

#### Attributes of the CostAnalyzer

Attributes of the CostAnalyzer

The CostAnalyzer provides:

- The attribute CollectData .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyCostAnalyzer.CollectData := false
MyCostAnalyzer.CollectData
posit := Station.Cont.XPos
```

##### CollectData [SimTalk] - CostAnalyzer

Sets if the CostAnalyzer designated by &lt;Path&gt; collects data ( true ) or does not collect data ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.CollectData:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyCostAnalyzer.CollectData := true
```

See also

Collect Data [check box] - CostAnalyzer

