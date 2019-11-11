# CSE 15L Midterm Learning Outcomes



## Vim

Explain the relevance of vim:

> Vim is used to ensure the fastest and most efficient way to program and script any code is done. 



User vim to create a file or edit an existing file:

``` BASH
vim <filename>
```



Explain the difference between command mode and insert mode: 

> **command mode**  is a mode in vim in which a user can input commmands to modify, save, or maneuver through the file,
>
> whereas **insert** mode is a mode in which the user can append or insert actual text into the file.

Define the functionality of the movement commands:

``` VIM (Command Mode)
// MOVEMENT COMMANDS

h	// move cursor to the left

j	// move cursor down

k	// move cursor up

l 	// move cursor to the right

w	// move to the start of a word to the right

W 	// move to the start of a word to the right 
	// (including the punctuation)

e 	// move to the end of a word to right

E	// move to the end of a word to the right
	// (including the punctuation)

b	// move to the start of a word to the left

B	// move to the start of a word to the left
	// (including the punctuation)

gg 	// move to the beginning of the file

G	// move to the end of the file

0	// move to the beginning of a line

$	// move to the end of a line

^	// move to the first nonblank (character) position of the current line

(	// move to the beginning of a sentence of a line (going up)

)	// move to the beginning of a sentence of a line (going down)

{	// move to the beginning of a paragraph 

}	// move to the end of a paragraph

:{#}	// where {#} represents a number, this command allows the user to 				
	// go to line number

{#}G	// where {#} represents a number, this command allows the user to
	// go to the line number
```



Define the functionality of the insert commands:

```VIM (insert mode)
// INSERT COMMMANDS

a		// append after cursor

A		// append after end of the line

i		// insert at cursor

I		// insert at the beginning of the line

o		// insert newline below current line and enter insert mode

O		// insert newline above current line and enter insert mode

<esc> 		// (where <esc> is the escape key) 
		// exit insert mode
		
```



Define the functionality of the delete, yank, and paste commands:

```VIM (command mode)
// COMMAND MODE

p	// paste after cursor

P	// paste before cursor

yy	// yank/copy line

yw	// yank/copy a single word at cursor

y$	// yank/copy from cursor to the end of the line

y^	// yank/copy from cursor to beginning of the line

y}	// yank/copy from cursor to end of the paragraph

dd 	// delete line

dw	// delete word

d$	// delete from cursor to end of line

d^	// delete from cursor to the beginning of the line

d}	// delete from cursor to the end of paragraph

D	// delete from cursor to the end line (same as d$)

x	// cut character in cursor

X	// cut character before cursor
```

Define the functionality of the charging and replacing text commands:

```VIM command mode
~ 	// changes case of character in cursor

cw	// cuts from cursor to end of word and enters insert mode

J	// Joins current line and line below.
	
R	// enter REPLACE mode

r{char} // where {char} represents a character
```

Define the functionality of searching commands:

```VIM (command mode)
// SEARCH MODE (using '/' or '?')

n	// next occurrence

N 	// previous occurrence

/{pattern}	// search below cursor for {pattern}

?{pattern}	// search above cursor for {pattern}

:%s/{old}/{new}/	// replaces single occurrence of {old} with {new}
			// in each line

:%s/{old}/{new}/g	// replaces all occurrences of {old} with {new}
			// in each line
									
:%s/{old}/{new}/c	// replaces single occurrence of {old} with {new}
			// in each line with confirmation
```



Define the functionality of file saving, editing, and exiting commands:

```VIM (command mode)
:q 	// quit file

:q!	// override/force quit file

:w	// save/write file

:wq	// save and quit file

ZZ	// saves changes if modified, and quits file if not modified

:e	// load latest file changes menu

:f	// display filename, current line number, line count, and column number

```



Define the functionality of higher level control commands:

```VIM (command mode)
u 		// Undos last change

U 		// Undo or Restore last change 

. 		// repeat last command

{#}{command}	// (where {#} is a number and {command} is a vim command to
							// be repeated # times)
```



