### COM

The COM Interface enables you to control Plant Simulation from other applications by entering Tecnomatix.PlantSimulation.RemoteControl . This starts the most recent version. If you have installed several versions, you can also specify the version with Tecnomatix.PlantSimulation.RemoteControl.&lt;Major&gt;.&lt;Minor&gt; , for example Tecnomatix.PlantSimulationRemote.Control.25.0 .

You might, for example, start a simulation run in Plant Simulation from Microsoft Excel and then write the results into an Excel table. You can use the COM Interface to control Plant Simulation from any application that can address COM objects. This includes all Office applications, the Windows Scripting Host, and many other applications.

**The type of the interface is IRemoteControl :**

```simtalk
interface IRemoteControl : IDispatch { HRESULT NewModel(); HRESULT LoadModel(BSTR); HRESULT SaveModel(BSTR); HRESULT CloseModel(); HRESULT StartSimulation(BSTR); HRESULT StopSimulation(); HRESULT ResetSimulation(BSTR); HRESULT IsSimulationRunning([out,retval]VARIANT_BOOL*); HRESULT SetPathContext(BSTR); HRESULT ExecuteSimTalk(BSTR,[optional]VARIANT,[out,retval]VARIANT*); HRESULT GetValue(BSTR,[out,retval]VARIANT*); HRESULT SetValue(BSTR,VARIANT); HRESULT Quit(); };
```

**Note**

The COM Interface is part of the Plant Simulation Interface Package .

See also

Functions of the COM Interface

Events of the COM Interface

#### Functions of the COM Interface

Functions of the COM Interface

The COM Interface provides the functions listed in the table of contents to the left.

The examples below are for the Windows Scripting Host using the syntax of JScript. They assume that Plant Simulation was initialized with:

```simtalk
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
```

##### CloseModel [SimTalk] - active model

Closes the active simulation model.

Remarks

This corresponds to the command Close Model on the Quick Access Toolbar .

**Note**

You can also define a Method with the name onCloseModel in any folder in the Class Library , including the Basis folder. This method is being executed when you close the model or when you exit the application. You can, for example, program clean-up tasks, delete temporary files, etc.

The method onCloseModel has to declare the boolean parameter onExitApplication . Plant Simulation sets this parameter to false when onCloseModel is called when you close the model. Plant Simulation sets this parameter to true when onCloseModel is called when you exit Plant Simulation .

You can also program several onCloseModel methods and place them into different folders. Plant Simulation then calls all existing onCloseModel method classes in the Class Library when you close the model or exit the application.

Type

Function

Syntax

PlantSim.CloseModel

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.CloseModel("C:\\Models\\MyCOMTest.spp")
```

See also

Close Model

**ExecuteSimTalk [SimTalk]**

##### ExecuteSimTalk [SimTalk]

Executes the source code, which you specify, in a Method .

Type

Function

**Syntax**

```simtalk
PlantSim.ExecuteSimTalk(SourceCode:string[, Parameter1, Parameter2, Parameter3])
-> any
```

**Parameters**

- The parameter SourceCode of data type string designates the source code, which is going to be executed in the Method .

When the source code of the method contains a parameter, you can enter this as the second parameter into the method ExecuteSimTalk . The method ExecuteSimTalk then will return the return value of the method.

- The optional parameters Parameter1 , Parameter2 and Parameter3 allow to pass up to three arguments to the SimTalk method contained in the first argument.

**Return Value**

The return value has the data type any .

It is the return value of the Method .

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.ExecuteSimTalk("->real; return 3.14159")
PlantSim.ExecuteSimTalk("param r:real->real; return r*r", 3.14159)
```

##### GetValue [SimTalk] - COM

Returns the value of the specified attribute of the designated Plant Simulation object.

Type

Function

**Syntax**

```simtalk
PlantSim.GetValue(ObjectName:string)
-> any
```

**Parameter**

The parameter ObjectName of data type string designates the name of the Plant Simulation object and the name of the attribute.

Return Value

The return value has the data type any .

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.GetValue(".Models.Model.MyStation.ProcTime")
```

**See also**

**SetValue [SimTalk]**

Show Comment [AttributeExplorer]

##### IsSimulationRunning [SimTalk]

Returns if the simulation is running at the moment (true) or if it is not running (false).

Type

Function

Syntax

PlantSim.IsSimulationRunning -&gt; boolean

**Return Value**

The return value has the data type boolean .

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.IsSimulationRunning
```

##### LoadModel [SimTalk] - COM

Loads the specified Plant Simulation simulation model.

Remarks

LoadModel corresponds to the command Open Model on the Quick Access Toolbar .

The function LoadModel does not load call chains.

Type

Function

Syntax

```simtalk
PlantSim.LoadModel(ModelName:string[, Password:string])
```

**Parameters**

