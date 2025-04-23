## Snake Robot - ROS Controllers


### Instructions to run the code:
- Clone the repo using: $ git clone https://github.com/aakka7/snake_robot.git
- $ cd snake_robot/snakebot_ws
- $ catkin_make
- $ source devel/setup.bash
- To spawn the controllers and the model in gazebo: $ roslaunch snakebot snakebot.launch
- To run the gait simulation, for example: to move the snake in the simple forward motion:
  - Open a new terminal
  - Change the directory to /snakebot_ws
  - $ source devel/setup.bash
  - $ rosrun snakebot forward.py
 
### Common error fixes
To fix error:
```
[ERROR] Could not load controller 'joint_<#>_position_controller' because controller type 'effort_controllers/JointPositionController' does not exist. 
```
Ensure effort controller is installed (we're using noetic)
```
sudo apt-get install ros-<your-ros-distro>-effort-controllers
```

To fix error:
```
[ERROR] [1745438802.398592968, 0.511000000]: Exception thrown while initializing controller 'joint_<#>_position_controller'. Could not find resource 'rod_<#>_joint' in 'hardware_interface::EffortJointInterface'.
```
Ensure is installed controlle and controllers is installed (we're using noetic)
```
sudo apt-get install ros-<your-ros-distro>-ros-control ros-<your-ros-distro>-ros-controllers
```

### Notes
- Gait is now in its own folder outside of `scripts` to remove circular dependencies
- Coordinates in `forward.py` appear correct from plots
- ==TODO== Determine why movement not occurring in Gazebo simulation

## From Original Repo
### Results: Output video

[![All the snake gaits](https://user-images.githubusercontent.com/32901101/111253024-ca6d4e00-85e8-11eb-8b49-166eb2cf8421.PNG)](https://drive.google.com/file/d/1BfiJ1PDn6ounzhUILLyYK5kYYPiaXl7P/view?usp=sharing)

[![Transformer gait](https://user-images.githubusercontent.com/32901101/111253242-3bad0100-85e9-11eb-8c0c-89df66aeea76.PNG)](https://drive.google.com/file/d/1lpOsV6T_p5WpRXYhA7TPNdCAyq_wULQ6/view?usp=sharing)


### References:
- [https://en.wikipedia.org/wiki/Gait](https://en.wikipedia.org/wiki/Gait)
- [https://en.wikipedia.org/wiki/Sidewinding](https://en.wikipedia.org/wiki/Sidewinding)
- [https://www.ivlabs.in/uploads/1/3/0/6/130645069/rebis.pdf](https://www.ivlabs.in/uploads/1/3/0/6/130645069/rebis.pdf)
- [http://biorobotics.ri.cmu.edu/projects/modsnake/gaits/gaits.html](http://biorobotics.ri.cmu.edu/projects/modsnake/gaits/gaits.html)
- [https://userweb.ucs.louisiana.edu/~brm2286/locomotn.htm](https://userweb.ucs.louisiana.edu/~brm2286/locomotn.htm)
- [http://biorobotics.ri.cmu.edu/research/gaitResearch.php](http://biorobotics.ri.cmu.edu/research/gaitResearch.php)



