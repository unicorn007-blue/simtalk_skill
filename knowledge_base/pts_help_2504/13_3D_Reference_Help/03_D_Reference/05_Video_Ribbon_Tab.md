### Video Ribbon Tab

The Video ribbon tab of the 3D window provides commands to access its functions.

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

<!-- image -->

| Command                    | Looks like this   | SimTalk function                   |
|----------------------------|-------------------|------------------------------------|
| Start Simple Recording     |                   | F3DrecordVideo [SimTalk]           |
| Start Simulation Recording |                   | F3DrecordSimulationVideo [SimTalk] |
| Pause/Resume Recording     |                   | F3DpauseVideo [SimTalk]            |
| Cancel Recording           |                   | -                                  |
| Finish Recording           |                   | F3DfinishVideo [SimTalk]           |
| Play Video                 |                   | -                                  |

**Note**

The other tabs on the Ribbon Bar provide additional commands pertaining to 3D .

See also

**Record a Video**

\_Accessing Video Recording Settings

#### Start Simple Recording

Start Simple Recording

Click Start Simple Recording and select the settings for recording and saving the AVI file. This then records a video of Plant Simulation or of the active 3D window without any connection with a simulation.

<!-- image -->

<!-- image -->

The video will be recorded in real-time, meaning that recording a minute of physical real time corresponds to a minute of playback time in the video. You might, for example, use this type of video recording to demonstrate how to operate a model .

To start recording the video with the selected settings, click Start .

To close the dialog without starting the recording and without applying settings, click Cancel .

**SimTalk**

F3DrecordVideo [SimTalk]

Output File

Accept the default namePlantSimulationVideo.avi -for the finished AVI file or type a different path and name into the text box.

<!-- image -->

By default, the file is saved here C:\Users\YourLoginName\Desktop\ . To select another folder to save the AVI file to, click Browse .

<!-- image -->

Once you click Finish Recording , Plant Simulation writes the video it recorded to the file and folder you set above. If you do not type in another name, the file will be overwritten when you create a new video.

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

**Frame Rate [video settings]**

##### Frame Rate [video settings]

Accept the default frame rate of 30 frames per second for recording the video or type a frame rate of your choice into the text box Frame Rate .

<!-- image -->

The higher the Frame Rate , the faster the video plays.

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

Description [video]

Type in the description that will be shown in the first frame of the video.

If you do not type in a description, Plant Simulation automatically uses the file name of the model as Description .

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

**Record Entire Application**

##### Record Entire Application

To record the entire content of the entire Plant Simulation application window, select this check box.

<!-- image -->

Clear the check box to record the active 3D window.

SimTalk

F3DrecordSimulationVideo [SimTalk]

##### Resize For

To resize the Plant Simulation window to be recorded to a certain video format, click the respective button.

- Click HD to resize the window to be recorded to the size of 1280x720 pixels.
- Click Full HD to resize the window to be recorded to the size of 1920×1080 pixels.
- Click UHD 4K to resize the window to be recorded to the size of 3840x2160 pixels.

**Start**

##### Start

To start recording the video with the selected settings, click this button.

<!-- image -->

##### Start Simulation Recording

Start Simulation Recording

Click Start Simulation Recording and select the settings for recording and saving the AVI file. This starts both the simulation or continues it and the video recording of the simulation.

<!-- image -->

The video records in scaled simulation time, meaning that the number of minutes of simulation time, which you entered as Real-time x [video] , corresponds to one minute playback time of the video.

You can, for example, use this type of video recording to play the simulated production with realistic time behavior. With Start Simulation-time and End Simulation-time you can set the time span that interests you.

<!-- image -->

To start recording the video with the selected settings, click Start .

To close the dialog without starting the recording and without applying settings, click Cancel .

SimTalk

F3DrecordSimulationVideo [SimTalk]

##### Output File

##### Output File

Accept the default namePlantSimulationVideo.avi -for the finished AVI file or type a different path and name into the text box.

<!-- image -->

By default, the file is saved here C:\Users\YourLoginName\Desktop\ . To select another folder to save the AVI file to, click Browse .

<!-- image -->

