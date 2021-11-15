# rover-ros-software
ROS packages developed for our Rover

## ***Installation guide (for ROS melodic)***
#### **1) Install dependencies:**  
     ros-melodic-teleop-twist-keyboard  
     ros-melodic-teleop-twist-joy  
     ros-melodic-navigation  
     ros-melodic-rosserial-arduino  
     ros-melodic-ar-track-alvar  
     ros-melodic-rtabmap-ros  
     ros-melodic-librealsense2  
  
#### **2) Download the repository and compile**
  - Create a workspace:  
       `mkdir -p catkin_ws/src`  
  - Clone the repository inside src folder:  
       `cd catkin_ws/src`  
       `git clone htpps://github.com/ProjectRED-Dismi/rover-ros-software`  
  - Download `darknet_ros` package from this Drive repository into src (too big for github):  
       [https://drive.google.com/drive/folders/1Z_OqpmTszYe6-CS5gbhk7V-8SkbtjBZG?usp=sharing](url)  
  - Compile:  
       `cd ..`  
       `catkin_make  `
       
#### **3) Enable ethernet connection for communication with Arduino**  
  `sudo chmod a+rw /dev/ttyAMC0`
    
    
## ***Running on ROS***  
#### **1) Enable ROS network communication**  
  Assuming the robot as *master* and PC as *slave*:  
  Search for ethernet IP address in BOTH devices (*169.254.x.x*):  
  `ifconfig`  
  
  - On *master* device (robot):  
      `export ROS_IP=<slave-ip>`  
      
  - On *slave* device (PC):  
     `export ROS_MASTER_URI=<master-ip>:11311`  
     `export ROS_IP=<master-ip>`  
     
#### **2) Start roscore on MASTER device**  
  `roscore`
  
#### **3) Run Command Line Interface menu**  
  `cd catkin_ws`  
  `source devel/setup.bash`  
  `rosrun cli cli.py`  
  
#### **4) ENJOY! :)** 
