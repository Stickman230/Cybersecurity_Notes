#Tools #Defensics
- Defensics provides test suites for testing a wide range of protocols, file formats, and interfaces

- If there is a need to limit test execution time or define a maximum number of test cases to run, it is possible too
---
### **Defensics Integration in Projects**

Headless Defensics CI integrations has three options:

- ==CLI==
    
- ==HTTP API==
    
- Jenkins plugin

---
### **Managing fuzzing time**

- `--max-run-time` 
- sets the upper limit for testing duration. In GUI, **Run control** > **Stop criteria** > **Limit running time**

- `--max-run-cases` 
- sets the upper limit for the amount of test cases executed. Useful when there is a need to meet minimum testing policies. In GUI, **Run control** > **Stop criteria** > **Limit test cases**.

- `--max-fails-limit` 
- stops testing once more than the defined number of fails are logged. Can be used to free resources automatically in cases where it is important to fix the issues before doing more testing. In GUI, **Run control** > **Stop criteria** > **Max failed cases before stop**.

- `--selection-mode balanced` 
- executes test cases in an order that ensures at least some protocol feature coverage even if the test is interrupted because one of the stop criteria triggers. In GUI, **Test cases** > **Execution mode** > **Balanced case execution**.
---

### **CLI Integration** 

[CLI integration Documentation](https://sig-product-docs.synopsys.com/bundle/defensics-integration/page/cli.html)

Defensics comes with a few different reports:

- `single-html` produces a full report as a single HTML page.

- `summary-html` produces an executive report as a single HTML page.

- `html` produces a browsable HTML summary and cases as separate pages.

- `zip` produces a zip packet of the HTML files with an HTML summary.

- `remediation` produces a zip packet of remediation report.

---
### **HTTP API integration**

#### Run Defensics in server mode

 - Make sure Defensics and test suites have been installed. 
 - Then start Defensics, for example, **binding to localhost only**:

```
java -jar boot.jar --api-server 8080
```

On the first run, the server generates an API token for authentication. 
- **Save the token securely** for client use. 
- When the server starts, it also prints the REST API documentation location. (*Refer to it for typical call flow implementations.)*

#### HTTP API reference

Full documentation of the HTTP API starting and security configurations is available in the CLI help section 7

```
java -jar boot.jar --full-help
```

- Detailed documentation of the RESTful API endpoints is available as OpenAPI documentation.

- OpenAPI documentation **comes installed with Defensics**,

	- in the application installation folder like `/opt/Synopsys/Defensics/monitor/docs/doc-defensics-api.html` for Linux
	- `C:\Program Files\Synopsys\Defensics\monitor\docs\doc-defensics-api.html` for Windows. 

 There is also a YAML version of the same file if you prefer hosting it yourself.

---
