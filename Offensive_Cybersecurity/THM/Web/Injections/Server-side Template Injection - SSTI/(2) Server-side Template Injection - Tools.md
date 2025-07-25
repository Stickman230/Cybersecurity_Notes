#SSTI #WebInjection #WEB
## SSTImap

- #SSTImap is a tool that automates the process of testing and exploiting SSTI vulnerabilities in various template engines. Hosted on [GitHub](https://github.com/vladko312/SSTImap), it provides a framework for discovering template injection flaws
	- **Template Engine Detection**: SSTImap can help identify the template engine used by a web application, which is crucial for crafting specific exploits.
	- **Automated Exploitation**: For known vulnerabilities, SSTImap can automate the process of exploiting them.
	- git clone https://github.com/vladko312/SSTImap.git

Usage:
```bash
python3 sstimap.py -X POST -u 'http://ssti.thm:8002/mako/' -d 'page='
```