# rsudo by m4rkw

executes sudo bash to get a root shell on a remote server in one command.
this is done by capturing the sudo password locally before the ssh connection
is made. it requires /etc/sudoers.d/USER to exist, with the following
content:

````
#user ALL = NOPASSWD: ALL
````

rsudo will uncomment this line for one second in order to sudo bash on the
remote server without a password, then revert it.

this idea came from routinely needing to execute commands on remote servers as
root while travelling on the London Underground where wifi only works for very
brief periods at the stations.
