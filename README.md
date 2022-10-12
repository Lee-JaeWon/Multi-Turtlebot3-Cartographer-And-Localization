# Multi-Turtlebot3-Cartographer-And-Localization

## Abstract
It is a repository that uses Cartographer using several real turtlebot3 burgers, not simulation.<br>
It is introduced in ROBOTIS to perform cartographer with one Turtlebot3, but it is not introduced to perform it by specifying namespaces on multiple units.<br>
Cartographer and turtlebot3 packages must be installed, and need to understand TF Tree configuration and urdf, lua files.<br>

## Environment
- catkin
- ubuntu 20.04 for PC and turtlebot3(Rasbraspberry pi4)
- ROS1 Noetic

## Cartographer
### For Turtlebot3
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

### For PC
```
roscore
```
```
git clone https://github.com/Lee-JaeWon/Multi-Turtlebot3-Cartographer-And-Localization.git
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
## Localization : AMCL
It performs localization on a given map and reaches the target point using ROS navigation stack when setting the target point respectively(in rviz).<br>
This repository visualizes the current location and sampled path.<br><br>
### For Turtlebot3
All robots do this,
```
ssh ubuntu@{Your turtlebot's IP}
```
```
ROS_NAMESPACE=tb3_0 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_0" set_lidar_frame_id:="tb3_0/base_scan"
```
```
ROS_NAMESPACE=tb3_1 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_1" set_lidar_frame_id:="tb3_1/base_scan"
```
```
ROS_NAMESPACE=tb3_2 roslaunch turtlebot3_bringup turtlebot3_robot.launch multi_robot_name:="tb3_2" set_lidar_frame_id:="tb3_2/base_scan"
```

### For PC
```
roscore
```
```
git clone https://github.com/Lee-JaeWon/Multi-Turtlebot3-Cartographer-And-Localization.git
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
roslaunch multi_tb3_cartographer tb3_localization.launch
```
<p align="center"><img src="/doc/1.png" width = "600" ></p>
<p align="center"><img src="/doc/2.png" width = "600" ></p>

## Edit
To change the number of robots, it is necessary to modify the launch file and add the lua file. The settings related to the TF Tree are sensitive, so care must be taken when modifying them.

## Reference
This repository used Turtlebot3 (ROBOTIS) and Cartographer (Google) packages, and the copyright is held by the company.<br>
[ROBOTIS : emanual](https://emanual.robotis.com/docs/en/platform/turtlebot3/slam/#run-slam-node)<br>
[Cartographer](https://google-cartographer-ros.readthedocs.io/en/latest/)