# Multi-Turtlebot3-Cartographer

## Abstract
It is a repository that uses Cartographer using several real turtlebot3 burgers, not simulation.<br>
It is introduced in ROBOTIS to perform cartographer with one Turtlebot3, but it is not introduced to perform it by specifying namespaces on multiple units.<br>
Cartographer and turtlebot3 packages must be installed, and need to understand TF Tree configuration and urdf, lua files.<br>

## Environment
- catkin
- ubuntu 20.04 for PC and turtlebot3(Rasbraspberry pi4)
- ROS1 Noetic

## For Turtlebot3
All robots do this,
```
ssh ubuntu@{Your turtlebot's IP}
```
```
ROS_NAMESPACE=tb3_1 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_1" set_lidar_frame_id:="tb3_1/base_scan"
```
```
ROS_NAMESPACE=tb3_2 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_2" set_lidar_frame_id:="tb3_2/base_scan"
```
```
ROS_NAMESPACE=tb3_3 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_3" set_lidar_frame_id:="tb3_3/base_scan"
```

## For PC
```
roscore
```
```
git clone https://github.com/Lee-JaeWon/Multi-Turtlebot3-Cartographer.git
```
```
cd catkin_ws/
```
```
catkin_make
```
```
source catkin_ws/devel/setup.bash
```
```
roslaunch multi_tb3_cartographer tb3_cartographer.launch
```
## Edit
To change the number of robots, it is necessary to modify the launch file and add the lua file. The settings related to the TF Tree are sensitive, so care must be taken when modifying them.