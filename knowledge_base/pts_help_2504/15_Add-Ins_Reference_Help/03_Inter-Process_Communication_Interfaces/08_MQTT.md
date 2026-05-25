### MQTT

The MQTT Interface provides an open network protocol to transmit messages from device to device over the Internet. MQTT stands for M essage Q ueuing T elemetry T ransport.

**Icon**

<!-- image -->

**Description**

According to https://mqtt.org 'MQTT is an OASIS standard messaging protocol for the Internet of Things ( IoT ). It is designed as an extremely lightweight publish/subscribe messaging transport that is ideal for connecting remote devices with a small code footprint and minimal network bandwidth. MQTT today is used in a wide variety of industries, such as automotive, manufacturing, telecommunications, oil and gas, etc.'

The MQTT Interface provides a connection between Plant Simulation and an MQTT message broker. Plant Simulation can send and receive MQTT messages. You can, for example, use the MQTT Interface to connect AGVs with a control system or a fleet manager.

As the quality of service , that ensures the reliability of message delivery to the subscriber, 0 is preset. The MQTT Interface attempts to deliver MQTT messages only once. The Client does not have to confirm that it received the transmitted message, and it is not ensured that the message arrives in any case.

Consult the file ReadMe\_OSS.html in the Plant Simulation installation folder for information about the open-source software we use. The default installation folder for Plant Simulation 2504 is C:\Program Files\Siemens\Tecnomatix Plant Simulation 2504 .

The Profiler shows the entire MQTT Communication Statistics .

To show a tooltip with information about the MQTT Interface , hover with the mouse over it.

To change the length of the graphic and the anchor points of the MQTT Interface , click Show

Manipulators on the Edit ribbon tab or press M on the keyboard.

<!-- image -->

Add the Object to the Simulation Model

To add the MQTT Interface to the Class Library , click Manage Class Library &gt; Basic Objects &gt;

<!-- image -->

Information Flow &gt; MQTT on the Home ribbon tab.

<!-- image -->

See also

Functions for Communicating with an HTTP Server

#### Dialog Box of the MQTT Interface

Dialog Box of the MQTT Interface

Double-click the icon of the MQTT Interface to open its dialog box.

Edit Simulation Properties

In the dialog box you can change its simulation properties . The shared properties are described under Dialog Items of the Objects .

Edit Animation Properties

To edit the 3D properties of the object in the dialog box Edit 3D Properties [dialog] .

<!-- image -->

<!-- image -->

- Click the button Edit 3D Properties in the lower left corner of the simulation properties dialog box.
- Select the object in the model and press the spacebar .

In 3D you can manipulate the graphic of the object by clicking Show Manipulators [button] on the Edit ribbon tab or by pressing M on the keyboard.

##### Active [check box] - MQTT

Active [check box] - MQTT

To activate the MQTT Interface and to connect it with the configured MQTT broker, select this check box. Then, click Apply or OK .

<!-- image -->

To disconnect and to deactivate the MQTT Interface , clear the check box. Then, click Apply or OK .

SimTalk

Active [SimTalk] - MQTT

See also

Tab Session Log

Tab Attributes

Tab Attributes

The tab Attributes provides the settings listed in the table of contents to the left.

###### Host Name [MQTT]

Type in the Name or the IP address of the host computer on which the MQTT broker runs.

If the MQTT broker runs on the same computer as the MQTT Interface , you have to type in localhost or the IP address 127.0.0.1 .

If you do not specify a host name, Plant Simulation shows an error message when activating the MQTT Interface .

SimTalk

HostName [SimTalk] - MQTT

**Port [MQTT]**

###### Port [MQTT]

Type in the Port Number with which the MQTT Interface exchanges data with other applications.

<!-- image -->

The setting Host Name sets the MQTT broker with which a connection is established. The port then is relevant, because other applications or protocols might be provided or supported on the server on which the MQTT broker is running.

- The standard port for an unencrypted connection is 1883.
- The standard port for an encrypted connection with TLS is 8883.
- If you type in 0 as port number, the MQTT Interface uses, depending on a possible encryption, the respective standard port.

SimTalk

Port [SimTalk] - MQTT

See also

Host Name [MQTT]

###### Protocol Version [drop-down list]

Select the protocol version with which the MQTT Interface establishes a connection with an MQTT broker. Protocol version 5.0 is the default setting.

<!-- image -->

**Note**

The Callback Method of the MQTT Interface only receives properties in JSON format when using the MQTT protocol version 5.0. For this setting the parameter Protocol of the Callback Method will always be empty.

The parameter Properties of the method publish for sending additional information via the properties only works with the MQTT protocol version 5.0.

The read-only attributes of the MQTT Interface containing properties only work with the MQTT Protocol Version 5.0.

You have to set the MQTT protocol version before connecting to the MQTT brokers or before activating the MQTT Interface respectively.

You can also select the number of a lower protocol version.

- MQTT protocol version 3.1.
- MQTT protocol version 3.1.1.

SimTalk

**ProtocolVersion [SimTalk]**

See also

Callback Method [MQTT]

publish [SimTalk]

**Callback Method [MQTT]**

###### Callback Method [MQTT]

Click the ellipsis button and select a Method object in the dialog Select Object . Type in the source code of the Callback Method .

<!-- image -->

As soon as the MQTT broker confirms the subscription, published messages reaching the MQTT broker from any clients are delivered to the MQTT Interface and passed on to the Callback Method for further processing.

Instead of choosing Select Object , you can also select the Method in a Frame , drag it to the text box and drop it there.

**Create a Control that is a Method of the Object**

To create a control as a user-defined attribute of data type Method , for example:

<!-- image -->

- Type a meaningful name into the text box and select Create Control . Plant Simulation then inserts self.Name\_you\_typed\_in\_for\_the\_control , such as self.A1Ctrl .
- Select Create Control . Plant Simulation then inserts self.OnBuilt\_in\_name\_of\_the\_control , such as self.OnEntrance .

Type the source code of this control into the Method that opens.

To edit the source code later on:

- Press F2 .
- Or hold down Shift and double-click into the text box.
- Or click the tab User-defined and double-click the name of the Method in the list.
- To delete this control, delete the user-defined attribute . If you only delete the name from the text box, the user-defined attribute is retained.

The standard callback method as a user-defined attribute looks like this:

**Parameters**

The callback method has three parameters:

```simtalk
param topic:string, payload:any, properties:json
```

- The parameter Topic of data type string is the topic belonging to the respective subscription specified by the publishing client.
- The parameter Payload of data type any designates the payload, which can be passed to the method as text, as JSON data, or as an array of integer numbers for binary data (one integer per byte).

