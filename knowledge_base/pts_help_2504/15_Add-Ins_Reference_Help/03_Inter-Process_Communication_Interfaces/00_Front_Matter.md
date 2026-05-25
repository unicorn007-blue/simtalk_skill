## Inter-Process Communication Interfaces

Plant Simulation provides the inter-process communication interfaces to exchange and share data between them.

- ActiveX provides the interface between Plant Simulation and the ActiveX controls . It enables you to embed ActiveX controls into a Plant Simulation Frame . You can access methods and attributes of ActiveX controls using methods and attributes .
- C enables you to extend the features and functionalities of Plant Simulation considerably by integrating functions you programmed in the programming language C, such as numerical evaluation and optimization procedures, etc.
- COM enables you to control Plant Simulation from other applications by entering Tecnomatix.PlantSimulation.RemoteControl . This starts the most recent version. If you have installed several versions, you can also specify the version with Tecnomatix.PlantSimulation.RemoteControl.&lt;Major&gt;.&lt;Minor&gt; , for example Tecnomatix.PlantSimulationRemote.Control.25.0 .
- MQTT provides an open network protocol to transmit messages from device to device over the Internet. MQTT stands for M essage Q ueuing T elemetry T ransport.
- OPCClassic provides the interface between Plant Simulation and control and automation technology systems for accessing and exchanging data. The OPCClassic Interface acts as a client and can read the control variable and the signals of PLC controls and provide other applications with data. OPC stands for Open Platform Communications .
- OPCUA provides the interface between Plant Simulation and control and automation technology systems for accessing and exchanging data. It enables access to process monitors, such as PLC controls via the OPC Unified Architecture . The OPCUA Interface acts as a client and can read and write control variables and the signals of PLC controls. OPC stands for Open Platform Communications .
- PLCSIM\_Advanced provides the interface to PLCSIM Advanced of version 5.0 or higher. The Siemens program PLCSIM Advanced simulates functions of virtual PLCs (Programmable Logic Controllers). The object PLCSIM\_Advanced enables to exchange data between Plant Simulation simulation models and virtual PLCs which are executed in PLCSIM Advanced .
- SIMIT provides the interface between Plant Simulation and process control devices, such as PLC controls, via SIMIT, which stands for Simulation &amp; Testing.
- Socket provides a TCP/IP interface for Plant Simulation . It communicates with other applications, which have a socket interface.
- Teamcenter [object] provides the interface between Plant Simulation and Teamcenter for accessing and exchanging data. It provides the commands required for Plant Simulation to connect to Teamcenter , to receive Teamcenter data in Plant Simulation , to parse the information received, and make it useful for Plant Simulation .

To add the interfaces that are not built-in to your simulation model, click Manage Class Library &gt;

Basic Objects &gt; Information Flow on the Home ribbon tab.

<!-- image -->

<!-- image -->

