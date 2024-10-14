# Suspending Processes

The description asks me to suspend `/challenge/run` process and then launch it again.
This can be done by using the hotkey `ctrl-Z`.

```bash
Connected!
hacker@processes~suspending-processes:~$ run
ssh-entrypoint: run: command not found
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      65  0 11:25 pts/0    00:00:00 bash /challenge/run
root          85      83  0 11:25 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      65  0 11:25 pts/0    00:00:00 bash /challenge/run
root          90      65  0 11:26 pts/0    00:00:00 bash /challenge/run
root          92      90  0 11:26 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{8CltKm4BW9CMUfTvif5mQ-m5iYB.dVDN4QDLwMjN0czW}
hacker@processes~suspending-processes:~$
```

This is how I soolved it.
