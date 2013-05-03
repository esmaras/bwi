FRI-BWI Code 2013
GitHub link: https://github.com/esmaras/bwi.git
Eric Maras // Moises Holguin // Chester Omenukor // James Sweetman
-----------------

Power on the robot and the base. Make sure the robot has a hokuyo laser.

Run
$ roscore

Make the ROS package

$ rosmake wifi_lookup

Run Robert's node and our node on the Robot. These should be run on the robot so that the WiFi is sensed from the actual robot. 

$ rosrun wifi_lookup wifi.py  
$ rosrun wifi_lookup wifi_test 

These should be run on the robot as well to ensure the AMCL pose is working. They must be run on the robot because the hokuyo is attached there

$ rosrun map_server map_server ~/ros/rosbuild_ws/segbot_apps/segbot_navigation/maps/3ne-real.yaml
$ roslaunch segbot_bringup segway_base.launch 
$ roslaunch segbot_navigation amcl.launch --screen

This can be run on either the desktop or the robot

$ roslaunch segbot_navigation rviz.launch 

This can also be run on the desktop or the robot, whichever is preferred.

$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py

Executing this line might help if there is a Seg fault error

$ rm CMakeCache.txt


