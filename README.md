# RoboticsND-MapMyWorld
Implement robot with camera sensor in ROS/Gazebo and map simulated world using this robot and SLAM.

# Setup

```
mkdir -p MapMyWorld/catkin_ws/src
cd MapMyWorld/catkin_ws/src
git clone https://github.com/max-kazak/RoboticsND-MapMyWorld.git .
catkin_init_workspace
cd ..
catkin_make
```

# Run code
Terminal1 (launching simulation):

```
cd MapMyWorld/catkin_ws/
source devel/setup.bash
roslaunch my_robot world.launch
```

Terminal2 (setting up robot controls):

```
cd MapMyWorld/catkin_ws/
source devel/setup.bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

Terminal3 (launching SLAM):

```
cd MapMyWorld/catkin_ws/
source devel/setup.bash
roslaunch my_robot mapping.launch
```

# After mapping
View mapping database:

```
rtabmap-databaseViewer ~/.ros/rtabmap.db
```

To run localization with built map:

```
cd MapMyWorld/catkin_ws/
source devel/setup.bash
roslaunch my_robot localization.launch
```