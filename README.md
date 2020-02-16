# PathfindingBasic
This is a very basic pathfinding game algorithm in __Javascript__, visualized in a 2 dimensional view of a virtual city and a robot, which uses the streets of the city to move to the target. Multidimensional arrays are used to display the city and to generate the path to the target from the current position of the robot. The script is implemented and displayed in a __HTML__ file using __CSS__. Thus it can be opened by any familar browsers like Chrome etc. You can open the file under the following URL:__[http://www.littleorange.de/pathfinding/pathfinding.html](http://www.littleorange.de/pathfinding/pathfinding.html)__ . I appreciate any comments, critics and hints - Thank you in advance. 

For describing the project there are 3 sections:
- __Design / Initialisation:__ The whole city is displayed in a "chessboard", 2 dimensional view. The city is defined in a object array _citygrid_.All buildings, streets and empty places are saved in this array, the arrayposition is also the position where this item are in the city. For example the item _citygrid[1][2]_ represents the point x=2 and y=3.  The display of the array is realized with the __DOM__ and __CSS__. Fieldsizes, backgroundcolors are defined, the empty places are  shown in a "Wood"(green) or "Clear"(brown) using a Randomselection in Javascript. If the arrays are changed, also other Cities are possible to display. In a separate array _streetgrid_ all items of _citygrid_ are saved, that have the attribute="street" are saved. As written before with the attributes _x_ and _y_ also the coordinates of all streets are saved in this array. For the first robot position,is determined by a random selection over all the street coordinates. Variables: _cur_x_robot_ and _cur_y_robot_.
- __Pathgenerating:__ This is the core point of the script: How is the way from the current to the target point determined. How it is saved for the visualisation of the movement of the robot?
- __Visualisation the movement of the robot:__ Using a timespan for each point of the path from current point to target point.

##Design / Initialisation


