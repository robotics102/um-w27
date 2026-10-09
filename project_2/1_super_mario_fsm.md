---
layout: page
parent: Project 2
title: Super Mario FSM
nav_order: 1
---

# Super Mario State Machine
{: .no_toc }
{: .fs-6 .fw-300 }

## Instructions

In this checkpoint, you will write a Finite State Machine to transition Mario between states based on events in the game environment. Complete the following:

- Implement the super mario finite state machine in the ```playGame()``` function in ```p2_bug_navigation/1_super_mario.cpp``` according to the header file ```p2_bug_navigation/super_mario/super_mario.h``` and the behavior specified below.

A good way to structure your code is to use a ```switch()``` statement to switch between code that should run in each state. Inside each case you may need another ```switch()``` statement to decide how the state should transition based on the ```currentEvent```. The Dead Mario state is handled for you.

## Expected Behavior

The program should adhere to the following behavior:

Mario has three states:
* Small Mario (represented as the `.` character or `0`)
* Regular Mario (represented as the `m` charater or `1`)
* Big Mario (represented as the `M` charater or `2`)
* Dead Mario (represented as the `x` charater or `-1`)

Mario starts off Regular Mario (`m`), and encounters events. Events are represented as `char` variables, and the whole game sequence is stored as a vector of events. Mario can encounter the following events:
* No event (an underscore, `_`): State states the same.
* A turtle (a minus sign, `-`): This makes Mario decrease to the next smallest size. If he is already Small Mario, this will terminate the game.
* A mushroom (a plus sign, `+`): This will make Mario increase to the next biggest size. If he is already Big Mario, he will stay the same size.

This is a Finite State Machine that can be visualized as follows:

![Super Mario FSM](https://robotics102.org/um-w27/assets/images/p2/super_mario_fsm.jpg){:style="width:800px;" .centered .rd-corners}

Every step taken in Small Mario state should add 0 points. Every step taken in Regular Mario state should add 1 point. Every step taken in Big Mario state should add 3 points.

## Testing

All the code for this checkpoint can be tested by running the local unit tests. To test only the functions for this checkpoint run ```ctest -R SuperMario --output-on-failure``` in the ```/build``` directory.

If you want to run the game for yourself you can run the executable ```super_mario```. Just running the executable will generate a random event sequence. If you want to run on one of the test sequences run ```./super_mario ../test/EVENT_FILE_NAME``` where "EVENT_FILE_NAME" is one of the event files in the ```/test``` directory, for example ```no_events.txt``` or ```seq01.txt```.
