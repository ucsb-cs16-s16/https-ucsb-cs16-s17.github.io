---
layout: lab
num: lab04
ready: true
desc: "Void Functions and Command Line Arguments"
assigned: 2017-04-26 08:00:00.00-7
due: 2017-05-02 12:00:00.00-7
---

<div markdown="1">

<h1>CS16: Programming Assignment 04</h1>
<h2>Introduction</h2>
The assignment for this week will utilize concepts of void functions, function calls-by-reference, and command line arguments. 
I will discuss void functions and calls-by-reference in class on Thursday, 4/27. These are also discussed in the textbook in Chapter sections 5.1 and 5.2.

<h2>Step 1: Getting Ready</h2>
Open a terminal window and log into the correct machine.
Change into your CS 16 directory, create a lab04 directory and change into it.
Remember that at any time, you can check what directory you are currently in with the command <b>pwd</b>.

<h2>Step 2: Create and Edit Your C++ Files</h2>
This week, you will need to create <b>2 files called change.cpp, and multiply.cpp</b>:
Each corresponds to one of the problems listed below, which make up this lab.
Each is worth 50 points and should be solved in its own file and both must be submitted for full assignment credit. 

*IMPORTANT NOTE:* This lab will be also graded for use of comments and style. See below for details. In addition, we will take points OFF if you use C++ instructions/libraries/code that either (a) was not covered in class, or (b) was found to be copied from outside sources (or each other) withoutproper citation.

<h3>CHANGE.CPP</h3>
Write a program that tells what coins to give out for any amount of change from 1 cent to 99 cents. For example, if the amount is 86 cents, the output would be something like the following:

`86 cents can be given as 3 quarters, 1 dime, 1 penny.`

Use coin denominations of 25 cents (quarters), 10 cents (dimes), and 1 cent (pennies). Do not use nickel and half-dollar coins. 

Your program should use the following function (among others):

```cpp
void compute_coins(int coin_value, int& num, int& amount_left);
// Precondition: 0 < coin_value < 100; 0 <= amount_left < 100.
// Postcondition: num has been set equal to the maximum number
// of coins of denomination coin_value cents that can be obtained
// from amount_left. Additionally, amount_left has been decreased
// by the value of the coins, that is, decreased by
// num * coin_value.
```

For example, suppose the value of the variable `amount_left` is 86. Then, after the following call: 

`compute_coins(25, number, amount_left);`

the value of `number` will be 3 and the value of `amount_left` will be 11 (because if you take 3 quarters from 86 cents, that leaves 11 cents).

Include a loop that lets the user repeat this computation for new input values until the user says he or she wants to end the program by inputting a zero (see example below).

Your program <i><b>must use</b></i> the `compute_coins` function declaration shown above. A program which does not will be awarded a score of zero, even if all tests pass.

A session should look <b><i>exactly</i></b> like the following example (including whitespace and formatting - note that there is no whitespace at the end of each of these lines and each printed line has a newline at the end), with all manners of different numbers for inputs and the output:

<img src="change.png" width="700" alt="change program example" />

Also note that the words have to match the numbers (so singulars for quarter, dime, and penny are expected as appropriate for the case). This can be trickier than it looks.

<h3>MULTIPLY.CPP</h3>
You will write a simple program that multiplies two numbers provided as command line arguments. When it is complete, the program should take exactly two command line arguments that are integers, multiply them together, and print their product on the standard output.

If the number of arguments is not exactly two (other than the program name itself), a "Usage" message is printed (see the sample runs below). <b>Hint:</b> you may want to use <code>cerr</code> instead of <code>cout</code> to output the usage message.
While cerr and cout are alike in that they direct values to standard output, we usually use cout for the standard output, but use cerr to show or report errors to the user and the system.

Here are some sample runs:

<img src="multiply.png" width="700" alt="multiply program example" />

<h2>Step 3: Create a makefile and Compile the Codes with the make Command</h2>
In order to learn another way to manage our source codes and their compilations, we will first create a makefile and put in the usual g++ commands in it. Afterwards, whenever we want to compile our programs, the Linux command is a lot shorter. The use of makefiles will reveal itself to be very useful the more complex our programs and CS projects become.

Using your text editor, create a new file called makefile and enter the following into it:

<div markdown="1">
```
all: change reverseArgs multiply

change:
	change.cpp g++ -std=c++11 change.cpp -o change

multiply:
	g++ -std=c++11 multiply.cpp -o multiply
```
</div>

Then from the Linux prompt, you can do one of two things: either issue separate compile commands for each project, like so:

`$ make change`

Or, you can issue one command that will compile all the projects mentioned in the makefile, like so:

`$ make`

If the compilation is successful, you will not see any output from the compiler. You can then run your programs, for example:

`$ ./change`

<b>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general.</b>

Remember to re-compile the relevant files after you make any changes to the C++ code.

<h2>Step 4: Submit</h2>

*BEFORE YOU SUBMIT YOUR FILES:* Make sure that you have COMMENTS in your program that would help explain what your program is doing to another person reading your program code. Also make sure that you STYLIZE your program appropriately with correct indendation and so on to additionally make it easier on others reading your code. These 2 aspect (having appropriate comments and style) will be graded for an extra 20 points beyond the automatic grade you get from submit.cs.

Once you are satisfied that your programs are correct, it is time to submit them. Login at [https://submit.cs.ucsb.edu](https://submit.cs.ucsb.edu), then navigate to “CS16_s17” and click on “lab04”. Then click “Make Submission”, and make your submission the same way as last week. Remember to submit both .cpp files.

Please remember that you must submit the programs to obtain any credit for the assignment; just completing the programs is not enough.

Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.

You can alternatively submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely. To submit the the three source files to this assignment by running the command:

`$ ~submit/submit -p 716 change.cpp multiply.cpp`

You can copy the URL shown in the output of the above and paste into a web browser to reach the submission result page.

<h2>Step 5: Check Submission Results</h2>

After the 1 minute delay, the submit system will show your score and give you feedback on your submission. Refresh the webpage after a minute to see this information.

You may submit this lab multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.

<h2>Step 6: Done!</h2>

Once your submission receives a score of 100/100, you are done with this assignment. REMEMBER that there are 20 additional points that will be scored according to your proper use of comments and styling. The total will then be normalized to 100 points again (i.e. 120 score will be 100%, 111 score is 92.5%, etc...) to grade this lab.

If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.

If you are logged in remotely, you can log out using the exit command:

`$ exit`

</div>
