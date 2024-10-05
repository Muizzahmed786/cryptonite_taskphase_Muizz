# Help for builtins

the description tells us the concept of builtins. To get a list of builtins we use builtin `help`.
In this case we have to look `challenge` builtin help to find the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "g1Pec7Ds".
hacker@man~help-for-builtins:~$ challenge --secret g1Pec7Ds
Correct! Here is your flag!
pwn.college{g1Pec7DsYsRuHQWxkdFhPFNJAix.dRTM5QDLwMjN0czW}
```

This is how I solved it.
