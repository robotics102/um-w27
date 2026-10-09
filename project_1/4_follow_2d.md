---
layout: page
parent: Project 1
title: Follow Me 2D
nav_order: 4
---

# Follow Me 2D
{: .no_toc }
Project 1 Activity
{: .fs-6 .fw-300 }

## Instructions

In this activity you will implement two functions for finding the minimum value in a vector. The first will be a basic implementation and the second will ignore values of zero so that it can be used with the Lidar, which returns values of zero on bad readings. You will then implement follow me 2D by repeatedly finding the minimum value of the current Lidar scan, and then applying either bang-bang control or p-control to maintain a setpoint distance from the obstacle in the direction of the shortest Lidar scan. Complete the following:

- Implement ```findMinDist()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement ```findMinNonzeroDist()``` in ```mbot_lib/mbot_lib/utils.cpp``` according to the header file ```mbot_lib/mbot_lib/utils.h```.
- Implement follow me 2D in ```p1_wall_follower/4_follow_2d.cpp``` so that the robot performs the behavior specified below.

Feel free to look back at how you implemented follow me 1D.

- *Hint: Remember to use the appropriate function for finding the minimum distance in a real Lidar scan.*
- *Hint: Driving in polar coordinates should look familiar.*

## Expected Behavior

The robot should follow the nearest obstacle without spinning, as shown in the video below. Be sure to demonstrate that following works in multiple directions, not just the forward / backward.

<iframe style="max-width: 100%;" class="centered" width="560" height="315" src="https://www.youtube.com/embed/Dg6IREtXIS0?si=4PyFbt7oCZn5iOkq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe><br/>

## Testing

The functions can be tested by running the local unit tests. To test only the functions for this checkpoint run ```ctest -R FindMinDist --output-on-failure && ctest -R FindMinNonzeroDist --output-on-failure``` in the ```/build``` directory.

The robot behavior can be tested by running the ```follow_2d``` executable. 
