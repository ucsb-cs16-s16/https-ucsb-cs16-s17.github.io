---
layout: lab
num: lab00
ready: false
desc: "Getting started with C++"
assigned: 2016-09-26 08:00:00.00-7
due: 2016-09-30 12:00:00.00-7
---
<h2>Introduction</h2>

Your first lab for this week is an introduction to programming on CSIL and in the Computer Science lab.</br>
You will write your first C++ program that will print a specific text out on your computer display.
<p>Also, please note (I'll only do this this one time, on your 1st lab) that your completed lab assignment must be turned in by this FRIDAY at NOON. In fact, all of your assignments will be given to you on your Monday labs and then be expected to be submitted by the coming Friday at noon.</p>

<h3>Step 1: Create an Engineering Account</h3>

<p>To log in to the machines in the Computer Science labs, or to connect remotely, you will need a <b>College of Engineering account</b>.</p>

<p>You can create an account online at <a href="https://accounts.engr.ucsb.edu/create" target="_blank">https://accounts.engr.ucsb.edu/create</a>.</p>

<p>If you are enrolled in <i>any</i> CoE course this quarter (including CS16), you can create your account immediately. If you are not, you will need to contact the ECI Help Desk at <a href="mailto:help@engineering.ucsb.edu">help@engineering.ucsb.edu</a>.</p> 

<h3 id="step2">Step 2: Open a Terminal</h3>

<p>The first step in every assignment will be to open a <b>terminal window</b>, which will be the environment you use to write, compile, and run your programs.</p>

<p>If you are working on a machine in the Computer Science lab in Phelps 3525, go to <a href="#step2a">Step 2a</a>.</p>
<p>If you are working on your laptop and it is a Mac or Linux machine, go to <a href="#step2b">Step 2b</a>.</p>
<p>If you are working on your laptop and it is a Windows machine, go to <a href="#step2c">Step 2c</a>.</p>

<h4 id="step2a">Step 2a: Opening a Terminal on a Phelps Lab Machine</h4>

<p>Log in to the machine using your account credentials (i.e. your username and password) created in Step 1.</p>

<p>Find the "Activities" menu, which is in the top-left corner of the screen. Click on it to open the menu.</p>

<p>Next, type &ldquo;shell&rdquo; into the search box. Then click the &ldquo;Terminal&rdquo; application which appears.</p>

<p>You should now see a terminal window open. You can open more tabs or windows from the Terminal application's menu.</p>

<h4 id="step2b">Step 2b: Connecting to CSIL via SSH on Mac OS X or Linux</h4>

<p>To get started on Mac OS X or Linux, you first need to open a terminal program. This involves slightly different steps on either OS.</p>

<p>On Ubuntu (an example Linux distribution), you will first want to find the search menu. It appears at the top of the Unity bar:</p>
<img src="images/ubuntu-menu.png" width="297" alt="Ubuntu Search Menu" />

<p>Click on that icon to open the search menu. Then type &ldquo;terminal&rdquo; and click on the &ldquo;Terminal&rdquo; application which appears:</p>
<img  src="images/ubuntu-search.png" width="357" alt="Ubuntu Terminal Application" />

<p>On Mac OS X, open the &ldquo;Terminal&rdquo; application. It is found inside the <em>Applications</em> folder of your main drive, inside the <em>Utilities</em> subfolder. The icon looks like this:</p>
<img src="images/mac-terminal.png" width="79" alt="Mac OS X Terminal Icon" />

<p>You can also find it using Spotlight by typing &ldquo;terminal&rdquo; and pressing enter.</p>

<p>Once you have a terminal window open on your machine, you next need to connect to the CSIL server remotely. This will be done using a program called <em>SSH</em>.</p>

<p>Type the following command in your terminal, replacing <span class="code">USERNAME</span> with <em>your CSIL username</em>:</p>
<pre>$ ssh USERNAME@csil.cs.ucsb.edu</pre>

<p>SSH will first ask you a question which looks like this:</p>
<pre>The authenticity of host 'csil.cs.ucsb.edu (128.111.43.14)' can't be established.
RSA key fingerprint is 90:ab:6a:31:0b:81:62:25:9b:11:50:05:18:d3:1a:b5.
Are you sure you want to continue connecting (yes/no)? </pre>

<p>Type <span class="code">yes</span> to continue. It will next ask for your CSIL account password. When you type it in, nothing will show on the screen. However what you type is still being sent and once you are finished with your password, you can press enter to login.</p>

<p>You should now be remotely connected to CSIL! You can make sure by typing the following command (which will tell you what machine you are currently issuing commands to):</p>
<pre>$ hostname</pre>

<p>This should show <span class="code">csil.cs.ucsb.edu</span>. You can now do anything you could normally do in a terminal window in CSIL or the Phelps lab (except run graphical programs).</p>

<h4><em>Extra Note: Graphical Forwarding</em></h4>

<p>This is not required or necessary to use CSIL remotely, so if you are not interested, go ahead and skip this part.</p>

<p>If you have an X windows system installed you can get graphical applications running by <em>forwarding</em> X from CSIL to your machine. To do this, add the <span class="code">-X</span> option to the SSH command like this:</p>
<pre>$ ssh -X USERNAME@csil.cs.ucsb.edu</pre>

<p>X windows is almost always installed on graphical Linux, and can be installed on Mac OS X as XQuartz (which can be found at <a href="http://xquartz.macosforge.org/landing/">http://xquartz.macosforge.org/landing/</a>).</p>

<p>Doing this on the CSIL server will be very slow, since the server is shared between everyone logged in. For better performance, use one of the CSIL workstation names as your SSH destination instead. You can find a list of the workstations at <a href="http://www.cs.ucsb.edu/~don/machines/csilmap.php">http://www.cs.ucsb.edu/~don/machines/csilmap.php</a>. To login to a workstation, just replace &ldquo;CSIL&rdquo; with the name of the workstation. For example, to login to mickey:</p>
<pre>$ ssh -X USERNAME@mickey.cs.ucsb.edu</pre>

<h4 id="step2c">Step 2c: Connecting to CSIL via SSH with PuTTY</h4>

<p>To connect remotely on Windows machines, we recommend using a program called <em>PuTTY</em>. This program is a well-known and widely-used SSH client for the Windows OS.</p>

<p>First, download the program from <a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html">http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html</a>. You only need <span class="code">putty.exe</span>, but feel free to download any other programs that you want. The page includes portable versions and an version with an installer. Always make sure to download PuTTY from this site, so that you can make sure it is the correct program.</p>

<p>Then open PuTTY like you would open other programs. If you just download the <span class="code">putty.exe</span> file, you can open it from your downloads folder directly. You can also move it to any other location on your machine and open it from there. If you used the installer, open PuTTY from the Start Menu.</p>

<p>When PuTTY opens, you should see a window that looks like this:</p>
<img src="images/putty-empty.png" width="469" alt="Empty PuTTY window" />

<p>Type <em>csil.cs.ucsb.edu</em> into the box labeled &ldquo;Host Name (or IP address)&rdquo;. Leave the &ldquo;Port&rdquo; setting as 22 and leave the &ldquo;SSH&rdquo; button checked. The window should now look like this:</p>
<img src="images/putty-full.png" width="472" alt="Completed PuTTY window" />

<p>Then click on the &ldquo;Open&rdquo; button to connect. PuTTY will then show a prompt which looks like this:</p>
<img  src="images/putty-hostkey.png" width="433" alt="PuTTY Host Key Prompt" />

<p>Click &ldquo;Yes&rdquo; to accept and remember CSIL's key.</p>

<p>Once a connection is made, CSIL will ask for both your username and then your password. Type in your CSIL username and password. The password will not be shown on the screen, but the characters you type are being used. This step will look something like this (with your username instead of &ldquo;username&rdquo;):</p>
<img src="images/putty-login.png" width="677" alt="PuTTY Login Prompt" />

<p>Once you have logged in successfully, you should be connected remotely to the CSIL server. Run the following command to make sure (this command shows the full host name of the machine you are logged in to):</p>
<pre>$ hostname</pre>

<p>This command should output <span class="code">csil.cs.ucsb.edu</span>. You can now do anything in this terminal window that you could do on a CSIL machine or a Phelps lab machine, except run graphical applications.</p>

<h3 id="step3">Step 3: Create CS16 and Programming Assignment 01 Directories</h3>

<p>Now that your environment is set up, you next will need to create a directory (a folder is also called <i>directory</i> in Linux) that will contain all your work for the course. Then, inside that directory, you will need to create another directory to contain your work for this assignment.</p>

<p>To create your CS16 directory, use the <span class="code">mkdir</span> command. Type the following in the terminal and press enter:</p>
<pre>$ mkdir cs16</pre>

<p>The <span class="code">$</span> represents the terminal prompt; you won't type this character. Whenever you see it, that means that the following command is intended to be typed into the terminal window and run by pressing enter.</p>

<p>You can see list of files and directories in the current directory with <span class="code">ls</span> command. Type the following in the terminal and press enter:</p>
<pre>$ ls</pre>

<p>You should be able to see the directory you just created i.e. <span class="code">cs16</span> </p>

<p>Now move into that new CS16 directory with the <span class="code">cd</span> command as follows:</p>
<pre>$ cd cs16</pre>

<p>And create and move into a PA 01 directory:</p>
<pre>$ mkdir pa01
$ cd pa01   </pre>

<p>At any time, you can check what directory you are current in with the command <span class="code">pwd</span>. It will output the full path of the current directory. For example, if you are inside your <span class="code">pa01</span> directory, you might see:</p>
<pre>/cs/student/yourcsilname/cs16/pa01</pre>


<h3 id="step4">Step 4: Create a C++ File</h3>

<p>Now that we have a directory to contain our work for the assignment, let's start writing our code. Create a file called <span class="code">hello.cpp</span> with the <span class="code">touch</span> command:</p>
<pre>$ touch hello.cpp</pre>

<p><span class="code">hello.cpp</span> is now a completely empty file that you will use throughout the rest of the assignment to write your C++ code.</p> 


<h3 id="step5">Step 5: Edit <span class="code">hello.cpp</span></h3>

<p>To put text inside the <span class="code">hello.cpp</span> file, you will need to use a <i>text editor</i>.</p>

<p>We will describe how to use the <span class="code">gedit</span> graphical text editor, which you can use on Phelps lab machines or CSIL machines, and the <span class="code">emacs</span> editor, which you can use any time (including when connected remotely).</p>

<p>To open the <span class="code">hello.cpp</span> with <span class="code">gedit</span>, you can use the following command:</p>
<pre>$ gedit hello.cpp</pre>

<p>You can then edit the file. Make sure to save the file frequently to avoid lost work.</p>

<p>Alternatively, or if you are logged in remotely, you can edit the file with <span class="code">emacs</span> using the following command:</p>
<pre>$ emacs hello.cpp</pre>

<p>If you have never used <span class="code">emacs</span> before, a short tutorial can be found in <a href="#step5a">Step 5a</a>.</p>

<p>You are not required to use one of the two mentioned editors. If you are more comfortable with another installed editor (such as <span class="code">vim</span>), you are free to use it. However, the TAs and Professor may not be able to answer all questions about any given editor.</p>

<h4 id="step5a">Step 5a: Using <span class="code">emacs</span></h4>

<p>Once <span class="code">emacs</span> is open, you can start editing the file immediately. To move around, use the arrow keys.</p>

<p><span class="code">emacs</span> commands usually take the form <span class="code">C-x C-c</span>. This means press and hold the <span class="code">control</span> key then press the <span class="code">x</span> key, then next press and hold the <span class="code">control</span> key and press the <span class="code">c</span> key. You can also hold the <span class="code">control</span> key and then press <span class="code">x</span> and <span class="code">c</span> in succession. In contrast, the command <span class="code">C-x 1</span> means press and hold the <span class="code">control</span> key, then release the <span class="code">control</span> key and then press the <span class="code">1</span> key.</p>

<p>Some useful commands are:</p>
	<ul>
		<li><span class="code">C-x C-c</span> closes <span class="code">emacs</span></li>
		<li><span class="code">C-x C-s</span> saves the current file</li>
		<li><span class="code">C-x 1</span> closes all other panes except the current one (you can use this close the help panel)</li>
		<li><span class="code">C-g</span> at any point in a command will cancel the command</li>
		<li><span class="code">C-k</span> &ldquo;kills&rdquo; or cuts the current line, and <span class="code">C-y</span> &ldquo;yanks&rdquo; or pastes the line back at the cursor location</li>
	</ul>

<p>You can find a comprehensive beginners guide to <span class="code">emacs</span> at <a href="http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/">http://www.jesshamrick.com/2012/09/10/absolute-beginners-guide-to-emacs/</a>.</p>

<p>You can find a reference card (that prints on one page front and back) that includes a huge number of common <span class="code">emacs</span> commands at <a href="https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf">https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf</a>.</p>

<h3 id="step6">Step 6: Write the Code</h3>

<p>Now it is time to write the program! This assignment only needs to print out two lines, and nothing else. The output should look exactly as follows (no space before or after each line, except the newlines):</p>
<pre class="source">Hello, world!
CS16 Winter 2016.</pre>

<p>Start with a skeleton program that contains the necessary structure but that does not do anything:</p>
<pre class="source">#include &lt;cstdio&gt;
#include &lt;iostream&gt;

using namespace std;

int main() {
    // Your printing code should go here

    return 0;
}</pre>

<p>Go ahead and type this in to the <span class="code">hello.cpp</span> file. Alternatively, you can copy and paste it directly from this page.</p>

<p>Next, you will need to replace the comment with code to print out the expected output. Comments in C++ are lines that start with <span class="code">//</span> or text between <span class="code">/*</span> and <span class="code">*/</span>. The second type can span multiple lines.</p>

<p><em>Important note: For students familiar with Python, remember that lines starting with the <span class="code">#</span> character are not comments in C++. Rather, they are important include lines that allow your program to use the input and output functionality. Make sure to copy those lines in your program as well. Only <span class="code">//</span> or <span class="code">/*</span> create comments in C++.</em></p>

<p>To print out text to the terminal, you can use the <span class="code">cout</span> stream. To output something use the <span class="code">&lt;&lt;</span> operator as shown below:</p>
<pre>cout &lt;&lt; "This will be printed out to the terminal" &lt;&lt; endl;</pre>

<p>The <span class="code">endl</span> will cause a newline to be printed and the next print to go on the next line.</p>

<p>You can adapt this line to achieve the objective of the assignment. Remember that we need to print two lines, each with a newline at the end. You can do this with one statement or with two.</p>

<h3 id="step7">Step 7: Compile the Code</h3>

<p>Now that the code is written, we need to <em>compile</em> it. This will be done using a special program called a <em>compiler</em>.</p>

<p>Before moving on, make sure you save your code and close the text editor. The following step will be done in the terminal.</p>

<p>For C++ code we will use the <span class="code">g++</span> compiler. You can compile the <span class="code">hello.cpp</span> file into an executable called <span class="code">hello</span> with the following command:</p>
<pre>$ g++ -std=c++11 -o hello hello.cpp</pre>

<p>This will make an executable version of your code. Specifically, it will tell the compiler to take the source code file <span class="code">hello.cpp</span> and compile and link it to an executable called <span class="code">hello</span>. It also tells the compiler to use C++11, which is the C++ version we will use throughout the course. But you don't have to worry about the specifics for now.</p>

<p>If the compilation is successful, you won't see any output from the compiler. You can then use the following command to run your program:</p>
<pre>$ ./hello</pre>

<p>Which means in the current directory, represented by the <span class="code">.</span> character, run the program <span class="code">hello</span>. You should see the program output the two expected lines.</p>

<p>The other possibility is that the program does not compile successfully. In this case, you might see output that looks like:</p>
<pre class="source">hello.cpp: In function ‘int main()’:
hello.cpp:10:1: error: expected ‘;’ before ‘}’ token
 }
 ^</pre>

