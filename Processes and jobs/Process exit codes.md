# Process exit codes

The description asks us to find the exit code of `challenge/get-code` and then pass it as an argument of `/challenge/submit-code`.
This can be done by using `?` operator and prepending it with `$`.
`$` is used to read the value.
This will give us the exit code of the recently terminated program.

```bash
Connected!
hacker@processes~process-exit-codes:~$ /challenge/get-code $?
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
107
hacker@processes~process-exit-codes:~$ /challenge/submit-code 107
CORRECT! Here is your flag:
pwn.college{UJrtiYOdWc90IkiJkvQp5L3qsA4.dljN4UDLwMjN0czW}
hacker@processes~process-exit-codes:~$
```

This is how I solved it.
