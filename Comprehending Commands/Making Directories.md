# Making Directories

The description asks us to make a driectory `/tmp/pwn` and create a file `college` in it using the command `mkdir`

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.XvrUsDZh8M
hacker@commands~making-directories:/tmp$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{MtkTJH2cyLSYDoN9V6mLLr_Tlqp.dFzM4QDLwMjN0czW}
```

This is how I solved it.