- The parameter ModelName of data type string designates the name of the model that you want to open.
- The optional parameter Password of data type string designates the password that is used for loading an encrypted model.

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.LoadModel("C:\\Modely\MyCOMTest.spp")
```

**See also**

**Open Model File**

**NewModel [SimTalk]**

##### NewModel [SimTalk]

Creates a new simulation model.

Remarks

NewModel corresponds to the command New Model on the Quick Access Toolbar .

Type

Function

Syntax

PlantSim.NewModel(FilePath:string)

Parameter

The parameter FilePath of data type string designates the name of the new model.

Example

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.NewModel("C:\\Models\MyCOMModel.spp")
```

See also

New Model

##### OpenConsoleLogFile [SimTalk]

Routes the output of the Plant Simulation Console to a file.

Remarks

To terminate routing to the file, specify an empty string "" .

Type

Function

Syntax

PlantSim.OpenConsoleLogFile(FilePath:string)

**Parameter**

The parameter FilePath of data type string designates the path to the file into which the Console output is going to be written.

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.OpenConsoleLogFile("C:\\temp\\MyConsoleProtocolFile.txt")
```

**Quit [SimTalk]**

##### Quit [SimTalk]

Exits Plant Simulation .

Remarks

Quit corresponds to the command Exit on the Quick Access Toolbar .

Type

Function

Syntax

PlantSim.Quit

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.Quit
```

**See also**

Exit Application

##### QuitAfterTime [SimTalk]

Exits Plant Simulation after the specified time in milliseconds has passed.

Type

Function

Syntax

PlantSim.QuitAfterTime(Time:integer)

**Parameter**

The parameter Time of data type integer designates the time after which Plant Simulation will be terminated.

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.QuitAfterTime(10)
```

##### ResetSimulation [SimTalk]

ResetSimulation [SimTalk]

Resets the EventController .

Remarks

ResetSimulation corresponds to the Reset Simulation button of the EventController .

Type

Function

Syntax

PlantSim.ResetSimulation(PathOfEventController:string)

Parameter

The parameter PathOfEventController of data type string designates the path of the EventController .

Example

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.ResetSimulation(".Models.Model.EventController")
```

See also

Reset Simulation [EventController]

##### SaveModel [SimTalk]

Saves the active simulation model with the name you specify.

Remarks

SaveModel corresponds to the command Save Model on the Quick Access Toolbar .

Type

Function

Syntax

PlantSim.SaveModel(ModelName:string)

Parameter

The parameter ModelName of data type string designates the name of the model.

Example

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SaveModel("Plant Cedar Rapids, Iowa")
```

See also

Save Model File

**SetLicenseType [SimTalk]**

##### SetLicenseType [SimTalk]

Sets the license type that is going to be used for Plant Simulation .

Type

Function

Syntax

PlantSim.SetLicenseType(LicenseType:string)

Parameter

The parameter LicenseType of data type string designates the license type.

Example

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetLicenseType("Professional")
```

See also

Start Plant Simulation with Different Kinds of Licenses

Plant Simulation License Types

##### SetNoMessageBox [SimTalk]

Shows a message box ( true ) or hides it ( false ).

Type

Function

Syntax

PlantSim.SetNoMessageBox(Value:boolean)

**Parameter**

The parameter Value of data type boolean sets if Plant Simulation shows a message box ( true ) or not ( false ).

**Example**

```simtalk
// JScript
var PlantSim =
```

WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl") PlantSim.SetNoMessageBox(true)

**SetPathContext [SimTalk]**

##### SetPathContext [SimTalk]

Sets where a relative path starts.

Type

Function

Syntax

PlantSim.SetPathContext(StartOfRelativePath:string)

**Parameter**

The parameter StartOfRelativePath of data type string designates the start of the relative path.

**Note**

The function only applies to the methods getValue and setValue .

**Example**

```simtalk
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetPathContext(".Models.Study1")
PlantSim.GetValue("MyStation.ProcTime") // accesses .Models.Study1.MyStation.ProcTime
```

**See also**

Object Paths in SimTalk

GetValue [SimTalk] - COM

SetValue [SimTalk]

##### SetSuppressStartOf3D [SimTalk]

Sets if Plant Simulation suppresses starting 3D or not.

Type

Function

Syntax

PlantSim.SetSuppressStartOf3D(Value:boolean)

**Parameter**

The parameter Value of data type boolean sets if Plant Simulation suppresses starting of 3D ( true ) or not ( false ).

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetSuppressStartOf3D(true)
```

**SetTrustModels [SimTalk]**

##### SetTrustModels [SimTalk]

Sets if the COM Interface permits models to have access to the computer or not.

Type

Function

Syntax

PlantSim.SetTrustModels(Trust:boolean)

**Parameter**

The parameter Trust of data type boolean sets if the COM Interface permits models to have access to the computer ( true ) or not ( false ).

Specifying true corresponds to the start option /TrustModels , meaning that general access to the computer is permitted and that model-specific or library-specific settings are overridden.

**Example**

```simtalk
// JScipt
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetVisible(true)
PlantSim.SetTrustModels(true)
```

See also

Specifying Start Options

Prohibit Access to the Computer [model settings]

##### SetValue [SimTalk]

Assigns a value to an attribute of a Plant Simulation object.

Type

Function

**Syntax**

eMPlant.SetValue(NameOfObject:string, AttributeValue:any)

**Parameters**

- The parameter NameOfObject of data type string designates the name of the object and its attribute.
- The parameter AttributeValue of data type any designates the value of the attribute.

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetValue("Station.Proctime",120)
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetValue(".Models.Model.MyDataTable[2,1]", 3)
```

