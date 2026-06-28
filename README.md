# 🤖 AMR — URDF Workspace
> A basic ROS2 workspace for an Autonomous Mobile Robot (AMR) built using URDF, simulated in RViz and Gazebo.

---

## 📸 Demo

![AMR in Gazebo](amr_description/images/task2(1).gif)
---

## 🤖 The Robot

An Autonomous Mobile Robot (AMR) with a simple but complete URDF model:

- 1 rectangular base link — `0.5 x 0.3 x 0.1 m`
- 4 cylindrical wheels — `radius=0.1m, length=0.02m`
- All 4 wheels connected via `continuous` joints
- Blue body, black wheels
- Differential drive — back 2 wheels driven, front 2 passive

---

## 🎯 Objective

The goal of this project is to:

- Build a modular AMR robot model using URDF
- Understand robot structure definition in ROS2
- Spawn and simulate the robot in Gazebo
- Control the robot 

---

## 🧩 Features

- ROS2 package structure (`amr_description`)
- URDF-based robot model with collision, inertia, and Gazebo colors
- Differential drive plugin for movement control
- Keyboard teleoperation via `teleop_twist_keyboard`
- Modular design ready for future expansion

---

## 📁 Project Structure

```
amr_ws/
├── src/
│   └── amr_description/
│       ├── urdf/
│       │   └── amr.urdf
│       ├── CMakeLists.txt
│       └── package.xml
└── README.md
```

---

## ⚙️ Requirements

- ROS2 Humble
- Gazebo 11
- `ros-humble-gazebo-ros-pkgs`
- `ros-humble-teleop-twist-keyboard`
- `ros-humble-urdfdom`

Install all dependencies:

```bash
sudo apt install ros-humble-gazebo-ros-pkgs
sudo apt install ros-humble-teleop-twist-keyboard
sudo apt install ros-humble-urdfdom
```

---

## 🚀 How to Run

**Step 1 — Validate the URDF:**
```bash
check_urdf amr.urdf
```

**Step 2 — Launch Gazebo:**
```bash
ros2 launch gazebo_ros gazebo.launch.py
```

**Step 3 — Spawn the robot:**
```bash
ros2 run gazebo_ros spawn_entity.py \
  -file ~/intro-to-urdf/amr_ws/src/amr_description/urdf/amr.urdf \
  -entity amr
```

**Step 4 — Control with keyboard:**
```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

### Keyboard Controls

| Key | Action |
|---|---|
| `i` | Forward |
| `,` | Backward |
| `j` | Turn left |
| `l` | Turn right |
| `k` | Full stop |
| `q` / `z` | Increase / decrease speed |

---

## 📚 What I Learned

- Robot modeling using URDF
- Difference between RViz (visualizer) and Gazebo (physics simulator)
- How to add `collision`, `inertial`, and Gazebo color tags to a URDF
- How the ROS2–Gazebo bridge works (`gazebo_ros_pkgs`)
- How differential drive works — turning via wheel speed difference
- How to use the `diff_drive` Gazebo plugin
- ROS2 workspace architecture and package structure

---

## 📌 Future Improvements

- Integrate sensors (LiDAR, IMU, camera)
- Add SLAM and navigation stack
- Autonomous path planning
- Launch file to start everything in one command

---

## 📜 License

This project is open for learning and academic use.
