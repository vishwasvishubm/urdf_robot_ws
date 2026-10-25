# ROS 2 URDF Differential-Drive Robot (RViz)

A URDF model of a differential-drive robot (`base_link` + two continuous wheel joints), visualised in RViz with the included `robot_view.rviz` config.

## Packages

- `robot_description` (ament_cmake): `urdf/differential_robot.urdf`

## Requirements

- Ubuntu 24.04, ROS 2 Jazzy
- `ros-jazzy-joint-state-publisher-gui`, `ros-jazzy-rviz2`

## Build

```bash
cd urdf_robot_ws
source /opt/ros/jazzy/setup.bash
colcon build
source install/setup.bash
```

## Run

Source `install/setup.bash` in every new terminal first.

```bash
# Terminal 1
ros2 run robot_state_publisher robot_state_publisher \
  --ros-args -p robot_description:="$(cat src/robot_description/urdf/differential_robot.urdf)"

# Terminal 2
ros2 run joint_state_publisher_gui joint_state_publisher_gui

# Terminal 3
rviz2 -d robot_view.rviz
```

## Concepts practised

URDF links and joints, TF, robot_state_publisher, RViz
