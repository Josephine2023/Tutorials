## This tutorial covers services and clients

# Prerequisites
  - cd ros2_ws
  - cd src
  - source /opt/ros/foxy/setup.bash

# Create package with dependencies
  - ros2 pkg create --build-type ament_python py_srvcli --dependencies rclpy example_interfaces
# Add python files
  - cd py_srvcli
  - cd py_srvcli
  - wget https://raw.githubusercontent.com/Josephine2023/Tutorials/main/service_client/client_member_function.py 
  - wget https://raw.githubusercontent.com/Josephine2023/Tutorials/main/service_client/service_member_function.py 
  
# Running server and client
  - In ros2_ws:
      - rosdep install -i --from-path src --rosdistro foxy -y
      - colcon build --packages-select py_srvcli
  - In new terminal
      - cd ros2_ws
      - source install/setup.bash
      - ros2 run py_srvcli service
  - In new terminal
      - cd ros2_ws
      - source install/setup.bash
      - ros2 run py_srvcli client 2 3

