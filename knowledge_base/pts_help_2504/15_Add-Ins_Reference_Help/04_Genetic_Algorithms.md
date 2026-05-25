## Genetic Algorithms

Plant Simulation provides genetic algorithms as optimization tools for solving complex sequential, allocation, and selection tasks. Genetic Algorithms work along the same line as the biological evolution does.

The add-in Genetic Algorithms provides these objects:

<!-- image -->

Naturalist Charles Darwin found out that those individuals, who adapted best to their natural surroundings, procreate the best. Once an individual acquires an advantageous characteristic, either by mutation or by cross-breeding, it may use these advantages and pass them on to its offspring. They, and their descendants, will benefit from these selection advantages, so that over the generations all individuals of the corresponding species will acquire these characteristics. Individuals without these advantages will have fewer offspring because of this selection disadvantage, so that the lack of an advantageous characteristic will lead to their extinction.

Genetic Algorithms use these same principles. The most successful solutions are selected from a given initial set of proposed solutions and used for creating new solutions. Then, better solutions are created over succeeding generations. If a proposed solution has a selection advantage and if it then is used for creating new solutions depends on the so-called Fitness Value that is determined by a simulation model.

You might, for example, have to optimize the loading sequence of orders for a production plant. A simulation model will provide you the with entire processing time for each proposed loading sequence of orders. The evolution cycle will then produce successively better sequences that will process the orders in as little a time as possible.

Major advantages of genetic algorithms are that they are task-independent and that they return good results. This is why genetic algorithms are ideally suited in effectively supporting you in a variety of simulation-based optimization tasks.

You can apply Genetic Algorithms to solve a variety of problems without spending too much time for implementing, and for adapting, your simulation models. How you can accomplish this is described under Optimize Models with Genetic Algorithms .

**Note**

Instead of configuring your optimization tasks with the individual objects of the Genetic Algorithms , you can accomplish this much more comfortably with the GAWizard .

**Add the Objects to the Simulation Model**

To add the objects of the Genetic Algorithms to the Class Library , click Manage Class Library &gt; Basic Objects &gt; GA on the Home ribbon tab.

<!-- image -->

The Wizard for Genetic Algorithms ( GAWizard ) integrates genetic algorithms into an existing simulation model. You can use it for optimizations in which the evaluation is based on a simulation run as well as for optimizations in which the evaluation is based on calculations in methods.

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

#### Genetic Algorithms and Simulation

### Genetic Algorithms and Simulation

Genetic Algorithms use an iterative process to generate solutions for an optimization task. The simulation model computes the fitness of the proposed solutions. This fitness then determines if the solution under consideration is used for generating new solutions or not.

The chart shows the interaction between you user, the objects of the Genetic Algorithms and the Plant Simulation model.

Figure 15-1: Optimization as an iterative process

<!-- image -->

Initially, you will define an optimization task. Then, Genetic Algorithms and a Plant Simulation model use an iterative process to generate new and better solutions. After completing the optimization cycles, the optimal solution that was found, is ready to be used for further modeling.

##### Optimization Tasks

#### Optimization Tasks

Genetic algorithms solve optimization tasks.

You can use genetic algorithms to solve optimization tasks that are characterized by:

- Large solution spaces.
- Unknown characteristics of the solution space.
- Discontinuities within the solution space that do not allow for mathematical-numerical optimization of the task.
- Many soft restrictions for the solutions. Soft restrictions are restrictions that do not necessarily have to be kept, but lead to worse results.

The number of possible solutions depends on the type of the optimization task and on the number of items contained in the defined set. The defined set contains the items to be optimized.

As a rule optimization with genetic algorithms works well if the problem contains multiple peaks with similar fitness values. Then, the optimization produces different solutions.

<!-- image -->

A flat plane with narrow peaks on the other hand leads to many solutions with equal fitness. The fitness does not direct the algorithm toward the peak, so the genetic algorithm does not find a maximum.

<!-- image -->

**As basic tasks you can:**

- Define Sequence Tasks with the Object GASequence
- Define Selection Tasks with the Object GASelection
- Define Allocation Tasks with the Objects GARangeAllocation and GASetAllocation

The type of task determines, which genetic operators you can use, compare Genetic Operators .

You can randomly combine different types of basic tasks. These are managed by the object GAOptimization , compare the Tab Settings .

##### Define Sequence Tasks with the Object GASequence

When solving sequence tasks , the relative sequence of order of the item of the definition set is important. Each item may only occur once in each solution.

A typical example of a sequence task is the Traveling Salesman Problem , for which you have to optimize the traveling route of a salesman through a defined number of cities. The aim is as short a route as possible. In a production and manufacturing environment on the other hand, the main task is to arrive at a high utilization rate by finding an optimized loading sequence of the orders to be processed.

You can define Position Restrictions (comparable to constraints for the items of a sequence task) for each item by entering the permitted positions for each item into a list of integer values, which is managed by the object GASequence .

- Click into a cell of the column Define Sets on the tab Contents .
- Click the tab Attributes and select Integer from the drop-down list Data Type .
- Enter integer numbers into the cells below Position Constraints that restrict the position.

Typical applications in the fields of production planning and production control for position restrictions are assigning production orders to groups of machines, managing personnel or placing goods in a high bay warehouse.

##### Define Selection Tasks with the Object GASelection

When solving selection tasks the selection of a defined number of items from a defined set is to be optimized. Thus, the solution set is always less than the definition set. Each item of the definition set may only occur once in the solution set.

You can define and solve selection tasks with the object GASelection .

##### Define Allocation Tasks with the Objects GARangeAllocation and GASetAllocation

When solving allocation tasks items from another set (range) are allocated to the items of the definition set. Each item of the definition set is assigned an item of the range, in which the items out of the range may be used once, several times or not at all. You can also define a range of its own for each item of the definition set.

A typical allocation task would optimize the allocation of bundles to roll stands with the aim of minimizing the set-up times while considering the production schedule.

You can define and solve selection tasks with the object GASetAllocation .

If the range consists of numerical values within a defined interval, use the object GARangeAllocation .

#### Course of Optimization

Course of Optimization

Using the definition of the basic tasks, the object GAOptimization generates solutions for the individual basic tasks. The proposed solution for a basic task is called a chromosome . All chromosomes together form the individual . The fitness value of the individual will be determined by the simulation model or an evaluation method. Each individual may be considered as a solution for an optimization task.

The previous chapter described how an optimization task may be built by combining a certain number of basic tasks of types allocation , selection , or sequence .

After the Initialization Phase the Evolution Cycle starts.

See also

GAOptimization

##### Initialization Phase

Type in the Initial Rate In Percent, which is the number of items to be initialized, on the tab Attributes of the individual GA objects. The number of predefined chromosomes is located between 0 and the size of the generation, compare Size of Generation . The selection from the initialization set is random whereby initialization solutions can only occur several times if the initialization rate has not been reached after selecting all initialization solutions. The remaining chromosomes contain random numbers which are determined depending on the type of task. For allocation tasks a random value of the valid value range is determined, while for selection and sequence tasks the elements are brought into a random sequence.

While creating the first generation, the genetic algorithm uses as many of the predefined initialization solutions as you enter for the Initialization Rate . The genetic algorithm attempts to incorporate all solutions evenly into the first generation.

If position restrictions of a sequence task are given, the genetic algorithm starts finding solutions by a random search which meets all position restrictions. The genetic algorithm starts with the elements with the smallest number of allowed positions.

This is followed by the Evolution Cycle .

See also

Initial Rate In Percent [GASelection]

##### Evolution Cycle

After the genetic algorithm has generated the start generation of the individuals during the Initialization Phase , it executes the generation cycle. The generation cycle consists of:

- The stochastic or deterministic selection of the parents (reproduction of solutions).
- The generation of the offspring (children) created by the random application of genetic operations ( crossover , Mutation , Inversion ).
- The evaluation of the fitness of the offspring (objective function).

After the initialization, the individuals of the start generation are evaluated by determining a fitness value for each solution. Then, a selection rule, which you select under Parent Selection in the object GAOptimization , determines, which parents out of the start generation are going to be used. The individuals you picked are going to be the parents. Both parents are copied, so that daughter and son are clones of mother and father. Then, the genetic operators are going to be applied to daughter and son. Whether the operators are used or not depends on the probability of the operators which you define. The evaluation method then starts calculating the fitness values.

The individuals for the next generation are chosen from each family according to the Offspring Selection . Once all individuals for the next generation are determined, new pairs of parents are determined from these individuals that then generate the children of the next generation, etc.

This cycle is terminated, when the maximum number of generations or a defined grade for the fitness value or the average of the fitness values is reached.

See also

Parent Selection [drop-down list]

Offspring Selection [check box]

#### Genetic Operators

Genetic Operators

The genetic operators play an important role when generating new individuals. The way the genetic operators work depends on the respective basic task. Below we describe how they work. If and how often they are used depends on the probabilities you set for the operator.

You can select the:

- Mutation Operator [general description]
- Inversion Operator
- Crossover Operator

##### Mutation Operator [general description]

The Mutation Operator randomly changes individual genes.

For Allocation Tasks

For allocation tasks the mutation operator stochastically determines a value from the allocation set or chosen from the defined interval and then allocated to the selected gene.

For Sequence Tasks

For sequence tasks the mutation operator exchanges two randomly chosen genes. The illustration below demonstrates how the operator works.

Figure 15-2: Mutation for a sequence task

<!-- image -->

You can set how the genetic algorithm exchanges the positions by using a probability for exchanging each individual item or by entering a number for the exchanges (compare Start Probability , Delta per Generation , Inversion/Mutation Operator ).

If you entered a number for the exchanges, you can also define the maximum distance of the positions of the items to be exchanged.

