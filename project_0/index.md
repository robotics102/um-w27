---
layout: page
title: Project 0
nav_order: 4
has_children: true
has_toc: false
---

# Pocket Calculator
{: .no_toc }
Project 0
{: .fs-6 .fw-300 }

## Teams

Project 0 will be done individually on your laptop. Feel free to chat with other students, but don't share any specifics. Refer to the syllabus for official guidelines.

## Getting Your Code

Make sure you've completed the [Computer Setup](https://robotics102.org/um-w27/workflows/computer_setup.html) guide before continuing! 

Project 0 has it's own codebase. To get your starter code download the files by clicking [here](https://robotics102.org/um-w27/assets/template_code/p0_pocket_calculator_template.zip) and extracting them, or by running the commands below in your terminal. 

* Navigate to a directory that is not already a git repository using ```cd```. If running ```git status``` outputs ```fatal: ...``` you're not in a git repository.
* Download the files from the website ```wget https://robotics102.org/um-w27/assets/template_code/p0_pocket_calculator_template.zip```.
* Unzip the files ```unzip p0_pocket_calculator_template.zip```.
* Delete the zip archive ```rm p0_pocket_calculator_template.zip```.

## Setting Up Your Repository

Setting up a GitHub repo for this project is optional. If you don't know what GitHub is, and we haven't covered it in class yet, feel free to skip this section. If you like to skip ahead, or are already familiar with git refer to the [Setting Up a Repository](https://robotics102.org/um-w27/workflows/setting_up_repo.html) guide. 

## Building Your Code

* Navigate to the root directory of your repository using ```cd```. (The root is the outermost folder of your project.)
* Configure your build system by running ```cmake -B build```. You will only need to run this command once in a given local repository. 
* Run your build system using ```cmake --build build```. You will need to re-run this every time you change your code. 

## Testing Your Code

There are two ways to test your code in this course: running unit tests and checking output, and running code and observing its behavior. In this project, all code will be graded via unit testing. However, you'll still be able to run your own code, just to see what is does and mess around. 

To run your unit tests follow the steps below. There may be more specific commands for a given checkpoint, but these apply generally.

* Navigate to the root directory of your repository using ```cd``` and make sure your code has been built, following the steps above. 
* Go down into the ```build``` directory of your repository by running ```cd build```.
* Run ```ctest --output-on-failure``` and read the output to see if all the tests for any functions you have implemented passed.

To run your code follow the steps below. There may be more specific commands for a given checkpoint, but these apply generally.

* Navigate to the root directory of your repository using ```cd``` and make sure your code has been built, following the steps above. 
* Go down into the ```build``` directory of your repository by running ```cd build```.
* Run the executable associated with your current checkpoint with ```./<executable_name>```. For example
    * ```./hello_world```.
    * ```./eliza```.

The name of the executable and the expected behavior of the program should be described in the instructions for the checkpoint. 

## Submitting Your Code

You must submit your code in order for it to be graded. 

Your code will be graded in almost exactly the same way as you tested it. The test cases you have locally will be run along with another set of test cases that have a similar structure, but different values. We call the tests you already have *public tests* and the ones we're hiding from you *private tests*. Both tests suites will be run on your code when you submit on [Autograder.io](https://autograder.io/). You will know exactly what your code did wrong if you fail public tests because you can see the output locally, but you won't know exactly what went wrong if you fail the private tests. This is intentional. It's an anti-cheating measure.

To submit your code navigate to the project on [Autograder.io](https://autograder.io/) and submit the requested files.