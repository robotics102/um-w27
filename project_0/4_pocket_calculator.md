---
layout: page
parent: Project 0
title: Pocket Calculator
nav_order: 4
---

# Pocket Calculator
{: .no_toc }
Project 0
{: .fs-6 .fw-300 }

## Instructions

This is the full Pocket Calculator project. In this checkpoint you will implement similar functionality to last time in several functions. You will then use these functions to implement the full pocket calculator according to the specification below. Complete the following:

- Implement ```addTwoNumbers()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```subtractTwoNumbers()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```multiplyTwoNumbers()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```divideTwoNumbers()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```getNumber()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```getOperator()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Implement ```performOperation()``` in ```src/common/utils.cpp``` according to the header ```include/pocket_calculator/common/utils.h``` and the behavior specified below.
- Complete the program in ```src/6_pocket_calc.cpp``` so that it performs the pocket calculator behavior specified below.

You'll want to use the functions to your advantage!

## Expected Behavior

The functions are intended to help you implement the calculator modularly and successfully. First we will dicuss the required behavior of the functions, then we will discuss the required behavior of the calculator. Keep an eye out for how you can best leverage the functions to implement the calculator.

### Function Behavior

In general, when writing C or C++, functions will be defined and documented in a header file (a file ending in ```.h```), and then implemented in a source file ```.cpp```. The definition and documentation are *exactly* a description of the function's intented behavior. Tests can then be written to check that the function adheres to the specified behavior. 

In this course we'll occaisonally give you function definitions with documentation and ask you to implement them. You'll be graded (via testing) on whether your functions deliver the specified behavior. For now we'll take a look at the documentation together, but we'll do so with the hope that in future projects and future experiences beyond this course you'll be able to understand intended behavior by reading documentation on your own. Let's have a look in ```include/pocket_calculator/common/utils.h```:

```
/**
 * Adds two numbers and returns their sum.
 * @param  operand1 The first number to be added.
 * @param  operand2 The second number to be added.
 * @return  The sum of the arguments.
 */
float addTwoNumbers(float operand1, float operand2);
```
This is a function for performing addition. The comment is the function documentation and the line at the bottom is the function definition. The first line in the documentation is called the brief. It tells you what the function *does*. Sometimes it'll be marked ```@brief``` if there is a more long-winded description also in the documentation. Lines starting with ```@param``` describe the purpose of parameters in the function definition. Lines starting with ```@return``` tell you what the function returns. The function definition describes information like function name, return type, and parameter type. See how reading the documentation tells you what the function should do? The tests will test this expected behavior. Let's look at another function in this file.

```
/**
 * Multiplies two numbers and stores the result in the third argument.
 * @param  operand1 The first number to be multipled.
 * @param  operand2 The second number to multiply the first by.
 * @param[out]  product The product of the arguments.
 */
void multiplyTwoNumbers(float operand1, float operand2, float &product);
```

This mostly looks the same as ```addTwoNumbers()```. The difference is that this function doesn't have any return values and there is no ```@return``` tag. However, the last parameter is passed by reference and intended to capture output of the function. This behavior can be described with the ```@param[out]``` tag, which tells the user the variable is only used to capture input. The input value of these parameters don't affect the function's behavior. If the variable's input value is used inside the function and the variable is also used to capture output it can be marked ```@param[in, out]```. The ```@param[in]``` case is the default, so the ```[in]``` is usually omitted. Let's take a look at another function that makes use of these cases.

```
/**
 * Prompts the user to input an operator, stores the operator, and checks for errors with the operator.
 * @param[out]  output_stream The stream on which to prompt the user.
 * @param[in, out]  input_stream The stream on which to take user input.
 * @param[out]  operation The operator collected from the user.
 * @return  A bool, true if the operator is not one of (+, -, *, /, q), false otherwise.
 *
 * NOTE: The user is assumed to input a single character on the input stream.
 */
bool getOperator(std::ostream& output_stream, std::istream& input_stream, char &operation);
```

