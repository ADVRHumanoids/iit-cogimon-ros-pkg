cmake_minimum_required(VERSION 3.0)

set(ROBOT_NAME cogimon)
project(iit-${ROBOT_NAME}-ros-pkg VERSION 1.0.0)

include(GenerateXrdf.cmake)

## add sub-packages
add_subdirectory(cogimon_urdf)
add_subdirectory(cogimon_srdf)
add_subdirectory(cogimon_gazebo)

enable_testing()

include(GenerateDeb.cmake)
