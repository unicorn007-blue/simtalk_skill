### Drain

#### Drain [object]

Use the Drain for removing the parts from the plant after they have been processed. It usually represents the shipping department of your plant.

Icon

<!-- image -->

**Description**

Use the Drain to model the shipping department of your plant. The built-in properties of the Drain are the same as those of the Station . Like it, it has a single processing place. The only difference is that the Drain removes the processed part from the plant instead of moving it on to a succeeding object in the flow of materials.

The Drain basically is the counterpart of the Source .

You can also show the statistics table of a Drain in an HtmlReport , compare Display a Drain .

To show a tooltip with information about the Drain , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Drain , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Drain to your simulation model, click MaterialFlow &gt; Drain on the Home ribbon tab.

Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Remove Parts from the Installation with the Drain

Check How Many Parts Left the Plant

#### Dialog Box of the Drain

Dialog Box of the Drain

Double-click the icon of the Drain to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

##### Dialog Box of the Drain

- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Define Processing Times

Select the Set-Up Time

Processing Time [general description]

Set-up Time [general description]

Recovery Time [general description]

Cycle Time [general description]

**Tab Set-Up**

##### Tab Set-Up

Define properties for setting the object up as described under the Tab Set-Up .

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , a Set-up Control , and a Pull Control .

**Note**

The Drain does not have an Exit Control . It deletes the MUs from the simulation model at the end of its processing time.

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

In addition, you can select the Shift Calendar .

See also Select Object [for controls] Entrance Control [general description] Set-up Control

Pull Control [general description]

**Tab Statistics [Drain]**

##### Tab Statistics [Drain]

Statistics is described under the tab Statistics . In addition to the statistical data described under the Statistics Report , the Drain collects and shows the statistical data of the mobile objects .

You can also select to collect statistics for MUs with the same name that pass through your simulation model, compare the tab Type Statistics .

Each time the Drain removes a part from the plant, it computes the proportional average value of each statistical value displayed. For this it divides the average value by the average lifetime times 100.

To view Cumulated Statistics of the Parts which the Drain Removed From the Plant in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

<!-- image -->

**See also**

Tab Statistics [material flow objects]

Tab Type Statistics

Statistics Report [described]

Product Statistics of the MUs [general description]

Resource Statistics [check box]

Resource Type Tab Type Statistics Tab Type Statistics The tab Type Statistics provides the check box Type Dependent Statistics . Activate it to collect statistics for MUs with the same name that pass through your simulation model.

Click Detailed Statistics Table to open the table that itemizes the MUs , which the Drain removed from the plant, according to their types.

The tab itself shows this statistical data:

| Item       | Description                                                                                                                                                                                                                                             | Read-only Attribute                                                                                                               | Item German   |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------|
| Working    | Shows the percentage of the sum of the times during which the MUs were located on a working object, in relation to the statistics collection periods of all MUs . In general, the statistics collection period is the life time of the MUs .            | StatProdWorkingPortion [SimTalk] - Drain + StatStoreWorkingPortion [SimTalk] - Drain + StatTranspWorkingPortion [SimTalk] - Drain | Arbeitend     |
| Setting-up | Shows the percentage of the times during which the objects were setting-Up for the MUs , in relation to the statistics collection periods of all MUs .                                                                                                  | StatProdSetupPortion [SimTalk] - Drain + StatStoreSetUpPortion [SimTalk] - Drain + StatTranspSetupPortion [SimTalk] - Drain       | Rüstend       |
| Waiting    | Shows the percentage of the times during which the objects were waiting for the MUs , in relation to the statistics collection periods of all MUs . In general, the statistics collection period is the life time of the MUs .                          | StatProdWaitingPortion [SimTalk] - Drain + StatStoreWaitingPortion [SimTalk] - Drain + StatTranspWaitingPortion [SimTalk] - Drain | Wartend       |
| Stopped    | Shows the percentage of the sum of the times during which the MUs were located on an object that was stopped , in relation to the statistics collection periods of all MUs . In general, the statistics collection period is the life time of the MUs . | StatProdStoppedPortion [SimTalk] - Drain + StatStoreStoppedPortion [SimTalk] - Drain + StatTranspStoppedPortion [SimTalk] - Drain | Angehalte n   |
| Failed     | Shows the percentage of the sum of the times during which the MUs were located on an object that was failed , in relation to the statistics collection periods of all MUs . In general, the statistics collection period is the life time of the MUs .  | StatProdFailPortion [SimTalk] - Drain + StatStoreFailPortion [SimTalk] - Drain + StatTranspFailPortion [SimTalk] - Drain          | Gestört       |

