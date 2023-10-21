## compile the

Clone the repository and catkin_make:

```
    cd ~/$A_ROS_DIR$/src
    git clone https://github.com/hku-mars/FAST_LIO.git
    cd FAST_LIO
    git submodule update --init
    cd ../..
    catkin_make  -DCATKIN_WHITELIST_PACKAGES="fast_lio"
    source devel/setup.bash
```
- Remember to source the livox_ros_driver before build (follow 1.3 **livox_ros_driver**)
- If you want to use a custom build of PCL, add the following line to ~/.bashrc
  ```export PCL_ROOT={CUSTOM_PCL_PATH}```


## 跑demo
```sh
roslaunch fast_lio mapping_velodyne.launch

# another termianl 
cd /mnt/hgfs/data/230910_slam_ds/221122_FAST_LIO_DS/Velodyne_HDL-32E
rosbag play 20130110.bag
```

```sh
roslaunch fast_lio mapping_horizon.launch

# another termianl 
cd /mnt/hgfs/data/230910_slam_ds/220313_livox_mapping
rosbag play around_park_2021-09-24-11-36-03.bag
```




```
/mnt/hgfs/data/230910_slam_ds/221122_FAST_LIO_DS/Velodyne_HDL-32E$ rosbag in 20130110.bag 
path:        20130110.bag
version:     2.0
duration:    17:05s (1025s)
start:       Jan 11 2013 03:47:17.25 (1357847237.25)
end:         Jan 11 2013 04:04:23.14 (1357848263.14)
size:        7.0 GB
messages:    116818
compression: none [6709/6709 chunks]
types:       sensor_msgs/Imu         [6a62c6daae103f4ff57a132d6f95cec2]
             sensor_msgs/NavSatFix   [2d3a8cd499b9b4a0249fb98fd05cfa48]
             sensor_msgs/PointCloud2 [1158d486dd51d683ce2f1be655c3c181]
topics:      gps_fix        7186 msgs    : sensor_msgs/NavSatFix  
             gps_rtk_fix    2791 msgs    : sensor_msgs/NavSatFix  
             imu_raw       96629 msgs    : sensor_msgs/Imu        
             points_raw    10212 msgs    : sensor_msgs/PointCloud2

```