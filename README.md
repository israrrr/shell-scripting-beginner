# Bash Shell Scripting for Automation: A Beginner's Guide

Welcome to the "Bash Shell Scripting for Automation" GitHub repository! This guide is designed for beginners who want to learn how to automate tasks using Bash shell scripting. Whether you're looking to streamline your workflow, manage repetitive tasks, or simply improve your command-line skills, this repository has you covered.


<!----------------------------------------------------------------------------TABLE OF CONTENT SECTION------------------------------------------------------------------------>

## Table of Contents

- [Bash Shell Scripting for Automation: A Beginner's Guide](#bash-shell-scripting-for-automation-a-beginners-guide)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Setting Up Your Environment](#setting-up-your-environment)
  - [Basic Concepts](#basic-concepts)
    - [What is a Shell Script?](#what-is-a-shell-script)
    - [Hello World Script](#hello-world-script)
    - [Running Your First Script](#running-your-first-script)
  - [Core Concepts](#core-concepts)
    - [Variables](#variables)
    - [Arrays](#arrays)
    - [Conditionals](#conditionals)
    - [Case](#case)
    - [Logical-Operators](#logical-operators)
    - [Loops](#loops)
      - [For Loop](#for-loop)
      - [While Loop](#while-loop)
      - [Until Loop](#until-loop)
      - [Infinite Loop](#infinite-loop)
      - [Using `break` command in a loop.](#using-break-command-in-a-loop)
      - [Using `continue` command in a loop](#using-continue-command-in-a-loop)
    - [Functions](#functions)
    - [Arguments](#arguments)
  - [Advanced Topics](#advanced-topics)
    - [Working with Files](#working-with-files)
    - [Error Handling](#error-handling)
    - [Scheduling Scripts with Cron](#scheduling-scripts-with-cron)
    - [Script name](#script-name)
    - [Overwriting](#overwriting)
    - [Connectivity check](#connectivity-check)
    - [Random number generator](#random-number-generator)
    - [User Check](#user-check)
    - [Debugging](#debugging)
  - [Projects](#projects)
    - [Monitoring FREE RAM space](#monitoring-free-ram-space)
    - [Monitoring the free filesystem space disk](#monitoring-the-free-filesystem-space-disk)
    - [System Monitoring Script](#system-monitoring-script)
    - [Archive Older Logs](#archive-older-logs)
    - [User Management - 1](#user-management---1)
    - [User Management - 2](#user-management---2)
  - [Resources](#resources)


<!--INTRODUCTION SECTION-->

## Introduction

`Bash` (Bourne Again Shell) is a powerful scripting language that is commonly used on Unix-based systems, including Linux and macOS. With Bash scripting, you can automate tasks, manage system operations, and handle complex workflows with ease. This guide will take you from the basics to more advanced scripting techniques, providing clear examples and practical exercises along the way.

## Getting Started

### Prerequisites

Before you begin, ensure you have the following:

- Basic understanding of the command line interface (CLI)
- A Unix-based operating system (Linux, macOS, or Windows Subsystem for Linux)

### Setting Up Your Environment

1. **Open your terminal:** This is where you will write and execute your Bash scripts.
2. **Choose a text editor:** You can use any text editor, such as `vim`, `nano`, or a graphical editor like VSCode or Sublime Text.
3. **Check Bash version:** Make sure you have Bash installed by running `bash --version` in your terminal. The output should display the version number of your Bash installation.


<!--BASIC CONCEPTS SECTION-->

## Basic Concepts

### What is a Shell Script?

A shell script is a text file that contains a sequence of commands for a Unix-based operating system to execute. These scripts are used to automate repetitive tasks and can range from simple to complex operations.

### Hello World Script

The simplest Bash script prints "Hello, World!" to the terminal.

```bash
#!/bin/bash
echo "Hello, World!"
```

### Running Your First Script

To run your first Bash script, follow these steps:

1. **Create the script:** Save the above code in a file named `hello_world.sh`.
2. **Make the script executable:** Run `chmod +x hello_world.sh` in your terminal to make the script executable.
3. **Execute the script:** Run `./hello_world.sh` to see the output.


<!-------------------------------------------------------------------------CORE CONCEPTS SECTION------------------------------------------------------------------------------>

## Core Concepts

<!--VARIABLES-->

### Variables

Variables store data that can be used and manipulated within your script. They are essential for creating dynamic and flexible scripts.

1. Assigning Variable.

```bash
#!/bin/bash
name="KALI"
age=25

#To execute variable use "$" sign

echo "My name is $name and age is $age."
```

2. Re-assigning variable.

```bash
#!/bin/bash
name="LIKA"

echo "My name is $name."
```

3. Usibg Linux command as an output value for variable.

```bash
#!/bin/bash
Hostname=(hostname)

echo "Name of this machine is $Hostname."
```
```bash
#!/bin/bash
ID=$(id)

echo "ID of this machine is $ID."
```

4. Constant variable (never changing value).

```bash
#Use "readonly" before assigning variable

#!/bin/bash
readonly College=Xavier

echo "My college name is $College."

#Trying to reassign value

College=Furgusson

echo "My college is $College."

#It will show an error line.
```

<!--ARRAYS-->

### Arrays

1. Defining and calling an array.

```bash
#Arrays should be space saperated

#!/bin/bash
myArray=(1 20 30.5 KALI "Hello World!")

#Calling an array (Based on Index - Index counting start from zero)

echo "Value in 3rd index is ${myArray[2]}"

echo "All the values in the array are ${myArray[*]}"
```

2. How to get the length of array (use "#")

```bash
#!/bin/bash
myArray=(1 20 30.5 KALI "Hello World!")

echo "Number of values/length of array is ${#myArray[*]}."
```

3. How to get specific values in array (use ":").

```bash
#!/bin/bash
myArray=(1 20 30.5 KALI "Hello World!")

echo "Values from index 2-3 is ${myArray[*]:2:2}"

#In this line first ":2" is representing the staring index counting and second ":2" is representing the number of index you want to go.
```

4. How to update an array with new values.

```bash
#!/bin/bash
myArray+=(New 30 40)

echo "Values of new array are ${myArray[*]}."
```

5. Arrays KEY-VALUE

```bash
#!/bin/bash
declare -A newArray
newArray=( [name]=KALI [age]=25 [city]=Laddakh )

echo "My name is ${newArray[name]}."
echo "My age is ${newArray[age]}."
echo "My city is ${newArray[city]}."
```

6. Length of string.

```bash
#!/bin/bash
myVar="Hello KALI, how are you?"

#Use "#" before variable

myVarLength=${#myVar}
echo "Length of my string is $myVarLength."
```

7. All upper case.
```bash
#!/bin/bash
myVar="Hello KALI, how are you?"

echo "Upper case is ${myVar^^}"
``` 

8. All lower case.

```bash
#!/bin/bash
myVar="Hello KALI, how are you?"

echo "Lower casr is ${myVar,,}"
```

9.  Replacing a string.

```bash
#Remove by first typing the target string followed by the string you want to write.

#!/bin/bash
newVar=${myVar/KALI/LIKA}

echo "New Variable is $newVar."
```

10. Slicing a string.

```bash
#!/bin/bash
myVar="Hello KALI, how are you?"

echo "After slice ${myVar:5:5}."
```

11. Taking input from users.

```bash
#Use "read -p" command to write your dialogue for user.
#Here "NAME" is variable (Whatever command user will input).

#!/bin/bash
read -p "What is your name?-" NAME

echo "Your name is $NAME."
```

12. Mathematical Calculations

```bash
#Use "let" command for mathametical calculations.
#!/bin/bash
x=10
y=2

#First method
let mul=$x*$y
echo "Multiplication is $mul"

let sum=$x+$y
echo "Sum is $sum"

#Second method
echo "Substration is $(($x-$y))"
```

<!--CONDITIONALS-->

### Conditionals

Conditionals allow your script to make decisions based on certain conditions. The `if` statement is used to execute code only if a certain condition is met.

```bash
#!/bin/bash
if [ "$1" -gt 10 ]; then
  echo "The number is greater than 10."
else
  echo "The number is 10 or less."
fi
```

1. Taking input from user for conditional statements.

```bash
#Use double "[[ $X ]]" and proper spacing

#!/bin/bash
read -p "Enter your marks:" marks


if [[ $marks -gt 40 ]]
then 
 echo "You are pass."
else
 echo "You are fail."
fi
```

2. Operator table and symbols.

| Operator Name         | Symbol   |
| --------------------- | -------- |
| Equal                 | -eq / == |
| Greater Than Equal To | -ge      |
| Less Than Equal To    | -le      |
| Not Equal             | -ne / != |
| Greater Than          | -gt      |
| Less Than             | -lt      |


3. Multiple conditions

```bash
#Use "elif" for multiple conditions

#!/bin/bash
read -p "Enter your marks:" marks

#Use double "[[ $X ]]" and proper spacing

if [[ $marks -ge 80 ]]
then
 echo "1st Division Pass."
elif [[ $marks -ge 60 ]]
then
 echo "2nd Division Pass."
elif [[ $marks -ge 40 ]]
then
 echo "3rd Division Pass."
else
 echo "You are FAIL."
fi
```

<!--CASE-->

### Case
The `case` command in Linux is used for pattern matching and is a good alternative to multiple `if-elif-else` statements when there are several possible conditions to handle.

```bash
#Using case command for multiple options.

#!/bin/bash
echo "Provide an option."
echo "a for print date."
echo "b for list of scripts."
echo "c to check rhe current location."

read choice

case $choice in
 a)date;;
 b)ls;;
 c)pwd;;
 *)echo "Please provide a valid value"
esac
```

<!--LOGICAL OPERATORS-->

### Logical-Operators
1. `AND` condition1 "&&" condition2 both are `true` otherwise `false`.

```bash
#!/bin/bash
read -p "What is your age?" age

read -p "Nationality: " country
if [[ $age -ge 18 ]] && [[ $country == India ]]
then
 echo "You can vote."
else
 echo "You can't vote."
fi
```

2. `OR` condition1 "||" condition2 either of them is `true` then `true`.

```bash
#!/bin/bash
read -p "What is your age?" age

read -p "Nationality: " country
if [[ $age -ge 18 ]] || [[ $country == India ]]
then
 echo "You can vote."
else
 echo "You can't vote."
fi
```

3. Combination of Logical Operators.

```bash
#!/bin/bash
read -p "What is your age?" age

[[ $age -ge 18 ]] && echo "You are adult." || echo "You are Minor."
```

<!--LOOPS-->
### Loops

Loops enable you to execute a block of code multiple times. The `for` loop is one of the most common loops in Bash scripting.

```bash
#!/bin/bash
for i in {1..5}; do
  echo "Iteration $i"
done
```

<!--FOR-->
#### For Loop
1. Dealing with names and numbers

```bash
#!/bin/bash
for i in 1 2 3 4 5 6 7 8 9 10
do
 echo "Number is $i"
done
```

```bash
#!/bin/bash
for name in Ina Mina Dika
do
 echo "Name is $name"
done
```

2. For range of numbers

```bash
#Use "{..}"

#!/bin/bash
for i in {1..20}
do
 echo "The new numbers are $i"
 sleep 3s
done
```

3. Use `nohup` command to run your scriot in background, let you to work on comand line.
`nohup ./script.sh &` here `script.sh` is your target script.

4. Using for loop to get values frome a `file.txt`.

```bash
#Specify the exact location of file.

#!/bin/bash
FILE=/home/kali/myscripts/names.txt

for name in $(cat $FILE)
do
 echo "Name is $name"
done
```

5. Using for loop in array.

```bash
#!/bin/bash
myArray=(1 2 3 4 5 Hello "Pillu")

length=${#myArray[*]}

for (( i=0;i<$length;i++ ))
do
 echo "Value of array is ${myArray[$i]}"
done
```

<!--WHILE-->
#### While Loop

A `while` loop executes a block of code as long as a specified condition is true. It is useful when the number of iterations is not known in advance and depends on dynamic conditions.

1. Loop runs till conditions are meeting.

```bash
#!/bin/bash
count=0
num=10

while [[ $count -le $num ]]
do
 echo "Value of count variable is $count"
 let count++
done
```

<!--UNTIL-->
#### Until Loop

An `until` loop is similar to a `while` loop, but it executes the block of code until a specified condition becomes true. It runs as long as the condition is false.

1. Increasing order counting use `++`.

```bash
#!/bin/bash
count=0
num=10

while [[ $count -le $num ]]
do
 echo "Value of count variable is $count"
 let count++
done
```

2. Reverse counting use `--`.

```bash
#!/bin/bash
a=10

until [[ $a -eq 1 ]]
do
 echo "Value of a is $a"
 let a--
done
```

<!--INFINITE-->
#### Infinite Loop

An infinite loop runs indefinitely and only stops when externally interrupted or a break statement is encountered. It can be created using `while true` or `for ((;;))` in shell scripts.

1. Infinite loop with 1 second `sleep` cycle.

```bash
#!/bin/bash
while true
do
 echo "KALI"
 sleep 1s
done
```

2. Infinte for loop

```bash
#!/bin/bash
for (( ;; ))
do
 echo "TILUA"
 sleep 0.5s
done
```

#### Using `break` command in a loop.
```bash
#!/bin/bash


#We just need to confirm in a given no. if present or not

number=6

for i in 1 2 3 4 5 6 7 8 9
do
 #Break the loop if number found
 if [[ $number -eq $i ]]
 then
  echo "$number is found"
  break
 fi
 echo "Number is $i"
done
```

#### Using `continue` command in a loop

```bash
#!/bin/bash

#Suppose we only need to print odd numbers

for i in 1 2 3 4 5 6 7 8 9 10
do
#"% " is modulation (even number divided by 2 will end to zero)
 let r=$i%2
 if [[ $r -eq 0 ]]
 then
  continue
 fi
 echo "Odd number is $i"
done
```

<!--FUNCTIONS-->
### Functions

1. Making and calling a function

```bash
#!/bin/bash

#Method1

function WelcomeNote { echo "Welcome SIR"
}

#How to call function

WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote

#Method2

WelcomeNote() { echo "Welcome again SIR"
}
 
#How to call function

WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote
WelcomeNote
```

Functions help you organize your code into reusable blocks, making your scripts more modular and easier to manage.

2. Using arguments in functions

```bash
#!/bin/bash
# $1 and $2 are arguments

addition() {
 local num1=$1
 local num2=$2
 let sum=$num1+$num2
echo "Sum of $num1 and $num2 is $sum"
}

#Calling function with "12" and "13" as arguments "$1" and "$2" respectively.

addition 12 13
```

3. Accessing the arguments.

```bash
#!/bin/bash
#For debugging use "set -x" in the start of script
set -x


#Use "exit 1" command to stop whole process, when there is not argument provided.

if [[ $# -eq 0 ]]
then
 echo "Provide arguments"
 exit 1
fi

echo "First argument is $1"
echo "Second argument is $2"

#Porvide values while calling script

echo "All the arguments are - $@"
echo "Number of arguments are - $#"
```

4. FOR loop to access the values from arguments.

```bash
#!/bin/bash
for filename in $@
do
 echo "Copying file - $filename"
done
```

<!--ARGUMENTS-->
### Arguments

1. Accessing the arguments

```bash
#!/bin/bash

#For debugging use "set -x" in the start of script
set -x

#Use "exit" command to stop whole process

if [[ $# -eq 0 ]]
then
 echo "Provide arguments"
 exit 1
fi

echo "First argument is $1"
echo "Second argument is $2"

#Porvide value while calling script

echo "All the arguments are - $@"
echo "Number of arguments are - $#"

#FOR loop yo access the values from arguments
for filename in $@
do
 echo "Copying file - $filename"
done
```

2. Using `shift` command to give rest part as single argument.

```bash
#!/bin/bash

#To create a user, provide username and description

echo "Creating user"
echo "Username is $1"

shift
echo "Description is $@"
```

<!----------------------------------------------------------------------------ADVANCED TOPICS--------------------------------------------------------------------------------->

## Advanced Topics

### Working with Files

Learn how to create, read, and manipulate files within your scripts. This is crucial for tasks such as logging, configuration management, and data processing.

```bash
#!/bin/bash
#To read content from a file
while read myVar
do
 echo "Value from file is $myVar"
done < /home/kali/myscripts/names.txt
```

```bash
#!/bin/bash

# Create a file and write to it
echo "This is a test file." > testfile.txt

# Read from the file
cat testfile.txt
```

<!--EXIT-->
### Error Handling

Implement error handling to make your scripts more robust and reliable. This involves checking for errors and taking appropriate actions when they occur.

```bash
#!/bin/bash
if ! [ -d "/my_directory" ]; then
  echo "Directory not found!"
  exit 1
fi
```
<!--CRONTAB-->
### Scheduling Scripts with Cron

Automate your scripts to run at specified intervals using cron jobs. This is useful for tasks like backups, updates, and periodic maintenance.

To schedule a script to run every day at midnight, add the following line to your crontab (edit with `crontab -e`):

Using `crontab` to automate the tasks.

Run your `crontab` command in command line.

```bash
#For scheduling only one time, use "AT"

#at 12:09 PM
# <your_command>
#ctrl+D

#"atq" to check scheduled job
#"atrm<id>" to remove the schedule


#Repetative tasks by crontab
#To check the existing tasks use "crontab -l"
#To add new task use "crontab -e"

# * * * * * cd /home/kali/myscript && ./script.sh

#1st * - day of week (0-6)(Sunday=0)
#2nd * - month (1-12)
#3rd * - day of month (1-31)
#4th * - hour (0-23)
#5th * - minute (0-59)

#Use link "crontab guru" to easily understand.
```

```bash
#Run this command in command prompt
0 0 * * * /path/to/your/script.sh
```

### Script name

Checking name of your script.

```bash
#!/bin/bash

echo "Name of the script is ${0}"
```

### Overwriting

Redirecting the `ping` command.

```bash
#!/bin/bash

#Overwrite ">"
#Add ">>"
ping -c 1 www.google.com > redirect.log

ping -c 1 www.youtube.com >> redirect.log
```

### Connectivity check

1. Using `ping` command to check your connectivity.

```bash
#!/bin/bash

read -p "Which site you want to check?" site

#Using "/dev/null" will dump the output

ping -c 1 $site &> /dev/null

#Checking if the last command is executed or not.

#If "$?" is euqal to 0 then the command is successfully executed and if it is 1 then not executed

if [[ $? -eq 0 ]]
then
 echo "Successfully connected to $site"
else
 echo "Unable to connect to $site"
fi
```

### Random number generator

Creating a random number between 1 to 6 (LUDO)

```bash
#!/bin/bash
NO=$(( $RANDOM % 6 + 1 ))
echo "Number is $NO"
```

### User Check

Checking if the user is root or not.

```bash
#!/bin/bash
if [[ $UID -eq 0 ]]
then
 echo "It is a root user."
else
 echo "It is not a root user."
fi
```

### Debugging

Cheching is any error present in command.
```bash
#!/bin/bash

#Use "set -e" to exit from the script when there is error
set -e

pwd
date
cd /root
ls
```

<!---------------------------------------------------------------------------------PROJECTS----------------------------------------------------------------------------------->
## Projects

**NOTE:** Try running each of your commands separately on the command line to make sure everything is operating as it should.

### Monitoring FREE RAM space

Automate your computer to timely check the free RAM space and alter you at its threshold.

```bash
#!/bin/bash

#"TH" is threshold
FreeSpace=$(free -mt | grep "Total" | awk '{print $4}')
TH=500

#Mail address for alert
TO=abc123@mail.com

if [[ $Free_Space -lt $TH ]]
then
  echo "Warning, RAM is running low - $Free_Space M" | mail -s "Disk Space ALert!" $TO 
else
  echo "RAM space is sufficient - $Free_Space M"
fi
```
Use `crontab` to automate your tasks.


### Monitoring the free filesystem space disk
```bash
#!/bin/bash
FU=$(df -H | egrep -v "Filesystem|tmpfs" | grep "sda1" | awk '{print $5}' | tr -d %
)

#Sending mail alert
TO=xyz123@mail.com

if [[ $FU -ge 20 ]]
then
 echo "Warning, disk space is running low - $FU %" | mail -s "Disk Space ALert!" $TO 
else
 echo "Disk Space is sufficient."
fi

```
Use `crontab` to automate your task.


### System Monitoring Script

Monitor system resources like CPU and memory usage.

```bash
#!/bin/bash
echo "CPU Usage:"
top -b -n1 | grep "Cpu(s)"

echo "Memory Usage:"
free -mth
```
Use `crontab` to automate your task.


### Archive Older Logs

Larger size older log files that are needed to be archived'

```bash
#Vairables
BASE="/home/kali/dir/file"
DAYS=30
DEPTH=1
RUN=0

#Check if the directory is present or not
if [[ ! -d $BASE ]]
then
 echo "Directory does not exist: $BASE"
 exit 1
fi

#Create "archive" folder if not present
if [[ ! -d $BASE/archive ]]
then
 mkdir $BASE/archive
fi

#Find the list of files larger than 20MB
for i in 'find $BASE -maxdepth $DEPTH -type f -size +20M'
do
if [[ $RUN -eq 0 ]]
then
  echo "[$(date"+%Y-%m-%d %H:%M:%S")] archiving $i ==> $BASE/archive"
  gzip $i || exit 1
  mv $i.gz $BASE/archive || exit 1
fi
done
```
Use `crontab` to automate your script.


### User Management - 1

Creating local user.

```bash
#!/bin/bash

set -x

# Script should be executed with sudo/root access
if [[ "${UID}" -ne 0 ]]
then
  echo "Please run with sudo or root."
  exit 1
fi

# User should provide at least one argument as username
if [[ "${#}" -lt 1 ]]
then
  echo "Usage: ${0} USER_NAME [COMMENT]..."
  echo "Create a user with name USER_NAME and comments field of the rest of the arguments."
  exit 1
fi

# Store 1st argument as username
USER_NAME="${1}"
echo "$USER_NAME"

# In case of more than one argument, store it as comments
shift
COMMENT="${@}"
# echo $COMMENT

# Create a password
PASSWORD=$(date +%s%N | sha256sum | head -c32)
echo "$PASSWORD"

# Create the user
useradd -c "$COMMENT" -m "${USER_NAME}"
# Check if user is successfully created or not
if [[ $? -ne 0 ]]
then
  echo "The account is not created."
  exit 1
fi

# Set the password for the user
echo "${USER_NAME}:${PASSWORD}" | chpasswd

# Check if password is successfully set or not
if [[ $? -ne 0 ]]
then
  echo "Password is not set."
  exit 1
fi

# Force password change on first login
passwd -e "${USER_NAME}"

# Display the username, password, and the host where the user was created
echo
echo "Username: ${USER_NAME}"
echo
echo "Password: ${PASSWORD}"
echo
echo $(hostname)
```

### User Management - 2

Create a script to manage users, including adding, deleting, and modifying users.
```bash
#!/bin/bash

# Function to display the menu
display_menu() {
  echo "User Management Script"
  echo "1. Add User"
  echo "2. Delete User"
  echo "3. Modify User"
  echo "4. Exit"
}

# Function to add a user
add_user() {
  read -p "Enter username: " username
  sudo useradd $username
  echo "User $username added."
}

# Function to delete a user
delete_user() {
  read -p "Enter username: " username
  sudo userdel $username
  echo "User $username deleted."
}

# Function to modify a user
modify_user() {
  read -p "Enter username: " username
  read -p "Enter new shell (e.g., /bin/bash): " shell
  sudo usermod -s $shell $username
  echo "User $username modified."
}

# Main script loop
while true; do
  display_menu
  read -p "Choose an option: " choice

  case $choice in
    1) add_user ;;
    2) delete_user ;;
    3) modify_user ;;
    4) exit 0 ;;
    *) echo "Invalid option, please try again." ;;
  esac
done
```

***NOTE:*** Don't forget to create `name.txt` file and `test.csv` file while using some scripts.

1. `name.txt` file

| #   | Name    |
| --- | ------- |
| 1   | Ina     |
| 2   | Mina    |
| 3   | Dika    |
| 4   | Neel    |
| 5   | Nitin   |
| 6   | Mukesh  |
| 7   | Tika    |
| 8   | Malkhan |
| 9   | Tillu   |

2. `test.csv` file

| ID  | Name    | Age |
| --- | ------- | --- |
| 01  | Tika    | 29  |
| 02  | Mlakhal | 28  |
| 03  | Tillu   | 25  |
| 04  | Neel    | 34  |
| 05  | Nitin   | 32  |
| 06  | Mukesh  | 30  |
| 07  | Ina     | 24  |
| 08  | Mina    | 26  |
| 09  | Dika    | 28  |

```bash
#Use this fomat for making a .csv file
id,name,age
01,Tika,29
02,Mlakhal,28
03,Tillu,25
04,Neel,34
05,Nitin,32
06,Mukesh,30
07,Ina,24
08,Mina,26
09,Dika,28
```


## Resources

- [Bash Official Documentation](https://www.gnu.org/software/bash/manual/)
- [Linux Command Line Basics](https://www.learnshell.org/)
- [Advanced Bash-Scripting Guide](http://tldp.org/LDP/abs/html/)
