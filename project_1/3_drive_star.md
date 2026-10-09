---
layout: page
parent: Project 1
title: Drive Star
nav_order: 3
---

# Drive Star
{: .no_toc }
Project 1 Activity
{: .fs-6 .fw-300 }

## Instructions

In this activity you will implement functions for converting between polar and cartesian coordinates. You will then use one of these functions to drive the robot in a star shape without turning. Complete the following:

- Implement ```rayConversionCartesian()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement ```rayConversionVector()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement drive star in ```p1_wall_follower/3_drive_star.cpp``` so that the robot performs the behavior specified below.

You may want to look up or derive the angles associated with a five pointed star.

- *Hint: The sides of the star are easiest to describe in polar coordinates but ```robot.drive()``` needs cartesian coordinates.*

## Expected Behavior

The robot should drive in an equilateral five pointed star shape without spinning. Aim for a side length of around 1 meter.

[Video](https://youtube.com/shorts/BatxiM1iyVQ?feature=share)

Note that the error from driving will likely keep your shape from looking exactly like a star.

## Testing

The functions can be tested by running the local unit tests. To test only the functions for this checkpoint run ```ctest -R RayConversionCartesian --output-on-failure && ctest -R RayConversionVector --output-on-failure``` in the ```/build``` directory.

The robot behavior can be tested by running the ```drive_star``` executable. 