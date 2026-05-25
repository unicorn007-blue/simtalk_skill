### Pack a Model and Send It to Another User

To pack and send a Plant Simulation model to somebody, who does not have Plant Simulation installed on his computer, you can use Pack and Go .

When you create a Pack and Go model , you can select if you want to restrict the permissions to a Plant Simulation Viewer License . If the check box is not selected, you can pass the license to be used with the start parameter /L to the Pack&amp;Go application . This enables you to use features of the superior license, provided this license is available. If you do not specify the start parameter, the freely available Viewer license will be used.

<!-- image -->

Pack and Go takes all files needed for starting the selected simulation model with a Plant Simulation Viewer License , packs the files, and saves them as a self-extracting executable. You can send this packed model to a customer for example, who can open the model by double-clicking it.

**Note**

The Pack and Go executable does not include all Plant Simulation features, even if you do not restrict the license. As we want the executable to be as small as possible, we do not include the entire Plant Simulation installation. This prevents you from using the OPCUA Interface or the Teamcenter Interface in Plant Simulation for example.

- To start Pack and Go , select File &gt; Share &gt; Pack and Go in the Plant Simulation window.
- To save your model, before sending it, click Yes in the dialog that opens.
- Navigate to the folder into which you want to save the model file. Enter a name and click Save .
- Click OK after Pack-and-Go successfully created the package. Then, distribute the file, for example by sending it as an e-mail or by putting it in your Intranet, etc.

<!-- image -->

<!-- image -->

- The recipient can double-click the file you sent and start the simulation to view what you wanted to show.

As the Pack-and-Go model uses the Plant Simulation Viewer License only a limited set of functions is available.

