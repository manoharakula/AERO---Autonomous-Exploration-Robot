# AERO---Autonomous-Exploration-Robot


In this project, we aimed to develop an exploration robot capable of Navigating unknown challenging
environments without the help of GPS, Identifying and avoiding obstacles, and identifying objects of
interest. We used AWS robomaker-small warehouse world as the simulated challenging environment
in gazebo.

System Design
The Developed System can be described with the following modules:
1. Robot Design: The Robot was described using
the Unified Robot Description Format (URDF).
The designed robot has 2 rear wheels and a
front caster wheel. The robot is fitted with a 2D
lidar scanner(180-degree view). An RGB camera
is also attached to the robot for object detection.
2. Obstacle Detection, Mapping, and Localization:
We used a ROS package called gmaping-SLAM
to create a map of the surroundings and
estimate the pose of the robot. Gmaping-SLAM uses the odometry and sensor streams (2D
Lidar giving output in LaserScan format in ROS) to create an occupancy grid
(nav_msgs/OccupencyGrid) that can be used to navigate the environment. RVIZ is used to
visualize the generated map. In the generated map gray areas are unmapped areas, black
areas are traversable areas, pink areas are untraversable areas(obstacles) and blue areas are
buffer areas around obstacles to avoid collision with obstacles.

3. Navigation and Path Generation: We use
the ROS Navigation stack to generate paths for
the robot. ROS navigation stack takes in
information from odometry and sensor streams
and outputs velocity commands to send to a
mobile base. ROS navigation stack uses Dijkstra’s
algorithm to generate both the local and global
path for the robot. Rviz is used to specify the pose
and where the robot has to move in the generated
SLAM map.

4. Object Detection: We used YOLO V4 pre-trained on COCO dataset. It is based on a single
Convolutional Neural Network (CNN) which divides images into regions and then it predicts the
boundary boxes and probabilities of an object for each region. The robot will be able to identify
different objects in the captured footage in real-time and then perform actions based on the
detected object.

Results and Conclusion
1. The proposed system was designed and developed in ROS and simulated in Gazebo.
2. Using simulation results we can show that the robot is able to navigate through the challenging
environment using slam and ROS navigation stack.
3. Using Yolo V4-Tiny algorithm, we were able to achieve decent object detection at 5fps on a
system with an intel i5 8th generation CPU and without any GPU.
4. Using Object Detection we were able to detect moving humans and objects of interest.

Hardware:
● Large Plastic storage container as Chasis
● Raspberry pi 4B
● Arduino Mega
● L298N Motor Drivers
● 12V DC Motor 110RPM w/Encoder
● 360degree 2D RPLidar
● Raspberry Pi Camera Module 2
● Ultrasonic Sensors
Was able to implement Slam, Global & local path planning and object detection on real world robot.

Future Scope
● A robust crowd-navigation robot using Reinforcement Learning can be used.
● Development of real-world robots and performing tests in different scenarios.
● Angled 2d Lidars for better estimation of distances of objects smaller than the robot.
● Use State-Machines to give different behaviors to robots based on different scenarios.
● More robust local path planners can be used.


## Results & Demo Video

https://drive.google.com/file/d/15QXRt7GDIkjIEkE-CAzzhSP0d4vmpzm7/view

