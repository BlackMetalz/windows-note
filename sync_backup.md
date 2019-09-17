# Use CYGWIN
- Install required packages:
+ openssh
+ rsync
+ cygrunsrv
+ vim ( because i prefer use this instead of nano )
+ cron ( for schedule auto backup )

- Create an user in windows for using ssh

after that Setup open ssh and cron by
- ssh-host-config

*** Query: Should StrictModes be used? (yes/no) yes
*** Query: Do you want to install sshd as a service?
*** Query: (Say "no" if it is already installed as a service) (yes/no) yes
*** Query: Enter the value of CYGWIN for the daemon: [] tty ntsec

- cron-config
The cron daemon can run as a service or as a job. The latter is not recommended.
Do you want to install the cron daemon as a service? (yes/no) yes
Enter the value of CYGWIN for the daemon: [ ] ntsec
You must decide under what account the cron daemon will run.
If you are the only user on this machine, the daemon can run as yourself.
   This gives access to all network drives but only allows you as user.
To run multiple users, cron must change user context without knowing
  the passwords. There are three methods to do that, as explained in
  http://cygwin.com/cygwin-ug-net/ntsec.html#ntsec-nopasswd1
If all the cron users have executed "passwd -R" (see man passwd),
  which provides access to network drives, or if you are using the
  cyglsa package, then cron should run under the local system account.
Otherwise you need to have or to create a privileged account.
  This script will help you do so.
Do you want the cron daemon to run as yourself? (yes/no) no

Were the passwords of all cron users saved with "passwd -R", or
are you using the cyglsa package ? (yes/no) no
Do you want to use another privileged account name? (yes/no) no
Do you want to proceed anyway? (yes/no) yes

Running cron_diagnose ...
WARNING: You do not currently have a crontab file.

... no problem found.

Do you want to start the cron daemon as a service now? (yes/no) yes
OK. The cron daemon is now running.

# Last step: do it as in linux cause ssh and rsync already setup. Im too lazy to write fully description :v

- Note: Port default of cygwin sshd is 22 ( remember to allow it in firewall with specific IP )
