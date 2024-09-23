# SMART-Script
A bash script to collect SMART Drive Data and send it to a remote MySQL Database

Requires MySQL Client, SmartMonTools, and BASH to be installed

This script defines the MySQL parameters inside as variables, secure this file. 

It will use sysctl -n kern.disks to get a list of disk drives installed</br>
Then, it will iterate over each disk:</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  First, calls smartctl -x to receive a detailed report for that disk</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Then, parses the data with grep | awk to isolate the values and store to vars</br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Finally, call mysql command line to issue an INSERT data into remote table.</br>
  
