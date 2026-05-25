#### Time Consumption

A material flow object receives a MU , when some of its capacity is available and when it is not failed or paused, and its entrance is not closed.

The object rejects a MU and adds it to the end of its Forward Blocking List , Backward Blocking List , or Exit Blocking List if one of these conditions is met or if the entrance is closed because you set a recovery time, etc. After the object starts Working again, it processes the first MU in the Blocking List .

The material flow object checks the names of the MUs to determine if it has to set up and thus use a Set-up Time to process that type of MU . If MUs have different names, the object knows that it needs to set up for them.

**Note**

.MUs.Transporter:1 and .MUs.Transporter:2 have the same name.

When the first MU of a certain type enters an object it always has to set up. After receiving the MU , the object determines the processing time after which the MU exits.

Failures, controlled by the setting Failed and by the setting Active of the individual failure profiles , or pauses, controlled by the setting Paused/Planned/Unplanned , prolong the time a MU remains on an object. In addition, each object has an internal failure generator controlling the duration of and the interval between failures.

After the Processing Time has elapsed, the material flow object moves the MU on to its successor object within the flow of materials. If there is more than one successor, they are cyclically fed parts in succession.

The successor is the object that is connected to the selected object with a Connector and that succeeds it in the sequence of stations in the simulation model.

To reorder the sequence of the successors of the selected object, right-click the object in the Frame and select Reorder Successors on the context menu.

<!-- image -->

The predecessor is the object that is connected to the selected object with a Connector and that precedes it in the sequence of stations in the simulation model.

See also bwBlockList [SimTalk] - material flow objects exitBlockList [SimTalk] - material flow objects fwBlockList [SimTalk] - material flow objects Paused [state, material flow objects]

