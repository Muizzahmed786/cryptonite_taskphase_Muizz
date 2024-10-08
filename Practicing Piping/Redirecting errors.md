# Redirecting errors

The description asks us to redirect the output of `/challenge/run` to `myflag` and errors to `instructions`.
To get the flag we have to read the file `myflag`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~redirecting-errors:~$ /challenge/run 1> myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{0O-aYCsD5UMHxK6DFYpQdAK3QtD.ddjN1QDLwMjN0czW}

hacker@piping~redirecting-errors:~$
```

This is how I solved it.
