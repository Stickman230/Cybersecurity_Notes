#Tools
The usual flow for server-side testing on a high level goes like this:

1. Configure Defensics and the protocol test suite
2. Configure the tested system to accept incoming connections from Defensics
3. Configure proper instrumentation method
4. Run tests
5. Open the Results view to see pass/fail verdicts and other details
6. Re-run the failures
7. Depending on how detailed instrumentation method you have, either inspect Defensics Results, or log in to your target system to see what went wrong
8. Once you have verified the found vulnerabilities are real, create a Remediation Package, and forward your findings to the person responsible for fixing the issues

---

### **Results Output**

- HTML Document 
- Microsoft Exel (.xls)
- Verizon