<p>The compiler will try to give you hints on the line (in this case 10) where the error occurs, and also what the error is (in this case a missing semicolon).</p>

<p>If you encounter an error, use the compiler hints and examine the line in question. If the compiler messsage is not sufficient to identify the error, you can search online to see when the error occurs in general. Once you have fixed the error, run the compilation command again.</p>

<!--
<p>You can find a list of common C++ errors and possible solutions at <a href="http://charlottehill.com/cpperrors.html">http://charlottehill.com/cpperrors.html</a>.</p>
-->

<h3 id="step8">Step 8: Submit</h3>

<p>Once you are satisfied that your program is correct, it is time to submit it.</p>

<p><strong>Please remember that you must submit the program to obtain any credit for the assignment; just completing the program is not enough.</strong></p>

<p>In this course we will use the <a href="https://submit.cs.ucsb.edu/">submit.cs.ucsb.edu</a> system. You can make a submission from either the command line on any CS machine, or from a browser.</p>

<p>If you don't have a submit.cs account, you will first need to create one. This can be done at <a href="https://submit.cs.ucsb.edu/form/user">https://submit.cs.ucsb.edu/form/user</a>.</p>

<p>Once you have an account created, login at <a href="https://submit.cs.ucsb.edu/session">https://submit.cs.ucsb.edu/session</a>.</p>

