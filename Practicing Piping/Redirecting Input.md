# Redirecting Input

The description asks us to contain the value of `COLLEGE` in `PWN` with `echo` as a command.
Then to redirect `PWN` to `/challenge/run`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{sA54uJC4PZ-tokzVlOJk5nFQtll.dBzN1QDLwMjN0czW}
hacker@piping~redirecting-input:~$
```

This is how I solved it.
