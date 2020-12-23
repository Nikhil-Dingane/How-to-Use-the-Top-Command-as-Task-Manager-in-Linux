Windows user often uses the task manager to monitor or end the task, but when we comes to Linux there is no such task manager with rich UI. Instead of GUI task manager there is a mangical command is avialable on the Linux which can be used as task manager on the Linux.The top command offers a quick overview of system information. It reports data about current processes which is refreshed (by default) every 3 seconds. I am going to give a short introduction of the 'top' command. The top command offers a quick overview of system information. It reports data about current processes which is refreshed (by default) every 3 seconds.Using and understanding a program like top is an essential system administration skill.

##Understanding top command in Linux

    top

This simple command will bring you into the top application. When you want to exit, type the letter q to quit. There are also other key commands to make full use of it that I’ll discuss later.


![image](https://github.com/Nikhil-Dingane/How-to-Use-the-Top-Command-as-Task-Manager-in-Linux/blob/main/images/Screenshot%20from%202020-12-23%2012-48-47.png)

You can easily check CPU load, the number of current tasks, as well as viewing information about memory usage.There is a lot of detailed information displayed in a condensed format. Let’s break it into smaller pieces so that we can understand it. The first four lines contain the overview data I mentioned before. Let’s understand them line by line.

## User Info, Uptime, and Load Averages

    Tasks: 210 total,   2 running, 208 sleeping,   0 stopped,   0 zombie

The first piece of information is a timestamp, which is pretty self-explanatory. Next to it you will see the system up time. In my case, it reads 24 mins. This refers to how long the computer has been running without interruption. Next we see three values for the load average. These figures are readings over 1 minute, 5 minutes, and 15 minutes, in that respective order. Nex, there are different states of processes. 

## CPU information in top command

    %Cpu(s):100.0 us,  0.0 sy,  0.0 ni,  0.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
    
Each of the values here is a percentage of time spent on the respective tasks. The table below explains what is meant by each abbreviation. This gives a fairly detailed breakdown of how processing power is being used.
   
## Memory usage in top command
MiB Mem :   7974.7 total,   5974.0 free,   1046.9 used,    953.9 buff/cache
MiB Swap:   4095.5 total,   4095.5 free,      0.0 used.   6660.1 avail Mem 
These lines are similar ot the output of the free command in Linux.

## Task Table
This is really the heart of the top command. If you came from windows, you’re probably familiar with using CTRL+ALT+DEL to access Task Manager. This is sort of a more “stripped” down version of that. You see the table of all the currently running tasks.

## Customizing and interacting with the top command output
Once you have your display set up in a way that you like. It’s time to get some work done. Let’s take a look at the full list of options for top (accessible by typing h) and look at some examples.

1. Color and Memory Scale

            Z,B,E,e   Global: 'Z' colors; 'B' bold; 'E'/'e' summary/task memory scale
    We have covered the color changes, but you can also modify the memory scale from bytes all the way up to petabytes. E modifies the figures from the summary section, while a e adjusts the scale in the task table.
    
2. Toggle Views for Summary Info

        l,t,m     Toggle Summary: 'l' load avg; 't' task/cpu stats; 'm' memory info
    Each respective key will adjust the display options. The default is a text based output, but there are also simulated bars or you can turn items off completely.

3. View CPU-Specific Info

        0,1,2,3,I Toggle: '0' zeros; '1/2/3' cpus or numa node views; 'I' Irix mode
    I only have one CPU on my virtual machine, but you can see how it would work if there were multiples. You can separate into individual nodes with their own statistics.

4. Top Field Manipulation

        Fields: 'f'/'F' add/remove/order/sort; 'X' increase fixed-width
    We can add or remove any fields we want displayed, we can also adjust the fixed-width of the text.
    
5. Locate String

        L,&,<,> . Locate: 'L'/'&' find/again; Move sort column: '<'/'>' left/right
    As like vi editor you can search the string.
6. Toggle Full-Path, Idle Tasks, Cumulative Time, and Text Justification
 
        Toggle: 'c' Cmd name/line; 'i' Idle; 'S' Time; 'j' Str justify
    When you toggle c, you will see the full path of commands. Idle removes all non-active tasks from the display. S uses cumulative time. String justify changes the default left-aligned position of string fields.

7. Toggle Highlights

        x,y     . Toggle highlights: 'x' sort field; 'y' running tasks
    Using x to toggle sort field and y to sort running tasks.
    
8. Filter by User or Field/Value

        u,U,o,O . Filter by: 'u'/'U' effective/any user; 'o'/'O' other criteria
    We can easily filter out specific users or field/values. This is great for a system with many users or a lot of open tasks. Filters require a comparison operator between the field and the value. As you can see here I typed COMMAND=top to filter all commands except for top. Using shift with either command toggles case-sensitivity.

9. Filter number of Processes

        n,#,^O  . Set: 'n'/'#' max tasks displayed; Show: Ctrl+'O' other filter(s)
    Using either n or # will give you the option to enter a numeric value. This will show only the number of processes desired.

10. Renice or Kill Process with PID in top command

        k,r       Manipulate tasks: 'k' kill; 'r' renice
    Using these commands, we can change the nice value or kill the process. I filtered out the specific PID to make it easier to see. I changed the nice value to 20. Then I sent a kill command. Using kill by default sends a SIGTERM signal. This allows it to finish executing code before terminating.

11. Change the default update time in top command

        d or s    Set update interval
    Here, I have changed the default update time from every 3.0 seconds, to every 1 second. You can adjust any time that suits your needs. It’s possible to use d or s to perform the same operation.
    
I hope this enough information to introduce to top command of Linux.
