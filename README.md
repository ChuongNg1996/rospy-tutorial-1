# ROSPy Tutorial
My rospy tutorial.

## Prerequisites
* Studied a least one (common) programming languague on beginner level.  

## Questions
1. Given a common programming language that you don't know, do you think that language is **LIKELY** to have:
* Variables of different types.
* If-else condition (or similar).
* For Loop.
* While Loop.
* Function Call. 
* Common programming paradigms (e.g. Object-Oriented programming).
* Containers/Data Structures.

2. If **MOST** of the answer from question 1 is **YES**, do you think they are enough to construct many (simple) robotics projects?

## Exercises 
1. Construct an Python program `exercise1.py` with a **variable x** (can be a constant or user-defined) that:
* Print "forward" if x is equal to 1. 
* Print "backward" if x is equal to 2. 
* Print "left" if x is equal to 3.
* Print "right" if x is equal to 4. 

Remember to allow permission to the file (e.g. `sudo chmod +x exercise1.py`). To run the Python program: `python exercise1.py`

2. Complete the [rospy (publisher-subscriber) tutorial](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29).
3. Combine **ex.1** and **ex.2** -> The result is displayed on **subscriber node** (by whatever method).
4. Install the [ROS keyboard](https://github.com/lrse/ros-keyboard) package.
    
    ```sh
    cd ~/catkin_ws/src
    git clone https://github.com/lrse/ros-keyboard
    cd ..
    catkin_make
    ```
    
 Then construct a pipeline such that:
 * Print "forward" on **subscriber node** if key W is pressed.
 * Print "backward" on **subscriber node** if key S is pressed.
 * Print "left" on **subscriber node** if key A is pressed.
 * Print "right" on **subscriber node** if key D is pressed.
 
 HINT: 
 * Use [rostopic](http://wiki.ros.org/rostopic) commands, such as `rostopic list` to list all the ROS topics and `rostopic echo /ros_topic` to see the messages sent to the topic.
 * Notice what **number** is displayed on the topic when a key is pressed.
 * The data type of callback functions must be correct.
