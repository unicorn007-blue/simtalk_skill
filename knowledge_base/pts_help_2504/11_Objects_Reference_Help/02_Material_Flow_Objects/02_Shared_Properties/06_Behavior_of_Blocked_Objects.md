#### Behavior of Blocked Objects

A material flow object, whose Capacity is exhausted, will reject any MUs attempting to move onto it.

The object then enters these MUs into its Forward Blocking List , its Backward Blocking List , or its Exit Blocking List respectively. The blocking lists are managed according to the FIFO rule, first in first out. The first MU entered into the blocking list will also be the first to be removed from the blocking list after the blockage is removed. Once a processed MU exits a material flow object, and it thus is ready to receive the next one, the EventController informs the first MU in the blocking list that it now can move onto the material flow object.

See also

Capacity [general description]

Backward Blocking List , bwBlockList [SimTalk] - material flow objects

Exit Blocking List , exitBlockList [SimTalk] - material flow objects

Forward Blocking List , fwBlockList [SimTalk] - material flow objects

Entrance Locked [material flow objects]

Exit Locked [material flow objects]

