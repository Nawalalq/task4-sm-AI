# task4-sm-AI
Use Turtlebot3 with SLAM approach to create and save a map
# command link:

https://emanual.robotis.com/docs/en/platform/turtlebot3/slam_simulation/

# 1-Install ROS on Remote PC

$ sudo apt-get update

$ sudo apt-get upgrade

$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh

$ chmod 755 ./install_ros_kinetic.sh 

$ bash ./install_ros_kinetic.sh

# 2-Install Dependent ROS Packages

$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
  # 3-Install TurtleBot3 Packages

$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3

# 4-Set TurtleBot3 Model Name

Set the default TURTLEBOT3_MODEL name to your model. Enter the below command to a terminal.

    In case of TurtleBot3 Burger

    $ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc

    In case of TurtleBot3 Waffle Pi

    $ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
    
  # 5- Gazebo simulation:
  1-Install Simulation Package:
  
  $ cd ~/catkin_ws/src/
  
$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

$ cd ~/catkin_ws && catkin_make
# 6- TurtleBot3 World:

$ export TURTLEBOT3_MODEL=waffle

$ roslaunch turtlebot3_gazebo turtlebot3_world.laun
# Run SLAM Node:

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
# Run Teleoperation Node:

$ export TURTLEBOT3_MODEL=burger

$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
