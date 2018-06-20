cmake_minimum_required(VERSION 2.8.3)
project(robot_mover)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  forward_kinematics
  lwr_defs
  robot_sim
  std_msgs
  sensor_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES project2
#  CATKIN_DEPENDS forward_kinematics lwr_defs robot_sim sensor_msgs
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(mover src/mover.cpp)

target_link_libraries(mover
  ${catkin_LIBRARIES}
)

