# Duplicating Piped data with tee

The description wants us to pipe `/challenge/pwn` to `/challenge/college`.
We also have use `tee` command to take the output from `/challenge/pwn`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~duplicating-piped-data-with-tee:~$ ls /challenge
DESCRIPTION.md  bin  chio.py  college  pwn
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee pwn1_output | /challenge/college
Processing...
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat pwn1_output
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "cuWwv2Cf"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret cuWwv2Cf | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{cuWwv2Cfm9kGzYRhdfSyzD7hf1I.dFjM5QDLwMjN0czW}
```

This is how I solved it.
