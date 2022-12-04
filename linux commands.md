SAR command in Linux to monitor system performance

It can be used to monitor Linux system’s resources like CPU usage, Memory utilization, I/O devices consumption, Network monitoring, Disk usage, 
process and thread allocation, battery performance, Plug and play devices, Processor performance, file system and more.

Syntax : 
$ sar -[ options ] time_interval number_of_tines_to_display

To verify the sar version : 
$ sar -V

To report CPU details total 5 times with the interval of 2 seconds : 
$ sar -u 2 5

To report about the amount of memory used, amount of memory free, available cache, available buffers total 3 times with the interval of 1 second : 
$ sar -r 1 3

Note: sar may not be installed by default. We need to install sysstat before using it (For example, in Ubuntu, we can install using sudo apt install sysstat).
