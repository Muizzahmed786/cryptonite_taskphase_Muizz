# Killing processes

The description aks us to use the `kill` command to terminate `/challenge/dont_run` and then run `/challenge/run` to get the flag.

First we have to use the `ps -ef` command to get the list of all running processes.
Then we have to identify the PID of `/challenge/dont_run` and then pass it as an argument to `kill` command for termination.
Finally, now we can run `/challenge/run` to get the flag.

```
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 11:11 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 11:11 ?        00:00:00 /run/dojo/bin/sleep 6h
hacker        74       1  0 11:11 ?        00:00:00 sleep 6h
hacker        75       0  0 11:11 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker        93      75  0 11:11 pts/0    00:00:00 /bin/bash /challenge/dont_run
hacker        94      93  0 11:11 pts/0    00:00:00 sleep 6h
hacker        95       0  0 11:12 pts/1    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       119      95  0 11:14 pts/1    00:00:00 grep --color=auto /challenge/dont_run
hacker       120       0  1 11:14 pts/2    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       137     120  0 11:14 pts/2    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill 93
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 11:11 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 11:11 ?        00:00:00 /run/dojo/bin/sleep 6h
hacker        74       1  0 11:11 ?        00:00:00 sleep 6h
hacker        94       1  0 11:11 ?        00:00:00 sleep 6h
hacker        95       0  0 11:12 pts/1    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       119      95  0 11:14 pts/1    00:00:00 grep --color=auto /challenge/dont_run
hacker       120       0  0 11:14 pts/2    00:00:00 /run/dojo/bin/ssh-entrypoint
hacker       139     120  0 11:15 pts/2    00:00:00 ps -ef
hacker@processes~killing-processes:~$ /challenge/run
Nope! /challenge/dont_run is still running! You gotta terminate it before I
give you the flag!
hacker@processes~killing-processes:~$ kill 119
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{4jr5Nortvx4NcoggluZ6XWzb8nK.dJDN4QDLwMjN0czW}
hacker@processes~killing-processes:~$
```

This is how I solved it.
