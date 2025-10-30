Self-Driven RC Car (Autonomous Vehicle using ROS2)
An autonomous RC car developed using the ROS2 (Robot Operating System 2) framework on Linux, capable of real-time mapping, object detection, and path planning. This project demonstrates the integration of robotics software with embedded hardware to achieve a self-driving miniature vehicle.

🧠 Overview
The goal of this project is to create a fully autonomous RC car that can navigate and make decisions in real-time without human intervention.
The system leverages LiDAR-based SLAM, sensor fusion, and ROS2 nodes to perceive its environment, localize itself, and plan a safe path.

⚙️ Key Features
🗺️ LiDAR-based SLAM — Real-time environment mapping using Simultaneous Localization and Mapping (SLAM).
🤖 Object Detection & Avoidance — Detects obstacles and adjusts its route dynamically.
🧭 Path Planning — Generates efficient trajectories to reach the destination while avoiding collisions.
🖥️ ROS2 Integration — Modular ROS2 nodes for sensor data handling, mapping, planning, and control.
🔧 Embedded Control — Real-time motor control via a microcontroller for differential drive actuation.
📡 Edge Processing — Sensor data processed on a Raspberry Pi for decision-making and communication with the microcontroller.

🛠️ Hardware Components
Component	Description:-
- Raspberry Pi 4:	Handles ROS2 nodes, SLAM, and decision logic
- LiDAR Sensor:	Provides 360° environmental scanning for mapping and obstacle detection
- Microcontroller: ( Arduino )	Executes motor and servo control commands
- Motor Driver: Controls the speed and direction of the DC motors
- RC Car Chassis:	Physical base for sensors, motors, and controller integration
- Ultrasonic Sensors (optional)	Used for short-range obstacle detection and lane stabilization to overcome inefficiencies of the hardware chassis and tires
- Battery Pack:	Powers the entire system

![WhatsApp Image 2023-10-06 at 23 32 51_babced82](https://github.com/user-attachments/assets/29493f4b-062c-400e-8b41-c493734d8180)




💻 Software Stack
Layer	Tools / Frameworks
- Operating System	Ubuntu (ROS2-compatible)
- Middleware	ROS2 (Humble)
- Mapping	LiDAR-based SLAM (e.g., GMapping, Hector SLAM, or Cartographer)
- Object Detection	Custom ROS2 node or external vision module
- Path Planning	ROS2 Navigation Stack
- Motor Control	Custom ROS2 topic to microcontroller via serial communication



🔁 System Architecture
graph TD
A[LiDAR Sensor] -->|Scan Data| B [ROS2 Mapping Node]
B --> C [SLAM / Localization]
C --> D [Path Planning Node]
D --> E [Motor Control Node]
E -->|PWM Commands| F [Microcontroller]
F -->|Drive Signals| G [Motors]
C --> H [Visualization (RViz)]

🚀 How It Works
1- LiDAR scans the surrounding environment in real time.
2- SLAM algorithm constructs and updates a 2D occupancy map.
3- Localization estimates the car’s position within the map.
4- Path planner determines the best route to the target.
5- Motor control node sends velocity and steering commands to the microcontroller.
6- The car navigates autonomously, avoiding obstacles and updating its map dynamically.

![WhatsApp Image 2024-07-05 at 15 19 06_981e4b57](https://github.com/user-attachments/assets/122f433f-b0f3-45c3-87b1-a2c492f83fe5)
<img width="919" height="508" alt="daswecfvvb" src="https://github.com/user-attachments/assets/0f733163-4802-45e2-814a-f8a6806dd9d5" />




🧩 Future Improvements

- Integrate camera-based vision for lane detection and traffic sign recognition.
- Enhance sensor fusion with IMU and GPS data for outdoor navigation.
- Implement deep reinforcement learning for decision-making.
- Add web-based dashboard for remote monitoring and telemetry.
