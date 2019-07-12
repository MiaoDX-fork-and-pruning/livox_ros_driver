# Usage of Livox Mid-100 Lidar

[https://github.com/Livox-SDK/livox_ros_driver.git](https://github.com/Livox-SDK/livox_ros_driver.git)

* change `const uint32_t kPublishIntervalMs = 50; // unit:ms` to `10` for denser sampling/integration of motion

* `roslaunch livox_ros_driver livox_lidar_pc_time.launch`, pc time as timestamp
* `roslaunch livox_ros_driver livox_lidar.launch`, if w/ PPS, timestamp should be accurate enough, if w/o, timestamp starts at device start (useless)

* run with bd_list
    - 1LVDG1F006MX4R
    - roslaunch livox_ros_driver xxx.launch bd_list:="broadcast_code1&broadcast_code2&broadcast_code3"
    - roslaunch livox_ros_driver xxx.launch bd_list:="1LVDG1F006MX4R1&1LVDG1F006MX4R2&1LVDG1F006MX4R3"

* visualization
    - `roslaunch livox_ros_driver livox_rviz_only.launch`

* record bags
    - `rosbag record --all --split --duration 20`, change the params

* local and remote run
    - server side:
    - client side: source ./listen_client.sh
