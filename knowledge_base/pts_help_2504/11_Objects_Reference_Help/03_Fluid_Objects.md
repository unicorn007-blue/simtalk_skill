## Fluid Objects

Plant Simulation provides the fl uid objects to simulate free-flowing materials, be they in liquid, gaseous, or pourable form. The fl uid objects are especially suited for the food and beverages processing industries and for the pharmaceutical industries.

<!-- image -->

<!-- image -->

### Fluid Objects

A typical simulation with fluid objects consists of several FluidSources which provide the ingredients for mixing together the intermediate or the finished product. The FluidSources are connected with Connectors and Pipes to Tanks , which temporarily store the ingredients or the products, or to Mixers which mix the different ingredients to an intermediate or to a finished product. Pipes transport the free-flowing materials from fluid object to fluid object. The fluid objects themselves have to be connected with Pipes . The FluidDrain removes the finished product from the plant.

**Note**

You have to connect the individual fluid objects with Connectors . You cannot connect them with Pipes only.

You can control the flow of ingredients by opening or closing the entrances or the exits of the Tanks , Mixers , and Pipes . The Mixer pulls the ingredients from the predecessors via inflow connections according to the chemical formula which you typed into the MaterialsTable . Provided an open Pipe is connected, the Mixer sends the processed product on via an outflow connection .

- Use the Connector to establish connections between the fluid objects.
- Use the DePortioner to empty incoming parts of bulk goods or fluids, create a fluid out of it, and feed the resulting fluids into a.
- Use the FluidSource to produce the ingredients of the product, either bulk goods or fluids, which are processed in the plant.
- Use the FluidDrain to remove the product from the plant after it has been mixed or processed.
- Use the MaterialsTable to define the ingredients and the products to be processed in the plant.
- Use the Mixer to transmute the ingredients of the process into an intermediate or a finished product by mixing them.
- Use the ContinuousMixer to transmute the ingredients of the process into an intermediate or finished product by continuously mixing them.
- Use the PatchMatrix to connect an entrance pipe with an exit pipe to control the flow of the materials within the plant.
- Use the Pipe to transport free-flowing materials between the other fluid objects in the plant.
- Use the Portioner to create a mobile object out of a free-flowing product.
- Use the Tank to temporarily store a single material before or after processingg.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Shared Properties

Simulate Free-flowing Materials and Fluids

#### Shared Properties

### Shared Properties

The fluid objects share the following properties.

- Dialog Items of the Fluid Objects
- Methods of the Fluid Objects
- \_Read-Only Attributes of the Fluid Objects
- \_Attributes of the Fluid Objects

You will find the object-specific properties in the subchapters of the respective objects.

<!-- image -->

#### Dialog Items of the Fluid Objects

Dialog Items of the Fluid Objects

The fl uid objects share a number of dialog items and menus. To open the dialog box of an object, double-click its icon.

After opening the dialog, Plant Simulation shows the current values. Type new settings into the text boxes or select them from the drop-down lists. Click OK or Apply to accept changes you made and to update the dialog. Instead, you can also press F5 to show the most current results of a simulation run on some of the tabs.

<!-- image -->

To edit the 3D properties of the object in the 3D model, select the object and press the spacebar . Then change the respective settings in the dialog Edit 3D Properties .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

**See also**

| Inheritance [general description]                | Tab Set-Up [general description]              |
|--------------------------------------------------|-----------------------------------------------|
| Name [general description]                       | Tab Failures [general description]            |
| Label [general description]                      | Tab Controls [general description]            |
| Failed [check box] - material flow objects       | Tab Exit [general description]                |
| Paused/Planned/Unplanned [material flow objects] | Tab Statistics [material flow objects]        |
| Entrance Locked [material flow objects]          | Tab Importer [general description]            |
| Exit Locked [material flow objects]              | User-defined Attributes [general description] |
| OK                                               | Navigate Menu                                 |
| Cancel                                           | View Menu                                     |
| Apply                                            | Tools Menu                                    |

| Context Menu of Text Boxes in Dialogs   | Help Menu                                          |
|-----------------------------------------|----------------------------------------------------|
| Tab Times [general description]         | LEDs and States of the Material Flow Objects in 2D |

**Entrance Locked [fluid objects]**

##### Entrance Locked [fluid objects]

To close the entrance of the fluid object, select this check box.

<!-- image -->

If you lock the entrance of the fluid object, no material can flow into the object.

<!-- image -->

The LED of a fluid object whose entrance is locked is cyan .

3D shows the State Graphic of the object as a colored ring on a pole by default.

SimTalk

EntranceLocked [SimTalk] - fluid objects

##### Exit Locked [fluid objects]

To close the exit of the fluid object, select this check box.

<!-- image -->

If you close the exit of a fluid object, Plant Simulation prevents material from flowing off.

SimTalk

ExitLocked [SimTalk] - material flow objects

**Tab Statistics [fluid objects]**

##### Tab Statistics [fluid objects]

The fl uid objects show the most important statistical data on the tab Statistics .

The values for Waiting , Working , Blocked , Setting-Up , Failed , Stopped , Paused and Unplanned should add up to 100 percent.

<!-- image -->

| Item English   | Description                                                                                                                                                             | Item German   |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Working        | Shows the portion of the statistics collection period during which the fluid object was Working .                                                                       | Arbeitend     |
| Setting-up     | Shows the portion of the statistics collection period during which the fluid object was setting up.                                                                     | Rüstend       |
| Waiting        | Shows the portion of the statistics collection period during which the fluid object was waiting.                                                                        | Wartend       |
| Blocked        | Shows the portion of the statistics collection period during which the fluid object was Blocked .                                                                       | Blockiert     |
| Failed         | Shows the portion of the statistics collection period during which the fluid object was Failed .                                                                        | Gestört       |
| Paused         | Shows the portion of the statistics collection period during which the fluid object was Paused .                                                                        | Pausiert      |
| Unplanned      | Shows the portion of the statistics collection period during which the fluid object was Unplanned , i.e., is not scheduled to work to the statistics collection period. | Ungeplant     |

Not all fluid objects provide all statistics values described above, while some fluid objects provide additional values that are described in the chapter of the respective object.

To view Resource Statistics of Stationary Resources in the Statistics Report , select View &gt; Show Statistics Report in the dialog of the object. You can also click the right mouse button in the Frame and select Show Statistics Report or you can press F6 .

See also

View Statistics in the Dialogs of the Objects

\_Attributes of the Fluid Objects

Methods of the Fluid Objects

**Navigate Menu**

**Navigate Menu**

The commands are described under the Navigate Menu .

**View Menu**

The View Menu provides commands to access its functions.

| Refresh [on View menu]                     | Associated Lockout Zones         |
|--------------------------------------------|----------------------------------|
| Show Attributes and Methods [on View menu] | Associated Shift Calendar        |
| Contents [material flow objects]           | Exit Blocking List ( Portioner ) |
| Forward Blocking List ( DePortioner )      |                                  |

The View Menu also provides these commands pertaining to the Transport Importer :

| Exporters [on View menu]   | Unavailable Services [on View menu]   |
|----------------------------|---------------------------------------|
| Services [on View menu]    | Associated Workplaces [on View menu]  |

**Tools Menu**

**Tools Menu**

The commands are described under the Tools Menu .

**Help Menu**

The commands are described under the Help Menu .

#### Methods of the Fluid Objects

Methods of the Fluid Objects

The fluid objects provide:

- The Methods of All Objects .
- The \_Methods for Defining Failures .
- The \_Methods of the Importer .

The sub-chapters about the objects list additional methods for the fluid objects.

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

#### Read-Only Attributes of the Fluid Objects

\_Read-Only Attributes of the Fluid Objects

The Fluid Objects provide:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyMixer.ResWorking

##### CurrentInFlowrate [SimTalk]

CurrentInFlowrate [SimTalk]

Returns the Current Inflow Rate of the fluid object designated by &lt;Path&gt;.

Remarks

The inflow rate is the amount of liters of the material per second which flows into the object.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentInFlowrate → real

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

print FluidDrain.CurrentInFlowrate

##### CurrentMaterialColor [SimTalk]

Returns the current material color in the fluid object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentMaterialColor → real

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

print SourceCocoa.CurrentMaterialColor

See also

MaterialsTable

##### CurrentMaterialDensity [SimTalk]

CurrentMaterialDensity [SimTalk]

Returns the current material density in the fluid object designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.CurrentMaterialDensity → real
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

```simtalk
print SourceCocoa.CurrentMaterialDensity // might, for example,
return 1 for 1 gram per cubic centimeter
```

See also

MaterialsTable

##### CurrentOutFlowrate [SimTalk]

Returns the current out-flow rate of the fluid object designated by &lt;Path&gt;.

Remarks

The out-flow rate is the amount of liters per second which flows out of the object.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentOutFlowrate → real

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

Example

print Tank.CurrentOutFlowrate

**CurrentWeight [SimTalk]**

##### CurrentWeight [SimTalk]

Returns the weight of the current material in the DePortioner , Mixer , Portioner , or Tank designated by &lt;Path&gt;.

Remarks

The weight is shown in the unit which you selected under Model Settings &gt; Unit &gt; Mass .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentWeight → real

Return Value

The return value has the data type real .

Example

print MyMixer.CurrentWeight

See also

Mass [model settings]

ResBlocked [SimTalk] - fluid objects

