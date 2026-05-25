#### How the Transporter Gets to Its Destination

When you assign the Transporter a Destination , it decides how to get there.

You specify the Destination either on the Tab Controls by typing a destination into the text box Destination or by assigning the destination to the attribute Destination .

**Note**

Automatic routing for tugger trains only works when you type the Destination into the tractor .

The Transporter proceeds as follows to find its destination:

- If you define an Exit Control , the Exit Control determines to which object the Transporter drives. It does not consider the Destination .
- If you do not define an Exit Control , the Forward Destination list or the Backward Destination list of the Tracks/TwoLaneTracks , which are connected to the Track/TwoLaneTrack on which the Transporter is driving, determine to which successor respectively predecessor the Transporter will drive.

The Transporter searches the Destination Lists of all the successors/predecessors for the Destination you typed in, and, once it finds it, drives to the respective successor/predecessor. Plant Simulation terminates the search after it found the Destination for the first time.

- If the Transporter does not find the Destination and if you activated Automatic Routing , Plant Simulation automatically computes the shortest route to the Destination along the direction of motion. The route can include connected Tracks/TwoLaneTracks , Sub-Frames or surrounding Frames , as long as they are connected with Connectors . The Transporter then drives to the computed Destination .
- If you did not type in a Destination for the Transporter , or both the Destination Lists and Automatic Routing could not determine the successor/predecessor, the Driving Control of the Transporter determines the successor/predecessor.
- If none of the above determined the successor/predecessor, the Exit Strategy sends the Transporter to its Destination .

Show the Route of the Transporter

Drag the mouse over the Transporter to show its name, its current location, its destination, and the previous route in a Tooltip .

<!-- image -->

The command View &gt; Route to Destination selects the objects that are part of the route to the destination in the Frame .

<!-- image -->

As opposed to the Part and the Container , the Transporter commits to a fixed route to the destination from the start. If several alternative routes of the same length exist, all Transporters take the same route.

**See also**

Model Tugger Trains &gt; Model a Tugger Train

Model a Battery-powered Transporter, Basic

Model a Battery-powered Transporter, Extended

Model an Automated Guided Vehicle System (AGVS)

Routing and Driving Properties

##### Model Tugger Trains

