

````markdown
# Panda Color Sorting System (ROS 2)

A ROS 2-based intelligent color sorting system powered by the **Franka Emika Panda** robotic arm. This project integrates **OpenCV** computer vision, **MoveIt 2** motion planning, and **Gazebo** simulation to create an autonomous pick-and-place system that detects and sorts colored objects with precision.

---

## Features

- 🎨 **Color Detection**: Real-time OpenCV-based vision system for Red, Green, and Blue objects  
- 🦾 **Motion Planning**: Advanced trajectory planning using MoveIt 2  
- 🎯 **Autonomous Operation**: Fully automated pick-and-place with gripper control  
- 🔄 **Dynamic Target Selection**: Switch between colors without restarting the system  
- 📊 **Visual Feedback**: Integrated RViz visualization for motion planning and execution  

---

## Folder Structure

```text
panda_ws/
├── panda_bringup        # Launch files and robot initialization
├── panda_controller     # Robot control nodes
├── panda_description    # URDF, meshes, and robot description files
├── panda_moveit         # MoveIt 2 configuration and motion planning
├── panda_vision         # Color detection and image processing nodes
├── pymoveit2            # Python-based MoveIt 2 interface examples
└── .gitignore           # Git ignore file
````

---

## Quick Start

**Step 1: Build the ROS 2 workspace**

```bash
cd ~/panda_ws
colcon build
```

**Step 2: Source the workspace**

```bash
source ~/panda_ws/install/setup.bash
```

**Step 3: Launch the pick-and-place simulation**

```bash
ros2 launch panda_bringup pick_and_place.launch.py
```

**Step 4: Run Python MoveIt 2 pick-and-place node with target color**

```bash
source ~/panda_ws/install/setup.bash
ros2 run pymoveit2 pick_and_place.py --ros-args -p target_color:=R
```

> Replace `R` with `G` or `B` to sort different colors.

---

## Screenshots

**Simulation in Gazebo:**

![Gazebo Simulation](images/gazebo_simulation.png)

**Pick-and-Place Operation in RViz:**

![RViz Visualization](images/rviz_pick_and_place.png)

## Acknowledgements

* [Franka Emika Panda](https://www.franka.de/)
* [ROS 2](https://docs.ros.org/en/rolling/) and [MoveIt 2](https://moveit.ros.org/)
* OpenCV for computer vision

