# Using sudo

The description asks me to get the flag with the help of `sudo`.
if we write `cat /flag` in the command promt, it won't give us permission as we are not the `root` user.
For this we use `sudo`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@users~using-sudo:~$ cat /flag
cat: /flag: Permission denied
hacker@users~using-sudo:~$ sudo cat/flag
sudo: cat/flag: command not found
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{oolmc0WX7D8PLyIN8iXrK5gNqEs.dhTN0UDLwMjN0czW}
hacker@users~using-sudo:~$
```

This is how I solved it.
