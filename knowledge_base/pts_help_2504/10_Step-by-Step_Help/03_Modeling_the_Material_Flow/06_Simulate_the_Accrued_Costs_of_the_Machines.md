### Simulate the Accrued Costs of the Machines

<!-- image -->

With the object CostAnalyzer you can analyze the costs that accrue for the active material flow objects , for the Part and for the Container in your plant.

You can enter the respective costs on the tab Costs of the material flow objects , and on the tab Costs of the Part and of the Container .

We will demonstrate how to:

- Specify the Costs of the Conveyors
- Specify the Costs of the Stations and the Parts
- Configure the Costs Report
- View the Costs Report

The finished simulation model looks like this:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**Back to Modeling the Material Flow**

#### Specify the Costs of the Conveyors

While creating our model, we also enter the costs which the Conveyors create. To show how the costs from sub-Frames are collected and displayed, we modeled part of our model in the sub-Frame named SubFrame . To show the content of the sub-Frame instead of its icon, we activated Show content on the tab Graphics of the sub-Frame in 3D.

<!-- image -->

For Conveyor1 we typed in these costs:

<!-- image -->

For the Conveyor in the sub-Frame we typed in these values:

<!-- image -->

For Conveyor1 in the sub-Frame we typed in these values:

<!-- image -->

For the Conveyor connecting the AssemblyStation with the Drain we typed in these values:

Back to Simulate the Accrued Costs of the Machines

<!-- image -->

#### Specify the Costs of the Stations and the Parts

Now we enter the costs that the Stations create. To show how the costs from sub-Frames are collected and displayed, we modeled part of our model in the sub-Frame named SubFrame . To show the content of the sub-Frame instead of its icon, we activated Show content on the tab Graphics of the sub-Frame in 3D.

- For Station1 we typed in these values:

<!-- image -->

In addition we typed in a constant processing time of 10 minutes:

<!-- image -->

- For the Station in the sub-Frame we typed in these values:

<!-- image -->

In addition we typed in a constant processing time of 15 minutes:

<!-- image -->

- For the AssemblyStation we typed in these values:

<!-- image -->

We also selected these settings:

<!-- image -->

**Note**

Only type the name of the mounting part into the Assembly Table , not the entire path.

- Next we entered the costs for our part types, namely for the Part and for MyMountingPart :

<!-- image -->

#### Configure the Costs Report

- Finally we configured our Sources named SourceMainParts and SourceMountingParts by typing in a creation interval each:

<!-- image -->

Back to Simulate the Accrued Costs of the Machines

**Configure the Costs Report**

We cannot configure the CostAnalyzer as such. To show the results of the cost analysis, drag the CostAnalyzer from the Frame onto the icon of the HtmlReport and drop it there.

<!-- image -->

- If the content of the HtmlReport is inherited, the data of the CostAnalyzer replaces the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.

<!-- image -->

- If the content of the HtmlReport is not inherited, Plant Simulation appends the data of the CostAnalyzer to the pre-defined content of the HtmlReport . Plant Simulation opens the display window of the HtmlReport automatically.

To show the results of the cost analysis, you can also drag the object CostAnalyzer into the open window of the HtmlReport and drop it there, for example below the heading Statistics . Then the HtmlReport also shows the pre-defined General Information when you click Show Report .

<!-- image -->

This adds the following instruction to the HtmlReport :

**Statistics ## CostAnalyzer [CostAnalyzer]**

**Back to Simulate the Accrued Costs of the Machines**

#### View the Costs Report

The costs report that we created with our settings looks like this:

<!-- image -->

- In the table Investment Costs the Report shows the summed up investment costs of this Frame in the unavailable cells.

Below it lists the investment costs , the depreciation period , and the operating costs of the individual objects inserted into this Frame , row by row.

You can also query the investment costs with the method putInvestmentCostsIntoTable .

- In the table Piece Costs the Report shows die summed up piece costs of the used MU type , in our case of the Part .

- The MU Type (part type) designates the name of the parts when they arrive in the Drain . When parts change their name during the simulation, for example during the different production phases, the costs are assigned to the final product.
- The Piece costs proper is the sum of the material costs , the accrued costs , and the general costs are 8.32 €.
- The Material costs designate the costs, which accrue during the simulation when a new part enters the production, are 8.00 €.
- The Accrued costs designate the costs, which are assigned to the part while it is processed on the material flow object, are 0.17 €.
- The General costs designate the costs, which accrue when a material object is empty during the simulation, are 0.15 €. These costs are distributed across the part types which were processed by the material flow object.
- The Throughput designates the number of parts which were processed and moved through the production line, 10650 parts in our case.
- The Work in process designates the number of parts which are currently passing through the production process, 6 parts in our case.

Click Investment Costs in the dialog of the CostAnalyzer to show the investment costs.

<!-- image -->

You can also query the investment costs with the method putInvestmentCostsIntoTable .

Click Piece Costs in the dialog of the CostAnalyzer to show the piece costs.

<!-- image -->

You can also query the piece costs with the method putPieceCostsIntoTable .

Back to Simulate the Accrued Costs of the Machines

**Simulating the Power Consumption in Your Facility**