If the received payload is parsed by the JSON parser without raising an error, the result may not be of data type JSON. Any resulting array of data, even of JSON objects, every string or number may be contained in the payload parameter, if the type of this parameter is any and the MQTT properties contain a ContentType property of value 'application/json'.

To distinguish the passed payload, you can, for example use the functions isString , isJson , or isArray / isInteger

Specify the payload as a value of data type string to attempt to pass all incoming payload data, even JSON data, as text. Binary payload data of a received message then causes an error because an array of integer numbers cannot be passed.

Specify the payload as a value of data type json to make the callback method only accept JSON data. Text, numbers, arrays and binary data of a received message cause an error.

If the content to be received contains valid JSON data, but the result of parsing the received data does not result in data of the type JSON (compare the method parse ), this data will cause an error. If the MQTT properties contain a ContentType of value 'application/json', but the payload does not contain necessary JSON objects, use the data type any . Otherwise, use the parameter Payload of data type string and parse the received payload inside the callback method.

- The parameter Properties of data type json designates the MQTT properties which were attached to the received broadcast by the publishing client.

<!-- image -->

**Note**

The Callback Method only receives properties in JSON format when using the MQTT protocol version 5.0. For older MQTT protocol versions the parameter Protocol of the Callback Method will always be empty.

You can also specify the parameters as follows:

```simtalk
param topic:string, payload:string, properties:json
```

If the payload is of data type string , JSON data is passed as text. Binary data of a received message cause an error as no array of integer numbers can be passed.

```simtalk
param topic:string, payload:json, properties:json
```

If the payload is of data type json , the callback method can only receive JSON data. Text and binary data of a received message cause an error.

SimTalk

CallbackMethod [SimTalk] - MQTT

See also

Select Object [for controls]

subscribe [SimTalk]

Functions for Communicating with an HTTP Server

###### Session Log

To activate the session log of the MQTT Interface , select this check box. To not activate it, clear the check box.

<!-- image -->

If the session log is active, the MQTT Interface adds entries to the session log.

If the session log is not active, the MQTT Interface does not add entries to the session log.

**Note**

After activating and showing the Session Log on the Tab Session Log , the ongoing update of the list of entries will slow down Plant Simulation , especially if the size of the session log increases.

**SimTalk**

SessionLogActive [SimTalk]

**Clear on Reset**

###### Clear on Reset

To delete the session log of the MQTT Interface when you reset the simulation, select this check box.

<!-- image -->

To keep the session log when you reset the simulation, clear the check box.

**SimTalk**

ClearSessionLogOnReset [SimTalk]

Log Size

Type in the maximum number of entries in the session log of the MQTT Interface .

<!-- image -->

Type in -1 to allow an unlimited number of entries in the session log.

Type in 0 to delete all entries from the session log and prevent that new entries are added.

SimTalk

SessionLogSize [SimTalk]

Tab Security

Tab Security

The tab Security provides the settings listed in the table of contents to the left.

<!-- image -->

User Name [MQTT]

Type in the User Name with which you want to log in to the MQTT broker.

Plant Simulation saves the user name in the model file.

SimTalk

UserName [SimTalk] - MQTT

###### User Name [MQTT]

###### Password [MQTT]

Type in the Password with which you want to log in to MQTT broker .

Plant Simulation encrypts the password and saves it in the model file.

SimTalk

setPassword [SimTalk] - MQTT

**Client ID**

###### Client ID

Type in the Client ID , i.e., the client identification, to let the MQTT broker identify the client.

<!-- image -->

The Client ID must be unique.

If you do not specify a Client ID , the MQTT broker will generate a random Client ID .

The MQTT specifications allow the Client ID to be up to 23 characters long and to only contain alphanumerical characters. All MQTT brokers may accept longer Client IDs and Client IDs with characters outside of the alphanumerical range though.

SimTalk

ClientID [SimTalk]

###### Use TLS

To use the encryption protocol TLS (Transport Layer Security) for the secure transmission of data over the Internet, select this check box.

<!-- image -->

**Note**

To enable TLS encryption, you must provide a CA Certificate File .

Otherwise the activated setting Use TLS will generate an error when connecting with a MQTT message broker by activating the client.

**SimTalk**

TLS [SimTalk]

**CA Certificate File**

###### CA Certificate File

Click the folder button and select the certificate file from the certifying authority . Or type in the name of the file.

<!-- image -->

**Note**

To enable TLS encryption, you must provide a CA Certificate File .

Otherwise the activated setting Use TLS will generate an error when connecting with a MQTT message broker by activating the client.

CA Certificate Files are required to validate the certificate of the MQTT broker.

If you use several certificate files from the certifying authority, which will be used to validate the certificate of the MQTT broker, we advise to create a folder. You can then store the certificate files there and reference this folder instead of a file. It is important that this folder is known to OpenSSL and that the folder OpenSSL is rehashed after any changes.

If, on the other hand, it is clear which CA has issued the certificate of the MQTT broker and if only this certificate has to be validated over again, it suffices to specify the path to this CA certificate file.

**SimTalk**

TLSCAFileOrFolder [SimTalk]

###### Certificate File

Click the folder button and select the Certificate File . Or type in the name of the file.

<!-- image -->

If you specify a Certificate File , you also have to specify a Private Key File .

If you do not specify these two settings, this causes an error while establishing the connection when activating the MQTT Interface !

For establishing a TLS encryption the Certificate File and the Private Key File are not mandatory, except if the MQTT broker expects that a certificate including its keys is provided for you.

Your IT department might provide you with this file.

SimTalk

**TLSCertificateFile [SimTalk]**

See also

Private Key File

**Private Key File**

###### Private Key File

Click the folder button and select the Private Key File . Or type in the name of the file.

<!-- image -->

If you specify a Private Key File , you also have to specify a Certificate File .

If you do not specify one of these two setting, this causes an error while establishing the connection when activating the MQTT Interface !

For establishing a TLS encryption the Private Key File and the Certificate File are not mandatory, except if the MQTT broker expects that a certificate including its keys is provided for you.

If the Key File itself is encrypted, you have to provide the respective password with the method setTLSKeyFilePassword .

Your IT department might provide you with this file.

SimTalk

TLSKeyFile [SimTalk]

setTLSKeyFilePassword [SimTalk]

See also

Key File Password

Certificate File

###### Key File Password

Type in the Key File Password if the private key file is encrypted. Your IT department might provide you with this file.

<!-- image -->

**SimTalk**

setTLSKeyFilePassword [SimTalk]

See also

Private Key File

##### Tab Subscriptions

The tab Subscriptions shows settings about the subscriptions which you established with the method subscribe .

<!-- image -->

- Topic designates a specific topic for which the connected MQTT broker is to deliver messages.

