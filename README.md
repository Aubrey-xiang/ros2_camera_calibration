# ros2_camera_calibration
ros2的相机标定工具

参考文档：https://blog.csdn.net/qq_64079631/article/details/136423941

标定板生成网站：https://calib.io/pages/camera-calibration-pattern-generator

**1.安装工具**
```
  sudo apt install ros-humble-camera-calibration-parsers
```
```
  sudo apt install ros-humble-camera-info-manager
```
```
  sudo apt install ros-humble-launch-testing-ament-cmake
```
**2.clone该仓库，解压压缩包**

```
git clone 
```

**3.打开camera/src,在该目录下打开终端运行以下命令编译**

```
colcon build --symlink-install --parallel-workers 4
```

**4.选择不同的相机运行不同的节点,运行节点前别忘了source**

```
source install/setup.bash 
```


(1)海康相机

```
ros2 run hik_camera hik_camera_node 
```


(2)迈德威视

```
ros2 run mindvision_camera mindvision_camera_node 
```

**5.运行标定工具**

```
source install/setup.bash
```


```
  ros2 run camera_calibration cameracalibrator --size 10x7 --square 0.015 image:=/image_raw  camera:=/camera --no-service-check
```

  参数：
  
  --size表示棋盘格角点数量，如8x9个格子的棋盘格，角点个数为7x8个，size参数就要写7x8  
  
  --square表示 棋盘格一个小格子的宽度（注意单位为m）

  image:=表示：图像话题名称为/image_raw 相机标定节点将从该话题接收图像进行标定
  
  camera:=表示：指定相机名称/camera
