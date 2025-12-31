# SimToFly - Drone Autonomy Guide

**From Simulation to Flight**

Complete tutorials for autonomous drones with ROS2 and ArduPilot.

[Start Phase 1 →](phase-1-simulation/README.md){ .md-button .md-button--primary }
[View on GitHub](https://github.com/simtofly/simtofly-guide){ .md-button }

---

## Overview

Learn autonomous drone development from simulation to real hardware using modern robotics tools.

**What you'll learn:**
- ArduPilot SITL simulation and Gazebo Harmonic 3D visualization
- ROS2 integration with MAVROS for advanced control
- Companion computer setup on Raspberry Pi
- Complete hardware deployment and real flight testing

**Who this is for:**
- Beginners with no prior ROS or ArduPilot experience
- Students learning autonomous drone systems
- Developers building drone applications
- Hobbyists transitioning from simulation to hardware

---

## Tutorial Phases

### Phase 1: Simulation Mastery

Master drone fundamentals in safe virtual environment.

**Content:**
- Prerequisites and environment setup
- ArduPilot SITL installation
- MAVProxy command-line control
- Gazebo Harmonic 3D simulation
- First autonomous waypoint mission

**Status:** ✅ Complete  
**Time:** 6-8 hours  
**Start:** [Phase 1 Overview](phase-1-simulation/README.md)

---

### Phase 2: ROS2 Integration

Connect ArduPilot to Robot Operating System.

**Content:**
- ROS2 Humble installation
- MAVROS setup and configuration
- Topics, services, and messages
- Custom ROS2 control nodes
- Autonomous missions via ROS2

**Status:** 🚧 In Development  
**Expected:** February 2026

---

### Phase 3: Companion Computer

Deploy ROS2 on Raspberry Pi for onboard processing.

**Content:**
- Raspberry Pi configuration
- Serial connection to flight controller
- ROS2 node deployment
- Hardware-in-the-loop testing
- Network communication

**Status:** 📋 Planned  
**Expected:** March 2026

---

### Phase 4: Real Hardware

Deploy complete system on actual drone.

**Content:**
- Hardware assembly and wiring
- Pre-flight safety procedures
- Ground testing
- First real flight test
- Complete mission deployment

**Status:** 📋 Planned  
**Expected:** April 2026

---

## Technology Stack

| Category | Tools |
|----------|-------|
| **Simulation** | ArduPilot SITL, Gazebo Harmonic, MAVProxy |
| **Middleware** | ROS2 Humble, MAVROS |
| **Hardware** | Pixhawk/Cube Orange, Raspberry Pi 4 |
| **Development** | Ubuntu 22.04 LTS, Python 3, Git |

---

## Verified System

All tutorials tested on real hardware:

**Software:**
- Ubuntu 22.04 LTS
- ArduPilot Copter 4.5.7
- ROS2 Humble
- Gazebo Harmonic
- MAVProxy 1.8+

**Hardware (Phase 4):**
- Flight Controller: Cube Orange / Pixhawk 6X
- Companion Computer: Raspberry Pi 4 (4GB+)

**Last verified:** December 2025

---

## Getting Started

!!! tip "Prerequisites"
    Before starting, ensure you have:
    
    - Ubuntu 22.04 LTS (native or VM)
    - 8GB RAM minimum (16GB recommended)
    - 30GB free disk space
    - Basic terminal familiarity
    
    No prior ROS or ArduPilot experience required.

**Quick Start:**

1. Check [Prerequisites](phase-1-simulation/1.1-prerequisites.md)
2. Set up [Environment](phase-1-simulation/1.2-environment-setup.md)
3. Follow [Phase 1 Overview](phase-1-simulation/README.md)

[Begin Phase 1 Now →](phase-1-simulation/README.md){ .md-button .md-button--primary }

---

## Features

**Beginner-Friendly:**
- Assumes zero prior knowledge
- Step-by-step instructions with verification
- Comprehensive troubleshooting sections
- Video demonstrations for complex procedures

**Complete Workflow:**
- Covers simulation through real hardware
- Modern stack (ROS2, not ROS1)
- Verified on actual drones
- Safety-first approach

**Actively Maintained:**
- Regular updates and improvements
- Community-driven development
- Responsive issue tracking
- New content added regularly

---

## Community & Support

### Get Help

- **Questions:** [GitHub Discussions](https://github.com/simtofly/simtofly-guide/discussions)
- **Bug Reports:** [GitHub Issues](https://github.com/simtofly/simtofly-guide/issues)
- **Live Chat:** Coming soon

### Contribute

We welcome contributions:

- Report bugs or errors
- Suggest improvements
- Submit pull requests
- Share your projects
- Help other learners

[Contributing Guidelines](https://github.com/simtofly/simtofly-guide/blob/main/CONTRIBUTING.md)

### Stay Connected

- ⭐ [Star on GitHub](https://github.com/simtofly/simtofly-guide)
- Watch for updates
- Follow [@sidharthmohannair](https://github.com/sidharthmohannair)

---

## About

**Author:** [Sidharth Mohan Nair](https://github.com/sidharthmohannair)

**Mission:** Make drone autonomy accessible to everyone, from complete beginners to experienced developers.

**Project Goals:**
- Provide complete learning path from simulation to hardware
- Use modern, industry-standard tools
- Verify all content on real hardware
- Maintain beginner-friendly approach
- Build active learning community

**License:** MIT — Free to use for personal and commercial projects

---

## Acknowledgments

Built with knowledge from:

- [ArduPilot](https://ardupilot.org/) community
- [ROS2](https://docs.ros.org/) documentation
- [MAVROS](https://github.com/mavlink/mavros) project
- Open-source robotics community

Special thanks to everyone who contributes to open-source drone software.

---

<p align="center">
  <b>Ready to begin?</b><br>
  <a href="phase-1-simulation/README.md">Start Your Drone Autonomy Journey →</a>
</p>