Examples for topics you set with the method subscribe are:

- Sensors/temperature/DMG300/MillingHead

Subscribes all messages relating to the temperature sensors of the milling head of a DMG300 machine.

- AssemblyLines/Line1/power/electricity/hookup1
- Subscribes all messages relating to the first electrical hookup of the first AssemblyLine.
- QM/product\_A/tests/mechanical/surface/front/quality
- Subscribes all messages relating to surface tests of the quality management of product A.
- You can use these placeholders to create a topic filter:
- ◊ + designates a single hierarchy level
- ◊ # designates a hierarchy level and all its sub-hierarchies

Examples for topic filters you can set with the method subscribe are:

- ◊ Sensors/temperature/+/MillingHead

Subscribes all messages for milling heads relating to temperature sensors independent of the associated machines.

- ◊ AssemblyLine/+/power/electricity/hookup1
- Subscribes all messages relating to first electrical hookup of all assembly lines.
- ◊ AssemblyLine/+/power/#

Subscribes all messages relating to the power supply of all assembly line of all power types and all hook ups.

- QoS (Quality of Service) ensures the reliability of message delivery to the subscriber. 0 is the preset. The MQTT Interface attempts to deliver MQTT messages only once. The Client does not have to confirm that it received the transmitted message and it is not ensured that the message arrives in any case.
- Send no local sets if the messages which the MQTT Interface broadcasts arrive at the MQTT Interface via the set subscriptions again ( true ) or not ( false ).
- Retain as published sets if the MQTT broker retains published messages ( true ) or not ( false ).

Normally the MQTT brokers reset this setting for retained messages after broadcasting them.

If the connection to the MQTT broker is interrupted and then re-established again and the subscriptions are restored again, retained messes are normally sent to the MQTT Interface .

If the setting is reset after the message was broadcast once, this message cannot be received again after the connection was restored.

- Send retain never sets if no retained messages are to be broadcast to the MQTT Interface after establishing the subscription, but only newly received messages from the MQTT broker.
- ID is the ID of the subscription.

SimTalk publish [SimTalk]

subscribe [SimTalk] unsubscribe [SimTalk]

**Tab Session Log**

##### Tab Session Log

The MQTT Interface lists the active connections on the tab Session Log .

It shows the name of the host computer on which the process is running and, separated by a colon, the internal identifying number for each connection per session.

**Note**

After activating and showing the Session Log here, the ongoing update of the list of entries will slow down Plant Simulation , especially if the size of the session log increases.

SimTalk

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

See also

Show Sessions Log

Save Session Log

Tab User-defined

Tab User-defined

Define your own attributes as described under the Tab User-defined .

The MQTT Interface provides the built-in user-defined attributes init and Subscriptions .

They are intended to create a defined initial state when starting the simulation.

<!-- image -->

**init [SimTalk] - MQTT**

###### init [SimTalk] - MQTT

The built-in user-defined attribute named init establishes the connection to the configured MQTT broker and creates the subscriptions defined in the subscriptions table.

<!-- image -->

**See also**

Subscriptions [SimTalk] - MQTT

###### Subscriptions [SimTalk] - MQTT

The built-in user-defined attribute named Subscriptions helps to create a defined initial state when starting the simulation.

Type in the settings for the subscriptions to be created.

<!-- image -->

The user-defined init method then establishes the connection to the configured MQTT broker and creates the subscriptions defined in the table.

**Watchable**

The attribute is watchable .

**Navigate Menu**

##### Navigate Menu

The commands are described under the Navigate Menu .

View Menu

The View Menu provides commands to access its functions. Refresh [on View menu] Show Attributes and Methods [on View menu] Edit Ignored Items Clear Ignored Items SimTalk updateDialog [SimTalk] See also View Menu [general description]

Tools Menu Tools Menu The Tools Menu provides commands to access its functions. Edit Controls Edit Observers 3D Save Session Log Clear Session Log

**Save Session Log**

###### Save Session Log

Saves the session log of the MQTT Interface to an HTML file.

The command opens the dialog Save As . Then, select the drive, and the file type, and enter a name for the log file.

Plant Simulation saves the contents of the session log in the same HTML format to a file as used in the read-only attribute SessionLog .

See also

SessionLog [SimTalk]

Tab Session Log

###### Clear Session Log

Deletes the contents of the session log of the MQTT Interface .

See also

clearSessionLog [SimTalk]

Tab Session Log

**Help Menu**

##### Help Menu

The commands are described under the Help Menu .

##### LEDs and States of the MQTT Interface

During the simulation runs Plant Simulation shows the state of the MQTT Interface as one or more colored dots in the LED display along the upper border of the icon in the Frame .

3D shows the states as horizontally arranged cubes along the top of the picture of the object.

The LED display can display several active states at the same time, while the state icon can only display the single state it represents.

<!-- image -->

<!-- image -->

<!-- image -->

| Description                                                                    | LED    | Looks like this   |
|--------------------------------------------------------------------------------|--------|-------------------|
| The MQTT Interface is connecting/disconnecting .                               | yellow |                   |
| The MQTT Interface is connected .                                              | green  |                   |
| The MQTT Interface subscribed contents .                                       | orange |                   |
| The MQTT Interface has detected an error or the MQTT broker reported an error. | red    |                   |

See also

States &gt; State Graphic in 3D

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Mobile Objects

LEDs and States of the Method

#### Methods of the MQTT Interface

\_Methods of the MQTT Interface

The MQTT Interface provides:

- The methods listed in the table of contents to the left.
- The Methods of All Objects .

To view all of the methods , read-only attributes and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

An example of the Syntax line of the individual methods might look like this:

<!-- image -->

- The expression &lt;Path&gt; designates the path of the object to which the method applies.
- The signature of the method, consisting of the identifier and the data type of the parameter, is listed in parentheses. The expression (Parameter:string) , for example, designates a parameter of data type string . Instead of a constant value, you can also use a variable of the required type or a method that returns the required data type.

**Note**

Make sure to enter the parentheses for expressions within parentheses (…). Not entering them may lead to unexpected results and open the Debugger .

Optional parameters are listed within brackets. The expression [,Parameter:boolean] , for example, means that you can, but do not have to enter the boolean parameter.

If a parameter has a default value, the signature shows the default value after the parameter.

If the method has a return value, the signature shows its data type after the arrow -&gt;.

clearSessionLog [SimTalk]

Deletes all entries from the session log of the MQTT Interface designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.clearSessionLog

Example

MyMQTT.clearSessionLog

SimTalk

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

See also

Clear Session Log

##### logMessage [SimTalk]

Creates a message in the session log of the MQTT Interface designated by &lt;Path&gt;.

Remarks

