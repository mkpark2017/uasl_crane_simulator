UASL_crane_simulator
--------------------

It is a crane simulator for KIMM's crane project designed by UNIST ASL.
=======================================================================

Installation Instructions - Ubuntu 16.04 with ROS Kinetic
-----------------------------------------------------------------------
  ```
  $ mkdir -p ~/catkin_ws/UASL_crane_ws/src
  $ cd ~/catkin_ws/UASL_crane_ws/src
  $ git clone https://github.com/mkpark2017/uasl_crane_simulator.git
  $ cd ..
  $ rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y
  $ catkin build
  $ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
  $ source ~/.bashrc
  ```

Basic Usage
-----------

Launch the gazebo simulator
  ```
  $ roslaunch uasl_crane_gazebo testbot_world.launch
  ```

Launch the controller
  ```
  $ roslaunch uasl_crane_control testbot_control.launch
  ```

Control the crane by terminal
  ```
  $ rostopic pub -1 /testbot/joint1_position_controller/command std_msgs/Float64 "data: 1.7"
  ```
or using RQT using Message Publisher
