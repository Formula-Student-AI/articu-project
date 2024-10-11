# README

This repository contains the .devcontainer files for VSCode to build a Ubuntu 20.04 docker container with ROS 2 Foxy installed as part of the articu-project team project.

## Versions
- OS: Ubuntu 20.04 (Focal)
- ROS: ROS 2 Foxy

## Setup
```
git clone https://github.com/Formula-Student-AI/articu-project
```

1. Follow the [setup guide](https://bristol-fsai.notion.site/Guides-11c29866e62680b3a193ee29496b3f37) if you need to set up Docker.

2. Build the packages
   ```
   colcon build --symlink-install
   ```

3. Source the overlay
   ```
   source install/setup.bash
   ```

4. Launch the world
   ```
   ros2 launch articubot_one launch_sim.launch.py world:=./src/articubot_one/worlds/obstacles.world
   ```

5. Put tennis ball in gazebo models paths
   ```
   sudo cp -r tennis_ball/ /usr/share/gazebo-11/models/
   ```

6. Open a new terminal, source the overlay again, and launch the ball tracker
   ```
   source install/setup.bash
   ros2 launch ball_tracker ball_tracker.launch.py params_file:=./src/articubot_one/config/ball_tracker_params_sim.yaml 
   ```

7. Now you can spawn in a tennis ball into the Gazebo sim and the robot will follow it! (To spawn in the tennis ball, you will need to add /articu-project to the path by going to Insert -> Add Path -> Computer -> '/' -> Choose 'articu-project'. Then you can insert the tennis ball as a model and move it around.).


## Credit
- [ijnek](https://github.com/ijnek/ros-devcontainer-template)
- [Josh Ewans](https://github.com/joshnewans)
