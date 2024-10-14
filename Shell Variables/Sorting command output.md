# Sorting command output

The description asks us to read the output of the command `/challenge/run` into the variable `PWN`.
For this we have to ivoke the following as a prompt: `PWN=$(/challenge/run)`. 
After this we have use `echo` command and `PWN`  as an argument to it to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
hacker@variables~storing-command-output:~$ echo "$PWN"
pwn.college{0mG4oq3OC1bdXiyI04kmR3itUxx.dVzN0UDLwMjN0czW}
hacker@variables~storing-command-output:~$
```

This is how I solved it.
