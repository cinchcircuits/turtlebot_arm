TurtleBot Arm
=============

This is the catkin-ized and moveit-ed version of turtlebot arm. It's currently not on a TurtleBot:

## Attaching the Arm to a Robot
Open your xacro-macro-magic URDF, and add something like:

   <xacro:include filename="$(find turtlebot_arm_description)/urdf/arm.xacro" />
   <turtlebot_arm parent="base_link" color="black" gripper_color="green" joints_vlimit="1.571" pan_llimit="-2.617" pan_ulimit="2.617">
      <origin xyz="0 0 0" rpy="0 0 0"/>
    </turtlebot_arm>

This will attach a turtlebot arm to your robot. Replace base_link with whatever link you want to attach to,
and change the origin as needed.

## Running MoveIt
I need to generate a .rosinstall file for this, currently you need to checkout moveit_core, moveit_ros,
moveit_plugins and arbotix_ros from source. That should be fixed with the next release.

The turtlebot_arm_moveit_config/demo.launch is a bit wonky, but the move_group action underlying it works
fine. Demo file coming shortly.

