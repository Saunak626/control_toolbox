control_toolbox
===============

This c++ repository is designed for use on robotics systems with the purpose of dynamic modelling, control, state estimation, model predictive control, etc.

# Repositories

## The Control Toolbox
The main repo is [The Control Toolbox](https://adrlab.bitbucket.io/ct/v2.3/ct_doc/doc/html/index.html), created by researchers from the Agile & Dexterous Robotics Lab (ADRL) at ETH Zurich, Switzerland. The [API](https://adrlab.bitbucket.io/ct/v2.3/ct_doc/doc/html/pages.html) can be found by clicking on any of the modules: CT Core, CT Optimal Control, CT Rigid Body Dynamics, and CT Models.

## Kindr - Kinematics and Dynamics for Robotics
The Control Toolbox uses this repo heavily, and so it is included. Kindr was originally developed by the ADRL, but is now maintained by [ANYbotics](https://www.anybotics.com/). You can find the github page for kindr [here](https://github.com/ANYbotics/kindr).

# Building

## Building with catkin
For consistency with our other repos, we will compile the control_toolbox with catkin. However, each of the above repositories does not contain standard catkin packages, thus, this repo will be compiled separately (using the command: catkin_make_isolated) and then chained with existing catkin workspaces.

If you are on the OSU Underwater Robotics Team, then clone this repo to your Ubuntu environment in the same manner as for our other repos:

```
mkdir -p ~/osu-uwrt/control_toolbox/src
cd ~/osu-uwrt/control_tolbox/src
catkin_init_workspace
cd ..
git clone https://github.com/osu-uwrt/control_toolbox.git src
catkin_make_isolated
```

## Editing the .bashrc
To make the main repo (riptide_software) work with the control_toolbox, you need to edit the .bashrc file on your computer:

Enter the ~/.bashrc file: 
```
nano ~/.bashrc
```

Scroll down to the bottom. Directly above the line:
```
source ~/osu-uwrt/riptide_software/devel/setup.bash
```
add the following line:
```
source ~/osu-uwrt/control_tooolbox/devel_isolated/setup.bash
```

To exit and save your changes, press CTRL-X, type "y", then press ENTER. These changes will now take effect in any new terminal that you open.