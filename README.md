# SimToFly — Complete Drone Autonomy Guide

![Cover Image](/assets/images/cover_image.png)

<p align="center">
  <b>From Simulation to Flight</b><br>
  Your complete path to autonomous drones with ROS2 and ArduPilot
</p>

<p align="center">
  <a href="#-what-youll-learn">What You'll Learn</a> •
  <a href="#-tutorial-phases">Tutorial Phases</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-verified-hardware">Verified Hardware</a> •
  <a href="#-about">About</a>
</p>

---

## 🎯 What You'll Learn

This comprehensive tutorial takes you from zero to autonomous drone flight:

- ✅ **ArduPilot SITL** — Master simulation before touching hardware
- ✅ **Gazebo Integration** — Realistic 3D simulation with physics
- ✅ **ROS2 + MAVROS** — Connect ArduPilot to Robot Operating System
- ✅ **Companion Computer** — Setup Raspberry Pi for onboard processing
- ✅ **Real Hardware Deployment** — Deploy and fly your actual drone

**Beginner-friendly** • **Step-by-step verification** • **Tested on real hardware**

---

## 📚 Tutorial Phases

### Phase 1: Simulation Mastery 🖥️
*Master the fundamentals in a safe, virtual environment*

- Prerequisites and environment setup
- ArduPilot SITL installation and first launch
- MAVProxy command-line control
- Gazebo 3D simulation integration
- First autonomous mission in simulation

**Status:** 🚧 Under development

---

### Phase 2: ROS2 Integration 🤖
*Connect your drone to the Robot Operating System*

- ROS2 Humble installation
- MAVROS setup and configuration
- Understanding topics, services, and messages
- Building custom ROS2 control nodes
- Autonomous missions via ROS2

**Status:** 📋 Planned

---

### Phase 3: Companion Computer 🔧
*Setup onboard processing with Raspberry Pi*

- Raspberry Pi configuration for drones
- Serial connection to flight controller
- Deploying ROS2 nodes on companion computer
- Hardware-in-the-loop testing
- Network communication setup

**Status:** 📋 Planned

---

### Phase 4: Real Hardware 🚁
*Deploy everything on your actual drone*

- Hardware assembly and wiring
- Pre-flight safety checklist
- Ground testing procedures
- First real flight test
- Complete mission deployment

**Status:** 📋 Planned

---

## 🚀 Getting Started

### Prerequisites

Before starting, you need:

- **Computer:** Ubuntu 22.04 (native or VM), 8GB RAM minimum
- **Time:** Plan for 2-4 hours per phase
- **Attitude:** Patience and willingness to learn

**No prior ROS experience required** — we teach everything from scratch.

### Start Here

👉 **[Begin with Phase 1: Simulation Mastery](docs/phase-1-simulation/README.md)**

Each phase builds on the previous, so follow in order.

---

## ✅ Verified Hardware

All tutorials are tested on real hardware:

- **Flight Controller:** Cube Orange / Pixhawk family
- **Companion Computer:** Raspberry Pi 4 (4GB+)
- **Software Stack:**
  - Ubuntu 22.04 LTS
  - ROS2 Humble
  - ArduPilot Copter 4.5.x
  - Gazebo Garden
  - MAVROS 2.x

**Last verified:** December 2024

---

## 🗂️ Repository Structure
```
simtofly-guide/
├── docs/
│   ├── phase-1-simulation/      # SITL and Gazebo tutorials
│   ├── phase-2-ros2/            # ROS2 integration guides
│   ├── phase-3-companion/       # Raspberry Pi setup
│   └── phase-4-hardware/        # Real drone deployment
├── assets/
│   ├── images/                  # Screenshots and diagrams
│   └── videos/                  # Tutorial video clips
└── README.md                    # You are here
```

---

## 🤝 About SimToFly

**SimToFly** bridges the gap between simulation and real-world drone deployment.

Most tutorials stop at simulation or skip critical steps. We provide:

- **Complete workflow** — Simulation through real flight
- **Beginner-friendly** — Assumes zero prior knowledge
- **Verified steps** — Every command tested on actual hardware
- **Modern stack** — ROS2 (not ROS1), latest ArduPilot
- **Safety-first** — Proper testing progression

Created by [@sidharthmohannair](https://github.com/sidharthmohannair)

**Other SimToFly Repositories:**
- [simtofly-ros2](https://github.com/simtofly/simtofly-ros2) — ROS2 packages and examples *(coming soon)*
- [simtofly-setup](https://github.com/simtofly/simtofly-setup) — Automated setup scripts *(coming soon)*

---

## 🌟 Why SimToFly?

**What makes this different:**

| Feature | SimToFly | Others |
|---------|----------|--------|
| ROS Version | ROS2 (current) | Mostly ROS1 (legacy) |
| Hardware Validation | ✅ Tested on real drones | ⚠️ Simulation only |
| Companion Computer | ✅ Complete Raspberry Pi setup | ⚠️ Brief mentions |
| Beginner-Friendly | ✅ Assumes zero knowledge | ⚠️ Assumes experience |
| Maintenance | ✅ Actively updated | ⚠️ Often outdated |

---

## 📖 Documentation Status

🚧 **Phase 1 is under active development**

Follow this repository or ⭐ star it to get notified when sections are published.

**Estimated timeline:**
- Phase 1: January 2026
- Phase 2: February 2026
- Phase 3: March 2026
- Phase 4: April 2026

---

## 💬 Community & Support

- **Questions?** [Open an issue](https://github.com/simtofly/simtofly-guide/issues)
- **Found an error?** [Submit a pull request](https://github.com/simtofly/simtofly-guide/pulls)
- **Want to contribute?** See [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 📜 License

This tutorial is released under the **MIT License** — see [LICENSE](LICENSE) for details.

You are free to:
- ✅ Use for personal or commercial projects
- ✅ Modify and adapt
- ✅ Share and distribute

**Attribution appreciated but not required.**

---

## 🙏 Acknowledgments

Built with knowledge from:
- [ArduPilot](https://ardupilot.org/) community and documentation
- [ROS2](https://docs.ros.org/) official guides
- [MAVROS](https://github.com/mavlink/mavros) maintainers
- Countless forum posts and GitHub issues from the community

Special thanks to everyone who contributes to open-source drone software.

---

<p align="center">
  <b>Ready to start your journey?</b><br>
  👉 <a href="docs/phase-1-simulation/README.md">Begin Phase 1: Simulation Mastery</a>
</p>

---

<p align="center">
  Made with ❤️ for the drone community<br>
  <a href="https://github.com/simtofly">SimToFly</a> • 
  <a href="https://github.com/sidharthmohannair">@sidharthmohannair</a>
</p>
