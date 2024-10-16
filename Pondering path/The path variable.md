# The path variable

The description asks us to get the flag by running `/challenge/run` such that it does not delete the flag.
For this we have to set the `PATH` to empty, such that it doesn't recognize the `rm` command.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@path~the-path-variable:~$ rm /challenge/run
rm: remove write-protected regular file '/challenge/run'?
hacker@path~the-path-variable:~$ PATH="rm"
hacker@path~the-path-variable:~$ rm /challenge/run
ssh-entrypoint: rm: command not found
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{8SRDzqEd2tdNjltlL4CpvzXEnR3.dZzNwUDLwMjN0czW}
hacker@path~the-path-variable:~$
```

This is how I solved it.
