cmake_minimum_required(VERSION 2.8.3)
project(cogimon_srdf)

find_package(catkin REQUIRED)

catkin_package()

# mark srdf for installation
install(DIRECTORY srdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
