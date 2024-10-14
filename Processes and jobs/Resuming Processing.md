# Resuming Processing

The description asks me to suspend `/challenge/run` and then resume it using `fg` command.

```bash
Connected!
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{sFgfKiKxsqTtBzYGptaoiYxYubh.dZDN4QDLwMjN0czW}
Don't forget to press Enter to quit me!

Goodbye!
hacker@processes~resuming-processes:~$
```

This is how I solved it.
