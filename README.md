# spraybot

This repos serves as the base to clone all the repos needed for the spraybot project

## Setup Spraybot Workspace

Create workspace and clone all repos:

```bash
mkdir -p ~/spraybot_ws/src
cd ~/spraybot_ws
wget https://raw.githubusercontent.com/spraybot/spraybot/main/spraybot.repos
vcs import src < spraybot.repos
```

Install dependencies for all the packages:

```bash
# If rosdep has not been initalized
sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src -y
```

## Tooling

Install Dependencies:

```bash
python3 -m pip install vcstool yamllint
```

Linter:

```bash
yamllint spraybot.repos -f github -d "{extends: default, rules: {document-start: {present: false}, key-ordering: {}}}"
```
