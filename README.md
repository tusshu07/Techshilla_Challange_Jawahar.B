# Techshilla_Swarm_Challange
Drone   Swarming Challenge

We are using ROS, Gazebo, and ArduPilot to swarm 12 drones and draw a given shape. First, we draw a pattern or shape on a PC or tablet, and then extract 12 points that correspond to the 12 drones' desired positions. We use ROS to manage the drone swarm, Gazebo to simulate the drones and environment, and ArduPilot to control the drones' flight. The goal of this project is to demonstrate the capabilities of these technologies in coordinating a drone swarm to perform a specific task. Through this project, we aim to showcase the potential of swarm robotics and the advantages it offers over traditional single-robot systems.

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

