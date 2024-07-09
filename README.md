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

정상적으로 뜰 경우 not found가 뜰것 입니다. 다시 끕니다.

아두이노를 실행하고 
https://github.com/micro-ROS/micro_ros_arduino/releases
라이브러리 추가 후 

예제파일에서 퍼블리셔를 선택하여 업로드합니다.

이때 에러가 발생하면 /.arduino15/packages/arduino/hardware/sam/1.6.12 경로에서 txt를 수정합니다. 

다시 실행하여 
ros2 run micro_ros_agent micro_ros_agent serial --dev /dev/ttyACM0 

정상적으로 구독된것을 확인하고 값을 확인하시면 됩니다.
