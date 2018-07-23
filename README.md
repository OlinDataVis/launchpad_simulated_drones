# Simulated Quadrotor Drone
Have you ever just had a burning desire to fly around a simulated drone? Even if you haven't, this launchpad is for you! You'll have the opportunity to learn a bit about how to leverage ROS, a popular robot control system, Gazebo, an awesome robot simulator, and OpenCv, a powerful computer vision library, to run some neat simulations right from your computer.

## 1. Setup
Before we can jump right in to simulating this drone, we have to set a few things up.

### a. Simulated Drone Setup:
The instructions to set up ROS, Gazebo, and our beautiful quadrotor drone are all right here:
https://github.com/OlinDataVis/ardrone_gazebo

### b. Controller Setup
Of course, what's a drone without a means of controlling it? ROS's teleop_twist_keyboard makes it possible to control our drone with nothing but our keyboard. All you have to do is open your terminal and type:

    $ sudo apt-get install ros-kinetic-teleop-twist-keyboard

If you installed a version of ROS other than kinetic, just change "kinetic" to whatever version you installed. If you're interested in the official documentation, here it is: http://wiki.ros.org/teleop_twist_keyboard

## 2. Driving around your Drone
It's finally time to have some fun with this drone! Here's a cheatsheet of commands you need to get the simulation up and running (NOTE: You'll need a new terminal for each of these commands. Ctrl+Shift+T and TAB complete are the real strat here.)

    $ roscore
    $ roslaunch ardrone_vislab_gazebo ardrone_vislab.launch
    $ rostopic pub /quadrotor/ardrone/takeoff std_msgs/Empty "{}" 
    $ ROS_NAMESPACE=quadrotor rosrun teleop_twist_keyboard teleop_twist_keyboard.py
    
You should now be able to fly your drone around when you select the terminal running the teleop twist keyboard. Have some fun flying around the drone and exploring what's possible thorugh the Gazebo GUI. If the simulation breaks, don't worry. You can always restart it by restarting the terminal running "roslaunch ardrone_vislab_gazebo ardrone_vislab.launch".

## 3. How is all of this working?
So all of this stuff is really awesome, but so far we haven't talked very much about what's going on behind the scenes. 
