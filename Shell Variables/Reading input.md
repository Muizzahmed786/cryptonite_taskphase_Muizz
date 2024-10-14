# Reading Input

the description asks us to use the `read` command to set the value of variable `PWN` to `COLLEGE`.
we have to use `-p` after `read` command to specify our argument which is in this case `PWN`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@variables~reading-input:~$ PWN=COLLEGE
You've set the first PWN variable properly, but you seem to not have used
'read' to do it. Please set it using 'read'
hacker@variables~reading-input:~$ read -p PWN
PWN
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{MhCpW-sCsDu9ymn6ojrBpuJAVQn.dhzN1QDLwMjN0czW}
hacker@variables~reading-input:~$
```

This is how i solved it.
