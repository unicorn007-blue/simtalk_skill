### Convey Parts Laterally with the Converter

You can use the Converter to convey a part either straight through or for conveying it to the left-hand side or right-hand side.

You can insert the Converter into your simulation model from the folder MaterialFlow in the Class Library or from the toolbar Material Flow in the Toolbox .

<!-- image -->

In our examples we will demonstrate how to:

- Convey Parts Straight Through

- Convey Parts Laterally According to Their Name
- Convey Parts According to a Strategy Control
- Send Parts to the Default Exit
- Feed Parts from a Branch Line into the Main Line

As we originally created the models in 2D, we continue using some screenshots of the 2D models which show the direction of the parts with the directional arrow more clearly than 3D.

Back to Modeling the Material Flow

#### Convey Parts Straight Through

In this basic sample model we demonstrate how you can use the Converter with its default settings, i.e., without changing anything.

The Source produces parts and moves them on to the connected Conveyor . The Converter passes the parts straight through to the succeeding Conveyor .

The finished simulation model looks like this:

<!-- image -->

To create the simulation model, insert the objects so that they match the screenshot above. You can use the Conveyors and the Converter as you inserted them, i.e., without changing their settings.

<!-- image -->

To limit the number of parts in the plant, the Source produces 5 parts only.

<!-- image -->

Start the simulation and watch how the parts move on the Conveyors and how the Converter conveys them straight through in the direction of motion, first from right to left and then from bottom to top. The notch of the part is located on its right side

Back to Convey Parts Laterally with the Converter

<!-- image -->

#### Convey Parts Laterally According to Their Name

Convey Parts Laterally According to Their Name

In this sample model the Source produces six different types of parts with a different frequency each. The parts move over a number of Conveyors to two pairs of Converters , which-according to their nameconvey them laterally onto and remove them laterally from two different processing stations.

In our examples we will:

- Configure the Source that Produces the Parts [Converter]
- Configure the Converters that Convey Parts to and from ProcessingA
- Configure the Stations ProcessingA and ProcessingB
- Configure the Converters that Transport Parts to and from ProcessingB

The finished simulation model looks like this:

Back to Convey Parts Laterally with the Converter

<!-- image -->

Configure the Source that Produces the Parts [Converter, laterally]

Insert and configure the Source which produces the parts:

- Select the time and the interval at which the parts are to be produced.
- We selected an adjustable interval and a normally distributed time in our example, as shown in the screenshot below.

<!-- image -->

- Select the type of part to be used and how these parts are to be produced.
- We selected a random frequency .
- We selected the name of the Frequency Table , which we inserted before, namely the DataTable named MyParts . Selecting the table automatically applied the correct format.
- We entered the required information, as shown in the screenshot below.

<!-- image -->

The Source then produces the parts with the settings above and the Converters convey them sideways to the stations ProcessingA or ProcessingB respectively.

Back to Convey Parts Laterally According to Their Name

##### Configure the Converters that Convey Parts to and from ProcessingA

Insert and configure the Converters that convey the parts to and from the station ProcessingA :

- As we want to convey the parts laterally to the station ProcessingA or ProcessingB respectively depending on their name, we opened ConverterToA and selected the Strategy &gt; MU Name .
- We then clicked Open List and entered the names of the parts which we want to move to the station ProcessingA into the list. We want the parts named A1 , A2 , and A3 to be conveyed laterally to the left , so we entered their names and selected side 3 in the attribute list. As you remember, the numbers designate the side of the Converter at which the part exits.
- As we want to convey the parts arriving from ProcessingA straight on, we opened ConverterFromA and selected the Strategy &gt; MU Name .
- We then clicked Open List and entered the names of the parts which we want to move on into the list. We want the parts named A1 , A2 , and A3 to be conveyed straight on , so we entered their names and selected side 0 in the attribute list.

<!-- image -->

Back to Convey Parts Laterally According to Their Name

<!-- image -->

Configure the Stations ProcessingA and ProcessingB

Insert and configure the processing stations, which process the parts for the specified time before feeding them back into the factory:

- We inserted two stations of type ParallelStation in our sample model.
- Enter the capacity of the processing stations. We entered 5 as the X-Dimension and as the Y-Dimension respectively. This results in 25 processing places on each station.
- Enter a Processing Time . We decided to use a normally distributed time with the settings below.

<!-- image -->

Back to Convey Parts Laterally According to Their Name

<!-- image -->

Configure the Converters that Transport Parts to and from ProcessingB

Insert and configure the Converters that convey the parts to and from the station ProcessingB :

- As we want to convey the parts laterally to the station ProcessingB depending on their name, we opened ConverterToB and selected the Strategy &gt; MU Name .
- We then clicked Open List and entered the names of the parts which we want to move to the station ProcessingB into the list. We want the parts named B1 , B2 , and B3 to be conveyed laterally to the left , so we entered their names and selected side 3 in the attribute list. As you remember, the numbers designate the side of the Converter at which the part exits.

<!-- image -->

