chris_turtlebot_navigation
======

This package contains launch and parameter files for setting up navigation experiments with the chris_ros_turtlebot setup using either ROS Navigation (move_base)
or the newer ROS FlexBE-based flexible_navigation package (https://github.com/CNURobotics/flexible_navigation)

This version converts the ```move_base``` Twist.msg velocity command into a smoothed TwistStamped.msg.


### Bring up system

To run the typical configuration, first startup the CHRISLab Turtlebot system using launch files from ```chris_ros_turtlebot``` packages.
Both simulation and hardware instances are supported.

### Start localization

Then run the appropriate localization demo with the appropriate map.  The map is handled within a single robot namespace to allow different robots to used different maps or mapping techniques.  

The ```amcl_demo.launch``` performs Adaptive Monte Carlo Localization relative to the given map.  There are several variations (e.g. ```amcl_creech_world.launch```) that invoke ```amcl_demo.launch``` with a particular map file.

The ```fake_localization_demo.launch```, and its associated variations with specific maps (e.g. ```fake_creech_sim.launch```), use the ``ground_truth`` odometry message published by the CHRISLab Turtlebot Gazebo simulation.  The demo creates a map server that provides the associated map for planning.  

The ```gmapping_demo.launch``` builds a map from scratch within the robot namespace.

### Start planning and control

The ```move_base_demo.launch``` starts the standard ```move_base``` navigation planning framework.  The namespace can be set as needed.

### Visualization

The ```chris_turtlebot_rviz.launch``` file opens an RViz setup that includes laser scans and map displays.
