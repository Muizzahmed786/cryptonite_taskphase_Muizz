# Redirecting Output

The description asks us to Redirect `PWN` to `COLLEGE` using `>`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{8Mg4UJHtLHJ4PlURjvnQPLA4VA1.dRjN1QDLwMjN0czW}
hacker@piping~redirecting-output:~$
```

This is how I solved it.
