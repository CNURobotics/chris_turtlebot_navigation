cmake_minimum_required(VERSION 2.8.3)
project(chris_turtlebot_navigation)

# Load catkin and all dependencies required for this package
find_package(catkin REQUIRED COMPONENTS tf roscpp sensor_msgs)

# What other packages will need to use this package
catkin_package(
    CATKIN_DEPENDS tf roscpp sensor_msgs nav_msgs chris_world_models
)

catkin_add_env_hooks(25.turtlebot-basic-navigation SHELLS sh DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/env-hooks)


###########
## Build ##
###########
include_directories(${catkin_INCLUDE_DIRS})

# Add_executables

#############
## Install ##
#############

# Mark anything (useful) else for installation
install(DIRECTORY launch
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY param
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY mprim
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)


