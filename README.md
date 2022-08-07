# arm_pkg

# install Arduino IDE
$ sudo .//Downloads/arduino-1.8.19-linux64/arduino-1.8.19/install.sh



# Install the arduino package and ros library 
$ include <ros.h>
$ include <std_msgs/String.h>
$ sudo apt-get install ros-noetic-rosserial-arduino
$ sudo apt-get install ros-noetic-rosserial


# Install ros_lib into the Arduino Environment
cd ~/Arduino/libraries
rm -rf ros_lib
 rosrun rosserial_arduino make_libraries.py .
 cd ros_lib
 rosrun rosserial_arduino make_libraries.py .
 
 
# Controlling the robot arm by joint_state_publishe
$ roslaunch robot_arm_pkg check_motors.launch
$ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200


# Simulation
$ roslaunch robot_arm_pkg check_motors.launch
$ roslaunch robot_arm_pkg check_motors_gazebo.launch
$ rosrun robot_arm_pkg joint_states_to_gazebo.py


# Controlling the robot arm by Moveit and kinematics
$ roslaunch moveit_pkg demo.launch
$ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200

$ roslaunch moveit_pkg demo_gazebo.launch

