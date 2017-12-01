# gummi_ee_handshake

Package for definitions of the End Effector Handshake. 

## Setting up a new base

Fork or clone this repository. 

Rename gummi_ee_handshake to gummi_ee_YOUR_OWN_EE

`$ mv gummi_ee_handshake gummi_ee_YOUR_OWN_EE`

Edit the file gummi_ee_YOUR_OWN_EE/set_env_gummi.sh

`$ gedit gummi_ee_YOUR_OWN_EE/set_env_gummi.sh`

And change the line containing "export ROS_GUMMI_EE=handshake" to "export ROS_GUMMI_EE=YOUR_OWN_EE"

You can now proceed to change gummi_ee_YOUR_OWN_EE/launch/controllers_base.launch to contain the motor drivers that your end effector has and where they are connected in the bus and the updating the yaml definitions of joints in gummi_ee_YOUR_OWN_EE/dynamixel
