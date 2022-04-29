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

install(DIRECTORY launch/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
  PATTERN ".svn" EXCLUDE)

install(DIRECTORY meshes/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/meshes
  PATTERN ".svn" EXCLUDE)

install(DIRECTORY script/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/script
  PATTERN ".svn" EXCLUDE)

install(DIRECTORY urdf/
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/urdf
  PATTERN ".svn" EXCLUDE)

