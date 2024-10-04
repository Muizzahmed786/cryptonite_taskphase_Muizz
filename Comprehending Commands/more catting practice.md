# more catting practice

the description asks us to use the `cat` command without changing directories with `cd`

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/local/include/flag. Go cat it out **without** cding into that
directory!
hacker@commands~more-catting-practice:~$ cat /usr/local/include/flag
pwn.college{YNuIp2Dv8KzY-_Ex8Nh095Az9PH.dBjM5QDLwMjN0czW}
hacker@commands~more-catting-practice:~$
```

This is how I solved it.

i have used the `cat` command on the given path location `/usr/local/include/flag` to get the flag.
