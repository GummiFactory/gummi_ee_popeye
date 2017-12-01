# gummi_ee_handshake

Package for definitions of the End Effector Handshake. 

## Setting up a new end effector

Fork or clone this repository. 

Rename gummi_ee_handshake to gummi_ee_YOUR_OWN_EE

`$ mv gummi_ee_handshake gummi_ee_YOUR_OWN_EE`

Edit the file gummi_ee_YOUR_OWN_EE/set_env_gummi.sh

`$ gedit gummi_ee_YOUR_OWN_EE/set_env_gummi.sh`

And change the line containing "export ROS_GUMMI_EE=handshake" to "export ROS_GUMMI_EE=YOUR_OWN_EE"

You can now proceed to change gummi_ee_YOUR_OWN_EE/launch/controllers_base.launch to contain the motor drivers that your end effector has and where they are connected in the bus and the updating the yaml definitions of joints in gummi_ee_YOUR_OWN_EE/dynamixel

## Testing the end effector without a base 

It is possible to run just the end effector without a base, but you need to load the mananger for your end effector. 

First fork this repository and make the suitable changes to describe your end-effector.

Open the /launch/manager_only_ee.launch file and remove the interfaces that are not being used and change if necessary the id definitions for your current setup. 

Run catkin_make after setting up your other packages. 

Do a source from devel/setup.bash

Roslaunch the eddited manager_only_ee.launch from your gummi_ee_template.

Now roslaunch the controllers_ee.launch

Run the rest of your code as usual.
