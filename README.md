**ARES-Bot**

Autonomous Wheeled-Leg Security and Search-Rescue Robot Using Edge AI and Multi-Modal Sensor Fusion

ARES-Bot is a highly advanced, interdisciplinary robotics project designed for autonomous patrol, suspicious activity detection, and victim localization in emergency scenarios. Built on the T-REX wheeled-leg robot platform, it combines the high-speed efficiency of wheel-drive systems with the terrain adaptability of legged mechanisms.

Team Supervisor: Ejoe Tso

All rights reserved by Ejoe Tso.

**Table of Contents**

Core Capabilities
System Architecture
Hardware & Software Stack
ROS Node Structure
Directory Structure
Getting Started

**16-Week R&D Roadmap**
License & Acknowledgements
**Core Capabilities
**
Wheeled-Leg Balancing: Advanced LQR control systems for self-balancing, dual-leg length control for roll compensation, and scissor-effect mitigation.
SLAM Navigation: LiDAR and Visual Inertial Odometry (VIO) fusion for robust indoor/outdoor mapping, obstacle avoidance, and waypoint patrol.
AI Vision System: Real-time object detection and human tracking using YOLO and DeepSORT running on TensorRT. Capable of suspicious activity recognition.
Victim Localization: Fusion of thermal imaging and audio microphone arrays to detect heat signatures and localize shouting in search-and-rescue scenarios.
Remote Dashboard: Web-based interface for remote monitoring, displaying robot maps, streaming multi-modal camera feeds, and real-time AI-driven alerts.

**System Architecture
** ARES-Bot utilizes a multi-layered software and hardware architecture:
Mobility Layer: Wheel-leg balancing, PID/LQR control, and autonomous movement execution.
Sensor Layer: Stereo Camera, Thermal Camera, LiDAR, IMU, Audio Mic Array.
Localization Layer: VIO, SLAM (2D/3D), MSCKF, GPS Fusion.
AI Layer: Human detection, victim localization, suspicious activity detection, object tracking.
ROS Integration Layer: Custom ROS topics, Services, Actions, and Navigation Stack integration.
Application Layer: Patrol system, mobile surveillance logic, rescue monitoring, and alert dashboard.

**Hardware & Software Stack
**
**Hardware
**
Main Robot Platform: T-REX Wheeled-Leg Robot
Edge AI Processor: Horizon RDK-X3

Sensors: LiDAR, Thermal Camera, USB Stereo Camera, Microphone Array, IMU

Software

OS: Ubuntu 20.04

Robotics Framework: ROS Noetic / ROS2 Humble

Computer Vision: OpenCV, YOLOv8

AI & Deep Learning: PyTorch, TensorRT

Visualization/Simulation: RViz, Gazebo, Foxglove Studio

**ROS Node Structure**

The system is distributed across several specialized ROS nodes:

/ares_navigation_node
/ares_patrol_node
/ares_rgb_detection_node
/ares_thermal_detection_node
/ares_audio_detection_node
/ares_sensor_fusion_node
/ares_victim_localization_node
/ares_activity_detection_node
/ares_dashboard_node
/ares_alert_node


** Directory Structure
**
ARES-Bot/
├── src/
│   ├── ai_models/          # YOLO, PyTorch, and DeepSORT tracking models
│   ├── config/             # YAML configurations, Rviz setups, and LQR tuning
│   ├── control/            # LQR balancing and wheeled-leg kinematic scripts
│   ├── dashboard/          # Backend server and web-based monitoring UI
│   ├── launch/             # ROS2 launch files for integrated bringup
│   ├── localization/       # VIO, MSCKF, and TF broadcasting scripts
│   ├── navigation/         # SLAM Toolbox and Nav2 configuration packages
│   └── perception/         # Sensor fusion (RGB, Thermal, Audio, LiDAR)
├── datasets/               # Sample data, rosbag recordings for testing
├── documentation/          # Facilitation guides, system specs, and hardware manuals
├── evaluation/             # Metrics, test results, and performance graphs
└── README.md

**Getting Started**

1. Prerequisites

Ensure you have Ubuntu 20.04 installed, along with ROS2 Humble.

2. Setup the Workspace

Clone the repository and build the ROS workspace:

# Create a ROS workspace
mkdir -p ~/ares_ws/src
cd ~/ares_ws/src

# Clone the repository
git clone [https://github.com/your-org/ARES-Bot.git](https://github.com/your-org/ARES-Bot.git)

# Install dependencies using rosdep
cd ~/ares_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y

# Build the workspace
colcon build --symlink-install

# Source the setup file
source install/setup.bash


3. Launching the Robot

To bring up the core T-REX platform and the ARES-Bot sensor suite:

ros2 launch ares_bringup robot_core.launch.py


(Refer to the documentation/ folder for specific launch commands related to the AI Vision System and Dashboard).

**16-Week R&D Roadmap**

This project is structured around a comprehensive 16-week facilitation guide:

Phase 1 (Weeks 1-2): Project Foundation & Environment Setup
Phase 2 (Weeks 3-5): Mobility Control & SLAM Navigation
Phase 3 (Weeks 6-8): AI Vision System Integration
Phase 4 (Weeks 9-11): Multi-Modal Victim Localization
Phase 5 & 6 (Weeks 12-14): Dashboard UI & Full System Integration
Phase 7 (Weeks 15-16): Research Evaluation & Final Demonstration

License & Acknowledgements

Copyright © 2026 ARES-Bot Research Team.

Team Supervisor: Ejoe Tso

All rights reserved by Ejoe Tso.

Built using the T-REX Wheeled-Leg Robot platform and Horizon RDK-X3 edge computing environment.

Suitable for Undergraduate Capstone Projects, AI Robotics Hackathons, and Industrial R&D Prototyping.