If you defined position restrictions, the genetic algorithm will attempt to meet these restrictions by performing a cycle exchange of some items of the sequence task. In the figure above the exchanged items 2 and 5 have a position offset of 3 .

See also

Start Probability [general description]

Delta per Generation [general description]

Inversion/Mutation [GASequence]

**For Selection Tasks**

For selection tasks the mutation operator exchanges a gene between the unused definition set and the active selection set.

Inversion Operator

The Inversion Operator inverts the sequence within a defined range of the individual.

You cannot use the Inversion Operator for allocation tasks.

For Sequence and Selection Tasks

For sequential and selection tasks the inversion operator first selects a random inversion range and then inverts the sequence of genes within this range.

Figure 15-3: Mutation for an inversion task

<!-- image -->

##### Crossover Operator

As opposed to the mutation and inversion operators, the Crossover Operator is applied to two chromosomes. It exchanges items between these two. It initially selects two randomly crossing points and then exchanges the ranges between these two points.

Figure 15-4: Crossover between two solutions

<!-- image -->

Using the Crossover Operator will result in better solutions because there is a high probability that short good ranges are preserved and will thus be reproduced in a growing number of solutions.

For sequence and selection tasks we differentiate between two different types of the crossover operator. The operators differ in how they stress the relative and absolute position of the individual items.

- Order Crossover (OX) preserves the relative position (neighbor relation) of the items of the solution to each other.
- Partially Matched Crossover (PMX) stresses the absolute position of the objects. So, when you use OX , small groups of solution objects are kept together, while PMX separates the solution objects to preserve the absolute position of individual items.

#### GAOptimization

### GAOptimization

Define the basic tasks of your optimization problem with the object GAOptimization . During the optimization run the GAOptimization manages the individuals of the different generations. The individuals correspond to proposed solutions of the optimization problem you are analyzing.

Icon Description To show a tooltip with information about the GAOptimization , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the GAOptimization , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

<!-- image -->

To add the object GAOptimization to the Class Library , click Manage Class Library &gt; GA &gt; GAOptimization on the Home ribbon tab.

#### Dialog Box of the GAOptimization

Dialog Box of the GAOptimization

Double-click the icon of the GAOptimization to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Settings

Tab Settings

The tab Settings provides the settings listed in the table of contents to the left.

**Size of Generation**

###### Size of Generation

Type in the number of parent individuals of a generation to be used for the optimization.

<!-- image -->

This value is the number of families within a generation whereupon not all parent individuals establish a family, compare Parent Selection .

The number of children of a generation is twice the value of the Size of Generation .

SimTalk

GenerationSize [SimTalk]

See also

Parent Selection [drop-down list]

###### Number of Generations [text box]

Type in the maximum number of generations for which you would like to perform the optimization.

<!-- image -->

Once that number of optimization steps is reached, the Termination Control is called.

SimTalk

NumGenerations [SimTalk]

See also

Termination Control [GAOptimization]

###### Task

Task To open a list, into which you type the paths to the tables that define the optimization task, click Task .

<!-- image -->

Each row stands for a basic task that is part of the entire problem.

<!-- image -->

**SimTalk**

TaskTable [SimTalk]

Tab Goal

Tab Goal

The tab Goal provides the settings listed in the table of contents to the left.

###### Direction [GAOptimization]

Select whether the optimum is going to be a high ( Maximum ) or a low fitness value ( Minimum ).

<!-- image -->

###### Fitness

Fitness

Type in the Fitness Limit of the optimization run.

<!-- image -->

If at least one individual reaches or exceeds this value, the GAOptimization terminates the optimization and calls the Termination Control . Otherwise it executes the number of optimization runs which you enter as the Number of Generations .

SimTalk

FitnessTarget [SimTalk]

See also

Termination Control [GAOptimization]

Number of Generations [text box]

###### Average Fitness

Type in the Average Fitness for the individuals of a generation.

<!-- image -->

Once Plant Simulation reaches this value, it terminates the optimization run. Otherwise, it executes the number of optimization runs set in the Number of Generations .

SimTalk

FitnessTargetAverage [SimTalk]

See also

Number of Generations [text box]

Tab Selection

Tab Selection

The tab Selection provides the settings listed in the table of contents to the left.

**Fitness Reference [drop-down list]**

###### Fitness Reference [drop-down list]

After a new generation has been generated and evaluated, the object GAOptimization determines the individuals of the parent generation used for creating the individuals of the next generation. Select if the fitness value of the individual proposed solutions is evaluated relative to the worst solution of the generation or relative to absolute zero.

<!-- image -->

- Absolute evaluates the fitness value of the individual solutions relative to absolute zero. At the beginning of the optimization runs Absolute produces good results because of the variance of the individuals in the generation. For homogeneous generations the selection pressure is extremely low with this setting.
- Relative evaluates the fitness value of the individual solutions relative to the worst solution of the generation. For homogeneous generations an even selection pressure is maintained.

**SimTalk**

FitnessReference [SimTalk]

###### Parent Selection [drop-down list]

Select if the Parent Selection is going to be deterministic , according to its fitness value, or randomly , where all individuals have the same likelihood to be used as parents.

<!-- image -->

- Deterministic selects the parents randomly according to their fitness values (roulette wheel selection). For this reason individuals with good fitness values will be used more often as parents for creating the
- next generation. But individuals with a bad fitness value also have a chance to be used as parents.
- Random does not use the fitness values. All individuals have the same likelihood to be used as parents.

**SimTalk**

**ParentSelection [SimTalk]**

**Clone Best Solution [check box]**

###### Clone Best Solution [check box]

To take the best solution of a generation over unchanged into the next generation, select this check box. Clear it to not take it over.

SimTalk

CloneBestSolution [SimTalk]

###### Offspring Selection [check box]

Select how the GAOptimization selects family members, which are going to be used in the next generation.

<!-- image -->

- 1of2 only uses the two child solutions and selects the solution with the better fitness value.
- 1of4 uses parent and child solutions and selects the best solution.
- Prob (probabilistic) uses parent and child solutions. It uses a stochastic selection. Selection probabilities are proportional to the quality of the solution.
- Random selects the individual taken for the new generation regardless of the fitness value.

**SimTalk**

OffspringSelection [SimTalk]

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

**See also**

Select Object [for controls]

Evaluation Control [GAOptimization]

Change of Generations Control

Termination Control [GAOptimization]

Error Handling Control

###### Evaluation Control [GAOptimization]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Evaluation Control , which is called once the individuals of a new generation have been created.

<!-- image -->

The Evaluation Control controls how the GAOptimization evaluates the newly generated individuals.

These newly generated individuals are going to be passed to the method as parameter of data type table . Within the method or within a simulation run started by the method, the fitness value is going to be calculated for each newly created individual of the generation. The simulation model computes the fitness value and writes it into column 2 of the table.

<!-- image -->

An individual consists of the chromosomes whose number matches the number of entries in the Task table. The contents of each chromosome is a solution proposal for the respective basic task.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .

**Evaluation Control [GAOptimization]**

- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

EvaluationCtrl [SimTalk]

See also

Select Object [for controls]

###### Change of Generations Control

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code that controls the Alternation of Generations , which is called once a generation and its offspring generation have been completely evaluated.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Parameter

A DataTable is passed as parameter to the Method , containing information about the current and the previous generation. Column 1 contains the generation as integer . The following columns contain the tables Adults, Children, Families, Best Solutions and Statistics that you can also access on the tab Recording .

Note The GenerationChangeCtrl may not call the method evolve for the GAOptimization .

Use the GenerationChangeCtrl to graphically display intermediate results of an optimization run:

```simtalk
param recording: table
var sta: table sta := recording[6,1]
StTab.delete
StTab.insertList(1,1,sta.copy({2,1}..{2,*}))
StTab.insertList(2,1,sta.copy({3,1}..{3,*}))
StTab.insertList(3,1,sta.copy({4,1}..{4,*}))
StatisticsChart.update
```

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

**Change of Generations Control**

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

**SimTalk**

GenerationChangeCtrl [SimTalk]

evolve [SimTalk]

See also

Select Object [for controls]

Tab Recording

###### Termination Control [GAOptimization]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Termination Control , which is called when the optimization run is terminated.

<!-- image -->

An optimization run is terminated when evaluation runs have been performed for all generations or when the limit for fitness or the fitness average has been reached or has not been reached. A table containing information about the active and older generations is going to be passed as parameter to the method.

Column 1 contains the generation as integer value. The following columns contain the tables Adults , Children , Families , Best Solutions , and Statistics that you can also access on the tab Recording .

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

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

SimTalk TerminationCtrl [SimTalk] See also Select Object [for controls] Tab Recording

###### Error Handling Control

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Error Handling Control , which is called when an error occurred during the optimization.

<!-- image -->

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

Parameters

Two parameters are passed to the Method that is called.

- The parameter errorNo of data type integer is the number of the error.
- The parameter ErrorMessage of data type string describes the error itself.

The following example illustrates how to use the Error Handling Control : The genetic algorithm cannot recognize or prove conflicting position restrictions for sequence problems. The genetic algorithm thus terminates the search for initial solutions after the number of attempts you set and shows a message if you programmed the Error Handling Control :

```simtalk
param errorNo: integer, ErrorMessage: string
print ?.name," reports: "
print "Error ",errorNo," means \"",ErrorMessage,"\""
```

If the GAOptimization cannot create the first generation because of conflicting position restrictions, the Error Handling Control outputs this message in the Console :

GAOptimization reports: Error 1 means "No valid solutions found. The restrictions might be conflicting."

Create a Control that is a Method of the Object

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

##### Tab Recording

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

SimTalk

ErrorCtrl [SimTalk]

See also

Select Object [for controls]

Tab Recording

Tab Recording

The tab Recording provides the settings listed in the table of contents to the left.

###### Adults

To open a table, which shows the proposed solutions and fitness values of the active parent generation, click this button.

