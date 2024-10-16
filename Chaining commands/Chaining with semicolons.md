# Chaining with semicolons

The description asks us to chain `/challenge/pwn` and `/challenge/college`.
We can do this by using `;` (semicolon).

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{4oyLHJYmC4_JBeFKD_PrwEtm1f1.dVTN4QDLwMjN0czW}
hacker@chaining~chaining-with-semicolons:~$
```

This is how I solved it.
