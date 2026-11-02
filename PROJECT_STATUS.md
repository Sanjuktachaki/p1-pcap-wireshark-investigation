# P1 — PCAP / Wireshark Investigation

## Project Status

* **Project:** P1 — PCAP / Wireshark Investigation
* **Current week:** W8
* **Project dates:** 19 October–21 November 2026
* **Current milestone:** M1 — Project setup and dataset approval
* **Status:** In progress
* **Technical investigation started:** No

## Completed Tasks

* Project scope and planning requirements defined.
* Initial milestone plan established.
* Created the project workspace and initial PROJECT\_STATUS.md
* Opened the official Wireshark Sample Captures page and confirmed that sample captures are available.
* Reviewed the available capture names and descriptions in the Wireshark Sample Capture page.
* Identified nb6-startup.pcap and reviewed its published description.
* Compared candidate capture descriptions against beginner suitability and P1 scope.
* Downloaded the candidate nb6-http.pcap from the official Wireshark Sample Captures page.
* Located nb6-http.pcap in Downloads and copied its file path.
* Calculated and recorded the SHA-256 hash of nb6-http.pcap.
* Confirmed Git installation and identified the local project directory.
* Committed the initial PROJECT\_STATUS.md.
* Created the initial dataset record using the reported file metadata and SHA-256 baseline.
* Created DATASET\_NOTES.md.
* Reviewed the official Wireshark capture description and source information.
* Recorded the initial SHA-256 hash.
* Confirmed the raw PCAP is excluded from Git changes.

## Pending Tasks

* Perform packet analysis and document evidence.
* Complete the report and publication checks.

## Decisions

* Timeline is fixed to W8–W12.
* Weekly time budget is 7–14 hours.
* Project scope is restricted to network traffic and packet analysis.
* Only safe, authorized datasets will be used.
* Wireshark Sample Captures is the initial source for dataset discovery: no capture has been selected, downloaded or analyzed.
* Preferred candidate: nb6-http.pcap.
* Reason: focused comparison of HTTP traffic across private IPv4, public IPv4 and public IPv6/L2TP contexts.
* Approval status: pending reuse-terms verification and dataset acquisition; no packets analyzed; no findings or IOCs established.
* Primary dataset: nb6-http.pcap.
* Approved for local educational analysis.
* Raw PCAP will not be redistributed through GitHub.
* GitHub publication will link to the original Wireshark source.

## Initial technical inspection

* **Status:** Completed
* **Dataset:** nb6-http.pcap
* **Packet count:** 62
* **Capture duration:** 16 seconds
* **Encapsulation:** Ethernet
* **Wireshark opening errors:** None reported
* **Raw PCAP:** Not committed

## Protocol hierarchy analysis

* **Status:** Completed
* **Total frames:** 62
* **Ethernet:** 62 packets
* **IP:** 46 packets
* **Additional protocols identified:** TCP, IPv6, ICMP, L2TP, LCP, UDP, HTTP, PPP, PPPoE and DNS
* **Packet-level interpretation:** Pending

## GitHub Status

* Local Git repository: Initialized and verified.
* Initial commit: Completed.
* Local repository initialized.
* Dataset documentation committed, according to your report.
* Raw PCAP excluded.

## LinkedIn Status

* No post planned before meaningful work is verified.

## Interview Readiness

* Not yet assessed for this project.

## Next Task

* Verify the local project workspace and initial status file.