The session log highlights each message with a specific color bar to the left of the message. This color coding enables you to recognize the messages created by the method logMessage .

Type

Method

Syntax

```simtalk
< Path >.logMessage([Caption:string, ]Message:string])
```

**Parameters**

- The optional parameter Caption of data type string designates the caption of the message.
- The parameter Message of data type string designates the message as such. If you also specify the Caption , Plant Simulation indents the message below the caption.

**Example**

MyMQTT.logMessage("This is a caption", "This is the message") // puts two entries into the session log, a colored caption and an indented message below MyMQTT.logMessage( 'This is the message') // puts an entry into the session log, the message is shown in color

**SimTalk**

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

**logMessage [SimTalk]**

##### publish [SimTalk]

Publishes the specified payload with the specified topic at the connected MQTT broker of the MQTT Interface designated by &lt;Path&gt;.

Remarks

The MQTT broker then broadcasts the payload to other connected clients that subscribed this topic.

As the quality of service that ensures the reliability of message delivery to the subscriber, 0 is preset. The MQTT Interface attempts to deliver MQTT messages only once. The Client does not have to confirm that it received the broadcast message, and it is not ensured that the message arrives in any case.

Type

Method

Syntax

```simtalk
< >.publish(Topic:string, Payload:any[, Retain:boolean:=false,
Path Properties:json:={}]) → void
```

**Parameters**

- The parameter Topic of data type string designates the specific topic for which the connected MQTT broker is to deliver messages.
- The parameter Payload of data type any designates the data that can be broadcast by this publishing process. This can be binary data in the form of a one-dimensional array of data type integer , plain text, or JSON data.

If you pass the payload as text or JSON data, you have to meet the rules of the MQTT standard.

To send JSON data as payload according to the MQTT standard you have to pass a Variable of data type JSON to the Method as parameter for the payload.

The textual representation of the JSON structure, which is then generated, consists of a single line and thus does not contain any line breaks or indentations (control characters).

- The optional parameter Retain of data type boolean sets if this message is to be retained by the MQTT broker to be delivered to subscriptions created later on. If the message is not retained, this message, including the payload, is only broadcast to the currently existing subscribers.

**Default Value of the Parameter**

The default value is false.

- The optional parameter Properties of data type json designates JSON data containing MQTT properties for publishing messages.

**Note**

The parameter Properties of the method publish for sending additional information via the properties only works if the MQTT protocol version is set to 5.0.

Each JSON element that cannot be translated into an MQTT property creates an error. The same applies to each JSON element or each MQTT property which is not intended for publishing.

An application example is the MQTT property Topic-Alias allowing you to define an alias for a certain topic or using the alias if the passed topic is an empty string "".

The MQTT Interface supports these properties for publishing:

- Message-Expiry designates the time in seconds until the message expires and is deleted by the MQTT broker.
- Content-Type designates a string that is defined according to IANA, which defines a MIME type for the payload, such as text/html or text/xml. The Content-Type is set automatically depending on the type payload to text/plain or application/json. Setting the Content-Type in the properties overrides this.
- Response-Topic sets that this message is treated as a request, Response-Topic defines the topic, without placeholder, under which responses to this request have to be published.
- Correlation-Data contains Base64 encoded as value in the JSON element. Enables to align the responses to a request to exactly one request under the Response-Topic.

This property is only relevant for the sender of a request and the receiver of an answer to this request.

- Topic-Alias : The value has the data type integer .
- ◊ If the specified topic is a non-empty string and if this property exists, the MQTT Interface defines an alias for the topic with the MQTT broker.
- ◊ If the specified topic is an empty string "" and if this property exists, the alias defined with the MQTT broker will be reused for a topic of this MQTT Interface .
- ◊ If no topic alias is defined for the MQTT Interface with the MQTT broker, the MQTT broker creates an error.
- User-Property is an array of JSON elements, which are translated with their names and values into the MQTT user properties

**Default Value of the Parameter**

The default value is an empty JSON string.

**Return Value**

The return value has the data type boolean .

true if publishing the messages was successful.

false if publishing failed.

**Example**

```simtalk
var properties:json
properties.parse("{\"User-Property\": {\"Client-ID\": 1, \"Client-Name\": \"Client01\" }}") // Since JSON cannot have multiple "User-Property" elements, the implementation uses an // array of JSON elements or a JSON element to build multiple "UserProperty" MQTT properties." // broadcasts the payload as string, as plain text // automatic Content-Type is text/plain MyMQTT.publish("QM/product_A/tests/mechanical/surface/front/quality", true, "3", properties) // broadcasts the payload as JSON structure // automatic Content-Type is application/json var payload:json payload.parse("{\"average roughness value\": 3}") MyMQTT.publish("QM/product_A/tests/mechanical/surface/front/quality", true, payload, properties) // broadcasts the payload as JSON structure // automatic Content-Type is application/json var binaryData:integer[] := [1] MyMQTT.publish("QM/product_A/tests/mechanical/surface/front/quality", payload, true, properties)
```

**See also**

Tab Subscriptions subscribe [SimTalk] unsubscribe [SimTalk] PublishProperties [SimTalk] ProtocolVersion [SimTalk]

setPassword [SimTalk] - MQTT

Sets the password with which you log in to the MQTT Interface designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setPassword(Password:string)

Parameter

The parameter Password of data type string designates the password.

Example

MyMQTT.setPassword("MyPassword123")

See also

Password [MQTT]

setTLSKeyFilePassword [SimTalk]

Sets the password of the key file of the TLS encryption protocol of the MQTT Interface designated by &lt;Path&gt;.

Type

Method

Syntax

&lt; Path &gt;.setTLSKeyFilePassword(Password:string)

Parameter

The parameter Password of data type string designates the password.

Example

MyMQTT.setTLSKeyFilePassword("TheKeyFilePassword123")

See also

Key File Password

**subscribe [SimTalk]**

##### subscribe [SimTalk]

Contacts the MQTT broker of the MQTT Interface designated by &lt;Path&gt;.

**Remarks**

subsribe creates a subscription with the specified settings for the specified topic filter with the MQTT broker.

As soon as the MQTT broker confirms the subscription, published messages that reach the MQTT broker from any Clients are delivered to the MQTT Interface which passes it on to the Callback Method for further processing.

Type

Method

Syntax

```simtalk
< Path >.subscribe(TopicFilter:any[, SendNoLocal:boolean:=false, RetainAsPublished:boolean:=false, SendRetainNever:boolean:=false]) → integer
```

**Parameters**

- The parameter TopicFilter of data type any designates a specific topic for which the connected MQTT broker is to deliver messages.

Examples for topics are:

- Sensors/temperature/DMG300/MillingHead

