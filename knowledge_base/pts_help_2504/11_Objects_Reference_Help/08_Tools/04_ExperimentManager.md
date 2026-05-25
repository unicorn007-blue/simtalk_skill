### ExperimentManager

#### ExperimentManager [object]

Use the ExperimentManager for running experiments with your simulation model.

Icon

<!-- image -->

Description

To add the ExperimentManager to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt; Experiment Manager on the Home ribbon tab.

<!-- image -->

**Note**

We modeled the ExperimentManager as an application object in a Frame . For this reason opening help with F1 and What's This Help in the dialogs of the objects do not work. To open help for the object, select Help &gt; Help on Object in its dialog.

We modeled the dialogs of the objects with the object Dialog . The window of the ExperimentManager does not use the standard Siemens PLM theme, but your Windows theme.

To assign a different name or a label to the object, click it with the right mouse button and select Rename .

Run Experiments with the ExperimentManager shows how you can run your simulation experiments even more productively.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category &gt; Tools and the Topic &gt; Experiment Manager in the dialog Sample Models and click Open Model .

**See also**

| How It Works and What You Can Do with It   | Define Rule-based Settings                                          |
|--------------------------------------------|---------------------------------------------------------------------|
| Defining the Experiments                   | Recording the Results of a Simulation Study                         |
| Controlling the Experiment Runs            | Attributes of the ExperimentManager                                 |
| Viewing Evaluations                        | Configuring DCOM for Remote Access                                  |
| Run Distributed Simulations                | Run Experiments with the ExperimentManager in the Step-by-Step-Help |
| Advanced Settings                          |                                                                     |

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=Lq7rr7kWAFtQaUQX](https://youtu.be/HKDhTbohV6M?si=Lq7rr7kWAFtQaUQX)

#### How It Works and What You Can Do with It

How It Works and What You Can Do with It

The ExperimentManager supports you in running simulation studies.

A simulation study consists of several experiments, which the ExperimentManager automatically executes. You will carry out simulation studies to investigate different variants of the input values and arrive at statistically safe results

You will typically carry out your simulation studies at times when you do not need your Plant Simulation license and your computer for your daily work. This will usually be at night.

The ExperimentManager can also distribute the simulation runs onto several different computers within your local network, compare Executing Distributed Simulations . For executing the simulation studies you need one of these Plant Simulation license for each of the used computers: Professional , Standard , Application , Runtime , Research , or Educational .

When different licenses are available on the used computers, the ExperimentManager can use the Highest Available license.

For controlling the simulation study the ExperimentManager needs one of these licenses: Professional , Application , Research , or Educational .

**Using the ExperimentManager**

##### Using the ExperimentManager

The diagram below shows how we intend the ExperimentManager to be used. The figure shows which chapters you have to read to solve a certain task with the ExperimentManager .

The black filled items are essential in understanding the ExperimentManager , the gray unfilled items are optional.

<!-- image -->

##### Conducting Simulation Studies

In a simulation study we investigate how model parameters, which are a set of input values, influence certain resulting values, which are output values.

An experiment consists of one or several simulation runs for which the input values do not change.

When your simulation model only contains deterministic processes, the output values are uniquely determined by the input values. In such a deterministic simulation study an experiment consists of a single simulation run.

When your model contains components, which show an unpredictable behavior, you will use probability distributions for modeling them. Such components encompass, for example, failures of machines. The stochastic processes lead to fluctuating output values. The output values can then be interpreted as realizations of a random number. The objective of an experiment of a stochastic simulation study is to determine the properties of the probability distributions of the output values, such as the mean value and the standard deviation. Within an experiment the ExperimentManager executes several simulation runs with unchanged input values and determines the output values. For this reason we call the simulation runs of an experiment observations . For carrying out the observations , the ExperimentManager changes the seed values of the random number streams which are associated with the stochastic processes. Type in the number of observations for each experiment into the text box Observations per experiment . Compare Modeling Random Processes in the Step-by-Step Help .

<!-- image -->

##### Defining the Experiments

Video on YouTube

[https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&amp;t=625](https://youtu.be/Rj5eYZu8pl4?si=j8ngdeR3Ykgp2JjR&t=625)

#### Defining the Experiments

Defining the Experiments

After you have finished creating your simulation model, you can start running experiments with it.

A simulation run always has to end. Many models might continue running after the processes, which interest you, have been simulated, for example to simulate failures, etc. When you use the method stop of the EventController in your simulation model, you have to call the method endSim of the ExperimentManager at the appropriate place.

<!-- image -->

**You can:**

- Select the Output Values for the Experiments
- Select the Input Values for the Experiments
- Define the Input Values in the Experiment Table
- Restore Input Values

**· Run Distributed Simulations**

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=474\_fqDFY5CskvSC&amp;t=218](https://youtu.be/HKDhTbohV6M?si=474_fqDFY5CskvSC&t=218)

##### Select the Output Values for the Experiments

Before carrying out your simulation study you have to define the output values. You cannot start the ExperimentManager without output values.

You can view the output values after a simulation run in your model. To open the table Output , click the button Define Output Values . If you want to, you can also type in any explanatory text which describes the output value in plain words. All results are then represented by this text.

<!-- image -->

When you drag a material flow object onto the ExperimentManager , it offers all attributes and methods of this object, which can be used as output values in an experiment study in a selection dialog. Hold down Ctrl and select one or several of these attributes. When you click OK or Apply , the ExperimentManager executes a plausibility check of the output values.

Figure 11-15: Defining the output values

<!-- image -->

In addition, you can specify a Plant Simulation DataTable as the output value. The ExperimentManager determines mean values, standard deviations, and the minimum and the maximum for all numeric values within this table. This enables you to represent result data according to your ideas.

The Output DataTable contains numeric values of data types weight , speed , length , acceleration , real , time , money , and integer . The Output DataTable also contains values of data type string which are usually used as descriptions of numeric values. The ExperimentManager does not consider cells of data types object , table , list , stack , queue , date , and dateTime .

If you typed in true High Values are Better , the ExperimentManager determines all experiments whose parametrization resulted in the maximum mean value for the output value. If you typed in false only the parametrizations with the minimum mean value are determined. The parametrizations are also shown in the Report of the ExperimentManager . This setting is not evaluated for an Output DataTable . If you neither typed in true nor false into the column High Values are Better , this evaluation is not executed for the respective output value.

The ExperimentManager can also process models in a batch run. To do so, start the experiment in the autoexec method with the method startExp :

- If you call the method with the default setting, the ExperimentManager does not show the HTMLReport at the end of the experiment run. (The optional parameter generateReport of data type Boolean is false.)
- If you call the method with the optional parameter generateReport of data type Boolean set to true , the ExperimentManager shows the HTMLReport at the end of the experiment run:

.Models.MySimulation.ExperimentManager.startExp // does not show the report

.Models.MySimulation.ExperimentManager.startExp(true) // shows the report

This corresponds to the check box Show Report on the tab Report and to the respective user-defined attribute showHTMLatEnd of the ExperimentManager .

The method startExp executes the actions which clicking the buttons Reset and Start in the ExperimentManager trigger.

See also

Step 1: Define input values and output values of the experiments in the Step-by-Step Help

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=tcZ63Doub1SXGZw0&amp;t=68](https://youtu.be/HKDhTbohV6M?si=tcZ63Doub1SXGZw0&t=68)

##### Select the Input Values for the Experiments

The ExperimentManager sets the input values in the model before it starts an experiment. The input values are not changed for the simulation runs of the experiment.

The input values have to be of data type string , boolean , speed , length , acceleration , real , integer , or time . You can also use parameters of probability distributions or the contents of a table as input values.

When you hold down Shift and drag a material flow object onto the ExperimentManager , it opens a dialog offering all attributes of this object. Hold down Ctrl and select one or several of these attributes.

Figure 11-16: Selecting input values and output values with drag-and-drop

<!-- image -->

The ExperimentManager only provides attributes of the data types described above. After you have selected the attributes, the ExperimentManager opens the table Input . In addition to selecting attributes, you can also type the names of the attributes into it.

Figure 11-17: Specifying the input values

<!-- image -->

You can also click the button Define Input Values to open this table. You can type input values into the table Input or you can delete them from it.

<!-- image -->

If you want to, you can also type in any explanatory text which describes the output value in plain words. All results are then represented by this text. After closing the table Input , the ExperimentManager checks the plausibility of the input values.

Click Define Experiments and type the user-defined names of the experiments into the ExpTable . The ExperimentManager deletes the user-defined experiment names when creating an experiment design.

<!-- image -->

See also Step 1: Define input values and output values of the experiments in the Step-by-Step Help Video on YouTube https://youtu.be/HKDhTbohV6M?si=1UaMMz81vspoflcj&amp;t=168

[https://youtu.be/HKDhTbohV6M?si=474\_fqDFY5CskvSC&amp;t=218](https://youtu.be/HKDhTbohV6M?si=474_fqDFY5CskvSC&t=218)

##### Define the Input Values in the Experiment Table

To open the experiment table ExpTable , click Define Experiments .

<!-- image -->

In this table you can define the input values, which only depend on the number of the experiment. We call this type of parametrization static parametrization . To deactivate static parametrization, clear the check box Use input values . You can only open the experiment table ExpTable by clicking the button Define Experiments after you did set the input values.

<!-- image -->

You can exclude individual experiments from a simulation study by typing false into the corresponding cell in the column Active. By typing in true , you can execute these experiments at a later point in time by clicking Start without having to repeat already executed experiments. The following columns show the input values which you typed into the table Input . You can type in the values for the individual experiments.

Click Define Experiments and type the user-defined names of the experiments into the ExpTable . The ExperimentManager deletes the user-defined experiment names when creating an experiment design.

See also

Step 1: Define input values and output values of the experiments in the Step-by-Step Help

##### Restore Input Values

Select Tools &gt; Advanced Settings &gt; Settings &gt; Restore Input Values to restore these input values after each experiment run.

By default, this setting is deactivated. Compare Restore original input values .

The ExperimentManager recognizes if the current values of the input values differ from the saved values when you start an experiment run and shows a warning message. You can then decide if the ExperimentManager saves the current values of the input values or not. In both cases the ExperimentManager starts the experiment run.

The command Tools &gt; Restore Input Values writes the values saved in the ExperimentManager back to the model. This way you can return to the original model configuration after an unwanted interruption of the experiment run, caused, for example, by a debugger call. The method restoreParam of the ExperimentManager triggers this action.

<!-- image -->

**Note**

To determine the different observations of an output value, the ExperimentManager changes the random number values. You have to reset this value in the dialog of the EventController .

##### Controlling the Experiment Runs

#### Controlling the Experiment Runs

To start an experiment run, click Start in the dialog of the ExperimentManager . To delete all results of an experiment run, click Reset .

When you used distributed simulations, the ExperimentManager terminates the Plant Simulation processes on the simulation machines.

<!-- image -->

**Note**

As each simulation run has to end, you must type the End time into the EventController . If your simulation model contains a ShiftCalendar , objects with failures, etc., the simulation might not end, making it impossible to use the ExperimentManager .

**Note**

It is important that no Plant Simulation processes run permanently on the simulation machines. This, might, for example, occur if you inadvertently terminate the controlling Plant Simulation process .

You can stop the experiment run by clicking Stop . The observations of the current experiment will still be executed. You can continue an interrupted experiment run later on at an opportune time by clicking Start again. If you do not click Reset , the ExperimentManager retains the results of the already executed experiments.

You can prematurely cancel an experiment study by clicking Reset in the dialog of the ExperimentManager . If you click one of the three buttons of the EventController while an experiment study is being executed, Plant Simulation shows the message asking if you want to open the dialog of the ExperimentManager that controls the experiment study.

If you are not using dynamic parametrization with rules, compare the example of a Dynamic Parametrization , you can execute the experiments of an experiment run in arbitrary order, compare Define the Input Values in the Experiment Table . You can change the input values of an already executed experiment on the table ExpTable or you can append additional new experiments to the end of the table ExpTable . When you click the button Start , without clicking Reset beforehand, the ExperimentManager only executes the changed and the new experiments.

**Note**

The results of previously executed experiments can be lost through this iterative procedure when you change the simulation model during an interrupted experiment run. After changing your model, you have to delete already executed experiments by clicking Reset and start a new experiment run.

During an experiment run you can view which simulation run of which experiment is executed at the moment. When you are using distributed simulations without rules, you can view the total number of executed observations. When you are employing simulation without rules together with distributed simulations, you cannot interrupt the experiment run, as simulation runs for different experiments may have been started.

The ExperimentManager can also run models in a batch run. Start the experiment in the experiment study in the autoexec method with the method startExp .

- If you call the method with the default setting, the ExperimentManager does not show the HTMLReport at the end of the experiment run. (The optional parameter generateReport of data type Boolean is false.)

.Models.MySimulation.ExperimentManager.startExp // does not show the report

- If you call the method with the optional parameter generateReport of data type Boolean set to true , the ExperimentManager shows the HTMLReport at the end of the experiment run:

.Models.MySimulation.ExperimentManager.startExp(true) // shows the report

This corresponds to the check box Show Report on the tab Report and to the respective user-defined attribute showHTMLatEnd of the ExperimentManager .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

See also

Step 2: Run the experiments with the settings you defined in the Step-by-Step Help

Automatically Generating Experiments

Automatically Generating Experiments

The Tools menu provides commands for automatically creating experiments.

The ExperimentManager assigns values to all input values; this is called experimental design. It automatically fills the experiment table ExpTable . All experiments and their evaluations will be deleted when you employ an experimental design.

<!-- image -->

**You can:**

- Use a Multi-level Experimental Design
- Use a Random Experimental Design
- Use a Two-level Experimental Design and Use Factorial Analysis

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

###### Use a Multi-level Experimental Design

The command Tools &gt; Multi-level Experimental Design opens the table GeneralDesign .

Let us assume that to systematically investigate the input values you want to change all values between two boundaries in steps which you define.

<!-- image -->

In the table GeneralDesign you can define a multi-level experimental design. All input values are diversified independently of each other within the boundaries.

The number of interim values results from the increment size which you can type into the table GeneralDesign for each input value.

The table below results in 2 times 5 times 3 times 2 equaling 30 experiments. The first input value is allocated the values 20.0000 and 1:20.0000. The third input value is allocated the values 50, 70, and 90. The range of values of the second input value has five values. As the ExperimentManager creates all combinations of these allocations, this results in a considerable amount of experiments for even a few input values. The ExperimentManager tells you the number of resulting experiments and offers to cancel the experimental design.

Figure 11-18: Defining the input values and multi-level experimental design

<!-- image -->

Close the table GeneralDesign . After the ExperimentManager has informed you about the number of resulting experiments, it opens the table ExpTable .

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=X7xd5wBkMwRuUkxw&amp;t=916](https://youtu.be/HKDhTbohV6M?si=X7xd5wBkMwRuUkxw&t=916)

###### Use a Random Experimental Design

If you want to create a large number of experiments whose input values are not distributed according to certain patterns, you can do this with the random experimental design.

The results of such an experiment study are ideally suited for training an Artificial Neural Network .

The command Tools &gt; Random Experimental Design opens the table RandomDesign . Type in the values defining the random experimental design. All input values are determined independently of each other via a uniform distribution between the bounds by throwing the dice.

<!-- image -->

Figure 11-19: Defining the input values and random experimental design

<!-- image -->

Then, type in the number of experiments into the dialog that opens.

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=IK2PIAIoeckC3bTu&amp;t=1058](https://youtu.be/HKDhTbohV6M?si=IK2PIAIoeckC3bTu&t=1058)

###### Use a Two-level Experimental Design and the Factorial Analysis

In an analysis of factors you can explore upon which of the input values one of the output values significantly depends (screening).

You are not as much interested in exact and statistically safe results, but you mainly want to investigate how the input values influence the model. For this purpose we use an experimental design in which each input value is allocated two different values (levels). When you have n input values, a two-level experimental design consists of 2n experiments. The factorial method enables you to detect the combined effects of several input values or the nonexistent effect of individual input values on the output value.

We describe how to proceed using the inventory model by Law and Kelton. The model is described in Averill M. Law and W. David Kelton: Simulation Modeling &amp; Analysis. McGraw-Hill 1991, Chapter 1.5 Simulation of an Inventory System , pages 75-82. The execution of the experiment is described in Chapter 12 Experimental Design and Optimization on pages 656--670.

To open this model and to run experiments with it, click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection and click Open Model .

This simulation study intends to find the most cost-efficient order strategy for an inventory system. We simulate for 10 years. The output value designates the inventory costs per month.

Customers randomly arrive with an average interval of 3 days (exponentially distributed) and order 1 to 4 parts according to this probability distribution. The table below contains a random order size.

|   Order size | With probability   |
|--------------|--------------------|
|            1 | 1/6                |
|            2 | 1/3                |
|            3 | 1/3                |
|            4 | 1/6                |

The inventory is checked every one or two months. An additional input value is the interval between the inventory checks, here called the inventory-evaluation interval .

When the safety stock falls below a certain level, an employee orders the difference to the maximum stock level from the supplier. The safety stock and the difference to the maximum stock level are input values of the simulation study. The table below contains input values of the ordering strategy for the store.

| Item         | Values   |
|--------------|----------|
| Safety stock | 20, 60   |
| Difference   | 10, 50   |

| Item                          | Values      |
|-------------------------------|-------------|
| Maximum stock level           | 30, 70, 110 |
| Inventory-evaluation interval | 1, 2 months |

Ordering parts result in costs. We can choose between two delivery options : A fast, but expensive, express order and a cheaper normal order, which takes longer.

| Item               | Normal   | Express   |
|--------------------|----------|-----------|
| Setup costs        | 32 €     | 48 €      |
| Incremental costs  | 3 €      | 4 €       |
| Earliest lead time | 15 days  | 7 days    |
| Latest lead time   | 30 days  | 14 days   |

The shipments randomly arrive at the store between the earliest and the latest lead time.

We assigned three different random number streams with different seed values to the random model components inter-arrival time, size of demand, and lead time.

Parts in the store cause holding costs of 1 € per month and part. When customer orders cannot be met backlog costs of 5 € per month and per part accrue.

The inventory-evaluation interval , the type of order , the safety stock , and the difference between the maximum inventory level are input values. The holding costs are the only output value. While the input values inventory-evaluation interval and type of order have two levels only from the beginning, we manually have to set two levels for the safety stock and for the difference .

To set the lower level and the upper level for all input values, select the menu command Tools &gt; Two-level Experimental Design . This opens the table Design .

Figure 11-20: Two-level experimental design for four input values

<!-- image -->

After you close the table Design , the ExperimentManager creates 16 experiments. As random components exist, you should execute several simulation runs for each experiment.

You can check which input values result in which output values, by clicking the button Results on the tab Evaluation , which opens the table Results .

Figure 11-21: Overview of the results of the experiment study

<!-- image -->

After the simulation study you can execute a factorial analysis. To open the table Effects , select Tools &gt; Analysis of Factors .

The main effects H1, … H4, describe the average change of inventory costs, which you have to take into account, when you change the respective input value from the lower to the upper level. Surprisingly enough our example showed that the inventory-evaluation interval does only slightly affect the output value. The order type Express though will considerably increase costs. The interactions effects W describe the mean change of the output value based on the simultaneous change of two input values.

Figure 11-22: Evaluations of two-level experimental design: main effects and interdependency effects

<!-- image -->

The experimental design for the described example showed that a further investigation with the input values safety stock and difference suffices. You can initiate the systematic search within a parameter space via rule-based settings or with a multi-level experimental design for the two remaining input values.

##### Viewing Evaluations

#### Viewing Evaluations

View the input values and the output values of the individual experiments on the tab Evaluation . It provides a complete overview over all experiments.

<!-- image -->

**You can:**

- Click Results open the table Results . It shows all input values and all output values for all experiments. The button opens this table as a dialog. The context menu command Show Results does not open the table as a dialog.
- Click Detailed Results to open the table DetailedResults . It shows the mean value, the standard deviation, the minimum, the maximum, and die interval bounds of the confidence intervals for all output values. If a table is an output value, the detailed results show subtables containing the mean values, the standard deviations, the minimum values, and the maximum values of the numerical values of the output table.

**Note**

You can use the attribute ResultsPrecision to set the number of decimal places of the results in the tables. This setting also determines how the values are shown in the HtmlReport . If you want to show the results with a suitable number of decimal places, you have to set the value of the attribute ResultsPrecision of the ExperimentManager to a value between 1 and 14 . The default setting -1 shows the results values with maximally 15 decimal places.

**Compare this example:**

ExperimentManager.ResultsPrecision := 3

**Note**

You can use the attribute DecimalSeparator of data type string to set the values "." (period) or "," (comma) as the decimal separator. The results tables then use this decimal separator, compare Text File Format &gt; Decimal Separator .

- Show the Results in a Report .
- View Output Values of Interest .

Figure 11-23: Statistical evaluation for the output values

<!-- image -->

The results of all simulation runs are contained on the subtables of the columns Observations . To open the subtable, click in the respective cell and press F2 .

You can show all parametrizations of the model for each output value with the method getBestParameter , which result in a maximum or a minimum value respectively.

Experimentmanager.getBestParameter(DataTable, "Throughput", true)

The first parameter of the method getBestParameter designates an object of type DataTable or an attribute of data type table .

This DataTable contains a set of values of the output values in each row which have a maximum or a minimum output value.

The second parameter designates the output value.

The third parameter sets if you are interested in a Maximum (designated by true ) or a Minimum (designated by false ).

The fourth optional parameter sets if the table also show additional output values of the experiment study (value TRUE).

The HtmlReport shows the values of all input and output values, which lead to a maximal or minimal mean value of the respective output value respectively under the heading Best Parametrizations of the Model . If several parametrizations with minimal or maximal mean value exist, you can analyze target conflicts of different output criteria by showing all output values in the HtmlReport .

See also

Defining the Output Values of the Experiments

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=WM3S7G1tZzp2fTNY&amp;t=504](https://youtu.be/HKDhTbohV6M?si=WM3S7G1tZzp2fTNY&t=504)

##### Show the Results in a Report

To open a Report , click Report on the tab Evaluation or select the command on the context menu.

<!-- image -->

After the experiment run you can save the report to the folder whose name you type in under Tools &gt; Advanced Settings &gt; Report .

<!-- image -->

To show the logo of your company in the Report , create a new icon for the ExperimentManager and name it logo . Then paste the logo of your company to this icon.

<!-- image -->

Experimental studies with a large number of experiments can create extensive Reports whose detailed statistics are of no great use to you. When the number of executed experiments exceeds the value of the attribute MaxNumExpForDetailedReport , the Report does not contain the topic with the statistical evaluations of the output values.

The mean values of the output values are still contained in the topic General Information of the reduced Report .

The default value of the attribute is 1000 . You can change it to meet your needs though.

See also

Step 3: Evaluate the results of the simulation study in the Step-by-Step Help

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=WM3S7G1tZzp2fTNY&amp;t=504](https://youtu.be/HKDhTbohV6M?si=WM3S7G1tZzp2fTNY&t=504)

View Output Values of Interest

View Output Values of Interest

Type in the confidence level for the confidence intervals into the text box Confidence level (%) on the tab Settings .

In models with random components the output values usually fluctuate around a mean value.

##### View Output Values of Interest

<!-- image -->

To select the output values for this evaluation, click Variable on the tab Evaluation . This opens a selection dialog. You can select several values by holding down Ctrl and clicking the values. To ensure readability, the output values should have a similar order of magnitude.

Figure 11-24: Selecting output values of interest

<!-- image -->

To close the dialog, click OK . To open the chart with the selected output values, click Show on the tab Evaluation . The output values for the individual experiments are connected with each other. The chart draws the confidence intervals or the min-max intervals around the mean values of the output values. In addition to the min-max interval, the median or the 50 percent quartile, the 25 percent quartile, and the 75 percent quartile can be shown. An x percent quartile is a certain value so that x percent of the observations of an output value of an experiment are less than or equal to this value. The letter x designates one of these percentages, 25, 50, or 75.

The figure below shows the min-max values and confidence intervals for the selected output value combined in a single chart.

<!-- image -->

The values are depicted as a box plot like this:

<!-- image -->

Selecting Tools &gt; Analysis of Variance enables you to test the hypothesis if the mean values of a selected output values in two experiments are the same or if they are significantly different. To check this, Plant Simulation runs a test.

Figure 11-25: The p values of the t test for the observations of an output value in the executed experiments

<!-- image -->

Figure 11-26: Statistics of a selected output value

<!-- image -->

You might ask yourself how many observations are required so that the confidence interval for an output value reaches the desired width. In general, you can expect halving of the width of the confidence interval after the multiplication of the number of observations. Selecting Tools &gt; Number of Observations shows the functional correlation between the number of observations and the width of the confidence interval.

The chart shows how the number of observations on the x-axis influences the width of the confidence interval on the y-axis for the selected output value.

Figure 11-27: Estimate of the number of observations based on an experiment with 10 observations

<!-- image -->

In addition to viewing the output values, you can:

- Add User-defined Charts and Sankey Diagrams to the Report
- Add User-defined Entries to the Report
- Prematurely Terminate an Experiment Study

**See also**

Step 3: Evaluate the results of the simulation study in the Step-by-Step Help

###### Add User-defined Charts and SankeyDiagrams to the Report

To show Charts with special evaluations for each experiment or SankeyDiagrams in the Report , drag these chart objects onto the ExperimentManager .

This opens a table with all charts that are registered for this purpose. Delete the Diagrams or SankeyDiagrams which you do not want to show in the HtmlReport from this table.

The HtmlReport only shows evaluations with Charts or SankeyDiagrams by default for the first observation of an experiment.

If you want to show these evaluations for all observations in the HtmlReport you have to set the attribute Charts4AllObservations from false to true .

You can also open the table by selecting Tools &gt; Charts .

Figure 11-28: Registered Chart objects

<!-- image -->

As the Report uses the labels of the charts to display them, the different charts should have different labels.

Figure 11-29: Report of an experiment study with two user-defined charts

<!-- image -->

As the graphics required for displaying the charts are saved in the model, we recommend to reset the ExperimentManager before saving the model. The respective objects requiring a lot of disk space will then be deleted in the model and the model files will thus become smaller.

If you would like the ExperimentManager to save the model files after each experiment, we recommend to not include charts in the report as the user-defined graphics greatly increase the size of the model file.

**Note**

When you use a distributed simulation, you cannot add user-defined charts to the Report .

###### Add User-defined Entries to the Report

You can add your own items to the report using the HtmlReport named UserReport which is inserted into the ExperimentManager .

ExperimentManager.UserReport.appendConveyor(to_str("Observed waiting time ", Machine.statWaitingTime," in experiment ", ExperimentManager.currExpNo))

###### Prematurely Terminate an Experiment Study

When a simulation reaches a state during an experiment run which does not warrant further investigations of the running experiment, i.e., a non-promising scenario was detected, you can prematurely terminate this experiment in a non-distributed simulation by calling the method endOfExperiment in your source code.

The ExperimentManager runs the statistical evaluations of this experiment up until the point in time at which you terminated the experiment. The table Detailed Results on the tab Evaluation shows the reduced number of observations in the column Observations which were available for the statistical evaluation. Afterward the ExperimentManager parametrizes the next experiment in the non-distributed experiment study.

For a distributed simulation all simulation runs will always be started, as they are scheduled at the start of the experiment study and can thus be executed in any random sequence.

if Drain.StatNumIn > 15 // non-promising great throughput ExperimentManager.endOfExperiment end

#### Advanced Settings

Advanced Settings

Select Tools &gt; Advanced Settings to open the dialog in which you can select additional settings. You can run simple experiment studies without changing any of the default settings.

Figure 11-30: Selecting settings in the dialog Advanced Settings

<!-- image -->

The confidence level is used for calculating all of the confidence intervals. You can change this value after a study has been finished and observe how the changes affect the tables and charts.

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=VXUebgk278pe8Wn1&amp;t=800](https://youtu.be/HKDhTbohV6M?si=VXUebgk278pe8Wn1&t=800)

##### Use a Configuration Method

Click the ellipsis button and select the Configuration method .

Or type in the name of the Method in which you set the input values. Click Apply in the dialog Advanced Settings .

You might, for example, use the configuration method to set the worker creation table of the WorkerPool to determine the number of Workers in an experiment.

This method will be called after the input values have been set, and after the rules have been executed. You can use all commands which SimTalk provides.

The parameter localExp designates the number of the respective experiment. For most simulation studies this parameter is the row number in the experiment table.

SimTalk

UserConfigMethod

**Use an Evaluation Method**

##### Use an Evaluation Method

Click the ellipsis button and select the Evaluation method .

Or type in the name of the Method in which you define the final evaluations of the experiment study. Click Apply in the dialog Advanced Settings .

The ExperimentManager calls this method after it read the output values. You can use all commands which SimTalk provides.

The parameter ExperimentManager designates the calling ExperimentManager .

SimTalk

UserEvalMethod

##### Set the Random Number Seed Values

When your model contains stochastic processes, you have to execute several observations within each experiment. The ExperimentManager realizes the different observations by changing the attribute RandomNumbersVariant of the EventController .

Plant Simulation uses this value to determine the start values for creating random numbers. By default, the ExperimentManager uses the value of the attribute RandomNumbersVariant for simulating an observation of the output values which corresponds to the number of the observation. This process is known as common random numbers ( CRN ). Then the observations of different experiments are not independent of each other so that certain statistical evaluation methods should not be used. A long failure, which always occurs in the simulation runs of the first observation, can, for example, lead to a significant reduction of the output for these simulation runs. Statistics applications, like the Analysis of Variance ( ANOVA ), need independent runs within and between all experiments.

Click and select the Method in which you set the attribute RandomNumbersVariant of the ExperimentManager . Or type in the name of the Method in which you define the final evaluations of the experiment study. Click Apply in the dialog Advanced Settings .

If you do not want to use the CRN method, you can use the following method template for generating the seed table:

```simtalk
param ExpNo,ObservNo:integer
EventController.RandomNumbersVariant := ObservNo + ?.~.NumRuns * (ExpNo - 1) // NumRuns is the attribute of the Eventcontroller which sets the number of observations of the experiments
```

The ExperimentManager only works correctly when Increment Variant on Reset in the EventController in your simulation model is deactivated.

SimTalk

UserSeedValueMethod

See also

RandomSeed of the material flow objects

Random Numbers Variant of the EventController Specify Settings for the Statistical Reliability All confidence intervals use the value you type in as the confidence level.

<!-- image -->

You can also show min-max intervals with quartiles, compare View the Results in a Chart .

##### Additional Settings

You can activate Restore original input values in the group box Additional Settings :

Restore original input values

Select the check box to restore those values which you entered before executing the experiment study. Compare Restore the Original Model Configuration .

**Restore original input values**

##### Restore original input values

Select Tools &gt; Advanced Settings &gt; Settings &gt; Restore original input values to restore the input values after each experiment run. By default, this setting is deactivated.

**Note**

You do not need this setting for a distributed simulation as the controlling ExperimentManager does not modify the model within a distributed simulation.

When you selected the check box Restore original input values for a non-distributed simulation, the input values are saved before the first simulation run of the experiment run in the ExperimentManager and are written to the model again after the last simulation run. To set the saved original input values at the end of the experiment run, the ExperimentManager executes a Reset . This Reset is, for example, required to set buffer capacities.

The ExperimentManager recognizes if the current values of the input values differ from the saved values when you start an experiment run and shows a warning message. You can then decide if you want to start the experiment run without saving the values, or you can save the values by selecting the menu command Tools &gt; Store Input Values . The method storeParam of the ExperimentManager triggers this action.

The command Tools &gt; Restore Input Values writes the values saved in the ExperimentManager back to the model. This way you can return to the original model configuration after an unwanted interruption of the experiment run, caused, for example, by a debugger call. The method restoreParam of the ExperimentManager triggers this action. The report shows the original input values.

<!-- image -->

**Note**

For determining the differing observations of an output value, the ExperimentManager changes the random number seed values, which you can also reset this way.

Validating the Simulation Study

Validating the Simulation Study

Validate your simulation study under Tools &gt; Advanced Settings &gt; Validation .

<!-- image -->

To analyze any errors which occurred, you can click All Recordings on the tab Validation . This opens a table showing all actions which the ExperimentManager executed. The figure below shows the Recording table of an experiment study with two observations per experiment.

<!-- image -->

###### Save the Models After Each Experiment

Select the check box Save models after experiments on the tab Validation to save the model after each experiment.

For a distributed simulation the ExperimentManager saves the model at the end of the simulation study.

Type the name of the model file into the text box Model file (*.spp). Type the name of the folder into which you want to save the file into the text box Model Folder .

**Note**

You cannot save the models during an experiment run when you use distributed simulations.

<!-- image -->

<!-- image -->

###### Specify the Parameters of a Simulation Run in the Simulation Model

To parametrize a model according to a simulation run, use the settings below Model parameterization .

Clicking the button Set Parameters calls the method setParameter , which expects two parameters of data type integer : Number of the Experiment and number of the Observation.

<!-- image -->

<!-- image -->

**Note**

If you use rules, you cannot set the parameter of a certain experiment without running the entire experiment study.

To execute additional experiment studies with this model, we recommend to re-enter the model parameterization for the first experiment, the first observation, and for the first run into the model after validation.

##### Run Distributed Simulations

If your computer has a multicore processor, you can significantly shorten the time it takes to run a study by executing the simulation runs in parallel.

The ExperimentManager recognizes the number of cores and starts several Plant Simulation processes on your computer. You can configure distributed simulations under Tools &gt; Advanced Settings &gt; Distribution .

Figure 11-31: Settings for distributed simulations

<!-- image -->

<!-- image -->

As for a distributed simulation, without using rule-based settings, the simulations for all experiments can be executed in parallel, the ExperimentManager then only shows the number of simulations that have already been executed in its dialog.

If you have several Plant Simulation licenses of the same type and if you want to run time-consuming and extensive simulation studies, the ExperimentManager can execute the simulation runs on several computers within your local network (LAN).

**Note**

You can also execute an optimization with the GAWizard using the distributed simulation. It provides the same functionalities as the ExperimentManager .

Executing the simulation runs in parallel on several computers can significantly reduce the time the simulation study takes. The ExperimentManager on the control computer starts Plant Simulation processes on other computers, on the so-called simulation machines , loads the model, which was saved last, on the simulation machines and manages the simulation results, which the individual simulation machines arrived at. You will define the experiments in the ExperimentManager on the control computer.

**Note**

The entire simulation model is transmitted to the simulation computers within your LAN when you start an experiment study. If this process takes a very long time, we recommend to not employ distributed simulations. Be aware that the simulation model should not access external files.

If a multiprocessor computer is available for distributed simulations, you can use this computer multiple times as your simulation computer. A respective license for Plant Simulation has to be available though. The ExperimentManager recognizes a computer with several cores. Select the check boxes Distributed simulation in both dialogs as shown below to use distributed simulations.

Click Insert and type in the name of the computer on which the simulation runs are going to be executed. Type in the number of parallel processes on the simulation machine.

<!-- image -->

If you would like to know how many cores the simulation machine has, double-click localhost (n) . The dialog then shows this number in the text box Number of parallel processes .

If you did not type in any simulation computers yet, and you then select the check box, the ExperimentManager executes distributed simulations according to the number of cores. In this case the table of the simulation computers shows localhost (n) . Then number n, designating the number of cores, does not show the actual number of used cores though but the number of available cores on any host that will be used, local or across the network. This ensures that distributed simulations with this model on another computer uses then number of available cores.

In this case the simulation machines are not visible. When the attribute RemoteMachinesVisible of the ExperimentManager has the value true , the simulation machines will be visible. You can view and change the attribute in the window Show Attributes and Methods ( F8 ).

If an error occurs during the distributed simulation and if the attribute SaveModelOnError has the value true, the current state of the model is saved on the Desktop of the remote computer with the name ErrorModel.spp . You can use this model to analyze a hard to reproduce error in your model that caused a canceled simulation run. All Recordings on the tab Validation of the dialog Advanced Settings shows the description of the error and a hint to the model file ErrorModel.spp and to the remote computer.

You can set the time between starting the remote processes of a distributed simulation a delay of milliseconds with the attribute DCOM\_StartDelay . This time is required for preparing the Plant-SimulationProcesses. The default setting is a millisecond. You can change the value in the window Show Attributes and Methods ( F8 ).

You can set if the simulation runs of a distributed or of a non-distributed study are being executed with deactivated MU and State Animation with the attribute simulateWithAnimation

The check box Simulate with 3D sets the boolean attribute SimulateWith3D of the ExperimentManager or of the GAWizard respectively. The default value is true .

When you clear the check box or set the attribute SimulateWith3D to false , large 3D models will be loaded faster. The simulation might also run faster. Access to 3D in your model or in the used libraries with SimTalk is then not possible.

Click Insert and Remove to designate specific computers within your LAN as simulation machines. Instead, you can also double-click an entry in the list. Click Test to check if the selected remote computer is able to run a remote simulation or not.

After the simulation study is finished, you can track the execution of the simulation runs for all simulation machines. When errors occurred on the simulation machine, you can analyze the cause of the error by clicking the button Protocol . This opens the table MachinesTable containing information about all used simulation machines. Column 8 of this table recorded the communication of the controlling computer with the respective simulation machines. To open a subtable, click in the respective cell and press F2 .

At the start of the simulation study, the ExperimentManager starts Plant Simulation processes on all simulation machines with the license you selected under Remote license, compare Execute Experiments with the ExperimentManager . These Plant Simulation processes execute simulation runs one after the other.

Type the CPU time into the text box Terminate after after which the ExperimentManager terminates a Plant Simulation process on a simulation machine if the simulation did not progress during this CPU time. This might, for example, occur when a simulation run opened the Debugger or if it does not terminate because of an endless loop.

When no additional simulation runs have to be executed for the simulation study, all Plant Simulation -processes on the simulation machines will be terminated.

To start the Plant Simulation process on the simulation machine with a lower priority, select the check box Lower priority. Then you can work better on the simulation machine at the same time.

After the simulation study has been finished, you can open an overview over the simulation machines, which the simulation experiment used, by selecting Evaluate Simulation Machines on the context menu. Analyzing the number of simulation runs on the simulation machines and their mean run times enables you to better organize future distributed simulation studies. For a few parallelizable simulation runs it might be better to not use a slow simulation machine, as this computer might cause faster computers to wait for it.

Figure 11-32: Evaluating the simulation runs

<!-- image -->

Figure 11-33: Evaluating the simulation machines

<!-- image -->

During the simulation study you can observe how parallelizable simulation runs are executed. Select Show Distributed Simulation on the context menu to do so.

When employing distributed simulation, you cannot handle data within your LAN the way you are used to do. We recommend to not read data from files, but to first save them to your model. You cannot save the active model while distributed simulations are running.

If you would like to log special events or system states in the Report of the ExperimentManager , the Frame containing the simulation model has to contain corresponding Methods with prompt messages.

You can designate the number of the simulation run, which belongs to the row in the JobsTable , on the associated simulation computer with the attribute currentTaskNo of the ExperimentManager .

// use the numbers of the experiment and of the observation during the simulation

```simtalk
if ExperimentManager.UsingRemote // Use distributed simulation
	var n:integer := ExperimentManager.currentTaskNo
	ExperimentNo  := ExperimentManager.JobsTable[1,n]
	ObservationNo := ExperimentManager.JobsTable[2,n]
else
	ExperimentNo  := ExperimentManager.CurrExpNo
	ObservationNo := ExperimentManager.CurrRunNo
end
```

**Note**

If you use rules, all observations for an experiment have to be finished before the next experiment can start. For this reason only the observations of a single experiment can be executed in parallel when you employ distributed simulation.

Video on YouTube

[https://youtu.be/HKDhTbohV6M?si=q8jaR-Ni1VqFKS8O&amp;t=1125](https://youtu.be/HKDhTbohV6M?si=q8jaR-Ni1VqFKS8O&t=1125)

Defining Rule-based Settings

Define Rule-based Settings

You can parametrize the experiments in the ExpTable . The parameters only depend on the respective number of the experiment. We call this type of parameterization static parameterization . You can also use rules to set the input parameters depending on the results of the previous experiment. We call this type of parameterization dynamic parameterization .

You can apply rules to input values of the data types weight , speed , length , acceleration , real , integer , and time . You cannot apply rules to input values of data type string or boolean . You can set input values of any type in the Configuration method .

<!-- image -->

A rule consists of a condition and of an action. The action will only be executed, when the condition is met. The rules are evaluated before the experiment when you select the check box Rule-based settings on the tab Rules and when the Number of experiments which you entered, has not been reached yet.

You can create, manage, and delete rules by clicking the buttons.

- To create a new rule, click Create New Rule . Enter a name which meets the naming conventions for user-defined names in Plant Simulation .
- To open a table, which contains all rules, click Show All Rules . This table only shows the rules. Do not change them there as then the ExperimentManager does not carry out any plausibility checks.
- To delete the displayed rule, click Delete Displayed Rule .

How Do Rules Work?

How Do Rules Work?

The condition of a rule is a logic expression which you define in a table or in a method.

The part of the condition which is defined by a table is called the table condition , the part which is defined by a method, is called method condition .

The tab Rules provides buttons with these names. The action will only be carried out when both conditions, i.e., the table condition and the method condition are met. The table condition is checked first. When you leave the table of the table condition empty, the table condition is met. The methods for a method condition , which you defined in the ExperimentManager , all have the return value true .

The action of a rule consists of a table action , which you define in a table, and of a method action . The tab Rules provides buttons with these names. The table condition will be executed first.

**Table Condition**

**Table Condition**

To open the table into which you enter the table condition , click the button Table Condition .

The ExperimentManager only saves and processes an error free condition.

**Table Action**

To open the table into which you type the table action , click the button Table Action .

The operators +, -, +%, -% access the input values of the previous experiment.

- The operator +% increases the input values of the previous experiment by the percentage, which you type into the column Value .
- The operator -% works along the same lines.
- The operator = sets the value to a constant, which you typed into the column Value .
- The operator + increases the input values of the previous experiment by the value which you typed into the column Value . This operator matches the instruction x:= x + r , r being the value from the column Value .

**Method Condition**

**Method Condition**

To open the dialog of the Method , click the button Method Condition .

Then, type in the method condition.

**Method Action**

To open the dialog of the Method , click the button Method Action .

Then, type in the source code which the method action is going to execute.

**Scope and Priorities**

**Scope and Priorities**

If you did not select the check box Rule is active , the ExperimentManager does not use this rule for any of the experiments.

<!-- image -->

Type in the scope of application into the text box Valid for experiment . Type in the number of the experiment. When you do not type in anything, the rule is active.

**Initialization Rules**

Rules which are only evaluated in the first experiment are called initrules or initialization rules .

You can designate an initialization rule by selecting the check box Use for first simulation run . You cannot define a condition for an initialization rule as there is no previous experiment. You cannot use the operators +, +%, -% for the table actions of initialization rules, as these access the results of the previous experiment. A table action of an initialization rule thus only contains the operator =.

<!-- image -->

**Priority of a Rule**

**Priority of a Rule**

Define the sequence in which the rules are evaluated via the priority which you type into the text box Priority of the rule .

The ExperimentManager evaluates rules with a higher priority before it evaluates rules with a lower priority.

<!-- image -->

##### Example of a Dynamic Parameterization

We'll demonstrate how to use rule-based parameterization by means of the inventory model by Law and Kelton.

The experiment design showed that the least cost-intensive order strategy for the store consists of the order type Normal and the inventory-evaluation interval of 1 month. We want to investigate the inventory costs for all values ranging from 0 to 70 with a step size of 5 for the values safety stock and the difference . We do not use the experiment table in this example.

Now we have to create rules which set these pairs of values ( safety stock and difference ):

(0,0), (0,5), (0,10), … , (0,70), (5,0), (5,5), (5,10), … , (5,70), (10,0), (10,5), (10,10), … , (70,70)

This results in 152, i.e., 225 experiments. In the first experiment an initialization rule sets both values to 0. In a second rule we check if the value difference is less than or equal to 70. If this condition is met, the value difference is increased by 5. A third rule checks if the value 70 for the difference is exceeded. When this is the case the corresponding action resets the value difference to 0 and increases the value safety stock by 5.

The second and the third rule only work when the second rule is evaluated first. For this reason you have to assign a greater priority to the second rule than to the third rule.

Then, we set the Number of experiments to 225 on the tab Rules . Finally, we start the experiment run by clicking Start .

Figure 11-34: Showing the results in a user-defined chart

<!-- image -->

To open this model and to run experiments with it, click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection and click Open Model .

If you want to show the results in a Chart as a 3D Surface , you have to use the evaluation method in the example model.

Our analysis has shown that monthly costs could be reduced to €115.57. The values belonging to the minimum are a safety stock of 15 and a difference of 30.

See also

Use a Two-level Experimental Design and Use Factorial Analysis

#### Recording the Results of a Simulation Study

On the tab Report you can type in a description of the project and designate folders into which you want to save the report and the simulation models.

For documenting and archiving the reports you can type in important information about the project on the tab Report. The report shows this information along the top of the page. After an experiment run the ExperimentManager opens the report showing all results. When you select the check box Save report, the ExperimentManager saves this report to the Folder whose name you type in. Compare Show the Results in a Report .

If you would like the ExperimentManager to save the model files after each experiment, we advise against including charts in the report as the user-defined graphics greatly increase the size of the model file.

Figure 11-35: Project data and folder for results

<!-- image -->

To start several simulation studies one after the other with a BATCH file, compare Specifying Start Options , you have to prevent Plant Simulation from opening any modal dialogs which require user actions. To prevent Plant Simulation from showing message boxes, select the respective check box. In addition, you might not want to open reports after such a simulation run.

| Check box        | Attribute                                                             | Description   |
|------------------|-----------------------------------------------------------------------|---------------|
| showRuntimeAtEnd | Shows how much time the study required.                               | Show run time |
| showHTMLatEnd    | Opens the report after the study is finished.                         | Show report   |
| saveHTMLatEnd    | Saves the report to a folder after the study is finished.             | Save report   |
| saveExcelAtEnd   | Saves the table Results as an Excel file after the study is finished. | Save results  |

If you do not want to show the message asking to save the model before executing distributed simulations, you have to set the user-defined attribute AskForSaveModel to false .

Within tables the ExperimentManager adjusts the column width to the length of the expression you type in as the column index. This way, Plant Simulation always shows the entire column index. When displaying output tables with many columns it might be helpful to set a constant column width. To do so, change the value of the user-defined attribute columnWidth\_standard from the default value 0 to the column width of your choice. To change the values of these attributes, click the ExperimentManager in the Frame into which you inserted it and press the F8 key.

If you would like the ExperimentManager to inform you when a time-consuming simulation study is finished, select the check box Send e-mail . Then type in your e-mail address and the name of your e-mail server.

##### Attributes of the ExperimentManager

#### Attributes of the ExperimentManager

The ExperimentManager provides:

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
ExperimentManager.UserConfigMethod := "UserConfig"
print ExperimentManager.UserConfigMethod
posit := MyStation.Cont.XPos
```

##### UserConfigMethod [SimTalk]

Sets the name of the Method in which you can set the input values of the ExperimentManager designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.UserConfigMethod:string

Assignment Value

You can assign a value of data type string .

Example

MyDismantleStation.UserConfigMethod := "UserConfigMethod"

See also

Using a Configuration Method

##### UserEvalMethod [SimTalk]

Sets the name of the Method in which you can run the final evaluations of the experiment study of the ExperimentManager designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.UserEvalMethod:string

Assignment Value

You can assign a value of data type string .

Example

MyDismantleStation.UserEvalMethod := "UserEvaluation"

See also

Using an Evaluation Method

##### UserSeedValueMethod [SimTalk]

Sets the name of the Method in which you can set the random seed values of the ExperimentManager designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.UserSeedValueMethod:string

Assignment Value

You can assign a value of data type string .

Example

MyDismantleStation.UserSeedValueMethod := "UserSeedValueMethod"

See also

Using a Configuration Method

#### Configuring DCOM for Remote Access

Configuring DCOM for Remote Access

For successfully running distributed simulations, you have to configure DCOM for remote access.

We recommend the following DCOM configuration settings as a starting point if you are unfamiliar with COM and/or DCOM. Once you are more comfortable with DCOM configuration, you can modify your settings based on your own set of requirements.

**Note**

You can only configure DCOM when you have Administrator privileges.

**Note**

When no identical user account exists on both computers, no authentication can take place. To deactivate authentication, you can create the following registry key of type DWORD and assign it the value 1 : HKEY\_CURRENT\_USER/Software/Siemens/Tecnomatix Plant Simulation XX/Settings/ RPC\_C\_AUTHN\_LEVEL\_NONE . This might pose a security vulnerability.

Go to Configuring DCOM on the Remote Computer

##### Configure DCOM on the Remote Computer

**First, select general DCOM settings:**

1. On the remote computer, type Component Services into the Search field.
2. Expand Component Services , expand Computers , and right-click My Computer . Select Properties .
3. Click the tab Default Properties . Select Enable Distributed COM on this computer. Set the Default Authentication Level to Connect ( None also works). Set the Default Impersonation Level to Identify ( Impersonate also works).
4. Click the tab COM Security .
5. Under Access Permissions click Edit Default . Add SYSTEM , INTERACTIVE , and NETWORK . You also have to include the user whose authentication credentials will be used to access the COM application

<!-- image -->

to this list. You can, for example, add the specific user or add a group the user belongs to. You might type in:

- Domain\Username (A specific user)
- Domain\Administrators (All administrators on a specific domain)
- Everyone (All users)
6. Under Launch Permissions click Edit Default . Make sure that the Launch Permissions have the same values as the Access Permissions .
7. Click the tab Default Protocols . Make sure Connection-oriented TCP/IP is listed first. Click OK .

**Then, configure the COM application you would like to access:**

1. Expand Component Services , expand Computers , expand My Computer , and click DCOM Config . Right-click the application you would like to configure and select Properties . To configure Plant Simulation , select Tecnomatix Plant Simulation &lt;your version&gt; .
2. Click the tab General . Set the Authentication Level to Default .
3. Click the tab Location . Select Run application on this computer .
4. Click the tab Security . Set Launch Permissions to Customize . Set Access Permissions to Customize . Set Configuration Permissions to Customize .

<!-- image -->

<!-- image -->

5. Click Edit and add yourself to the list of users.

<!-- image -->

6. Click the tab Identity . Select The launching user .

**Note**

On some systems you have to designate a specific user under This user .

<!-- image -->

7. Click the tab Endpoints . Select default system protocols .

<!-- image -->

**8. Click OK .**

**Note**

When no identical user account exists on both computers, no authentication can take place. To deactivate authentication, you can create the following registry key of type DWORD and assign it the value 1 : HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation XX/ Settings\RPC\_C\_AUTHN\_LEVEL\_NONE . Be aware that this might pose a security vulnerability.

#### GAWizard

