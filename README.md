# Pincher-arm

<img 
src="https://github.com/Taireyune/pincher-arm/blob/main/images/move_object.gif" 
width="600" height="446" alt="move object">

## Overview
The physical robotic arm used for sim2real learning in the over-arching project is the Pincher arm px150 from Trossen Robotics. This project is an edited version of the Interbotix SDK from Trossen Robotics to fit the designed pipeline. Please go to [Interbotix](https://github.com/Interbotix/interbotix_ros_core/tree/main/interbotix_ros_xseries/interbotix_xs_sdk) for the source.

Robotic arms used in the industry often operate based on position, using PID controllers to achieve precise joint angles. Users write the coordinates of where they want the arm to go to complete the intended task. This type of control is useful for highly repetitive tasks in very controlled environments and almost no variability, but tasks that require delicate handling of fragile and soft objects with high variability becomes very difficult. To allow a robotic arm to handle these tasks, effort-based control (specifying the amount of torque each joint applies) may be required. 

<img 
src="https://github.com/Taireyune/pincher-arm/blob/main/images/real_robotic_arm_circled.png" 
width="500" height="500" alt="robotic arm relationship">

## Cortex Commands
Pincher arm can recieve commands from either a [PS4 controller or an ML agent]() through the JointCommands.msg to control its joints. The message format mirrors that of the [cortex-message-handling](https://github.com/Taireyune/cortex-message-handling) used in Unity Simulations. Although it feels difficult to control the arm with effort-based control using the PS4 controller, end-to-end training of an agent with this accompanied by visual, kinematics, and joint-states inputs may achieve the said capabilities.