Subscribes all messages relating to the temperature sensors of the milling head of a DMG300 machine.

- AssemblyLines/Line1/power/electricity/hookup1

Subscribes all messages relating to the first electrical hookup of the first AssemblyLine.

- QM/product\_A/tests/mechanical/surface/front/quality

Subscribes all messages relating to surface tests of the quality management of product A.

You can uses these placeholders to create a topic filter:

- + designates a single hierarchy level
- # designates a hierarchy level and all its sub-hierarchies

**Examples for topic filters are:**

- Sensors/temperature/+/MillingHead

Subscribes all messages for milling heads relating to temperature sensors independent of the associated machines.

- AssemblyLine/+/power/electricity/hookup1

Subscribes all messages relating to first electrical hookup of all assembly lines.

- AssemblyLine/+/power/#

Subscribes all messages relating to the power supply of all assembly line of all power types and all hook ups.

- The optional parameter SendNoLocal of data type boolean sets if the messages, which the MQTT Interface broadcasts, arrive at the MQTT Interface via the set subscriptions again ( true ) or not ( false ).

**Default Value of the Parameter**

The default value is false.

- The optional parameter RetainAsPublished of data type boolean sets if the MQTT broker retains published messages ( true ) or not ( false ).

Normally the MQTT brokers reset this setting for retained messages after broadcasting them.

If the connection to the MQTT broker is interrupted and then re-established again and the subscriptions are restored again, retained messes are normally sent to the MQTT Interface .

If the setting is reset after the message was broadcast once, this message cannot be received again after the connection was restored.

**Default Value of the Parameter**

The default value is false.

- The optional parameter SendRetainNever of data type boolean sets if no retained messages are to be broadcast to the MQTT Interface after establishing the subscription ( true ), but only newly received messages from the MQTT broker ( false ).

**Return Value**

The return value has the data type integer .

The return value is the ID of the created subscription at the MQTT broker.

If an error occurs, for example in the optional properties or in the communication with the MQTT broker, Plant Simulation opens the Debugger and shows the error.

**Example**

MyMQTT.subscribe("AssemblyLine/+/power/electricity/hookup1")

##### subscribe [SimTalk]

See also Tab Subscriptions publish [SimTalk] unsubscribe [SimTalk] Callback Method [MQTT]

unsubscribe [SimTalk]

Terminates the subscription of the MQTT Interface designated by &lt;Path&gt; with the MQTT broker.

Type

Method

Syntax

&lt; Path &gt;.unsubscribe(Subscription:integer) → boolean

Parameter

The parameter Subscription of data type integer designates the ID of the subscription to be terminated.

Return Value

The return value has the data type boolean .

true if the subscription was terminated.

false if it could not be terminated, for example if no subscription with the ID exists.

If an error occurs when terminating the subscription, Plant Simulation opens the Debugger and shows the error.

Example

MyMQTT.unsubscribe(2)

See also

Tab Subscriptions

publish [SimTalk]

subscribe [SimTalk]

#### Read-Only Attributes of the MQTT Interface

\_Read-Only Attributes of the MQTT Interface

The MQTT Interface provides:

- The read-only attributes listed in the table of contents to the left.
- The \_Read-Only Attributes of All Objects .

**Note**

The read-only attributes of the MQTT Interface containing properties only work with the MQTT Protocol Version 5.0.

You can query the values of the read-only attributes , but you cannot set them as Plant Simulation computes the value for the point-in-time at which you query it. In most cases a read-only attribute corresponds to an unavailable dialog item on one of the tabs of the object, for example on the tab Statistics .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

To query the value of a read-only attribute , you might, for example, type:

```simtalk
print MyMQTT.ConnackProperties
```

##### ConnackProperties [SimTalk]

Returns a JSON data structure. It contains the returned MQTT properties of the MQTT broker while confirming the last established connection with the MQTT Interface designated by &lt;Path&gt;.

Remarks

This encompasses, among others, the Topic-Alias-Maximum of the MQTT broker, the Server-Keep-Alive of the MQTT broker, the Session-Expiry of the MQTT broker, etc.

Type

Read-only attribute

Syntax

&lt; Path &gt;.ConnackProperties -&gt; json

Watchable

The read-only attribute is watchable .

**Note**

If you are watching ConnackProperties with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type json .

The return value is an empty JSON string { } if no connection has been established yet.

Example

print MyMQTT.ConnackProperties

See also

ConnackReason [SimTalk]

Edit Observers [general description]

##### ConnackReason [SimTalk]

Returns the text of the last connection of the MQTT Interface designated by &lt;Path&gt;.

Remarks

The text describes the success or the error that occurred in more detail.

After the message of the MQTT broker or of the MQTT Interface the so-called reason code is executed decimal or hexadecimal.

Type

Read-only attribute

Syntax

&lt; Path &gt;.ConnackReason -&gt; string

Watchable

The read-only attribute is watchable .

**Note**

If you are watching ConnackReason with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type string .

The return value is an empty string "" if no connection has been established yet.

Example

print MyMQTT.ConnackReason

See also

ConnackProperties [SimTalk]

Edit Observers [general description]

##### DisconnectProperties [SimTalk]

Returns a JSON data structure. It contains the returned MQTT properties of the MQTT broker while disconnecting the last established connection with the MQTT Interface designated by &lt;Path&gt;.

Remarks

The properties encompass, among others, the Session-Expiry, the Server-Reference, etc.

Type

Read-only attribute

Syntax

< Path >.DisconnectProperties -> json

Watchable

The read-only attribute is watchable .

**Note**

If you are watching DisconnectProperties with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type json .

Is an empty JSON string if no connection has been disconnected yet.

Example

```simtalk
print MyMQTT.DisconnectProperties
```

See also

DisconnectReason [SimTalk]

Edit Observers [general description]

##### DisconnectReason [SimTalk]

Returns the reason of the last disconnection of the MQTT Interface designated by &lt;Path&gt; from the MQTT broker.

Remarks

The disconnection of the MQTT Interface from the MQTT broker can be in order because you deactivated the MQTT Interface . It can also be caused by an MQTT protocol error causing the MQTT broker to disconnect.

After the message of the MQTT broker or of the MQTT Interface the reason code is executed in decimal or hexadecimal fashion.

Type

Read-only attribute

Syntax

&lt; Path &gt;.DisconnectReason -&gt; string

Watchable

The read-only attribute is watchable .

**Note**

If you are watching DisconnectReason with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type string .

Is an empty JSON string if no connection has been disconnected yet.

Example

print MyMQTT.DisconnectReason

**See also DisconnectProperties [SimTalk] Edit Observers [general description]**

##### PublishProperties [SimTalk]

Returns a JSON data structure of the MQTT Interface designated by &lt;Path&gt;.

