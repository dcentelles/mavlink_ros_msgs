cmake_minimum_required(VERSION 2.8.3)
project(mavlink_ros_msgs)

find_package(catkin REQUIRED
        roscpp
        rospy
	std_msgs
	message_generation
)

## Declare ROS messages and services
add_message_files(
  DIRECTORY
        msg
  FILES
        pid_debug.msg
 )

 generate_messages(
   DEPENDENCIES
        roscpp
        std_msgs
 )


catkin_package(
   CATKIN_DEPENDS
       roscpp
       std_msgs
       message_runtime
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)
