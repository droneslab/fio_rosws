This repo is used to run FAST-LIO lidar mapping and localization. It is intended to support the [FOV Optimization main rep](https://github.com/yuyangch/FOV_Optimization_On_Manifold).

To run lidar mapping i.e. generate a PCD map file using FAST-LIO use the following:

``
roslaunch fio-main run.launch mapping_mode:=1
``

The generated map is stored in `src/fast-lio-optimization/PCD/scans.pcd`. A subsequent run of the mapping will overwrite `scans.pcd`. To save a map for later use, please make a copy of it.


To run localization i.e. use a saved PCD map and publish odometry with FAST-LIO, use the following:

``
roslaunch fio-main run.launch mapping_mode:=0
``

`src/fast-lio-localization/PCD/scans.pcd` will be usd for localization. Ensure the right maps is copied over to this.

To capture frames from the realsense camera for COLMAP and for FOV optimization runs, use `debug.launch` like so:

``
roslaunch fio-main debug.launch
``
