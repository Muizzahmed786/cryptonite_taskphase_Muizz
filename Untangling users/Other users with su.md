# Other users with su

The description asks us to use the `su` command to switch to user `zardus` and then enter the password `dont-hack-me`.
After this we havee to run `/challenge/run` program to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{8l48TGkB3lKb3DjojkVJMI711PU.dZTN0UDLwMjN0czW}
zardus@users~other-users-with-su:/home/hacker$
```

This is how I solved it.
