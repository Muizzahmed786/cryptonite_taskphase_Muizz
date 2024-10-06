# Exclusionary globbing

the description asks me to run `/challenge/run` with all files that don't start with `p`, `w`, `,n`.
This can be done by using `!` as the first character of glob`[ ]`.

 ```bash
muizz@LAPTOP-VF1FT9IQ:~$ ssh -i ./key hacker@dojo.pwn.college
Connected!
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]
Your expansion did not expand to the requested files (amazing beautiful
challenging delightful educational fantastic great happy incredible jovial kind
laughing magical optimistic queenly radiant splendid thrilling uplifting
victorious xenial youthful zesty).
Instead, it expanded to:
[!pwn]
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{8c_tXinly3AG_Hil5jAiYuqj3as.dZjM4QDLwMjN0czW}
hacker@globbing~exclusionary-globbing:/challenge/files$
```

This is how I solved it.
`*` is used to get the remaining file name.