## Unix

Describe the Unix file hierarchy and explain the difference between absolute and relative paths. 

>The **UNIX file hierarchy** :
>
>- "/" is the root directory, where in the root directory we have subdirectories such as "/users", "/bin", "/tmp", etc. 
>
>- Inside the "/users" directory, we would have all our users listed as directories
>
>- Inside the "/users/user", we would have their specific files and directories. 
>
> 
>
>The difference between absolute and relative paths:
>
>- An **absolute** path is the complete path to a folder or directory relative to the root directory. 
>  - (ex: "/users/john/files")
>- a **relative** path is the a path to file or directory relative to the current directory 
>  - (ex: "./files")



Define the meaning of the following symbols as they relate to paths and use them to construct paths: 

```BASH 
.	// current directory

~	// home directory

/ // root directory
```



Explain the purpose of the shell and how it relates to programs and the kernel.

>A **shell** is an *interface* between the *user* and the *kernel*. (i.e. a command line interpreter)
>
>The shell relates to programs and the kernel by calling commands/programs that are executed by the kernel.



Describe the importance of spacing when executing commands with arguments. 

>Spacing allows distinguishability between commands, arguments, and options.
>
>- note: important for shell scripting (i.e. [ ... ] needs spacing in shell scripting)



Recall the three standard IO streams, their file descriptor numbers, their associated symbols, and syntax for usage with programs. 

> **Standard Input** (stdin)
>
> ```bash
> $ command < somefile
> ```
>
> **Standard Output** (stdout)
>
> ```bash
> $ command > afile1
> # or
> $ command 1> afile2
> ```
>
> **Standard Error** (stderr)
>
> ```bash
> $ command 2> afile3
> ```



Explain the difference in usage of standard IO symbols in reading from file, writing to file, appending to file, and redirecting standard IO streams to each other and to /dev/null. 

>```bash
># Reading from file
>$ file1 < file2
>
># Redirect standard output to append to a file
>$ command >> afile1
>
># Redirect standard error to append to a file
>$ command 2>> afile3
>
>```



Explain piping and apply piping to a sequence of commands.
 Compare and contrast the functionality and output of standard IO and piping. 

>**Piping** takes the output of a command and inputs it into the subsequent command:
>
>Ex:
>
>```bash
>man ls | wc
># will take the output of 'man ls' and send the output to the 'wc' comman
>```



Explain how to manage permissions using chmod and apply chmod to modify permissions for files and directories using both incremental permission changes and assigning permissions. 

>**chmod** modifies permissions for *user*, *group*, and *other*.
>
>options:
>
>​	a = all	
>
>​	u = user
>
>​	g = group
>
>​	o = other
>
>- 4 - Read - R
>- 2 - Write - W
>- 1 - Execute - X



Explain the variables PS1 and PS2 and which is displayed to the terminal, including after \<enter>. 

>PS1 and PS2 are the primary and secondary prompt strings. After pressing \enter PS2 will be 
>
>displayed because it waits for user input. [>   ]
>
>



Define the functionality of and apply common Unix commands and associated options: 

```bash
cat <file> 	# concatenate a file to the output stream

cd <PATH> 	# change diectory or go to path
		# if <PATH> is blank, default is home directory (~)

clear		# clear output stream

cp [-p -r] <source> <target>	# copy files from <source> to <target>
				# [-p] tag is to preserve the attribute of 										# the file when copying
				# [-r] tag is to recursively copy a source

date # outputs the date and time at the time of execution

diff # outputs the differences between two files

echo [-n -e] 	# prints the subsequent input with a newline
		# [-n] prints without a newline
		# -e allows you to add on \a, \b, etc backslash options

kill <PID>	# kills process of PID

ls [-a -l] 	# prints current directory's content
		# [-a] prints all files (including hidden)
		# [-l] prints files into a list format

man <command> # prints manual/instructions for bash <command>

mkdir # make a directory of the subsequential input name

mv # move a file or rename a file

ps # shows all processes in bash session

pwd # prints current directory path

read # read input (useful mainly in shell scripting)

rm [-r -d -f]	# remove file or empty directory
		# [-r] removes contents of directory or file recursively
		# [-d] attempt to remove directory
		# [-f] attempt to remove files without prompting for 				
		# confirmation, regardless of permissions. 

touch # change file access and modification times/make a new file

wc [-l]	# finds the word count for a file.
	# [-l] finds the line count of a file

```



