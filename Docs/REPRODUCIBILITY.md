# Investigation Reproducibility Guide

## 1\. Purpose

This document explains how to reproduce the main steps of the PCAP investigation using the same sample capture and Wireshark.

## 2\. Dataset

* Dataset: `nb6-http.pcap`
* Source: Wireshark Sample Captures
* File size: 8.60 KB
* Packet count: 62
* Capture duration: Reported as approximately 16 seconds
* Link-layer type: Ethernet

The original PCAP is not included in this repository because redistribution permission was not established. Obtain the capture from its original source before reproducing the investigation.

## 3\. Required Tool

* Wireshark

Use a Wireshark installation capable of opening the supplied PCAP file.

## 4\. Reproduction Steps

### Step 1 — Open the Capture

1. Open Wireshark.
2. Select File → Open.
3. Locate `nb6-http.pcap`.
4. Open the capture.

### Step 2 — Verify Capture Properties

1. Open Statistics → Capture File Properties.
2. Inspect the packet count, capture duration and link-layer type.
3. Compare the results with the dataset notes.

### Step 3 — Inspect Protocol Distribution

1. Open Statistics → Protocol Hierarchy.
2. Review the protocols identified in the capture.
3. Compare the protocol distribution with the saved investigation evidence.

### Step 4 — Inspect HTTP Requests

1. Enter the display filter:

   `http.request`

2. Press Enter.
3. Inspect the HTTP request packets.
4. Review request methods, hostnames, request URIs and destination addresses.

### Step 5 — Inspect DNS Traffic

1. Replace the existing filter with:

   `dns`

2. Press Enter.
3. Inspect DNS queries and responses.
4. Review transaction IDs, response codes and answer records where present.

### Step 6 — Review DNS and HTTP Correlation

Compare the DNS information with the HTTP hostnames and destination addresses documented in the investigation.

Do not assume that two DNS packets belong to the same transaction without verifying their transaction IDs.

### Step 7 — Review Investigation Outputs

Review the following project documents:

* `DATASET\_NOTES.md`
* `Filters/WIRESHARK FILTERS.md`
* `Findings/IOC\_ASSESSMENT.md`
* `Findings/INVESTIGATION TIMELINE.md`
* `Findings/FINAL REPORT.md`
* `Docs/INVESTIGATION METHODOLOGY.md`

## 5\. Evidence

The investigation's supporting evidence is stored in the `Evidence/` directory.

Use the saved screenshots and exported protocol information to compare reproduced observations with the original analysis.

## 6\. Integrity Note

The SHA-256 hash calculated during the original investigation was:

`8AF47406B623A45C2523BA3CA230D4B7B61F15C9C1DD85411A5F5E6F9210D0DF`

This records the hash calculated for the original local file. It is not an independently verified publisher checksum.

## 7\. Reproducibility Limitations

* The original PCAP is not included in the repository.
* The capture's redistribution permission was not established.
* Results should be compared using the same original capture.
* Differences in Wireshark versions or protocol dissectors may affect presentation.
* Reproducing observations does not independently establish malicious activity.

## 8\. Reproducibility Conclusion

The documented procedure provides a repeatable approach for opening the sample capture, reviewing its protocol distribution, applying the investigation filters and examining the DNS and HTTP evidence.

