# Techshilla_Swarm_Challange
Drone   Swarming Challenge
REQUIREMENTS AND INSTALLATIONS

 *ROS 
:- 
ROS (Robot Operating System) is a flexible framework for writing robot software, providing libraries and tools to help developers create complex robot applications.
Instructions for installing ROS http://wiki.ros.org/noetic/Installation

*GAZEBO 
:- 
GAZEBO is a 3D robotics simulation environment used for testing and developing robots and autonomous systems.
Instructions for installing GAZEBO http://classic.gazebosim.org/tutorials?tut=install_from_source&cat=install

*ARDUPILOT 
:-
ArduPilot is an open-source autopilot software suite that controls fixed-wing aircraft, multirotor helicopters, and other unmanned vehicles.
Instructions for installing ARDUPILOT https://ardupilot.org/planner/docs/mission-planner-installation.html

Instruction for Swarm in Ardupilot

Go to - ardupilot/Tools/autotest/pysim/vehicleinfo.py
```
            "gazebo-drone1": {
                "waf_target": "bin/arducopter",
                "default_params_filename": ["default_params/copter.parm",
                                            "default_params/gazebo-drone1.parm"],
            },
            "gazebo-drone2": {
                "waf_target": "bin/arducopter",
                "default_params_filename": ["default_params/copter.parm",
                                            "default_params/gazebo-drone2.parm"],
            }
```

Do this similar for 12 drones.
Create the following files- 

```
default_params/gazebo-drone1.parm
default_params/gazebo-drone2.parm
```

each with their corresponding SYSID_THISMAV parameter value ie

default_params/gazebo-drone1.parm should contain SYSID_THISMAV 1
default_params/gazebo-drone2.parm should contain SYSID_THISMAV 2

Example of the param file that needs to be created for all 12 drones -

```
# Iris is X frame
FRAME_CLASS 1
FRAME_TYPE  1
# IRLOCK FEATURE
RC8_OPTION 39
PLND_ENABLED    1
PLND_TYPE       3
# SONAR FOR IRLOCK
SIM_SONAR_SCALE 10
RNGFND1_TYPE 1
RNGFND1_SCALING 10
RNGFND1_PIN 0
RNGFND1_MAX_CM 5000
SYSID_THISMAV 1
```
After all these, clone the repository and perform catkin make!

Go to <package-name>/scripts and open the terminal and run -
```
./swarm.sh
```
Open another terminal and run the following scripts.

```
roslaunch <package-name> multi_drone.launch
roslaunch <package-name> multi-apm.launch
```

FINALLY when the drones are ready to fly, run the final script and enjoy!

```
roslaunch <package-name> multi-swarm.launch
```

