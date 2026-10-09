---
layout: page
parent: Project 0
title: First C++ Programs
nav_order: 1
---

# First C++ Programs
{: .no_toc }
Project 0 Activity
{: .fs-6 .fw-300 }

## Instructions

In this activity you will write your firt C++ programs from scratch. Complete the following:

- Write a program in ```src/1_hello_world.cpp``` so that it performs the behavior specified below.
- Write a program in ```src/2_go_blue.cpp``` so that it performs the behavior specified below.
- Write a program in ```src/3_fight_song.cpp``` so that it performs the behavior specified below.

Congrats in advance for writing your first C++ programs. Don't worry if this seems easy for now, things will speed up quickly.

- *Hint: Don't forget to ```#include <iostream>```.*
- *Hint: The escape character is ```\```.*

## Expected Behavior

The hello world program should output: 

```
Hello, World!

```

The go blue program should output:

```
When you see someone
wearing the big block "M"
say "Go Blue!"

```

The fight song program should output:

```
Now for a cheer they are here, triumphant!
Here they come with banners flying,
In stalwart step they're nighing,
With shouts of vict'ry crying,
We hurrah, hurrah, we greet you now,
Hail!

Far we their praises sing
For the glory and fame they've bro't us
Loud let the bells them ring
For here they come with banners flying
Far we their praises tell
For the glory and fame they've bro't us
Loud let the bells them ring
For here they come with banners flying
Here they come, Hurrah!

Hail! to the victors valiant
Hail! to the conqu'ring heroes
Hail! Hail! to Michigan,
the leaders and best

Hail! to the victors valiant
Hail! to the conqu'ring heroes
Hail! Hail! to Michigan,
the champions of the West!

```

Feel free to copy-paste, but you'll need to add some formatting!

## Testing

All the code for this checkpoint can be tested by running the local unit tests. Make sure to build your code first by following the [instructions here](https://robotics102.org/um-w27/project_0/#building-your-code). Run the following commands in the ```/build``` directory to run the tests for your code. Run ```ctest -R HelloWorld --output-on-failure``` to test Hello World. Run ```ctest -R GoBlue --output-on-failure``` to test Go Blue. Run ```ctest -R FightSong --output-on-failure``` the Fight Song.

If you want to run your code manually and inspect the output (for debugging or just for fun) run one of the following in the ```/build``` directory.
- Run ```./hello_world``` to run the hello world executable.
- Run ```./go_blue``` to run the go blue executable.
- Run ```./fight_song``` to run the fight song executable.