| Item                  | Description                                                                                                                                                                                                                                                                    | Read-only Attribute                                                                                                               | Item German                 |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| Paused                | Shows the percentage of the sum of the times during which the MUs were located on a paused or unplanned object, in relation to the statistics collection periods of all MUs . In general, the statistics collection period is the life time of the MUs .                       | StatProdPausingPortion [SimTalk] - Drain + StatStorePausingPortion [SimTalk] - Drain + StatTranspPausingPortion [SimTalk] - Drain | Pausiert                    |
| Average lifespan      | Shows the average life-span of MUs , which were created and removed from the plant during the statistics collection period. Only those MUs are counted for which you activated product statistics.                                                                             | StatAvgLifeSpan [SimTalk] - MUs                                                                                                   | Mittlere Lebenszei t        |
| Average exit interval | Shows the average time interval between exits of the MUs that the Drain removed from the plant. It results from adding up the times of all intervals, and then dividing them by the number of intervals. Statistics only starts counting from the time the first part arrived! | StatAvgExitInterval [SimTalk]                                                                                                     | Mittlerer Austrittsa bstand |
| Total throughput      | Shows the number of MUs that the Drain removed from the plant, starting at the time, at which you activated Type dependent statistics .                                                                                                                                        | StatDeleted [SimTalk] - Drain                                                                                                     | Gesamtdu rchsatz            |
| Throughput per minute | Shows the number of MUs that the Drain removed from the plant in a minute over all observed times during which the Drain was available.                                                                                                                                        | StatThroughputPerMinute [SimTalk]                                                                                                 | Durchsatz pro Minute        |
| Throughput per hour   | Shows the number of MUs that the Drain removed from the plant in an hour over all observed times during which the Drain was available.                                                                                                                                         | StatThroughputPerHour [SimTalk] - Drain                                                                                           | Durchsatz pro Stunde        |
| Throughput per day    | Shows the number of MUs that the Drain removed from the plant in a day over all observed times during which the Drain was available. This is the value of the throughput per hour multiplied with 24.                                                                          | StatThroughputPerHour [SimTalk] - Drain                                                                                           | Durchsatz pro Tag           |

**Note**

The sum of the percentages for the states working , setting-up , failed , stopped , and paused of the MUs adds up to 100 percent.

To view the Part Types Which the Drain Removed From the Plant in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

<!-- image -->

**See also**

