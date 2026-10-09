---
layout: page
title: Project 1
nav_order: 5
has_children: true
has_toc: false
---

# Wall Follower
{: .no_toc }
Project 1
{: .fs-6 .fw-300 }

## Teams

Project 1 will be done individually, while project 2 will be done in in teams of two! First get team assignments from your instructor. Then follow the instructions for **Getting Your Code** and **Setting Up Your Repository** below. Only one teammate needs to execute these steps. Once your repository is set up the other teammate can simply [clone the repository](https://hellorob.org/tutorials/git#sec_clone).

## Getting Your Code

Project 1 and project 2 use the same codebase. To get your starter code download the files by clicking [here](https://robotics102.org/um-f24/assets/template_code/p1_and_p2_template.zip) and extracting them, or by running the commands below in your terminal. 

* Navigate to a directory that is not already a git repository using ```cd```. If running ```git status``` outputs ```fatal: ...``` you're not in a git repository.
* Download the files from the website ```wget https://robotics102.org/um-f24/assets/template_code/p1_and_p2_template.zip```.
* Unzip the files ```unzip p1_and_p2_template.zip```.
* Delete the zip archive ```rm p1_and_p2_template.zip```. 

## Setting Up Your Repository

To be able to easily transfer your code between your laptop and your robot, you'll want to create a remote repository on GitHub, create a local git repository in the folder you just downloaded, make an initial commit in your local repository, and push the commit to your remote repository. Follow the [Setting Up a Repository](https://robotics102.org/um-w27/workflows/setting_up_repo.html) guide to complete these steps. 

You can refer back to the [Git Tutorial](https://hellorob.org/tutorials/git) on HelloRob to refresh on general Git and GitHub usage. 

## Building Your Code

* Navigate to the root directory of your repository using ```cd```.
* Configure your build system by running one of the two commands below. You will only need to run this command once in a given local repository. 
    * If your repository is on the robot run ```cmake -B build```. 
    * If your repository is on your laptop run ```cmake -B build -DLAPTOP=ON```.
* Run your build system using ```cmake --build build```. You will need to re-run this every time you change your code. 

## Testing Your Code

There are two ways to test your code in this course: running unit tests and checking output, and running code (usually on the robot) and observing its behavior. Make sure the unit tests for any functions you are using pass before you attempt to run code (on the robot). 

To run your unit tests follow the steps below. 

* Navigate to the root directory of your repository using ```cd``` and make sure your code has been built, following the steps above. 
* Go down into the ```build``` directory of your repository by running ```cd build```.
* Run ```ctest --output-on-failure``` and read the output to see if all the tests for any functions you have implemented passed.

To run your code (on the robot) follow the steps below.

* Navigate to the root directory of your repository using ```cd``` and make sure your code has been built, following the steps above. 
* Go down into the ```build``` directory of your repository by running ```cd build```.
* Run the executable associated with your current checkpoint with ```./<executable_name>```. For example
    * ```./drive_square```.
    * ```./follow_1d```.

The name of the executable and the expected behavior of the robot should be described in the instructions for the checkpoint. 

## Submitting Your Code

You must submit your code in order for it to be graded. 

Your code will be graded in almost exactly the same way as you tested it. The test cases you have locally will be run along with another set of test cases that have a similar structure, but different values. We call the tests you already have *public tests* and the ones we're hiding from you *private tests*. Both tests suites will be run on your code when you submit on [Autograder.io](https://autograder.io/). You will know exactly what your code did wrong if you fail public tests because you can see the output locally, but you won't know exactly what went wrong if you fail the private tests. This is intentional.

To grade the performance of your robot, we need to see of video of it working. Take a video of your robot exhibiting the expected behavior and upload it to your Umich Google Drive. Please keep the video under 30 seconds. Copy the sharing link, and paste it in the appropriate spot in your ```README.md``` file. **Make sure the sharing settings make your video available to anyone with the link**. We will hand grade your demo videos after the project deadline. You will be able to see the grades for your demo videos via the handgrading rubric on [Autograder.io](https://autograder.io/).

To submit your code navigate to the project on [Autograder.io](https://autograder.io/) and submit the requested files. 
