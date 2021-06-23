# px4_teleop_control
Control PX4 drone using teleop keyboard

Install PX4 drone simulation gazebo from https://github.com/PX4/PX4-Autopilot

To run PX4 drone in gazebo follow the commands

Terminal-1 : `cd PX4-Autopilot &&  no_sim=1 make px4_sitl gazebo`

Terminal-2 : 
```
cd PX4-Autopilot
source Tools/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
roslaunch gazebo_ros empty_world.launch
```

(set world and iris model)

Terminal-3 : `roslaunch mavros px4.launch fcu_url:="udp://:14540@127.0.0.1:14557"`

Then clone this repo.
run `catkin_make`

To run control the drone:
Terminal-4 : 
```
cd <to the workspace>
rosrun offb keyboard_node
```

Terminal-5 : `rosrun teleop_twist_keyboard teleop_twist_keyboard.py`

To Run the RTABMAP with this run the following command

Terminal-6 : `roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete_db_on_startrgb_topic:=/camera/rgb/image_raw depth_topic:=/camera/depth/image_raw camera_info_topic:=/camera/rgb/camera_info`




