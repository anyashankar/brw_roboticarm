# Robotic Arm Control & Simulation

A ROS-based system for controlling and simulating a 6-DOF robotic arm. This project demonstrates **real-time motion planning**, **inverse kinematics**, and **hardware–software integration** with support for both physical and simulated environments.

---

## Features

- **Inverse Kinematics Engine:** Computes joint trajectories for arbitrary end-effector targets.
- **Multi-Modal Control:** Keyboard and gamepad input relayed to ROS topics for arm control.
- **Simulation & Visualization:** Integrated with RViz and URDF for physics-based simulation.
- **Safe & Stable Motion:** Power regulation, motor protection logic, and current monitoring.
- **Modular ROS Nodes:** Clear separation of IK solver, controller coordination, and input relay nodes.

---

## Tech Stack

- **Languages:** Python, C++
- **Frameworks:** ROS (Robot Operating System)
- **Simulation:** RViz, URDF
- **Build System:** CMake / catkin
- **Messaging:** ROS topics and services for motor control and state feedback

---

## Installation

```bash
# Clone into your ROS workspace
cd ~/catkin_ws/src
git clone <repo_url>
cd ..
catkin_make
source devel/setup.bash
```

---

### Usage
Launch the simulation and control interface:

```bash
# Example: Start robot simulation
roslaunch arm_sim <launch_file>.launch

# Run keyboard input relay
rosrun keyboard_relay keyboard_input_relay.py
```

(Replace `<launch_file>` with the appropriate file for your setup.)

### System Architecture
- **IK Solver Node:** Calculates joint configurations for desired end-effector poses.
- **Controller Coordinator:** Synchronizes motor drivers and manages safe voltage/current limits.
- **Input Relay:** Bridges user inputs (keyboard or gamepad) to ROS topics.
- **Simulation Layer:** Provides visual and physical simulation for testing without hardware.

### Applications
- Robotics and automation (manufacturing, assembly lines)
- Human–machine interfaces (surgery, remote operations)
- Robotics research and ROS development practice

### Key Learnings & Highlights
- Designed and implemented modular ROS nodes with a CI-friendly build system.
- Applied motion planning and real-time input relaying with fault tolerance.
- Integrated hardware-level concepts (electromagnets, motor drivers) into software abstractions.
- Implemented simulations to allow development without physical hardware.

### Future Improvements
- Add computer vision for autonomous grasping
- Improve IK solver with trajectory optimization
- Expand control interface with web or mobile APIs

