### Removing Parts with the Dismantle Station

#### Remove Parts with the Dismantle Station

<!-- image -->

The DismantleStation removes mounting parts from a main part.

You can insert the DismantleStation into your simulation model from the folder Material Flow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In this sample model we demonstrate how to remove parts from a car in a junk yard with the DismantleStation .

In our example we will:

- Configure the Source Where the Cars Enter the Junk Yard
- Configure the Dismantle Station That Removes the Parts
- Configure the Station That Tests the Parts
- Configure the Station That Distributes the Removed Parts
- Open the Dismantle Model in 3D

The finished simulation model looks like this in 2D:

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

Back to Modeling the Material Flow

#### Configure the Source Where the Cars Enter the Junk Yard

The Source produces parts of type Car and moves them on a Conveyor to the DismantleStation . It removes the trunk lid , the outside mirrors , and the wheels and sends the stripped car in to the scrap press . The removed parts are sent on to the station TestParts , which checks if they can be resold or not. It sends the good parts on to the respective Drain , which removes them from the scrap yard proper. The bad parts, on the other hand, are moved to the scrap press .

Insert and configure the Source which produces the parts:

- Select how the Source CarsIn produces the parts. We selected an adjustable interval and the uniform distribution .
- Select the type of part which the Source is to produce. We selected Car in our example.

<!-- image -->

With these settings the Source CarsIn creates cars whose inter-arrival time is uniformly distributed between 29 and 35 minutes.

Back to Remove Parts with the Dismantle Station

#### Configure the Dismantle Station That Removes the Parts

Insert and configure the DismantleStation which removes the mounting parts from the main part. In our example it removes the trunk lid , the outside mirrors , and the wheels from the car:

- Select the Sequence in which it moves the parts on to its successors. We selected Main MU after other MUs , which means that it first moves the mounting parts-trunk lid, outside mirrors, wheels in our case-on to the successor, and then the main MU , the stripped car in our case.

We then clicked Dismantle Table and entered the required information about the mounting parts which we want to remove:

- We want to remove 4 wheels and send them on to the successor with the number 2 of the DismantleStation .
- We want to remove 2 mirrors and send them on to the successor with the number 2 .
- We want to remove 1 trunkLid and send it on to the successor with the number 2 .
- Select the Dismantle Mode . We used the default setting Create MUs ; the DismantleStation then creates a new part for each successor and moves that part there.
- Select the successor to which the main MU , the stripped car in our case, moves. We used the default setting 1 .
- Select if the DismantleStation moves the main MU or a new MU in to its successor. We used the default setting Main MU .

<!-- image -->

As removing the parts also takes up some time, we entered 30 minutes as the Processing Time on the tab Times .

As we want to also show that the parts were removed from the car, we drew an icon of the car without these parts. This icon has the number 1.

To make the successor line display the picture of the stripped car, we created an Entrance Control for this Conveyor and programmed it to switch to the icon with the number 1 once the car moves onto it.

<!-- image -->

@.CurrIconNo := 1

The result looks like this:

<!-- image -->

Back to Remove Parts with the Dismantle Station

#### Configure the Station That Tests the Parts

Insert and configure the station which checks if the quality of the parts is good enough to be sold or if they have to be scrapped.

In our example we used a Station which we named TestParts . Except for the Exit Strategy you can use it with its default settings.

- As we want a certain percentage of the parts to be bad, we selected the strategy Percentage . The test station then moves the parts on to its successors according to a percentage distribution.
- We then clicked Open List and entered the percentages of the parts that are sent on to the two successors.
- 10 percent of the parts are sent on to the successor with the number 1 . These parts are bad and have to be scrapped; they end up in the scrap press .

- 90 percent of the parts are sent on to the successor with the number 2 . These parts are good enough to be sold.

<!-- image -->

<!-- image -->

Back to Remove Parts with the Dismantle Station

#### Configure the Station That Distributes the Removed Parts

Insert and configure the station which distributes the removed parts according to their types.

We decided to use a FlowControl which moves the parts on to the type-specific Drains according to an attribute of the respective part.

- We selected the Exit Strategy &gt; MU Attribute .
- We then clicked Open List and entered the required information into the Attribute List . We used the attribute Name of all parts. For this reason we only have to enter Name once into the column Attribute and can leave these cells empty for the remaining two parts.
- We entered Name , followed by the value of the attribute, namely Wheel , followed by the number of the successor onto which the part is to be moved, namely 1 .
- We then entered Mirror , followed by the number of the successor , namely 2 .
- We finally entered TrunkLid , followed by the number of the successor , namely 3 .

<!-- image -->

Start the simulation and watch how the DismantleStation removes the trunk lid , the outside mirrors , and the wheels from our car . The stripped car is sent straight on to the scrap press , while the removed parts are sent to the test station which checks if they are good or bad. The bad ones are sent to the scrap press , while the parts, which can be resold, are distributed to the respective Drains .

<!-- image -->

You can also view the Statistics Report at the end of the simulation run ( F6 ) which contains detailed statistics information.

<!-- image -->

You can extend this model at will, for example to remove more parts, such as the engine, doors, bumpers, fenders, etc. You can also add Workers , who carry parts from station to station and who test and sell parts as we did in the scrap yard model in the examples collection .

**Back to Remove Parts with the Dismantle Station**

##### Open the Dismantle Model in 3D

As we originally created the model in 2D, we now open it in 3D by clicking on the Start ribbon tab.

It then looks like this:

<!-- image -->

<!-- image -->

We are going to make some adjustments so that the model looks pleasing in 3D:

<!-- image -->

- We delete the graphic named Default of the Frame as we do not need it in the model.
- We activate Captions of the objects to allow us to identify them. To do so, we click the object and press the spacebar . We change to the tab Captions and activate Name/label activated .

<!-- image -->

We repeat this for all objects in the model. We can hide or show all captions by clicking the button

<!-- image -->

- We assign the dismantled parts wheel , mirror , and trunk lid a different material each as we do not have a 3D graphic for them at the moment.

We click the object with the right mouse button on the Class Library and select Open in 3D . We click the graphic named Default of the object and press the spacebar . We change to the tab Material , select Material active , and select a color. Our wheel is blue, our mirror is red, and our trunk lid is green. This then looks like this:

<!-- image -->

- We finally move the conveyors closer to the stations so that the connect directly. This then looks like this:

Back to Remove Parts with the Dismantle Station

<!-- image -->