Define the functionality of and apply Unix filtering commands:

```bash
grep [-e -i -n -r] <pattern>	# finds instances of a given <pattern>
				# [-e] specify multiple patterns or use pattern with a -
			      	# [-i] ignore cases when searching
                            	# [-n] add line number with output
                           	# [-r] look for it recursively in all files in directory

sort [-r] 	# will display contents of the file sorted
		# [-r] will sort a file in reverse

uniq 	# shows unique lines found in a file

more	# can only down and by page [more is older]

less	# can browse a file but can go up and down, by page, and search [less is better]

```



Explain the difference between wildcards:

```bash
*	# This is for strings to be filled in

?	# this can only be used for characters
```



Define the functionality of and apply common Unix compression commands and associated options: 

```bash
tar [-c -f -v -x -z] 	# tar is used to archive a group a files
			# -c creates an archive
			# -f make filename
			# -v verbose output
			# -x extract
			# filter archive to gzip


gzip [-r -d] 	# gzip is used to zip files (compress files)
		# -r is used to recursively zip a directory and contents
		# -d is used to zip a directory

gunzip [-r]	# gunzip is used to unzip a zipped file/directory
		# -r unzip for all files in the directory
```



Define the functionality of scp [-r] and recall the syntax for using scp to transfer files. 

>*scp* copies files through ssh.
>
>-r copies files through recursively in a directory
>
>```bash
>scp username@remotehost.blah:<sourcepath> <local~destinationpath> 
>
>scp -r username@remotehost.blah:<sourcepath> <local~destinationpath>
>```



## Shell Scripting

Explain the datatype of variables in Bash and how variables are created and accessed. 

>variables in bash are strings by default
>
>their values are accessed with the '$' character.



Recall and use the syntax for creating and accessing lists of variables. 

>- To create lists (array) - parantheses
>
>  ```bash
>  $ colors = (red green)
>  ```
>
>- To set a list element - square bracket 
>
>  ```bash
>  $ colors[1]=yellow
>  ```
>
>- To view a list element:
>
>  ```bash
>  $ echo ${colors[1]}
>  ```



Define and compare the difference between strong quotes, weak quotes, and back quotes. 

>Strong quotes " ", print variable contents within quotes
>
>Weak quotes ' ' , will print everything literally
>
>Back quotes `` are used to evaluate expressions 
>
>

Use and analyze the effect of quotes in combination with variables and Unix commands and programs. 

>IN MIDTERM REVIEW SLIDES
>
>



Explain the meaning and recall the usage of #! at the top of a script.  

>'#!' used to execute the script for shell, making it the first line in a shellscript.
>
>'#!/bin/sh'



Recall how to comment in a script. 

>'#' is used to make comments
>
>



Compare and contrast the different methods for executing a script: 

```bash
./scriptfilename.sh # needs execute permission, new process

.scriptfilename.sh 	# executes in current shell process

source scriptfilename.sh # executes in current shell process

bash scriptfilename.sh 	# executes in new bash process
```



Define and use the variables associated with argument position and the shift command: 

```shell
$# 	# number of arguments passed

$0 	# name of the script

$1 	# first argument

${number} 	# (where {number} is a value from 1 to and including 9)
		# subsequent arguments corresponding to number
```



Define and use common global variables:

```shell
SHELL	# current shell

DISPLAY	# used by x-windows to identify the display

HOME	# full name of your login directory

PATH  # search path for commands

MANPATH # serach path for <man> pages

PS1  # primary prompt strings 

PS2  # secondary prompt strings

USER  # user's login name

TERM  # terminal type

PWD	# currrent working directory
```



