### \_Accessing Video Recording Settings

SimTalk provides the functions listed in the table of contents to the left for accessing and recording a video.

#### F3DfinishVideo [SimTalk]

Finishes the currently running video recording.

Remarks

If you started the video recording with the dialog Start Simulation Recording or the function F3DrecordSimulationVideo [SimTalk] , finishing the video recording will stop the simulation.

Type

Function

Syntax

F3DfinishVideo

Example

F3DfinishVideo

See also

Video Ribbon Tab &gt; Finish Recording

stop [SimTalk] - EventController

#### F3DisRecordingAVideo [SimTalk]

Returns if a video is recorded at the moment or not.

Type

Function

Syntax

F3DisRecordingAVideo -&gt; boolean

**Example**

```simtalk
-- If a video is currently being recorded we set the camera to different positions if F3DisRecordingAVideo -- First we want to show the model from a position we generated -- with the ribbon command 3D->View->Marks->Generate SimTalk Code... F3DconfigureView([1.043, -26.821, 13.465], 58.500, -17.565, .Models.Model) wait 15 -- Now we play the camera path Ani1 wait _3D.CameraAnimations.Ani1.play wait 5 -- We set the camera to another position and direction F3DconfigureView([1.043, -26.821, 13.465], 58.500, -17.565, .Models.Model) wait 10 -- Now we pause the to skip parts of the simulation F3DpauseVideo(true) wait 15 -- Now we continue recording F3DpauseVideo(false) wait 10
waituntil Source.Cont != void
var MU = Source.Cont -- We now attach the camera to a part on the source F3DAttachCamera(MU)
waituntil MU.Location = Conveyor2 -- Detach the camera F3DAttachCamera(void) -- We set the camera to another position and direction F3DconfigureView([1.043, -26.821, 13.465], 58.500, -17.565, .Models.Model) wait 10 -- Finish the video recording F3DfinishVideo end
```

#### F3DpauseVideo [SimTalk]

Pauses the currently running video recording or continues playing it.

Type

Function

Syntax

```simtalk
F3DpauseVideo([StartPause:boolean:=true])
```

**Parameter**

The optional parameter StartPause of data type boolean sets if the recording will be paused ( true or parameter not specified) or continued ( false ).

**Default Value of the Parameter**

The default value is true.

Example

F3DpauseVideo

See also

Video Ribbon Tab &gt; Pause/Resume Recording

#### F3DrecordSimulationVideo [SimTalk]

Starts the simulation or resumes it and records a video of it.

Remarks

3D records the video with the current settings of the dialog Record Simulation Video .

<!-- image -->

Deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer to permit the function F3DrecordSimulationVideo to copy data from another folder and write them to the model folder or its sub-folders. The function cannot copy files from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
F3DrecordSimulationVideo(FilePath:string, ObjectOfInterest:object/3D object, RealTimeScale:real[, FrameRate:integer:=25, Description:string/void:="", RecordApplication:boolean:=false, StartTime:time/void:=void, EndTime:time/void:=void, CameraPath:string:="", LoopInfinitely:boolean:=false, StartPathWithRecording:boolean:=false, EndRecordingWithPath:boolean:=false])
```

**Parameters**

- The parameter FilePath of data type string designates the path to the video file that is going to be recorded.
- The parameter ObjectOfInterest of data type object or 3D object designates the object from whose view the simulation is recorded. The object either has to be the root Frame of a simulation or be inserted into the root Frame . An object which does not have an EventController , for example a class, is not allowed.
- The parameter RealTimeScale of data type real designates the real timescale with which the video will be played later on.
- The optional parameter FrameRate of data type integer designates the frame rate for recording the video file. The default setting is 25 frames per second.

**Default Value of the Parameter**

The default value is 25.

- The optional parameter Description of data type string designates the descriptions that is shown on the first frame of the video.
- Specify void to show no description on the first frame.
- Specify an empty string "" to use the default description, i.e., the file name of the model. The default setting is "" .

**Default Value of the Parameter**

The default value is an empty string "" .

- The optional parameter RecordApplication of data type boolean sets if the entire application window will be recorded ( true ) or only the 3D window of the ObjectOfInterest ( false ).
- Specify false to record a window of an ObjectOfInterest , provided such a window is open.
- If no such window is open, Plant Simulation opens a suitable window.

**Default Value of the Parameter**

The default value is false.

- The optional parameter StartTime of data type time or void sets when recording starts.
- Specify void or nothing to start recording when the simulation is started or continued.
- If you specify a time, recording starts at this point in time.
- If the point in time is located in the past, relative to the current simulation time, the simulation is going to be reset beforehand.

**Default Value of the Parameter**

The default value is void.

- The optional parameter EndTime of data type time or void sets when recording terminates.
- Specify void or nothing to never terminate recording by itself.

- If you specify a time, recording and simulation run up to this point in time of the simulation and then terminates. In addition, an End Time which you typed into the EventController will be deactivated for the duration of the recording.

**Default Value of the Parameter**

The default value is void.

- The optional parameter CameraPath of data type string designates the camera path that will be played during the simulation and the recording of the video. If you specify an empty string "" or nothing no camera path is going to be played automatically.

**Note**

This parameter only applies to the Frame .

**Default Value of the Parameter**

The default value is an empty string "" .

- The optional parameter LoopInfinitely of data type boolean sets if camera path is looped infinitely.
- Specify true to play the path again from the start after reaching its end.
- Specify false or nothing to make the view remain at it location when the end of the path is reached.

**Note**

This parameter only applies to the Frame .

**Default Value of the Parameter**

The default value is false.

- The optional parameter StartPathWithRecording of data type boolean sets if the camera path will be played when recording starts ( true ) or when the simulation starts/continues (false or nothing).

**Note**

This parameter only applies to the Frame .

**Default Value of the Parameter**

The default value is false.

- The optional parameter EndRecordingWithPath of data type boolean sets if simulation and video recording are also terminated when reaching the end of the camera path ( true ) or if simulation and video recording are to be continued after the end of the path has been reached ( false nothing).

**Note**

This parameter only applies to the Frame .

**Default Value of the Parameter**

The default value is false.

**Example**

F3DrecordSimulationVideo("C:\Users\ha\Desktop\PlantSimulationVideo.avi", 6, 25, "")

**See also**

Prohibit Access to the Computer [model settings]

Start Simulation Recording

Video Ribbon Tab &gt; Start Simulation Recording

#### F3DrecordVideo [SimTalk]

Records a video of Plant Simulation or of the active 3D window.

Remarks

3D records the video with the current settings of the dialog Record Video .

<!-- image -->

If you deactivate the safety setting File &gt; Model Settings &gt; General &gt; Prohibit Access to the Computer , the function F3DrecordVideo can copy data from another folder and write them to the model folder or its sub-folders. The function cannot copy files from the model folder or its sub-folders.

Type

Function

Syntax

```simtalk
F3DrecordVideo(FilePath:string[, FrameRate:integer:=25, Description:string:="", RecordApplication:boolean:=false])
```

**Parameters**

- The parameter FilePath of data type string designates the path to the video file that is going to be recorded. By default, the file is saved here C:\Users\YourLoginName\Desktop\ .
- The optional parameter FrameRate of data type integer designates the frame rate for recording the video file. The default setting is 25 frames per second.

**Default Value of the Parameter**

The default value is 25.

- The optional parameter Description of data type string designates the descriptions that is shown on the first frame of the video.

**F3DrecordVideo [SimTalk]**

- Specify void to show no description on the first frame.
- Specify an empty string "" to use the default description, i.e., the file name of the model.

**Default Value of the Parameter**

The default value is an empty string "" .

- The optional parameter RecordApplication of data type boolean sets if the entire application window will be recorded ( true ) or only the 3D window of the ObjectOfInterest ( false ).

**Default Value of the Parameter**

The default value is false.

**Example**

F3DrecordVideo("C:\Users\ha\Desktop\PlantSimulationVideo.avi", 25, .Models.MyChocolatePlant)

**See also**

Prohibit Access to the Computer [model settings]

Video Ribbon Tab &gt; Start Simple Recording

