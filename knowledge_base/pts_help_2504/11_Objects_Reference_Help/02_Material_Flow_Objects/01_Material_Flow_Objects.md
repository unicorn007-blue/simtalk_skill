### Material Flow Objects

- Use the Conveyor for modeling a conveyor system or a part thereof.
- Use the Cycle for synchronizing the transfer of parts from station to station.
- Use the DismantleStation for removing mounting parts from a main part.
- Use the Drain for removing the parts from the plant after they have been processed. It usually represents the shipping department of your plant.
- Use the FlowControl for modeling strategies for splitting-up and bringing together the flow of materials in your plant.
- Use the ParallelStation for modeling stations for processing several parts in parallel at the same time.
- Use the PickAndPlace Robot for picking up a part at one station, rotating it, and placing it onto another station.
- Use the PlaceBuffer for temporarily holding parts in a row, one behind the other.

By default the PlaceBuffer to process parts on a number of buffer places, which are arranged in a row, one behind the other. It is not part of the built-in objects that the Toolbox provides. You can add it at any time to your simulation model by clicking Manage Class Library on the Home ribbon tab.

- Use the Sorter for sorting parts according to different sort criteria.
- Use the Source for producing the parts that move through your model. It usually represents the receiving department of your plant or the main machine producing the parts.
- Use the Station for processing parts on a single processing place. You'll use it for modeling most of your machines.
- Use the Store for storing parts.
- Use the Track for modeling a part of a transport line, with or without automatic routing , on which the Transporter drives and moves parts.
- Use the Turnplate for modeling a rotating platform, which rotates the loaded parts and ensures the uniform orientation of the leaving parts.
- Use the Turntable for modeling a rotating platform, which moves the part onto one of several connected material flow objects and/or turns it around.
- Use the TwoLaneTrack for modeling a transport line with two lanes on which Transporter traffic moves in opposing directions.
- The mobile objects which the material flow objects process or which transport materials:
- Use the Container for modeling pallets, bins, boxes, etc.
- Use the Part for modeling parts being produced and transported.
- Use the Transporter for modeling self-propelled vehicles allowing it to drive on its own on a Track or TwoLaneTrack or freely within the plant and to transport parts.

- The resource objects , which represent the workers and stations related to them:
- Use the AGVPool for creating automated guided vehicles ( AGVs ). You can then model AGV systems in your installation in which the AGVs are not bound to a permanently installed route network.
- Use the Broker for brokering offered services and required services. You might model the supervisor of an plant or the foreman of a shop with it.
- Use the Exporter for providing and exporting services. It represents a group of people, whose individual members you cannot distinguish and whom you cannot address as individuals.
- Use the FootPath for modeling a path on which the Worker walks from the WorkerPool to the Workplace .
- Use the LockoutZone for combining a group of material flow objects. If one of these stations fails, all other stations within the lockout zone stop processing their parts as well.
- Use the Marker for setting waypoints in your simulation model along which the Automated Guided Vehicle drives from the AGVPool to its destination .
- Use the ShiftCalendar for modeling the shifts worked in your plant.
- Use the Worker for doing a job on a workplace at a station.
- Use the WorkerPool for modeling the lounge or the staff room of your plant.
- Use the Workplace for modeling the actual place at the station, where the Worker performs his job.
- In addition Plant Simulation provides the TransferStation for loading and unloading stations.

**See also**

Shared Properties of the Material Flow Objects

Shared Properties of the Mobile Objects