**See also**

GetValue [SimTalk] - COM

Show Comment [AttributeExplorer]

**SetVisible [SimTalk]**

##### SetVisible [SimTalk]

Makes the application Plant Simulation visible ( true ) or invisible ( false ).

Remarks

If Plant Simulation is created as a COM server it is invisible by default. You can use SetVisible to make Plant Simulation visible.

Type

Function

Syntax

eMPlant.SetVisible(Visible:boolean)

**Parameter**

The parameter Visible of data type boolean sets if the application Plant Simulation is visible ( true ) or invisible ( false ).

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.SetVisible(true)
```

##### StartSimulation [SimTalk]

Starts the simulation with the EventController .

Remarks

StartSimulation corresponds to the Start/Stop Simulation button.

Type

Function

Syntax

```simtalk
eMPlant.StartSimulation(PathOfEventController:string[, SimulationWithoutAnimation:boolean])
```

**Parameters**

- The parameter PathOfEventController of data type string designates the path of the EventController .
- The optional parameter SimulationWithoutAnimation of data type boolean sets if the simulation is going to be executed without animation ( true ) or with animation ( false ).

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.StartSimulation(".Models.Model.EventController")
```

**See also**

Start/Stop Simulation [EventController]

**StopSimulation [SimTalk]**

##### StopSimulation [SimTalk]

Stops the running simulation.

Remarks

StopSimulation corresponds to the Start/Stop Simulation button in the EventController .

Type

Function

Syntax

eMPlant.StopSimulation

**Example**

```simtalk
// JScript
var PlantSim = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl")
PlantSim.StopSimulation
```

See also

Start/Stop Simulation [EventController]

#### Events of the COM Interface

Events of the COM Interface

The COM Interface provides the events named SimulationFinished and FireSimTalkMessage .

**Note**

Consult the documentation that came with your programming application for instructions on how to connect to these events.

See also

SimulationFinished [SimTalk]

FireSimTalkMessage [SimTalk]

**FireSimTalkMessage [SimTalk]**

##### FireSimTalkMessage [SimTalk]

Triggers the event SimTalkMessage from within SimTalk .

**Remarks**

The name of the function, which will be triggered, depends on the programming language you use, such as Visual Basic, JavaScript, etc. Check the documentation that came with your programming application for details.

**Note**

You have to specify a parameter of data type string .

**Example**

fireSimTalkMessage("The buffer is full.")

**See also**

Example of a JScript

##### SimulationFinished [SimTalk]

At the end of a simulation run Plant Simulation triggers the event SimulationFinished . You can use it to read the results of a simulation run.

#### Example of a JScript

A JScript might look as follows:

```simtalk
var vbOKCancel = 1;
var vbCancel = 2;
var vbInformation = 64;
var Finished=false;
var WSHShell = new ActiveXObject("WScript.Shell");
var simple = WScript.CreateObject("Tecnomatix.PlantSimulation.RemoteControl1", "RemoteControl_");
simple.SetLicenseType("Runtime"); try { // Enter the path to a model file!
simple.LoadModel("C:\\Models\\Test.spp"); } catch (e) {
WScript.Echo("Could not load Model!");
WScript.Quit(); } try {
simple.SetValue(".Models.Model.Buffer.ProcTime", 700.0); } catch (e) { r=WSHShell.Popup(e.description, 0, "Continue?", vbOKCancel + vbInformation); if (r == vbCancel) {
simple.CloseModel();
WScript.Quit(); } }
simple.StartSimulation(".Models.Model.EventController"); if (simple.IsSimulationRunning())
WScript.Echo("Simulation is running!"); // Wait until simulation is finished while (!Finished)
WScript.Sleep(2000);
simple.CloseModel();
simple.Quit();
WScript.Quit(); function RemoteControl_SimulationFinished() {
WScript.Echo("Simulation Finished!"); Finished = true; } function RemoteControl_SimTalkMessage(str) {
WScript.Echo(str); }
```

**Example of a JScript**

#### Example of a Python Script

A Python script might look as follows:

```simtalk
**Install pywin32 with this command: # pip install pywin32 import
win32com.client import time PlantSim = win32com.client.Dispatch("Tecnomatix.PlantSimulation.RemoteControl.25.4")
PlantSim.SetVisible(True)
PlantSim.LoadModel("D:/Test.spp")
PlantSim.StartSimulation(".Models.Model");
time.sleep(10)
PlantSim.StopSimulation()
PlantSim.Quit()**
```

**See also**

PythonModule

#### OPCUA

