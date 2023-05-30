# Publisher & Subscriber tutorial
Based on Ros2 Publisher/ Subscriber tutorial from:
https://docs.ros.org/en/foxy/Tutorials/Beginner-Client-Libraries/Writing-A-Simple-Py-Publisher-And-Subscriber.html

## Steps to:
  - create a package 
  - source publisher/subscriber python files
  - and to call the functions

## Prerequisites

  1. source /opt/ros/foxy/setup.bash
  2. cd ros2_ws
  3. cd src
    - if there are any duplicate test packages: rm -r name of package
  
## Create package
  4. ros2 pkg create --build-type ament_python name of package
  5. cd package name
  6. cd package name
  
## Import python files
  7. Import github files: the code here is specific to this repository and file names
      - wget https://github.com/Josephine2023/pubsubs/raw/main/publisher.py
      - wget https://github.com/Josephine2023/pubsubs/raw/main/subscriber.py
  8. cd .. 'should be in ros2_ws/src/<name>'
  9. Open file explorer and open up package.xml, setup.py, and setup.cfg and change dependencies
        - Make sure to add these to package.xml:
        - <exec_depend>rclpy</exec_depend>
        - <exec_depend>std_msgs</exec_depend>
  10. In setup.py add:
        - 'talker = <name of package>.<name of publisher function>:main'
        - 'listener = <name of package>.<name of subscriber function>:main'
  
## Running both files
  11. Build and run both files
      - In ros2_ws:
          - rosdep install -i --from-path src --rosdistro foxy -y
          - colcon build --packages-select <name of package>
      - In new terminal:
          - cd ros2_ws
          - source install/setup.bash
          - ros2 run name of package talker
      - In new terminal:
          - cd ros2_ws
          - source install/setup.bash
          - ros2 run name of package listener