<p>Next, you need to join the CS16 course. Look for the &ldquo;Join Class&rdquo; link at the top of the page. It is in the top bar, seen below:</p>
<img src="images/submit-topbar.png" width="542" alt="submit.cs Top Bar" />

<p>Once you see the list of all courses, click on the &ldquo;Join CS16_w16&rdquo; button. It looks like this:</p>
<img src="images/cs16-button.png" width="144" alt="Join CS16_w16 Button" />

<p>You should then see CS16 appear on your homepage when logging in to the submit.cs system. Click on the course now.</p>

<p>Now find &ldquo;pa01&rdquo; and click on the &ldquo;Make Submission&rdquo; button. It looks like this:</p>
<img src="images/make-submission-button.png" width="154" alt="Make Submission Button" />

<p>This is the web interface for submitting your code for the assignment. You can upload your source file directly on this page. The browser will open a dialog, and you will need to navigate to the directory containing your <span class="code">hello.cpp</span> file and select it.</p>
	
<p>Once your file is uploaded, click &ldquo;Submit 1 File&rdquo;:</p>
<img src="images/submit-file-button.png" width="129" alt="Submit 1 File Button" />

<p>Once you submit, you should see a page detailing your submission. The system will automatically grade your program and will show you the results on this page after a 1 minute delay.</p>