Compare and contrast the following syntaxes for performing arithmetic operations: 

```shell
expr	# express space and syntax matters, must be seperated by spaces, multiply use \* x =`expr $x +1`

let	# let "x=x + 1"
both these have more arguements and are the same
((..))	# x =$((x + 1))
```



Recall and use the syntax for common logic structures:

```shell
#test is equivalent to [ ]

#if statement 
if [ "$i" -lt 1]
then
   echo "help me"
fi

#for loop 
for i in {1..100}
do
	echo $i
done

#while loop
while [ $ind -lt 10 ]
do
	echo $ind
	ind = $((ind+1))
done

#until loop 
until [ i -gt 10]
	do
		ind = $((ind+1))
	done

#case statement 
case $animal in
	"dog") echo "woof";;
  	"cat") echo "meow";;
esac

#function
functionHelp()
{
echo "Help me"
}
```



Describe the functionality of the following control statements: 

```shell
continue	# continue used to go back into loop
	
break		# used to exit the loop
```



Explain exit codes (return codes) #? for programs and how they can be used in logic structures.

$?

Zero success

Non-Zero Failure

2 incorrect usage

127 not found

Recall the commands for performing a logic test and use the commands:

```shell
#test
test item comparator item2
[ ... ]	# spaces are important
[ item1 comparator item2 ]
```



Recognize and apply standard comparators and options for **test**:



```shell
== # to see if strings are similar

!= # to see if strings are not similar

>  #

< 

-eq # equal to 

-ne # not equal to

-lt # less than

-gt # greater than

-le # less than or equal

-ge # greater than or equal

-d # check if input is a directory

-f # check if input is not a directory

-r # check if file is readable

-w # check if file ia writable

-x # check if file is executable

-e # check if filename exists

-z # check if filename has zero length

-n # check if string is not null

-a # logical and

-o # logical or
```



Recognize and apply standard symbols to combine tests (&& and ||) .

>```bash
>if cond1 && cond2 || cond3
>if [ cond1 -a cond2 -o cond3 
>
>if [ $a -lt 5]
># these are equivalent
>```



## Debugging

Explain the importance of good debugging techniques. 

>good debugging techniques are important for saving time.
>
>



Recall that no algorithm exists that can debug all programs. 

>because debugging is not algorithmic
>
>



Explain how to apply the scientific method to debugging and how it relates to the phrase that “Science never proves theories, only disproves them.” 

>1. make a guess at what is causing the problem
>2. conduct an experiment to test the guess
>3. if result contradics guess, go back to 1
>4. if more experiments are needed go back to 2
>5. fix the problem
>
>



Order the steps to debugging and explain their purpose: 

1. Understand the system 

2. Identify the problem
3. Reproduce the problem in as few steps as possible
4. Diagnose the cause of the problem
5. Fix the problem
6. Reflect and learn from the problem and associated fix 

> Need to order



Explain which debug steps can be performed by developers and which by the average user. List common command-line debugging tools. 

>Developers can do all steps, while an average user can possibly do steps 1 - 3.
>
>valgrind and gdb are common command-line debugging tools



List the steps required to compile code for debugging, including gcc and javac, execute the compiled program, and execute the appropriate debugger. 

```bash
# C

gcc myfile.c
gdb a.out

javac myfile.java
valgrind --leak-check=yes myfile
```



Define and apply common gdb commands:

```gdb
break x = make a breakpoint at x

run = run program

continue = continue execution after program stops

step = step into a function if called

next = executes one more line, without stepping into a function

finish = finishes rest of a function if stepped into 

list = displays lines of source code around current line executed 

print = print contents of a variable

x = prints memory

where = display the current line and function and the stacks of calls that got you there.

quit = quit gdb.

```



Explain the different methods of setting breakpoints using gdb. 