Check How Many Parts Left the Plant

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=sryvv1gjwWw1LOUF&amp;t=57](https://youtu.be/BvHLQCIjGIA?si=sryvv1gjwWw1LOUF&t=57)

###### Type Dependent Statistics

Type Dependent Statistics

To activate statistics collection depending on the type of the MU , which the Drain removed from the plant, select this check box.

SimTalk

TypeStatOn [SimTalk]

See also

StatThroughputPerDay [SimTalk] - Drain

StatThroughputPerHour [SimTalk] - Drain

StatAvgExitInterval [SimTalk]

typeStatisticsCumulated [SimTalk]

###### Detailed Statistics Table [Drain]

To open the Detailed Statistics Table , click this button.

<!-- image -->

The Detailed Statistics Table itemizes the MUs , which the Drain removed from the plant, according to their types. It contains this statistical data:

| Item             | Description                                                                                                                                                                                           | Read-only Attribute                                                            |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| Type             | Shows the name of the MU .                                                                                                                                                                            | -                                                                              |
| Time             | Shows the last arrival of part of this type.                                                                                                                                                          | -                                                                              |
| Total throughput | Shows the number of parts of this type.                                                                                                                                                               | StatThroughputPerDay [SimTalk] - Drain StatThroughputPerHour [SimTalk] - Drain |
| %Parts           | Shows the percentage of parts of this type.                                                                                                                                                           | -                                                                              |
| LT_Mean          | Shows the mean life time (throughput time) of all investigated parts.                                                                                                                                 | -                                                                              |
| LT_StdDev        | Shows the standard deviation of the life times of all investigated parts.                                                                                                                             | -                                                                              |
| LT_Min           | Shows the minimum life time of the investigated parts.                                                                                                                                                | -                                                                              |
| LT_Max           | Shows the maximum life time of the investigated parts.                                                                                                                                                | -                                                                              |
| TPh_Mean         | Shows the number of MUs that the Drain removed from the plant in an hour over all observed times during which the Drain was available.                                                                | -                                                                              |
| TPh_StdDev       | Shows the standard deviation of the throughput per hour.                                                                                                                                              | -                                                                              |
| TPh_Min          | Shows the minimum throughput per hour.                                                                                                                                                                | -                                                                              |
| TPh_Max          | Shows the maximum throughput per hour.                                                                                                                                                                | -                                                                              |
| TPd_Mean         | Shows the number of MUs that the Drain removed from the plant in a day over all observed times during which the Drain was available. This is the value of the throughput per hour multiplied with 24. | -                                                                              |

| Item       | Description                                                                     | Read-only Attribute   |
|------------|---------------------------------------------------------------------------------|-----------------------|
| TPd_StdDev | Shows the standard deviation from the throughput per day.                       | -                     |
| TPd_Min    | Shows the minimum throughput per day.                                           | -                     |
| TPd_Max    | Shows the maximum throughput per day.                                           | -                     |
| CT_Mean    | Shows the mean cycle time of two parts that arrive back-to-back.                | -                     |
| CT_StdDev  | Shows the standard deviation of the cycle time difference.                      | -                     |
| CT_Min     | Shows the minimum cycle time difference of two parts that arrive back-to-back.  | -                     |
| CTS_Max    | Shows the maximum cycle time difference of two parts that arrive back-to-back.  | -                     |
| IP_Mean    | Shows the mean processing time of the investigated parts.                       | -                     |
| IP_StdDev  | Shows the standard deviation of the processing times of the investigated parts. | -                     |
| IP_Min     | Shows the minimum processing times of the investigated parts.                   | -                     |
| IP_Max     | Shows the maximum processing times of the investigated parts.                   | -                     |
| S_Mean     | Shows the mean set-up time of the investigated parts.                           | -                     |
| S_StdDev   | Shows the standard deviation of the set-up times of the investigated parts.     | -                     |
| S_Min      | Shows the minimum set-up times of the investigated parts.                       | -                     |
| S_Max      | Shows the maximum set-up times of the investigated parts.                       | -                     |
| W_Mean     | Shows the mean waiting time of the investigated parts (compare Waiting [MUs] ). | -                     |
| W_StdDev   | Shows the standard deviation of the waiting times of the investigated parts.    | -                     |
| W_Min      | Shows the minimum waiting time of the investigated parts.                       | -                     |

| Item        | Description                                                                                                      | Read-only Attribute                      |
|-------------|------------------------------------------------------------------------------------------------------------------|------------------------------------------|
| W_Max       | Shows the maximum waiting time of the investigated parts.                                                        | -                                        |
| Stp_Mean    | the mean time that the investigated parts were located on a stopped resource.                                    | StatProdStoppedPortion [SimTalk] - Drain |
| Stp_StdDev  | Shows the standard deviation of the times that the investigated parts were located on a stopped resource.        | -                                        |
| Stp_Min     | Shows the minimum time that a part was located on a stopped resource.                                            | -                                        |
| Stp_Max     | Shows the maximum time that a part was located on a stopped resource.                                            | -                                        |
| F_Mean      | Shows the mean time that the investigated parts were located on a failed resource.                               | -                                        |
| F_StdDev    | Shows the standard deviation of the times that the investigated parts were located on a failed resource.         | -                                        |
| F_Min       | Shows the minimum time that a part was located on a failed resource.                                             | -                                        |
| F_Max       | Shows the maximum time that a part was located on a failed resource.                                             | -                                        |
| P_Mean      | Shows the mean time that the investigated parts were located on a paused resource.                               | -                                        |
| P_StdDev    | Shows the standard deviation of the times that the investigated parts were located on a paused resource.         | -                                        |
| P_Min       | Shows the minimum time that a part was located on a paused resource.                                             | -                                        |
| P_Max       | Shows the maximum time that a part was located on a paused resource.                                             | -                                        |
| IP_P_Mean   | Shows the mean processing times of the investigated parts on a resource of type Production.                      | StatProdWorkingPortion [SimTalk] - Drain |
| IP_P_StdDev | Shows the standard deviation of the processing times of the investigated parts on a resource of type Production. | -                                        |
| IP_P_Min    | Shows the minimum processing time of the investigated parts on a resource of type Production.                    | -                                        |
| IP_P_Max    | Shows the maximum processing time of the investigated parts on a resource of type Production.                    | -                                        |

| Item         | Description                                                                                                                  | Read-only Attribute                      |
|--------------|------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|
| S_P_Mean     | Shows the mean set-up times of the investigated parts on a resource of type Production.                                      | StatProdSetupPortion [SimTalk] - Drain   |
| S_P_StdDev   | Shows the standard deviation of the set-up times of the investigated parts on a resource of type Production.                 | -                                        |
| S_P_Min      | the minimum set-up time of the investigated parts on a resource of type Production.                                          | -                                        |
| S_P_Max      | Shows the maximum set-up time of the investigated parts on a resource of type Production.                                    | -                                        |
| W_P_Mean     | Shows the mean waiting times of the investigated parts on a resource of type Production.                                     | StatProdWaitingPortion [SimTalk] - Drain |
| W_P_StdDev   | Shows the standard deviation of the waiting times of the investigated parts on a resource of type Production.                | -                                        |
| W_P_Min      | Shows the minimum waiting time of the investigated parts on a resource of type Production.                                   | -                                        |
| W_P_Max      | Shows the maximum waiting time of the investigated parts on a resource of type Production.                                   | -                                        |
| Stp_P_Mean   | Shows the mean times of the investigated parts on a stopped resource of type Production.                                     | StatProdStoppedPortion [SimTalk] - Drain |
| Stp_P_StdDev | Shows the standard deviation of the times that the investigated parts were located on a stopped resource of type Production. | -                                        |
| Stp_P_Min    | Shows the minimum time of the investigated parts on a stopped resource of type Production.                                   | -                                        |
| Stp_P_Max    | Shows the maximum time of the investigated parts on a stopped resource of type Production.                                   | -                                        |
| F_P_Mean     | Shows the mean times of the investigated parts on a failed resource of type Production.                                      | StatProdFailPortion [SimTalk] - Drain    |
| F_P_StdDev   | Shows the standard deviation of the times that the investigated parts were located on a failed resource of type Production.  | -                                        |
| F_P_Min      | Shows the minimum time of the investigated parts on a failed resource of type Production.                                    | -                                        |
| F_P_Max      | Shows the maximum time of the investigated parts on a failed resource of type Production.                                    | -                                        |

| Item        | Description                                                                                                                 | Read-only Attribute                        |
|-------------|-----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| P_P_Mean    | Shows the mean times of the investigated parts on a paused resource of type Production.                                     | StatProdPausingPortion [SimTalk] - Drain   |
| P_P_StdDev  | Shows the standard deviation of the times that the investigated parts were located on a paused resource of type Production. | -                                          |
| P_P_Min     | Shows the minimum time of the investigated parts on a paused resource of type Production.                                   | -                                          |
| P_P_Max     | Shows the maximum time of the investigated parts on a paused resource of type Production.                                   | -                                          |
| IP_T_Mean   | Shows the mean processing times of the investigated parts on a resource of type Transport.                                  | StatTranspWorkingPortion [SimTalk] - Drain |
| IP_T_StdDev | Shows the standard deviation of the processing times of the investigated parts on a resource of type Transport.             | -                                          |
| IP_T_Min    | Shows the minimum processing time of the investigated parts on a resource of type Transport.                                | -                                          |
| IP_T_Max    | Shows the maximum processing time of the investigated parts on a resource of type Transport.                                | -                                          |
| S_T_Mean    | Shows the mean set-up times of the investigated parts on a resource of type Transport.                                      | StatTranspSetupPortion [SimTalk] - Drain   |
| S_T_StdDev  | Shows the standard deviation of the set-up times that the investigated parts were located on a resource of type Transport.  | -                                          |
| S_T_Min     | Shows the minimum set-up time of the investigated parts on a resource of type Transport.                                    | -                                          |
| S_T_Max     | Shows the maximum set-up time of the investigated parts on a resource of type Transport.                                    | -                                          |
| W_T_Mean    | the mean waiting times of the investigated parts on a resource of type Transport.                                           | StatTranspWaitingPortion [SimTalk] - Drain |
| W_T_StdDev  | Shows the standard deviation of the waiting times that the investigated parts were located on a resource of type Transport. | -                                          |
| W_T_Min     | Shows the minimum waiting time of the investigated parts on a resource of type Transport.                                   | -                                          |
| W_T_Max     | Shows the maximum waiting time of the investigated parts on a resource of type Transport.                                   | -                                          |

| Item         | Description                                                                                                                  | Read-only Attribute                        |
|--------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| Stp_T_Mean   | Shows the mean times of the investigated parts on a stopped resource of type Transport.                                      | StatTranspStoppedPortion [SimTalk] - Drain |
| Stp_T_StdDev | Shows the standard deviation of the times that the investigated parts were located on a stopped resource of type Transport.  | -                                          |
| StpF_T_Min   | Shows the minimum time of the investigated parts on a stopped resource of type Transport.                                    | -                                          |
| Stp_T_Max    | Shows the maximum time of the investigated parts on a stopped resource of type Transport.                                    | -                                          |
| F_T_Mean     | Shows the mean times of the investigated parts on a failed resource of type Transport.                                       | StatTranspFailPortion [SimTalk] - Drain    |
| F_T_StdDev   | Shows the standard deviation of the times that the investigated parts were located on a failed resource of type Transport.   | -                                          |
| F_T_Min      | Shows the minimum time of the investigated parts on a failed resource of type Transport.                                     | -                                          |
| F_T_Max      | Shows the maximum time of the investigated parts on a failed resource of type Transport.                                     | -                                          |
| P_T_Mean     | Shows the mean times of the investigated parts on a paused resource of type Transport.                                       | StatTranspPausingPortion [SimTalk] - Drain |
| P_T_StdDev   | Shows the standard deviation of the times that the investigated parts were located on a paused resource of type Transport.   | -                                          |
| P_T_Min      | Shows the minimum time of the investigated parts on a paused resource of type Transport.                                     | -                                          |
| P_T_Max      | Shows the maximum time of the investigated parts on a paused resource of type Transport.                                     | -                                          |
| IP_S_Mean    | Shows the mean processing times of the investigated parts on a resource of type Storage.                                     | StatStoreWorkingPortion [SimTalk] - Drain  |
| IP_S_StdDev  | Shows the standard deviation of the processing times that the investigated parts were located on a resource of type Storage. | -                                          |
| IP_S_Min     | Shows the minimum processing time of the investigated parts on a resource of type Storage.                                   | -                                          |
| IP_S_Max     | Shows the maximum processing time of the investigated parts on a resource of type Storage.                                   | -                                          |

| Item         | Description                                                                                                               | Read-only Attribute                       |
|--------------|---------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| S_S_Mean     | Shows the mean set-up times of the investigated parts on a resource of type Storage.                                      | StatStoreSetUpPortion [SimTalk] - Drain   |
| S_S_StdDev   | Shows the standard deviation of the set-up times that the investigated parts were located on a resource of type Storage.  | -                                         |
| S_S_Min      | Shows the minimum set-up time of the investigated parts on a resource of type Storage.                                    | -                                         |
| S_S_Max      | Shows the maximum set-up time of the investigated parts on a resource of type Storage.                                    | -                                         |
| W_S_Mean     | Shows the mean waiting times of the investigated parts on a resource of type Storage.                                     | StatStoreWaitingPortion [SimTalk] - Drain |
| W_S_StdDev   | Shows the standard deviation of the waiting times that the investigated parts were located on a resource of type Storage. | -                                         |
| W_S_Min      | Shows the minimum waiting time of the investigated parts on a resource of type Storage.                                   | -                                         |
| W_S_Max      | Shows the maximum waiting time of the investigated parts on a resource of type Storage.                                   | -                                         |
| Stp_S_Mean   | Shows the mean times of the investigated parts on a stopped resource of type Storage.                                     | StatStoreStoppedPortion [SimTalk] - Drain |
| Stp_S_StdDev | the standard deviation of the times that the investigated parts were located on a stopped resource of type Storage.       | -                                         |
| Stp_S_Min    | Shows the minimum time of the investigated parts on a stopped resource of type Storage.                                   | -                                         |
| Stp_S_Max    | Shows the maximum time of the investigated parts on a stopped resource of type Storage.                                   | -                                         |
| F_S_Mean     | Shows the mean times of the investigated parts on a failed resource of type Storage.                                      | StatStoreFailPortion [SimTalk] - Drain    |
| F_S_StdDev   | Shows the standard deviation of the times that the investigated parts were located on a failed resource of type Storage.  | -                                         |
| F_S_Min      | Shows the minimum time of the investigated parts on a failed resource of type Storage.                                    | -                                         |
| F_S_Max      | Shows the maximum time of the investigated parts on a failed resource of type Storage.                                    | -                                         |

| Item       | Description                                                                                                              | Read-only Attribute                       |
|------------|--------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|
| P_S_Mean   | Shows the mean times of the investigated parts on a paused resource of type Storage.                                     | StatStorePausingPortion [SimTalk] - Drain |
| P_S_StdDev | Shows the standard deviation of the times that the investigated parts were located on a paused resource of type Storage. | -                                         |
| P_S_Min    | Shows the minimum time of the investigated parts on a paused resource of type Storage.                                   | -                                         |
| P_S_Max    | Shows the maximum time of the investigated parts on a paused resource of type Storage.                                   | -                                         |

**SimTalk**

typeStatistics [SimTalk] - Drain

typeStatisticsCumulated [SimTalk]

Video on YouTube

[https://youtu.be/BvHLQCIjGIA?si=RrcV9zshpXbrOs0I&amp;t=508](https://youtu.be/BvHLQCIjGIA?si=RrcV9zshpXbrOs0I&t=508)

##### Tab Importer [Drain]

Define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station on the tab Importer . This also enables the Worker to carry parts to the Drain .

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

See also

Tab Importer [general description]

Processing Importer

Set-up Importer

Failure Importer

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The View Menu provides commands to access its functions.

| Refresh                     | Services                  |
|-----------------------------|---------------------------|
| Show Statistics Report      | Unavailable Services      |
| Show Attributes and Methods | Associated Workplaces     |
| Contents                    | Exiting MUs               |
| Forward Blocking List       | Associated Lockout Zones  |
| Exporters                   | Associated Shift Calendar |

##### Tools Menu

The commands are described under the Tools Menu .

**Tabs Menu**

##### Tabs Menu

Use the commands of the Tabs menu to show or hide individual tabs of the material flow objects. If you hide tabs that you do not need, Plant Simulation opens the dialog faster, and you can change to those tabs faster that you need in your daily work.

To apply the changed settings, click OK , close the dialog, and reopen it

The menu shows a check mark to the left of the displayed tabs.

The command Inherit turns inheritance of the displayed or hidden tabs in the dialog off or on.

<!-- image -->

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Drain

#### Methods of the Drain

The Drain provides:

- The methods listed in the table of contents to the left.
- The Methods of the Station .
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

##### typeStatistics [SimTalk] - Drain

Returns the Detailed Statistics Table of the Drain designated by &lt;Path&gt; and writes it into a table.

Remarks

The column Read-only Attribute lists the read-only attributes of the corresponding statistics values for all part types .

Type

Method

Syntax

```simtalk
< Path >.typeStatistics([TypeStatisticsTable:table]) → boolean
```

**Parameter**

The optional parameter TypeStatisticsTable of data type table designates the name of the table.

Return Value

The return value has the data type boolean .

- true if statistics collection is activated.

false if statistics collection is deactivated. Then the table remains unaltered.

- The return value is the table containing the statistics data if statistics collection is activated if you do not specify the optional parameter.

void if statistics collection is deactivated.

**Examples**

```simtalk
MyDrain.typeStatistics(MyDrainStatisticsTable) // Writes the statistics values to the table named MyDrainStatisticsTable. // The
return value is true
if statistics collection is activated. // It is false if it is deactivated. Then the table remains unaltered.
MyDrain.typeStatistics // Writes the statistics values to a table. // The
return value is the statistics table
if statistics collection is activated. // It is void if statistics collection is cleared.
```

SimTalk

typeStatisticsCumulated [SimTalk]

TypeStatOn [SimTalk]

See also

Detailed Statistics Table [Drain]

Statistics report , Part Types Which the Drain Removed From the Plant

##### typeStatisticsCumulated [SimTalk]

Returns the cumulated statistics table containing the MU types which the object designated by &lt;Path&gt; removed from the plant.

Type

Method

Syntax

```simtalk
< Path >.typeStatisticsCumulated([CumulatedTypeStatisticsTable:table]) → boolean
```

Parameter

The optional parameter CumulatedTypeStatisticsTable of data type table designates the name of the table.

The columns are the same as those in the table which the method typeStatistics fills. The column Type remains empty though.

Return Value

The return value has the data type boolean .

- true if statistics collection is activated. false if statistics collection is deactivated. Then the table remains unaltered.
- The return value is the table containing the statistics data if statistics collection is activated if you do not specify the optional parameter.
- void if statistics collection is deactivated.

**Examples**

```simtalk
MyDrain.typeStatisticsCumulated(myCumulatedDrainStatistics) // Writes the statistics values to the table named MyDrainStatisticsTable. // The
return value is true
if statistics collection is activated. // It is false if it is deactivated. Then the table remains unaltered.
MyDrain.typeStatisticsCumulated // Writes the statistics values to a table. // The
return value is the statistics table
if statistics collection is activated. // It is void if statistics collection is deactivated.
```

SimTalk

typeStatistics [SimTalk] - Drain

TypeStatOn [SimTalk]

#### Read-Only Attributes of the Drain

\_Read-Only Attributes of the Drain

The Drain provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .
- The Read-Only Attributes of the Material Flow Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Drain.StatAvgExitInterval

##### StatAvgExitInterval [SimTalk]

StatAvgExitInterval [SimTalk]

Returns the average time interval between exits of the MUs which the Drain designated by &lt;Path&gt; removed from the plant.

Remarks

StatAvgExitInterval results from adding up the times of all intervals, and then dividing them by the number of intervals. Statistics only starts counting from the time at which the first MU arrived.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatAvgExitInterval → time

Return Value

The return value has the data type time .

Example

print MyDrain.StatAvgExitInterval

See also

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatAvgLifeSpan [SimTalk] - Drain Returns the average life span of the MUs which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

< Path >.StatAvgLifeSpan → time

Return Value

The return value has the data type time .

Example

```simtalk
print MyDrain.StatAvgLifeSpan
```

See also

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatDeleted [SimTalk] - Drain Returns the number of MUs which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatDeleted → integer

Return Value

The return value has the data type integer .

Example

print MyDrain.StatDeleted

See also

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

Statistics report , Part Types Which the Drain Removed From the Plant

##### StatProdFailPortion [SimTalk] - Drain

Returns the portion of the sum of all life times of the MUs during which these stayed on a failed material flow object of resource type Production , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatProdFailPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var ra: real
ra := Drain.StatProdFailPortion + Drain.StatStoreFailPortion + Drain.StatTranspFailPortion
if ra > 0.6
	print "Considerable delays caused by failed machines."
end
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatProdPausingPortion [SimTalk] - Drain Returns the portion of the sum of all life times of the MUs during which these stayed on a paused or unplanned material flow object of resource type Production , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatProdPausingPortion → real

Return Value

The return value has the data type real .

Example

print MyDrain.StatProdPausingPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

##### StatProdSetupPortion [SimTalk] - Drain

Returns the portion of the sum of all life times of the MUs during which these stayed on a material flow object of resource type Production that was setting-up for the MU type, and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatProdSetUpPortion → real

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatProdWaitingPortion
print "The waiting time portion on resources of resource type Production for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatProdSetUpPortion
print "The set-up time portion on resources of resource type Production for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatProdStoppedPortion [SimTalk] - Drain Returns the time portion during which the MU was located on a material flow object of resource type Production that was stopped by a LockoutZone , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatProdStoppedPortion → real

Return Value

The return value has the data type real .

Example

print Drain.StatProdStoppedPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

##### StatProdWaitingPortion [SimTalk] - Drain

Returns the time portion of the sum of all life times of the MUs during which these stayed on a waiting material flow object of resource type Production , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatProdWaitingPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatProdWaitingPortion
print "The waiting time portion on resources of resource type Production for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatProdSetUpPortion
print "The set-up time portion on resources of resource type Production for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatProdWorkingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a working material flow object of resource type Production , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatProdWaitingPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatProdWaitingPortion
print "The waiting time portion on resources of resource type Production for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatProdSetUpPortion
print "The set-up time portion on resources of resource type Production for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatStoreFailPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a failed material flow object of resource type Storage , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoreFailPortion → real

Return Value

The return value has the data type real .

Example

print MyDrain.StatProdFailPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatStorePausingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a paused or unplanned material flow object of resource type Storage , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStorePausingPortion → real

Return Value

The return value has the data type real .

Example

print MyDrain.StatStorePausingPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatStoreSetUpPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a material flow object of resource type Storage that was setting-up for the MU type, and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatStoreSetUpPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatStoreWaitingPortion
print "The waiting time portion on resources of resource type Storage is ", round(100*(wa),2)," %."
ra := MyDrain.StatProdSetUpPortion
print "The set-up time portion on resources of resource type Storage is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatStoreStoppedPortion [SimTalk] - Drain Returns the time portion during which the MU was located on a material flow object of type Store that was stopped by a LockoutZone , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoreStoppedPortion → real

Return Value

The return value has the data type real .

Example

print Drain.StatStoreStoppedPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

##### StatStoreWaitingPortion [SimTalk] - Drain

Returns the time portion of the sum of all life times of the MUs during which these stayed on a waiting material flow object of resource type Storage , and which the Drain designated by &lt;Path&gt; removed from the plant.

Syntax

```simtalk
< Path >.StatStoreWaitingPortion → real
```

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatStoreWaitingPortion
print "The waiting time portion on resources of resource type Storage for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatProdSetUpPortion
print "The set-up time portion on resources of resource type Storage for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatStoreWorkingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a working material flow object of resource type Storage , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatStoreWorkingPortion → real

Return Value

The return value has the data type real .

Example

print MyDrain.StatStoreWorkingPortion

See also

Resource Type of the material flow objects

Tab Type Statistics of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatThroughputPerDay [SimTalk] - Drain Returns the number of MUs that the Drain designated by &lt;Path&gt; removed from the plant in a day over all observed times during which the Drain was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughputPerDay → real

Return Value

The return value has the data type real .

This is the value of the throughput per hour multiplied with 24.

The throughput is measured in liters.

Example

print MyDrain.StatThroughputPerDay

See also

Tab Type Statistics of the Drain

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatThroughputPerHour [SimTalk] - Drain Returns the number of MUs that the Drain designated by &lt;Path&gt; removed from the plant in an hour over all observed times during which the Drain was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughputPerHour → real

Return Value

The return value has the data type real .

The throughput is measured in liters.

Example

print MyDrain.StatThroughputPerHour

See also

Tab Type Statistics of the Drain

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

##### StatThroughputPerMinute [SimTalk]

Returns the number of MUs that the Drain designated by &lt;Path&gt; removed from the plant in a minute over all observed times during which the Drain was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughputPerMinute → real

Return Value

The return value has the data type real .

Example

print MyDrain.StatThroughputPerMinute

See also

Tab Type Statistics of the Drain

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatTranspFailPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a failed material flow object of type Transport which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspFailPortion -&gt; real

Return Value

The return value has the data type real .

Example

print MyDrain.StatThroughputPerHour

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatTranspPausingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a paused or unplanned material flow object of type Transport , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspPausingPortion -&gt; real

Return Value

The return value has the data type real .

Example

print MyDrain.StatTranspPausingPortion

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatTranspSetupPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a material flow object of type Transport that was setting-up for the MU type, and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspSetUpPortion -&gt; real

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatTranspWaitingPortion
print "The waiting time portion on resources of type transport for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatTranspSetUpPortion
print "The set-up time portion on resources of type transport for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

StatTranspStoppedPortion [SimTalk] - Drain

Returns the time portion during which the MU was located on a material flow object of resource type Transport that was stopped by a LockoutZone , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspStoppedPortion -&gt; real

Return Value

The return value has the data type real .

Example

print Drain.StatTranspStoppedPortion

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatTranspWaitingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a waiting material flow object of resource type Transport , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspWaitingPortion -&gt; real

Return Value

The return value has the data type real .

Example

```simtalk
var ra,wa: real
wa := MyDrain.StatTranspWaitingPortion
print "The waiting time portion on resources of resource type Transport for all parts is ", round(100*(wa),2)," %."
ra := MyDrain.StatTranspSetUpPortion
print "The set-up time portion on resources of type transport for all parts is ", round(100*(ra),2)," %."
```

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant StatTranspWorkingPortion [SimTalk] - Drain Returns the time portion of the sum of all life times of the MUs during which these stayed on a working material flow object of resource type Transport , and which the Drain designated by &lt;Path&gt; removed from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatTranspWorkingPortion -&gt; real

Return Value

The return value has the data type real .

Example

print MyDrain.StatTranspWorkingPortion

See also

Resource Type of the material flow objects

Detailed Statistics Table [FluidDrain] of the Drain

Statistics report , Cumulated Statistics of the Parts which the Drain Removed From the Plant

#### Attributes of the Drain

Attributes of the Drain

The Drain provides:

- The attribute TypeStatOn [SimTalk] .
- The Attributes of the Station .
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
MyDrain.Pause := true
print MyDrain.Pause
posit := MyStation.Cont.XPos
```

##### TypeStatOn [SimTalk]

Activates collecting statistics values of the Drain designated by &lt;Path&gt; depending on the type of MU ( true ) or deactivates it ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.TypeStatOn:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyDrain.TypeStatOn := false

See also

Type Dependent Statistics

typeStatistics [SimTalk] - Drain

typeStatisticsCumulated [SimTalk]

