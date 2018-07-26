<p align="center">
  <img width="400" height="142,687 " src="https://user-images.githubusercontent.com/40801473/43266230-c2dd979c-90e2-11e8-95a0-0722aedd1667.png">
</p>

# Robotics-ColumbiaX-Project3
7 DOF KUKA Robot control through Forward Kinematics | ROS, RVIZ based.\

# How to run

First you have to place kuka_lwr_arm.urdf urdf file to your home/my_name directory or the ../ directory where you clone this repo.\

Steps to run the demo:\
	- roscore\
	- rosparam set robot_description --textfile kuka_lwr_arm.urdf\
	- rosrun robot_sim robot_sim_bringup\
	- rosrun robot_mover mover\
	- rosrun forward_kinematics solution.py\
	- rosrun rviz rviz\
