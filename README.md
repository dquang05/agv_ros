## Robot Package Template

This is a GitHub template. You can make your own copy by clicking the green "Use this template" button.

It is recommended that you keep the repo/package name the same, but if you do change it, ensure you do a "Find all" using your IDE (or the built-in GitHub IDE by hitting the `.` key) and rename all instances of `agv_ros` to whatever your project's name is.

Note that each directory currently has at least one file in it to ensure that git tracks the files (and, consequently, that a fresh clone has direcctories present for CMake to find). These example files can be removed if required (and the directories can be removed if `CMakeLists.txt` is adjusted accordingly).

## My note for setup
# AGV_ROS (ROS 2 + URDF/Xacro + RViz2)

## Requirements
- Ubuntu 22.04 + ROS 2 Humble (WSL2 OK)
- `colcon` build tools installed

---

## Build
```bash
cd ~/dev_ws
colcon build --symlink-install
```
## Source the workspace
source ~/dev_ws/install/setup.bash
## Run RViz2 with robot state publisher
```bash
ros2 launch agv_ros rsp.launch.py
ros2 run joint_state_publisher joint_state_publisher
rviz2 -d ~/dev_ws/src/agv_ros/config/view_bot.rviz
```