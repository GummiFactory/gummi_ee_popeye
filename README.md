# gummi_ee_handshake

![](https://github.com/frederico-klein/gummi_ee_handshake/blob/master/images/handshake_dovetail.png "New handshake end effector with dovetail end.")


Package for definitions of the handshake Picker End Effector.

## Setting up a new end effector

Fork or clone this repository.

Rename gummi_ee_handshake to gummi_ee_YOUR_OWN_EE

`$ mv gummi_ee_handshake gummi_ee_YOUR_OWN_EE`

Edit the file gummi_ee_YOUR_OWN_EE/scripts/set_env_gummi.sh

`$ gedit gummi_ee_YOUR_OWN_EE/set_env_gummi.sh`

And change the line containing "export ROS_GUMMI_EE=handshake" to "export ROS_GUMMI_EE=YOUR_OWN_EE"

You can now proceed to change gummi_ee_YOUR_OWN_EE/launch/controllers_base.launch to contain the motor drivers that your end effector has and where they are connected in the bus and the updating the yaml definitions of joints in gummi_ee_YOUR_OWN_EE/dynamixel

## Testing the end effector without a base

It is possible to run just the end effector without a base, but you need to load a custom mananger for your end effector.

First fork this repository and make the suitable changes to describe your end-effector.

Open the /launch/manager_only_ee.launch file and remove the interfaces that are not being used and change if necessary the id definitions for your current setup.

Run catkin_make after setting up your other packages.

Do a source from devel/setup.bash

Roslaunch the eddited manager_only_ee.launch from your gummi_ee_template.

Now roslaunch the controllers_ee.launch

Run the rest of your code as usual.

## Setting up new urdf definitions for end effector

The xacro file in the xacro directory has all the urdf definitions (joints and links) for the end-effector from elbow to gripper, and should be updated to match the current end-effector

## What's new

 - updated to real mesh files instead of the red box approximation done by hand from the previous model after adding dovetail design (fastswitch joint in the urdf)
 - removed some elements that I thought might lead to collisions, so adjacent joints are kinda floating next to each other
 - added a transformation frame for the camera, in case one may want to work with tf2 to have the visual-servoing working with move-it
 - aligned the axis from the tool element to the camera, so that now moving it in the x axis means it will get closer to the handshake, z is up, y is a sideways movement, all in relationship to the camera image. The previous axis seemed to be in a rather strange orientation, parallel to a face of the gripper that doesn't even exist in this version anymore


##

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>

<br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
