#XXE #XML #WebInjection #WEB
# Introduction

***XML (Extensible Markup Language)*** is a markup language derived from SGML, which is the same standard that HTML is based on. 
It is typically used by applications to store and transport data in a format that's both human-readable and machine-parseable.

XML is widely used in web applications for data exchange, storage, and configuration. It's often used for web services and APIs, such as SOAP and REST, to exchange data between systems.

## What is XSLT #XSLT

XSLT can be used to facilitate XXE attacks in several ways:  

1. **Data Extraction**: XSLT can be used to extract sensitive data from an XML document, which can then be used in an XXE attack. For example, an XSLT stylesheet can extract user credentials or other sensitive information from an XML file.
2. **Entity Expansion**: XSLT can expand entities defined in an XML document, including external entities. This can allow an attacker to inject malicious entities, leading to an XXE vulnerability.
3. **Data Manipulation**: XSLT can manipulate data in an XML document, potentially allowing an attacker to inject malicious data or modify existing data to exploit an XXE vulnerability.
4. **Blind XXE**: XSLT can be used to perform blind XXE attacks, in which an attacker injects malicious entities without seeing the server's response.

## What are DTD #DTD

Purpose and usage of DTDs:

- **Validation**: DTDs validate the structure of XML to ensure it meets specific criteria before processing, which is crucial in environments where data integrity is key.
- **Entity Declaration**: DTDs define entities that can be used throughout the XML document, including external entities which are key in XXE attacks

---
# XML Entities

*XML entities are placeholders for data or code that can be expanded within an XML document.*
**5 types of entities**: internal entities, external entities, parameter entities, general entities, and character entities.

### Types of Entities

1. ***Internal Entities*** are essentially variables used within an XML document to define and substitute content that may be repeated multiple times. They are defined in the DTD (Document Type Definition) and can simplify the management of repetitive information. For example:

    ```xml
    <!DOCTYPE note [
    <!ENTITY inf "This is a test.">
    ]>
    <note>
            <info>&inf;</info>
    </note>
    ```


2. ***External Entities*** are similar to internal entities, but their contents are referenced from outside the XML document, such as from a separate file or URL. This feature can be exploited in XXE (XML External Entity) attacks if the XML processor is configured to resolve external entities. For example:

    ```xml
    <!DOCTYPE note [
    <!ENTITY ext SYSTEM "http://example.com/external.dtd">
    ]>
    <note>
            <info>&ext;</info>
    </note>
    ```


3. ***Parameter Entities*** are special types of entities used within DTDs to define reusable structures or to include external DTD subsets. They are particularly useful for modularizing DTDs and for maintaining large-scale XML applications. For example:

    ```xml
    <!DOCTYPE note [
    <!ENTITY % common "CDATA">
    <!ELEMENT name (%common;)>
    ]>
    <note>
            <name>John Doe</name>
    </note>
    ```


4. ***General Entities*** are similar to variables and can be declared either internally or externally. They are used to define substitutions that can be used within the body of the XML document. Unlike parameter entities, general entities are intended for use in the document content. For example:

    ```xml
    <!DOCTYPE note [
    <!ENTITY author "John Doe">
    ]>
    <note>
            <writer>&author;</writer>
    </note>
    ```


5. ***Character Entities*** are used to represent special or reserved characters that cannot be used directly in XML documents. These entities prevent the parser from misinterpreting XML syntax. For example:
    
    - `&lt;` for the less-than symbol (`<`)
    - `&gt;` for the greater-than symbol (`>`)
    - `&amp;` for the ampersand (`&`)
    
    ```xml
    <note>
            <text>Use &lt; to represent a less-than symbol.</text>
    </note>
    ```

## Understanding the Graph 

![[XXE_graoh.png]]


---

[[(2) XXE injection - Detection & Exploitation|Continue to XXE Detection & Exploitation]]

---
#### Definition

- ***SGML (Standard Generalized Markup Language)*** : 

- ***XSLT (Extensible Stylesheet Language Transformations)*** : Language used to transform and format XML documents.

- ***DTD (Document Type Definitions)*** : Defines the structure and constraints of an XML document : allowed elements, attributes, and relationships between them. DTDs can be **internal within the XML document or external in a separate file.**