---
layout: page
parent: Project 1
title: Wall Follower
nav_order: 5
---

# Wall Follower
{: .no_toc }
Project 1
{: .fs-6 .fw-300 }

## Instructions

This is the final checkpoint for the wall following project. In this checkpoint you will implement functions for adding vectors and taking the cross product between vectors. You will then use these and code from previous checkpoints to implement wall following. Complete the following:

- Implement ```vectorAdd()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement ```crossProduct()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement ```computeWallFollowerCommand()``` in ```mbot_lib/mbot_lib/behaviors.cpp``` according to the header file ```mbot_lib/mbot_lib/behaviors.h```.
- Implement wall following in ```p1_wall_follower/5_wall_follower.cpp``` so that the robot performs the behavior specified below.

The functions ```vectorAdd()``` and ```crossProduct()``` as well as functions from earlier checkpoints will come in handy for implementing ```computeWallFollowerCommand()```.

## Expected Behavior

The robot should drive parallel to the nearest obstacle and maintain a set distance between itself and the nearest obstacle. You can choose whether to wall follow to the left or the right. Be sure to demonstrate that your wall follower can follow multiple walls at different angles in sequence. Your robot should not hit a wall at any point.

## Testing

The functions ```vectorAdd()``` and ```crossProduct()``` can be tested by running the local unit tests. The function ```computeWallFollowerCommand()``` is not unit tested and is simply provided to help you structure your code so that it can be reused in project 2. To test only the functions for this checkpoint run ```ctest -R VectorAdd --output-on-failure && ctest -R CrossProduct --output-on-failure``` in the ```/build``` directory.

The robot behavior can be tested by running the ```wall_follower``` executable. 