# OCS2 ROS2 + Coal + Pinocchio

## Summary
OCS2 ROS2 is developed based on [OCS2](https://github.com/leggedrobotics/ocs2)

## Installation
### Prerequisites
The OCS2 is tested under Ubuntu 22.04 with library versions as provided in the package sources.

### Dependencies
* C++ compiler with C++17 support
* ros2 humble
* Eigen (v3.4)
* Boost C++ (v1.74)
* For rigid multi-body dynamics library and self collision support clone Pinocchio and Coal into your workspace
```
# clone ocs2
git clone https://github.com/andy-wen/ocs2_ros2.git
# clone pinocchio
git clone --recurse-submodules https://github.com/andy-wen/pinocchio.git
# clone coal
git clone --recurse-submodules https://github.com/andy-wen/coal.git
```
* For various robotic assets used in OCS2 unit tests and the robotic examples
```
# Clone ocs2_robotic_assets in ros2_ws/src
git clone https://github.com/zhengxiang94/ocs2_robotic_assets.git
```
* plane_segmentation_ros2
```
# Clone plane_segmentation_ros2 in ros2_ws/src
git clone https://github.com/zhengxiang94/plane_segmentation_ros2.git
```
* others
```
sudo apt-get install ros-humble-grid-map-cv ros-humble-grid-map-msgs ros-humble-grid-map-ros ros-humble-grid-map-sdf libmpfr-dev libpcap-dev libglpk-dev ros-humble-octomap
```
* build
```
source /opt/ros/humble/setup.bash
colcon build --parallel-workers 8 --packages-up-to ocs2_mobile_manipulator_ros --cmake-args -DCMAKE_BUILD_TYPE=RelWithDebInfo
```
* launch
```
source install/setup.bash
ros2 launch ocs2_mobile_manipulator_ros manipulator_ridgeback_ur5.launch.py
```
