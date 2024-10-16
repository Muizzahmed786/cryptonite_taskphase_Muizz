# Setting path

The description asks us to overwrite `PATH` with `/challenge/more_commands` and then run `/challenge/run` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@path~setting-path:~$ PATH=/challenge/more_commands/win
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
/challenge/run: line 4: win: command not found
It looks like that did not work... Did you set PATH correctly?
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{oVVu3KqtIGR7k-OdfF7U4Y-bwDS.dVzNyUDLwMjN0czW}
hacker@path~setting-path:~$
```

This is how I solved it.
