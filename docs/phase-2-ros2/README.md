# Phase 2: ROS2 Integration

Connect ArduPilot to the ROS2 robotics ecosystem for programmable drone control.

---

## Overview

Phase 1 taught you drone control through MAVProxy commands. Phase 2 bridges that knowledge to ROS2, the industry-standard robotics framework.

**What changes:**

| Phase 1 | Phase 2 |
|---------|---------|
| Type commands manually | Write Python code |
| MAVProxy scripting | ROS2 nodes |
| Basic mission files | Programmable missions |
| 2D map visualization | RViz 3D visualization |
| No data recording | ROS2 bag recording |

**What stays the same:**

- Same SITL simulator
- Same Gazebo (optional)
- Same drone behavior
- Same MAVLink protocol underneath

---

## What You'll Build

By the end of Phase 2:

- Telemetry monitoring node
- Flight control node (arm, takeoff, navigate, land)
- Mission execution system with YAML configuration
- RViz visualization with path and waypoint markers
- Flight recording and replay capability

---

## Prerequisites

Before starting Phase 2:

- Phase 1 complete
- SITL launches and accepts commands
- Gazebo integration working (optional but recommended)
- Comfortable with basic terminal operations

---

## Tutorial Sections

| Section | Title | Time |
|---------|-------|------|
| [2.1](2.1-ros2-installation.md) | ROS2 Installation and Core Concepts | 60 min |
| [2.2](2.2-mavros-setup.md) | MAVROS Setup | 45 min |
| [2.3](2.3-reading-drone-data.md) | Reading Drone Data | 60 min |
| [2.4](2.4-controlling-drone.md) | Controlling the Drone | 90 min |
| [2.5](2.5-autonomous-mission.md) | Autonomous Mission Node | 90 min |
| [2.6](2.6-rviz-visualization.md) | RViz Visualization | 45 min |
| [2.7](2.7-recording-replay.md) | Recording and Replay | 45 min |

**Total time:** 8-10 hours

---

## Technology Stack

| Component | Version | Purpose |
|-----------|---------|---------|
| ROS2 | Humble | Robotics middleware |
| MAVROS | 2.x | MAVLink-ROS2 bridge |
| Python | 3.10 | Node development |
| RViz2 | Humble | Visualization |

**From Phase 1 (already installed):**

- ArduPilot SITL (Copter 4.5.7)
- Gazebo Harmonic
- MAVProxy

---

## Architecture

```
┌────────────────────────────────────────────────────┐
│                                                    │
│  ┌──────────┐       ┌──────────┐                   │
│  │  Gazebo  │◄─────►│   SITL   │                   │
│  │ (opt.)   │       │ ArduPilot│                   │
│  └──────────┘       └────┬─────┘                   │
│                          │                         │
│                     MAVLink                        │
│                          │                         │
│                    ┌─────▼─────┐                   │
│                    │  MAVROS   │                   │
│                    └─────┬─────┘                   │
│                          │                         │
│                   ROS2 Topics                      │
│            ┌─────────────┼─────────────┐           │
│            ▼             ▼             ▼           │
│     ┌──────────┐  ┌──────────┐  ┌──────────┐       │
│     │ Your     │  │  RViz    │  │  rosbag  │       │
│     │ Nodes    │  │          │  │          │       │
│     └──────────┘  └──────────┘  └──────────┘       │
│                                                    │
└────────────────────────────────────────────────────┘
```

---

## Workspace Structure

After completing Phase 2:

```
~/simtofly_ws/
├── ardupilot/              # From Phase 1
├── ardupilot_gazebo/       # From Phase 1
├── logs/                   # Flight recordings
├── missions/               # Mission files
├── scripts/                # Helper scripts
└── ros2_ws/
    ├── src/
    │   └── drone_control/  # Your ROS2 package
    │       ├── drone_control/
    │       │   ├── telemetry_node.py
    │       │   ├── flight_control.py
    │       │   ├── mission_node.py
    │       │   ├── path_publisher.py
    │       │   └── waypoint_markers.py
    │       ├── config/
    │       │   └── mission.yaml
    │       └── rviz/
    │           └── drone.rviz
    ├── build/
    ├── install/
    └── log/
```

---

## Quick Reference

### Launch Sequence

```bash
# Terminal 1: SITL
cd ~/simtofly_ws/ardupilot/ArduCopter
sim_vehicle.py -v ArduCopter --map --console

# Terminal 2: MAVROS
ros2 launch mavros apm.launch fcu_url:=udp://:14550@127.0.0.1:14555

# Terminal 3: Your nodes
ros2 run drone_control mission_node
```

### Common Commands

```bash
# List topics
ros2 topic list

# Echo topic data
ros2 topic echo /mavros/state

# Call service
ros2 service call /mavros/cmd/arming mavros_msgs/srv/CommandBool "{value: true}"

# Record bag
ros2 bag record -o my_flight /mavros/state /mavros/local_position/pose

# Play bag
ros2 bag play my_flight
```

---

## Success Criteria

Phase 2 is complete when you can:

- Launch ROS2 + MAVROS + SITL stack
- Read telemetry via Python subscriber
- Control drone via Python (arm, fly, land)
- Execute waypoint mission from YAML file
- Visualize flight in RViz
- Record and replay flight data

---

## Getting Help

If you encounter issues:

1. Check troubleshooting section in relevant tutorial
2. Verify all previous sections completed successfully
3. Search existing issues on GitHub
4. Open new issue with:
   - Section you're on
   - Command that failed
   - Full error message
   - Output of `ros2 topic list`

---

## Ready to Start?

[Begin with 2.1 ROS2 Installation →](2.1-ros2-installation.md)

---

[← Back to Home](../index.md) | [Phase 1 Review](../phase-1-simulation/README.md)
