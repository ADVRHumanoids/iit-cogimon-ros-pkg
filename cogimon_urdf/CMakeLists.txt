cmake_minimum_required(VERSION 2.8.3)
project(cogimon_urdf)

find_package(catkin REQUIRED COMPONENTS
  joint_state_publisher
  robot_state_publisher
  rospy
)

catkin_package()

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_custom_target(  compile_urdf_sdf ALL
                    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/script/create_urdf_srdf_sdf.sh cogimon)

