<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 2.552 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β31
* Thu Jan 06 2022 02:41:31 GMT-0800 (PST)
* Source doc: ToIP Trust Registry V1 Specification—Working Draft

ERROR:
undefined internal link to this URL: "#heading=h.wkss4j4dw9a".link text: Trust Registry Service Property
?Did you generate a TOC?


ERROR:
undefined internal link to this URL: "#heading=h.wkss4j4dw9a".link text: Trust Registry Service Property
?Did you generate a TOC?


ERROR:
undefined internal link to this URL: "#heading=h.3347f9q1h53g".link text: Data Model
?Did you generate a TOC?

* This document has images: check for >>>>>  gd2md-html alert:  inline image link in generated source and store images to your server. NOTE: Images in exported zip file from Google Docs may not appear in  the same order as they do in your doc. Please check the images!

----->


<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 3; WARNINGs: 0; ALERTS: 6.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>


<h2>ToIP Trust Registry Protocol V1 Specification— \
Working Draft Deliverable</h2>


**_Editor’s Note: This is currently a Draft Deliverable of the [Trust Registry Task Force](https://wiki.trustoverip.org/display/HOME/Trust+Registry+Task+Force) of the ToIP Technology Stack Working Group. For more on the structure of this Task Force and purpose of this deliverable, please see the [TRTF home page](https://wiki.trustoverip.org/display/HOME/Trust+Registry+Task+Force). _**

**_Status—2021-09-16: This deliverable is currently a Community Review Draft. The Trust Registry Task Force meeting is now meeting as part of the Technology Architecture Task Force meetings on Thursdays from 07:00-8:00 PT / 15:00-16:00 UTC and again at 1:00-2:00PM PT / 21:00-22:00 UTC. See the [ToIP Calendar](https://wiki.trustoverip.org/display/HOME/Calendar+of+ToIP+Meetings) for Zoom meeting info._**

**_How to contribute: please add any comments or edits in Suggest Mode. The editors will periodically review and resolve new contributions._**

_NOTE: All diagrams developed by contributors should be accompanied by the source._

**Table of Contents**


[TOC]


<h2>Contributors</h2>


To comply with the intellectual property rights protections in[ the charter of the ToIP Foundation](https://docs.google.com/document/d/1hJ4YWH_efrYTRvzRI1N9YHwhUOyI_ScrPmI1D9T4_oc/edit?usp=sharing) (as required by all Joint Development Foundation projects hosted by the Linux Foundation), all contributors in any capacity to this Draft Deliverable MUST be current members of the ToIP Foundation. The following contributors each certify that they meet this requirement:

**Editors**



* [Darrell O'Donnell](https://wiki.trustoverip.org/display/~darrell.odonnell), Continuum Loop Inc.
* [Drummond Reed](https://wiki.trustoverip.org/display/~drummondreed), Evernym

**Contributors**



* Antti Kettunen
* Dan Bachenheimer, Accenture
* Eric Drury, Forth Consulting
* Jim St. Clair, Lumedic
* Sankarshan Mukhopadhyay, Dhiway
* Scott Perry, Scott S. Perry CPA
* Vikas Malhotra, WOPLLI Technologies

<h2>Terminology</h2>


In this document, the key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL", when appearing in ALL CAPITALS, are to be interpreted as described in[ RFC 2119](https://tools.ietf.org/html/rfc2119).

All other terms in **bold** will be defined in one or more ToIP glossaries in the process specified by the ToIP [Concepts and Terminology Working Group](https://wiki.trustoverip.org/pages/viewpage.action?pageId=65700).

<h2>Purpose</h2>


The purpose of this **ToIP specification** is to define a standard interoperable protocol for interacting with a global web of **peer trust registries**, each of which can answer queries about whether a particular **party** is trusted and authorized to perform a particular **action** in a particular **digital trust ecosystem**, as well as which **peer trust registries** trust each other.

<h2>Motivations</h2>


A core role within **Layer 4** of the **ToIP stack** is a **trust registry** (previously known as a **member directory**). This is a network service that enables the **governing authority** for an **ecosystem governance framework (EGF)** to specify what **governed parties** are authorized to perform what **actions** under the EGF. For example:



1. Which **issuers** are **authorized** to issue what types of **verifiable credentials**.
2. Which **verifiers** are **authorized** to request what types of **verifiable presentations**.
3. What other **governing authorities** are trusted to authorize which **parties** can perform what **actions** within their own **trust registries**.

As with all layers of the **ToIP stack**, the purpose of a **ToIP specification** is to enable the technical interoperability necessary to support **transitive trust** within and between different **trust communities** implementing the **ToIP stack**. In this case, the desired interoperability outcome is a common protocol that works between any number of decentralized **peer trust registries** operated by independent **governing authorities** representing multiple legal and business **jurisdictions**. One specific example of this need is the **digital trust ecosystem** defined by the [Interoperability Working Group for Good Health Pass](https://wiki.trustoverip.org/pages/viewpage.action?pageId=73790) (GHP). 

<h2>Conceptual Diagrams</h2>


Figure 1 represents a conceptual overview of a **digital trust ecosystem** that illustrates the central role of a **trust registry**.



{TODO: get image in - conceptual diag}


![alt_text](images/conceptual-model.png "image_tooltip")


**Figure 1: Overview diagram of key components of a digital trust ecosystem**



Figure 2 is a conceptual overview of a network of independent **trust registries** representing different **digital trust ecosystems**, all of which can interoperate using the ToIP Trust Registry Protocol to enable **transitive trust** across any two ecosystems.


{TODO: get image in - multiple registries}


![alt_text](images/network-of-trustregistries.png "network of peer trust registries")


**Figure 2: A network of trust registries who are all peers **

<h2>Scope</h2>


In the first version of this specification (V1), the following **requirements** represent specific limitations on scope. Subsequent versions MAY remove or revise these limitations.

The ToIP Trust Registry Protocol V1 defined in this specification:



1. SHALL support query operations for the current status of a **registry entry**.
2. SHALL NOT support query operations for the history of a **registry entry**. 
    1. This SHOULD be considered for V2.
3. SHALL NOT support query operations for metadata about a **trust registry**.
    2. This SHOULD be considered for V2, including such attributes as:
        1. Legal name of **trust registry** service
        2. Legal name of **trust registry** operator (if different)
        3. Description
        4. Language variants supported (for text items returned)
        5. List of **ecosystem governance frameworks** (EGFs) served (DID, name, supported **credential type URIs**, supported **presentation type URIs**)
4. SHALL NOT include support for a DIDComm interface, only a REST interface.
    3. A DIDComm interface SHOULD be included in V2.
5. SHALL NOT support the following capabilities, which should be considered in future versions:
    4. Automated **rules** processing.
    5. API-based operations for **registering parties**.
    6. An alternative architecture based on **chained credentials** as defined by the ToIP [Authentic Chained Data Container](https://wiki.trustoverip.org/display/HOME/ACDC+%28Authentic+Chained+Data+Container%29+Task+Force) (ACDC) specifications.

<h2>Governing Authorities</h2>


**Governing authorities** compliant with this specification:



1. MUST have exactly one **primary trust registry**.
2. MAY have zero or more **secondary trust registries**. (The **primary trust registry** plus all **secondary trust registries** are collectively the **authorized trust registries**.)
3. MUST publish an **EGF** that meets the **requirements** in:
    1. This specification.
    2. The [ToIP Governance Architecture Specification](https://wiki.trustoverip.org/pages/viewpage.action?pageId=71241). Note that this includes the requirement that the **EGF** and all **governed parties** (which includes **authorized issuers** and **authorized verifiers**) must be identified with a **DID**.
4. MUST publish, in the **DID document** associated with the **DID** identifying its **EGF**, a **service property **specifying the **service endpoint** for its **primary trust registry** that meets the **requirements** in the [Trust Registry Service Property](#heading=h.wkss4j4dw9a) section.
5. MUST publish in its **EGF** a list of any other EGFs governing **secondary trust registries.**
6. MUST specify in the EGF any additional **requirements** for an **authorized trust registry**, including:
    3. **Information trust requirements**.
    4. Technical **requirements**.
    5. Operational **requirements**.
    6. Legal contracts.
7. MUST specify in its **EGF** (or in any referenced **credential governance framework**) **requirements** for:
    7. An **authorized issuer**, including:
        1. The **EGF URI** that MUST be included as a **claim** in any authorized **credential**.
        2. The **credential type URI** that MUST be used for any authorized **credential**.
    8. An **authorized verifier**, including:
        3. The **presentation type URI** that an **authorized verifier** MUST use for any authorized **presentation request**.
8. SHOULD specify in the **EGF** the following **requirements** for an **authorized trust registry** and any **registered party** (i.e., issuer, verifier, or peer trust registry):
    9. The set of **DID methods** authorized for use in the ecosystem.
    10. The **requirements** to become authorized.
    11. How to request registration.
    12. The **requirements** for assignment of each **status value** for a **registry entry**.
    13. Access control mechanisms.
    14. How to request access.

<h2>Trust Registry Service Property</h2>


The **DID document** for the **DID** that identifies an **EGF** compliant with this specification MUST include a service property that meets the **requirements** [in section 5.4 of the W3C Decentralized Identifiers (DIDs) 1.0 specification](https://www.w3.org/TR/did-core/#services) plus the following additional **requirements**:



* The value of the `type` property MUST be `TrustRegistry`.
* The value of the `serviceEndpoint` property MUST be exactly one HTTPS URI.

<h2>Trust Registry Protocol</h2>


The authoritative technical specifications for the API calls in the ToIP Trust Registry Protocol V1 are specified in Appendix A (OpenAPI YAML file). This section contains a textual description of the **requirements**.

**Trust registries** implementing this protocol:



1. MUST maintain the service implementing this protocol at the HTTPS URI specified in the [Trust Registry Service Property](#heading=h.wkss4j4dw9a)_ section.
2. MUST return responses to queries for the **status value** of a **registry entry** that satisfies one or more of the following sets of query parameters:
    1. **Authorized issuers**: EGF URI, **credential type URI**, issuer URI
    2. **Authorized verifiers**: EGF URI, **presentation type URI**, verifier URI
    3. **Trusted peer registries for authorized issuers:** EGF URI, **credential type URI**, EGF URI
    4. **Trusted peer registries for authorized verifiers:** EGF URI, **presentation type URI**, EGF URI
3. MUST return responses using the data model specified in the [Data Model](#heading=h.3347f9q1h53g) section.
4. MUST return exactly one of the following **status values** for a **registry entry** satisfying the query parameters:
    5. `Not found`
    6. `Current`
    7. `Expired` (not renewed after the previous valid registration period)
    8. `Terminated` (voluntary termination by the **registered party**)
    9. `Revoked` (involuntary termination by the **governing authority**)
5. For queries returning a **status value** other than `Not Found`, the response MUST return the following values:
    10. The parameter values exactly as supplied in the query (so responses can be stateless).
    11. The **status value**.
    12. Exactly two **datetime values** conforming to the following requirements:
        1. The value labels MUST be:
            1. `AuthorizationStartDate`
            2. `AuthorizationEndDate`
        2. The values MUST be formatted to comply with [RFC 3339](https://tools.ietf.org/html/rfc3339) in the UTC/Z time zone with no offset.
        3. The `AuthorizationStartDate` MUST be the date that the **registered party’s** authorization began.
        4. The `AuthorizationEndDate` MUST be either:
            3. `Null` for an entry whose **status value** is `Current` at the time of the query.
            4. A specific date value if the **registered party’s** **status value** is `Expired`, `Terminated` or `Revoked.`
        5. If a **registered party** has multiple entries (representing an authorization history), the most recent value MUST be returned.

<h2>Data Model</h2>


The authoritative technical specifications for the data model for requests and responses in the ToIP Trust Registry Protocol V1 are specified in Appendix A ([OpenAPI YAML file](https://github.com/trustoverip/tswg-trust-registry-tf/blob/main/api/toip.trustregistry.api.yaml)). This section contains a textual description of the requirements.




![alt_text](images/data-model-text.png "image_tooltip")


<h2>APPENDIX A: OpenAPI Specification</h2>


The OpenAPI YAML file can be found here: [https://github.com/trustoverip/tswg-trust-registry-tf/blob/main/api/toip.trustregistry.api.yaml](https://github.com/trustoverip/tswg-trust-registry-tf/blob/main/api/toip.trustregistry.api.yaml) 

<&lt;TODO: to replace with a tagged commit once we have “locked” things down.>>
