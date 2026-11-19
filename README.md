# PCAP Network Traffic Investigation Using Wireshark

## Project Overview

This project demonstrates a structured investigation of a sample network packet capture (PCAP) using Wireshark.

The investigation focuses on network protocol analysis, HTTP requests, DNS activity, DNS/HTTP correlation, indicator extraction, timeline construction and evidence-based reporting.

## Objectives

* Understand the structure of a PCAP file.
* Inspect network protocols using Wireshark.
* Apply display filters to isolate relevant traffic.
* Analyse HTTP requests and DNS queries and responses.
* Correlate observed DNS information with HTTP destinations.
* Extract and assess candidate indicators of compromise (IOCs).
* Construct an investigation timeline.
* Document findings, limitations and conclusions.

## Dataset

* Capture: `nb6-http.pcap`
* Source: Wireshark Sample Captures
* Packets: 62
* Reported capture duration: approximately 16 seconds
* Link-layer type: Ethernet

The original PCAP is not included in this repository because redistribution permission was not established.

## Tools Used

* Wireshark
* GitHub Desktop
* Git
* Markdown

## Investigation Process

1. Dataset selection and integrity recording.
2. Initial PCAP inspection.
3. Protocol hierarchy analysis.
4. HTTP request inspection.
5. DNS query and response analysis.
6. DNS/HTTP correlation.
7. Endpoint and destination analysis.
8. Candidate IOC extraction and assessment.
9. Investigation timeline construction.
10. Final report and reproducibility documentation.

## Key Observations

The investigation identified:

* Three HTTP GET requests.
* DNS query and response activity associated with the observed HTTP hostnames.
* IPv4 and IPv6 destination addresses.
* DNS responses with NOERROR status.
* DNS responses without an Answer section.
* Candidate indicators documented for further assessment.

The observed indicators were not classified as confirmed malicious based solely on this capture.

## Repository Structure


p1-pcap-wireshark-investigation/
├── README.md

├── .gitattributes
├── PROJECT\_STATUS.md
├── DATASET\_NOTES.md
├── Docs/
├── Evidence/
├── Filters/
└── Findings/

## Main Investigation Documents

* `DATASET\_NOTES.md` — dataset information and initial observations.
* `Docs/INVESTIGATION METHODOLOGY.md` — investigation methodology.
* `Docs/REPRODUCIBILITY.md` — reproduction procedure.
* `Filters/WIRESHARK FILTERS.md` — display filters used.
* `Findings/IOC\_ASSESSMENT.md` — candidate indicator assessment.
* `Findings/INVESTIGATION TIMELINE.md` — selected packet events and timestamps.
* `Findings/FINAL REPORT.md` — final investigation report.

## Evidence

Screenshots and supporting investigation evidence are stored in the `Evidence/` directory.

## Limitations

* The investigation is limited to the supplied sample capture.
* A PCAP represents only the traffic available within that capture.
* Observed domains and IP addresses are not automatically malicious.
* DNS responses without Answer sections require careful interpretation.
* No conclusion about compromise or malicious activity should be made from these observations alone.
* The original PCAP is not redistributed with this repository.

## Conclusion

This project demonstrates a structured, evidence-based approach to analysing a sample network capture using Wireshark.

It documents protocol inspection, filtering, DNS and HTTP analysis, indicator assessment, timeline construction, investigation limitations and reproducibility.

The conclusions are restricted to the evidence available in the sample PCAP.

## Author

Cybersecurity Portfolio Project — PCAP / Wireshark Investigation

