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
* Threading.

2. If **MOST** of the answer from question 1 is **YES**, do you think they are enough to construct many (simple) robotics projects?

## Installation
* Python. 
* [ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu).
* VS Code. Python Add-In and CoPilot Add-In are recommended.

## Exercises 
1. Construct a Python program `exercise1.py` with a **variable x** (can be a constant or user-defined) that:
* Print "forward" if x is equal to 1. 
* Print "backward" if x is equal to 2. 
* Print "left" if x is equal to 3.
* Print "right" if x is equal to 4. 

Remember to allow permission to the file (e.g. `sudo chmod +x exercise1.py`). To run the Python program: `python exercise1.py`


2. At `/usr/home/"user's name"` (`"user's name"` is arbitrary), create a ROS workspace named `catkin_ws` and a ROS package named `beginner_tutorials`. On terminal: 
   ```sh
   mkdir -p ~/catkin_ws/src
   cd ~/catkin_ws/src
   catkin_create_pkg beginner_tutorials
   cd ..
   catkin_make
   ```
   Source the `setup.bash` of the ROS workspace, either manually for each new terminal:
   ```sh
   source ~/catkin_ws/devel/setup.bash
   ```
   Or permanently:
   ```sh
   gedit ~/. bashrc
   ```
   Copy & Paste & Save `source ~/catkin_ws/devel/setup.bash` at the end of `bashrc`. Close and open new terminal. 
   
   
3. Complete the [rospy (publisher-subscriber) tutorial](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29). While two ROS nodes are running:
* Open another terminal and type `rostopic list` (More about [rostopic](http://wiki.ros.org/rostopic)), what are displayed? 
* Listen to `/chatter` ROS topic by typing `rostopic echo /chatter`
* To know the type of message of `/chatter`, type `rostopic type /chatter | rosmsg show` 
* On a new terminal, type but **do not press ENTER**: `rostopic pub -1 /chatter`  **AND** press **TAB** . What is displayed next?


4. Combine **ex.1** and **ex.3** -> The result is displayed on **subscriber node**. In particular:
* Variable x is on Publisher node.
* The Publisher node EITHER sends (1) **value of x** OR (2) result of **condition from x** (e.g. "forward", "backward", "left", "right") to the Subscriber node. Choose one method.
* The final message (e.g. "forward", "backward", "left", "right") is displayed on the Subscriber node.


5. Complete the [tutorial of making a ROS message/msg](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv) (of your own), ignore the service/srv file for now. Also, create a new ROS package (in `~/catkin_ws/src`) with different name than `beginner_tutorials` (which is the same as ex.2), called `msg_tutorials`.


6. Try to apply created ROS message of `msg_tutorials` to `beginner_tutorials`. In particular:
* Add the dependency of `msg_tutorials` to `CMakeLists.txt`. Open `CMakeLists.txt` of `beginner_tutorials` package and:
** asdad



7. Install the [ROS keyboard](https://github.com/lrse/ros-keyboard) package.
    
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


8. Install the [ROS joy](https://github.com/ros-drivers/joystick_drivers) package
    ```sh
    sudo apt-get install libusb-dev
    cd ~/catkin_ws/src
    git clone https://github.com/ros-drivers/joystick_drivers -b melodic-devel
    cd ..
    catkin_make
    ```
    To [use the package](http://wiki.ros.org/joy/Tutorials/ConfiguringALinuxJoystick).
