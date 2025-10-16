# ros2_camera_calibration
ros2的相机标定工具

参考文档：https://blog.csdn.net/qq_64079631/article/details/136423941

标定板生成网站：https://calib.io/pages/camera-calibration-pattern-generator

1.安装工具
```
  sudo apt install ros-humble-camera-calibration-parsers
```
```
  sudo apt install ros-humble-camera-info-manager
```
```
  sudo apt install ros-humble-launch-testing-ament-cmake
```
2.clone该仓库

3.进入ros2_camera_calibration/camera目录下

4.在该目录下打开终端colcon build

5.运行需要标定的相机节点
  
 - 运行海康相机节点

```
  source install/setup.bash
```
```
  ros2 run hik_camera hik_camera.launch.py
```
  - 运行mindvison相机节点
```
  source install/setup.bash
```
```
  ros2 run mindvision_camera mindvision_camera_node 
```
  - 运行galaxy相机节点
```
  source install/setup.bash
```
```
  ros2 run galaxy_camera galaxy_camera_node
```
  
6.运行标定工具
```
  source install/setup.bash
```

```
  ros2 run camera_calibration cameracalibrator --size 7x10 --square 0.015 image:=/image_raw  camera:=/camera --no-service-check
```

  参数：
  
  --size表示棋盘格角点数量，如8x11个格子的棋盘格，角点个数为7x10个，size参数就要写7x10  
  
  --square表示 棋盘格一个小格子的宽度（注意单位为m）

  image:=表示：图像话题名称为/image_raw 相机标定节点将从该话题接收图像进行标定
  
  camera:=表示：指定相机名称/camera
