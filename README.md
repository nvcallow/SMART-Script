# SMART-Script
A bash script to collect SMART Drive Data and send it to a remote MySQL Database

Requires MySQL Client, SmartMonTools, and BASH to be installed

This script defines the MySQL parameters inside as variables, secure this file. 

It will use sysctl -n kern.disks to get a list of disk drives installed</br>
Then, it will iterate over each disk:</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  First, calls smartctl -x to receive a detailed report for that disk</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Then, parses the data with grep | awk to isolate the values and store to vars</br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Finally, call mysql command line to issue an INSERT data into remote table.</br>
  
smartscript3 is an updated version that loads more parameters into the database.  It also now includes a function to look for leading zeros.  Some of the smart paramters have been normalized in the report and are provided as XXX.  When this parameter is 100 that is ok.  When the value drops to 099 the leading zero causes issues.  The new functions remove the leading zeros and make sure all values are values.  
