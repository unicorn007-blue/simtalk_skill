### Sequential Sampler

Use the SequentialSampler for starting a simulation study, which consists of a single, non-terminating simulation run. The SequentialSampler analyzes a single target value.

Icon

<!-- image -->

To add the SequentialSampler to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt; Sequential Sampler on the Home ribbon tab. Plant Simulation adds the Sequential Sampler to the tab Tools in the Toolbox .

<!-- image -->

<!-- image -->

**Description**

Insert the SequentialSampler into the root frame of the simulation model. It does not change any model parameters. The SequentialSampler and the ExperimentManager determine an interval to a given confidence level containing the mean value of the target value with a given confidence probability. While the ExperimentManager determines the width of the interval to a given number of observations, the SequentialSampler determines the required number of observations to the given width of the interval. The SequentialSampler thus enables determining the target size to a given precision. The number of required observation is shown in the dialog during the simulation study.

The SequentialSampler determines a confidence interval of a target value, so that the width of the confidence interval is smaller than a given size.

The observations, which are required for computing the confidence interval, are determined sequentially either by several simulation runs or by a single simulation run. The SequentialSampler terminates creating the observations when the confidence interval has the desired width. If your model has a long warm-up period, you can determine the number of observations by a single simulation run. After the warm-up period the SequentialSampler determines the target value in time intervals of fixed duration, so-called batches. You can set the warm-up period with the attribute StartStat of the EventController . At the start of such a time interval statistics of the target value is reset. This typically happens with the method initStat . The so-called batch method gives an estimate for the required number of observations. More timeconsuming is determining the number with several simulation runs as the ExperimentManager enables you to do. The ExperimentManager returns easily reproducible values for each individual observation.

The Reset button deletes the results of the previous study. The Start button starts the study sequentially creating observations of the target value. The Stop button interrupts creating observations. A message window shows when the desired width of the confidence interval has been reached. The SequentialSampler terminates creating observations as soon as the desired width of the confidence interval has been reached for the first time. Experience has shows that the desired width of the confidence intervals has only been ensured reliably after five additional observations.

You can open the observed values, a histogram of these observations and statistical values of interest with the menu commands of the Tools menu.

At the end of the study or with Tools &gt; Restore Model Settings the original model settings are restored which the SequentialSampler changed for more quickly creating the observations (animation and settings of the EventController ).

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

#### Tab Definition

The tab Definition provides these settings:

<!-- image -->

<!-- image -->

Type in the target value, i.e., the name of a material flow object and the name of a method. The data type of the target value of the simulation study has to be convertible into the type real (such as length , but not string or boolean ). The data type time is displayed in the time format.

There is only one target value, which the object evaluates several times during a single simulation run.

You can also define the target value by dragging an object onto the wizard and dropping it there and by then selecting one of the statistics methods of the dropped object.

<!-- image -->

Type in the confidence level. The unknown expected value of the random number of the target value is contained in the confidence interval with the probability of the confidence level. We want to determine the confidence interval for a given precision and confidence level, using as few observations as possible during a simulation run. Type in a value greater than 50 and less than 100 .

<!-- image -->

Type in the half-width of the confidence level. The half-width of the confidence interval is measured like the Target value .

<!-- image -->

Type in the minimum number of observations. Plant Simulation simulates this number of batches at least. This number must be greater than 1.

<!-- image -->

Type in the maximum number of observations. Plant Simulation terminates the simulation is after this number of batches. Type in -1 to only terminate the simulation when the desired width is reached.

Batch method

<!-- image -->

Activate the check box Batch method to show the next two settings:

<!-- image -->

When you select this check box, the user-defined method prepareBatch resets the statistics of the target value and prepares the model for the next batch. Click Edit and type in your source code. You will typically type in an instruction such as Drain.initStat .

<!-- image -->

Type in the batch duration. The target value is measured at the end of this time span. It is an observation for the calculation of the confidence interval.

The simulation model should be in a stable state after the warm-up phase. Type this time value into the EventController . It is the start point in time for the interval for setting the first observation of the target value.

#### Tab Evaluation

On the tab Evaluation the SequentialSampler shows the computed statistics values mean value, standard deviation, half-width of the confidence interval, and minimum and maximum of all observations for the sample at hand.

The tab Evaluation provides these settings:

<!-- image -->

These values are also contained in the table Results that the command Show Results/Close Results opens and closes.

The command Show Histogram visualizes the distribution of the observations of the sample.

The table Observations contains the different observations of the sample. You can also show this table with the command Show Observations .

**Note**

You can set the decimal precision of the results with the attribute ResultsPrecision . You can set the precision of the results to be displayed according to the application. The default value -1 shows the resulting values with 15 decimal places at the most.

#### Statistics Tools

