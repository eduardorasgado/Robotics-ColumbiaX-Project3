cmake_minimum_required(VERSION 2.8.3)
project(robot_sim)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  sensor_msgs
  #std_msgs
  urdf
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
# generate_messages(
#   DEPENDENCIES
#   std_msgs
#   sensor_msgs
# )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES robot_sim
#  CATKIN_DEPENDS roscpp rospy sensor_msgs urdf
#  DEPENDS system_lib
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)


add_executable(joint_state_publisher_node src/joint_state_publisher.cpp)
add_executable(position_controller_node src/position_controller.cpp)
add_executable(robot_node src/robot.cpp)
add_executable(robot_sim_bringup_node src/robot_sim_bringup.cpp)
add_executable(velocity_controller_node src/velocity_controller.cpp)

add_dependencies(joint_state_publisher_node joint_state_publisher_node_generate_messages_cpp)
add_dependencies(position_controller_node position_controller_node_generate_messages_cpp)
add_dependencies(robot_node robot_node_generate_messages_cpp)
add_dependencies(robot_sim_bringup_node robot_sim_bringup_node_generate_messages_cpp)
add_dependencies(velocity_controller_node velocity_controller_node_generate_messages_cpp)

target_link_libraries(joint_state_publisher_node ${catkin_LIBRARIES})
target_link_libraries(position_controller_node ${catkin_LIBRARIES})
target_link_libraries(robot_node ${catkin_LIBRARIES})
target_link_libraries(velocity_controller_node ${catkin_LIBRARIES})
target_link_libraries(robot_sim_bringup_node ${catkin_LIBRARIES})