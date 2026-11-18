# Wireshark Display Filter Reference

## 1\. Purpose

This document records the Wireshark display filters used during the PCAP investigation.

The filters help isolate relevant network traffic for protocol inspection and investigation.

## 2\. HTTP Filters

### HTTP Requests

**Filter:**

http.request


**Purpose:**

Displays HTTP request packets.

**Project use:**

Used to identify HTTP requests, inspect GET methods, hostnames and request URIs.

## 3\. DNS Filters

### DNS Traffic

**Filter:**

dns


**Purpose:**

Displays packets identified as DNS traffic.

**Project use:**

Used to inspect DNS queries, responses, transaction IDs, response codes and DNS record information.

## 4\. Filter Usage Notes

* Display filters change which packets are visible, not the original capture contents.
* DNS queries and responses must be distinguished by inspecting packet details.
* HTTP requests should be examined for their hostnames, methods and destination addresses.
* A displayed packet is not automatically evidence of malicious activity.

## 5\. Reproducibility

To reproduce the filtering process:

1. Open `nb6-http.pcap` in Wireshark.
2. Locate the display filter bar.
3. Enter the required filter.
4. Press Enter.
5. Inspect the resulting packets and their Packet Details.

## 6\. Limitations

This reference contains the filters used in the current investigation. It is not intended to be a complete list of Wireshark display filters.