- As we want to convey the parts arriving from ProcessingB straight on, we opened ConverterFromB , and selected the Strategy &gt; MU Name .
- We then clicked Open List and entered the names of the parts which we want to move on into the list. We want the parts named B1 , B2 , and B3 to be conveyed straight on , so we entered their names and selected side 0 in the attribute list.
- Start the simulation and watch how the Converters convert the parts laterally to the left and straight on depending on their name. To better recognize that they do this correctly, we drew an icon with an arrow pointing in the direction of motion.

<!-- image -->

You will notice that the right hand side of the part points downwards after it has moved from ConverterToB into the processing station. This is because moving the part laterally to the left rotates it 90 degrees clockwise.

Once the part moves from the processing station to ConverterFromB , it is rotated another 90 degrees clockwise, thus moving backward toward the Drain , which removes it from the installation.

The directional arrows on the parts in the 2D model illustrate the conveying direction.

Back to Convey Parts Laterally According to Their Name

<!-- image -->

#### Conveying Parts According to a Strategy Control

Convey Parts According to a Strategy Control

In this sample model the Source produces 10 parts each of three different types. It moves the parts to a Converter , which conveys them laterally to the left, laterally to the right, or straight through according to their names. We programmed where exactly each type goes in a strategy control .

In our examples we will:

- Configure the Source that Produces the Parts [Converter, laterally]
- Configure the Converter that Conveys the Parts

The finished simulation model looks like this:

Back to Convey Parts Laterally with the Converter

<!-- image -->

Configure the Source that Produces the Parts [Converter]

Insert and configure the Source which produces the parts:

- Select when and how many parts of a certain type are to be produced. We selected a Delivery Table in our example, as shown in the screenshot below.

<!-- image -->

- We then selected the name of the delivery table, which we inserted before, namely the DataTable . Selecting it automatically applied the correct format.

We entered the required information, as shown the screenshot below.

<!-- image -->

The Source then produces the parts with the settings above and the Converter conveys them to the connected objects.

##### Back to Convey Parts According to a Strategy Control

Configure the Converter that Conveys the Parts

Insert and configure the Converter that conveys the parts:

- As we want to convey the parts-depending on their type-laterally or straight on to the stations connected to the Converter , we select the Strategy &gt; Method .

<!-- image -->

- To create the control, we right-clicked into the text box Strategy Method and selected Create Control . Plant Simulation then entered self.OnStrategy and opened the method.

We then typed in the following source code. It conveys the parts named A laterally to the left, i.e., to exit 3 of the Converter , the parts named B laterally to the right, i.e., to exit 1, and the parts named C straight on, i.e., to exit 0 of the Converter .

```simtalk
param entranceNo: integer
if @.name = "C"
	?.ExitForMU := 0 /* number of the exit of the converter*/
elseif @.name = "A"
	if entranceNo = 2
		?.ExitForMU := 3
	else
		?.ExitForMU := 0
	end
else
	if entranceNo = 2
		?.ExitForMU := 1
	else
		?.ExitForMU := 0
	end
end
```

- Start the simulation and watch how the Converter first moves the 10 parts named A laterally to the left, the 10 parts named B laterally to the right, and the 10 parts named C straight on.

The directional arrows on the parts in the 2D model illustrate the conveying direction.

Back to Convey Parts According to a Strategy Control

<!-- image -->

#### Send Parts to the Default Exit

In this sample model the Converter sends all arriving parts to the Default Exit , which we select.

To create the simulation model, insert the objects so that they match the screenshot below.

The finished simulation model looks like this:

<!-- image -->

To make the Converter move the parts to the default exit on the respective succeeding Conveyor , open the dialog of the Converter .

- Select the Strategy &gt; Default Exit .
- Select the number of the Default exit . We selected 3 as we want all parts to exit upward. As you surely remember, the exits are numbered like this:

<!-- image -->

Start the simulation and watch how the parts move on the Conveyors and how the Converter conveys them to the exit with the number you selected, 3 in our case.

Back to Convey Parts Laterally with the Converter

<!-- image -->

#### Feed Parts from a Branch Line into the Main Line

In this sample model the Converter feeds parts from a branch line into the main line, once the gap, which you enter, is big enough to accommodate the part.

To create the simulation model, insert the objects so that they match the screenshot below.

The finished simulation model looks like this:

<!-- image -->

Insert and configure the Source which produces the parts moving on the main line:

- Select when the parts are to be produced. We entered a constant interval of 30 seconds, meaning that the Source produces a part every 30 seconds.
- Select which part type is going to be produced. We selected the part named Part , to which we added a direction arrow in its icon.

<!-- image -->

To make the Converter feed the parts from the branch line into the main line, provided the gap between the parts on the main line is big enough, open the dialog of the Converter .

- Select the Strategy &gt; Feed in .
- Enter the size of the gap between the parts. We entered a gap of 5 meters.

<!-- image -->

Start the simulation and watch how the Converter moves the parts from the branch line into the main line and conveys them with the orientation in which they were fed in.

<!-- image -->

Back to Convey Parts Laterally with the Converter

