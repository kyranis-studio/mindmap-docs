you are an experienced ui developer. rewrite the graph ui interaction system for a node editor from scratch. implement the following features and behaviors, using a state machine architecture for handling complex ui interactions:

features to implement:

node selection:

* ctrl + click to select multiple nodes

* single click to select a node

* click outside to deselect

grid snapping:

* hold shift to enable grid snapping while dragging nodes

* snap nodes to grid positions when shift is held

Grouping:

* ctrl + drag a node into a group to add it to the group

* ctrl + drag a node from within a group to remove it, stop group extension while holding ctrl so you can drag the node out

* ctrl + G to group selected nodes

* ctrl + G again to ungroup selected nodes

Node manipulation:

* ctrl + D to duplicate selected nodes

* delete to delete selected nodes

* drag nodes to move them freely

View controls:

* spacebar to toggle pan mode

* pan the canvas when in pan mode

Link creation:

* ctrl + drag while creating a link to create routing points

Architecture:

* use a state machine pattern to manage all ui interaction states (idle, selecting, dragging, panning, linking, grouping, etc.)

* ensure clean state transitions between all modes

* handle edge cases like releasing ctrl during group drag operations

* make the system modular and maintainable

Write the complete implementation following best practices for ui state management.
