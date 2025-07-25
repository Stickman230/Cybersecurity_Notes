#Authentication #Enumeration #WEB #WebAuthentication
# Wayback Machine

Think of the Internet Archive's Wayback Machine ([https://archive.org/web/](https://archive.org/web/)) as a time machine.
- travel back and explore older versions of websites, uncovering files and directories that are no longer visible but might still linger on the server. These relics can sometimes provide a backdoor right into the present system.
- Downloadable on Github : [Waybackmachine](https://github.com/tomnomnom/waybackurls)

# Google Dorking

These queries can pull up everything from exposed administrative directories to logs containing passwords and indices of sensitive directories. For example:

- To find administrative panels: `site:example.com inurl:admin`
- To unearth log files with passwords: `filetype:log "password" site:example.com`
- To discover backup directories: `intitle:"index of" "backup" site:example.com`