This function uses streams so that it can take input on stdin and write output on stdout when used with a driver program, but it can also interact with other streams for testing purposes. (You should call this function from your pocket calculator program with ```my_bool = getOperator(std::cout, std::cin, my_char);```, and you can use ```output_stream``` and ```input_stream``` inside the function just like you'd use ```std::cout``` and ```std::cin```.) Note that all the parameters are passed by reference so they need to be marked ```[out]``` (streams need to be passed by reference). The value of ```input_stream``` when it's passed to the function matters so it needs to be marked ```[in, out]```. The ```operation``` does not need to be marked ```[in]``` because it shouldn't matter what character it represents at the moment it is passed to the function. The ```NOTE:``` comment is used to specify anything unusual about the function, like particular assumptions it makes. You might also want to notice that we don't specify what the prompt to the user should look like, so don't expect unit tests to test this. (However, you might find a specific prompt valuable for implementing the full pocket calculator.)

Hopefully from what you've seen in this brief guide, you'll be able to figure out the expected behavior of the other functions just by reading their documentation. If you're unsure you understood correctly, talk to an instructor or just run the test cases!

### Calculator Behavior

This checkpoint also assumes a potentially adversarial user. The user may enter incorrect values for operands, but will not type spaces and will not type more than one character for an operand. The user also always enters numbers correctly. The program should behave as follows:

The program must always begin with the following two output, two input sequence:

Program:
```
Please type a number and press enter: 
```

User:
```
<response for number>
```

Program:
```
Please type a math operator (one of: + - * / or q to quit): 
```

User:
```
<response for operator>
```

The value in ```<response for number>``` should be stored for use in future computation. If ```<response for operator>``` is not a valid operator, the program should output ```Error: specified operation (<response for operator>) not recognized``` on stderr and then output the same prompt again on stdout. If the operator is ```q``` the program should output 

Program:
```
Calculator: quitting now

``` 

on stdout and return 0. If the operator is valid and not ```q``` the program should prompt the user for another number, as below.

Program:
```
Please type a number and press enter: 
```

User:
```
<response for another number>
```

Just as before, the value in ```<response for another number>``` should be stored for use in future computation. **The program should always behave this way when giving the number prompt**. Next the program should compute the specified computation. If this requires dividing by zero, the program should output 

Program:
```
Error: Divide by zero attempted!!!

```

on stderr and return -1. For any other computation, the program should output the result and then immediately prompt for another operator from the user:

Program:
```
<response for number> <response for operator> <response for another number> = RESULT_OF_THE_OPERATION
Please type a math operator (one of: + - * / or q to quit):
```

User:
```
<response for another operator>
```

Just as before, if ```<response for another operator>``` is not a valid operator, the program should output ```Error: specified operation (<response for another operator>) not recognized``` on stderr and then output the same prompt again on stdout. If the operator is ```q``` the program should output the quitting message and return 0. If the operator is valid and not ```q```, the program should repeat the cycle above, beginning with prompting for another number. **The program should always behave this way when giving the operator prompt**.

Program:
```
Please type a number and press enter: 
```

User
```
<response for an other another number>
```

... and so on. The program should only end via dividing by zero (and returning -1) or via the user entering ```q``` (and returning 0). Just like with the calculator operation program, you should use floats to represent numbers.

### Examples

All of that logic can get confusing, so here a two possible calculator program runs as they would appear in the terminal:

**Example scenario 1:**
```
Please type a number and press enter: 12
Please type a math operator (one of: + - * / or q to quit): /
Please type a number and press enter: 2
12 / 2 = 6
Please type a math operator (one of: + - * / or q to quit): +
Please type a number and press enter: 1
6 + 1 = 7
Please type a math operator (one of: + - * / or q to quit): l
Error: specified operation (l) not recognized
Please type a math operator (one of: + - * / or q to quit): '
Error: specified operation (') not recognized
Please type a math operator (one of: + - * / or q to quit): .
Error: specified operation (.) not recognized
Please type a math operator (one of: + - * / or q to quit): /
Please type a number and press enter: 3
7 / 3 = 2.33333
Please type a math operator (one of: + - * / or q to quit): q
Calculator: quitting now

```

**Example scenario 2:**
```
Please type a number and press enter: 30
Please type a math operator (one of: + - * / or q to quit): /
Please type a number and press enter: 15
30 / 15 = 2
Please type a math operator (one of: + - * / or q to quit): -
Please type a number and press enter: 2.5
2 - 2.5 = -0.5
Please type a math operator (one of: + - * / or q to quit): /
Please type a number and press enter: -1
-0.5 / -1 = 0.5
Please type a math operator (one of: + - * / or q to quit): +
Please type a number and press enter: 32.123
0.5 + 32.123 = 32.623
Please type a math operator (one of: + - * / or q to quit): / 
Please type a number and press enter: 0
Error: Divide by zero attempted!!!

```

Be sure your output looks like this, down to the formatting!

### Summary

The program has two possible prompts which it gives in a cycle on stdout and which respond to input in the same way every cycle:

- The number prompt ```Please type a number and press enter: ``` takes a floating point number from the user.
- The operator prompt ```Please type a math operator (one of: + - * / or q to quit): ``` takes a character from the user, outputs the quitting message if given "q", outputs the operation not recognized error if given an invalid operator, and outputs the number prompt if given a valid operator.

The program has two error messages which are given on stderr in response to user input:

- The operation not recognized error ```Error: specified operation (<response for another operator>) not recognized``` is always output after the operator prompt and followed by another operator prompt.
- The divide by zero error ```Error: Divide by zero attempted!!!``` is output immediately after a number prompt resulting in division by zero and immediately before returning -1.

The program also has an output message for computing a result and an output message for quitting, both delivered on stdout:

- The result message ```<operand 1> <operator> <operand 2> = RESULT_OF_THE_OPERATION``` is output immediately after the user has supplied enough information to run another computation.
- The quitting message ```Calculator: quitting now``` is output immediately after a "q" input on the operator prompt and immediately before returning 0.

You are encouraged to use any of the helper functions you implemented in ```src/common/utils.cpp``` to produce this behavior. This is not required, but the functions will be tested separately so you'll have to implement them, and might as well put them to good use.

## Advanced Extensions

Advanced extensions are optional features which you may complete to explore this assignment further. They are not required and are not part of your grade. Complete them in ```src/7_pocket_calc_advanced.cpp```, using the additional helper functions declared for them in ```include/pocket_calculator/common/utils.h```.

- **P0.i:** Enable the user to undo their last operation by specifying ```u``` as the operator.
- **P0.ii:** Enable the user to clear the calculator by specifying ```c``` as the operator.
- **P0.iii:** Compute the final result of the user specified equation using the Order of Operations.
- **P0.iv:** Enable the user to store and load their current set of operations through a file named ```resultcalc.txt``` such that this equation can be used across multiple program executions, by specifying ```s``` to save and ```l``` to load.

Unlike the base pocket calculator, the advanced version keeps the whole equation around instead of a single running result, so it can undo, clear, and re-evaluate it with the order of operations as you go. The operator prompt becomes ```Please type a math operator (one of: + - * / or u to undo, c to clear, s to save, l to load, q to quit): ```.

### Testing the Extensions

The test cases for these extensions exist in ```test_public.cpp``` but are disabled by default (their test suite names start with ```DISABLED_```) so they don't affect your grade on the base checkpoint. If you implement an extension and want to check your work, either remove the ```DISABLED_``` prefix from the suites you've implemented, or run all of them at once with ```./test_public --gtest_also_run_disabled_tests``` in the ```/build``` directory.

## Testing

All of the code for this checkpoint can be tested by running the local unit tests. Make sure your code is built, then run ```ctest -R PocketCalculator --output-on-failure```.

To use your pocket calculator for arithmetic or debugging, run ```./pocket_calculator``` in the ```/build``` directory. To try the advanced extensions, run ```./pocket_calculator_advanced``` instead.