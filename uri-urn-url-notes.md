# URI vs. URN vs. URL: Undergraduate Course Notes

## Table of Contents
1. [Introduction and Overview](#introduction-and-overview)
2. [The URI Hierarchy](#the-uri-hierarchy)
3. [Generic URI Structure](#generic-uri-structure)
4. [URLs - Uniform Resource Locators](#urls---uniform-resource-locators)
5. [URNs - Uniform Resource Names](#urns---uniform-resource-names)
6. [Namespace Registration and IANA](#namespace-registration-and-iana)
7. [Practical Applications](#practical-applications)
8. [Resolution and DOI Case Study](#resolution-and-doi-case-study)
9. [Design Guidelines](#design-guidelines)
10. [Summary and Key Takeaways](#summary-and-key-takeaways)

---

## Introduction and Overview

### What are Web Resource Identifiers?
Web resource identifiers are standardized ways to uniquely identify resources on the internet. They form a hierarchy where:
- **URI (Uniform Resource Identifier)** is the broadest category
- **URL (Uniform Resource Locator)** and **URN (Uniform Resource Name)** are specific types of URIs
- **All URLs and URNs are URIs, but not all URIs are URLs or URNs**

### Why Do We Need Different Types?
- **URLs** tell you *how to reach* something (location + access method)
- **URNs** tell you *what something is called* (permanent name, independent of location)
- **URIs** provide the general framework for both approaches

---

## The URI Hierarchy

```
URI (Uniform Resource Identifier)
├── URL (Uniform Resource Locator)
│   └── Examples: http://example.com, mailto:user@domain.com
└── URN (Uniform Resource Name)
    └── Examples: urn:isbn:9780134685991, urn:doi:10.1038/example
```

### Key Relationship
- A URI can be a locator (URL), a name (URN), or both
- The distinction depends on whether the identifier contains location/access information

---

## Generic URI Structure

All URIs follow the template defined by RFC 3986:

```
<scheme> ":" <hier-part> [ "?" <query> ] [ "#" <fragment> ]
```

### Components Breakdown

| Component | Purpose | Example |
|-----------|---------|---------|
| **Scheme** | Protocol or naming system | `http`, `https`, `mailto`, `urn` |
| **Hier-part** | Hierarchical part (usually starts with `//authority`) | `//example.com/path` |
| **Query** | Non-hierarchical data for server | `?search=term&lang=en` |
| **Fragment** | Client-side reference | `#section1` |

### Authority Structure
When present, authority has the format:
```
[userinfo "@"] host [ ":" port ]
```

Examples:
- `user:pass@db.example.org:5984` (full authority)
- `en.wikipedia.org` (host only)
- `localhost:8080` (host with port)

---

## URLs - Uniform Resource Locators

### Definition
A **URL** is a URI that embeds a **network location and access mechanism**. It tells you both what the resource is and how to retrieve it.

### Typical Structure
```
scheme://authority/path[?query][#fragment]
```

### Key Characteristics
- **Immediately dereferenceable** - browsers can fetch the resource
- **Location-dependent** - breaks if the server or path changes
- **Access method included** - specifies how to retrieve the resource

### URL Example Analysis
```
https://john:secret@media.example.com:8443/videos/play.mp4?time=90#t=1m30s
```

| Component | Value | Purpose |
|-----------|-------|---------|
| Scheme | `https` | Secure HTTP protocol |
| Userinfo | `john:secret` | Authentication credentials |
| Host | `media.example.com` | Server location |
| Port | `8443` | Non-standard port |
| Path | `/videos/play.mp4` | Resource location on server |
| Query | `time=90` | Server parameter |
| Fragment | `t=1m30s` | Client-side position marker |

### Common URL Schemes
- `http://` and `https://` - Web pages and resources
- `ftp://` - File Transfer Protocol
- `mailto:` - Email addresses
- `file://` - Local file system
- `tel:` - Telephone numbers

---

## URNs - Uniform Resource Names

### Definition
A **URN** is a URI under the literal scheme `urn:` that provides **persistent, location-independent naming**. It identifies *what* a resource is, not *where* it is.

### Canonical Structure (RFC 8141)
```
urn:<NID>:<NSS>[?+r][?=q][#f]
```

### Components Explained

| Component | Full Name | Purpose | Example |
|-----------|-----------|---------|---------|
| **NID** | Namespace Identifier | Registered namespace (case-insensitive) | `isbn`, `doi`, `ietf` |
| **NSS** | Namespace Specific String | Unique identifier within namespace | `9780134685991` |
| **r-component** | Resolution hints | Optional resolution service hints | `?+SRV:global` |
| **q-component** | Query parameters | Parameters for the named resource | `?=lang=en` |
| **f-component** | Fragment | Sub-resource marker | `#chapter5` |

### URN Example
```
urn:isbn:9780134685991?=lang=en#chapter5
```
- **NID**: `isbn` (International Standard Book Number namespace)
- **NSS**: `9780134685991` (specific book identifier)
- **q-component**: `?=lang=en` (language preference)
- **f-component**: `#chapter5` (specific chapter)

### URN Equivalence Rules
Two URNs are considered identical when:
1. `urn` scheme and NID are compared **case-insensitively**
2. NSS octets are compared **without decoding percent-encodings**
3. **r/q/f components are ignored** for identity comparison

Example of equivalent URNs:
- `URN:ISBN:9780134685991`
- `urn:isbn:9780134685991?+SRV:global`

---

## Namespace Registration and IANA

### What is Namespace Registration?
When organizations want to create persistent URNs, they must register a **namespace** - a set of rules for creating identifiers within that domain.

### The Registration Process
1. **Define the namespace** - syntax, assignment rules, contact information
2. **Submit to IANA** - complete standardized template (RFC 3406/8141)
3. **Expert review** - technical and policy evaluation
4. **Receive NID** - unique Namespace Identifier (e.g., `isbn`, `doi`)

### IANA's Role
The **Internet Assigned Numbers Authority (IANA)** maintains the official **URN Namespaces registry**:
- Ensures no NID collision globally
- Reviews registration templates
- Publishes approved namespaces publicly
- Pronunciation: "eye-A-en-A" (spelled out as individual letters)

### How Global Uniqueness is Guaranteed

| Level | Responsibility | Mechanism |
|-------|---------------|-----------|
| **Global** | IANA | One-time NID assignment, no duplicates |
| **Namespace** | Namespace owner | Local uniqueness rules for NSS |
| **Persistence** | Both | No reassignment of URNs to different resources |

### Common Registered Namespaces
- `urn:isbn:` - International Standard Book Numbers
- `urn:issn:` - International Standard Serial Numbers  
- `urn:doi:` - Digital Object Identifiers
- `urn:ietf:` - Internet Engineering Task Force documents
- `urn:uuid:` - Universally Unique Identifiers

---

## Practical Applications

### When to Use URLs
- **Direct web navigation** - user needs to click and access immediately
- **API endpoints** - programmatic access to services
- **Short-term references** - temporary or frequently changing resources
- **Controlled environments** - you own the domain and can maintain redirects

### When to Use URNs
- **Long-term citations** - academic papers, legal documents
- **Standards references** - RFC documents, ISO standards
- **Digital preservation** - archival systems, libraries
- **Protocol identifiers** - SAML entity IDs, OAuth scopes
- **Cross-platform references** - identifiers that must work across different systems

### Comparison Table

| Aspect | URL | URN |
|--------|-----|-----|
| **Primary purpose** | Location + access method | Permanent identification |
| **Uniqueness basis** | DNS domain hierarchy | IANA namespace registry |
| **Stability** | Breaks when location changes | Designed for permanence |
| **Actionability** | Immediately clickable | Requires resolution service |
| **Best for** | Web navigation, APIs | Citations, standards, archives |

---

## Resolution and DOI Case Study

### DOI as Resolvable URN
The **Digital Object Identifier (DOI)** system demonstrates how URNs can be both permanent names and actionable links.

### DOI in Multiple Formats

| Format | Example | Purpose |
|--------|---------|---------|
| **Pure DOI** | `10.1038/s41586-025-00001-0` | Compact identifier |
| **DOI as URN** | `urn:doi:10.1038/s41586-025-00001-0` | Formal URN namespace |
| **Resolvable URL** | `https://doi.org/10.1038/s41586-025-00001-0` | Clickable link |

### How DOI Resolution Works
1. **User accesses DOI** (as URL or processes URN)
2. **Handle System lookup** - DOI resolver queries Handle System servers
3. **Redirect to current location** - HTTP 3xx redirect to publisher's current URL
4. **Resource accessed** - user reaches the actual content

### Benefits of DOI Approach
- **Permanent citations** - DOI never changes
- **Flexible hosting** - content can move between publishers
- **Immediate access** - works as clickable link
- **Global infrastructure** - managed by International DOI Foundation

### What Happens When Resources Move?
1. **Content transfer** - journal changes publishers
2. **Metadata update** - new host updates DOI record with new URL
3. **No citation changes** - existing DOI references continue to work
4. **Transparent to users** - resolution automatically goes to new location

---

## Design Guidelines

### Decision Framework

| Choose | When You Need | Notes |
|--------|---------------|-------|
| **URL** | Immediate retrieval over network protocol | Breaks if location changes |
| **URN** | Stable reference independent of location | Requires namespace registration |
| **Custom URI** | App-specific or protocol-specific identifiers | Define clear dereferencing rules |

### Encoding Requirements
- **Reserved characters** (`:/?#[]@!$&'()*+,;=`) must be percent-encoded when used as data
- **Unreserved characters** (A-Z, a-z, 0-9, -, ., _, ~) should remain unencoded
- **Non-ASCII characters** must be UTF-8 encoded then percent-encoded

### Percent-Encoding Example
Greek letter "ρ" (U+03C1):
1. UTF-8 bytes: `0xCF 0x81`
2. Percent-encoded: `%CF%81`

### Best Practices
1. **Choose the right tool** - URL for access, URN for citation
2. **Plan for persistence** - consider long-term maintenance
3. **Follow standards** - use registered namespaces when possible
4. **Provide resolution** - consider resolver services for URNs
5. **Document your choices** - explain identifier policies to users

---

## Summary and Key Takeaways

### The Three-Layer Model
1. **URI** - Generic framework for resource identification
2. **URL** - Specific type that includes location and access method
3. **URN** - Specific type that provides location-independent naming

### Critical Distinctions

| Characteristic | URL | URN |
|---------------|-----|-----|
| **Includes location** | Yes | No |
| **Includes access method** | Yes | No |
| **Designed for permanence** | No | Yes |
| **Immediately actionable** | Yes | Optional |
| **Requires registration** | No (uses DNS) | Yes (uses IANA) |

### Real-World Applications
- **Web browsing** - URLs for immediate access
- **Academic citations** - DOIs and other URNs for permanence
- **Legal documents** - URNs for stable references
- **Digital archives** - URNs for preservation
- **Mobile apps** - Custom URI schemes for deep linking

### Future Considerations
- **Link rot** - URLs break over time, URNs designed to persist
- **Resolution services** - Bridge between permanent names and current locations
- **Namespace evolution** - New domains require new registration approaches
- **Decentralized systems** - Blockchain and other technologies may create new identifier types

### Study Questions
1. What makes a URN different from a URL?
2. How does IANA ensure global uniqueness of URN namespaces?
3. Why might you choose a DOI over a regular URL for academic citations?
4. What are the components of a URI, and how do they differ between URLs and URNs?
5. How does the DNS system relate to URI uniqueness?

---

*These notes provide a comprehensive foundation for understanding web resource identifiers. For deeper study, consult RFC 3986 (URI specification), RFC 8141 (URN specification), and the IANA URN Namespaces registry.*