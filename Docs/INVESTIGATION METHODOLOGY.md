# Investigation Methodology

## 1\. Purpose

This document describes the methodology used to investigate the supplied `nb6-http.pcap` sample using Wireshark.

The purpose is to explain the investigation process, evidence collection approach, packet inspection methods and reasoning used to document observations.

## 2\. Investigation Scope

* **Dataset:** `nb6-http.pcap`
* **Analysis tool:** Wireshark
* **Traffic examined:** DNS, HTTP and relevant supporting protocols
* **Environment:** Authorized sample PCAP analysis
* **Scope restriction:** Analysis was limited to the supplied capture.

No unauthorized network traffic or external systems were examined.

## 3\. Evidence Preservation

The original PCAP was retained as the source evidence.

The SHA-256 hash was calculated to record the file's integrity reference.

The original capture was not modified during analysis.

The raw PCAP was excluded from the public repository because redistribution permission for the individual capture file was not established.

## 4\. Initial Triage

The capture was opened in Wireshark.

The following information was examined:

* Capture packet count
* Capture duration
* Link-layer type
* Capture errors and warnings
* Protocol Hierarchy

These checks established an initial understanding of the dataset before focused packet inspection.

## 5\. Protocol Inspection

Selected packets were inspected through Wireshark's Packet Details pane.

The investigation included:

* PPP and LCP field inspection
* DNS query and response inspection
* HTTP request inspection
* IPv4 and IPv6 destination address identification

Protocol fields were recorded from the packet details rather than inferred from packet numbers alone.

## 6\. Display Filter Usage

Wireshark display filters were used to narrow the capture to relevant traffic.

The investigation used HTTP and DNS filtering to identify requests, queries and responses.

The filter reference will be maintained separately in:

`../Filters/WIRESHARK FILTERS.md`

## 7\. DNS and HTTP Analysis

DNS observations were compared with HTTP request hostnames and destination addresses.

DNS transaction IDs were considered when evaluating query-response relationships.

Responses without an Answer Section were recorded as observations and were not automatically treated as failures.

HTTP methods, hostnames, request URIs and destination addresses were recorded from the selected packets.

## 8\. IOC Extraction

Observed domains and IP addresses were recorded as candidate indicators.

Their presence in the capture was not treated as proof of malicious activity.

The candidate indicator inventory and assessment are maintained in:

`../Findings/IOC ASSESSMENT.md`

## 9\. Timeline Construction

Selected packet timestamps were collected from Wireshark's Time column.

The selected DNS and HTTP packet events were arranged chronologically.

The completed timeline is maintained in:

`../Findings/INVESTIGATION TIMELINE.md`

Only observations supported by packet evidence were included.

## 10\. Findings and Reporting

The investigation observations, analysis, limitations and conclusions were consolidated into:

`../Findings/FINAL REPORT.md`

The report distinguishes observed network activity from confirmed security findings.

## 11\. Limitations

* The investigation is limited to one supplied PCAP.
* The capture may not represent all network activity.
* Packet observations alone do not establish malicious intent.
* No endpoint compromise was confirmed.
* Candidate indicators were not independently established as malicious.
* DNS correlation requires transaction-level verification.
* The investigation does not establish the full context or intent of the observed communications.

## 12\. Conclusion

The methodology provided a structured process for examining the supplied PCAP, preserving evidence, inspecting DNS and HTTP traffic, extracting candidate indicators and constructing a chronological timeline.

The process prioritizes evidence-based observations, cautious interpretation and transparent limitations.

