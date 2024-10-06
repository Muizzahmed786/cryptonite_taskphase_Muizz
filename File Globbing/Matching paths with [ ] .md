# Matching paths with [ ]

The description wants us to run `/challenge/run` with a single argument which globs into the absolute paths of `file_b`, `file_a`, `file_s`, `file_h`.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{AY4EBfz8jDuqmRbteVl1uyA4hju.dRjM4QDLwMjN0czW}
hacker@globbing~matching-paths-with-:~$
```

This is how i solved it.
While solving I was doing the command in the `/challenge/file` directory, this showed an error and told me to work in the `~` directory.
