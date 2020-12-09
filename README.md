# roboclaw_ros
[![Build Status](https://travis-ci.org/sonyccd/roboclaw_ros.svg?branch=master)](https://travis-ci.org/sonyccd/roboclaw_ros)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/6f65acd1242e4a0582ecb04c7cc70f68)](https://www.codacy.com/app/snakes-in-the-box/roboclaw_ros?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=sonyccd/roboclaw_ros&amp;utm_campaign=Badge_Grade)

This is the ROS driver for the Roboclaw motor controllers made by [Ion Motion Control](http://www.ionmc.com/) and a fork of the original driver from [sonyccd/roboclaw_ros](https://github.com/sonyccd/roboclaw_ros).

It incoperates different improvements, enhancements and features from other forks:
* thread safe due to the use of mutexes [MSDRobotics/roboclaw_ros](https://github.com/MSDRobotics/roboclaw_ros)
* diagnostics for currents
* main battery voltage publisher (BatteryState)
* option to run without encoders


## Usage
Just clone the repo into your catkin workspace. It contains the ROS package and the motor controller driver.  Remmeber to make sure ROS has permisions to use the dev port you give it.
```bash
cd <workspace>/src
git clone https://github.com/uweswrtz/roboclaw_ros.git
cd <workspace>
catkin_make
source devel/setup.bash
roslaunch roboclaw_node roboclaw.launch
```

## Parameters
The launch file can be configure at the command line with arguments, by changing the value in the launch file or through the rosparam server.

|Parameter|Default|Definition|
|-----|----------|-------|
|dev|/dev/ttyACM0|Dev that is the Roboclaw|
|baud|115200|Baud rate the Roboclaw is configured for|
|address|128|The address the Roboclaw is set to, 128 is 0x80|
|max_speed|2.0|Max speed allowed for motors in meters per second|
|ticks_per_meter|4342.2|The number of encoder ticks per meter of movement|
|base_width|0.315|Width from one wheel edge to another in meters|
|encoders|True|When false uses duty cycle to drive motors. ticks_per_meter is duty factor

## Topics
### Subscribed
/cmd_vel [(geometry_msgs/Twist)](http://docs.ros.org/api/geometry_msgs/html/msg/Twist.html)  
Velocity commands for the mobile base.
### Published
/odom [(nav_msgs/Odometry)](http://docs.ros.org/api/nav_msgs/html/msg/Odometry.html)  
Odometry output from the mobile base.

~mainbattery [(sensor_msgs/BatteryState)](http://docs.ros.org/api/sensor_msgs/html/msg/BatteryState.html)  
Main battery voltage and some state

#IF SOMETHING IS BROEKN:
Please file an issue, it makes it far easier to keep track of what needs to be fixed. It also allows others that might have solved the problem to contribute.  If you are confused feel free to email me, I might have overlooked something in my readme.
