# Micro-ros-with-audino-due
한국인들이 마이크로로스를 쉽게 설치하기 위해 제작된 저장소

https://github.com/micro-ROS/micro_ros_arduino 참고하세요

빠른 설치

cd ~/ros2_ws/src
git clone -b $ROS_DISTRO https://github.com/micro-ROS/micro_ros_setup.git

sudo apt update && rosdep update
rosdep install --from-paths src --ignore-src -y

sudo apt-get install python3-pip


cd ..
colcon build --packages-select micro_ros_setup
source install/local_setup.bash

ros2 run micro_ros_setup create_agent_ws.sh

ros2 run micro_ros_setup build_agent.sh
source install/local_setup.bash

ros2 run micro_ros_agent micro_ros_agent serial --dev /dev/ttyACM0

