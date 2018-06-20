cmake_minimum_required(VERSION 2.8.3)
project(forward_kinematics)


find_package(catkin REQUIRED COMPONENTS
  rospy
  sensor_msgs
  tf
  urdfdom_py
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES forward_kinematics
  CATKIN_DEPENDS 
    rospy 
    sensor_msgs 
    tf
    urdfdom_py
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

