#General:

Hello,


This script is used to monitor CPU, Disk and memory usage and output them into a log file as well as show it on the screen (For debugging purposes).

Now, Let's break down the script.




Functions:
I started by defining the function "Syntax" which will be used later to show the correct syntax - to the user - that can be used with the script to avoid errors.




'BODY()':

I started by using the 'date' command to show the date and time for when the script was invoked which helps with tracking the logs and makes it much easier to 'grep' a specfic day if needed.

 
 After that we moved to the actual monitoring by using 'df' command (Disk Free) which shows the disk usage for all the partitions on the machine then setup the logic for the warnings in case any partition's disk usage exceeds 80% or the specified threshold (in case of using '-t' option).
 
 The 'warning_message' variable will have the output of the commands used to check for disk usage by running 'df' then using 'sed' to remove the "%" in the output then used awk to compare column #5 (Use%) with the threshold as well as make sure that the input is an integer.
 
 I set it this way as otherwise the string "Use%" would be taken into consideration too and will mess up the output.
 
 
 
 
 CPU Usage:
 'mpstat' was used along with awk to check the CPU usage.
 
 
 
 
Memory Usage:
In this section, We used 'free' along with 'grep' to isolate the 'MEM' row then used 'awk' to calculate the free, used and total memory.




Top 5 processes:
To do this I used the 'ps' command with the option 'aux' to display all processes with CPU and MEM usage for each process then added '--sort' option to sort the 'MEM' usage in a descending order.




Main code:
For readability purposes we defined and used 'RED' for the red font and 'NC' for no color font.

I used an 'if' conditional to check if the number of provided arguements is less than 1 or not to determine if the user wants to use the script with options or not.

Less than "1" arguement means the user wants to use the script without any conditionals and if more than "1" arguement this means we move to the 'else'.

In the 'else' we check which option is the user using and in each case of the options we use error detection to make sure that the user provided the correct number of arguements in the right sequence otherwise they get an error message with the correct syntax to use.