**Children**

###### Children

To open the table, which shows the proposed solutions and fitness values of the active child generation, click this button.

###### Families

To open a table, which shows the relationships of the individuals of the child generation to the individuals of the parent generation, click this button.

**Evolution**

###### Evolution

To save the tables Children , Families and Adults for all generations during the evolution cycle, select the check box and click Apply .

<!-- image -->

Evolution Table

To open a table that shows data for the Population , Adults , Children , and for Families , click Evolution .

SimTalk

Evolution [SimTalk]

###### Best Solutions

To open a table that shows the best solutions of all generations until now, click this button.

<!-- image -->

SimTalk

NumBestSolutions [SimTalk]

**Number [text box] - GAOptimization**

###### Number [text box] - GAOptimization

Type in the number of best solutions which the GAOptimization is going to save.

<!-- image -->

SimTalk

NumBestSolutions [SimTalk]

###### Statistics [button] - GAOptimization

To open a table that shows the Best Fitness , Average Fitness and Worst Fitness value for each generation evaluated until the current simulation time, click this button.

**Note**

The GAOptimization does not save the contents of these tables when you save your model. Thus, you cannot stop an optimization run, save it and reload it later on! The GAOptimization always resets when you insert it.

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The View Menu menu provides the command Refresh [on View menu] . SimTalk updateDialog [SimTalk]

##### Tools Menu

The commands are described under the Tools Menu .

**Help Menu**

##### Help Menu

The Help Menu provides commands to access its functions.

**Contents**

Help on Object

Using Online Help describes the different ways of using and searching in the help.

##### Methods of the GAOptimization

#### Methods of the GAOptimization

The GAOptimization provides:

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

##### evolve [SimTalk]

evolve [SimTalk]

Creates a new generation for the object designated by &lt;Path&gt;.

Remarks

The parent generation and the set genetic operators are used to create the individuals of the new generation.

After the method evolve has been called, the Evaluation Control is called, which is going to evaluate the newly created individuals.

Type

Method

Syntax

&lt; Path &gt;.evolve

Example

GAOptimization.evolve

See also

Evaluation Control [GAOptimization]

##### reset [SimTalk] - GAOptimization

Resets the object designated by &lt;Path&gt;, as clicking Reset Simulation in the EventController does not do this.

Type

Method

Syntax

&lt; Path &gt;.reset

Example

GAOptimization.reset

#### Read-Only Attributes of the GAOptimization

Read-Only Attributes of the GAOptimization

The GAOptimization provides:

- The \_Read-Only Attributes of the DataTable .
- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

<!-- image -->

**Attributes of the GAOptimization**

#### \_Attributes of the GAOptimization

The GAOptimization provides:

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
GAOptimization.FitnessReference := "Relative"
print GAOptimization.FitnessReference
posit := Station.cont.XPos
```

##### CloneBestSolution [SimTalk]

Sets if the object designated by &lt;Path&gt; uses the best solution of a generation unchanged for the next generation ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.CloneBestSolution:boolean

Assignment Value

You can assign a value of data type boolean .

Example

GAOptimization.CloneBestSolution := true

See also

Clone Best Solution [check box]

Direction [SimTalk] - GAOptimization

Sets if the object designated by &lt;Path&gt; executes the optimization toward a high or a low fitness value.

Type

Attribute

Syntax

&lt; Path &gt;.Direction:string

Assignment Value

You can assign a value of data type string .

You can specify "Maximum" or "Minimum" .

Example

GAOptimization.Direction := "Maximum"

See also

Direction [GAOptimization] , drop-down list

**ErrorCtrl [SimTalk]**

##### ErrorCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;. Plant Simulation executes the control when an error occurred during the optimization of the GAOptimization .

Type

Attribute

Syntax

< Path >.ErrorCtrl:method

Assignment Value

You can assign a value of data type method .

Examples

```simtalk
GAOptimization.ErrorCtrl := &regErrors
param errorNo: integer, errorMessage: string
print ?.name," reports: "
print "error ",errorNo," means \"",errorMessage,"\""
```

See also

Error Handling Control

##### EvaluationCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

**Remarks**

Plant Simulation executes the Evaluation Control once the individuals of a new generation have been created by the GAOptimization designated by &lt;Path&gt;.

These newly generated individuals are going to be passed to the method as parameter of data type table . The evaluation method then computes a fitness value for each proposed solution of the new generation.

Type

Attribute

Syntax

&lt; Path &gt;.EvaluationCtrl:method

**Parameter**

The individuals of the new generation are going to be passed as parameters of data type table to the method. The method or a simulation run that was started by the method then computes the fitness value for each individual of the generation and writes it into column 2 of the table.

**Note**

You have to enter an Evaluation Control .

**Note**

The fitness value may not become negative.

The data type of column 1 is table and sets the proposed solutions of the active generation. An individual consists of chromosomes. The number of chromosomes equals the number of entries on the table Tasks .

Each chromosome sets one proposed solution for the corresponding basic task.

Assignment Value

You can assign a value of data type method .

**Example**

GAOptimization.EvaluationCtrl := &amp;evaluate

**See also**

Evaluation Control [GAOptimization]

##### Evolution [SimTalk]

Sets if the object designated by &lt;Path&gt; saves the tables Children , Families , and Adults for all generations during the evolution cycle ( true ) or not ( false ).

Type

Attribute

Syntax

&lt; Path &gt;.Evolution:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
GAOptimization.Evolution := true
```

See also

Evolution , button

##### FitnessReference [SimTalk]

Determines how the object designated by &lt;Path&gt; evaluates the fitness value of the individual proposed solutions relative to the worst solution of the generation or relative to absolute zero.

**Remarks**

- Absolute evaluates the fitness value of the individual solutions relative to absolute zero. At the beginning of the optimization runs Absolute produces good results because of the variance of the individuals in the generation. For homogeneous generations the selection pressure is extremely low with this setting.
- Relative evaluates the fitness value of the individual solutions relative to the worst solution of the generation. For homogeneous generations an even selection pressure is maintained.

Type

Attribute

Syntax

&lt; Path &gt;.FitnessReference:string

Assignment Value

You can assign a value of data type string .

You can specify "Absolute" or "Relative" .

Example

GAOptimization.FitnessReference := "Relative"

See also

Fitness Reference [drop-down list]

FitnessTarget [SimTalk]

Sets the fitness limit of the optimization run of the object designated by &lt;Path&gt;.

Remarks

If at least one individual reaches or exceeds this value, the GAOptimization terminates the optimization run and calls the Termination Control . Otherwise it executes the number of optimization runs set in the Number of Generations .

Type

Attribute

Syntax

&lt; Path &gt;.FitnessTarget:real

Assignment Value

You can assign a value of data type real .

Example

GAOptimization.FitnessTarget := 333.33

See also

Fitness

Number of Generations [text box]

##### FitnessTargetAverage [SimTalk]

Sets the average fitness target value of the individuals of a generation of the object designated by &lt;Path&gt; that has to be reached.

Remarks

After that the optimization run is terminated. Otherwise the number of optimization runs set in the Number of Generations is executed.

Type

Attribute

Syntax

&lt; Path &gt;.FitnessTargetAverage:real

Assignment Value

You can assign a value of data type real .

Example

GAOptimization.FitnessTargetAverage := 333.33

See also

Average Fitness

Number of Generations [text box]

##### GenerationChangeCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation executes the control as soon as a generation and its succeeding generations has been completely evaluated by the GAOptimization .

**Note**

The GenerationChangeCtrl may not call the method evolve for the GAOptimization .

Type

Attribute

Syntax

&lt; Path &gt;.GenerationChangeCtrl:method

**Parameter**

A DataTable is passed as parameter to the Method containing information about the current and the previous generation. Column 1 contains the generation as integer . The following columns contain the tables Adults, Children, Families, Best Solutions and Statistics that you can also access on the tab Recording .

Assignment Value

You can assign a value of data type method .

**Examples**

```simtalk
GAOptimization.GenerationChangeCtrl := &methObj
// graphically displays intermediate results of an optimization run
param recording: table
var sta: table sta := recording[6,1]
StTab.delete
StTab.insertList(1,1,sta.copy({2,1}..{2,*}))
StTab.insertList(2,1,sta.copy({3,1}..{3,*}))
StTab.insertList(3,1,sta.copy({4,1}..{4,*}))
StatisticsChart.update
```

See also Size of Generation Parent Selection [drop-down list] evolve [SimTalk] Tab Recording

##### GenerationSize [SimTalk]

Sets the number of parent individuals of a generation of the object designated by &lt;Path&gt;.

Remarks

This value matches the number of families in a generation.

Not every parent individual will have a family (compare ParentSelection ). The number of children in a generation is twice the value of GenerationSize .

Type

Attribute

Syntax

&lt; Path &gt;.GenerationSize:integer

Assignment Value

You can assign a value of data type integer .

Example

GAOptimization.GenerationSize := 30

See also

Size of Generation , text box

Number of Generations [text box]

ParentSelection [SimTalk]

##### NumBestSolutions [SimTalk]

Sets how many of the best solutions found until now the object designated by &lt;Path&gt; writes to the table Best Solutions .

Type

Attribute

Syntax

&lt; Path &gt;.NumBestSolutions:integer

Assignment Value

You can assign a value of data type integer .

Example

GAOptimization.NumBestSolutions := 10

See also

Best Solutions

Number [text box] - GAOptimization

##### NumGenerations [SimTalk]

Sets the maximum number of generations over which the object designated by &lt;Path&gt; performs the optimization.

Type

Attribute

Syntax

&lt; Path &gt;.NumGenerations:integer

Assignment Value

You can assign a value of data type integer .

Example

GAOptimization.NumGenerations := 12 * Variable

See also

Size of Generation

Number of Generations [text box]

##### OffspringSelection [SimTalk]

