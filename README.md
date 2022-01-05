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


## Tooling

Install Dependencies:

```bash
python3 -m pip install vcstool yamllint
```

Linter:

```bash
yamllint spraybot.repos -f github -d "{extends: default, rules: {document-start: {present: false}, key-ordering: {}}}"
```
