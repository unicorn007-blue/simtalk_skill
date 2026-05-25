### BottleneckAnalyzer

#### BottleneckAnalyzer [object]

Use the BottleneckAnalyzer for analyzing and displaying the flow of parts through a plant and thus identify bottlenecks.

Icon

<!-- image -->

Description

The BottleneckAnalyzer visualizes the standard statistics of the material flow objects and sorts the data into a table. It displays the statistics of the material flow objects that are located in the same Frame as the BottleneckAnalyzer or in Sub-frames of that Frame .

<!-- image -->

To add the BottleneckAnalyzer to the Class Library , click Manage Class Library &gt; Libraries &gt; Tools &gt;

Bottleneck Analyzer on the Home ribbon tab.

<!-- image -->

The BottleneckAnalyzer works statically, i.e., it does not collect data during the simulation run. For this reason you can insert it even after the simulation run is finished.

If, for example, you would like to increase the throughput of a production, you will start looking for the bottleneck at the Drains . The machines causing the bottleneck will have a high working portion. When the machines causing the bottleneck work faster, the throughput of the entire system will increase.

For a Frame the BottleneckAnalyzer shows the chart of the machine, which has the greatest working portion. To continue looking for the bottleneck in a Frame , check the chart of the objects, which you inserted into the Frame .

When you click OK , the BottleneckAnalyzer opens a table, which shows all material flow objects with the statistical values, which you selected.

**Note**

We modeled the BottleneckAnalyzer as an application object in a Frame . For this reason opening help with F1 and What's This Help in the dialogs of the objects do not work.

We modeled the dialogs of the objects with the object Dialog . The windows of the objects do not use the standard Siemens PLM theme, but your Windows theme.

To open help for the object, select Help &gt; Help on Object in its dialog.

To assign a different name or a label to the object, click it with the right mouse button and select Rename .

You can Analyze the model, Remove the statistics charts, and Open the ranking table.

You can also configure the BottleneckAnalyzer . You can select the type of Resources and select Display options.

<!-- image -->

<!-- image -->

#### Configure the BottleneckAnalyzer Through Other Objects

If an object has the user-defined attribute \_BNanalysed , of data type boolean , and if you set this attribute to false , this object will not be part of the BottleneckAnalyzer's analysis. You can create this attribute for an object by dragging the object over the BottleneckAnalyzer and by dropping it there.

#### Tab Analyze

Tab Analyze

The tab Analyze provides these settings:

Analyze

Remove

Open

**Analyze**

##### Analyze

To visualize statistics, click the Analyze button.

For a Frame , the BottleneckAnalyzer show the statistics of the critical resource, which is the material flow object processing the highest number of parts.

**Note**

The BottleneckAnalyzer only shows the statistics of a material flow object when the statistics is activated and for the type of resource you selected in the dialog Configure .

<!-- image -->

| This color   | Designates this state   |
|--------------|-------------------------|
| Green        | Working                 |
| Brown        | Setting-Up              |
| Gray         | Waiting                 |
| Yellow       | Blocked                 |
| Red          | Failed                  |
| Blue         | Paused or Unplanned     |

##### Remove

To delete the displayed values, click the Remove button.

**Open [BottleneckAnalyzer]**

##### Open [BottleneckAnalyzer]

To select the sorting criteria of the statistical values, which the BottleneckAnalyzer show and which it then writes to a data table, click the Open button.

When you click OK , the BottleneckAnalyzer opens a data table that lists all material flow objects, showing the statistical values for the states you selected.

#### Tab Configure

Tab Configure

The tab Configure provides these settings:

Resources

Display

##### Resources [BottleneckAnalyzer]

Select if the BottleneckAnalyzer displays statistical data for a resource of type Production , Transport and Storage on the tab Configure .

**Display [BottleneckAnalyzer]**

##### Display [BottleneckAnalyzer]

Select how the BottleneckAnalyzer displays the statistics values from the drop-down list.

As Only Bars , as Plus Scale , or Plus Background .

#### Navigate Menu

Opens the Frame window in which the selected object is located.

#### Help Menu

The Help Menu provides commands to access its functions.

Contents

The menu command Contents opens the table of contents of the Plant Simulation help.

Help on BottleneckAnalyzer

The menu command Help on BottleneckAnalyzer opens the help topic pertaining to the BottleneckAnalyzer .

