### Recording the errors when compile
#### Version of OS
- Ubuntu 16.04 
- ROS Kinetic
- Time 2019/11/12

> first to checkout catkin version

#### Errors
##### E1
find_package Eigen, Not providing FindEigen.cmake in CMAKE_MODULE_PAHT
##### A1
adding this line in lsd_slam/lsd_slam_viewer/CMakeLists.txt
include_directories()
