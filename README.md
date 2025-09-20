# RISC-V SoC Tapeout

This repository contains installation logs, tool snapshots, and documentation of the open-source VLSI flow used for a RISC-V SoC tapeout.  
It covers the setup and usage of tools such as Yosys, Icarus Verilog, GTKWave, Magic, Ngspice, and OpenLANE.  

> **Note:** The environment setup and installations are done on **Rocky Linux (RHEL-based)** instead of Ubuntu 20.04.

## Environment Setup

- OS: Rocky Linux (RHEL-based)
- VM: Oracle VirtualBox
- System Resources: 6 GB RAM, 50 GB HDD, 4 vCPUs

### System Preparation
Update system and install base packages:
```
sudo dnf update -y
sudo dnf groupinstall "Development Tools" -y
sudo dnf install git wget curl python3 python3-pip python3-venv make cmake\bison flex gawk tcl tk cairo-devel mesa libGL-devel mesa-libGLU-devel\ncurses-devel readline-devel zlib-devel libffi-devel -y