Sets how the object designated by &lt;Path&gt; selects family members used in the next generation.

Type

Attribute

Syntax

&lt; Path &gt;.OffspringSelection:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "1of2" only uses the two child solutions and selects the solution with the better fitness value.
- "1of4" uses parent and child solutions and selects the best solution.
- "Prob" (probabilistic) uses parent and child solutions for selecting the new generation. It uses a stochastic selection. Selection probabilities are proportional to the quality of the solution.
- "Random" selects the individual taken for the new generation regardless of the fitness value.

**Example**

GAOptimization.OffspringSelection := "1of4"

See also

Offspring Selection [check box]

##### ParentSelection [SimTalk]

Sets how the object designated by &lt;Path&gt; selects the parents for the next generation.

Type

Attribute

Syntax

&lt; Path &gt;.ParentSelection:string

Assignment Value

You can assign a value of data type string .

You can specify:

- "Deterministic" selects the parents randomly according to their fitness values ( roulette wheel selection).

For this reason individuals with good fitness values will be used more often as parents for creating the next generation. But individuals with a bad fitness value also have a chance to be used as parents.

- "Random" does not use the fitness values. All individuals have the same likelihood to be used as parents.

**Example**

GAOptimization.ParentSelection := "Random"

See also

Parent Selection [drop-down list]

##### TaskTable [SimTalk]

TaskTable [SimTalk]

Sets the table which describes the optimization task of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.TaskTable:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
GAOptimization.TaskTable.inheritContents := false
GAOptimization.TaskTable.delete
GAOptimization.TaskTable[1,1] := sequence
GAOptimization.TaskTable[2,1] := selection
```

See also

Task , button

##### TerminationCtrl [SimTalk]

Designates a Method object of the object designated by &lt;Path&gt;.

Remarks

Plant Simulation executes the control as soon as the optimization run of the GAOptimization designated by &lt;Path&gt; is finished.

Type

Attribute

Syntax

&lt; Path &gt;.TerminationCtrl:method

Parameter

A DataTable is passed as parameter to the Method containing information about the active and its preceding generations. Column 1 contains the generation as integer . The following columns contain the tables Adults , Children , Families , Best Solutions , and Statistics that may also accessed on the tab Recording .

Assignment Value

You can assign a value of data type method .

Example

GAOptimization.TerminationCtrl := &amp;Termination

See also

Termination Control [GAOptimization]

Tab Recording

#### GASelection

### GASelection

Define selection tasks for the genetic algorithm with the object GASelection .

Icon

<!-- image -->

Description

To show a tooltip with information about the GASelection , hover with the mouse over it.

To change the length of the graphic and the anchor points of the GASelection , click Show Manipulators

on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the object GASelection to the Class Library , click Manage Class Library &gt; GA &gt; GASelection on the Home ribbon tab.

See also

Define Selection Tasks with the Object GASelection

#### Dialog Box of the GASelection

Dialog Box of the GASelection

Double-click the icon of the GASelection to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

##### Tab Contents

###### Tab Contents [GASelection]

The tab Contents shows a table with the columns Define Set and Initial Sets .

<!-- image -->

**Note**

You can only change the column width after you deactivate Format &gt; Inherit Format .

**Define Set [GASelection]**

###### Define Set [GASelection]

Type in the total number of items the solutions consist of into the cells in the column Define Set .

Each item may occur once only. Type in the size of the solution set into the text box Selection Quantity on the tab Attributes . Select the Data Type of the definition set from the drop-down list on the tab Attributes .

<!-- image -->

See also

**Selection Quantity**

Data Type [drop-down list] - GASelection

###### Initial Sets [GASelection]

Type in the proposed start solutions into the column Initial Sets --&gt; and the following columns.

<!-- image -->

**Note**

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

See also

InitRate [SimTalk] - GASequence

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Initial Rate In Percent [GASelection]**

###### Initial Rate In Percent [GASelection]

Type in the share of chromosomes (in percent) that may be created for the initial generation by using the initialization data.

<!-- image -->

###### Data Type [drop-down list] - GASelection

Select the Data Type of the items of the chromosomes.

<!-- image -->

**SimTalk**

DataType [SimTalk] - GASelection

**Selection Quantity**

###### Selection Quantity

Type in the number of items that are to be selected from the definition set.

SimTalk

Selection [SimTalk]

Tab Genetic Operators

Tab Genetic Operators

Set the probabilities for the different genetic operators on the tab Genetic Operators .

The tab Genetic Operators provides the settings listed in the table of contents to the left.

###### Crossover [GASelection]

For selection tasks each item may only occur once in the solution set. Crossover tasks on the other hand may violate this condition. This is why procedures are needed that reorganize the remaining set, i.e., the set that is not changed by crossover , so that the condition is met again.

<!-- image -->

Select the type of crossover:

- OX (Order Crossover) attempts to preserve the relative position and thus the sequence of items of a chromosome as far as possible. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, it will be eliminated from the remaining set and the following items will move up.
- PMX (Partially Matched Crossover) makes the absolute position of the items take precedence over the sequence. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, this item is replaced by an item from the crossover set in chromosome 1 that is not contained in the crossover set of chromosome 2.

**SimTalk**

CrossoverOperator [SimTalk] - GASelection

CrossoverProb, CrossoverDelta [SimTalk] - GASelection

###### Inversion/Mutation [GASelection]

Inversion/Mutation [GASelection]

Select the genetic operator and type in a value for the Start Probability and for the Delta per Generation .

<!-- image -->

- The Mutation Operator randomly changes individual genes.
- The Inversion Operator inverts the sequence within a defined range of the individual.

SimTalk

Mutation [SimTalk] - GASelection

See also

Start Probability [GASelection]

Delta per Generation [GASelection]

Mutation Operator [general description]

Inversion Operator

###### Start Probability [GASelection]

Type in a value for the Start Probability of the respective genetic operator being applied to a newly created chromosome.

<!-- image -->

- For Mutation the probability refers to each individual item.
- For Inversion and Crossover the probability refers to the entire individual.

We found the following probabilities to yield good results:

| Mutation   | 0.01 to 0.1   |
|------------|---------------|
| Inversion  | 0 to 0.4      |
| Crossover  | 0.5 to 0.8    |

**SimTalk**

InversionProb, InversionDelta [SimTalk] - GASelection

Mutation [SimTalk] - GASelection

MutationProb, MutationDelta [SimTalk] - GASelection

**Delta per Generation [GASelection]**

###### Delta per Generation [GASelection]

Type in a value for the Delta per Generation that sets the change of the probabilities for the Mutation or the Crossover operators over the generations.

<!-- image -->

SimTalk

CrossoverProb, CrossoverDelta [SimTalk] - GASelection

MutationProb, MutationDelta [SimTalk] - GASelection

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**File Menu**

##### File Menu

The menu commands are described under the List Ribbon Tab .

| Import File            | Print List   |
|------------------------|--------------|
| Export to File [lists] | Print Setup  |
| Export Object File     | Close Model  |
| Text File Format       |              |

##### Edit Menu

The menu commands are described under the Home Ribbon Tab and the List Ribbon Tab .

| Cut [Home ribbon]                             | Select All [Home ribbon]   |
|-----------------------------------------------|----------------------------|
| Copy [Home ribbon]                            | Insert Row [lists]         |
| Paste Contents of the Clipboard [Home ribbon] | Find [lists]               |
| Delete [Home ribbon]                          | Replace [lists]            |

**Format Menu**

##### Format Menu

The menu commands are described under the List Ribbon Tab .

| Activate Column Index   | Inherit Contents [lists]   |
|-------------------------|----------------------------|
| Activate Row Index      | Inherit Comment [button]   |
| Inherit Format [button] |                            |

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The commands are described under the List Ribbon Tab .

| Recompute Formulas     | Highlight Empty Cells   |
|------------------------|-------------------------|
| Show Comment [lists]   | Go To Cell              |
| Show Data Type [lists] |                         |

##### Tools Menu

The commands are described under the Tools Menu .

**Help Menu**

##### Help Menu

The Help Menu provides commands to access its functions.

**Contents**

Help on Object

Using Online Help describes the different ways of using and searching in the help.

##### Methods of the GASelection

#### Methods of the GASelection

The GASelection provides:

- The Methods of Lists and Tables .
- The Methods of the DataTable .
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

#### Read-Only Attributes of the GASelection

Read-Only Attributes of the GASelection

The GASelection provides:

- The \_Read-Only Attributes of the DataTable .
- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyGASelection.UUID

**Attributes of the GASelection**

#### \_Attributes of the GASelection

The GASelection provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the DataTable .
- The Attributes of Lists and Tables .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
GASelection.CrossoverOperator := "PMX"
print GASelection.CrossoverOperator
posit := Station.cont.XPos
```

##### CrossoverOperator [SimTalk] - GASelection

Sets the procedure that reorganizes the remaining set when a crossover of the object designated by &lt;Path&gt; is executed.

Type

Attribute

Syntax

&lt; Path &gt;.CrossoverOperator:string

Assignment Value

You can assign a value of data type string .

You can specify "PMX" (Partially Matched Crossover) or "OX" (Ordered Crossover).

- "PMX" attempts to preserve the relative position and thus the sequence of items of a chromosome as far as possible. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, it will be eliminated from the remaining set and the following items will move up.
- "OX" makes the absolute position of the items take precedence over the sequence. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, this item is replaced by an item from the crossover set in chromosome 1 that is not contained in the crossover set of chromosome 2.

**Example**

GASelection.CrossoverOperator := "PMX"

See also

Crossover [GASelection] , drop-down list

##### CrossoverProb, CrossoverDelta [SimTalk] - GASelection