>b x or break x will set breakpoints at the x line.
>
>Break main
>
>Break file.c:#
>
>



Explain how a memory leak occurs and the effect that it has on a system. 

>A memory leak occurs when memory  allocated on the heap is not deallocated
>
>



Compare the difference between creating local variables that exist only the stack and variables that are allocated to the heap and the potential of each to result in a memory leak. 

>Variables on the stack are not that likely to result in a leak, because they are released once the program finishes execution. Variables allocated on the heap are given a reserved amount of memory but are not automatically deallocated which can result in memory leaks.
>
>



Recall the correct pairing of memory allocating commands and memory deallocating commands: 

```C
malloc ↔ free // C
```

```C++
new ↔ delete // C++
```



Recall how to run valgrind from the command line. 

```bash
valgrind --leak-check=yes <myprogram> <arg1> <arg2>
```



Examine the response of the valgrind output for common errors and be able to interpret the cause the issue, what the warning means, and where in your code to look for the error. Common errors include: 

> Uninitialized Memory Read - trying to access something that hasnt been declared
>
> Invalid Write - writing to an invalid address
>
> Memory Leak 



## Integraded Development Environments (IDEs)

Explain why IDEs are used and discuss when you might not want to use an IDE. 

>IDEs are used to maxmize programming efficiency by making debugging code and executing code more convenient through different features that an IDE may posses for specific software tools and languages.
>
>One might not need to use an IDE if working with smaller scale projects.



List the components contained in an IDE.

>1. User Interface
>2. Abilities to create classes
>3. Templates for code
>4. Auto-Code Completion
>5. Syntax checking
>6. Compiling and Running features
>7. Debugger



Explain the different types of breakpoints that can be set in IntelliJ. 

>The different types of breakpoints for IntelliJ:
>
>- Line breakpoints : breaks at line
>- Method breakpoints : breaks at method
>- Exception breakpoints : breaks at an exception
>- Conditional breakpoints : breaks given a condition



## Test-Driven Development

Explain the importance of testing code and developing a testing framework.

> Testing code is important for scalability when testing different modules of a project.
>
> When developing a testing framework, one has to think about the modularity of the program.
>
> Testing helps you to ensure your program:
>
> - do what it needs to do
> - meets the requirements
> - is correct
>
> A well established testing framework will increase your development speed



Explain the stages of test-driven development and diagram the flow between stages. 

>Write a Test --> Check if Test Fails --> Write Production code --> Run All Tests --> Clean Up Code



Describe the size of a “unit” in unit testing.

> A unit is a single method or constructor.



Discuss the pros and cons of test-driven development.

> | Pros                                             | Cons                                        |
> | ------------------------------------------------ | ------------------------------------------- |
> | Increased Productivity                           | does not test the full software             |
> | Results in modular and extensible software       | requires team buy-in                        |
> | better code functionality and cleaner interfaces | same developer coding and testing a feature |
> | goal driven code                                 | time consuming                              |



List and define the components in a unit testing framework.

>The components in in a unit testing framework:
>
>- test runner 
>- test cases
>- test suites
>- test execution



Explain the difference between failures and errors during testing.

> - Failures are when your test cases fail
> - Errors are unexpected errors that occur while trying to actually run the test



Define the functionality of the following assertions from the JUnit framework and apply them in a JUnit testing framework: 

```java
assertEquals(expected, actual) // checks if actual == expected

assertTrue(b_val) // checks if b_val is true

assertFalse(b_val) // checks if b_val is false

assertNull(b_val) // checks if b_val is NULL

assertNotNull(b_val) // checks if b_val is !NULL

assertSame(object1, object2) // checks if object1 == object2
```



## make and Makefiles

Explain the utility of scripting within the build process. 

>If you have a task that needs doing repeatedly, it is best to script the task instead.



Explain the functional relationship between make and the Makefile. 

>make is a scripting command that runs the context of Makefile or rules within a Makefile



Define rules, targets, dependencies, and actions as they pertain to a Makefile and use them to create a Makefile rule with proper syntax. 