Remarks

It contains the returned MQTT properties of the MQTT broker for the last unsuccessful attempt trying to publish payload of the MQTT Interface designated by &lt;Path&gt;, compare the method publish .

If no connection has been disconnected yet, an empty JSON data structure is returned.

As numerous messages can be published, PublishProperties will only be filled if an error occurs and thus is empty when the payload was published successfully.

Type

Read-only attribute

Syntax

&lt; Path &gt;.PublishProperties -&gt; json

Watchable

The read-only attribute is watchable .

**Note**

If you are watching PublishProperties with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type json .

Is an empty JSON string if no error occurred yet while publishing.

Example

```simtalk
print MyMQTT.PublishProperties
```

See also PublishReason [SimTalk] publish [SimTalk] Edit Observers [general description]

##### PublishReason [SimTalk]

Returns the text which describes the reaction of the MQTT broker to the attempt to publish payload of the MQTT Interface designated by &lt;Path&gt;.

Remarks

As numerous of messages can be published, PublishReason will only be filled if an error occurs and thus is empty when payload was published successfully.

After the message of the MQTT broker or of the MQTT Interface the so-called reason code is executed decimal or hexadecimal.

Type

Read-only attribute

Syntax

&lt; Path &gt;.PublishReason -&gt; string

Watchable

The read-only attribute is watchable .

**Note**

If you are watching PublishReason with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type string .

If an error occurs, it is described in the returned text.

Is an empty JSON string if no payload has been published yet.

Example

print MyMQTT.PublishReason See also PublishProperties [SimTalk] publish [SimTalk] Edit Observers [general description]

SessionLog [SimTalk]

Returns the contents of the session log of the MQTT Interface designated by &lt;Path&gt; as HTML text.

Remarks

The HTML text is UFT-8 encoded, and you can, for example, save it to a file.

Type

Read-only attribute

Syntax

&lt; Path &gt;.SessionLog -&gt; string

Return Value

The return value has the data type string .

Example

print MyMQTT.SessionLog

See also

Tab Session Log

Save Session Log

SimTalk

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

SessionLogMessagesCount [SimTalk]

Returns the current number of entries in the session log of the MQTT Interface designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.SessionLogMessagesCount -&gt; integer

Return Value

The return value has the data type integer .

Example

print MyMQTT.SessionLogMessagesCount

See also

Tab Session Log

Save Session Log

SimTalk

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

##### SubackReason [SimTalk]

Returns the text of the last subscription of the MQTT Interface designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.SubackReason -&gt; string

Watchable

The read-only attribute is watchable .

**Note**

If you are watching SubackReason with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type string .

Is an empty JSON string if no connection to an MQTT broker has been established yet.

The return string describes either the success of the action or the error in more detail.

Example

print MyMQTT.SubackReason

See also

UnsubackReason [SimTalk]

Edit Observers [general description]

##### SubscribeReason [SimTalk]

Returns the text which describes the reaction of the MQTT broker to the attempt to create a subscription of the MQTT Interface designated by &lt;Path&gt;.

Remarks

After the message of the MQTT broker or of the MQTT Interface the so-called reason code is executed decimal or hexadecimal.

Type

Read-only attribute

Syntax

&lt; Path &gt;.SubscribeReason -&gt; string

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type string .

Is an empty JSON string if no subscriptions have been created yet.

If an error occurs, it is described in the returned text.

Example

print MyMQTT.SubscribeReason

See also

UnsubscribeReason [SimTalk]

##### UnsubackReason [SimTalk]

Returns the text of the last termination of a subscription of the MQTT Interface designated by &lt;Path&gt;.

Type

Read-only attribute

Syntax

&lt; Path &gt;.UnsubackReason -&gt; string

Watchable

The read-only attribute is watchable .

**Note**

If you are watching UnsubackReason with an observer, Plant Simulation will call the observer method twice. The first time when emptying the read-only attribute before an interaction with an MQTT broker. The second time after the response of the MQTT broker was written to the read-only attribute.

Return Value

The return value has the data type string .

Is an empty JSON string if no connection to an MQTT broker has been established yet.

Either describes the success of the action or the error in more detail.

Example

print MyMQTT.UnsubackReason

See also

SubackReason [SimTalk]

Edit Observers [general description]

UnsubscribeReason [SimTalk]

Returns the text which describes the reaction of the MQTT broker to the attempt to unsubscribe a subscription of the MQTT Interface designated by &lt;Path&gt;.

Remarks

After the message of the MQTT broker or of the MQTT Interface the so-called reason code is executed decimal or hexadecimal.

Type

Read-only attribute

Syntax

&lt; Path &gt;.UnsubscribeReason -&gt; string

Watchable

The read-only attribute is watchable .

Return Value

The return value has the data type string .

Is an empty JSON string if no subscriptions have been unsubscribed yet.

If an error occurs, it is described in the returned text.

Example

print MyMQTT.UnsubscribeReason

See also

SubscribeReason [SimTalk]

##### Attributes of the MQTT Interface

\_Attributes of the MQTT Interface

The MQTT Interface provides:

- The attributes listed in the table of contents to the left.
- The Attributes of All Objects .

To view all of the methods , read-only attributes , and attributes of the object, open the window Show Attributes and Methods . The figure below illustrates the information using the example of the object Station .

<!-- image -->

- Select Show Attributes and Methods on the context menu of the Class Library to show the attributes and methods of the selected Class .
- Press the F8 key or click Show Attributes and Methods on the Home ribbon tab of the Frame into which you inserted an instance to show the attributes and methods of the selected Instance .

You can set the value of an attribute and you can get its value, either with the check boxes, the text boxes and drop-down lists in the dialog windows or by assigning values to the respective attributes.

- To set the value of an attribute, you might, for example, type:
- To get the value of an attribute, you might, for example, type:

```simtalk
MQTTInterface.HostName := "127.0.0.1"
print MQTTInterface.HostName
posit := Station.cont.XPos
```

##### Active [SimTalk] - MQTT

Active [SimTalk] - MQTT

Activates the object designated by &lt;Path&gt; ( true ) or deactivates it ( false ) .

Remarks

After being activated, the MQTT Interface establishes a connection with the configured MQTT broker.

In doing so it uses the attributes which can be configured for authenticating and securing the connection.

Title

Attribute

Syntax

&lt; Path &gt;.Active:boolean

Watchable

