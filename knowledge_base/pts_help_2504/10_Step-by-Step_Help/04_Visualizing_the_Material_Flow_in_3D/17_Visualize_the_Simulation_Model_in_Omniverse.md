### Visualize the Simulation Model in Omniverse

You can visualize your Plant Simulation 2504 simulation model in NVIDIA Omniverse using the Omniverse Connector .

The Omniverse Connector is only active if you have a subscription for this optional product.

<!-- image -->

To create an excellent looking visualization of your Plant Simulation 2504 simulation model in Omniverse, proceed as follows:

- Start the Omniverse Connector
- Set Up a New Filesystem Connection
- ·
- Establish a Live Connection to Omniverse You can open the project in the Live data area of the Nvidia Omniverse Composer and work on

enhancing the looks of the model.

- Use Omniverse with the Function MVA\_WriteUSD

See also

Omniverse Connector

#### Start the Omniverse Connector

Start the Omniverse Connector to establish a connection with NVIDIA Omniverse.

**Proceed as follows:**

- Start Plant Simulation 2504 and open the Frame containing the simulation model, which you want to use for exporting usd files or for a live connection with Omniverse.
- Change to the Edit ribbon tab and click Omniverse Connector
- This opens the LiveConnect window.

Back to Visualize the Simulation Model in Omniverse

<!-- image -->

.

#### Set Up a New Filesystem Connection

Set up a New Filesystem connection to export usd files and then establish a connection with Omniverse.

**Proceed as follows:**

- Click the Omniverse node in the LiveConnect window and select New Filesystem connection .
- Create a new folder in the file system on your computer by clicking the Make New Folder button or select an existing folder in the File Browser . Our folder is named USD Data Files .
- Type a Description of the project into the dialog Add new Filesystem connection .

<!-- image -->

<!-- image -->

<!-- image -->

The LiveConnect window then shows our connection node.

<!-- image -->

- Click the USD Data Files folder and select Connect to establish the Omniverse connection with this folder. Then, select the data folder link. Once the folder is selected, you can type a file name into the text box File name at the bottom of the LiveConnect window.

Plant Simulation does currently not use the setting Frames per second , you can leave this box empty.

<!-- image -->

Export the Simulation in USD Format

After setting-up the file system connection, you can export the running simulation to usd files. USD stands for Universal Scene Description .

**Proceed as follows:**

- Click Export to make Omniverse create the required usd files within the configured data folder. Start the simulation, which you want to record in Plant Simulation . Stop the simulation after everything is recorded that you want to show.
- Click Export again to stop the usd recording,
- Plant Simulation creates a library folder and a usd file in the data folder.
- You can then open the exported simulation project in the Nvidia Omniverse Composer and visualize the simulation model.

Back to Visualize the Simulation Model in Omniverse

#### Establish a Live Connection to Omniverse

Establishes a live connection to Omniverse using the Omniverse Nucleus Server .

**Proceed as follows:**

- Make sure that the Omniverse Nucleus Server is started and running.
- Right-click the Omniverse node in the LiveConnect window and select New Nucleus connection .
- Type in a Description and the IP address or the server name of the computer on which Omniverse Nucleus is installed.

Type in the Port number , which is configured for the Omniverse Nucleus Server. Click OK to close the dialog.

<!-- image -->

- Right-click the newly created server node and select Connect on the context menu. You will then see the Omniverse data folder on the server computer.
- Create a folder structure in Nvidia Omniverse Composer in the Projects folder .

<!-- image -->

<!-- image -->

- Right-click the Library folder in the project, MyProject01 in our example. Then select Set System root folder on the context menu.
- Select the project folder and type a project name into the text box File name . We typed in MyLiveProject01 .
- Click Connect and start the simulation in the Frame containing your simulation model.
- Open the project in the Live data area of the Nvidia Omniverse Composer .
- Stop the simulation in Plant Simulation and then terminate the Live connection by clicking Connect in the LiveConnect window.

<!-- image -->

Back to Visualize the Simulation Model in Omniverse

#### Use Omniverse with the Function MVA\_WriteUSD

Creates and activates a Nucleus Connection , or creates and activates a Filesystem Connection , or terminates a Live Connection , or a Filesystem Connection via SimTalk .

Remarks

Before using MVA\_WriteUSD , you

- Either have to load the Omniverse DLL via SimTalk with
- Or you have to manually start the Omniverse connection by clicking Omniverse Connector the Edit ribbon tab in Plant Simulation .

loadLibrary(applicationHome + "PlantSimOmniverse.dll")

Type

Function

Syntax

```simtalk
MVA_WriteUSD("parameter string")
```

Create and Activate a Nucleus Connection

Specify these instructions to create and activate a Nucleus Connection with MVA\_WriteUSD :

```simtalk
var system_root_path:string = "/Projects/My_Project01/Library"
var output_path:string = "omniverse://127.0.0.1:80/Projects/My_Project01/ myExport.live" MVA_writeUSD(output_path+"?sysroot="+system_root_path)
```

Parameter

The parameter string specifies the project file path in the first section and the Omniverse system root folder in the second section, which is to be used for the USD export or a live connection.

MVA_writeUSD(<project file path>?systemroot=<system root path>)

<!-- image -->

on For a live connection the project file and system root folder typically is a sub-folder in the Omniverse Nucleus project folder that is managed by the Omniverse Nucleus server.

Compare the examples for both use cases below.

Create and Activate a Live Connection or a Filesystem Connection

Specify these instructions to create and activate a Filesystem Connection with MVA\_WriteUSD :

```simtalk
var system_root_path:string = "D:/USD_DataFiles/My_Project01/Library"
var output_path:string = "file://d:/USD_DataFiles/My_Project01A/ myExport.usd" MVA_writeUSD(output_path+"?sysroot="+system_root_path)
```

Terminate an Open Live Connection or a Filesystem Connection

Type an empty string to terminate an open Live Connection or an open Filesystem Connection with MVA\_WriteUSD :

MVA_writeUSD("")

**Note**

Make sure, that Omniverse Composer does not have an open connection to a previously exported simulation while starting an new export from Plant Simulation with the same project file and system root.

**Note**

For a Nucleus Live Connection we do not yet support the function MVA\_writeUSD().

Back to Visualize the Simulation Model in Omniverse

