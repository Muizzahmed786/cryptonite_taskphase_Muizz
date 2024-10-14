# Foregrounding processes

The description asks us to firstly suspend `/challenge/run` and then use `bg` to run it in the background.
After that we have to use `fg` command to run it in foreground to get the flag.

```bash
Connected!
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &



hacker@processes~foregrounding-processes:~$ Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

hacker@processes~foregrounding-processes:~$
hacker@processes~foregrounding-processes:~$
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{MzyQHJ3U0G_91YXyTj_4PjYlZTb.dhDN4QDLwMjN0czW}
hacker@processes~foregrounding-processes:~$
```

This is how I solved it.