The attribute is watchable .

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyMQTT.Active := true
```

See also

Active [check box] - MQTT

##### CallbackMethod [SimTalk] - MQTT

Designates the Callback Method of the MQTT Interface designated by &lt;Path&gt;.

Title

Attribute

Syntax

&lt; Path &gt;.CallBackMethod:method

Parameters

The callback method has three parameters:

param topic:string, payload:any, properties:json

param topic:string, payload:string, properties:json

- The parameter topic of data type string is the topic belonging to the respective subscription specified by the publishing client.
- The parameter payload of data type any designates the payload, which can be passed to the method as text, as JSON data, or as an array of integer numbers for binary data (one integer per byte).

If the received payload is parsed by the JSON parser without raising an error, the result may be not of type JSON. Any resulting array of data, even of JSON objects, every string or number may be in the payload parameter, if the type of this parameter is any and the MQTT properties contain a Content-Type property of value 'application/json'.

To distinguish the passed payload, you can, for example, use the functions isString , isJson , or isArray / isInteger .

Specify the payload as a value of data type string to attempt to pass all incoming payload data, even JSON data, as text. Binary payload data of a received message then raises an error because an array of integer numbers cannot be passed.

Specify the payload as a value of data type Json so that the callback method can only accept JSON data. Text, numbers, arrays and binary data of a received message raise an error.

If the content to be received is valid JSON data, but the result of parsing the received data does not result in data of the type JSON (compare the method parse ), this data will raise an error. If the MQTT properties contain a Content-Type of value 'application/json', but the payload does not contain necessary JSON objects, use the data type any .

Otherwise, use the payload parameter of data type string and parse the received payload inside the callback method.

- The parameter properties of data type json designates the MQTT properties which were attached to the received broadcast by the publishing client.

**Note**

The Callback Method only receives properties in JSON format when using the MQTT protocol version 5.0. For older MQTT protocol versions, the parameter Protocol of the Callback Method will always be empty.

You can also specify the parameters as follows:

If the payload is of data type string , JSON data is passed as text. Binary data of a received message raises an error as no array of integer numbers can be passed.

```simtalk
param topic:string, payload:json, properties:json
```

If the payload is of data type json , the callback method can only receive JSON data. Text and binary data of a received message raise an error.

Assignment Value

You can assign a value of data type method .

Example

MyMQTT.CallBackMethod := &amp;MQTTMethod

See also

Callback Method [MQTT]

parse [SimTalk]

isString [SimTalk]

isJson [SimTalk]

isArray [SimTalk]

isInteger [SimTalk]

##### ClearSessionLogOnReset [SimTalk]

Deletes the session log ( true ) of the MQTT Interface designated by &lt;Path&gt; or does not delete it ( false ) when you reset the simulation.

Type

Attribute

Syntax

&lt; Path &gt;.ClearSessionLogOnReset:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyMQTT.ClearSessionLogOnReset := true

SimTalk

clearSessionLog [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

See also

Clear on Reset

##### ClientID [SimTalk]

ClientID [SimTalk]

Sets the client identification (ID) of the MQTT Interface designated by &lt;Path&gt;

Remarks

The MQTT Interface uses the Client ID to let the MQTT broker identify the client.

The Client ID must be unique.

If you do not specify a Client ID , the MQTT broker will generate a random Client ID .

The MQTT specifications allow the Client ID to be up to 23 characters long and to only contain alphanumerical characters. All MQTT brokers may accept longer Client IDs and Client IDs with characters outside of the alphanumerical range though.

Type

Attribute

Syntax

&lt; Path &gt;.ClientID:string

Assignment Value

You can assign a value of data type string .

Example

MyMQTT.ClientID := "ThisIsA-Unique-ClientID"

See also

Client ID

HostName [SimTalk] - MQTT

Sets the name or the IP address of the MQTT Interface designated by &lt;Path&gt;.

Remarks

The name or the IP address is used, together with the attribute Port , for establishing the connection of the MQTT Interface with the MQTT broker.

Type

Attribute

Syntax

```simtalk
< Path >.HostName:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyMQTT.HostName := "127.0.0.1"
```

See also

Host Name [MQTT]

Port [MQTT]

Port [SimTalk] - MQTT

##### Port [SimTalk] - MQTT

Port [SimTalk] - MQTT

Sets the port number with which the MQTT Interface designated by &lt;Path&gt; exchanges data with other applications.

Remarks

HostName sets with which MQTT broker a connection is established. The port then is relevant, because other applications or protocols might be provided or supported on the server on which the MQTT broker is running.

Type

Attribute

Syntax

&lt; Path &gt;.Port:integer

Assignment Value

You can assign a value of data type integer .

- Specify 1883 for the standard port for an unencrypted connection.
- Specify 8883 for the standard port for an encrypted connection with TLS.
- Specify 0 to use the respective standard port, depending on a possible encryption.

**Example**

```simtalk
MyMQTT.Port := 1883
```

See also

Port [MQTT]

HostName [SimTalk] - MQTT

##### ProtocolVersion [SimTalk]

Sets the protocol version that the MQTT Interface designated by &lt;Path&gt; uses to establish a connection with an MQTT broker.

Remarks

You have to set the MQTT protocol version before connecting to the MQTT brokers or before activating the MQTT Interface respectively.

**Note**

The Callback Method of the MQTT Interface only receives properties in JSON format when using the MQTT protocol version 5.0. For this setting the parameter Protocol of the Callback Method will always be empty.

The parameter Properties of the method publish for sending additional information via the Properties only works with the MQTT protocol version 5.0.

The read-only attributes of the MQTT Interface containing Properties only work with the MQTT Protocol Version 5.0.

Type

Attribute

Syntax

&lt; Path &gt;.ProtocolVersion:integer

**Assignment Value**

You can assign a value of data type integer .

- Specify 310 for the MQTT protocol version 3.1.
- Specify 311 for the MQTT protocol version 3.1.1.
- Specify 500 for the MQTT protocol version 5.0.

**Example**

MyMQTT.ProtocolVersion := 500

See also Protocol Version [drop-down list] CallbackMethod [SimTalk] - MQTT publish [SimTalk]

##### QoS [SimTalk]

Sets the Quality of Service (QoS) to be used for publishing messages and for receiving messages in subscriptions of the MQTT Interface designated by &lt;Path&gt;.

Remarks

The Quality of Service has three levels:

- Delivery at most once (0), also called "fire and forget".

Messages are published from a client to a broker and a broker to a client without any confirmation for having received those messages.

- Delivery at least once (1)

The receiving part acknowledges the receipt of the message in a two-step handshake, so that the sending part can resend the message if the acknowledgment is missing.

- Delivery exactly once (2)

A four-step handshake ensures that the message is delivered exactly once.

The higher the Quality of Service is, the more network traffic is generated and the more time is needed to deliver the message.

Type

Attribute

Syntax

```simtalk
< Path >.QoS:integer
```

Assignment Value

You can assign a value of data type integer .

You can assign the values 0 , 1 , or 2 for the three QoS levels.

**Example**

```simtalk
MyMQTT.QoS := 0
```

**ReadInterval [SimTalk]**

##### ReadInterval [SimTalk]

Sets the interval that elapses before the MQTT Interface designated by &lt;Path&gt; checks for new incoming messages.

Remarks

You can assign a value between 0 and 250 milliseconds to the ReadInterval . Plant Simulation will always round it the next lower multiple of 10 milliseconds.

The default setting of the ReadInterval is to 40 ms. Assign 0 to restore the default.

Type

Attribute

Syntax

```simtalk
< Path >.ReadInterval:integer
```

**Assignment Value**

You can assign a value of data type integer .

You can specify a multiple of 10 between 0 and 250 .

**Examples**

```simtalk
MyMQTT.ReadInterval :=
MyMQTT.ReadInterval := 22
print MyMQTT.ReadInterval   // returns 20
MyMQTT.ReadInterval := 259
print MyMQTT.ReadInterval   // returns 250
MyMQTT.ReadInterval := 260  // returns a value range error
MyMQTT.ReadInterval := 0    // restores the default read interval
print MyMQTT.ReadInterval   // returns 40
```

##### SessionLogActive [SimTalk]

Activates the session log ( true ) of the MQTT Interface designated by &lt;Path&gt; or does not activate it ( false ).

Remarks

If the session log is active, the MQTT Interface adds entries to the session log.

If the session log is not active, the MQTT Interface adds no entries to the session log.

Type

Attribute

Syntax

&lt; Path &gt;.SessionLogActive:boolean

Assignment Value

You can assign a value of data type boolean .

Example

MyMQTT.SessionLogActive := true

SimTalk

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogSize [SimTalk]

SessionLogMessagesCount [SimTalk]

See also

Session Log

##### SessionLogSize [SimTalk]

Sets the maximum number of entries in the session log of the MQTT Interface designated by &lt;Path&gt;.

Type

Attribute

Syntax

&lt; Path &gt;.SessionLogSize:integer

Assignment Value

You can assign a value of data type integer .

Specify -1 to allow an unlimited number of entries in the session log.

Specify 0 to delete all entries from the session log and prevent that new entries are added.

Example

MyMQTT.SessionLogSize := 1000

SimTalk

clearSessionLog [SimTalk]

ClearSessionLogOnReset [SimTalk]

logMessage [SimTalk]

SessionLog [SimTalk]

SessionLogActive [SimTalk]

SessionLogMessagesCount [SimTalk]

See also

Log Size

**TLS [SimTalk]**

##### TLS [SimTalk]

Sets if the MQTT Interface designated by &lt;Path&gt; uses the encryption protocol TLS (Transport Layer Security) for the secure transmission of data over the Internet ( true ) or not ( false ).

Remarks

**Note**

To enable TLS encryption, you must provide a CA Certificate File with the attribute TLSCAFileOrFolder .

Otherwise the setting true of the attribute TLS will generate an error when connecting with a MQTT message broker by activating the client.

When you are using TLS encryption, you can specify its settings with these attributes and methods:

- TLSCAFileOrFolder [SimTalk]
- TLSCertificateFile [SimTalk]
- TLSKeyFile [SimTalk]
- setTLSKeyFilePassword [SimTalk]

Type

Attribute

Syntax

&lt; Path &gt;.TLS:boolean

Assignment Value

You can assign a value of data type boolean .

Example

```simtalk
MyMQTT.TLS := true
```

See also

Use TLS

Port [MQTT]

**Host Name [MQTT]**

##### TLSCAFileOrFolder [SimTalk]

Sets the name of the certificate file or folder from the certifying authority of the MQTT Interface designated by &lt;Path&gt;.

Remarks

**Note**

To enable TLS encryption, you must provide a CA Certificate File .

Otherwise the setting true of the attribute TLS will generate an error when connecting with a MQTT message broker by activating the client.

CA certificate files are required to validate the certificate of the MQTT broker.

If you use several certificate files from the certifying authority, which will be used to validate the certificate of the MQTT broker, we advise to create a folder. You can then store the certificate files there and reference this folder instead of a file. It is important that this folder is known to OpenSSL and that the folder OpenSSL is rehashed after any changes.

If, on the other hand, it is clear which CA has issued the certificate of the MQTT broker and if only this certificate has to be validated over again, it suffices to specify the path to this CA certificate file.

Type

Attribute

Syntax

&lt; Path &gt;.TLSCAFileOrFolder:string

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyMQTT.TLSCAFileOrFolder := "MyTLSCACertificateFile"
```

