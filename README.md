## ROS2 learning journey

## My note for setup
# AGV_ROS (ROS 2 + URDF/Xacro + RViz2)

## Requirements
- Ubuntu 22.04 + ROS 2 Humble (WSL2 OK)
- `colcon` build tools installed
- ros-humble-gazebo-ros-pkgs

---
#THESE STEPS BELOW WERE WRITTEN IN AN AUTOMATED SCRIPT (launch_sim.launch.py) 
- ros2 launch agv_ros launch_sim.launch.py
## Build
```bash
cd ~/dev_wst
colcon build --symlink-install
- ros-humble-gazebo-ros-pkgs
- ros-foxy-gazebo-ros-pkgs
```
## Source the workspace
source ~/dev_ws/install/setup.bash
## Run RViz2 with robot state publisher
```bash
ros2 launch agv_ros rsp.launch.py
ros2 run joint_state_publisher joint_state_publisher
rviz2 -d ~/dev_ws/src/agv_ros/config/view_bot.rviz
## Gazebo Simulation
```bash
ros2 launch agv_ros rsp.launch.py use_sim_time:=true
ros2 launch gazebo_ros gazebo.launch.py
ros2 run gazebo_ros spawn_entity.py -topic robot_description -entity agv_bot 

ros2 run teleop_twist_keyboard teleop_twist_keyboard
``` 
