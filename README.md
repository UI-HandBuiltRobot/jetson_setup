# ROS 2 Humble System Setup Script (Ubuntu)

This repository contains a **single, primary setup script** intended to bootstrap a fresh Ubuntu system for **ROS 2 Humble–based robotics development**.

The script installs ROS 2, common robotics dependencies, development tools, remote desktop access, IDEs, and hardware support used in lab and research environments.

> **TL;DR:** Clone the repo, run the script once on a fresh machine, reboot, and you’re ready to work.

---

## What This Script Does

This script automates the following:

### System Setup
- Updates and upgrades the system
- Creates timestamped logs for debugging and record keeping

### ROS 2 Installation
- Installs **ROS 2 Humble Desktop**
- Skips installation if ROS 2 Humble is already present
- Installs commonly used ROS packages:
  - `vision_msgs`
  - `usb_cam`

### Development Tools
- Git
- Python 3, pip, virtualenv
- Editors: `vim`, `nano`, `gedit`, `emacs`
- Terminal tools: `terminator`

### IDEs
- Arduino IDE (via Snap)
- VS Code (via local `code.deb` installer)

### Networking & Remote Access
- Enables UFW firewall
- Opens SSH (port 22)
- Installs and configures:
  - XRDP
  - XFCE4 desktop environment
- Verifies Xorg (Wayland may break RDP)

### Hardware & Device Support
- Adds user to `dialout` group for serial devices
- Installs `v4l-utils` and `guvcview` for camera testing
- Adds udev rules for **Hiwonder robotic arms**
- Includes a test script for validating arm connectivity

### Snap Fixes
- Applies a known workaround for Snap issues on some Ubuntu systems

---

## Repository Contents

```text
.
├── setup.sh                     # Main setup script (this is the point of the repo)
├── startwm.sh                   # Modified XRDP window manager script
├── 99-hiwonder-arm.rules        # udev rules for Hiwonder arm
├── test_xarm_connection.py      # Hardware test script
├── code.deb                     # VS Code installer (will need to be installed by user following course instructions)
├── log/                         # Auto-generated setup logs
└── README.md
