# README

This repository contains the .devcontainer files for VSCode to build a Ubuntu 20.04 docker container with ROS 2 Foxy installed as part of the articu-project team project.

## Versions
- OS: Ubuntu 20.04 (Focal)
- ROS: ROS 2 Foxy

## Instructions

0. See https://github.com/Formula-Student-AI/ros-docker for instructions for how to setup .devcontainers in VSCode.

1. Navigate to your home folder and clone this repo
   ```
   git clone https://github.com/Formula-Student-AI/articu-project
   ```

2. Reopen in Container
   - Open the cloned repository in VSCode.
   - Click on the blue box in the bottom left-hand corner of the VSCode window.
   - Select "Reopen in Container".

3. Clone the articubot_one ROS package
   ```
   git clone https://github.com/joshnewans/articubot_one
   ```

4. Clone the ball_tracker ROS package
   ```
   git clone https://github.com/joshnewans/ball_tracker
   ```

5. Build the packages
   ```
   colcon build --symlink-install
   ```

6. Launch the world
   ```
   ros2 launch articubot_one launch_sim.launch.py world:=./src/articubot_one/worlds/obstacles.world
   ```

7. Launch the ball tracker
   ```
   ros2 launch ball_tracker ball_tracker.launch.py params_file:=./src/articubot_one/config/ball_tracker_params_sim.yaml 
   ```

## Credit
- ijnek: https://github.com/ijnek/ros-devcontainer-template
# articu-project
