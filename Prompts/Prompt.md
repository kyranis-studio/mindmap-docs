the graph UI interaction have become a bit buggy make a full rewrite of it taking these action in consideration

action to implement in the graph node editor

* control click on multiple node to select them

* shift to snap to the grid

* control drag a node into a group to add it

* control drag a node from group to remove it make sure to stop the group extension while pressing control so it is possible to drag the node out from the group

* control while dragging a link to create routing

<br />

the shortcut are

control + D to duplicate a node

control + G to group ungroup the nodes

space to toggle pan mode

delete to delete the node

it will be better to use a state machine for this complex UI interaction
