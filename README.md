# PathfindingBasic
This is a very basic pathfinding game algorithm in __Javascript__, visualized in a 2 dimensional view of a virtual city and a robot, which uses the streets of the city to move to the target. Multidimensional arrays are used to display the city and to generate the path to the target from the current position of the robot. The script is implemented and displayed in a __HTML__ file using __CSS__. Thus it can be opened by any familar browsers like Chrome etc. You can open the file under the following URL:__[http://www.littleorange.de/pathfinding/pathfinding.html](http://www.littleorange.de/pathfinding/pathfinding.html)__ . I appreciate any comments, critics and hints - Thank you in advance. 

For describing the project there are 3 sections:
- __Design / Initialisation:__ Further informations how the city, it's buildings streets and "empty" fields are displayed, which technologies are used to achieve this, and how the robot is shown.
- __Pathgenerating:__ This is the core point of the script: How is the way from the current to the target point determined. How it is saved for the visualisation of the movement of the robot?
- __Visualisation the movement of the robot:__ Using a timespan for each point of the path from current point to target point.

##Design / Initialisation

The whole city is displayed in checkboard, 2 dimensional view. The city is defined in two object arrays.The array _citygrid_ includes the fields in distinction wheter it contains a street ("street") or no-street("clear"). The array _dullsville_build_ contains all buildings of the city with their names (attribute:name) , their 2-dimensional coordinates(attributes:x,y) and their 2-dimensional coordinates for the streetaccess(sx,sy). The display of the array is realized with the __DOM__ and __CSS__.
