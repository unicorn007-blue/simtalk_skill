#### Model Tugger Trains

Tugger trains are widely used in materials handling. They may be manned or unmanned vehicles pulling trailers or trolleys moving on paved surfaces, for example at airports, or they may be trains consisting of a tractor pulling trailers on rail-bound systems, such as on an AGVS , etc.

The tugger train always consists of a powered vehicle, the tractor , which pulls one or more non-powered loaded trailers behind it or pushes them in front of it. In Plant Simulation the tractor can be located at any position within the train, at the front, at the back, or in the middle.

**Note**

Automatic routing only works if you type the Destination into the tractor .

**Note**

Plant Simulation treats a tugger train as a single object, when the Track/TwoLaneTrack , on which it drives, has a limited capacity .

**Note**

You can only move the first Transporter of a tugger train in an exit control with the method move . The methods insert and transfer do not work at all. You cannot move following Transporters ; you can only move the first Transporter in an exit control , not at an arbitrary position on the Track/TwoLaneTrack .

You can create a tugger train with the context menu command Create Tugger Train [2D] in 2D or Create Tugger Train [3D] in 3D by right-clicking the first and the last Transporter in the Frame .

The tractor and all trailers do not have to touch, as long as all Transporters are located all the way on the same Track/TwoLaneTrack . If necessary Plant Simulation moves the other Transporters up to the frontmost Transporter or tractor .

Instead, you can also hitch Transporters to other Transporters with the methods hitchFront and hitchRear .

<!-- image -->

Compare the sample models: Click the Window ribbon tab, click Start Page &gt; Getting Started &gt; Example Models &gt; Small Examples . Then, select the respective Category , the Topic , and the Example in the dialog Examples Collection , and click Open Model .

<!-- image -->

<!-- image -->

##### Hitching and Unhitching Transporters

To create a tugger train , you can hitch Transporters to other Transporters by right-clicking the first and the last Transporter , which you would like to hitch to each other, and by selecting Create Tugger Train on the context menu.

Instead, you can also use the methods hitchFront and hitchRear .

<!-- image -->

**Note**

When you hitch up two tugger trains , both of which have a tractor , Plant Simulation deactivates the attribute IsTractor of the train that is hitching up. The tractor of the train in front in the direction of motion then pulls the entire train.

To unhitch a Transporter from the train, use the methods unhitchFront and unhitchRear .

The read-only attribute GetFrontWagon returns the trailer which is hitched to the front of the active trailer in the direction of the Track/TwoLaneTrack on which they move.

The read-only attribute GetRearWagon returns the trailer which is hitched to the rear of the active trailer in the direction of the Track/TwoLaneTrack on which they move.

<!-- image -->

See also

Program the Collision Control

Create Tugger Train [3D]

##### Designating the Tractor

Designate the tractor of the tugger train , which pulls or pushes the trailers , by selecting the check box Is Tractor .

If you use the attribute IsTractor , this only applies to a Transporter , which is part of a tugger train . Each train has a single tractor for which the attributes relating to the battery and the driving behavior apply.

<!-- image -->

<!-- image -->

The Transporter then shows the icon tractor in 2D instead of the icon Operational . As a vector graphic the icon of the tractor looks like this . To find out which Transporter is the tractor of a train, you can use the read-only attribute GetTractor .

**Note**

To prevent the tractor from loading parts, type in 0 as the X-Dimension and the Y-Dimension for the Loading Space Type &gt; Store . For the loading space types Track and Line , type in 0 as the Capacity .

<!-- image -->

A tugger train evaluates the Destination of the tractor for Automatic Routing .

If the frontmost Transporter in the direction of motion is moved, the tugger train uses the Destination of the tractor for determining the successor with destination lists.

If the frontmost Transporter of a tugger train in the direction of motion exits the Destination object, the Destination Control of the tractor will be executed.

Sensors which only trigger actions, when the Transporter has the same destination as the sensor , evaluates the Destination of the tractor for all Transporters of a tugger train .

See also

Is Tractor [check box]

Define the Tractor of the Tugger Train

##### Failures and Pauses [tugger train]

Plant Simulation passes a failure of a trailer on to all members of the train and records it for statistics purposes.

If several trailers of a train fail, naturally none of them arrives at the Availability you set. As soon as any member of the tugger train fails, the entire train stops.

##### Controls of the Tugger Train

Each trailer of the tugger train activates all Sensor Controls of the Track / TwoLaneTrack . The material flow considers a tugger train as a single unit.

The tractor can pull or push the trailers . The front of the train is the front of the first Transporter in the direction in which the Track/TwoLaneTrack points. The same is true for the rear of the train. The Front or the Rear of the train activates the Entrance Controls and Exit Controls as well as the Destination and the Routing Controls .

**Note**

The Front of the Transporter always moves toward the end of the Track/TwoLaneTrack into the direction with which you inserted it along the direction of motion of the material flow.

If you insert a Track/TwoLaneTrack from left to right, the Front of the Transporter is located on the right-hand side and moves toward the right.

If you insert a Track/TwoLaneTrack from right to left, the Front of the Transporter is located on the left-hand side and moves toward the left.

<!-- image -->

This also applies to Transporters which drive Backward when you select the check box Backwards of the Transporter ! The Front of the Transporter keeps on pointing toward the end of the Track into the direction with which you inserted it along the direction of motion of the material flow.

- If a Track/TwoLaneTrack is connected with a Conveyor or a point-oriented object with a Connector , the train stops, when the Front or the Rear of the train reaches the Track/TwoLaneTrack .
- If you select Entrance Locked or Exit Locked before the train has completely left the Track/ TwoLaneTrack , the train can still pass its entrance or exit.
- If a tugger train collides, the Collision Control of the tractor will always be triggered. Within the control method the anonymous identifier @ is the Transporter , which actually collides, while the anonymous identifier ? designates the tractor of the train.

