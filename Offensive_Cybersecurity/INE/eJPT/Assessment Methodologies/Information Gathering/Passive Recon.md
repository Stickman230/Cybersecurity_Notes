#eJPT #INE #PassiveInformationGathering


| COMMAND | FUNTION         |
| ------- | --------------- |
| *host*  | Host DNS lookup |
|         |                 |

# What is Passive Information Gathering ?

**Gathering information without actively engaging the target and using public resources (Whois, DNS Recon...)**

# robots.txt and sitemap.xml 

Both are important files used in *managing how search engines interact with a website*, but they serve different purposes:
#### robots.txt

- Purpose: Instructs search engine crawlers on which parts of a website should not be crawled or indexed.
- Location: Placed in the root directory of a website (e.g., `https://www.example.com/robots.txt`).
- Format: Plain text file that uses specific directives, such as:
	- `User-agent`: Specifies which search engine bots the rules apply to.
	- `Disallow`: Specifies which paths should not be crawled.
	- `Allow`: Specifies which paths can be crawled, even if a parent path is disallowed.

#### sitemap.xml

- Purpose: Provides search engines with a structured list of the pages on a website, helping them understand the site's structure and find all content.
- Location: Typically found in the root directory (e.g., `https://www.example.com/sitemap.xml`), but can also be specified in the robots.txt file.
- Format: XML file that includes URLs, last modified dates, change frequency, and priority for each page.

**robots.txt tells crawlers what to avoid, while sitemap.xml tells them what to look for.**

#