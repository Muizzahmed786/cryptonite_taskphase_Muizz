# Writing to multiple programs

The description asks to run the `/challenge/hack` command and duplicate it's output and use it as input to the commands `/challenge/the` and `/challenge/planet`.
We have to use the `tee` and `>()` command to get the flag in this case.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{gQ7MM-GxPdzvsCdmJJuMi7SziXA.dBDO0UDLwMjN0czW}
hacker@piping~writing-to-multiple-programs:~$
```

This is how I solved it.
