#### Simulating Random Processes

When simulating random processes, Plant Simulation automatically uses a random number stream of its own for each and every material flow object.

Each Station for example has its own random number stream that will be used for determining the Processing Time , the Set-up Time , the Recovery Time , and the Cycle Time .

<!-- image -->

In addition, Plant Simulation assigns each failure profile its own random number stream.

<!-- image -->

Plant Simulation shows the selected failure profile blue on the tab Failures . It shows a failed failure profile red.

To run several simulation runs with different random numbers, you do not have to change settings in the Random Number Seed Values table, but set a different value by selecting Tools &gt; Random Numbers Variant in the EventController and entering a different number. When you change this number, Plant Simulation will generate other random number streams for all objects in the model as well as for the Distribution Functions .

To create different random numbers each time when you reset the simulation model, select Tools &gt; Increment Variant on Reset in the dialog of the EventController .

Instances of Transporters and Workers use the random number seed value of the class and the ID of the instance to initialize their random number streams. This means that each Transporter and Worker will generate different failure times. When you run the simulation again with the same random numbers variant of the EventController , the Transporter or Worker with the same ID will generate the same random numbers .

<!-- image -->

You may, at times, want to use the same random numbers for two objects. You might, for example, want to compare two production Conveyors , and insert two identical Source objects, which are going to create identical parts within identical intervals. To accomplish this, you need to set the random number seed value for the affected material flow objects to the same value, i.e., assign the same value to the attribute RandomSeed . When you create a new object, for example by inserting it into a simulation model, Plant Simulation automatically assigns a unique random number seed value to this object.

Plant Simulation uses the random number seed value together with the random numbers variant of the EventController to initialize the random number streams of the object. If the object has more than one random number stream, if for example the object has failure profiles, each random number stream will automatically be initialized differently.

In addition, you can open the Random Number Seed Values table for the Distribution Functions , such as z\_uniform , z\_normal , etc., under File &gt; Options and change the values there. Identical seed values mean that the associated streams create identical random numbers as long as the identical distribution functions are called with the same parameters.

<!-- image -->

In addition, each user-defined attribute of data type randtime has its own random number seed value . Plant Simulation assigns this value uniquely, but you can change it afterward if need be.

See also

RandomSeed [SimTalk] - material flow objects

Random Number Seed Values table

Increment Variant on Reset of the EventController

IncrementRandomNumbersVariantOnReset [SimTalk] of the EventController

Random Numbers Variant of the EventController

RandomNumbersVariant [SimTalk] of the EventController

Model Random Processes

setRandomSeedCounter [SimTalk]

