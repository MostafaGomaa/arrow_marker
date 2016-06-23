cmake_minimum_required(VERSION 2.8.3)
project(visualization_marker_tutorials)

find_package(catkin REQUIRED COMPONENTS roscpp visualization_msgs)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need

catkin_package(
  CATKIN_DEPENDS roscpp visualization_msgs
)

###########
## Build ##
###########

include_directories(include
  ${catkin_INCLUDE_DIRS}
)

add_executable(arrow src/arrow.cpp)
target_link_libraries(arrow
   ${catkin_LIBRARIES}
)


#############
## Install ##
#############

## Mark executables and/or libraries for installation
install(TARGETS 
  arrow
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