See also

Use TLS

**TLS [SimTalk]**

**CA Certificate File**

##### TLSCertificateFile [SimTalk]

Sets the name of the certificate file of the TLS encryption of the MQTT Interface designated by &lt;Path&gt;.

Remarks

If you assign a path to a Certificate File , you also have to assign a path to a Key File with the attribute TLSKeyFile .

If one of these two attributes is not set, this causes an error while establishing the connection when activating the MQTT Interface !

For establishing a TLS encryption the TLSKeyFile and TLSCertificateFile are not mandatory, except if the MQTT broker expects that a certificate including its keys is provided for you.

Type

Attribute

Syntax

&lt; Path &gt;.TLSCertificateFile:string

Assignment Value

You can assign a value of data type string .

Example

MyMQTT.TLSCertificateFile := "MyTLSCertificateFile"

See also

Certificate File

TLSKeyFile [SimTalk]

##### TLSKeyFile [SimTalk]

Sets the name of the key file of the TLS encryption protocol of the MQTT Interface designated by &lt;Path&gt;.

Remarks

If one of these two attributes is not set, this causes an error while establishing the connection when activating the MQTT Interface !

For establishing a TLS encryption the TLSKeyFile and TLSCertificateFile are not mandatory, except if the MQTT broker expects that a certificate including its keys are provided for you.

If the key file itself is encrypted, you have to provide the respective password with the method setTLSKeyFilePassword .

Type

Attribute

Syntax

```simtalk
< Path >.TLSKeyFile:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyMQTT.TLSKeyFile := "MyTLSKeyFile"
```

See also

Private Key File

TLSCertificateFile [SimTalk]

setTLSKeyFilePassword [SimTalk]

##### UserName [SimTalk] - MQTT

UserName [SimTalk] - MQTT

Sets the username of the MQTT Interface designated by &lt;Path&gt; used for logging in to the MQTT broker.

Type

Attribute

Syntax

```simtalk
< Path >.UserName:string
```

Assignment Value

You can assign a value of data type string .

Example

```simtalk
MyMQTT.UserName := "MyUsernameABC"
```

See also

User Name [MQTT]

#### ActiveX

