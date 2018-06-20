cmake_minimum_required(VERSION 2.8.3)
project(robot_mover)

find_package(catkin REQUIRED COMPONENTS
  #forward_kinematics
  #lwr_defs
  #robot_sim
  roscpp
  sensor_msgs
  std_msgs
)


## Generate messages in the 'msg' folder
# add_message_files(
#   FILES
#   Message1.msg
#   Message2.msg
# )

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

## Generate added messages and services with any dependencies listed here
 generate_messages(
   DEPENDENCIES
   sensor_msgs
   std_msgs
 )

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(mover_node src/mover.cpp)

add_dependencies(mover_node mover_node_generate_messages_cpp)

target_link_libraries(mover_node ${catkin_LIBRARIES})