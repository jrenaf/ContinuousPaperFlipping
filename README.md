# ContinuousPaperFlipping
An optimization with two functions added

1.setup arduino 

```roscore```

```rosrun rosserial_python serial_node.py /dev/ttyACM0```

```rostopic pub soft std_msgs/Int16 xxxx --once```

xxxx from 0000 to 4949 

first two numbers(from 0 to 49) decide pressure in one of fingers while the next two(from 0 to 49) decide pressure in the other.

2.setup camera

```roslaunch usb_cam usb_cam-test.launch```

```ROS_NAMESPACE=usb_cam rosrun image_proc image_proc```

```roslaunch apriltags_ros example.launch```

```rostopic echo /tag_detections```

3.setup UR10

check connection: ```ping 192.168.1.10```

```roslaunch ur_modern_driver ur10_bringup.launch robot_ip:=192.168.1.10```

```roslaunch ur10_moveit_config ur10_moveit_planning_execution.launch limited:=true```

```roslaunch ur10_moveit_config moveit_rviz.launch config:=true ```

```rosrun a4_paper_turning page_turning_april.py```
