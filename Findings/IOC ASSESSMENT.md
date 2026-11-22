# Candidate IOC Assessment

**Project:** P1 — PCAP / Wireshark Investigation  
**Capture:** `nb6-http.pcap`  
**Assessment:** Candidate network indicators; maliciousness not
established

## 1\. Objective

This document records and assesses network indicators identified during
analysis of the `nb6-http.pcap` sample capture.

The purpose is to:

* preserve the exact domains and IP addresses observed in DNS and HTTP
traffic;
* identify the packet-level evidence supporting each value;
* assess the strength and limits of the observed relationships; and
* state what can and cannot be concluded from this capture.

**Assessment boundary:** An indicator appearing in a packet capture is
not, by itself, proof that the indicator is malicious or that a system
has been compromised. All values in this document are treated as
candidate indicators for further investigation, not confirmed malicious
indicators.

## 2\. Scope and evidence basis

* **Capture file:** `nb6-http.pcap`
* **Capture SHA-256:**
`8AF47406B623A45C2523BA3CA230D4B7B61F15C9C1DD85411A5F5E6F9210D0DF`
* **Analysis tool:** Wireshark
* **Relevant protocols:** DNS, HTTP, IPv4 and IPv6
* **HTTP requests observed:** 3 GET requests — packets 10, 38 and 56
* **DNS inventory:** 16 DNS packets — 8 queries and 8 responses
* **Assessment type:** Candidate network-indicator assessment
* **Maliciousness verdict:** Not established by this capture

This assessment is based on packet observations recorded during the
investigation. It does not include independent reputation checks,
threat-intelligence enrichment, endpoint telemetry, or confirmation from
the systems involved.

## 3\. Assessment terminology

* **Observed:** Directly visible in the capture, such as a DNS question,
DNS answer, HTTP Host value or packet destination address.
* **Associated:** Two observations appear related based on the available
packet evidence. The basis and any correlation limitation must be
stated.
* **Candidate indicator:** A domain or IP address worth retaining as an
investigation pivot. This label does not mean the value is malicious.
* **Confirmed malicious indicator:** A value independently established
as malicious using reliable supporting evidence. No indicator in this
assessment meets that standard.
* **Confidence:** Confidence in the stated packet-level observation or
association. It is not a rating of how likely the indicator is
malicious.

## 4\. Candidate indicator assessment

Six candidate indicators were retained: three domains and three IP
addresses. The evidence and assessment for each are recorded separately
below. This format is used instead of a wide Markdown table so the
document remains readable in GitHub and in plain-text editors such as
Windows Notepad.

### 4.1 Domain — `ncdn.nb6ds1.neufbox.neuf.fr`

* **Type:** Domain
* **Packet evidence:** Packets 2 and 10
* **Observed activity:**

  * Packet 2 contains an AAAA DNS respond for this domain, transaction ID
`0x0002`.
  * Packet 10 contains an HTTP GET request whose Host value is this
domain.
* **Assessment:** High confidence that the domain appears in both DNS
and HTTP observations.
* **Correlation limitation:** Packet 6 has transaction ID `0x0004`, not
`0x0002`, and its answer name is `http.service-ncdn.sfr.net`. 
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.2 IPv4 address — `93.17.156.250`

* **Type:** IPv4 address
* **Packet evidence:** Packets 6 and 10
* **Observed activity:**

  * Packet 6 includes this address in DNS A-record answer data for
`http.service-ncdn.sfr.net`.
  * Packet 10 has this address as the HTTP destination.
* **Assessment:** High confidence that the address appears in DNS answer
data and as the destination of packet 10.
* **Correlation limitation:** The DNS answer name in packet 6 differs
from the HTTP Host value in packet 10. Do not claim that packet 6
directly resolved `ncdn.nb6ds1.neufbox.neuf.fr`.
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.3 Domain — `ipv4.icanhazip.com`

* **Type:** Domain
* **Packet evidence:** Packets 33 and 38
* **Observed activity:**

  * Packet 33 contains DNS A-record answer data for this domain.
  * Packet 38 contains an HTTP GET request whose Host value is this
domain.
* **Assessment:** High confidence that DNS and HTTP activity for this
domain are both present in the capture.
* **Correlation limitation:** This assessment records the observed DNS
and HTTP evidence; it does not establish malicious intent.
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.4 IPv4 address — `216.69.252.100`

* **Type:** IPv4 address
* **Packet evidence:** Packets 33 and 38
* **Observed activity:**

  * Packet 33 includes this address in DNS A-record answer data.
  * Packet 38 has this address as the HTTP destination.
* **Assessment:** High confidence that the address appears in DNS answer
data and as the HTTP destination for packet 38.
* **Correlation limitation:** The observed DNS answer and HTTP
destination support an association in this packet sequence; they do
not establish malicious intent.
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.5 Domain — `ipv6.icanhazip.com`

* **Type:** Domain
* **Packet evidence:** Packets 52 and 56
* **Observed activity:**

  * Packet 52 contains DNS AAAA answer data for this domain.
  * Packet 56 contains an HTTP GET request whose Host value is this
domain.
* **Assessment:** High confidence that DNS and HTTP activity for this
domain are both present in the capture.
* **Correlation limitation:** This assessment records the observed DNS
and HTTP evidence; it does not establish malicious intent.
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.6 IPv6 address — `2606:f200:0:7:bad:f00d:d00d:1`

