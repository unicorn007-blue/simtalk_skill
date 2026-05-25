### Shared Properties of the Mobile Objects

The three MU classes share a number of properties and features.

They mainly differ in their loading capacity and in their way of moving:

- The Part represents a single workpiece, such as a cylinder head, a crankshaft, etc. that is going to be processed.
- The Container transports other parts. It might represent pallets, bins, boxes, etc. in your plant into which parts are placed. You can assign it a Dimension , i.e., a Capacity .
- The Transporter represents self-propelled vehicles allowing it to drive on its own on a Track / TwoLaneTrack and transporting Parts , Containers and other Transporters . It uses the Capacity , the Speed , and the Acceleration which you define, when driving forward or in reverse.

You can hitch up several Transporters to create Tugger Trains .

You can also model automatically guided vehicle-systems with the Transporter and with the Resource Objects AGVPool and Marker where the Transporter drives freely within the area of the simulation model.

See also

Dialog Box of the Mobile Objects

LEDs and States of the Mobile Objects

Statistics of the Mobile Objects

