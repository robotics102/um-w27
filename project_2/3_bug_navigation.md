---
layout: page
parent: Project 2
title: Bug Navigation
nav_order: 3
---

# Bug Navigation
{: .no_toc }
{: .fs-6 .fw-300 }

## Instructions

This is the final checkpoint for the bug navigation project. In this checkpoint you will implement a function for checking whether the straight line path to a goal pose is obstructed. You will then use this function as a transition condition between the two states in the bug navigation state machine. The first state will drive in a straight line to the goal, like you implemented in [Robot Hits the Spot](https://robotics102.org/um-w27/project_2/2_hit_the_spot.html). The second state will wall follow around an obstruction, like you implemented in [Wall Follower](https://robotics102.org/um-w27/project_1/5_wall_follower.html). Complete the following:

- Implement ```isGoalAngleObstructed()``` in ```mbot_lib/mbot_lib/behaviors.cpp``` according to the header file ```mbot_lib/mbot_lib/behaviors.h```.
- Implement bug navigation in ```p2_bug_navigation/3_bug_navigation.cpp``` so that the robot performs the behavior specified below.

For ```isGoalAngleObstructed()```, you'll want to make use of the ```findMinNonzeroDistInSlice()``` utility function which is provided for you in ```mbot_lib/mbot_lib/utils.h```. This function can be best understood using the diagram below.

![findMinNonzeroDistInSlice()](https://robotics102.org/um-w27/assets/images/p2/find_min_in_slice.png){:style="width:400px;" .centered .rd-corners}

Using it in ```isGoalAngleObstructed()``` should make checking for obstacles near the robot in the direction of the goal pose much easier. For implementing the state machine you will want to make use of all the functions in ```mbot_lib/mbot_lib/behaviors.cpp```.

## Expected Behavior

The terminal should ask for the user to input values for an (x, y, theta) goal pose. The robot should then drive in a straight line to the goal pose. When it comes within a small distance (under 1 meter) of an obstacle it should begin wall following around the obstacle. When the goal pose can again be driven to in a straight line, the robot should resume driving straight.  Finally the terminal should output the final odometry position of the robot. The final odometry pose should be very close (within 3 centimeters and 0.15 radians) to the input goal pose. A demonstration of this behavior is shown in the video below.

<iframe style="max-width: 100%;" class="centered" width="560" height="315" src="https://www.youtube.com/embed/WvheWNQ9LaU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

In your demonstration, be sure to show the input goal pose and final pose.

## Testing

There are no unit tests for this checkpoint.

The robot behavior can be tested by running the ```bug_navigation``` executable. 