Sets the probability with which a crossover occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute CrossoverDelta . If the attribute CrossoverDelta takes the value 0, the probability of a crossover to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.CrossoverProb:real < Path >.CrossoverDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASelection.CrossoverProb := 0.2
GASelection.CrossoverDelta := 0
```

See also

Crossover [GASelection] , drop-down list

Start Probability [GASelection]

Delta per Generation [GASelection]

##### DataType [SimTalk] - GASelection

DataType [SimTalk] - GASelection

Sets the data type of the definition set of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DataType:string
```

Assignment Value

You can assign a value of data type string .

You can specify " Acceleration ", " Any ", " Boolean ", " Date ", " DateTime ", " Integer ", " Length ", " List ", " Money ", " Object ", " Queue ", " Real ", " Speed ", " Stack ", " String ", " Table ", " Time ", or " Weight ".

Example

```simtalk
GASelection.DataType := "integer"
```

See also

Data Type [drop-down list] - GASelection

##### InitRate [SimTalk] - GASelection

Sets the share of chromosomes in percent that may be created for the initial generation of the object designated by &lt;Path&gt; by using the initialization data.

Remarks

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

Type

Attribute

Syntax

&lt; Path &gt;.InitRate:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASelection.InitRate := 33
```

See also

Initial Rate In Percent [GASelection]

Initial Sets [GASelection]

InversionProb, InversionDelta [SimTalk] - GASelection

If the attribute Mutation takes the value false, the attribute InversionProb sets the probability of an inversion of the object designated by &lt;Path&gt; to occur in the first generation.

Remarks

This value changes for each new generation by the value of the attribute InversionDelta . If the attribute InversionDelta takes the value 0, the probability of an inversion to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.InversionProb:real < Path >.InversionDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASelection.Mutation := false
GASelection.InversionProb := 0.4
GASelection.InversionDelta := 0
```

See also

Mutation [SimTalk] - GASelection

Start Probability [GASelection] &gt; Inversion and Crossover

Delta per Generation [GASelection] &gt; Mutation

##### Mutation [SimTalk] - GASelection

Sets if the Mutation operator ( true ) or the Inversion operator ( false ) is going to be used as genetic operator of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.Mutation:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
GASelection.Mutation := true
```

See also

Inversion/Mutation [GASelection] , drop-down list MutationProb, MutationDelta [SimTalk] - GASelection If the attribute Mutation takes the value true, the attribute MutationProb sets the probability with which a mutation occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value designated by the attribute MutationDelta . If the attribute MutationDelta takes the value 0, the probability for a mutation to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.Mutation:real < Path >.MutationProb:real < Path >.MutationDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASelection.Mutation := true
GASelection.MutationProb := 0.4
GASelection.MutationDelta := 0
```

See also

Mutation [SimTalk] - GASelection , drop-down list

Start Probability [GASelection] , text box

Delta per Generation [GASelection]

##### Selection [SimTalk]

Defines the number of items from the definition set of the object designated by &lt;Path&gt; that is to be selected.

Type

Attribute

Syntax

&lt; Path &gt;.Selection:integer

Assignment Value

You can assign a value of data type integer .

Example

GASelection.Selection := 8

See also

Selection Quantity

#### GASequence

### GASequence

Define sequence tasks for the genetic algorithm with the object GASequence .

Icon

<!-- image -->

Description

To show a tooltip with information about the GASequence , hover with the mouse over it.

To change the length of the graphic and the anchor points of the GASequence , click Show Manipulators

<!-- image -->

on the Edit ribbon tab or press M on the keyboard.

Add the Object to the Simulation Model

To add the object GASequence to the Class Library , click Manage Class Library &gt; GA &gt; GASequence on the Home ribbon tab.

See also

Define Sequence Tasks with the Object GASequence

#### Dialog Box of the GASequence

Dialog Box of the GASequence

Double-click the icon of the GASequence to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

Tab Contents

Tab Contents [GASequence]

The tab Contents shows a table with these columns:

<!-- image -->

<!-- image -->

###### Define Set [GASequence]

Position Constraints

Initial Sets [GASequence]

**Note**

You can only change the column width after you deactivate Format &gt; Inherit Format .

**Define Set [GASequence]**

**Define Set [GASequence]**

Type in the total number of items the solutions consist of into the cells in the column Define Set .

Each item may only occur once. Select the data type of the definition set from the drop-down list Data Type on the tab Attributes .

<!-- image -->

**See also**

Data Type [drop-down list] - GASequence

###### Position Constraints

Type the names of sublists into the column Position Constraints for items for which you defined position restrictions.

Type in all positions (of data type integer ), which that item may occupy, into this sublist. If you do not create a sublist that item may occupy any position, i.e., no position restrictions apply to it.

<!-- image -->

**Initial Sets [GASequence]**

###### Initial Sets [GASequence]

Type the proposed start solutions into the column Initial Sets --&gt; and the following columns.

**Note**

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

<!-- image -->

**See also**

InitRate [SimTalk] - GASequence

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Initial Rate in Percent [GASequence]

Type in the share of chromosomes in percent that may be created for the initial generation by using the initialization data.

<!-- image -->

###### Data Type [drop-down list] - GASequence

Data Type [drop-down list] - GASequence

Select the Data Type of the elements of the chromosomes.

<!-- image -->

**SimTalk**

DataType [SimTalk] - GASequence

###### Number of Samples

Type in the Number of Samples after which the genetic algorithm terminates its random search for an initial solution for the start generation.

Note

This only applies if you defined Position Constraints for the sequence task.

SimTalk

NumOfGaSamples [SimTalk]

###### Number of Crossover Trials

Type in the Number of Crossover Trials that the genetic algorithm executes to realize the placements in the matching intersecting range.

<!-- image -->

A rearrangement attempt consists of the search for the cycle exchange for the items of the matching intersecting range.

Note

This only applies if you defined Position Constraints for the sequence task.

SimTalk

NumOfCrossOverTrials [SimTalk]

###### Number of Mutation Trials

Type in the Number of Mutation Trials , which the genetic algorithm executes by using cycle exchanges to meet the position restrictions you defined.

Note

This only applies if you defined Position Constraints for the sequence task.

SimTalk

NumOfMutationTrials [SimTalk]

###### Degree of Mutation Correction

Type in a number for the Degree of Mutation Correction , which is the maximum length of the cycles for a cycle exchange that a mutation triggered.

Note

This only applies if you defined Position Constraints for the sequence task with the mutation operator Fixed number of mutations .

Genetic Algorithms do not use the Degree of Mutation Correction for the mutation operator Random mutations .

SimTalk

DegreeOfCorrection [SimTalk]

Tab Genetic Operators

Tab Genetic Operators

The tab Genetic Operators provides the settings listed in the table of contents to the left.

###### Crossover [GASequence]

For sequence tasks each item may only occur once in the solution set. Crossover tasks on the other hand may violate this condition. This is why procedures are needed that reorganize the remaining set, i.e., the set that is not changed by Crossover , so that the condition is met again.

<!-- image -->

Select the type of crossover:

- OX (Order Crossover) attempts to preserve the relative position and thus the sequence of items of a chromosome as far as possible. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, it will be eliminated from the remaining set and the following items will move up.
- PMX (Partially Matched Crossover) makes the absolute position of the items take precedence over the sequence. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, this item is replaced by an item from the crossover set in chromosome 1 that is not contained in the crossover set of chromosome 2.

Then, enter a Start Probability and a Delta per Generation .

SimTalk

CrossoverOperator [SimTalk] - GASequence

CrossoverProb, CrossoverDelta [SimTalk] - GASequence

See also

Start Probability [GASequence]

Delta per Generation [GASequence]

**Start Probability [GASequence]**

###### Start Probability [GASequence]

Type in a value for the Start Probability of the respective genetic operator being applied to a newly created chromosome.

<!-- image -->

- For Mutation the probability refers to each individual item.
- For Inversion and Crossover the probability refers to the entire individual.

We found the following probabilities to yield good results:

<!-- image -->

| Mutation   | 0.01 to 0.1   |
|------------|---------------|
| Inversion  | 0 to 0.4      |
| Crossover  | 0.5 to 0.8    |

**SimTalk**

CrossoverProb, CrossoverDelta [SimTalk] - GASequence

InversionProb, InversionDelta [SimTalk] - GASequence

MutationProb, MutationDelta [SimTalk] - GASequence

Mutation [SimTalk] - GASequence

###### Delta per Generation [GASequence]

Type in a value for the Delta per Generation that sets the change of the probabilities for the respective genetic operators over the generations.

<!-- image -->

**SimTalk**

CrossoverOperator [SimTalk] - GASequence

CrossoverProb, CrossoverDelta [SimTalk] - GASequence

InversionProb, InversionDelta [SimTalk] - GASequence

Mutation [SimTalk] - GASequence

MutationProb, MutationDelta [SimTalk] - GASequence

###### Inversion/Mutation [GASequence]

Select the genetic operator.

- The Inversion Operator inverts the sequence within a defined range of the individual.
- The Mutation Operator randomly changes individual genes.

<!-- image -->

<!-- image -->

Here you can also select the mutation operator which the genetic algorithm uses:

**◦ Random mutations**

Type in a number for the Start Probability [GASequence] to define the probability for exchanging an item in the first generation.

Type in a number for the Delta per Generation [GASequence] to define the change of this probability for the genetic operators, when the generation changes.

**◦ Fixed number of mutations**

The GASequence shows the button Plan . It opens a table with four columns of data type integer where you define the number of mutations per chromosome for each generation. Decreasing the number of mutations, for example, enables you to better search for a local optimum during the end phase of the optimization. Type the first generation into the cells of the column Generation (from) , and the number of mutations for this and the following generations into the column Number of Mutations . Modify the number of mutations for a generation by typing values into another line/row of the table. Make sure that column 1 of the table is sorted in ascending order.

