# Redirecting script output

The description asks us to create a script that calls `/challenge/pwn` and then `/challenge/college`.
After that we have to pipe it's output to `/challenge/solve` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~redirecting-script-output:~$ touch script.sh
hacker@chaining~redirecting-script-output:~$ nano script.sh
hacker@chaining~redirecting-script-output:~$ cat script.sh
/challenge/pwn; /challenge/college

hacker@chaining~redirecting-script-output:~$ bash script.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{EdJIV8SQmKDvTVLO6sjYcuzLUWr.dhTM5QDLwMjN0czW}
hacker@chaining~redirecting-script-output:~$
```

This is how I solved it.
