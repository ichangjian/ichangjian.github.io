---
layout: post
title:  "更新AprilTag3可识别Aprilgrid"
date:   2020-04-09 21:38:05 +0800
categories: 计算机视觉
tag: SLAM
---

* content
{:toc}

[Kalibr](https://github.com/ethz-asl/kalibr)使用的[Aprilgrid](https://github.com/ethz-asl/kalibr/wiki/calibration-targets#olson)识别算法是在[Apriltag1](http://people.csail.mit.edu/kaess/apriltags/)的基础上增加了黑色边框的宽度形成的[Apriltag2](https://github.com/ethz-asl/ethzasl_apriltag2)。

现在最新的[Apriltag](https://github.com/AprilRobotics/apriltag)已经发展到了第3个版本：

1. 2011年[AprilTag: A robust and flexible visual fiducial system](https://april.eecs.umich.edu/papers/details.php?name=olson2011tags)
2. 2016年[AprilTag 2: Efficient and robust fiducial detection](https://april.eecs.umich.edu/papers/details.php?name=wang2016iros)
3. 2019年[Flexible Layouts for Fiducial Tags](https://april.eecs.umich.edu/papers/details.php?name=krogius2019iros)


我的[更新的Apriltag](https://github.com/ichangjian/apriltag)，是在[Apriltag3](https://github.com/AprilRobotics/apriltag)的基础上增加了“tagGrid36h11”，tagGrid36h11是在tag36h11的基础上增加了对黑色边框宽度的定义，并在**apriltag_quad_thresh_params**结构体中增加了**erode**变量控制**threshold**函数对图像进行腐蚀操作。测试下来对Aprilgrid识别的召回率和速度均有不同程度的提升。
