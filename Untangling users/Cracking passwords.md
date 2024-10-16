# Cracking passwords

The description wants us to crack the password for the user `zardus`.
We are given a leak in `/challenge/shadow-leak`, so we have to first use `cat`.
And then use `john the ripper` to crack the password.
After that we use `su` command to switch to `zardus` and type the password.
Finally we have to run `/challenge/run` to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@users~cracking-passwords:~$ /challenge/shadow-leak
ssh-entrypoint: /challenge/shadow-leak: Permission denied
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:19873:0:99999:7:::
daemon:*:19873:0:99999:7:::
bin:*:19873:0:99999:7:::
sys:*:19873:0:99999:7:::
sync:*:19873:0:99999:7:::
games:*:19873:0:99999:7:::
man:*:19873:0:99999:7:::
lp:*:19873:0:99999:7:::
mail:*:19873:0:99999:7:::
news:*:19873:0:99999:7:::
uucp:*:19873:0:99999:7:::
proxy:*:19873:0:99999:7:::
www-data:*:19873:0:99999:7:::
backup:*:19873:0:99999:7:::
list:*:19873:0:99999:7:::
irc:*:19873:0:99999:7:::
gnats:*:19873:0:99999:7:::
nobody:*:19873:0:99999:7:::
_apt:*:19873:0:99999:7:::
hacker::20000:0:99999:7:::
zardus:$6$X7OaYsqts4ZxZrLr$Wkz7Mcx/SAhwZrHlp2hqcwGJ5hjN9QmmRQgLj1pkfIHpE6GX7APiolQHs701teqwCP6wavv8IOfGCXT4J66Hk.:20012:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04906g/s 285.7p/s 285.7c/s 285.7C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{0f3IRwwFqZBUf6xsQFLJol62v9-.ddTN0UDLwMjN0czW}
zardus@users~cracking-passwords:/home/hacker$
```

This si how I solved it.
