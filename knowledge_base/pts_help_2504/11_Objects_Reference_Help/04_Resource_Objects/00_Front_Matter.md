## Resource Objects

Plant Simulation provides the resource objects to represent the Workers and the objects related to them for doing their job.

<!-- image -->

<!-- image -->

- Use the AGVPool for creating automated guided vehicles (AGVs).
- Use the Broker for brokering services offered and services required. The Broker might represent the supervisor of your plant who assigns jobs to the individual Workers .
- Use the Exporter for providing and exporting services. It represents a group of people, whose individual members you cannot distinguish and whom you cannot address as individuals.

- Use the FootPath for modeling a path on which the Worker walks from the WorkerPool to the Workplace .
- Use the LockoutZone for controlling a group of material flow objects. If one of these objects fails, all other objects within the lockout zone stop processing parts
- Use the Marker for setting milestones along which the AGVs drive from the AGVPool to their destination.
- Use the ShiftCalendar for modeling a shift work system in your plant.
- Use the Worker for doing a job on a workplace at a station.
- Use the WorkerPool for modeling the staff room of your plant.
- Use the Workplace for modeling the actual place attached to the station, where the Worker performs his job.

**Workplace**

