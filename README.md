# HIMLoco in IsaacSim using IsaacLab Manager-based RL Framework

This repository contains an implementation of **HIMLoco** [(Hybrid Internal Model for agile legged locomotion)](https://junfeng-long.github.io/HIMLoco) integrated with **IsaacSim** and the **IsaacLab Manager-based RL framework**. The setup enables efficient training of robotic locomotion models, leveraging IsaacSim’s advanced simulation capabilities and IsaacLab's reinforcement learning environment.

## Key Features:
- **Agile Legged Locomotion**: HIMLoco enables learning-based control for agile legged robots.
- **IsaacSim Integration**: Uses **IsaacSim** for physics-based simulations of robots and environments.
- **IsaacLab Framework**: Leverages **IsaacLab Manager-based RL framework** for easy setup, training, and testing of reinforcement learning algorithms.
- **GPU Acceleration**: Utilizes GPU-based simulation for faster and more scalable training.
- **Pre-configured Environments**: Ready-to-use environments for robot training in realistic conditions.
- **Modular Setup**: Modular components for easy configuration and extension to other robotics tasks.

## 📚 Getting Started

### Installation

We test our codes under the following environment:

- Ubuntu 22.04
- NVIDIA Driver: 535.183.01
- CUDA 12.2
- Python 3.10.15
- PyTorch 2.4.0
- Isaac Sim: 4.2.0

1. Install Isaac Sim:
  - Download and install Isaac Sim: 4.2.0 from https://docs.omniverse.nvidia.com/isaacsim/latest/installation/install_workstation.html
  - Verify Isaac Sim root directory 
    `export ISAACSIM_PATH="${HOME}/.local/share/ov/pkg/isaac-sim-4.2.0"`
  - Verify Isaac Sim python executable
    `export ISAACSIM_PYTHON_EXE="${ISAACSIM_PATH}/python.sh"`

2. Clone this repository.

  - `git clone https://github.com/shendredm/HIMLOCO_Isaacsim.git`
  - `cd HIMLOCO_Isaacsim`
  - `ln -s path_to_isaac_sim _isaac_sim`  
  **For example: ln -s /home/nvidia/.local/share/ov/pkg/isaac-sim-4.2.0 _isaac_sim**

3. Create an environment:
  - Option 1: Default name for conda environment is 'isaaclab'
    `./isaaclab.sh --conda  # or "./isaaclab.sh -c"`
  - Option 2: Custom name for conda environment
    `./isaaclab.sh --conda my_env  # or "./isaaclab.sh -c my_env"`

4. Install rsl_rl for HIMLoco.
  - `conda activate isaaclab`
  - `./isaaclab.sh --install none`  
  **Here none is important as we dont want to install other rl frameworks**
  - `cd rsl_rl && pip install -e .`
  

**Note:** Please use rsl_rl provided in this repo, there are modefications on these repos.

### Tutorial

1. Train a policy:

  - `python source/standalone/workflows/him_rsl_rl/train.py --task Isaac-Velocity-HIMLOCO-A1-v0`

2. Play and export the latest policy:
  - `python source/standalone/workflows/him_rsl_rl/play.py --task Isaac-Velocity-HIMLOCO-A1-Play-v0`

## 📚 Documentation

- [**HIMLoco**](https://junfeng-long.github.io/HIMLoco/)
- [**IsaacSim**](https://docs.omniverse.nvidia.com/isaacsim/latest/overview.html)
- [**IsaacLab**](https://isaac-sim.github.io/IsaacLab/main/index.html)


## 👏 Acknowledgements

- [HIMLoco]: Hybrid Internal Model for learning agile legged locomotion.
- [IsaacSim]: NVIDIA’s platform for robotics simulation. 
- [IsaacLab]: Open-source framework for reinforcement learning with robot simulation.


## Isaac Lab
**Isaac Lab** is a unified and modular framework for robot learning that aims to simplify common workflows
in robotics research (such as RL, learning from demonstrations, and motion planning). It is built upon
[NVIDIA Isaac Sim](https://docs.omniverse.nvidia.com/isaacsim/latest/overview.html) to leverage the latest
simulation capabilities for photo-realistic scenes and fast and accurate simulation.

Please refer to our [documentation page](https://isaac-sim.github.io/IsaacLab) to learn more about the
installation steps, features, tutorials, and how to set up your project with Isaac Lab.  

[![IsaacSim](https://img.shields.io/badge/IsaacSim-4.2.0-silver.svg)](https://docs.omniverse.nvidia.com/isaacsim/latest/overview.html)
[![Python](https://img.shields.io/badge/python-3.10-blue.svg)](https://docs.python.org/3/whatsnew/3.10.html)
[![Linux platform](https://img.shields.io/badge/platform-linux--64-orange.svg)](https://releases.ubuntu.com/20.04/)
[![Windows platform](https://img.shields.io/badge/platform-windows--64-orange.svg)](https://www.microsoft.com/en-us/)


