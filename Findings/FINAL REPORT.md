# Network Traffic Investigation Report

## PCAP Analysis Using Wireshark

## 1\. Executive Summary

This investigation examined the supplied `nb6-http.pcap` sample using Wireshark.

The analysis focused on DNS and HTTP traffic, protocol identification, packet-level inspection, DNS and HTTP observations, destination address identification, candidate indicator extraction and chronological event documentation.

The capture contained observable DNS and HTTP activity involving IPv4 and IPv6 addresses. The packet evidence examined does not establish confirmed malicious activity or system compromise.

## 2\. Problem and Investigation Objective

The objective was to examine the supplied packet capture, understand the observed network communication and determine what conclusions could reasonably be supported by the available evidence.

The investigation aimed to demonstrate:

* Network traffic analysis
* Protocol identification
* DNS and HTTP inspection
* Wireshark display filtering
* DNS and HTTP evidence correlation
* Destination address identification
* Candidate IOC extraction
* Timeline construction
* Evidence handling and limitation assessment

## 3\. Scope

**Dataset:** `nb6-http.pcap`

**Analysis tool:** Wireshark

**Capture observations recorded:**

* 62 packets
* The capture spans approximately 16.767 seconds, based on the final packet's relative timestamp. 

&#x20;   Wireshark's Capture File Properties displayed the elapsed duration as 00:00:16.

* Ethernet link-layer encapsulation

The investigation was restricted to the supplied sample capture.

No unauthorized network traffic or external systems were investigated.

## 4\. Methodology

The investigation followed these stages:

1. Selected and documented the sample PCAP.
2. Calculated its SHA-256 hash.
3. Opened the capture in Wireshark and inspected capture properties.
4. Examined the Protocol Hierarchy.
5. Inspected selected packet details and protocol fields.
6. Applied HTTP and DNS display filters.
7. Examined DNS queries and responses.
8. Compared observed HTTP destinations with DNS address information.
9. Extracted candidate indicators.
10. Constructed a chronological investigation timeline.
11. Documented evidence limitations and conclusions.

## 5\. Evidence and Observations

### 5.1 Capture Overview

The capture contained 62 packets and approximately 16 seconds of recorded traffic.

The Protocol Hierarchy showed multiple protocol layers, including Ethernet, PPPoE, PPP, IPv4, IPv6, TCP, UDP, DNS, HTTP, L2TP and ICMP-related traffic.

### 5.2 DNS Observations

The DNS investigation identified 16 DNS packets, consisting of 8 queries and 8 responses.

The responses examined reported NOERROR.

Some responses contained no Answer Section. This was recorded as an observation and was not automatically classified as a DNS failure.

DNS records included IPv4 and IPv6 address information.

### 5.3 HTTP Observations

The `http.request` display filter identified three HTTP GET requests.

|Packet|Host|Destination|
|-:|-|-|
|10|`ncdn.nb6ds1.neubox.neuf.fr`|`93.17.156.250`|
|38|`ipv4.icanhazip.com`|`216.69.252.100`|
|56|`ipv6.icanhazip.com`|`2606:f200:0:7:bad:f00d:d00d:1`|

These entries represent observed HTTP requests and their destination addresses.

### 5.4 DNS and HTTP Correlation

The investigation compared DNS information with the destinations of the three HTTP requests.

DNS responses contained address information associated with the observed hosts.

However, DNS transaction IDs must be checked before describing a particular query and response as a confirmed matching transaction. For example, the recorded transaction IDs for packets 2 and 6 differ.

The investigation therefore avoids overstating DNS correlation.

### 5.5 Candidate Indicators

Candidate domains and IP addresses were extracted and documented separately in:

`IOC ASSESSMENT.md`

Their presence in the capture does not establish malicious reputation or compromise.

## 6\. Investigation Timeline

The chronological packet observations are documented in:

`INVESTIGATION TIMELINE.md`

The timeline records selected DNS and HTTP packets using their Wireshark relative timestamps.

It is limited to the selected packet events and does not represent every event in the capture.

## 7\. Analysis and Findings

The supplied capture demonstrates DNS resolution activity and HTTP GET requests involving IPv4 and IPv6 destinations.

The packet inspection also demonstrates the use of multiple network protocols and encapsulation layers.

The available evidence supports documenting the observed network activity and extracting candidate indicators.

It does not establish that the observed communication was malicious.

## 8\. Limitations

* The investigation is limited to one supplied PCAP.
* The capture may not represent all network activity.
* No endpoint investigation was performed.
* No system compromise was established.
* No malicious reputation was confirmed for the candidate indicators.
* Some DNS responses contained no Answer Section.
* DNS transaction matching requires transaction-level verification.
* The capture does not establish the intent of the network communication.
* The raw PCAP is not included in the public repository because redistribution permission was not established.

## 9\. Conclusion

The investigation successfully documented DNS and HTTP activity within the supplied PCAP using Wireshark.

It identified three HTTP GET requests, examined DNS responses, recorded destination addresses, extracted candidate indicators and constructed a chronological timeline.

The evidence supports a description of the observed network communication. It does not support a conclusion that malicious activity or system compromise occurred.

## 10\. Recommendations

* Preserve the original PCAP and its integrity information.
* Retain packet-level evidence for important observations.
* Verify DNS transaction IDs before claiming query-response matches.
* Treat observed domains and IP addresses as candidate indicators until independently validated.
* Use additional authorized evidence sources if a broader security assessment is required.

## 11\. Supporting Project Documents

* `DATASET\\\\\\\_NOTES.md`
* `IOC ASSESSMENT.md`
* `INVESTIGATION TIMELINE.md`
* `Docs/INVESTIGATION METHODOLOGY.md`
* `Docs/REPRODUCIBILITY.md`
* `Evidence/`