>Rules consist of the following form:
>
>```
>target: dependency1 dependency2 ...
>	action1
>	action2
>	...
>```



Describe the interpretation of targets, dependencies, and actions in a Makefile rule. 

>Targets are the names of the rules,
>
>Dependencies are the files necessary for the target
>
>Actions are the commands done in light of the rule given the dependencies.



Analyze the resulting action(s) of a Makefile for a given make {target} command and associated file timestamps. 

>Depences can name other targets in the makefile.
>
>If any dependencies are old, *make* will try to remake it.
>
>This creates chains of dependence: a file can depend on some files, which depend on other files, etc.



Explain how a default target is selected from a Makefile. 

> The default target is always the first target created in the Makefile



Explain the purpose of a .PHONY target. 

> .PHONY is used to avoid a conflict with a file of the same name as the command.



Discuss how each line is executed in make and why ; and \ are required in some instances. 

>in a makefile, *make* <target> runs a rule given the dependencies. And \ is required to help organize large dependency lines, or when creating a variable equal to many.



Recall the format of the .SUFFIX directive, associated rule, and meaning of $<, and explain how the associated rule is interpreted. 

```shell
...
.SUFFIXES .java .class
.java.class:
javac $<
...
```

>.SUFFIX defines implicit rules for 'make'. If you define a rule who target is ''.java.class', *make* takes it to be a double-suffix rule with source suffix '.java' and target suffix '.class'. In general, it tells us how to make '.class' files from '.java' files.
>
>'$<' is used as a wildcard for the dependencies



Explain how to define and use Makefile macros. Explain how a chain of dependencies can occur. 

>Makefile macros act like variables.
>
>To make a Makefile macro called CLASS, we simply type:
>
>CLASS = A.class B.class
>
>A chain of dependencies can occur when a macro includes a target, thus creating a chain.



## Software Version Control and git

Discuss the importance of a version control system in software development. 

>VCSs are important for creating large scale projects with multiple features with a large team. They are also important for:
>
>- To collaborate with other developers.
>- To recover to an earlier version of your code or a prior release if needed.
>- To improve communication on the changes to the project.



List and order the steps in a software version control workflow. 

> Software Version Control Workflow
>
> Update --> Make Changes --> Update --> Resolve Conflicts --> Commit --> Update



Explain the differences between a centralized and distributed model in a version control system. 

>A centralized model has a central server that stores all versions of a project with single feature branches that are stored on local repositories/computers.



>A distributed model is where all versions of a project are distributed amongst multiple computers.



Explain the differences between saving a record of all differences between file versions and saving snapshots of a file system. 

>Saving a record of all differences between file versions is literally keeping a log of the differences while saving snapshots of a file system saves the contents of the data at a particular moment.



Describe the method git uses to track commits. 

> Git uses a tree structure to track commits.



Define the local operations that can be performed using git and diagram how local files transition between the three areas of working directory (working tree), staging area (index), and git directory (repository). 

>you can stage files to the staging area. You commit the staged files from the staging area to the local repository. You checkout from the git directory back to your working directory. 
>
>



Define the file status tags (untracked, unmodified, modified, staged) associated with files in git and diagram how the file statuses change in response to git commands. 

Untracked - files that have not been added to git to keep track
Unmodified - files that are being tracked 

Modified - files that have been edited and tracked

Staged- files that are ready to be commited to the repository

Define the functionality of the following common git commands:

```bash
init - initalizes the git repo 

clone - clones from the remote repo

branch - lists all branches of repo and can also create new branches if specified

checkout - switches branches

reset - resets current HEAD to the specified state

add - stages changes

commit - commits staged changes

pull - fetch from and integrate with another repository or a local branch

fetch - download objects and refs from another repository

merge - merge two branches

push - push changes from local to specified branch

status - shows the status of files in the directory

diff - shows the difference between between commits, branches, etc.

log - shows the log of all commits made to repo

tag - adds a reference to a commit/version
```



