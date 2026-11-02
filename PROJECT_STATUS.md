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

* Verify repository status before beginning packet analysis.
* Verify reuse terms and dataset source details.
* Approve and download the selected capture.
* Preserve the original and calculate its SHA-256 hash.
* Define the investigation question and begin packet analysis only after the dataset is verified.
* Define the investigation question.
* Preserve and verify the selected dataset.
* Perform packet analysis and document evidence.
* Complete the report and publication checks.

## Evidence

* No packet-analysis evidence collected yet.
* File properties reported by the user: nb6-http.pcap, 8.60 KB; size on disk 12.0 KB
* SHA-256 baseline: 8AF47406B623A45C2523BA3CA230D4B7B61F15C9C1DD85411A5F5E6F9210D0DF

## Findings

* No findings established.

## Tests

* No project tests performed yet.

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

## Limitations

* Dataset not yet selected.
* No investigation conclusions are available.
* Individual redistribution permission remains unconfirmed.
* Independent published-hash comparison has not been performed.

## Initial technical inspection

* &#x20;**Status:** Completed
* &#x20;**Dataset:** nb6-http.pcap
* &#x20;**Packet count:** 62
* &#x20;**Capture duration:** 16 seconds
* &#x20;**Encapsulation:** Ethernet
* &#x20;**Wireshark opening errors:** None reported
* &#x20;**Raw PCAP:** Not committed

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