Type the number of positions the genetic algorithm may move an item up into the column Max. Position Offset (up) or down into the column Max. Position Offset (down) . This is called position offset restriction of a mutation (compare the Mutation Operator for sequence tasks).

If you do not type values into the columns Max. Position Offset (up) and Max. Position Offset (down) , the genetic algorithm uses a mutation without position offset restrictions.

SimTalk InversionProb, InversionDelta [SimTalk] - GASequence Mutation [SimTalk] - GASequence MutationOperator [SimTalk] MutationProb, MutationDelta [SimTalk] - GASequence MutationPlan [SimTalk] See also Mutation Operator [general description] Mutation Operator [general description] Inversion Operator

**Tab User-defined**

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

##### File Menu [lists]

The commands are described under the List Ribbon Tab .

| Import File            | Print List   |
|------------------------|--------------|
| Export to File [lists] | Print Setup  |
| Export Object File     | Close Model  |
| Text File Format       |              |

**Edit Menu [lists]**

##### Edit Menu [lists]

The commands are described under the Home Ribbon Tab and the List Ribbon Tab .

| Cut [Home ribbon]                             | Select All [Home ribbon]   |
|-----------------------------------------------|----------------------------|
| Copy [Home ribbon]                            | Insert Row [lists]         |
| Paste Contents of the Clipboard [Home ribbon] | Find [lists]               |
| Delete [Home ribbon]                          | Replace [lists]            |

##### Format Menu [lists]

The commands are described under the List Ribbon Tab .

| Activate Column Index   | Inherit Contents [lists]   |
|-------------------------|----------------------------|
| Activate Row Index      | Inherit Comment [button]   |
| Inherit Format [button] |                            |

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

##### View Menu

The commands are described under the List Ribbon Tab .

| Recompute Formulas     | Highlight Empty Cells   |
|------------------------|-------------------------|
| Show Comment [lists]   | Go To Cell              |
| Show Data Type [lists] |                         |

**Tools Menu**

##### Tools Menu

The commands are described under the Tools Menu .

##### Help Menu

The Help Menu provides commands to access its functions.

<!-- image -->

##### Methods of the GASequence

#### Methods of the GASequence

The GASequence provides:

- The Methods of the DataTable .
- The Methods of Lists and Tables .
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

#### Read-Only Attributes of the GASequence

Read-Only Attributes of the GASequence

The GASequence provides:

- The Read-only Attributes of the DataTable .
- The Read-only Attributes of Lists and Tables .
- The Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyGASequence.UUID

**Attributes of the GASequence**

#### \_Attributes of the GASequence

The GASequence provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the DataTable .
- The Attributes of Lists and Tables .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
GASequence.CrossoverProb := 0.2
GASequence.CrossoverDelta := 0
print GASequence.CrossoverProb
posit := Station.cont.XPos
```

##### CrossoverOperator [SimTalk] - GASequence

Sets the procedure that reorganizes the remaining set when a crossover is executed by the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.CrossoverOperator:string

Assignment Value

You can assign a value of data type string .

You can specify "PMX" (Partially Matched Crossover) or "OX" (Ordered Crossover).

- "PMX" makes the absolute position of the items take precedence over the sequence. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, this item is replaced by an item from the crossover set in chromosome 1 that is not contained in the crossover set of chromosome 2.
- "OX" attempts to preserve the relative position and thus the sequence of items of a chromosome as far as possible. If an item is contained in the remaining set of chromosome 1 and in the crossover set of chromosome 2, it will be eliminated from the remaining set and the following items will move up.

**Example**

GASequence.CrossoverOperator := "PMX"

See also

Crossover [GASequence] , drop-down list

##### CrossoverProb, CrossoverDelta [SimTalk] - GASequence

Sets the probability with which a crossover occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute CrossoverDelta .

If the attribute CrossoverDelta takes the value 0, the probability of a crossover to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.CrossoverProb:real < Path >.CrossoverDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASequence.CrossoverProb := 0.2
GASequence.CrossoverDelta := 0
```

See also

Crossover [GASequence] , drop-down list

Start Probability [GASequence] , text box

Delta per Generation [GASequence]

DataType [SimTalk] - GASequence

Sets the data type of the definition set of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DataType:string
```

Assignment Value

You can assign a value of data type string .

You can specify " Acceleration ", " Any ", " Boolean ", " Date ", " DateTime ", " Integer ", " Length ", " List ", " Money ", " Object ", " Queue ", " Real ", " Speed ", " Stack ", " String ", " Table ", " Time ", or " Weight ".

Example

```simtalk
GASequence.DataType := "integer"
```

See also

Data Type [drop-down list] - GASelection , drop-down list

##### DegreeOfCorrection [SimTalk]

Sets the degree of mutation correction which the object designated by &lt;Path&gt; applies.

Type

Attribute

Syntax

&lt; Path &gt;.DegreeOfCorrection:integer

Assignment Value

You can assign a value of data type integer .

Example

GASequence.DegreeOfCorrection := 1

See also

Degree of Mutation Correction

##### InitRate [SimTalk] - GASequence

Sets the share of chromosomes in percent that the object designated by &lt;Path&gt; may create for the initial generation by using the initialization data.

Remarks

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

Type

Attribute

Syntax

&lt; Path &gt;.InitRate:real

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASequence.InitRate := 35
```

See also

Initial Rate in Percent [GASequence]

Sets InversionProb, InversionDelta [SimTalk] - GASequence If the attribute Mutation takes the value false, the attribute InversionProb sets the probability of an inversion to occur in the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute InversionDelta . If the attribute InversionDelta takes the value 0, the probability of an inversion to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.InversionProb:real < Path >.InversionDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASequence.Mutation := false
GASequence.InversionProb := 0.4
GASequence.InversionDelta := 0
```

See also

Inversion/Mutation [GASequence] , drop-down list

Start Probability [GASequence] , text box

Delta per Generation [GASequence]

##### Mutation [SimTalk] - GASequence

Sets if the genetic algorithm of the object designated by &lt;Path&gt; is going to use the Mutation operator ( true ) or the Inversion operator ( false ).

Type

Attribute

Syntax

```simtalk
< Path >.Mutation:boolean
```

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
GASequence.Mutation := true
```

See also

Inversion/Mutation [GASequence] , drop-down list

##### MutationOperator [SimTalk]

Sets the mutation operator, which the object designated by &lt;Path&gt; is going to use for the setting Mutation .

Type

Attribute

Syntax

&lt; Path &gt;.MutationOperator:string

Assignment Value

You can assign a value of data type string .

You can specify "Fixed number of mutations" or "Random mutations" .

- "Fixed number of mutations"

The GASequence shows the button Plan . It opens a table with four columns of data type integer , where you define the number of mutations per chromosome for each generation. Decreasing the number of mutations, for example, enables you to better search for a local optimum during the end phase of the optimization. Enter the first generation into the cells of the column Generation (from) , and the number of mutations for this and the following generations into the column Number of Mutations . Modify the number of mutations for a generation by entering values into another line/row of the table. Make sure that column 1 of the table is sorted in ascending order.

Enter the number of positions the genetic algorithm may move an item up into the column Max. Position Offset (up) or down into the column Max. Position Offset (down) . This is called position offset restriction of a mutation (compare Mutation Operator for sequence tasks).

When you do not enter values into the columns Max. Position Offset (up) and Max. Position Offset (down) , the genetic algorithm uses a mutation without position offset restrictions.

- "Random mutations"

Enter a number for the Start Probability to define the probability for exchanging an item in the first generation.

Enter a number for the Delta per Generation to define the change of this probability for the genetic operators, when the generation changes.

**Example**

```simtalk
GASequence.MutationOperator := "Random mutations"
```

**See also**

Mutation Operator [general description] , described

Mutation [SimTalk] - GASequence

**MutationPlan [SimTalk]**

##### MutationPlan [SimTalk]

Sets the table in which you define the number of mutations per chromosome and the position offset for each generation of the object designated by &lt;Path&gt;..

Remarks

MutationPlan applies for the setting Mutation &gt; Fixed Number of Mutations .

Type

Attribute

Syntax

```simtalk
< Path >.MutationPlan:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
GASequence.MutationPlan.delete
GAsequence.MutationPlan  := MutationSteps.copy
```

See also

Mutation Operator [general description] , described

##### MutationProb, MutationDelta [SimTalk] - GASequence

Sets the probability with which a mutation occurs within the first generation of the object designated by &lt;Path&gt; when the attribute Mutation takes the value true.

Remarks

This value changes for each new generation by the value of the attribute MutationDelta .