Once you click Finish Recording , Plant Simulation writes the video it recorded to the file and folder you set above. If you do not type in another name, the file will be overwritten when you create a new video.

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

##### Frame Rate [video settings]

Accept the default frame rate of 30 frames per second for recording the video or type a frame rate of your choice into the text box Frame Rate .

<!-- image -->

The higher the Frame Rate , the faster the video plays.

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

##### Description [video]

Description [video]

Type in the description that will be shown in the first frame of the video.

If you do not type in a description, Plant Simulation automatically uses the file name of the model as Description .

SimTalk

F3DrecordVideo [SimTalk]

F3DrecordSimulationVideo [SimTalk]

Real-time x [video]

Type in the real-time factor for real-time mode. The video will later be played with this real-time factor .

See also

Real-time x [EventController]

F3DrecordSimulationVideo [SimTalk]

**Record Entire Application**

##### Record Entire Application

To record the entire content of the entire Plant Simulation application window, select this check box.

<!-- image -->

Clear the check box to record the active 3D window.

SimTalk

F3DrecordSimulationVideo [SimTalk]

##### Start Simulation-time

Type in the simulation time at which recording of the video starts.

<!-- image -->

- If you do not specify a time, recording starts when the simulation is started or continued.
- If you do specify a time, recording starts at this point in time of the simulation.
- If the simulation is already running and the point in time is located in the past, relative to the current simulation time, the simulation will be reset before starting the recording.

See also

Start Date [EventController]

F3DrecordSimulationVideo [SimTalk]

**End Simulation-time**

##### End Simulation-time

Type in the simulation time at which recording of the video ends.

<!-- image -->

- If you do not specify a time, the recording never terminates by itself.
- If you do specify a time, the recording and the simulation run to this point in time of the simulation and then ends. In addition, an End time , which you typed into the EventController , will be deactivated for the duration of the recording.

See also

End Time [EventController]

F3DrecordSimulationVideo [SimTalk]

Play camera path

Play Camera Path

Select if and which camera path you would like to play. Plant Simulation shows the camera paths that you defined on the tab Camera Animation for the Frame .

<!-- image -->

If you select a camera path , Plant Simulation activates the settings below. Plant Simulation plays the camera path during the simulation and the recording of the video.

<!-- image -->

**Note**

These settings only apply to the Frame as only the Frame provides camera animations.

- Loop Infinitely
- Start Path with Recording
- End Recording with Path End

See also

F3DrecordSimulationVideo [SimTalk]

Camera Animation [Frame] &gt; Animation Paths [camera animation]

###### Loop Infinitely

To loop the path infinitely, select the check box.

<!-- image -->

Clear the check box to stop playing the path after reaching the end of the path.

**See also**

F3DrecordSimulationVideo [SimTalk]

**Start Path with Recording**

###### Start Path with Recording

To start playing the camera path when recording of the video starts, select the check box.

<!-- image -->

Clear the check box to play the camera path when the simulation starts or continues.

See also

F3DrecordSimulationVideo [SimTalk]

###### End Recording with Path End

To terminate the simulation and recording of the video when the end of the camera path has been reached, select the check box.

Clear the check box to continue the simulation and recording the video when the end of the camera path has been reached.

See also

F3DRecordSimulationVideo

**Resize For**

##### Resize For

To resize the Plant Simulation window to be recorded to a certain video format, click the respective button.

- Click HD to resize the window to be recorded to the size of 1280x720 pixels.
- Click Full HD to resize the window to be recorded to the size of 1920×1080 pixels.
- Click UHD 4K to resize the window to be recorded to the size of 3840x2160 pixels.

##### Start

To start recording the video with the selected settings, click this button.

#### Pause/Resume Recording

Pauses the active recording session, which you can then resume later on.

<!-- image -->

See also

F3DpauseVideo [SimTalk]

#### Cancel Recording

Closes and ends the active recording session without saving the recorded video file.

<!-- image -->

#### Finish Recording

Terminates the active recording session. This closes and saves the recorded video file, which you can then play by clicking Play .

<!-- image -->

See also

F3DfinishVideo [SimTalk]

#### Play Video

Opens the dialog of the default video player on your computer. To start playing the video, click Play .

<!-- image -->

#### Context Menus in 3D

