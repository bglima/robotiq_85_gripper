# Robotiq_85_gripper
Common packages for the Robotiq 85 Gripper provided by Stanley Innovation

Defaults to 'ttyUSB0' and 115200 baud rate

Single gripper and left gripper (in dual gripper configuration) need to be configured as device 9 using the Robotiq User Interface
Right gripper (in dual gripper configuration) need to be configured as device 9 using the Robotiq User Interface

Start with:
```
roslaunch robotiq_85_bringup robotiq_85.launch run_test:=true
```

To see RViz description only, run:
```
roslaunch robotiq_85_description display.launch

```

If you want to run Gazebo simulation:
```
roslaunch robotiq_85_gazebo robotiq_85.launch
```

In order to test gripper controller, run:
```
rostopic pub /gripper/command trajectory_msgs/JointTrajectory "header:
  seq: 0
  stamp:
    secs: 0
    nsecs: 0
  frame_id: ''
joint_names:
- 'gripper_finger1_joint'
points:
- positions: [0.80]
  velocities: [0]
  accelerations: [0]
  effort: [0]
  time_from_start: {secs: 1.00, nsecs: 0}"
```

Position equals to 0.8 means fully closing the gripper. It opens with position equals to 0.
