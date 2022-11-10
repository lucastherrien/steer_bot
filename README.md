# Steer Bot

A forked version of srmainwarings steer_bot simulating a Rosbot Mini outfitted with a TiM881P Lidar and a Kinect Camera.
This simulation environment is intended to be used for Phase 2 of UNC Charlotte's robotic delivery system.

## Installation

```bash
# Create a workspace folder
mkdir -p <catkin_ws>/src

# Clone the repo
cd <catkin_ws>/src
git clone https://github.com/lucastherrien/steer_bot

# Checkout a version of `steer_drive_ros` patched for ROS Noetic
https://github.com/lucastherrien/steer_drive_ros
cd steer_drive_ros
git checkout Noetic-devel

# Check dependencies
rosdep check --from-paths src --ignore-src --rosdistro noetic

# Install dependencies
rosdep install --from-paths src --ignore-src --rosdistro noetic -y

# Build
cd <catkin_ws>/src
catkin build
```

## Run

Start the Gazebo simulation:

```bash
roslaunch steer_bot_gazebo steer_bot_sim.launch
```

Start `rviz`:

```bash
roslaunch steer_bot_viz view_steer_bot_robot.launch
```

If all is working well you should see the robot in Gazebo and be able to
command it using `rqt_robot_steering`:

![steer_gazebo rviz](https://user-images.githubusercontent.com/14840534/199090321-dc328d9e-1c2b-493f-85f6-a15b31827664.png)

The robot model and odometry can be monitored in `rviz`: 

![steer_bot rviz](https://raw.githubusercontent.com/wiki/srmainwaring/steer_bot/images/steer_bot_rviz.png)


## License

This software is licensed under the BSD-3-Clause license found in the
LICENSE file in the root directory of this source tree.