Returns if the fluid object designated by &lt;Path&gt; is blocked (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.ResBlocked → boolean

Return Value

The return value has the data type boolean .

Example

print MyMixer.ResBlocked

See also

Blocked [state, material flow objects]

ResCurrentState [SimTalk] - fluid objects

Returns the current state of the fluid object designated by &lt;Path&gt;.

Remarks

During a simulation run a material flow resource can take on one of these states: Working , Setting-up , Waiting , Blocked , Failed , Stopped , Paused , Powering Up/down , or Unplanned .

**Note**

If two states occur at the same time, for example Paused and Failed , the read-only attribute returns the state that also has precedence for statistics collection. Paused for example for Paused and Failed .

Type

Read-only attribute

Syntax

&lt; Path &gt;.ResCurrentState → string

Watchable

The read-only attribute is watchable .

Use it in waituntil-instructions or to make the object TimeSequence record it in watch mode.

Return Value

The return value has the data type string .

Example

print MyMixer.ResCurrentState

See also

Resource Statistics [material flow objects]

Working [state, material flow objects] , Setting-Up [state, material flow objects] , Waiting [state, material flow objects] , Blocked [state, material flow objects] , Failed [state - material flow objects] , Stopped [state, material flow objects] , Paused [state, material flow objects] , Powering up/down [state, material flow objects] , Unplanned [state, material flow objects]

ResSetup [SimTalk] - fluid objects

ResSetup [SimTalk] - fluid objects

Returns if the fluid object designated by &lt;Path&gt; is Setting-up and not failed, not paused, or not stopped (true) or not (false).

Type

Read-only attribute

Syntax

&lt; Path &gt;.ResSetup → boolean

Return Value

The return value has the data type boolean .

Example

print FluidDrain.ResSetup

See also

Setting-Up [state, material flow objects]

ResWaiting [SimTalk] - fluid objects

Returns if the fluid object designated by &lt;Path&gt; is Waiting (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.ResWaiting → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyMixer.ResWaiting
```

See also

Waiting [state, material flow objects]

##### ResWorking [SimTalk] - fluid objects

ResWorking [SimTalk] - fluid objects

Returns if the fluid object designated by &lt;Path&gt; is Working (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.ResWorking → boolean
```

Return Value

The return value has the data type boolean .

Example

```simtalk
print MyMixer.ResWorking
```

See also

Working [state, material flow objects]

#### Attributes of the Fluid Objects

\_Attributes of the Fluid Objects

All fluid objects have attributes whose value you can set and query. An attribute corresponds to a dialog item, a check box or a command of a drop-down list, etc., on one of the tabs of the object.

The fluid objects provide:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Importer .
- The Attributes of All Objects .

The sub-chapters about the objects list additional attributes for these objects.

All fluid objects have predefined attributes controlling their behavior or representing their state. You can set the value of an attribute and you can get its value, either using the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the corresponding attributes.

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To set the value of an attribute, you might, for example, type:

```simtalk
MyMixer.EntranceLocked := true
```

To get the value of an attribute, you might, for example, type:

```simtalk
print MyMixer.EntranceLocked
posit := MyStation.Cont.XPos
```

##### EntranceLocked [SimTalk] - fluid objects

EntranceLocked [SimTalk] - fluid objects

Locks ( true ) or unlocks ( false ) the entrance of the fluid object designated by &lt;Path&gt;.

Remarks

You can also lock or unlock the entrance with the check box Entrance Locked .

Type

Attribute

Syntax

&lt; Path &gt;.EntranceLocked:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyMixer.EntranceLocked := true

SimTalk

EntranceFree [SimTalk]

See also

Entrance Locked [fluid objects]

##### ExitLocked [SimTalk] - fluid objects

Locks ( true ) or unlocks ( false ) the exit of the fluid object designated by &lt;Path&gt;.

Remarks

You can also lock or unlock the exit with the check box Exit Locked .

Type

Attribute

Syntax

&lt; Path &gt;.ExitLocked:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyMixer.ExitLocked := true
```

See also

Exit Locked [fluid objects]

##### RandomSeed [SimTalk] - fluid objects

Sets the seed values which are required for creating the random numbers of the fluid object designated by &lt;Path&gt; together with the Random Numbers Variant of the EventController .

**Remarks**

When you insert an object into your model, Plant Simulation automatically assigns a random number seed value to this object. You can query the next assigned random seed value with the function setRandomSeedCounter(0) . After the object is created, Plant Simulation increases this counter by 1, so that the next object gets a different random seed value.

If you assign the same random number seed value to two objects, these two objects will generate the same sequence of random numbers, for example for Processing Times which use a distribution, etc.

**Note**

The seed value affects the random number stream of the fluid object which is used for the Setup Time and other times. It also affects the random number streams of the failure profiles, and the random number streams of user-defined attributes of data type RandTime . Plant Simulation makes sure that all of these random number streams are initialized differently. This means that changing the attribute RandomSeed causes the random number stream of the fluid object and also the random number streams of all failure profiles and user-defined attributes to generate a new sequence of random numbers, and all of these streams will generate different sequences of numbers.

Type

Attribute

Syntax

&lt; Path &gt;.RandomSeed:integer

Assignment Value

You can assign a value of data type integer .

Example

MyMixer.RandomSeed := 40

SimTalk

IncrementRandomNumbersVariantOnReset [SimTalk]

RandomNumbersVariant [SimTalk] setRandomSeedCounter [SimTalk] See also Simulating Random Processes Random Seed Value Increment Variant on Reset of the EventController Random Numbers Variant of the EventController Data Types [SimTalk]

SetupTime [SimTalk] - fluid objects

SetupTime [SimTalk] - fluid objects

Sets the duration of the Set-up Time of the fluid object designated by &lt;Path&gt;.

Remarks

A fluid object has to set up whenever the name of the next material differs from the name of its preceding material.

The set-up time is the time it takes to set the object up for processing a different type of material . An identical name designates that materials are of the same type.

Type

Attribute

Syntax

< Path >.SetupTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyMixer.SetupTime := 120 // 2 minutes
```

See also

Set-up Time [general description]

Times and Distributions

### Pipe

Pipe Use the Pipe to transport free-flowing materials between the other fluid objects in the plant.

**Icon**

<!-- image -->

**Description**

Insert Pipes to transport free-flowing materials between the objects FluidSource , Tank , Mixer , Portioner , DePortioner , and FluidDrain .

While material flows through the Pipe , it shows the color of that material as its color. This is the color which you selected for the material in the MaterialsTable . You have to establish connections between Pipes and fl uid objects with the Connector . To make materials flow between the fl uid objects , you have to use Pipes .

You can insert the Pipe into a Frame as follows:

**· In a 3D Only Model**

As a curved object, which is the default setting.

By inserting any sequence of curved segments and straight segments, you can realistically model curved conveyor systems through which the fl uids flow.

You can select different configurations for the Pipe on the tab Appearance .

<!-- image -->

**· In a 2D Only Model**

As a curved object, which is the default setting.

With its icon, if you deactivate Curve mode on the Tab Curve by clearing the check box . Then, it looks like this .

To show a tooltip with information about the Pipe , hover with the mouse over it.

**Show Manipulators**

To change the length of the graphic and the anchor points of the object, click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

The manipulator at the start and at the end of the length-oriented object is cut off. When you attach an object of the same type to the other object, the two combined halves result in a complete manipulator again. When you move the mouse over a manipulator, Plant Simulation shows a Tooltip .

<!-- image -->

The height of the manipulators of the Pipe goes by the width of the Pipe .

<!-- image -->

Add the Object to the Simulation Model

To add the Pipe to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; Pipe

on the Home ribbon tab.

<!-- image -->

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

#### Dialog Box of the Pipe

Dialog Box of the Pipe

Double-click the icon of the Pipe to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes [Pipe]

The tab Attributes provides the settings listed in the table of contents to the left.

In 3D, you can edit the length of the graphic and the anchor points of the Pipe by clicking Show Manipulators on the Edit ribbon tab or by clicking M on the keyboard.

To change the length of the graphic and the anchor points of the Pipe , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

<!-- image -->

###### Outflow Rate [Pipe]

Type in the Outflow Rate with which the material flows out of the Pipe to the next object in the flow of materials.

<!-- image -->

The Outflow Rate is the amount of liters of the material that flows off in a second.

The default value -1 denotes that the Pipe uses the same outflow rate as its predecessor.

This applies to a Pipe that is located directly after a FluidSource , a DePortioner , a Tank , or a Mixer .

**Note**

This applies to a Pipe that is located directly after a FluidSource , a DePortioner , a Tank , or a Mixer .

**Note**

If you enter another value than the default value, Plant Simulation uses the entered Outflow Rate even if it is higher than the Outflow Rate of the predecessor.

The Outflow Rate enables you to create the effect that not all of the succeeding Pipes connected to a FluidSource , a Tank , a DePortioner , or a Mixer , have to have the same Outflow Rate .

If the predecessor of the Pipe is another Pipe , Plant Simulation ignores the value. For this reason the text box is unavailable.

This does not apply if the Pipe has a single successor and if the predecessor Pipe has a single successor as well. Thus, if several Pipes are arranged one behind the other, Plant Simulation uses the lowest specified value for all Pipes .

**SimTalk**

OutflowRate [SimTalk] - Pipe

###### Pipe Opened [check box]

To open the entrance of the Pipe so that materials can flow through it, select this check box.

<!-- image -->

This way you can model a valve or a gate valve to open and to close the Pipe . To close the Pipe , clear the check box.

If you clear Pipe Opened , it shows the state Pipe Closed in cyan.

<!-- image -->

**SimTalk**

**PipeOpened [SimTalk]**

Exit strategy

Exit Strategy - Pipe

Select the Exit Strategy according to which the Pipe distributes the flow rate to the succeeding fluid objects.

- Evenly distributed
- Percentage [Pipe]

**Note**

To show the items belonging to the new strategy, click Apply after you selected another strategy.

**Evenly distributed**

To distribute the flow rate of the Pipe evenly among the succeeding fluid objects, select this setting.

<!-- image -->

**Percentage [Pipe]**

**Percentage [Pipe]**

To distribute the flow rate of the Pipe according to a proportional distribution among the succeeding fluid objects, select Percentage from the drop-down list.

To show the button Open List , click Apply .

**Open List**

Click Open List and type in the percentages for the individual succeeding objects. In the example below successor 1 receives 20% of the material, successor 2 receives 30%, etc.

<!-- image -->

Type 0 into the cell of the respective successor to prevent that successor from receiving any material.

If a successor cannot receive any material, because a succeeding Tank is full for example, the Pipe distributes the portion of that successor of the flow rate according to the percentages to the remaining successors.

The sum of the percentages does not have to add up to 100%. Instead, the actual sum of the percentages of all successors, which can receive material, corresponds to a value of 100%. The percentages [40, 60], [0.4, 0.6], and [2, 3] are equivalent for example.

SimTalk

ExitStrategyPercentageValues [SimTalk] - Pipe

See also

Exit Strategy - Pipe

###### Current Material [Pipe]

Shows the name of the material that currently flows through the Pipe .

**Note**

The name of the Current Material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

In 3D the Pipe shows the current material with the color which you assigned to the material.

SimTalk

CurrentMaterial [SimTalk] - Pipe

###### Current Flow Rate [text box]

Current Flow Rate [text box]

Shows the Current Flow Rate of the materials flowing through the Pipe . This is the amount of liters per second.

SimTalk

CurrentFlowrate [SimTalk]

Tab Times

Define the Set-up Time as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Set-up Time [general description]

SetupTime [SimTalk] - fluid objects

Select the Set-Up Time

**Tab Statistics**

##### Tab Statistics

The Pipe provides the statistics values described under the Tab Statistics .

<!-- image -->

##### Tab Curve [Pipe]

Create curved Pipes for your simulation model as described under the tab Curve .

<!-- image -->

<!-- image -->

**Note**

The text box Curve Width will only be displayed when you deactivate Transfer Length . When you activate it, you can enter the Width in meters on the tab Attributes of the respective object.

<!-- image -->

**Number of Animation Events**

When you deactivate Curve mode, by clearing the check box Active , you can enter the Number of Animation Events . It sets how often Plant Simulation shows the MU , while it is located on the object Pipe during a simulation run. Conveyor

- Click the icon of the Pipe with the left mouse button and click Edit Icons on the Home ribbon tab.
- Change to the Animation ribbon tab and select Set Animation Events . Enter a number into the text box.

<!-- image -->

**Note**

The number you can enter here only applies, when you insert a length-oriented object in icon mode . In curve mode they animate the MUs with the setting you select for Animate Every x-th Pixel .

The settings Number of Animation Events or Animate Every x-th Pixel also apply to the rotation.

**See also**

Tab Curve [general description]

##### Tab User-defined Attributes

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu The commands are described under the View Menu . SimTalk updateDialog [SimTalk]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the Pipe

Methods of the Pipe

The Pipe provides the Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

#### Read-Only Attributes of the Pipe

\_Read-Only Attributes of the Pipe

The Pipe provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Pipe1.LengthOfPipe

**CurrentFlowrate [SimTalk]**

##### CurrentFlowrate [SimTalk]

Returns the current flow rate of the materials flowing through the Pipe designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentFlowrate → real

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type real .

It is the amount of liters per second.

Example

print Pipe1.CurrentFlowrate

See also

Current Flow Rate [text box]

CurrentMaterial [SimTalk] - Pipe

Returns the Current Material that currently flows through the Pipe designated by &lt;Path&gt;.

Remarks

The name of the current material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentMaterial → string

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type string .

Example

```simtalk
print Pipe1.CurrentMaterial
```

See also

Current Material [Pipe]

Relational Operators

##### LengthOfPipe [SimTalk]

LengthOfPipe [SimTalk]

Returns the Length of the Pipe designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.LengthOfPipe → real
```

Return Value

The return value has the data type real .

Is the length of the Pipe which you inserted into the Frame by clicking the left mouse button to set its first and its last point.

Example

```simtalk
print Pipe1.LengthOfPipe
```

#### Attributes of the Pipe

\_Attributes of the Pipe

The Pipe provides:

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
Pipe.PipeOpened := true
print Pipe.PipeOpened
posit := MyStation.Cont.XPos
```

ExitStrategy [SimTalk] - Pipe

ExitStrategy [SimTalk] - Pipe

Sets how the flow rate of the Pipe designated by &lt;Path&gt; is going to be distributed to the succeeding fluid objects.

Syntax

```simtalk
< Path >.ExitStrategy:string
```

Type

Attribute

Assignment Value

You can assign a value of data type string .

You can specify "Evenly distributed" or "Percentage" .

Example

```simtalk
MyPipe.ExitStrategy := "Evenly distributed"
```

See also

Exit Strategy - Pipe ExitStrategyPercentageValues [SimTalk] - Pipe Sets the proportional distribution of the flow rate of the Pipe designated by &lt;Path&gt; for the Exit Strategy &gt; Percentage .

Remarks

Specify 0 in the cell of the respective successor to prevent that successor from receiving any material.

If a successor cannot receive any material, because a succeeding Tank is full for example, the Pipe distributes the portion of that successor of the flow rate according to the percentages to the remaining successors.

The sum of the percentages does not have to add up to 100%. Instead, the actual sum of the percentages of all successors, which can receive material, corresponds to a value of 100%. The percentages [40, 60], [0.4, 0.6], and [2, 3] are equivalent for example.

Type

Attribute

Syntax

< Path >.ExitStrategyPercentageValues:array

Assignment Value

You can assign a value of data type array .

Example

```simtalk
MyPipe.ExitStrategy := "Percentage"
MyPipe.ExitStrategyPercentageValues := [20, 50, 30]
```

See also

Exit Strategy - Pipe &gt; Percentage [Pipe]

##### OutflowRate [SimTalk] - Pipe

Sets the outflow rate with which the material flows out of the Pipe designated by &lt;Path&gt; to the next object in the flow of materials.

Remarks

The default value -1 denotes that the Pipe uses the same outflow rate as its predecessor.

The outflow rate is the amount of liters of the material that flows off in a second.

**Note**

This applies to a Pipe that is located directly after a FluidSource , a DePortioner , a Tank , or a Mixer .

**Note**

If you specify another value than the default value, Plant Simulation uses the specified Outflow Rate even if it is higher than the Outflow Rate of the predecessor.

#### DePortioner

The Outflow Rate enables you to create the effect that not all of the succeeding Pipes connected to a FluidSource , a Tank , a DePortioner , or a Mixer , have to have the same Outflow Rate .

If the predecessor of the Pipe is another Pipe , Plant Simulation ignores the value. For this reason the text box is unavailable.

This does not apply if the Pipe has a single successor and if the predecessor Pipe has a single successor as well. Thus, if several Pipes are arranged one behind the other, Plant Simulation uses the lowest specified value for all Pipes .

Type

Attribute

Syntax

&lt; Path &gt;.OutflowRate:real

Assignment Value

You can assign a value of data type real .

**Example**

```simtalk
Pipe.OutflowRate := 1
```

**See also**

Outflow Rate [Pipe]

##### PipeOpened [SimTalk]

Opens the Pipe designated by &lt;Path&gt; so that materials can flow through it ( true ).

Remarks

Use PipeOpened to model a valve or a gate valve to open and to close the Pipe .

To close the Pipe specify false . The Pipe then shows the state Pipe Closed in cyan.

<!-- image -->

Type

Attribute

Syntax

&lt; Path &gt;.PipeOpened:boolean

Assignment Value

You can assign a value of data type boolean .

Example

Pipe.PipeOpened := true

See also

Pipe Opened [check box]

**FluidSource**

### FluidSource

Use the FluidSource to produce the ingredients of the product, either bulk goods or fluids, which are processed in the plant.

**Icon**

<!-- image -->

**Description**

Use the FluidDrain to remove the processed and mixed products from the plant.

To change the length of the graphic and the anchor points of the FluidSource , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

To show a tooltip with information about the FluidSource , hover with the mouse over it.

<!-- image -->

Add the Object to the Simulation Model

To add the FluidSource to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; FluidSource on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

**See also**

Configure the FluidSources Providing the Materials

Configure the FluidSources Which Produce the Materials

Produce Fluids in a Fixed Sequence

#### Dialog Box of the FluidSource

Dialog Box of the FluidSource

Double-click the icon of the FluidSource to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Outflow Rate [FluidSource]**

###### Outflow Rate [FluidSource]

Type in the Outflow Rate with which the material flows out of the object and flows through the objects of type Pipe to the next object in the flow of materials.

<!-- image -->

The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes enables this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

SimTalk

OutflowRate [SimTalk] - FluidSource

See also

Pipe

###### Material Selection [drop-down list]

Select how the FluidSource selects the material it produces.

<!-- image -->

**Note**

Depending on what you select here, the setting Material either defines the Material itself or the path to the sequence table .

- Constant : The FluidSource produces a single type of material only. Type the name of material into the text box Material .
- Sequence Cyclical : The FluidSource produces the materials in the sequence and with the amount in the order in which you type them into the Sequence Table .

<!-- image -->

Once the FluidSource has processed the entire sequence, it starts processing the information in the table again starting at the beginning of the sequence.

Type the name of the Sequence Table into the text box Material .

Or click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

<!-- image -->

- Sequence : The FluidSource produces the materials in the sequence and with the amount in the order in which you type them into the Sequence Table .

As opposed to Sequence Cyclical , the setting Sequence processes the sequence only once, not repeatedly. If the sequence is processed once, the FluidSource does not produce any additional materials.

Type the name of the Sequence Table into the text box Material .

Or click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

<!-- image -->

SimTalk MaterialSelection [SimTalk] See also Produce Fluids in a Fixed Sequence Material [text box] - FluidSource Material [SimTalk] - FluidSource

###### Material [text box] - FluidSource

Type in the name of the Material which the FluidSource is to produce.

<!-- image -->

<!-- image -->

- Constant : The FluidSource produces a single type of material only. Type the name of material into the text box Material .
- Sequence Cyclical : The FluidSource produces the materials in the sequence and with the amount in the sequence in which you type them into the Sequence Table .
- Once the Source has processed the entire sequence, it starts processing the information in the table again starting at the beginning of the sequence.

<!-- image -->

Type the name of the Sequence Table into the text box Material .

Or click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

<!-- image -->

- Sequence : The FluidSource produces the materials in the sequence and with the amount in the sequence in which you type them into the Sequence Table .
- As opposed to Sequence Cyclical , the setting Sequence processes the sequence only once, not repeatedly.
- Type the name of the Sequence Table into the text box Material .

Or click and select the name of the table in the dialog Select Object . Plant Simulation automatically formats the table.

<!-- image -->

**Sequence Table**

Define the materials, which the FluidSource is to produce in the sequence table .

<!-- image -->

You can type in:

- The name of the Material , for example MatA , MatB , MatC , MatD , etc.
- The Amount in liters of the Material that the FluidSource is to produce.

Define the names of the material in the MaterialsTable .

<!-- image -->

If the product consists of more than ten ingredients, add additional ingredients to the MaterialsTable , compare Add Additional Ingredients to the MaterialsTable .

**SimTalk**

Material [SimTalk] - FluidSource

See also

Produce Fluids in a Fixed Sequence

Material Selection [drop-down list]

MaterialSelection [SimTalk]

**Materials Table [FluidSource]**

###### Materials Table [FluidSource]

Click the ellipsis button and select the MaterialsTable in the dialog Select Object .

<!-- image -->

The MaterialsTable object contains the data of the different materials which the FluidSource can produce.

<!-- image -->

Or select the MaterialsTable in a Frame , drag it to the text box and drop it there.

SimTalk

MaterialsTable [SimTalk] - FluidSource

See also

MaterialsTable

Select Object [for controls]

###### Shift Calendar [FluidSource]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the FluidSource works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

**ShiftCalendarObject [SimTalk] - material flow objects**

See also

ShiftCalendar [object]

Associated Shift Calendar

Select Object [for controls]

**Current Outflow Rate [FluidSource]**

###### Current Outflow Rate [FluidSource]

Shows the Current Outflow Rate , i.e., the amount of liters of the material that flows out of the FluidSource in a second and that flows through objects of type Pipe to the next object in the flow of materials.

SimTalk

CurrentOutFlowrate [SimTalk]

See also

Pipe

##### Tab Failures

Define failures as described under the Tab Failures .

**Tab Statistics [FluidSource]**

##### Tab Statistics [FluidSource]

In addition to the values described under the Tab Statistics the tab Statistics of the FluidSource shows this object-specific value.

| Item English       | Description                                                       | Read-only attribute   | Item German   |
|--------------------|-------------------------------------------------------------------|-----------------------|---------------|
| Amount of Material | Shows the amount of material that flowed out of the FluidSource . | StatAmount [SimTalk]  | Materialmenge |

<!-- image -->

**See also**

**Statistics Report [described]**

##### Tab User-defined Attributes

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The commands are described under the View Menu .

SimTalk

updateDialog [SimTalk]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the FluidSource

Methods of the FluidSource

The FluidSource provides:

- The Methods of the Fluid Objects .
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

#### Read-Only Attributes of the FluidSource

Read-Only Attributes of the FluidSource

The FluidSource provides:

- The read-only attribute StatAmount [SimTalk] .
- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print FluidDrain.StatMaxFlowRate

**StatAmount [SimTalk]**

##### StatAmount [SimTalk]

Returns the amount of material, i.e., the number of liters, that the FluidSource designated by &lt;Path&gt; produced.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatAmount → real
```

Return Value

The return value has the data type real .

Example

print MyFluidSource.StatAmount

See also

Tab Statistics

#### Attributes of the FluidSource

\_Attributes of the FluidSource

The FluidSource provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyFluidSource.OutflowRate := 1
print MyFluidSource.OutflowRate
posit := MyStation.Cont.XPos
```

##### Material [SimTalk] - FluidSource

Sets the name of the material which the FluidSource designated by &lt;Path&gt; is to produce.

Remarks

**Note**

What you enter as the Material depends on the setting you selected as the MaterialSelection .

The name of the material has to be defined in the MaterialsTable .

Type

Attribute

Syntax

**&lt; Path &gt;.Material:string**

Assignment Value

For the setting Constant you can assign a value of data type string .

For the settings Sequence Cyclical and Sequence you can assign a value of data type any . This can either be a DataTable of data type object or the path to a DataTable .

You can specify:

- "Constant" : The FluidSource produces a single type of material only. Specify the name of material with the attribute Material .
- "Sequence cyclical" : The FluidSource produces the materials in the sequence and with the amount in the sequence in which you enter them into the Sequence Table .

Once the FluidSource has processed the entire sequence, it starts processing the information in the table again starting at the beginning of the sequence.

Specify the name of Sequence Table with the attribute Material .

- "Sequence" : The FluidSource produces the materials in the sequence and with the amount in the sequence in which you enter them into the Sequence Table .

As opposed to Sequence Cyclical , the setting Sequence processes the sequence only once, not repeatedly.

Specify the name of Sequence Table with the attribute Material .

- "Sequence table" : Define the materials, which the FluidSource is to produce in the sequence table .

You can specify:

- The name of the Material , for example StandardMaterial , Milk , Sugar , Cocoa , etc.
- The Amount in liters of the Material that the FluidSource is to produce.

**Examples**

```simtalk
MyFluidSource.Material := "MyMaterial"
MyFluidSource.MaterialSelection := "Sequence"
MyFluidSource.Material := .UserObjects.MySequenceTable
```

**See also**

Material [text box] - FluidSource

Materials Table [FluidSource]

MaterialSelection [SimTalk]

##### MaterialSelection [SimTalk]

Sets how the FluidSource designated by &lt;Path&gt; selects the material it produces.

Remarks

**Note**

Depending on what you select here, the setting Material either defines the Material itself or the path to the Sequence Table .

Type

Attribute

Syntax

&lt; Path &gt;.MaterialSelection:string

Assignment Value

For the setting Constant you can assign a value of data type string .

For the settings Sequence Cyclical and Sequence you can assign a value of data type any . This can either be a DataTable of data type object or the path to a DataTable .

You can specify:

- "Constant" : The FluidSource produces a single type of material only. Specify the name of material with the attribute Material .
- "ConstSequence cyclical" : The FluidSource produces the materials in the sequence and with the amount in the order in which you enter them into the Sequence Table .

Once the FluidSource has processed the entire sequence, it starts processing the information in the table again starting at the beginning of the sequence.

Specify the name of Sequence Table with the attribute Material

- "Sequence" : The FluidSource produces the materials in the sequence and with the amount in the order in which you enter them into the Sequence Table .

As opposed to Sequence Cyclical , the setting Sequence processes the sequence only once, not repeatedly. If the sequence is processed once, the FluidSource does not produce any additional materials.

Specify the name of Sequence Table with the attribute Material

**Example**

```simtalk
MyFluidSource.MaterialSelection := "Sequence"
MyFluidSource.Material := .UserObjects.MySequenceTable
```

SimTalk

Material [SimTalk] - FluidSource

See also

Material Selection [drop-down list]

Material [text box] - FluidSource MaterialsTable [SimTalk] - FluidSource Sets the MaterialsTable which contains the data of the different materials which the FluidSource designated by &lt;Path&gt; can produce.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialsTable:path

Assignment Value

You can assign a value of data type path .

Example

MyFluidSource.MaterialsTable := MyMaterialsTable

See also

Materials Table [FluidSource]

##### OutflowRate [SimTalk] - FluidSource

Sets the outflow rate with which the material flows out of the FluidSource designated by &lt;Path&gt;.

Remarks

The material then flows off through objects of type Pipe to the next object in the flow of materials. The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes permits this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

Type

Attribute

Syntax

```simtalk
< Path >.OutflowRate:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyFluidSource.OutflowRate := 1
```

See also

Outflow Rate [FluidSource]

Pipe

#### FluidDrain

### FluidDrain

Use the FluidDrain to define the ingredients and the products to be processed in the plant.

<!-- image -->

The FluidDrain removes the free-flowing materials, which the FluidSource introduced into the plant, from the plant after they have been mixed and processed. It differentiates the materials by their names.

To change the length of the graphic and the anchor points of the FluidDrain , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

To show a tooltip with information about the FluidDrain , hover with the mouse over it.

Add the Object to the Simulation Model

To add the FluidDrain to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids

&gt; FluidDrain on the Home ribbon tab.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

#### FluidSource

Simulate Free-flowing Materials and Fluids

#### Dialog Box of the FluidDrain

Dialog Box of the FluidDrain

Double-click the icon of the FluidDrain to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

##### Tab Attributes

- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Shift Calendar [FluidDrain]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the FluidDrain works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the objects into the list of the objects on the tab Resources of the ShiftCalendar .

SimTalk

**ShiftCalendarObject [SimTalk] - material flow objects**

See also

ShiftCalendar [object]

Associated Shift Calendar

Select Object [for controls]

**Current Inflow Rate [FluidDrain]**

###### Current Inflow Rate [FluidDrain]

Shows the Current Inflow Rate , i.e., the amount of liters of the material which flows into the FluidDrain in a second and which it in turn drains from the plant.

<!-- image -->

SimTalk

CurrentInFlowrate [SimTalk]

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Statistics

###### Tab Statistics [FluidDrain]

In addition to the resource statistics values that are described under the Tab Statistics , the tab Statistics of the FluidDrain shows these values.

| Item English        | Description                                                                                                                                                                           | Item German          |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Total Throughput    | Shows the amount of material that the FluidDrain drained from the plant.                                                                                                              | Gesamtdurchsatz      |
| Throughput per Hour | Shows the amount of material that the FluidDrain drained from the plant in an hour while the FluidDrain was available.                                                                | Durchsatz pro Stunde |
| Throughput per Day  | Shows the amount of material that the FluidDrain drained from the plant in a day while the FluidDrain was available. This is the value of the throughput per hour multiplied with 24. | Durchsatz pro Tag    |
| Maximum Flow Rate   | Shows the maximum flow rate ,i.e., the amount of liters of the material in a second that flowed through the FluidDrain .                                                              | Maximale Flußrate    |

**Tab Statistics [FluidDrain]**

<!-- image -->

###### Detailed Statistics Table [FluidDrain]

To open the Detailed Statistics Table , click this button.

<!-- image -->

The Detailed Statistics Table itemizes the materials , which the FluidDrain drained from the plant.

<!-- image -->

The table contains this statistical data:

<!-- image -->

| Name       | Description                                                                        |
|------------|------------------------------------------------------------------------------------|
| Material   | Shows the name of the material that the FluidDrain drained from the plant.         |
| Throughput | Shows the total amount of the material that the FluidDrain drained from the plant. |

**SimTalk**

typeStatistics [SimTalk] - FluidDrain

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

View Menu The commands are described under the View Menu . SimTalk

updateDialog [SimTalk]

##### Tools Menu

The commands are described under the Navigate Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the FluidDrain**

#### Methods of the FluidDrain

The FluidDrain provides:

- The method typeStatistics [SimTalk] - FluidDrain .
- The Methods of the Fluid Objects .
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

typeStatistics [SimTalk] - FluidDrain

Returns the Detailed Statistics Table of the FluidDrain designated by &lt;Path&gt; and writes it into a table.

Remarks

The table shows these values:

| Name       | Description                                                                        |
|------------|------------------------------------------------------------------------------------|
| Material   | Shows the name of the material that the FluidDrain drained from the plant.         |
| Throughput | Shows the total amount of the material that the FluidDrain drained from the plant. |

Type

Method

Syntax

&lt; Path &gt;.typeStatistics(TypeStatisticsTable:table)

Parameter

The parameter TypeStatisticsTable of data type table designates the name of the table.

Examples

```simtalk
var MyFluidDrainStatisticsTable: table
MyFluidDrain.typeStatistics(MyFluidDrainStatisticsTable)
```

MyFluidDrain.typeStatistics(MyFluidDrainStatisticsTable)

See also

Detailed Statistics Table [FluidDrain]

#### Read-Only Attributes of the FluidDrain

\_Read-Only Attributes of the FluidDrain

The FluidDrain provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of the Fluid Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print FluidDrain.StatMaxFlowRate

##### StatMaxFlowRate [SimTalk]

StatMaxFlowRate [SimTalk]

Returns the maximum flow rate of the FluidDrain designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatMaxFlowRate → real

Return Value

The return value has the data type real .

Is the amount of liters of material that flowed into the FluidDrain per second.

Example

print MyFluidDrain.StatMaxFlowRate

See also

Tab Statistics [FluidDrain]

##### StatThroughput [SimTalk] - FluidDrain

Returns the amount of material that the FluidDrain designated by &lt;Path&gt; drained from the plant.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughput → real

Return Value

The return value has the data type real .

The throughput is measured in liters.

Example

print MyFluidDrain.StatThroughput

See also

Tab Statistics [FluidDrain]

StatThroughputPerDay [SimTalk] - FluidDrain

Returns the amount of material that the FluidDrain designated by &lt;Path&gt; drained from the plant during a day while the FluidDrain was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughputPerDay → real

Return Value

The return value has the data type real .

This is the value of the throughput per hour multiplied with 24.

The throughput is measured in liters.

Example

print MyFluidDrain.StatThroughputPerDay

See also

Tab Statistics [FluidDrain]

##### StatThroughputPerHour [SimTalk] - FluidDrain

Returns the amount of material that the FluidDrain designated by &lt;Path&gt; drained from the plant in an hour while the FluidDrain was available.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughputPerHour → real

Return Value

The return value has the data type real .

The throughput is measured in liters.

Example

print MyFluidDrain.StatThroughputPerHour

See also

Tab Statistics [FluidDrain]

##### Attributes of the FluidDrain

Attributes of the FluidDrain

The FluidDrain provides:

- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

#### Tank

### Tank

Use the Tank to temporarily store a single material before or after processing. The material can flow into the Tank from several predecessors and can flow out of the Tank to several successors.

**Icon**

<!-- image -->

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyFluidDrain.Pause := true
print MyFluidDrain.Pause
posit := MyStation.Cont.XPos
```

**Description**

The Tank can only accommodate a single type of material at any one time. The inflow of the new material is blocked until the Tank is empty, so you cannot let another material flow into the Tank before it is empty all the way.

To show a tooltip with information about the Tank , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Tank , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Tank to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt;

Tank on the Home ribbon tab.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

<!-- image -->

**See also**

Simulate Free-flowing Materials and Fluids

Configure the Tanks Storing the Materials

#### Dialog Box of the Tank

Dialog Box of the Tank

Double-click the icon of the Tank to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

- Select the object in the model and press the spacebar .

Tab Attributes

Tab Attributes

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

The tab Attributes provides the settings listed in the table of contents to the left.

**Outflow Rate [Tank]**

###### Outflow Rate [Tank]

Type in the Outflow Rate with which the material flows out of the Tank and flows through the objects of type Pipe to the next object in the flow of materials.

The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes permits this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

**Note**

Plant Simulation shows error messages if the Outflow Rate of an empty Tank is greater than the Inflow Rate or if the inflow rate of a full Tank is greater than the Outflow Rate . Do not ignore these error messages, but create Sensors and program Methods which handle these situations. The Sensors have to prevent the Tank from becoming full or empty respectively by opening or closing the connected Pipes .

**SimTalk**

OutflowRate [SimTalk] - Tank

###### Volume [Tank]

Type in the Volume of the Tank , i.e. the space that the ingredient occupies within the tank.

SimTalk

Volume [SimTalk] - Tank

**Shift Calendar [Tank]**

###### Shift Calendar [Tank]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the Tank works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

**ShiftCalendarObject [SimTalk] - material flow objects**

See also

ShiftCalendar [object]

Associated Shift Calendar

Select Object [for controls]

###### Current Material [Tank]

Shows the name of the Current Material that is located in the Tank .

**Note**

The Tank can only accommodate a single type of material at any one time. The inflow of the new material is blocked until the Tank is empty, so you cannot let another material flow into the Tank before it is empty all the way.

**Note**

The name of the current material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**SimTalk**

CurrentMaterial [SimTalk] - Tank

**Current Fill Level [Tank]**

###### Current Fill Level [Tank]

Shows the Current Fill Level of the material in the Tank .

In 3D the Tank shows the current fill level on the outflow side.

<!-- image -->

**SimTalk**

CurrentFillLevel [SimTalk] - Tank

###### Current Amount [Tank]

Shows the Current Amount of the material that is located in the Tank .

SimTalk

CurrentAmount [SimTalk] - Tank

<!-- image -->

Current Inflow Rate [Tank]

Shows the Current Inflow Rate , i.e., the amount of liters of the material which flows into the Tank in a second.

SimTalk

CurrentInFlowrate [SimTalk]

###### Current Inflow Rate [Tank]

###### Current Outflow Rate [Tank]

Shows the Current Outflow Rate , i.e., the amount of liters of the material that flows out of the Tank in a second.

<!-- image -->

###### Sensors

**Sensors [Tank]**

To create sensors in the Tank , click Sensors .

<!-- image -->

The button opens the dialog Sensor List , where you create new sensors or modify or delete existing sensors.

To create a new sensor, click New

.

<!-- image -->

<!-- image -->

To edit the settings of the sensor, click Edit or double-click the name of the sensor in the sensor list.

To delete the sensor, which you selected in the list of sensors, click Delete

**For the Tank you can:**

- Select if the Position of the sensor in the Tank is relative or absolute .
- Select if sensor is to be triggered if the amount of material has Exceeded the position of sensor.
- Select if sensor is to be triggered if the amount of material is below the position, i.e., has Underrun it.
- Select or create the Control that the sensor triggers.

<!-- image -->

.

**Sensors [Tank]**

<!-- image -->

<!-- image -->

<!-- image -->

**See also**

\_Methods of the Sensors of the Tank

\_Attributes of the Sensors of the Tank

**Position [Tank]**

Select the type of the Position of the sensor in the Tank from the drop-down list. Then, type the position of the sensor into the text box Position .

- Relative : Type in a value between 0 and 1 , i.e., between 0 percent and 100 percent. Plant Simulation shows 0..1 as unit.
- Absolute : Type in a value between 0 and the Volume you specified. Plant Simulation shows l for liters as unit.

<!-- image -->

<!-- image -->

<!-- image -->

**SimTalk**

Position [SimTalk] - Tank

**Position [Tank]**

**PositionType [SimTalk]**

**Exceeded [check box]**

To trigger the sensor if the amount of material in the Tank has Exceeded the amount, i.e., is located above the sensor position, select this check box.

<!-- image -->

**SimTalk**

**Exceeded [SimTalk]**

**Underrun [check box]**

**Underrun [check box]**

To trigger the sensor if the amount of material in the Tank has Underrun the amount, i.e.,is located below the sensor position, select this check box.

<!-- image -->

**SimTalk**

**Underrun [SimTalk]**

**Control [Tank]**

Click the ellipsis button and select the Method in the dialog Select Object . Type in the source code of the Control , which the sensor calls.

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

The standard sensor control as a user-defined attribute looks like this:

<!-- image -->

**Control [Tank]**

**Parameters**

- As soon as the sensor calls this Method , it passes the Sensor-ID as an optional parameter. If the Method expects a parameter of data type integer , the sensor passes the Sensor-ID to the Method . If you do not specify an integer parameter, the Method will be called without a parameter.
- The optional parameter Exceeded of data type boolean shows the user if the sensor position is Exceeded or Underrun .

Once you enter a Sensor Control , the context menu of the object in the Frame shows the command Controls . You can then select the name of the sensor control on the submenu to edit it.

SimTalk

sensorID ( sensorID ). Control [SimTalk] - senor, Tank

ID [SimTalk] - Tank

See also

Select Object [for controls]

Tab Times

Define the Set-up Time as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Set-up Time [general description]

SetupTime [SimTalk] - fluid objects

Select the Set-Up Time

**Tab Failures**

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Statistics [Tank]

In addition to the values described under the Tab Statistics the tab Statistics of the Tank shows this object-specific value.

| Item English         | Description                                                                                                                                        | Read-only attribute                 | Item German       |
|----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|-------------------|
| Total Throughp ut    | Shows the amount of material that flowed through the Tank .                                                                                        | StatDeleted [SimTalk] - Drain       | Gesamtdu rchsatz  |
| Relatively Empty     | Shows the portion of the statistics collection period during which the Tank was Empty in relation to the time during which the Tank was available. | StatRelativeEmpty Portion [SimTalk] | Relativ leer      |
| Relatively Full      | Shows the portion of the statistics collection period during which the Tank was full in relation to the time during which the Tank was available.  | StatRelativeFullPor tion [SimTalk]  | Relativ voll      |
| Relative Occupatio n | Shows the sum of all dwelling times of all materials during the statistics collection period during which the Tank was not paused and not failed.  | Name [SimTalk] - MUs                | Relative Belegung |

<!-- image -->

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

Processing Importer

Set-up Importer

Failure Importer

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The View Menu provides commands to access its functions.

The View Menu also provides commands pertaining to the Transport Importer .

| Exporters [on View menu]   | Unavailable Services [on View menu]   |
|----------------------------|---------------------------------------|
| Services [on View menu]    | Associated Workplaces [on View menu]  |

See also

View Menu [general description]

Transport Importer

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Tank**

#### Methods of the Tank

The Tank provides:

- The General Methods of the Tank .
- The Methods of the Sensors of the Tank .
- The Methods of the Fluid Objects .
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

General Methods of the Tank

General Methods of the Tank

The Tank provides the general method setCurrentContent .

###### setCurrentContent [SimTalk] - Tank

Sets the Current Amount of the material in the Tank designated by &lt;Path&gt;.

Remarks

The new content replaces the previous content.

**Note**

Typically, you set the initial state of the object with the method setCurrentContent .

Type

Method

Syntax

```simtalk
< Path >.setCurrentContent(Amount:real[, Material:string, MaterialsTable:path])
```

**Parameters**

- The parameter Amount of data type real designates the amount of the material.
- The optional parameter Material of data type string designates the material as such.
- The optional parameter MaterialsTable of data type path designates the path to the MaterialsTable .

**Note**

If the Tank already contains a material, you can just enter the new Amount as a single parameter. Otherwise, you also have to specify the Material and the MaterialsTable .

**Examples**

Tank1.setCurrentContent(3, "MyProduct", .Fluids.MaterialsTable)

```simtalk
MyTank.setCurrentContent(5) -- MyTank already contains a material
```

**See also**

**MaterialsTable**

##### Methods of the Sensors of the Tank

Methods of the Sensors of the Tank

\_Methods of the Sensors of the Tank

The Tank provides the methods listed in the table of contents to the left for sensors.

See also

\_Attributes of the Sensors of the Tank

###### createSensor [SimTalk] - Tank

Creates a new sensor for the Tank designated by &lt;Path&gt;.

Type

Method

Syntax

```simtalk
< >.createSensor([Position:real, Control:method, Exceeded:boolean,
Path Underrun:boolean, PositionType:string]) → integer
```

**Parameters**

The sensor itself is defined by these parameters:

- The optional parameter Position of data type real sets the relative position.
- The optional parameter Control of data type method designates the name of the Method object that the sensor triggers.

You can specify the name of the method as a string , i.e., "myMethod" or you can specify &amp;myMethod .

- The optional parameter Exceeded of data type boolean sets if the sensor is going to be triggered when the amount of material in the Tank has exceeded, i.e., is located above the sensor position ( true ) or not ( false ).
- The optional parameter Underrun of data type boolean sets if the sensor is going to be triggered once the amount of material in the Tank has underrun, i.e., is located below the sensor position ( true ) or not ( false ).
- The optional parameter PositionType of data type string designates the position type of the sensor: Relative or Absolute .

**Return Value**

The return value has the data type integer .

It is the unique number of the sensor. You can use this number to access the sensor.

**Example**

```simtalk
var ID1,ID2: integer
ID1 := MyTank.createSensor(0.5,"SensorCtrl",true,false)
ID2 := MyTank.createSensor(0.7,&myMethod,false,true)
ID3 := MyTank.createSensor(3,"SensorCtrl",true,false,"absolute")
```

SimTalk

deleteSensor [SimTalk] - Tank

See also

Sensors [Tank]

\_Attributes of the Sensors of the Tank deleteSensor [SimTalk] - Tank Deletes the sensor from the Tank designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.deleteSensor(SensorID:integer)

Parameter

The parameter SensorID of data type integer designates the SensorID .

Example

MyTank.deleteSensor(2)

SimTalk

createSensor [SimTalk] - Tank

sensorID [SimTalk] - Tank

See also

Sensors [Tank]

Delete [sensor]

existsSensorID [SimTalk] - Tank

Returns if the specified sensor exists (true) or does not exist (false) in the Tank designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.existsSensorID(SensorID:integer) → boolean

Parameter

The parameter SensorID of data type integer designates the SensorID .

Return Value

The return value has the data type boolean .

Example

print MyTank.existsSensorID(2)

SimTalk

sensors.ID [SimTalk] - Tank

sensorID [SimTalk] - Tank

See also

Sensors [Tank]

sensorID [SimTalk] - Tank

Returns the designated sensor of the Tank designated by &lt;Path&gt;.

Remarks

The methods sensorNo(SensorID:integer) and sensorID(SensorID:integer) may reference different sensors.

Type

Method

Syntax

```simtalk
< Path >.sensorID(SensorID:integer) → any
```

Parameter

The parameter SensorID of data type integer designates the unique Sensor-ID which Plant Simulation assigns when you create the sensor.

Return Value

The return value has the data type any .

Example

```simtalk
MyTank.SensorID(3).Exceeded := true
if MyTank.SensorID(3).Exceeded = true then ?.EntranceLocked := true
end
```

**SimTalk**

sensors.ID [SimTalk] - Tank

sensorNo [SimTalk] - Tank

deleteSensor [SimTalk] - Tank

existsSensorID [SimTalk] - Tank

See also

Sensors [Tank]

###### sensorNo [SimTalk] - Tank

Returns a sensor of the Tank designated by &lt;Path&gt; whose unique identifier you do not know.

Remarks

The methods sensorNo(SensorNumber:integer) and sensorID(SensorID:integer) may reference different sensors.

Type

Method

Syntax

```simtalk
< Path >.sensorNo(SensorNumber:integer) → object
```

Parameter

The parameter SensorNumber of data type integer may be a value between 1 and the number of sensors. Which sensor Plant Simulation returns may change during the simulation, i.e., if existing sensors are deleted. Thus only use the method sensorNo if a method call iterates through all sensors of the object.

Return Value

The return value has the data type object .

Example

```simtalk
MyTank.sensorNo(1).Underrun := true
```

SimTalk

sensorID [SimTalk] - Tank

See also

Sensors [Tank]

###### sensors.ID [SimTalk] - Tank

sensors.ID [SimTalk] - Tank

Returns the specified sensor of the Tank designated by &lt;Path&gt;.

Type

Method

Syntax

< Path >.sensors.ID(<Number>) → any

Return Value

The return value has the data type any .

The number after the ID designates the unique identifier which Plant Simulation assigns when you create the sensor.

Examples

```simtalk
MyTank.sensors.ID3.Front := true
var sensor := MyTank.sensors.ID2
sensor.Front := true
```

SimTalk

sensorID [SimTalk] - Tank

existsSensorID [SimTalk] - Tank

See also

Sensors [Tank]

New [sensor]

#### Read-Only Attributes of the Tank

Read-Only Attributes of the Tank

The Tank provides:

- The \_General Read-Only Attributes of the Tank
- The \_Read-Only Attributes of the Sensors of the Tank
- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print Tank.Full
```

General Read-Only Attributes of the Tank

\_General Read-Only Attributes of the Tank

The Tank provides the general read-only attributes listed in the table of contents to the left.

CurrentAmount [SimTalk] - Tank

Returns the Current Amount of the material in the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentAmount → real

Return Value

The return value has the data type real .

The current amount is measured in liters.

Example

print MyTank.CurrentAmount

See also

Current Amount [Tank]

CurrentFillLevel [SimTalk] - Tank

Returns the Current Fill Level of the material in the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentFillLevel → real

Return Value

The return value has the data type real .

The current amount is measured in percent.

Example

print MyTank.CurrentFillLevel

See also

Current Fill Level [Tank]

###### CurrentMaterial [SimTalk] - Tank

Returns the Current Material that is located in the Tank designated by &lt;Path&gt;.

Remarks

The Tank can only accommodate a single type of material at any one time. The inflow of the new material is blocked until the Tank is empty, so you cannot let another material flow into the Tank before it is empty all the way.

**Note**

The name of the current material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such an case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare strings in an case-insensitive manner with the ~= operator, compare Relational Operators .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentMaterial → string

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type string .

Example

print MyTank.CurrentMaterial

**See also Current Material [Tank] Relational Operators**

Empty [SimTalk] - Tank

Returns if the Tank designated by &lt;Path&gt; is Empty (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Empty → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyTank.Empty Full [SimTalk] - Tank Full [SimTalk] - Tank Returns if the Tank designated by &lt;Path&gt; is Full (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Full → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyTank.Full StatRelativeOccupation [SimTalk] - Tank Returns the Relative Occupancy of the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatRelativeOccupation → real

Return Value

The return value has the data type real .

Example

print MyTank.StatRelativeOccupation

See also

Tab Statistics [Tank]

StatThroughput [SimTalk] - Tank

StatThroughput [SimTalk] - Tank

Returns the Throughput , i.e., the amount of material that flowed through the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.StatThroughput → real

Return Value

The return value has the data type real .

The throughput is measured in liters.

Example

print MyTank.StatThroughput

See also

Tab Statistics [Tank]

Read-Only Attributes of the Sensors of the Tank

\_Read-Only Attributes of the Sensors of the Tank

The Tank provides the read-only attributes listed in the table of contents to the left for sensors.

See also

\_Attributes of the Sensors of the Tank

###### ID [SimTalk] - Tank

Returns the unique identifier of a sensor of the Tank designated by &lt;Path&gt;, allowing you to access it.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Sensor.ID → integer
```

Return Value

The return value has the data type integer .

Example

```simtalk
// Deletes all sensors of the Tank that are triggered // when the amount of material exceeds the sensor position.
for i := MyTank.numSensors downto 1
	if MyTank.sensorNo(i).Exceeded = true
		sensorID := MyTank.sensorNo(i).ID
		MyTank.deleteSensor(sensorID)
	end
next
```

SimTalk

sensorID [SimTalk] - Tank

See also

Sensors [Tank]

NumSensors [SimTalk] - Tank

Returns the number of sensors defined for the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.NumSensors → integer

Return Value

The return value has the data type integer .

Example

print MyTank.NumSensors

See also

Sensors [Tank]

Origin [SimTalk] - Tank

Returns the origin of the sensor of the Tank designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Sensor.Origin → integer
```

Return Value

The return value has the data type integer .

If the sensor does not have an origin, it returns VOID.

Example

print MyTank.Sensors.id1.Origin

See also

Sensors [Tank]

##### Attributes of the Tank

Attributes of the Tank

The Tank provides:

- The \_General Attributes of the Tank .
- The \_Attributes of the Sensors of the Tank .
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyTank.OutflowRate := 1
print MyTank.OutflowRate
posit := MyStation.Cont.XPos
```

##### General Attributes of the Tank

###### \_General Attributes of the Tank

The Tank provides the general attributes listed in the table of contents to the left.

OutflowRate [SimTalk] - Tank

Sets the Outflow Rate of the material which the Tank designated by &lt;Path&gt; stores.

Remarks

The Outflow Rate is the amount of liters of the material that flows off in a second.

The material then flows off through objects of type Pipe to the next object in the flow of materials.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes permits this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

**Note**

Plant Simulation outputs error messages if the Outflow Rate of an empty Tank is greater than the Inflow Rate or when the Inflow Rate of a full Tank is greater than the Outflow Rate . Do not ignore these error messages but create Sensors and program Methods which handle these situations. The Sensors have to prevent the Tank from becoming full or empty respectively by opening or closing the connected Pipes .

Type

Attribute

Syntax

```simtalk
< Path >.OutflowRate:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyTank.OutflowRate := 1
```

###### OutflowRate [SimTalk] - Tank

See also

Outflow Rate [Tank]

Volume [SimTalk] - Tank

Sets the Volume , i.e., the amount of the ingredient which the Tank designated by &lt;Path&gt; can hold.

Type

Attribute

Syntax

```simtalk
< Path >.Volume:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyTank.Volume := 10
```

See also

Volume [Tank]

Attributes of the Sensors of the Tank

\_Attributes of the Sensors of the Tank

The Tank provides he attributes listed in the table of contents to the left for sensors.

See also

\_Methods of the Sensors of the Tank

###### Control [SimTalk] - senor, Tank

Control [SimTalk] - senor, Tank

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plants Simulation runs the Control when the sensor of the Tank designated by &lt;Path&gt; is triggered. A value, which you assign, has to be the reference to a Method ( object ) or the name of the Method .

As soon as the sensor calls this Method , it passes the Sensor-ID as optional parameter. If the Method expects an integer parameter, the sensor passes the Sensor-ID to the Method . If you do not enter an integer parameter, the Method will be called without a parameter.

The optional parameter Exceeded of data type boolean shows the user if the sensor position is Exceeded or Underrun .

The standard sensor control as a user-defined attribute looks like this:

<!-- image -->

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Control:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyTank.Sensors.ID2.Control := &mySensorCtrl
MyTank.Sensors.ID2.Control := "mySensorCtrl"
```

**See also**

Control [Tank]

Sensor-ID

**Exceeded [SimTalk]**

###### Exceeded [SimTalk]

Sets if the sensor is to be triggered if the amount of material in the Tank designated by &lt;Path&gt; has Exceeded , i.e., is located above the sensor position ( true ) or not ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Sensors.ID<Number>.Exceeded:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTank.Sensors.id1.Exceeded := true
if Exceeded = true then ?.EntranceLocked := true
end
```

See also

Exceeded [check box]

Position [SimTalk] - Tank

Sets the Position of the sensor on the Tank designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Sensors.ID&lt;Number&gt;.Position:real

Assignment Value

You can assign a value of data type real .

The values you can specify depend on the PositionType :

- For relative you can specify a value between 0 and 1 , i.e., between 0 percent and 100 percent, .
- For abolute you can specify a value between 0 and the Volume you specified.

**Example**

```simtalk
MyTank.Sensors.id2.Position := 0.1
```

SimTalk

PositionType [SimTalk]

Volume [SimTalk] - Tank

See also

Position [Tank]

Volume [Tank]

###### PositionType [SimTalk]

PositionType [SimTalk]

Sets the Position Type of the sensor on the Tank designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.Sensors.ID&lt;Number&gt;.PositionType:string

Assignment Value

You can assign a value of data type string .

You can specify "absolute" or "relative" .

Examples

MyTank.Sensors.ID2.PositionType:= "absolute"

MyTank.Sensors.ID1.PositionType:= "relative"

See also

Position [Tank]

###### Underrun [SimTalk]

Sets if the sensor is to be triggered if the amount of material in the Tank designated by &lt;Path&gt; has Underrun , i.e., is located below the sensor position ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Sensors.ID&lt;Number&gt;.Underrun:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyTank.Sensors.id1.Underrun := true
```

See also

Underrun [check box]

**Mixer**

### Mixer

Use the Mixer to transmute the ingredients of the process into an intermediate or a finished product by mixing them.

Icon

<!-- image -->

Description

The ingredients can flow into the Mixer simultaneously from several preceding FluidSources or Tanks .

#### Mixer

- If you defined the ingredients for the product in the MaterialsTable , the Mixer only uses the defined ingredients. As soon as the respective amount of these ingredients is present in the mixing container, the Mixer starts mixing them.
- If you did not define ingredients for the product, the Mixer takes all materials from the connected Pipes and starts mixing when the mixing container is full.

Once processing is finished, the product flows out of the Mixer . After the Mixer is empty again, the recovery time starts, which is required to flush and to clean it and to prepare it for the next process.

To show a tooltip with information about the Mixer , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Mixer , click Show Manipulators the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Mixer to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt;

Mixer on the Home ribbon tab.

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

**See also**

Configure the Mixers Transmuting the Materials

Configure the Mixer Which Mixes the Materials

#### Dialog Box of the Mixer

Dialog Box of the Mixer

Double-click the icon of the Mixer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

##### Tab Attributes

- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Outflow Rate [Mixer]

Type in the Outflow Rate with which the material flows out of the object and flows through the objects of type Pipe to the next object in the flow of materials.

The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes enables this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

SimTalk

OutflowRate [SimTalk] - Mixer

**Volume [Mixer]**

###### Volume [Mixer]

Type in the Volume of the Mixer , i.e. the amount of liters that is available for the ingredients or the product respectively within the mixing container.

<!-- image -->

###### Product [text box] - Mixer

Type in the name of the intermediate or of the finished Product , which the Mixer is to produce by mixing the ingredients.

<!-- image -->

Specify the name of this product in the MaterialsTable .

<!-- image -->

If the product consists of more than ten ingredients, Add Additional Ingredients to the MaterialsTable .

**SimTalk**

Product [SimTalk]

**Product Amount [text box]**

###### Product Amount [text box]

Type in the Amount of the intermediate or of the finished Product which the Mixer is to produce by mixing the ingredients.

The default value -1 means that the finished product fully utilizes the volume of the Mixer . The product amount is measured in liters.

**Note**

If the Product Amount differs from the Product Amount which you typed into the MaterialsTable , Plant Simulation adjusts the amounts of the individual ingredients accordingly to ensure that the ratio of the ingredients is retained.

**Note**

If you type in -1 for a recipe into the column Product Amount of the MaterialsTable of the Mixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

SimTalk

ProductAmount [SimTalk]

###### Materials Table [Mixer]

Click the ellipsis button and select the MaterialsTable in the dialog Select Object . The MaterialsTable object contains the data of the different materials which the Mixer can mix.

<!-- image -->

Or select the MaterialsTable in a Frame , drag it to the text box and drop it there.

If you type -1 for a recipe into the column Product Amount of the MaterialsTable of the Mixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

SimTalk

MaterialsTable [SimTalk] - Mixer

See also

MaterialsTable

Select Object [for controls]

**Shift Calendar [Mixer]**

###### Shift Calendar [Mixer]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the Mixer works.

<!-- image -->

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Or select the ShiftCalendar in a Frame , drag it to the text box and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

**ShiftCalendarObject [SimTalk] - material flow objects**

See also

ShiftCalendar [object]

Associated Shift Calendar

Select Object [for controls]

###### Current Fill Level [Mixer]

Shows the Current Fill Level of the mixing container in which the Mixer transmutes the materials.

In 3D the Mixer shows the current fill level of the material on the outflow side.

<!-- image -->

**SimTalk**

CurrentFillLevel [SimTalk] - Mixer

**Current Amount [Mixer]**

###### Current Amount [Mixer]

Shows the Current Amount of product that is located in the mixing container of the Mixer at the moment.

SimTalk

CurrentAmount [SimTalk] - Mixer Current Inflow Rate [Mixer]

Shows the Current Inflow Rate , i.e., the amount of liters of the material which flows into the Mixer in a second.

<!-- image -->

SimTalk

CurrentInFlowrate [SimTalk]

<!-- image -->

###### Current Outflow Rate [Mixer]

Shows the Current Outflow Rate , i.e., the amount of liters of the material that flows out of the Mixer in a second and that flows through objects of type Pipe to the next object in the flow of materials.

SimTalk

CurrentOutFlowrate [SimTalk]

See also

Pipe

**Current Outflow Rate [Mixer]**

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Processing Time [general description]

Set-up Time [general description]

Recovery Time [general description]

Define Processing Times

ProcTime [SimTalk] - Mixer

SetupTime [SimTalk] - fluid objects

RecoveryTime [SimTalk] - Mixer

Select the Set-Up Time

**Tab Failures**

##### Tab Failures

Define failures as described under the Tab Failures .

Tab Controls

Tab Controls

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

You can create a Ingredient Complete [Mixer] .

In addition, you can select the Shift Calendar .

**Ingredient Complete [Mixer]**

###### Ingredient Complete [Mixer]

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the Ingredient Complete Control , which is called when an ingredient of the recipe has completely arrived in the Mixer .

<!-- image -->

With the Ingredient Complete Control you can define/start any actions that need to take place in your simulation model via SimTalk .

The Ingredient Complete Control will also be called if the last ingredient or the last ingredients arrived at the same time at which the Mixer reached the Volume [Mixer] you specified.

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

##### IngredientCompleteCtrl [SimTalk]

**See also**

Select Object [for controls]

**Tab Statistics [Mixer]**

##### Tab Statistics [Mixer]

In addition to the values described under the Tab Statistics the tab Statistics of the Mixer shows these object-specific values.

| Item English      | Description                                                                                                                                   | Read-only attribute                 | Item German      |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|------------------|
| Total Through put | Shows the amount of product that flowed through the Mixer .                                                                                   | StatDeleted [SimTalk] - Drain       | Gesamtdurc hsatz |
| Relativel y Empty | Shows the portion of the statistics collection period during which the Mixer was Empty in relation to the time during which it was available. | StatRelativeEmpty Portion [SimTalk] | Relativ leer     |

<!-- image -->

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

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

The View Menu also provides commands pertaining to the Transport Importer .

| Exporters   | Unavailable Services   |
|-------------|------------------------|
| Services    | Associated Workplaces  |

See also

View Menu [general description]

Transport Importer

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

**Methods of the Mixer**

#### \_Methods of the Mixer

The Mixer provides:

- The methods listed in the table of contents to the left.
- The Methods of the Fluid Objects .
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

**addContent [SimTalk]**

##### addContent [SimTalk]

Adds the specified material to the existing content of the Mixer designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.addContent(Amount:real[, Material:string, MaterialsTable:path])

**Parameters**

- The parameter Amount of data type real designates the amount of material.
- The optional parameter Material of data type string designates the material.

Do not specify the optional parameter Material , to increase the existing amount of the contained (single) educt or the contained product after the mixing operation respectively by the specified amount.

Specify the optional parameter Material to add the specified amount of the new educt to the content in the Mixer during the filling process. After the mixing process the specified amount is added and the specified material replaces the currently existing product.

- The optional parameter MaterialsTable of data type path designates the path to the MaterialsTable .

**Example**

Tank1.addContent(3, "MyProduct", .Fluids.MaterialsTable)

SimTalk

MaterialsTable

##### setCurrentContent [SimTalk] - Mixer

Sets the current content of the material in the Mixer designated by &lt;Path&gt;.

Remarks

The new content replaces the previous content. The content can either be the educt or the product itself.

**Note**

Typically, you set the initial state of the object with the method setCurrentContent .

Type

Method

Syntax

```simtalk
< Path >.setCurrentContent(Amount:real[, Material:string, MaterialsTable:path])
```

**Parameters**

- The parameter Amount of data type real designates the amount of material.
- The optional parameter Material of data type string designates the material as such.
- The optional parameter MaterialsTable of data type path designates the path to the MaterialsTable .

**Note**

If the Mixer already contains a material, you can just enter the new Amount as a single parameter. Otherwise, you also have to specify the Material and the MaterialsTable .

**Examples**

MyMixer.setCurrentContent(3, "MyProduct", .Fluids.MaterialsTable)

Mixer1.setCurrentContent(8) -- Mixer1 already contains a material

**SimTalk**

**MaterialsTable**

#### Read-Only Attributes of the Mixer

\_Read-Only Attributes of the Mixer

The Mixer provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print Mixer.Full
```

CurrentAmount [SimTalk] - Mixer

Returns the Current Amount of the material in the mixing container of the Mixer designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentAmount → real

Return Value

The return value has the data type real .

The current amount is measured in liters.

Example

print MyMixer.CurrentAmount

See also

Current Amount [Mixer]

CurrentFillLevel [SimTalk] - Mixer

Returns the Current Fill Level of the material in the mixing container of the Mixer designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentFillLevel → real

Return Value

The return value has the data type real .

The current amount is measured in percent.

Example

print MyMixer.CurrentFillLevel

See also

Current Fill Level [Mixer]

Empty [SimTalk] - Mixer

Returns if the Mixer designated by &lt;Path&gt; is Empty (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Empty → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyMixer.Empty

See also

Full [SimTalk] - Mixer EntranceOpen [SimTalk] - Mixer Returns if material can enter the Mixer designated by &lt;Path&gt; because of current recovery times (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.EntranceOpen → boolean
```

Return Value

The return value has the data type boolean .

Example

print MyMixer.EntranceOpen

SimTalk

TimeUntilEntranceOpen [SimTalk] - Mixer

See also

Entrance Locked [material flow objects]

Full [SimTalk] - Mixer

Returns if the Mixer designated by &lt;Path&gt; is Full (true) or not (false).

Type

Read-only attribute

Syntax

```simtalk
< Path >.Full → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyMixer.Full

See also

Empty [SimTalk] - Mixer Ready [SimTalk] - Mixer Ready [SimTalk] - Mixer Returns if the Mixer designated by &lt;Path&gt; is done mixing the ingredients (true) or not (false) and Ready for a new mixing process.

Type

Read-only attribute

Syntax

```simtalk
< Path >.Ready → boolean
```

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type boolean .

Example

print MyMixer.Ready StatThroughput [SimTalk] - Mixer Returns the Throughput , i.e., the amount of the product that the Mixer designated by &lt;Path&gt; mixed using the ingredients.

Type

Read-only attribute

Syntax

```simtalk
< Path >.StatThroughput → real
```

Return Value

The return value has the data type real .

The throughput is measured in liters.

Example

```simtalk
print MyMixer.StatThroughput
```

See also

Tab Statistics [FluidDrain]

TimeUntilEntranceOpen [SimTalk] - Mixer

Returns the time until the entrance of the Mixer designated by &lt;Path&gt; opens again after the recovery time has elapsed.

Type

Read-only attribute

Syntax

&lt; Path &gt;.TimeUntilEntranceOpen → real

Return Value

The return value has the data type real .

Example

print MyMixer.TimeUntilEntranceOpen

See also

EntranceOpen [SimTalk] - Mixer

##### Attributes of the Mixer

Attributes of the Mixer

The Mixer provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyMixer.OutflowRate := 1
print MyMixer.OutflowRate
posit := MyStation.Cont.XPos
```

IngredientCompleteCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation executes the Ingredient Complete Control when an ingredient of the recipe has completely arrived in the Mixer designated by &lt;Path&gt;. This way you can define/start any actions that need to take place in your simulation model via SimTalk .

The Ingredient Complete Control will also be called if the last ingredient or the last ingredients arrived at the same time at which the Mixer reached the Volume you specified.

Type

Attribute

Syntax

&lt; Path &gt;.IngredientCompleteCtrl:method

Assignment Value

You can assign a value of data type object/method .

Example

MyMixer.IngredientCompleteCtrl := &amp;myIngredientCompleteCtrl

See also

Ingredient Complete [Mixer]

Volume [Mixer]

##### MaterialsTable [SimTalk] - Mixer

Sets the MaterialsTable which contains the data of the different materials which the Mixer designated by &lt;Path&gt; can mix.

Remarks

If you specify -1 for a recipe in the column Product Amount of the MaterialsTable of the Mixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

Syntax

&lt; Path &gt;.MaterialsTable:path

Assignment Value

You can assign a value of data type path .

Example

MyMixer.MaterialsTable := MyMaterialsTable

See also

Materials Table [Mixer]

OutflowRate [SimTalk] - Mixer

Sets the Outflow Rate of the material which the Mixer designated by &lt;Path&gt; creates.

Remarks

The material then flows off through objects of type Pipe to the next object in the flow of materials.

The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes permits this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

Type

Attribute

Syntax

&lt; Path &gt;.OutflowRate:real

Assignment Value

You can assign a value of data type real .

Example

MyMixer.OutflowRate := 1

See also

Outflow Rate [Mixer]

ProcTime [SimTalk] - Mixer

Sets the duration of the Processing Time of the Mixer designated by &lt;Path&gt;.

Remarks

The Processing Time is the time during which the Mixer transmutes materials.

Type

Attribute

Syntax

&lt; Path &gt;.ProcTime:time

Assignment Value

You can assign a value of data type time .

Example

```simtalk
MyMixer.ProcTime := 1:00:00 // one hour
```

See also

Processing Time [general description]

**Product [SimTalk]**

##### Product [SimTalk]

Sets the name of the intermediate or of the finished Product which the Mixer designated by &lt;Path&gt; is to produce by mixing the ingredients.

Remarks

The name of this Product has to be defined in the MaterialsTable .

Type

Attribute

Syntax

```simtalk
< Path >.Product:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyMixer.Product := "MyProduct"
```

See also

Product [text box] - Mixer

Materials Table [Mixer]

##### ProductAmount [SimTalk]

Sets the amount of the intermediate or of the finished product which the Mixer designated by &lt;Path&gt; is to produce by mixing the ingredients.

Remarks

The default value -1 means that the finished product fully utilizes the volume of the Mixer . The product amount is measured in liters.

**Note**

If the product amount differs from the product amount which you typed into the MaterialsTable , Plant Simulation adjusts the amounts of the individual ingredients accordingly to ensure that the ratio of the ingredients is retained.

**Note**

If you specify -1 for a recipe into the column Product Amount of the MaterialsTable of the Mixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

Type

Attribute

Syntax

&lt; Path &gt;.ProductAmount:real

Assignment Value

You can assign a value of data type real .

Example

MyMixer.ProductAmount := 70

See also

Product Amount [text box]

Materials Table [Mixer]

RecoveryTime [SimTalk] - Mixer

Sets the duration of the Recovery Time of the Mixer designated by &lt;Path&gt;.

Remarks

The Recovery Time is the time which is required to flush and clean the Mixer and to prepare it for the next process.

Type

Attribute

Syntax

&lt; Path &gt;.RecoveryTime:time

Assignment Value

You can assign a value of data type time .

Specify 0 to allow materials to enter continually.

Example

MyMixer.RecoveryTime := 1:00:00

See also

Recovery Time [general description]

Volume [SimTalk] - Mixer

Sets the Volumne that is available for the ingredients or the product respectively in the mixing container of the Mixer designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Volume:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyMixer.Volume := 10
```

See also

Volume [Mixer]

#### ContinuousMixer

### ContinuousMixer

Use the ContinuousMixer to transmute the ingredients of the process into an intermediate or a finished product by mixing them.

Icon

<!-- image -->

Description

The ingredients can flow into the ContinuousMixer simultaneously from several preceding fluid objects.

- The ContinuousMixer only processes fluids if the product and the ingredients information is defined in the MaterialsTable .

- The ContinuousMixer only starts the mixing process once it receives all the materials from the preceding objects in the correct ratio defined in the MaterialsTable .
- If the ratio is incorrect, the mixing process will stop immediately.
- The outflow from the ContinuousMixer starts simultaneously when the inflow starts. The outflow is typically equal to the cumulative inflow, but it can be different when you define the recipe in the MaterialsTable accordingly.

To show a tooltip with information about the ContinuousMixer , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the ContinuousMixer , click Show

**Manipulators**

on the

Edit

ribbon tab or press

<!-- image -->

Add the Object to the Simulation Model

To add the ContinuousMixer to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; ContinuousMixer on the Home ribbon tab.

See also

Continuously Mix Juice and Water

#### Dialog Box of the ContinuousMixer

Dialog Box of the ContinuousMixer

Double-click the icon of the ContinuousMixer to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

M

on the keyboard.

<!-- image -->

##### Tab Attributes

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

<!-- image -->

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings, which the object offers.

The settings are listed in the table of contents to the left.

The shared properties are described under the Tab Attributes .

###### Product [text box] - ContinuousMixer

Type in the name of the intermediate or of the finished Product which the ContinuousMixer is to produce by mixing the ingredients.

<!-- image -->

Specify the name of this product in the MaterialsTable .

<!-- image -->

If the product consists of more than ten ingredients, you can Add Additional Ingredients to the MaterialsTable .

SimTalk

Product [SimTalk] - ContinuousMixer

**Materials Table [ContinuousMixer]**

###### Materials Table [ContinuousMixer]

The MaterialsTable object contains the data of the different materials which the ContinuousMixer can mix.

<!-- image -->

Click the ellipsis button and select the MaterialsTable in the dialog Select Object .

Or select the MaterialsTable in a Frame , drag it to the text box and drop it there.

If you type -1 for a recipe into the column Product Amount of the MaterialsTable of the ContinuousMixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

SimTalk

MaterialsTable [SimTalk] - ContinuousMixer

See also

MaterialsTable

Select Object [for controls]

###### Shift Calendar [ContinuousMixer]

The ShiftCalendar contains the data of the shifts in your installation and controls during which shifts the ContinuousMixer works in the plant.

<!-- image -->

Remarks

Click the ellipsis button and select the ShiftCalendar in the dialog Select Object .

Instead of clicking the ellipsis button, you can also select the ShiftCalendar in a Frame , drag it to the text box, and drop it there.

This automatically enters the object into the list of Objects on the tab Resources of the ShiftCalendar .

SimTalk

ShiftCalendarObject [SimTalk] - material flow objects

See also

ShiftCalendar [object]

Associated Shift Calendar

Select Object [for controls]

**Current Inflow Rate [ContinuousMixer]**

###### Current Inflow Rate [ContinuousMixer]

Shows the Current Inflow Rate , i.e., the amount of liters of the material which flows into the ContinuousMixer in a second.

<!-- image -->

SimTalk

CurrentInFlowrate [SimTalk]

###### Current Outflow Rate [ContinuousMixer]

Shows the Current Outflow Rate , i.e., the amount of liters of the material that flows out of the ContinuousMixer in a second and that flows through objects of type Pipe to the next object in the flow of materials.

SimTalk

CurrentOutFlowrate [SimTalk]

See also

Pipe

<!-- image -->

**Tab Failures**

##### Tab Failures

Define failures as described under the Tab Failures .

Tab Times

Define the Set-up Time as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Select the Set-Up Time

**Tab Statistics [ContinuousMixer]**

##### Tab Statistics [ContinuousMixer]

In addition to the values described under the Tab Statistics , the tab Statistics of the ContinuousMixer shows this object-specific value.

| Item English      | Description                                                           | Read-only attribute           | Item German      |
|-------------------|-----------------------------------------------------------------------|-------------------------------|------------------|
| Total Through put | Shows the amount of product that flowed through the ContinuousMixer . | StatDeleted [SimTalk] - Drain | Gesamtdurc hsatz |

<!-- image -->

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

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

The View Menu also provides commands pertaining to the Transport Importer .

| Exporters   | Unavailable Services   |
|-------------|------------------------|
| Services    | Associated Workplaces  |

See also

View Menu [general description]

Transport Importer

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the ContinuousMixer

Methods of the ContinuousMixer

The ContinuousMixer provides:

- The Methods of the Fluid Objects .
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

#### Read-Only Attributes of the ContinuousMixer

Read-Only Attributes of the ContinuousMixer

The ContinuousMixer provides:

- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print ContinuousMixer.Full

##### Attributes of the ContinuousMixer

#### Attributes of the ContinuousMixer

The ContinuousMixer provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyContinuousMixer.OutflowRate := 1
print MyContinuousMixer.OutflowRate
posit := MyStation.Cont.XPos
```

MaterialsTable [SimTalk] - ContinuousMixer

Sets the MaterialsTable which contains the final product and the details of the ingredients of each FluidSource such as ratio/density/color, which the ContinuousMixer designated by &lt;Path&gt; can mix.

Syntax

&lt; Path &gt;.MaterialsTable:path

Assignment Value

You can assign a value of data type path .

Example

MyContinuousMixer.MaterialsTable := MyMaterialsTable

See also

Materials Table [Mixer] , object

##### Product [SimTalk] - ContinuousMixer

Sets the name of the intermediate or of the finished product which the ContinuousMixer designated by &lt;Path&gt; is to produce by mixing the ingredients.

Remarks

The name of this Product has to be defined in the MaterialsTable .

Type

Attribute

Syntax

&lt; Path &gt;.Product:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyContinuousMixer.Product := "MyProduct"
```

See also

Product [text box] - Mixer

Materials Table [Mixer]

#### Portioner

### Portioner

Use the Portioner to create a mobile object out of a free-flowing product.. You can then connect the Portioner with one of the material flow objects to further process the created MUs .

Icon

<!-- image -->

**Description**

You can think of the Portioner as the counterpart of the DePortioner .

To show a tooltip with information about the Portioner , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Portioner , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the Portioner to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; Portioner on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Portion and Deportion Materials

Simulate Free-flowing Materials and Fluids

Configure the Portioner Pouring the Chocolate Bars

Configure the Portioner Which Portions the Product

#### Dialog Box of the Portioner

Dialog Box of the Portioner

Double-click the icon of the Portioner to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

<!-- image -->

##### Tab Attributes

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

<!-- image -->

###### MU [Portioner]

Click the ellipsis button and select the type of MU into which the Portioner is to transmute the free-flowing material.

You can either use one of the predefined MUs or you can create your own MU for just this purpose.

SimTalk

MUPath [SimTalk]

**Amount per MU [Portioner]**

###### Amount per MU [Portioner]

Type in the total Amount of the material which the Portioner is to transmute into the MU .

<!-- image -->

SimTalk

AmountPerMU [SimTalk] - Portioner

See also

MU [Portioner]

###### Fluid from Predecessor [text box]

Type in the number of the Predecessor object which delivers the fluid material to the Portioner .

<!-- image -->

**Current Amount [Portioner]**

###### Current Amount [Portioner]

Shows the Current Amount of the material that is located in the Portioner at the moment.

SimTalk

CurrentAmount [SimTalk] - Portioner

###### Current Inflow Rate [Portioner]

Shows the Current Inflow Rate , i.e., the amount of liters of the material per second which flows into the Portioner in a second.

SimTalk

CurrentInFlowrate [SimTalk]

**Current Material [Portioner]**

###### Current Material [Portioner]

Shows the name of the Current Material that flows into the Portioner .

**Note**

The name of the current material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are case-insensitive with the ~= operator, compare Relational Operators .

**SimTalk**

CurrentMaterial [SimTalk] - Portioner Tab Times Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Set-up Time [general description]

Select the Set-Up Time

RecoveryTime [SimTalk] - Mixer

SetupTime [SimTalk] - fluid objects

**Tab Failures**

##### Tab Failures

Define failures as described under the Tab Failures .

##### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control and an Exit Control .

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

See also

Select Object [for controls]

Entrance Control [general description]

Exit Control [general description]

Tab Exit

Select to which of its successors the object moves the part to as described under the Tab Exit .

See also

Blocking [exit strategy]

Strategy [material flow objects]

**Tab Statistics**

##### Tab Statistics

The Portioner shows resource statistics as described under the Tab Statistics .

##### Tab Importer

On the Tab Importer you can define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station.

To view Importer Statistics in the Statistics Report , click the object in the Frame , and press F6 ( Show Statistics Report ), or click Show Statistics Report on the Home ribbon tab.

You can also click the object in the Frame with the right mouse button and select Show Statistics Report on the context menu.

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

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

The View menu also provides commands pertaining to the Transport Importer .

| Exporters [on View menu]   | Unavailable Services [on View menu]   |
|----------------------------|---------------------------------------|
| Services [on View menu]    | Associated Workplaces [on View menu]  |

See also

View Menu [general description]

Transport Importer

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

##### Methods of the Portioner

#### Methods of the Portioner

The Portioner provides:

- The Methods of the Fluid Objects .
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

#### Read-Only Attributes of the Portioner

\_Read-Only Attributes of the Portioner

The Portioner provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print Portioner.CurrentAmount CurrentAmount [SimTalk] - Portioner Returns the Current Amount of the fluid in the container of the Portioner designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentAmount → real

Return Value

The return value has the data type real .

The current amount is measured in liters.

Example

print MyPortioner.CurrentAmount

See also

Current Amount [Portioner]

CurrentMaterial [SimTalk] - Portioner

Returns the Current Material that flows into the Portioner designated by &lt;Path&gt;.

Remarks

The name of the current material is not case-sensitive, just like the names of attributes and methods of the objects are not case-sensitive.

To save memory and improve access speed, all places which use such a case-insensitive string point to the same string in main memory. The visible and unexpected result is that the first occurrence of the string defines how the string is written in terms of upper- and lower-casing.

In SimTalk you can compare if strings are a case-insensitive with the ~= operator, compare Relational Operators .

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentMaterial → string

Return Value

The return value has the data type string .

Example

print MyPortioner.CurrentMaterial

See also

Current Material [Portioner]

Relational Operators

**Attributes of the Portioner**

\_Attributes of the Portioner

The Portioner provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyPortioner.AmountPerMU := 10
print MyPortioner.AmountPerMU
posit := MyStation.Cont.XPos
```

AmountPerMU [SimTalk] - Portioner

Sets the Amount of the material in liters which the Portioner designated by &lt;Path&gt; is to transmute into individual MUs .

Type

Attribute

Syntax

&lt; Path &gt;.AmountPerMU:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
MyPortioner.AmountPerMU := 10
```

See also

Amount per MU [Portioner]

##### MUPath [SimTalk]

Sets the type of MU which the Portioner designated by &lt;Path&gt; is to create.

Remarks

You can either use one of the predefined MUs or you can create your own MU for just this purpose.

Type

Attribute

Syntax

&lt; Path &gt;.MUPath:path

Assignment Value

You can assign a value of data type path .

Example

MyPortioner.MUPath := .MUs.Container

See also

MU [Portioner]

**PredecessorNumber [SimTalk]**

##### PredecessorNumber [SimTalk]

Sets the number of the predecessor object which delivers the material to the Portioner designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.PredecessorNumber:integer

Assignment Value

You can assign a value of data type integer .

Example

MyPortioner.PredecessorNumber := 2

See also

Fluid from Predecessor [text box]

**DePortioner**

### DePortioner

Use the DePortioner to empty incoming parts of bulk goods or fluids, create a fluid out of it, and feed the resulting fluids into a Pipe .

Icon

<!-- image -->

Description

We provide three ways of defining the fluid that is to be created:

- By a fixed material and a fixed amount for every MU . For this setting you can enter the Material and the Amount per MU .
- By the MU Name depending on the MU names that are defined in the Mapping Table .
- By the MU Attribute , for which you can enter the Material Attribute and the Amount Attribute of the MU .

When the created fluid flows out of the DePortioner into a Pipe , the MU that delivered it will be deleted. If the outflow of fluids is interrupted, caused by a failure, a pause, or because the successor cannot accept anything at the moment, the Exporters will not be released.

You can, for example, use the DePortioner to empty barrels of fluids or bulk goods, which are then used as ingredients for mixed goods down your production line, and feed the material into Pipes .

You can think of the DePortioner as the counterpart of the Portioner .

To show a tooltip with information about the DePortioner , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Portioner , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the DePortioner to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; DePortioner on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Portion and Deportion Materials

Configure the DePortioner

##### Dialog Box of the DePortioner

Dialog Box of the DePortioner

Double-click the icon of the DePortioner to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.

<!-- image -->

- Select the object in the model and press the spacebar .

Tab Attributes

Tab Attributes

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

The tab Attributes provides the settings listed in the table of contents to the left.

**Outflow Rate [DePortioner]**

###### Outflow Rate [DePortioner]

Type in the Outflow Rate with which the material flows out of the DePortioner after it has emptied the arriving part and flows through the objects of type Pipe to the next object in the flow of materials.

The Outflow Rate is the amount of liters of the material that flows off in a second.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes enables this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

SimTalk

OutflowRate [SimTalk] - DePortioner

###### Fluid Depends On

Select how the DePortioner defines the material and the amount of the fluid that is to be created.

<!-- image -->

- By a Fixed Material and a Fixed Amount : Set the material and the amount per MU in the dialog items Material and Amount per MU .
- By the MU Name : Set the material and the amount per MU in the Mapping Table .
- By the MU Attribute : Set the material and the amount per MU in the dialog items Material Attribute and Amount Attribute . These are user-defined attributes of the MU which you have to create.

<!-- image -->

<!-- image -->

<!-- image -->

Define the name of each material that is to be used in the MaterialsTable .

**SimTalk**

FluidDependsOn [SimTalk]

###### Material [DePortioner]

Type in the name of the Material that the DePortioner creates.

<!-- image -->

It applies if you select Fixed for the setting Fluid Depends On .

<!-- image -->

**SimTalk**

Material [SimTalk] - DePortioner

**Amount per MU [DePortioner]**

###### Amount per MU [DePortioner]

Type in the total amount in liters of the fluid which the DePortioner creates.

<!-- image -->

Amount per MU applies if you select Fixed for the setting Fluid Depends On .

<!-- image -->

**SimTalk**

AmountPerMU [SimTalk] - Portioner

###### Mapping Table

Type in the name of the Mapping Table that contains the MU Name of the arriving MU , and the Material and the Amount of the fluid which the DePortioner creates.

<!-- image -->

The Mapping Table applies if you select MU Name for the setting Fluid Depends On .

<!-- image -->

Or click and select the Mapping Table .

**SimTalk**

MappingTable [SimTalk]

**Material Attribute**

###### Material Attribute

Type in the name of the user-defined Material Attribute which defines the fluid which the DePortioner creates.

It applies if you select MU Attribute for the setting Fluid Depends On .

<!-- image -->

**SimTalk**

AttrNameMaterial [SimTalk]

###### Amount Attribute

Type in the name of the user-defined Amount Attribute , which sets the amount of the fluid which the DePortioner creates.

The Amount Attribute applies if you select MU Attribute for the setting Fluid Depends On .

<!-- image -->

**SimTalk**

AttrNameAmount [SimTalk]

**Materials Table [DePortioner]**

###### Materials Table [DePortioner]

Click the ellipsis button and select the MaterialsTable in the dialog Select Object . The MaterialsTable contains the data of the different materials which the DePortioner can create.

<!-- image -->

Or select the MaterialsTable in a Frame , drag it to the text box and drop it there.

SimTalk

MaterialsTable [SimTalk] - DePortioner

See also

MaterialsTable

Select Object [for controls]

##### Current Amount [DePortioner]

Shows the Current Amount of the fluid that is located in the DePortioner at the moment.

SimTalk

CurrentAmount [SimTalk] - DePortioner

**Current Outflow Rate [DePortioner]**

###### Current Outflow Rate [DePortioner]

Shows the Current Outflow Rate , i.e., the amount of liters of the fluid which flows out of the DePortioner in a second.

<!-- image -->

SimTalk

CurrentOutFlowrate [SimTalk]

Tab Times

Define Times as described under the Tab Times .

Select a distribution from the drop-down list and type the values that this distribution requires into the text box. Plant Simulation shows the parameters along the upper border of the tab. You can also type in a constant time ( Const ).

You can set the type of the distribution and a complete set of parameters with the method setTypeAndAttr .

See also

Recovery Time [general description]

Set-up Time [general description]

Select the Set-Up Time

RecoveryTime [SimTalk] - Mixer

SetupTime [SimTalk] - fluid objects

**Tab Setup**

##### Tab Setup

Define properties for setting the object up as described under the Tab Set-Up .

**See also**

| Set a Station Up   | Set-up Only When Empty   |
|--------------------|--------------------------|
| Set-up For         | Set-up After n Parts     |
| Automatic Set-up   | Set-up Depends On        |

**Tab Failures**

Define failures as described under the Tab Failures .

###### Tab Controls

Click the ellipsis button and select a Method in the dialog Select Object . Type in the source code of the respective control.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

You can create an Entrance Control , an Exit Control , a Set-up Control , and a Pull Control .

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

See also

Select Object [for controls]

Before Actions

Entrance Control [general description]

Exit Control [general description]

Set-up Control

Pull Control [general description]

**Tab Statistics**

**Tab Statistics**

The DePortioner shows resource statistics as described under the Tab Statistics .

Tab Importer [DePortioner]

Define services for processing the parts, for setting the station up for a certain type of part, and for repairing the station on the tab Importer .

To view Importer Statistics in the Statistics Report , do one of the following:

- Select View &gt; Show Statistics Report in the dialog of the object.
- Click the object with the right mouse button in the Frame and select Show Statistics Report or press F6 .
- Click Show Statistics Report on the Home ribbon tab.

<!-- image -->

See also

Tab Importer [general description]

Processing Importer

Set-up Importer

Failure Importer

**Tab User-defined**

**Tab User-defined**

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

The commands are described under the Navigate Menu .

**View Menu**

**View Menu**

The View Menu provides commands to access its functions.

The View menu also provides commands pertaining to the Transport Importer .

| Exporters [on View menu]   | Unavailable Services [on View menu]   |
|----------------------------|---------------------------------------|
| Services [on View menu]    | Associated Workplaces [on View menu]  |

See also

View Menu [general description]

Transport Importer

**Tools Menu**

The commands are described under the Tools Menu .

**Help Menu**

The commands are described under the Help Menu .

##### Methods of the DePortioner

#### Methods of the DePortioner

The DePortioner provides:

- The Methods of the Fluid Objects .
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

##### Read-Only Attributes of the DePortioner

Read-Only Attributes of the DePortioner

The DePortioner provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print DePortioner.CurrentOutFlowrate

##### CurrentAmount [SimTalk] - DePortioner

Returns the Current Amount of the fluid in the DePortioner designated by &lt;Path&gt; at the moment.

Type

Read-only attribute

Syntax

&lt; Path &gt;.CurrentAmount → real

Return Value

The return value has the data type real .

The current amount is measured in liters.

Example

print MyDePortioner.CurrentAmount

See also

Current Amount [DePortioner]

#### Attributes of the DePortioner

\_Attributes of the DePortioner

The DePortioner provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MyDePortioner.AmountPerMU := 10
print MyDePortioner.AmountPerMU
posit := MyStation.Cont.XPos
```

AmountPerMU [SimTalk] - DePortioner

Sets the total amount in liters of the material which the DePortioner designated by &lt;Path&gt; creates.

Remarks

AmountPerMU applies when you select Fixed under Fluid Depends On / FluidDependsOn .

Type

Attribute

Syntax

&lt; Path &gt;.AmountPerMU:real

Assignment Value

You can assign a value of data type real .

Example

MyDePortioner.AmountPerMU := 20

SimTalk

FluidDependsOn [SimTalk]

See also

Amount per MU [DePortioner]

Fluid Depends On

##### AttrNameAmount [SimTalk]

Sets the name of the user-defined Amount Attribute of the MU which defines the amount of the material which the DePortioner designated by &lt;Path&gt; creates.

Remarks

AttrNameAmount applies if you select MU Attribute as the definition method of the setting FluidDependsOn .

Type

Attribute

Syntax

&lt; Path &gt;.AttrNameAmount:string

Assignment Value

You can assign a value of data type string .

Example

MyDePortioner.AttrNameAmount := "Amount"

SimTalk

FluidDependsOn [SimTalk]

See also

Amount Attribute

Fluid Depends On

##### AttrNameMaterial [SimTalk]

Sets the name of the user-defined Material Attribute of the MU, which defines the material which the DePortioner designated by &lt;Path&gt; creates.

Remarks

AttrNameMaterial applies when you select MU Attribute under FluidDependsOn .

Type

Attribute

Syntax

&lt; Path &gt;.AttrNameMaterial:string

Assignment Value

You can assign a value of data type string .

Example

MyDePortioner.AttrNameMaterial := "Material"

See also

FluidDependsOn [SimTalk]

See also

Material Attribute

Fluid Depends On

##### FluidDependsOn [SimTalk]

FluidDependsOn [SimTalk]

Sets how the DePortioner designated by &lt;Path&gt; creates the material and the amount of the fluid.

Remarks

The name of each material that is to be used has to be defined in the MaterialsTable .

Type

Attribute

Syntax

&lt; Path &gt;.FluidDependsOn:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Fixed" : Set the material and the amount per MU under Material / Material and Amount per MU / AmountPerMU .
- "MU Name" : Set the material and the amount per MU under Mapping table / MappingTable .
- "MU Attribute" : Set the material and the amount per MU under Material attribute / AttrNameMaterial and Amount attribute / AttrNameAmount . These are user-defined attributes of the MU which you have to create.

Example

MyDePortioner.FluidDependsOn := "Fixed"

See also

Fluid Depends On

MaterialsTable

##### MappingTable [SimTalk]

Sets the name of the data table that contains the MU Name of the arriving MU, the Material , and the Amount of the fluid, which the DePortioner designated by &lt;Path&gt; creates.

Remarks

MappingTable applies when you select MU Name under FluidDependsOn .

Type

Attribute

Syntax

&lt; Path &gt;.MappingTable:path

Assignment Value

You can assign a value of data type path .

Example

MyDePortioner.MappingTable := MyMappingTable

SimTalk

FluidDependsOn [SimTalk]

See also

Mapping Table

Fluid Depends On Material [SimTalk] - DePortioner Sets the name of the material which the DePortioner designated by &lt;Path&gt; creates.

Remarks

Material applies if you select Fixed under FluidDependsOn .

Type

Attribute

Syntax

&lt; Path &gt;.Material:string

Assignment Value

You can assign a value of data type string .

Example

MyDePortioner.Material := "StandardMaterial"

SimTalk

FluidDependsOn [SimTalk]

See also

Material [DePortioner]

Fluid Depends On

##### MaterialsTable [SimTalk] - DePortioner

Sets the MaterialsTable which contains the data of the different materials which the DePortioner designated by &lt;Path&gt; can create.

Type

Attribute

Syntax

&lt; Path &gt;.MaterialsTable:path

Assignment Value

You can assign a value of data type path .

Example

MyDePortioner.MaterialsTable := MyMaterialsTable

See also

Materials Table [DePortioner]

OutflowRate [SimTalk] - DePortioner

Sets the outflow rate with which the fluid flows out of the DePortioner designated by &lt;Path&gt;.

Remarks

The Outflow Rate is the amount of liters of the material that flows off in a second.

The material then flows off through objects of type Pipe to the next object in the flow of materials.

**Note**

The current Outflow Rate depends on the number of attached Pipes . Let's say you attached two Pipes , then the specified Outflow Rate flows through each one of these Pipes in case the Outflow Rate of the connected Pipes permits this.

If you just want to let the specified amount flow out of the object, attach a single Pipe and split that up into several Pipes later on.

Type

Attribute

Syntax

&lt; Path &gt;.OutflowRate:real

Assignment Value

You can assign a value of data type real .

Example

MyDePortioner.OutflowRate := 1

See also

Outflow Rate [DePortioner]

RecoveryTime [SimTalk] - DePortioner

Sets the duration of the Recovery Time of the DePortioner designated by &lt;Path&gt;.

Remarks

The Recovery Time is the time which is required to flush and clean the DePortioner and prepare it for the next process.

This is the time during which no material will be accepted after the MU exited the object.

Type

Attribute

Syntax

&lt; Path &gt;.RecoveryTime:time

Assignment Value

You can assign a value of data type time .

Specify 0 to allow materials to enter continually.

Example

MyDePortioner.RecoveryTime := 1:00:00

See also

RecoveryTime [SimTalk] - Mixer

#### PatchMatrix

### PatchMatrix

Use the PatchMatrix to connect an entrance pipe with an exit pipe to control the flow of the materials within the plant.

**PatchMatrix**

**Icon**

<!-- image -->

**Description**

Pipes transport free-flowing materials between the objects FluidSource , Tank , Mixer , Portioner , DePortioner , and FluidDrain .

Insert the objects with which you would like to model. Connect the Pipes with Connectors with the PatchMatrix .

<!-- image -->

Double-click the PatchMatrix and change to the tab Attributes . Click Connections and select the respective check boxes to allow materials to flow through these Pipes . The column header contains the incoming pipes, the row header contains the outgoing pipes.

<!-- image -->

To show a tooltip with information about the PatchMatrix , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the Portioner , click Show Manipulators on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the PatchMatrix to your simulation model, click Fluids &gt; DePortioner on the Home ribbon tab.

<!-- image -->

<!-- image -->

See also

Define How the PatchMatrix Fills the Tanks

#### Dialog Box of the PatchMatrix

Dialog Box of the PatchMatrix

Double-click the icon of the PatchMatrix to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Attributes

Tab Attributes

The tab Attributes provides the setting Connections

###### Connections [PatchMatrix]

To show the Pipes that are connected with the PatchMatrix , click this button.

<!-- image -->

Select the check boxes in the respective cells to connect the respective Pipes with each other.

The column header contains the incoming pipes, the row header contains the outgoing pipes.

<!-- image -->

In the example above we connected the entrance pipe named Pipe with the exit pipes Pipe2 and Pipe3 , and Pipe1 with Pipe2 .

If you drag the mouse over the PatchMatrix , the Tooltip shows this.

**Connections [PatchMatrix]**

<!-- image -->

**SimTalk**

getConnectionsForPred [SimTalk] getConnectionsForSucc [SimTalk] resetConnections [SimTalk] setConnections [SimTalk]

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu The commands are described under the View Menu . SimTalk updateDialog [SimTalk]

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The commands are described under the Help Menu .

#### Methods of the PatchMatrix

**\_Methods of the PatchMatrix**

The PatchMatrix provides:

- The methods listed in the table of contents to the left.
- The Methods of the Fluid Objects .
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

##### getConnectionsForPred [SimTalk]

Returns the numbers of the successors of the PatchMatrix designated by &lt;Path&gt; for which a connection from the predecessor exists.

Type

Method

Syntax

```simtalk
< Path >.getConnectionsForPred(Pred:integer) → array
```

Parameter

The parameter Pred of data type integer designates the number of the predecessor.

Return Value

The return value has the data type array .

Example

```simtalk
var c : integer[ ]
c := Patchmatrix.getConnectionsForPred(1)
```

SimTalk

getConnectionsForSucc [SimTalk]

setConnections [SimTalk]

See also

Connections [PatchMatrix]

##### getConnectionsForSucc [SimTalk]

getConnectionsForSucc [SimTalk]

Returns the numbers of the predecessor of the PatchMatrix designated by &lt;Path&gt; for which a connection to the successor exists.

Type

Method

Syntax

```simtalk
< Path >.getConnectionsForSucc(Succ:integer) → array
```

Parameter

The parameter Succ of data type integer designates the number of the successor.

Return Value

The return value has the data type array .

Example

```simtalk
var c : integer[ ]
c := Patchmatrix.getConnectionsForSucc(1)
```

SimTalk

getConnectionsForPred [SimTalk]

setConnections [SimTalk]

See also

Connections [PatchMatrix]

##### resetConnections [SimTalk]

Resets the existing connections of the PatchMatrix designated by &lt;Path&gt; to their predecessors and successors, i.e. it cuts the connections.

Type

Method

Syntax

&lt; Path &gt;.resetConnections

Example

Patchmatrix.resetConnections

SimTalk

setConnections [SimTalk]

See also

Connections [PatchMatrix]

**setConnections [SimTalk]**

##### setConnections [SimTalk]

Establishes the connections between the predecessors and the successors of the PatchMatrix designated by &lt;Path&gt; (connect is true ) or it cuts the connection (connect is false ).

Type

Method

Syntax

```simtalk
< Path >.setConnections(Pred:any, Succ:any, connect:boolean) → array
```

**Parameters**

- The parameter Pred of data type any designates the predecessor(s).

The parameter Pred can either be the number of the predecessor, the name of the predecessor, or an array of predecessor numbers.

- The parameter Succ of data type any designates the successor(s).

The parameter Succ can either be the number of the successor, the name of the successor, or an array of successor numbers.

- The parameter connect of data type boolean sets if the Pipes are going to be connected ( true ) or not ( false ).

**Example**

Patchmatrix.setConnections(1,2,true) Patchmatrix.setConnections(1,[1,2],true) Patchmatrix.setConnections("PipeIn1","PipeOut2",false)

**SimTalk**

getConnectionsForPred [SimTalk]

getConnectionsForSucc [SimTalk]

resetConnections [SimTalk]

See also

Connections [PatchMatrix]

#### Read-Only Attributes of the PatchMatrix

Read-Only Attributes of the PatchMatrix

The PatchMatrix provides:

- The \_Read-Only Attributes of the Fluid Objects .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyPatchMatrix.UUID

#### Attributes of the PatchMatrix

Attributes of the PatchMatrix

The PatchMatrix provides:

- The \_Attributes of the Fluid Objects .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
PatchMatrix.Name := "MyPatchMatrix"
print PatchMatrix.Name
posit := MyStation.Cont.XPos
```

**MaterialsTable**

**MaterialsTable**

Use the MaterialsTable to define the ingredients and the products to be processed in the plant.

<!-- image -->

The ingredients and products are going to be used by the FluidSource , by the DePortioner , and by the Mixer in your simulation model.

**You can type in:**

- The Name of the Material , for example DefaultProduct , MyIngredient , MyMaterial , etc. The material names are used for:
- All ingredients and for the product in a chemical formula of the object Mixer .
- The value Material of the FluidSource and of the DePortioner .
- The value of the Current material of the Pipe and the Tank .
- The values which the Tab Statistics of the object FluidDrain shows.
- The Density of the material.
- The Color to be used during the animation of the product. Click in the respective cell and select a color in the dialog Colors . Plant Simulation then enters the color and the color number into the cell.
- The Product Amount which is the amount of the intermediate or of the finished product which the Mixer is to produce using the ingredients.

If you type -1 for a recipe into the column Product Amount of the MaterialsTable of the Mixer , Plant Simulation assumes the sum of all ingredients as the Product Amount . You only have to explicitly specify the Product Amount if mixing the ingredients increases or decreases the volume, i.e., if the Product Amount is not the sum of the ingredients.

- The Unit of the material. Double-click in the respective cell and select the unit for the material from the drop-down list.
- The Name of Ingredient 1 to Ingredient 10 , its respective Amount , and its respective Unit . By default, we provide for ten ingredients. You can add additional columns for additional ingredient sets at any time, compare Add Additional Ingredients to the MaterialsTable . You do not have to fill in all columns.

<!-- image -->

The MaterialsTable shares most of the properties of the DataTable . It provides the Methods of the DataTable and the Attributes of the DataTable .

To add the MaterialsTable to your simulation model, click Manage Class Library &gt; Basic Objects &gt; Fluids &gt; MaterialsTable on the Home ribbon tab.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

**See also**

Add Additional Ingredients to the MaterialsTable

Simulate Free-flowing Materials and Fluids

Configure the Recipe in the MaterialsTable

Configure the Recipe of the Product in the MaterialsTable

Compare

CurrentMaterialColor [SimTalk]

CurrentMaterialDensity [SimTalk]

DataTable [object] Work with Data in a List or Table Work with Data in the DataTable Methods of the DataTable \_Attributes of the DataTable

#### Add Additional Ingredients to the MaterialsTable

By default, the MaterialsTable is designed for ten ingredients. You can add more ingredients as required.

To add additional ingredients:

<!-- image -->

- Deactivate Inherit Format and Inherit Contents on the List ribbon tab.
- Open the dialog List Format and change to the tab Dimension . Increase the number of columns per additional ingredient by three. In our example we added six columns, meaning two ingredients. Click OK and close the dialog.

<!-- image -->

<!-- image -->

This then looks like this when we scroll to the right:

<!-- image -->

- We then copy the columns for Ingredient 9 and Ingredient 10 and paste them into the added columns. While doing so Plant Simulation applies the data type , the caption of the column header , the column width , and the background color of the cells. This way we do not have to manually configure each of these columns.

<!-- image -->

- The column Ingredient has the data type string .
- The column Amount has the data type real .
- The column Unit has the data type string .

<!-- image -->

### Resource Objects

