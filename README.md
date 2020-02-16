# PathfindingBasic
This is a very basic pathfinding game algorithm in __Javascript__, visualized in a 2 dimensional view of a virtual city and a robot, which uses the streets of the city to move to the target. Multidimensional arrays are used to display the city and to generate the path to the target from the current position of the robot. The script is implemented and displayed in a __HTML__ file using __CSS__. Thus it can be opened by any familar browsers like Chrome etc. You can open the file under the following URL:__[http://www.littleorange.de/pathfinding/pathfinding.html](http://www.littleorange.de/pathfinding/pathfinding.html)__ . I appreciate any comments, critics and hints - Thank you in advance. 

For describing the project there are 3 sections:
## Design / Initialisation: 

__City Display:__ 

The whole city is displayed in a "chessboard", 2 dimensional view. The city is defined in a object array _citygrid_.All buildings, streets and empty places are saved in this array, the arrayposition is also the position where this item are in the city. For example the item _citygrid[1][2]_ represents the point x=2 and y=3.  The display of the array is realized with the __DOM__ and __CSS__. Fieldsizes, backgroundcolors are defined, the empty places are  shown in a "Wood"(green) or "Clear"(brown) using a Randomselection in Javascript. If the arrays are changed, also other Cities are possible to display. It is also possible to use bigger city sizes (not tested) by changing the arrays - currently a 8x8 size is used. 

__Robot Display / finding first position:__

In a separate array _streetgrid_ all items of _citygrid_ are saved, that have the attribute="street" are saved. As written before with the attributes _x_ and _y_ also the coordinates of all streets are saved in this array. For the first robot position,is determined by a random selection over all the street coordinates. Variables: _cur_x_robot_ and _cur_y_robot_. The code for the description can be found at the beginning of the script Line 42 and the function _loadfields()_ , which is executed after the html-file /site has been loaded completely (onload-Handler HTML body tag).
## Pathgenerating:

This is the core point of the script: How is the way from the current to the target point determined. How it is saved for the visualisation of the movement of the robot?

The target destination is set by random or speficic selected buldings (Array:_dullsville_build_). As written before the _sx_ and _sy_ attributes are the relevant coordinates for the streetaccess- and therefore for the robot.
The Pathgenerating is performed by the function _pathgenerate()_ The robot is moving with by chance selected direction. The possible directions are determined by the function _checksoround_: only if streets are placed certain directions (up, down, left, right) are possible. The function uses the citygrid to determine the possible direction dependent of the current position of the robot. The current direction can be changed (function _choosedir_) if a "crossing"-point is reached. A Crossing-point is a point with more than 2 streets suround. Two streets has the implication, that the current field is a straight street - Corners are not implemented. An exception is the first point - it is always a "crossing" point- no matter if there are only one (point on the cityborders) 2 (straight road) or more then two (crossing-point) streets soround.The selected direction is deleted in the crossingpoint (attribute: _dirs_), so that later on, this direction is not available. If the target is not reached with the chosen direction, the script jumps back to the last crossingpoint and gets a new direction. All points are saved in an objectarray _roadmap_. With _checksoround_ is being executed with each move, it also checks whether the target has been reached. In this case the _roadmap_ array is complete.
It is a multidimensional array. If a crossing point is reached, there can be munipal ways to reach the target. In this case a new branch in the _roadmap_ is generated. The reason for this is, that also all directions of this crossing can possibly _not_ lead to the target, if the cityborders are reached. In this case, the concerning branch is deletet from the _roadmap_ array, and the script switches to the crossing point before.The first point of the branch is the crossing point. Summarized all not relevant points / branches, which doesn't lead to the target are deleted (using array_slice-operation), and the script goes further until the target point is reached (_checksoround_) . 



- __Visualisation the movement of the robot:__ Using a timespan for each point of the path from current point to target point.

##Design / Initialisation


