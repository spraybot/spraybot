# spraybot

This repos serves as the base to clone all the repos needed for the spraybot project.

## Setup Spraybot Workspace

Create workspace and clone all repos:

```bash
mkdir -p ~/spraybot_ws/src
cd ~/spraybot_ws
git clone git@github.com:spraybot/spraybot.git
vcs import src < spraybot/spraybot.repos
```

Install dependencies for all the packages:

```bash
# If rosdep has not been initalized
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -y
```

## Extended Installation
Some other installation steps are needed for some applications. See the following [Extended Installation](https://github.com/spraybot/spraybot/wiki/Extended-Installation) wiki for detailed instructions.

## Continuous Integration
| Repository | Status |
| --- | --- |
| [spraybot_bringup](https://github.com/spraybot/spraybot_bringup) | [![ROS2 CI](https://github.com/spraybot/spraybot_bringup/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/spraybot/spraybot_bringup/actions/workflows/ci.yml) |
| [spraybot_navigation](https://github.com/spraybot/spraybot_navigation) | [![ROS2 CI](https://github.com/spraybot/spraybot_navigation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/spraybot/spraybot_navigation/actions/workflows/ci.yml) |
| [spraybot_perception](https://github.com/spraybot/spraybot_perception) | [![ROS2 CI](https://github.com/spraybot/spraybot_perception/actions/workflows/ci.yaml/badge.svg?branch=main)](https://github.com/spraybot/spraybot_perception/actions/workflows/ci.yaml) |
| [spraybot_simulation](https://github.com/spraybot/spraybot_simulation) | [![ROS2 CI](https://github.com/spraybot/spraybot_simulation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/spraybot/spraybot_simulation/actions/workflows/ci.yml) |
| [spraybot_utils](https://github.com/spraybot/spraybot_utils) | [![ROS2 CI](https://github.com/spraybot/spraybot_utils/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/spraybot/spraybot_utils/actions/workflows/ci.yml) |
| [mapviz](https://github.com/spraybot/mapviz) | [![CI](https://github.com/spraybot/mapviz/actions/workflows/main.yml/badge.svg)](https://github.com/spraybot/mapviz/actions/workflows/main.yml)
| [husky](https://github.com/spraybot/husky) | [![husky_ci](https://github.com/spraybot/husky/actions/workflows/ci.yml/badge.svg)](https://github.com/spraybot/husky/actions/workflows/ci.yml) |
| [ros2_ouster_drivers](https://github.com/spraybot/ros2_ouster_drivers) | [![ROS2 CI (Build Only)](https://github.com/spraybot/ros2_ouster_drivers/actions/workflows/ci.yml/badge.svg)](https://github.com/spraybot/ros2_ouster_drivers/actions/workflows/ci.yml) |
| [vectornav](https://github.com/spraybot/vectornav) | [![ROS2 CI (Build Only)](https://github.com/spraybot/vectornav/actions/workflows/ci.yml/badge.svg)](https://github.com/spraybot/vectornav/actions/workflows/ci.yml) |
| [pcl_processor](https://github.com/spraybot/pcl_processor) | None |

## Tooling

Install Dependencies:

```bash
python3 -m pip install vcstool yamllint
```

Linter:

```bash
yamllint spraybot.repos -f github -d "{extends: default, rules: {document-start: {present: false}, key-ordering: {}}}"
```
