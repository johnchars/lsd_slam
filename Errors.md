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
Line 30 find_package(Eigen REQUIRED) change to find_package(Eigen3 REQUIRED)
Line 36 include_directories(EIGEN_INCLUDE_DIR) change to include_directories(EIGEN3_INCLUDE_DIR)
adding message(STATUS "find_package Eigen: " ${EIGEN3_INCLUDE_DIR} )
lsd_slam_core/CMakeLists.txt has the same operations.
##### E2
opencv2/core/core.hpp: No such file or directory
##### A2
adding cmake_modules in package.xml

##### E3
fatal error: opencv2/core/core.hpp: No such file or directory in globalFuncs.h:22
##### A3
in lsd_slam_core/CMakeLists.txt
adding find_package(OpenCV REQUIRED) include_directories(${OpenCV_INCLUDE_DIRS}) target_link_libraries(${OpenCV_LIBS})

##### E4
qreal& {aka double&}
##### A4
https://github.com/tum-vision/lsd_slam/issues/163

##### E5
enum Status
##### A5
annotate KeyFrameDisplay.cpp #include "opencv2/opencv.hpp"

##### E6
Eigen::Map<const g2o::Vector7d> v(m)
##### A6
https://github.com/tum-vision/lsd_slam/issues/313

##### E7