If the attribute MutationDelta takes the value 0, the probability for a mutation to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.MutationProb:real < Path >.MutationDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASequence.Mutation := true
GASequence.MutationProb := 0.4
GASequence.MutationDelta := 0
```

See also

Start Probability [GASequence] , text box

Delta per Generation [GASequence]

##### NumOfCrossOverTrials [SimTalk]

Sets the number of crossover trials, which the object designated by &lt;Path&gt; executes.

Remarks

This only applies if you defined PositionConstraints for the sequence task.

Type

Attribute

Syntax

&lt; Path &gt;.NumOfCrossOverTrials:integer

Assignment Value

You can assign a value of data type integer .

Example

GASequence.NumOfCrossOverTrials := 2

See also

Number of Crossover Trials

Position Constraints

##### NumOfGaSamples [SimTalk]

Sets the number of samples, which the object designated by &lt;Path&gt; draws.

Type

Attribute

Syntax

```simtalk
< Path >.NumOfGaSamples:integer
```

Assignment Value

You can assign a value of data type integer .

Example

```simtalk
GASequence.NumOfGaSamples := 3
```

See also

Number of Samples

##### NumOfMutationTrials [SimTalk]

Sets the number of mutation trials, which the GASequence designated by &lt;Path&gt; executes.

Remarks

This only applies if you defined PositionConstraints for the sequence task.

Type

Attribute

Syntax

&lt; Path &gt;.NumOfMutationTrials:integer

Assignment Value

You can assign a value of data type integer .

Example

GASequence.NumOfMutationTrials := 3

See also

Number of Mutation Trials

Position Constraints

#### GARangeAllocation

### GARangeAllocation

Define allocation tasks for the genetic algorithm with the object GARangeAllocation . The individual items of the chromosomes may take values from a range defined by a minimum and a maximum , the distance of which is determined by a fixed interval .

Icon Description To show a tooltip with information about the GARangeAllocation , hover with the mouse over it.

<!-- image -->

To change the length of the graphic and the anchor points of the GARangeAllocation , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the object GARangeAllocation to the Class Library , click Manage Class Library &gt; GA &gt; GARangeAllocation on the Home ribbon tab.

See also

Define Allocation Tasks with the Objects GARangeAllocation and GASetAllocation

#### Dialog Box of the GARangeAllocation

Dialog Box of the GARangeAllocation

Double-click the icon of the GARangeAllocation to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

##### Tab Contents

##### Tab Contents

Tab Contents [GARangeAllocation]

The tab Contents shows a table with the columns Define Set and Initial Sets .

**Note**

You can only change the column width after you deactivate Format &gt; Inherit Format .

###### Define Set [GARangeAllocation]

Type in the total number of items the solutions consist of into the cells in the column Define Set .

<!-- image -->

###### Minimum [GARangeAllocation]

Type in the Minimum number of items into the cells into the column Minimum .

<!-- image -->

###### Maximum [GARangeAllocation]

Type in the Maximum number of items into the cells into the column Maximum .

<!-- image -->

**Interval [GARangeAllocation]**

###### Interval [GARangeAllocation]

Type in the Interval between the items into the cells in the column Interval .

You might, for example type in 0 , 20 , 40 , 60 , 80 , 100 for the solution items for the settings Minimum 0 , Maximum 100 , and Interval 20 .

<!-- image -->

###### Initial Sets [GARangeAllocation]

Type in the proposed start solutions into the column Initial Sets --&gt; and the following columns.

**Note**

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

<!-- image -->

**See also**

InitRate [SimTalk] - GARangeAllocation

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Initial Rate in Percent [GARangeAllocation]**

###### Initial Rate in Percent [GARangeAllocation]

Type in the share of chromosomes in percent that may be created for the initial generation by using the initialization data.

<!-- image -->

###### Data Type [drop-down list] - GARangeAllocation

Select the Data Type of the items of the chromosomes.

<!-- image -->

**Note**

If you select Date or DateTime , you have to select a value of data type Integer (meaning days) or Time as the Default Interval .

**SimTalk**

DataType [SimTalk] - GARangeAllocation

**Default Minimum**

###### Default Minimum

Type in the Default Minimum value.

<!-- image -->

The GARangeAllocation uses it if you did not specify an explicit Minimum for the item on the tab Contents .

SimTalk

StandardMinimum [SimTalk]

See also

Minimum [GARangeAllocation]

Tab Contents [GARangeAllocation]

###### Default Maximum

Type in the Default Maximum value.

<!-- image -->

The GARangeAllocation uses it if you did not specify an explicit Maximum for the item on the tab Contents .

SimTalk

StandardMaximum [SimTalk]

See also

Maximum [GARangeAllocation]

Tab Contents [GARangeAllocation]

###### Default Interval

Default Interval

Type in the Default Interval value.

The GARangeAllocation uses it if you did not specify an explicit Interval for the item on the tab Contents .

SimTalk

StandardMinimum [SimTalk]

See also

Interval [GARangeAllocation]

Tab Contents [GARangeAllocation]

Tab Genetic Operators

Tab Genetic Operators

The tab Genetic Operators provides the settings listed in the table of contents to the left.

<!-- image -->

###### Start Probability [GARangeAllocation]

Type in a a value for the Start Probability of the respective genetic operator being applied to a newly created chromosome.

<!-- image -->

- For Mutation the probability refers to each individual item.
- For Crossover the probability refers to the entire individual.

We found the following probabilities to yield good results:

| Mutation   | 0.01 to 0.1   |
|------------|---------------|
| Crossover  | 0.5 to 0.8    |

SimTalk

CrossoverProb, CrossoverDelta [SimTalk] - GARangeAllocation

MutationProb, MutationDelta [SimTalk] - GARangeAllocation

**Delta per Generation [GARangeAllocation]**

###### Delta per Generation [GARangeAllocation]

Type in a value for the Delta per Generation for the genetic operators Cross Over and Mutation over the generations.

<!-- image -->

SimTalk

CrossoverProb, CrossoverDelta [SimTalk] - GARangeAllocation

MutationProb, MutationDelta [SimTalk] - GARangeAllocation

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**File Menu**

##### File Menu

The menu commands are described under the List Ribbon Tab .

| Import File            | Print List   |
|------------------------|--------------|
| Export to File [lists] | Print Setup  |
| Export Object File     | Close Model  |
| Text File Format       |              |

##### Edit Menu

The menu commands are described under the Home Ribbon Tab and the List Ribbon Tab .

| Cut [Home ribbon]                             | Select All [Home ribbon]   |
|-----------------------------------------------|----------------------------|
| Copy [Home ribbon]                            | Insert Row [lists]         |
| Paste Contents of the Clipboard [Home ribbon] | Find [lists]               |
| Delete [Home ribbon]                          | Replace [lists]            |

**Format Menu**

##### Format Menu

The menu commands are described under the List Ribbon Tab .

| Activate Column Index   | Inherit Contents [lists]   |
|-------------------------|----------------------------|
| Activate Row Index      | Inherit Comment [button]   |
| Inherit Format [button] |                            |

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The commands are described under the List Ribbon Tab .

| Recompute Formulas     | Highlight Empty Cells   |
|------------------------|-------------------------|
| Show Comment [lists]   | Go To Cell              |
| Show Data Type [lists] |                         |

##### Tools Menu

The commands are described under the Tools Menu .

**Help Menu**

##### Help Menu

The Help Menu provides commands to access its functions.

**Contents**

Help on Object

Using Online Help describes the different ways of using and searching in the help.

##### Methods of the GARangeAllocation

#### Methods of the GARangeAllocation

The GARangeAllocation provides:

- The Methods of the DataTable .
- The Methods of Lists and Tables .
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

#### Read-Only Attributes of the GARangeAllocation

Read-Only Attributes of the GARangeAllocation

The GARangeAllocation provides:

- The \_Read-Only Attributes of the DataTable .
- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyGARangeAllocation.UUID

#### Attributes of the GARangeAllocation

\_Attributes of the GARangeAllocation

The GARangeAllocation provides:

- The attributes listed in the table of contents to the left.
- The \_Attributes of the DataTable .
- The Attributes of Lists and Tables .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
GARangeAllocation.Mutation := true
GARangeAllocation.MutationProb := 0.4
GARangeAllocation.MutationDelta := 0
print GARangeAllocation.Mutation
posit := Station.cont.XPos
```

##### CrossoverProb, CrossoverDelta [SimTalk] - GARangeAllocation

Sets the probability with which a crossover occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute CrossoverDelta . If the attribute CrossoverDelta takes the value 0, the probability of a crossover to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.CrossoverProb:real < Path >.CrossoverDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GARangeAllocation.CrossoverProb := 0.2
GARangeAllocation.CrossoverDelta := 0
```

See also

Start Probability [GARangeAllocation] , Crossover

Delta per Generation [GARangeAllocation] , Crossover

##### DataType [SimTalk] - GARangeAllocation

Sets the data type of the definition set of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DataType:string
```

Assignment Value

You can assign a value of data type string .

You can specify " Acceleration ", " Date ", " DateTime ", " Integer ", " Length ", " Money ", " Real ", " Speed ", " Time ", or " Weight ".

**Note**

If you select Date or DateTime , you have to select a value of data type Integer (meaning days) or Time as the Default Interval .

**Example**

```simtalk
GARangeAllocation.DataType := "real"
```

See also

Data Type [drop-down list] - GARangeAllocation

##### InitRate [SimTalk] - GARangeAllocation

Sets the share of chromosomes (in percent) that may be created for the initial generation of the object designated by &lt;Path&gt; by using the initialization data.

Remarks

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

Type

Attribute

Syntax

&lt; Path &gt;.InitRate:real

Assignment Value

You can assign a value of data type real .

Example

GARangeAllocation.InitRate := 33

See also

Initial Rate in Percent [GARangeAllocation]

Initial Sets [GASelection]

##### MutationProb, MutationDelta [SimTalk] - GARangeAllocation

Sets the probability with which a mutation occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute MutationDelta . If the attribute MutationDelta takes the value 0, the probability for a mutation to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.CrossoverProb:real < Path >.CrossoverDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GARangeAllocation.MutationProb := 0.4
GARangeAllocation.MutationDelta := 0
```

See also

Start Probability [GARangeAllocation] , Delta per Generation [GARangeAllocation] &gt; Mutation

**StandardInterval [SimTalk]**

##### StandardInterval [SimTalk]

The attributes StandardMaximum , StandardMinimum , and StandardInterval set the default values of the object designated by &lt;Path&gt;.

Remarks

Type

Attribute

Syntax

```simtalk
< Path >.StandardMinimum:real < Path >.StandardMaximum:real < Path >.StandardInterval:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
// definition set 0,10,20, ... 80,90,100
GARangeAllocation.StandardMinimum := 0
GARangeAllocation.StandardMaximum := 100
GARangeAllocation.StandardInterval := 10
```

See also

Default Interval , text box

StandardMaximum [SimTalk]

StandardMinimum [SimTalk]

##### StandardMaximum [SimTalk]

The attributes StandardMaximum , StandardMinimum , and StandardInterval set the default values of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.StandardMinimum:real < Path >.StandardMaximum:real < Path >.StandardInterval:real
```

