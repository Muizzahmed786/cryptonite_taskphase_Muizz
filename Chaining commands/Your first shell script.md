# Your first shell script

The description tells me to run `/challenge/pwn` and `/challenge/college` in a shell script.
For this we have to use `nano` command and pass `x.sh` to it. 
`nano` command is used to edit a file.
after this we have to write our commands in the `x.sh` file and save it.
Then use `bash` and `x.sh` as an argument to it to get the flag.

```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@chaining~your-first-shell-script:~$ bash x.sh
You must first call the '/challenge/pwn' command, not 'trap dbg debug'!
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{E48NH0J-w1tkjR-1Foh80t477iE.dFzN4QDLwMjN0czW}
hacker@chaining~your-first-shell-script:~$
```
This is how I solved it.

I got to know a new command in linux called as `nano`.
