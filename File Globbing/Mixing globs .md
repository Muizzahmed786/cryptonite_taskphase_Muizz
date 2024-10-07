# Mixing Globs

The description asks us to write a glob of 6 characters that will match the files `challenging`,`educational`,`pwning`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep*]
Your expansion did not expand to the requested files (challenging, educational,
pwning). Instead, it expanded to:
[cep*]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{IqnHj_h8wlbo2uHMHQXjomEY_La.dVjM4QDLwMjN0czW}
hacker@globbing~mixing-globs:/challenge/files$
```

This is how I solved it.
