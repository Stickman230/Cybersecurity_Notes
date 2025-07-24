#LDAP #ActiveDirectory #WebInjection
# What is LDAP

LDAP stands for **Lightweight Directory Access Protocol**, is a widely used protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP) network. *LDAP enables organizations to manage users centrally*, as well as groups and other directory information, often *used for authentication and authorization purposes* in web and internal applications.

**Services that use LDAP**:
- #MicrosoftActiveDirectory: A service for Windows domain networks, utilizing LDAP as part of its underlying protocol suite to manage domain resources.

- #OpenLDAP: An open-source implementation of LDAP, widely used for managing user information and supporting authentication mechanisms across various platforms.

## Structure

![[LDAP_Structure.png]]

At the top of the LDAP tree, we find the **top-level domain (TLD)**, such as `dc=ldap,dc=thm`. Beneath the TLD, there may be **subdomains** or **organizational units (OUs)**, such as `ou=people` or `ou=groups`, which further categorize the directory entries.

- **Distinguished Names (DNs):** Serve as unique identifiers for each entry in the directory, specifying the path from the top of the LDAP tree to the entry, for example, `cn=John Doe,ou=people,dc=example,dc=com`.

- **Relative Distinguished Names (RDNs):** Represent individual levels within the directory hierarchy, such as `cn=John Doe`, where `cn` stands for Common Name.

- **Attributes:** Define the properties of directory entries, like `mail=john@example.com` for an email address.

---
# Building LDAP Queries

The basic syntax for an LDAP search query looks like this:

```default
(base DN) (scope) (filter) (attributes)
```

1. **Base DN (Distinguished Name):** This is the search's starting point in the directory tree.

2. **Scope:** Defines how deep the search should go from the base DN. It can be one of the following:
    - `base` (search the base DN only),
    - `one` (search the immediate children of the base DN),
    - `sub` (search the base DN and all its descendants).

3. **Filter:** A criteria entry must match to be returned in the search results. It uses a specific syntax to define these criteria.
	*( syntax for LDAP filters is defined in [RFC 4515](https://www.openldap.org/lists/ietf-ldapbis/200606/msg00010.html) )*

5. **Attributes:** Specifies which characteristics of the matching entries should be returned in the search results.

## Filters

**Simple Filter:**

```default
(cn=John Doe)
```

This filter targets entries with a canonical name (`cn`) exactly matching "John Doe".

**Wildcards:**

```
(cn=J*)
```

This filter applies the wildcard operator to match any entry where the `cn` begins with "J".

**Complex Filters with Logical Operators:**

 Filters can be used with each other using logical operators such as AND (`&`), OR (`|`), and NOT (`!`).

```default
(&(objectClass=user)(|(cn=John*)(cn=Jane*)))
```

This filter searches for entries classified as "user" in their object class with a canonical name starting with either "John" or "Jane".


[[(2) LDAP Injection - Detection & Exploitation |Continue to Detection & Exploitation]]

---
#### Definitions

- ***LDAP Data Interchange Format (LDIF)*** : LDAP entries can be represented using this format, standard plain text data format for representing LDAP directory entries and update operations