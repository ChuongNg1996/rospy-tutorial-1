cmake_minimum_required(VERSION 3.0.2)
project(msg_tutorials)

find_package(catkin REQUIRED
   roscpp
   rospy
   std_msgs
   message_generation
   )
   
 add_message_files(
  FILES
  Num.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
	CATKIN_DEPENDS message_runtime
)


#include_directories(
#${catkin_INCLUDE_DIRS}
#)
