# 3. Installing and Starting

## System Requirements

The following system requirements apply for Plant Simulation .

**Minimum PC Configuration**

- Windows 10 64-bit or Windows 11 64-bit x86-64 CPU. We do not support ARM processors.
- 4 GB RAM
- 2 GB of free disk space

**Recommended PC Configuration**

- At least 16 GB RAM
- SSD with at least 4 GB of free disk space
- Graphics resolution of 1920 x 1080 pixels or higher
- We support 3D on workstations and servers running an NVIDIA, an AMD, or an Intel (HD 4600 or higher) GPU implementing OpenGL 3.3, or 4.5.
- The full graphical functionality is realizable only with OpenGL 4.5 or higher. Functionality is slightly reduced for OpenGL 3.3. Functionality is greatly reduced in the case of OpenGL 1.1 and 1.5.
- For 3D Navigation, we support the SpaceNavigatorTM by 3Dconnexion.

**Installing the Online Help Locally**

**Note**

To install help content in a language other than English , you must first install the English help content.

To install the online help on your computer and use it there without a connection to the internet:

- Consult the document Accessing the help from Plant Simulation on the download page ( https://support.sw.siemens.com/product/297028302/downloads ). It contains all you need for downloading and installing the help on your computer .
- Alternatively you can download the Siemens Documentation Server 3.0 or higher here https:// support.sw.siemens.com/product/266603595/downloads and install it on your computer.

**System Requirements**

- After you have installed the Siemens Documentation Server and the Plant Simulation 2504 Help , enter the Local Documentation Server on the tab General of the Preferences . Specify if you installed the help server on your local machine with the

http:/localhost:5000 default port. Plant Simulation automatically adds the identifier of the Plant Simulation user interface language you set.

**Installing Plant Simulation in the Microsoft Azure Cloud**

For information about installing and running Plant Simulation in Microsoft Azure , click here .

## Software Compatibility

Plant Simulation 2504 is compatible with the following software and interface protocols.

| Software or Interface Protocol   | Version                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| SIMIT                            | We support SIMIT 7.0 and higher. SIMIT must support the shared memory interface Version 1.                                                                         |
| PLCSIM Advanced                  | >= Version 5.0                                                                                                                                                     |
| MQTT                             | We support the MQTT protocol versions 3.1, 3.1.1 and 5.0                                                                                                           |
| OPC UA                           | We support the binary OPC UA protocol                                                                                                                              |
| ODBC                             | 64-bit ODBC drivers                                                                                                                                                |
| Python                           | >= Version 3.12                                                                                                                                                    |
| Teamcenter                       | See Excel file with Teamcenter Interoperability Matrix (sheet Tecnomatix ) on https://support.sw.siemens.com/en- US/product/282219420/download/PL20200617155641511 |

## Installing and Starting Plant Simulation 2504

Welcome to Plant Simulation , the standard software for object-oriented, graphical, and integrated modeling, for simulating and visualizing systems and business processes.

You can extend the functionality of Plant Simulation by purchasing a number of Add-Ins .

**Note**

Plant Simulation runs on the 64-bit version of Windows 11.

The current Plant Simulation version can open simulation models (.spp files) that were created in SiMPLE+ + 7.0 or higher.

In models that you created in a version older than Plant Simulation 9.0, the 3D part of the model will not be loaded. You can load the model in version 9.0 or higher, and then save it there though.

**Installing Plant Simulation in the Microsoft Azure Cloud**

For information about installing and running Plant Simulation in Microsoft Azure , click https:// learn.microsoft.com/en-us/azure/architecture/topics/high-performance-computing

**Running Plant Simulation from the Command Prompt**

You can also run the Plant Simulation console version by calling the PlantSimulationConsole.exe from the command prompt.

**Installing Plant Simulation X from Software Center**

For information about installing and running Plant Simulation X , see Install Plant Simulation X from Siemens Software Center .

**See also**

Installing Plant Simulation

Licensing Plant Simulation

Starting Plant Simulation

Starting PlantSimulationConsole.exe

System Requirements

Additional Installation Information

Add-Ins Reference Help

## Installing Plant Simulation

How to install Plant Simulation on your computer.

Proceed as follows to install Plant Simulation :

- Download the Plant Simulation installation package from this website https:// support.sw.siemens.com/product/297028302/downloads .

<!-- image -->

- Log on with Administrator rights under Windows 11.
- Change to the folder on your computer into which you downloaded the msi file and double-click the msi file to start the installation.
- Click the Next button to proceed with the installation.

<!-- image -->

- Select the folder into which you would like to install Plant Simulation or accept the standard folder. Click Next to proceed with the installation.

<!-- image -->

- Click the Install button to start the installation or click the Back button to return to the previous dialog and modify any of the settings there.

<!-- image -->

The installation program shows the percentage of the installation it completed. Click the Finish button after the installation is done.

- Restart your computer.
- Log on as Administrator again to ensure that the operating system correctly registers all files.
- When you install Plant Simulation for the fi rst time , you have to set up the license(s) for the product(s) you purchased. Click the respective button and follow the instructions on screen.

<!-- image -->

**Note**

The following description does not apply when you Use Cloud Licensing . Your cloud licenses are provided and managed by Siemens.

**Compare**

Install the Online Help Locally

**Use a Node-Locked License**

If you are using a floating license , you have to install the Sentinel driver .

<!-- image -->

**SimTalk**

applicationHome [SimTalk]

getRegistry [SimTalk]

licenseName [SimTalk]

**See also**

Installing Product Updates

Local Documentation Server

## Uninstalling Plant Simulation

How to uninstall Plant Simulation from your computer.

Proceed as follows to completely remove Plant Simulation from your computer:

- Select Start ⊞ &gt; Settings &gt; Apps &gt; Installed apps .
- Find Plant Simulation 2504 in the displayed list of apps.
- Click More options … &gt; Uninstall .

Uninstalling does not delete simulation models that are saved on your computer's hard drive.

Uninstalling does also not delete the file TrustID.txt , which normally is located in the directory C:\Users\&lt;username&gt;\AppData\Roaming\Siemens\Tecnomatix Plant Simulation . This file contains the Trust-ID , which identifies models as being saved by you.

**See also**

Trust-ID to Permit Models Access to the Computer

## Install the Online Help Locally

How to install the Plant Simulation Help on your computer if you do not have a permanent internet connection at your place of work.

We provide the Plant Simulation Help on the Web by default. This way you always get the current state of the help with the newest descriptions and enhancements.

If you want to install the Plant Simulation Help on your computer and use it there without a connection to the internet:

- Consult the document Accessing the help from Plant Simulation on the download page ( https://support.sw.siemens.com/product/297028302/downloads ). It contains all you need for downloading and installing the help on your computer .

<!-- image -->

- Alternatively you can download the Siemens Documentation Server 3.0 or higher here https:// support.sw.siemens.com/product/266603595/downloads and install it on your computer.

<!-- image -->

You can also download and install the Documentation Proxy 3.2 .

The Documentation Proxy enables you to access product documentation on the Support Center without logging in or creating a Siemens ID account. This eliminates the need and overhead of installing documentation locally while still providing secure access.

- Alternatively you can download the Plant Simulation 2504 Help here https:// support.sw.siemens.com/product/297028302/downloads and install it on your computer.

<!-- image -->

**Note**

To install help content in a language other than English , you must first install the English help content.

- After you have installed the Siemens Documentation Server and the Plant Simulation 2504 Help , specify the Local Documentation Server on the tab General of the Preferences .

Specify http:/localhost:5000 if you installed the help server on your local machine with the default port. Plant Simulation automatically adds the identifier of the Plant Simulation user interface language you set.

**Note**

Be aware that the installed version displays the state of the help of the date when we created the help package, not the most up-to-date version that is available on the Web.

The help on the Web and the version installed on your computer work the same.

**See also**

Using Online Help

### Licensing Plant Simulation

## Licensing Plant Simulation

**Note**

The following description does not apply when you Use Cloud Licensing .

Your cloud licenses are provided and managed by Siemens, see Install Plant Simulation X from Siemens Software Center .

<!-- image -->

After you have installed Plant Simulation for the first time, you have to set up the license(s) for the product(s) you purchased.

Click the respective button and follow the instructions on screen.

<!-- image -->

**Note**

If you are using a network license, you need the Siemens License Server 2.0.0 or higher. You can download it from here: https://support.sw.siemens.com/product/1586485382 . Also consult the accompanying documentation for Installing the License Server .

In old license files you have to replace the line:

VENDOR ugslmd

with this line:

VENDOR saltd

We automatically change this when installing the new license server when you specify an old license file. If you want to use another license file later on, you have to change this manually though.

**Note**

The Siemens License Server 2.0.0 uses the default Port number 29000 to avoid a conflict with the existing port number 28000.

You can:

- Use a Node-Locked License
- Use a Floating License
- Use a Computer-Dependent/Dongle ID License
- Use Redundant License Servers
- Install Plant Simulation X from Siemens Software Center
- Setting Default Values in the Windows Registry (Administrator)
- Specifying Start Options

[You can download your licenses here https://support.sw.siemens.com/product/297028302/downloads](https://support.sw.siemens.com/product/297028302/downloads)

Then, click Support Contacts &gt; Support Center to the right at the bottom of the page.

Your licenses are ready for you in the Account Center under Licenses .

<!-- image -->

<!-- image -->

**See also**

File &gt; Preferences &gt; License

License File

Plant Simulation License Types

Plant Simulation License Types

Plant Simulation Options

### Use a Node-Locked License

A node-locked license is only available for the user on whose computer the Plant Simulation license file is installed.

<!-- image -->

The Siemens License Server is not required for this type of license.

If you are using a Sentinel dongle, you can also move the dongle with the licenses to a different computer.

**See also**

File &gt; Preferences &gt; License

License File

### Use a Floating License

A fl oating license is available for any user within your computer network. If you purchased several floating licenses, several users can work with the number of Plant Simulation licenses installed on the license server computer. This license server can, but does not have to, be the computer on which the applications or application servers run.

**Note**

When using a floating license, the network administrator must change YourHostname in the license file to the computer name of the Plant Simulation user.

Change SERVER YourHostname &lt;host\_id or CID&gt; 29000 to SERVER DESTSJames001 &lt;host\_id or CID&gt; 29000 for example.

The SPLM License Service has to run on a server to assign and manage the licenses. You do not have to install it on the individual client computers running Plant Simulation .

**See also**

File &gt; Preferences &gt; License

Server [license] - 1

Borrow Licenses

<!-- image -->

### Use a Computer-Dependent/Dongle ID License

For retrieving the license, Plant Simulation uses the computer's ID. For floating licenses, this is the ID of the license server computer; for node-locked licenses, it is the ID of the local computer. The ID can be either computer-dependent or the ID of a Sentinel dongle. Both types of IDs support all license types described above.

You can use any one of these IDs:

- Ethernet ID ( MAC address ): The network card of your computer provides this computer-dependent ID. The ID only changes when you replace your network card.

An Ethernet ID might look like this: 001118ba11f0

- Sentinel Dongle ID : A software protection dongle is a piece of hardware which you plug into a USB port of your computer. The dongle ID is located on the dongle itself.
- Using a Sentinel dongle enables you to move the dongle and the license files to different computers. This is useful when you replace or reinstall the license server computer, or disconnect it from the network. The portable dongle makes licenses available again quickly and easily.
- Composite Host-ID ( CID ): The Composite Host-ID (CID) factors in the name of the computer and the network card. Use the first COMPOSITE in the field Query Host-IDs .

A Composite Host-ID might look like this: COMPOSITE=A12345B67899

**See also**

File &gt; Preferences &gt; License &gt; Query Host IDs

### Use Redundant License Servers

When you use a fl oating license or a node-locked license , you can also use three redundant license servers to significantly increase the availability of licenses within your computer network. The redundant servers are three separate computers within the network using the same license file which is required for the redundant license server mechanism.

As long as at least two of the three computers are available within the computer network, all licenses are available. Type in the names and the ports of the license servers on the tab License .

<!-- image -->

Then, select Use License Server Triad .

**See also**

File &gt; Preferences &gt; License

Use a License Server Triad

### Install the Siemens License Server (SLS)

If you install Plant Simulation for the first time and if you are Use a Floating License , you will have to install the Siemens License Server 2.0.0 or higher.

You can download it from here: https://support.sw.siemens.com/product/1586485382 . Also consult the accompanying documentation for Installing the License Server .

If you want to use the Sentinel dongle, you have to install the Sentinel driver in addition.

<!-- image -->

### Install the Sentinel Driver

If you want to use a Sentinel dongle to retrieve your license, you have to install the Sentinel driver on your computer.

You can download the Sentinel driver from our website https://support.sw.siemens.com/product/ 1586485382/download/202302004 . Click Sentinel\_System\_Driver\_Installer\_7.6.1.zip

<!-- image -->

**Note**

If a previous version of the Sentinel driver is installed on your computer, update your driver, so that the driver works together with the dongle you received.

To install the current Sentinel driver:

- Log on as Administrator .
- Double-click the program Sentinel System Driver Installer 7.6.1.exe .
- Select Sentinel driver and click Next .
- During the installation a dialog opens. Click Next and follow the instructions in the dialog.
- Restart your computer when the setup asks you to do so.
- After the computer has started up all the way, insert the Sentinel dongle into the appropriate port of your computer in the direction indicated by the arrow on the dongle.
- You can test the new functionality of the Sentinel dongle by double-clicking the respective entry in the Control Panel of your computer.

**See also**

Install the Siemens License Server (SLS)

### Start Plant Simulation with Different Kinds of Licenses

If you are using Plant Simulation with a license other than Professional , you can use the start parameter -L &lt;parameter&gt; or /L &lt;parameter&gt; to start Plant Simulation with one of these available licenses.

| For this license                  | Specify this start parameter      | Or this start parameter   |
|-----------------------------------|-----------------------------------|---------------------------|
| -L Application                    | /L Application                    | Application               |
| -L Educational                    | /L Educational                    | Educational               |
| -L Foundation                     | /L Foundation                     | Foundation                |
| -L HighestAvailable               | /L HighestAvailable               | Highest Available         |
| -L Professional (or no parameter) | /L Professional (or no parameter) | Professional              |
| -L Research                       | /L Research                       | Research                  |
| -L Runtime                        | /L Runtime                        | Runtime                   |
| -L Simulation                     | /L Simulation                     | Simulation                |
| -L Standard                       | /L Standard                       | Standard                  |

| For this license   | Specify this start parameter   | Or this start parameter   |
|--------------------|--------------------------------|---------------------------|
| Student            | -L Student                     | /L Student                |
| Viewer -L          | Viewer                         | /L Viewer                 |

You might, for example, type the following into the text box Target of a shortcut.

C:\Program Files\Siemens\Plant Simulation 2504\PlantSimulation2504.exe /L Standard

If you set the license type to Highest Available , Plant Simulation uses the first available license type in the following order:

- Professional
- Standard
- Foundation
- Application
- Runtime
- Research
- Educational
- Student

**Note**

If you purchased different license types, you have to explicitly specify the license type, which you want to use.

Or you might type the information in the screenshots below to start Plant Simulation English or German .

<!-- image -->

Naturally, you can also select the License Type in Plant Simulation itself under File &gt; Preferences &gt; License .

<!-- image -->

For licenses, which limit the number of objects you can use, the root object ( Basis ) in the Class Library shows how many objects are used and how many are allowed. For a Student license it might look like this:

<!-- image -->

**Set the Default License Type as Administrator**

If you are an Administrator , you can set the default license type by creating the registry entry

HKEY\_LOCAL\_MACHINE\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504 . Then, create the string value DefaultLicenseType and set the license type, for example to Professional .

**SimTalk**

licenseName [SimTalk]

numOfLimitedObjects [SimTalk]

NumberOfLimitedObjects [SimTalk] of the Frame

**See also**

License Type

License

### Starting Plant Simulation

## Starting Plant Simulation

After you installed Plant Simulation and typed your license information, you can start and run Plant Simulation .

<!-- image -->

Click Start &gt; All apps &gt; Plant Simulation 2504 or create a shortcut on your desktop and doubleclick the Plant Simulation icon.

<!-- image -->

Type in the information from the screenshots below to start Plant Simulation with the English or with the German user interface.

<!-- image -->

Type in the information from the screenshots below to start Plant Simulation with the Chinese , the Japanese , or the Hungarian user interface.

<!-- image -->

**See also**

Specifying Start Options

Setting Default Values in the Windows Registry (Administrator)

### Specifying Start Options

You can specify start options for Plant Simulation by typing in command line arguments into the dialog Properties .

To specify start options for Plant Simulation , follow these steps:

- Create a shortcut for Plant Simulation on the desktop.
- Open the dialog Properties of the shortcut.

<!-- image -->

<!-- image -->

- Extend the path to Plant Simulation in the text box Target with one or several of these start options. Do not type in the angle brackets.

<!-- image -->

| To do this                                                                                                                                                                                                                                                                    | Type in                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| Automatically save the model every t minutes.                                                                                                                                                                                                                                 | /a <t> , for example /a 10 Plant Simulation adds -AutoSave to the name of the simulation model. |
| Set the code page for correctly displaying the contents of tables in models that were created in foreign languages on a computer with an English or a German operating system. The code pages are: Japanese: 932 , Chinese: 936 , Hungarian: 1250 , English or German: 1252 . | /Codepage:932 /Codepage:936 /Codepage:1250                                                      |

| To do this                                                                                                                                                                                                                            | Type in                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Compare setCodePage [SimTalk] .                                                                                                                                                                                                       | /Codepage:1252                                                                                                                   |
| Start Plant Simulation , load the model designated by file_1 , and compare it with the model designated by file_2 . As a rule this only makes sense for automated use in source code version control tools.                           | /compare <file_2 file_1>                                                                                                         |
| Set the affinity mask which defines on which CPU cores Plant Simulation is allowed to run. The affinity mask is a number in which each bit represents a core on which the threads of the Plant Simulation process are allowed to run. | /CPU mask                                                                                                                        |
| Set the current working directory. Compare getCurrentDirectory [SimTalk] and setCurrentDirectory [SimTalk] .                                                                                                                          | /cwd dir                                                                                                                         |
| Run the source code of the text file named file .                                                                                                                                                                                     | /e file                                                                                                                          |
| Run the method of the model loaded with /f specified by < Path >                                                                                                                                                                      | /E < Path >                                                                                                                      |
| Start Plant Simulation and open the file named model file .                                                                                                                                                                           | /f model file                                                                                                                    |
| Start Plant Simulation , open the model file specified by file path , and start the simulation in the Frame designated by the absolute path in Frame .                                                                                | /f <filepath> /m <frame>                                                                                                         |
| Hide Plant Simulation after starting it, i.e., minimize it into the system tray.                                                                                                                                                      | /hideBBL                                                                                                                         |
| Start Plant Simulation with the license name which you type in. The name of the license is case-insensitive, the default is PROFESSIONAL. Also applies for Pack and Go .                                                              | /L APPLICATION /L EDUCATIONAL /L FOUNDATION /L HIGHESTAVAILABLE /L PROFESSIONAL /L RESEARCH /L RUNTIME /L SIMULATION /L STANDARD |

| To do this                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Type in                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| Write all messages which Plant Simulation writes to the Console to the file designated by file name into the folder into which you installed Plant Simulation . The log file contains a time stamp per line. Compare clearLogFile [SimTalk] and getLogFile [SimTalk] .                                                                                                                                                                                                                                                                                                                                                                          | /logfile file name                                                              |
| Use the previous, no longer supported Excel interface for reading and writing files using the xls-format. This enables you to use the Excel interface without Excel having to be installed on your computer.                                                                                                                                                                                                                                                                                                                                                                                                                                    | /NativeExcel                                                                    |
| Prevent Plant Simulation from creating a backup file (*.bak) when saving the model.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             | /NoBakFile                                                                      |
| Prevent Plant Simulation from opening any message boxes. If the message box shows a question with Yes and No buttons, the question will be answered with No . This is especially useful when you execute batch runs, as it prevents them from stopping, when a message box opens. When a runtime error occurs in a Method and when this error is not caught by an ErrorHandler, Plant Simulation normally opens the Method debugger . If you set the start option / NoMessageBox , Plant Simulation opens a message box instead telling you that it will automatically terminate in 5 seconds if you do not click OK in the message box window. | /NoMessageBox                                                                   |
| Prevent Plant Simulation from writing any of the info and debug messages, such as warnings, to the Console . Compare setConsoleFilter [SimTalk] .                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | /NoWarning                                                                      |
| Register the file extension .spp in the Registry .                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | /RegisterFileExtension                                                          |
| Start Plant Simulation with the user interface language English , German , Japanese , Chinese , or Hungarian . The Plant Simulation Online Help will also open in the respective language if it exists in that language. Compare userInterfaceLanguage [SimTalk] .                                                                                                                                                                                                                                                                                                                                                                              | /UILanguage:ENU /UILanguage:DEU /UILanguage:JPN /UILanguage:CHS /UILanguage:HUN |
| Treat models, which you receive from others as if they were your own models, i.e., models with your trust ID. When you open a model that your received from somebody else, for which the Model setting > Prohibit Access to the Computer [model settings] is deactivated, Plant Simulation permits access without asking you.                                                                                                                                                                                                                                                                                                                   | /TrustModels                                                                    |

| To do this                                                                                                                                                                                                                                                                                                                                | Type in   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| Models, which were saved with a version older than 14, do not receive a trust ID and thus are always considered to be models from other people. Normally access to the computer is denied when loading an old model into version 14. If you typed the start option /TrustModels , the old model automatically has access to the computer. |           |

**Note**

Instead of a forward slash / you can also type in a minus sign -. You can, for example, type /f MyAssemblyModel.spp or -f MyAssemblyModel.spp , both execute the same command.

**Note**

You can also pass any other command-line arguments which you can then query with the function getCommandLineArg [SimTalk] . Plant Simulation itself will ignore them.

**Note**

The start options are case-sensitive.

You might, for example, type this string into the text box Target of a shortcut.

"C:\Program Files\Siemens\Plant Simulation 2504\PlantSimulation2504.exe" / UILanguage:ENU /f MyAssemblyModel.spp

**See also**

Prohibit Access to the Computer [model settings]

Trust-ID to Permit Models Access to the Computer

SetTrustModels [SimTalk] , COM

License Type

Start Plant Simulation with Different Kinds of Licenses

Starting PlantSimulationConsole.exe

Creating a German Model with English Identifiers

getCommandLineArg [SimTalk]

### Setting Default Values in the Windows Registry (Administrator)

When you start Plant Simulation for the first time after installing it, it sets the preferences to default values.

If you are an Administrator and would like to specify different default values, for example a certain model language for new models, you can define your company's own settings for all users on the computer with the registry key HKEY\_LOCAL\_MACHINE\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504\Preferences . Here you can then set the exact same registry values, which Plant Simulation creates in the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences when a user changes the preferences. You do not have to set all registry values, you can also only define individual values.

If you want to define several preferences for all users on the computer, the best way to do this, is to set the desired settings and to select them in the dialog Preferences in Plant Simulation and to then close this dialog by clicking OK .

Then start regedit.exe and export the key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences . Then start notepad.exe and open the .reg-file . Delete all lines containing values which you do not want to use. Then change the line [HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences] to [HKEY\_LOCAL\_MACHINE\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504\Preferences] and save the file. When you double-click this file on any Windows computer, the default values for the preferences will be entered into the Registry . Plant Simulation only uses the default values when the registry key HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504\Preferences does not exist, for example when Plant Simulation is started for the first time.

**UpdateCheckDate**

The registry value UpdateCheckDate under

Computer\HKEY\_CURRENT\_USER\SOFTWARE\Siemens\Tecnomatix Plant Simulation 2504 designates the point in time of the last check for a version to be updated, specified in days since 01/01/2000. To permanently deactivate the check when starting the application, you can type a very great value, for example 100000.

**DigitalProductExperienceFeedback**

If the registry entry does not exist, create a new DWORD value under Computer\HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 and name it

DigitalProductExperienceFeedback .

Type 0 for Decline or 1 for Agree .

**See also**

**Data Privacy 1**

**ProductExcellenceProgramFeedback**

If the registry entry does not exist, create a new DWORD value under

Computer\HKEY\_CURRENT\_USER\Software\Siemens\Tecnomatix Plant Simulation 2504 and name it ProductExcellenceProgramFeedback .

Type 0 for Decline or 1 for Agree .

<!-- image -->

**See also**

Data Privacy 2

## Starting PlantSimulationConsole.exe

Start Plant SimulationConsole.exe from the Command prompt.

<!-- image -->

**Introduction**

PlantSimulationConsole.exe is a console version of Plant Simulation without a user interface.

With it you can run simulations from the command line. You will typically use it to specify the simulation model file and the Frame in which the simulation is to be executed in a Command Prompt window:

PlantSimulationConsole.exe /f MyModel.spp /m .Models.Model

After the simulation is finished, the Plant Simulation process exits. The simulation model should therefore write the simulation results to a file on the file system.

The executable PlantSimulationConsole.exe is located in the Plant Simulation installation folder. The default installation folder for version 2504 is C:\Program Files\Siemens\Plant Simulation 2504 .

**Licensing**

PlantSimulationConsole.exe runs with a Simulation license or any higher license type.

If you configured your license in the UI version of Plant Simulation on the tab License , the PlantSimulationConsole will use this license configuration.

If you did not configure a license, define it with the environment variable SALT\_LICENSE\_SERVER.

**See also**

Specifying Start Options

Features of the Individual Licenses

