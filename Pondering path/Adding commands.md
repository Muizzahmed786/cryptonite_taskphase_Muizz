# Adding commands

The description asks us to create a shell script `win` in which we have to invoke `cat /flag` and make `win` executable using `chmod` command.
After that we have to add the directory `/home/hacker`. This can be done by invoking `PATH="/home/hacker:$PATH"` to the command prompt.
After that we have to run `/challenge/run` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ chmod a+x win
hacker@path~adding-commands:~$ ls -l win
-rwxr-xr-x 1 hacker hacker 11 Oct 17 16:40 win
hacker@path~adding-commands:~$ PATH="/home/hacker:$PATH"
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{835NfKRJfAYxwdG2xg915Q1fDYa.dZzNyUDLwMjN0czW}
hacker@path~adding-commands:~$
```

This is how I solved it.