**Assignment Value**

You can assign a value of data type real .

**Example**

```simtalk
// definition set 0,10,20, ... 80,90,100
GARangeAllocation.StandardMinimum := 0
GARangeAllocation.StandardMaximum := 100
GARangeAllocation.StandardInterval := 10
```

See also

Default Maximum , text box

StandardMinimum [SimTalk]

StandardInterval [SimTalk]

**StandardMinimum [SimTalk]**

##### StandardMinimum [SimTalk]

The attributes StandardMinimum , StandardMaximum , and StandardInterval set the default value range of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.StandardMinimum:real < Path >.StandardMaximum:real < Path >.StandardInterval:real
```

**Assignment Value**

You can assign a value of data type real .

**Example**

```simtalk
// definition set 0,10,20, ... 80,90,100
GARangeAllocation.StandardMinimum := 0
GARangeAllocation.StandardMaximum := 100
GARangeAllocation.StandardInterval := 10
```

See also

Default Maximum , text box

StandardMaximum [SimTalk]

StandardMinimum [SimTalk]

#### GASetAllocation

### GASetAllocation

Define allocation tasks for the genetic algorithm with the object GASetAllocation . The individual items of the chromosomes may take values from a predefined set.

Icon

<!-- image -->

Description

To show a tooltip with information about the GASetAllocation , hover with the mouse over it.

To change the length of the graphic and the anchor points of the GASetAllocation , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the object GASetAllocation to the Class Library , click Manage Class Library &gt; GA &gt; GASetAllocation on the Home ribbon tab.

See also

Define Allocation Tasks with the Objects GARangeAllocation and GASetAllocation

#### Dialog Box of the GASetAllocation

Dialog Box of the GASetAllocation

Double-click the icon of the GASetAllocation to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

<!-- image -->

Tab Contents

Tab Contents [GASetAllocation]

The tab Contents shows a table with these columns:

<!-- image -->

Define Set [GASetAllocation]

Allocation Sets

Initial Sets [GASetAllocation]

**Note**

You can only change the column width after you deactivate Format &gt; Inherit Format .

###### Define Set [GASetAllocation]

Type in the total number of items the solutions consist of into the cells in the column Define Set .

<!-- image -->

**Allocation Sets**

###### Allocation Sets

Type in the names of subtables, which hold the allocation sets for the respective items, into the column Allocation Set . Each value in the subtable is an item of the respective allocation set.

<!-- image -->

###### Initial Sets [GASetAllocation]

Type in proposed start solutions into the cells in the column Initial Sets --&gt; and the following columns.

**Note**

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

<!-- image -->

**See also**

InitRate [SimTalk] - GASetAllocation

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

**Initial Rate in Percent [GASetAllocation]**

###### Initial Rate in Percent [GASetAllocation]

Type in the share of chromosomes in percent that may be created for the initial generation by using the initialization data.

<!-- image -->

###### Data Type [drop-down list] - GASetAllocation

Select the Data Type of the items of the chromosomes.

<!-- image -->

**SimTalk**

Initial Rate in Percent [GASetAllocation]

**Default Set**

<!-- image -->

###### Default Set

To type the default values of the allocation set into the table, click this button.

The GASetAllocation uses this default set if you did not specify a value for an item into the column Allocation Sets of the table on the tab Contents .

SimTalk

DefaultSet [SimTalk]

Tab Genetic Operators

Tab Genetic Operators

The tab Genetic Operators provides the settings listed in the table of contents to the left.

###### Start Probability [general description]

Type in a value for the Start Probability of the respective genetic operator being applied to a newly created chromosome.

<!-- image -->

- For Mutation the probability refers to each individual item
- For Crossover the probability refers to the entire individual

We found the following probabilities to yield good results:

| Mutation   | 0.01 to 0.1   |
|------------|---------------|
| Crossover  | 0.5 to 0.8    |

SimTalk

CrossoverProb, CrossoverDelta [SimTalk] - GASetAllocation

MutationProb, MutationDelta [SimTalk] - GASetAllocation

**Delta per Generation [general description]**

###### Delta per Generation [general description]

Type in a value for the Delta per Generation , which sets the change of the probabilities for the respective genetic operator across the generations.

<!-- image -->

SimTalk

CrossoverProb, CrossoverDelta [SimTalk] - GASetAllocation

MutationProb, MutationDelta [SimTalk] - GASetAllocation

##### Tab User-defined

Define your own attributes as described under the Tab User-defined .

**File Menu**

##### File Menu

The commands are described under the List Ribbon Tab .

**See also**

| Import File            | Print List   |
|------------------------|--------------|
| Export to File [lists] | Print Setup  |
| Export Object File     | Close Model  |
| Text File Format       |              |

##### Edit Menu

The commands are described under the Home Ribbon Tab and the List Ribbon Tab .

| Cut [Home ribbon]                             | Select All [Home ribbon]   |
|-----------------------------------------------|----------------------------|
| Copy [Home ribbon]                            | Insert Row [lists]         |
| Paste Contents of the Clipboard [Home ribbon] | Find [lists]               |
| Delete [Home ribbon]                          | Replace [lists]            |

**Format Menu**

##### Format Menu

The commands are described under the List Ribbon Tab .

| Activate Column Index   | Inherit Contents [lists]   |
|-------------------------|----------------------------|
| Activate Row Index      | Inherit Comment [button]   |
| Inherit Format [button] |                            |

##### Navigate Menu

The commands are described under the Navigate Menu .

**View Menu**

##### View Menu

The commands are described under the List Ribbon Tab .

| Recompute Formulas     | Highlight Empty Cells   |
|------------------------|-------------------------|
| Show Comment [lists]   | Go To Cell              |
| Show Data Type [lists] |                         |

##### Tools Menu

The commands are described under the Tools Menu .

**Help Menu**

##### Help Menu

The Help Menu provides commands to access its functions.

**Contents**

Help on Object

Using Online Help describes the different ways of using and searching in the help.

##### Methods of the GASetAllocation

#### Methods of the GASetAllocation

The GASetAllocation provides:

- The Methods of Lists and Tables .
- The Methods of the DataTable .
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

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

#### Read-Only Attributes of the GASetAllocation

Read-Only Attributes of the GASetAllocation

The GASetAllocation provides:

- The \_Read-Only Attributes of the DataTable .
- The \_Read-Only Attributes of Lists and Tables .
- The \_Read-Only Attributes of All Objects .

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

print MyGASetAllocation.UUID

#### Attributes of the GASetAllocation

\_Attributes of the GASetAllocation

The GASetAllocation provides:

- The attributes listed in the table of contents to the left.
- The Attributes of Lists and Tables .
- The \_Attributes of the DataTable .
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
GASetAllocation.InitRate := 33
print GASetAllocation.MutationProb
posit := Station.cont.XPos
```

##### CrossoverProb, CrossoverDelta [SimTalk] - GASetAllocation

Sets the probability with which a crossover occurs within the first generation of the object designated by &lt;Path&gt;.

Remarks

This value changes for each new generation by the value of the attribute CrossoverDelta .

If the attribute CrossoverDelta takes the value 0, the probability of a crossover to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.CrossoverProb:real < Path >.CrossoverDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASetAllocation.CrossoverProb := 0.2
GASetAllocation.CrossoverDelta := 0
```

See also

Start Probability [general description] , Crossover

Delta per Generation [general description] , Crossover DataType [SimTalk] - GASetAllocation Sets the data type of the definition set of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DataType:string
```

Assignment Value

You can assign a value of data type string .

You can specify " Acceleration ", " Any ", " Boolean ", " Date ", " DateTime ", " Integer ", " Length ", " List ", " Money ", " Object ", " Queue ", " Real ", " Speed ", " Stack ", " String ", " Table ", " Time ", or " Weight ".

Example

```simtalk
GASetAllocation.DataType := "string"
```

See also

Data Type [drop-down list] - GASetAllocation

##### DefaultSet [SimTalk]

DefaultSet [SimTalk]

Sets the default values of the allocation set of the object designated by &lt;Path&gt;.

Type

Attribute

Syntax

```simtalk
< Path >.DefaultSet:table
```

Assignment Value

You can assign a value of data type table .

Example

```simtalk
GASetAllocation.DataType := "boolean"
GASetAllocation.DefaultSet.delete
GASetAllocation.DefaultSet[1,1] := true
GASetAllocation.DefaultSet[1,2] := false
```

See also

Default Set , button

##### InitRate [SimTalk] - GASetAllocation

Sets the share of chromosomes (in percent) that may be created for the initial generation of the object designated by &lt;Path&gt; by using the initialization data.

Remarks

The genetic algorithm does not use each and every Initial Set as chromosome of an individual, but randomly selects them. This means that some chromosomes of an individual might be used more than once while others are not used at all.

Type

Attribute

Syntax

&lt; Path &gt;.InitRate:real

Assignment Value

You can assign a value of data type real .

Example

GASetAllocation.InitRate := 33

See also

Initial Rate in Percent [GASetAllocation]

Initial Sets [GASetAllocation]

MutationProb, MutationDelta [SimTalk] - GASetAllocation

Sets the probability with which a mutation of the object designated by &lt;Path&gt; occurs within the first generation.

Remarks

This value changes for each new generation by the value of the attribute MutationDelta .

If the attribute MutationDelta takes the value 0, the probability for a mutation to take place during the evolution cycle does not change.

Type

Attribute

Syntax

```simtalk
< Path >.MutationProb:real < Path >.MutationDelta:real
```

Assignment Value

You can assign a value of data type real .

Example

```simtalk
GASetAllocation.MutationProb := 0.4
GASetAllocation.MutationDelta := 0
```

See also

Start Probability [general description] , text box

Delta per Generation [general description]

