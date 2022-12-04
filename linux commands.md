# sudo command in Linux

sudo (Super User DO) command in Linux is generally used as a prefix of some command that only superuser are allowed to run. If you prefix “sudo” with any command, it will run that command with elevated privileges or in other words allow a user with proper permissions to execute a command as another user, such as the superuser. This is the equivalent of “run as administrator” option in Windows.

## The sudoers file

 It controls who can use the sudo command to gain elevated privileges. It is usually located at /etc/sudoers. The best and safest way to edit this file is by using the visudo command. This command will start the vi editor with elevated privileges so that you can edit the file and save it. It also will put a filelock on the sudoers file so that no one else can edit it. 
 This file contains many parameters. You can specify which users of which groups can perform what commands.
 
 ## Syntax
        $ sudo [command]
      
## sudo can be used with additional options:

- -h – help; displays syntax and command options
- -V – version; displays the current version of the sudo application
- -v – validate; refresh the time limit on sudo without running a command
- -l – list; lists the user’s privileges, or checks a specific command
- -k – kill; end the current sudo privileges

![Image](https://phoenixnap.com/kb/wp-content/uploads/2021/04/sudo-options.png)
------------------------------------------------------------------------------------------------------------------------
--------------------------------------------------------------------------------------------------------------------------


# SAR command in Linux to monitor system performance

It can be used to monitor Linux system’s resources like CPU usage, Memory utilization, I/O devices consumption, Network monitoring, Disk usage, 
process and thread allocation, battery performance, Plug and play devices, Processor performance, file system and more.

## Syntax : 
    $ sar -[ options ] time_interval number_of_tines_to_display

## To verify the sar version : 
    $ sar -V

## To report CPU details total 5 times with the interval of 2 seconds : 
    $ sar -u 2 5

## To report about the amount of memory used, amount of memory free, available cache, available buffers total 3 times with the interval of 1 second : 
    $ sar -r 1 3

- Note: sar may not be installed by default. We need to install sysstat before using it (For example, in Ubuntu, we can install using sudo apt install sysstat).
