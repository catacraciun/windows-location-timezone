Windows automatic timezone based on location
===============

This script is designed to run as a scheduled task on Windows. It uses telize.com API to get current geolocation and timezone, and sets the timezone. 

Installation
-------------------
Change policy to run scripts (from CMD as Admin): powershell -Command "Set-ExecutionPolicy -ExecutionPolicy Unrestricted"
 
Setup task scheduler instructions
---------------------------
- Open the Task Scheduler.
- In the Task Scheduler library, create a new task by clicking Create Task in the Actions panel on the right side.
- Give the task a name like "Update time zone on network connect" or whatever you choose
- On the Triggers tab, click New... and select On an Event from the dropdown box.
- Choose the following settings:
        Log: Microsoft-Windows-NetworkProfile/Operational
        Source: NetworkProfile
        Event ID: 10000
- Click OK, then go to the Conditions tab.
- Check the box for Start only if the following network connection is available and choose the network you want to run the script with
- Under the Actions tab, click New... and select Start a program. Enter the location of the script file you want to run, then click OK.
- Set any other task settings you want to, then click OK.
 
Command: powershell -file update_time_zone.ps1

Credits
------------------
This script was first created by: http://superuser.com/a/751262 
Thank you for your clever idea!