* **Type:** IPv6 address
* **Packet evidence:** Packets 52 and 56
* **Observed activity:**

  * Packet 52 includes this address in DNS AAAA answer data.
  * Packet 56 has this address as the HTTP destination.
* **Assessment:** High confidence that the address appears in DNS answer
data and as the HTTP destination for packet 56.
* **Correlation limitation:** The observed DNS answer and HTTP
destination support an association in this packet sequence; they do
not establish malicious intent.
* **Disposition:** Retain as a candidate indicator. Maliciousness is not
established.

### 4.7 Inventory summary

* **Domains:** `ncdn.nb6ds1.neufbox.neuf.fr`, `ipv4.icanhazip.com`,
`ipv6.icanhazip.com`
* **IPv4 addresses:** `93.17.156.250`, `216.69.252.100`
* **IPv6 addresses:** `2606:f200:0:7:bad:f00d:d00d:1`
* **Confirmed malicious indicators:** None

## 5\. DNS and HTTP correlation notes

Correlation must be based on actual packet fields and DNS transaction
identifiers, not merely on nearby packet numbers or similar-looking
domain names.

### 5.1 `ncdn.nb6ds1.neubox.neuf.fr` — correlation limitation

* Packet 2 is an AAAA DNS respond for `ncdn.nb6ds1.neufbox.neuf.fr`,
transaction ID `0x0002`.
* Packet 6 is a DNS response with transaction ID `0x0004`; it contains A
records for `http.service-ncdn.sfr.net`, including `93.17.156.250`.
* Packet 10 is an HTTP GET whose Host value is
`ncdn.nb6ds1.neubox.neuf.fr`, with destination `93.17.156.250`.

The appearance of `93.17.156.250` as the packet 10
destination is an observation, but the available evidence does not
establish a direct DNS resolution of the packet 10 Host value by packet
6.

### 5.2 `ipv4.icanhazip.com`

* Packet 33 contains DNS A-record answer data for `ipv4.icanhazip.com`,
including `216.69.252.100`.
* Packet 38 is an HTTP GET for `ipv4.icanhazip.com`, with destination
`216.69.252.100`.

The domain and address are both directly observed in the DNS and HTTP
evidence cited above.

### 5.3 `ipv6.icanhazip.com`

* Packet 52 contains DNS AAAA answer data for `ipv6.icanhazip.com`,
including `2606:f200:0:7:bad:f00d:d00d:1`.
* Packet 56 is an HTTP GET for `ipv6.icanhazip.com`, with destination
`2606:f200:0:7:bad:f00d:d00d:1`.

The domain and address are both directly observed in the DNS and HTTP
evidence cited above.

## 6\. Overall assessment

Six candidate network indicators were extracted: three domain names and
three destination IP addresses.

The packet evidence establishes that these values appear in the recorded
DNS and HTTP activity, with the specific relationships and limitations
documented in the indicator assessments and correlation notes. The
evidence is sufficient to preserve the values as candidate indicators
and use them as pivots for further investigation.

**The capture does not establish that any of the six indicators is
malicious.** It also does not establish that the traffic represents
command-and-control, malware delivery, data exfiltration, unauthorized
access or a successful compromise. Such conclusions would require
additional evidence and independent validation.

**Assessment result:** Candidate indicators identified; maliciousness
and compromise not confirmed.

## 7\. Evidence limitations

1. **Single-capture scope:** The assessment is limited to packets
present in `nb6-http.pcap`. It cannot establish what happened before
or after the captured interval.
2. **No independent reputation validation:** No external
threat-intelligence or reputation source was used to establish
whether the domains or IP addresses are known malicious
infrastructure.
3. **No endpoint context:** The capture does not provide process, user,
file or host telemetry sufficient to identify which application
initiated the requests or whether a host was compromised.
4. **DNS correlation is not uniform:** The packet 2 and packet 6
transaction IDs differ, and packet 6 contains a different answer
name. That relationship must remain qualified.
5. **DNS response status is not a security verdict:** `NOERROR`
indicates a successful DNS response code; it does not prove that the
resulting activity is safe or malicious.
6. **Observed HTTP requests do not prove impact:** A captured GET
request does not, by itself, prove that the requested content was
successfully received, executed or caused harm.
7. **Indicator presence is not proof of compromise:** Domains and
addresses can be legitimate infrastructure, shared hosting or
ordinary service endpoints. Their presence alone is insufficient to
classify them as malicious.

## 8\. Recommended follow-up for a real incident

If this capture were part of an active incident investigation, the
following validation steps would be appropriate:

* Check the exact domains and IP addresses against approved, reputable
threat-intelligence sources, recording the source and lookup date.
* Compare the network observations with endpoint process and connection
telemetry from the relevant host.
* Review the full HTTP request and response context where available,
rather than relying only on the request line and destination.
* Establish whether the activity was expected for the system and user
involved.
* Preserve any additional evidence and record whether independent
sources corroborate or contradict the initial assessment.

These are recommendations for further validation, not actions performed
as part of this PCAP analysis.

## 9\. Conclusion

The investigation identified three domains and three IP addresses as
candidate network indicators based on observed DNS and HTTP packets. The
packet-level evidence and correlation limitations are documented above.

No listed indicator is confirmed malicious, and the available capture
does not establish a security compromise.

