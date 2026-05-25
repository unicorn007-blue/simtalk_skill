#### LEDs and States of the Mobile Objects

During the simulation runs Plant Simulation shows the state of the MUs with colored dots in the LED display area along the upper border of their icons in the Frame .

Each MU has at least one icon, named Default , which Plant Simulation uses to display the object in the Class Library and in the Toolbox . Within a simulation model, the state the MU is in determines which icon Plant Simulation uses, i.e., if the state changes, Plant Simulation attempts to switch to a different icon to indicate the change. An icon with the name of the state has to exist for this to work.

The table lists the different states in 2D.

<!-- image -->

| Description                                       | State Icon   | Color of the Icon   | Vector Graphic   |
|---------------------------------------------------|--------------|---------------------|------------------|
| The MU is Working .                               | Operational  |                     |                  |
| The MU is Waiting .                               | Waiting      |                     |                  |
| The Transporter is Failed .                       | Failed       |                     |                  |
| The Transporter is Paused .                       | Pause        |                     |                  |
| The Transporter is the tractor of a tugger train. | Tractor      |                     |                  |

**Note**

Plant Simulation can only switch to the icons pause , failed , and waiting if the icon operational exists. If the MU does not provide the icon operational , the state of the part and its representation may not match in the simulation model.

<!-- image -->

When you display the MUs as vector graphics, you can activate Show State to display the states blocked, failed, and paused. Plant Simulation displays the graphic for blocked with a yellow border, for failed it has a red border , and for

<!-- image -->

paused it has a blue border .

<!-- image -->

The default vector graphic of the Part looks like this , of the Container it looks like this , and of the Transporter it looks like this .

3D shows the state of the Transporter as a colored ring on a pole on the left-hand side by default.

<!-- image -->

##### Statistics of the Mobile Objects

<!-- image -->

See also

States &gt; State Graphic in 3D

LEDs and States of the Material Flow Objects in 2D

LEDs and States of the Energy Features

LEDs and States of the Frame

LEDs and States of the Exporter

LEDs and States of the Method

LEDs and States of the MQTT Interface

**Statistics of the Mobile Objects**