<p>You can <em>alternatively</em> submit your code from the command line (terminal) on any CS machine, including the Phelps lab machines or the CSIL server. You can use this method when logged in remotely. To submit the the <span class="code">hello.cpp</span> file to this assignment by running the command:</p>
<pre>$ ~submit/submit -p 410 hello.cpp</pre>

<p>The program will ask you to login with your submit.cs username and password. The password will not be printed to the terminal, but what you type will be used. It will also offer the option to save your credentials, so that you do not have login next time you submit. You may choose to do this or not. After the submission succeeds, you should see the program output something like:</p>
<pre>Results will be available at: https://submit.cs.ucsb.edu/submission/xxxxx</pre>

<p>You can copy this URL and paste into a web browser to reach the same submission result page as described above.</p>


<h3 id="step9">Step 9: Check Submission Results</h3>

<p>After the 1 minute delay, the submit system will show your score and give you feedback on your submission. <em>Refresh the webpage after a minute to see this information.</em> This usually takes one of three forms:</p>

<p>A correct submission with a score of 100. This means that your program passed all the tests for this assignment. Once you get to this point, you are finished with the assignment and will receive full credit. This case will look like this:</p>
<img src="images/correct-submission.png" width="233" alt="Correct Submission." />

<p>An incorrect submission with a score of 0 to 99. This means that your program failed 1 or more of the tests. For this assignment, the system will show both the expected output and the output your program generated side-by-side so that you can see what went wrong. You will need to fix your program, and then do <a href="#step8">Step 8</a> again to re-submit. This case will look like this:</p>
<img src="images/incorrect-submission.png" width="706" alt="Incorrect Submission." />

<p>Or a submission for which compilation failed. This means that your program caused compilation errors when the system tried to compile it. You will need to interpret the compiler output and fix the errors. The system will show you the compilation command that failed along with the full error message. This case will look like this:</p>
<img src="images/compilation-failure.png" width="499" alt="Compilation Failure." />

<p>You may submit multiple times. You should submit only after local compilation does not produce any errors and runs as expected. The score of the last submission uploaded before the deadline will be used as your assignment grade.</p>

<h3 id="step10">Step 10: Done!</h3>

<p>Once your submission receives a score of 100/100, you are done with this assignment. Congratulations on completing your first C++ program!</p>

<p>If you are in the Phelps lab or in CSIL, make sure to log out of the machine before you leave. Also, make sure to close all open programs before you log out. Some programs will not work next time if they are not closed. Remember to save all your open files before you close your text editor.</p>

<p>If you are logged in remotely, you can log out using the <span class="code">exit</span> command:</p>
<pre>$ exit</pre>
