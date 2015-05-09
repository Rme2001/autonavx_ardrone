cmake_minimum_required(VERSION 2.8.3)
project(ardrone_joystick)

find_package(catkin REQUIRED COMPONENTS roscpp sensor_msgs std_srvs geometry_msgs)
catkin_package(
  DEPENDS libsdl-dev
  CATKIN_DEPENDS roscpp sensor_msgs std_srvs geometry_msgs
)

add_executable(ardrone_teleop src/main.cpp)
target_link_libraries(ardrone_teleop ${catkin_LIBRARIES})

#install Rules
install(TARGETS ardrone_teleop RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
