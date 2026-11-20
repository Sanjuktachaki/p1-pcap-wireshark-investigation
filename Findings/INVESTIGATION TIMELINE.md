# Investigation Timeline

## 1\. Objective

Construct a chronological timeline of relevant DNS and HTTP activity observed in the supplied PCAP.

## 2\. Time Reference

* **Dataset:** `nb6-http.pcap`
* **Timestamp source:** Wireshark Time column
* **Timestamp format:** Relative seconds
* **Capture duration:** 16 seconds

## 3\. Chronological Event Timeline

|Time (seconds)|Packet|Protocol|Observed Event|Evidence|
|-:|-:|-|-|-|
|0.033047|2|DNS|AAAA response for `ncdn.nb6ds1.neubox.neuf.fr`; transaction ID `0x0002`|DNS response details|
|0.099073|6|DNS|Response with A records including `93.17.156.249` and `93.17.156.250`; transaction ID `0x0004`|DNS response details|
|0.121887|10|HTTP|GET request to `ncdn.nb6ds1.neubox.neuf.fr`; destination `93.17.156.250`|HTTP request details|
|7.484055|31|DNS|Response with no Answer Section; NOERROR ; transaction ID '0x0a89'|DNS response details|
|7.502267|32|DNS|Response; transaction ID `0x56bb`;|DNS response details|
|7.573715|33|DNS|Response containing A records for `ipv4.icanhazip.com`, including `216.69.252.100` and `216.69.252.101`; NOERROR|DNS response details|
|7.752017|38|HTTP|GET request to `ipv4.icanhazip.com`; destination `216.69.252.100`|HTTP request details|
|16.110988|51|DNS|Response with no Answer Section; NOERROR|DNS response details|
|16.127497|52|DNS|AAAA response for `ipv6.icanhazip.com`; NOERROR|DNS response details|
|16.411100|56|HTTP|GET request to `ipv6.icanhazip.com`; destination `2606:f200:0:7:bad:f00d:d00d:1`|HTTP request details|

## 4\. Timeline Analysis

The capture contains DNS and HTTP activity across three chronological periods.

* The first period contains DNS activity involving `ncdn.nb6ds1.neubox.neuf.fr`, followed by an HTTP GET request.
* The second period contains DNS responses involving `ipv4.icanhazip.com`, followed by an HTTP GET request.
* The third period contains DNS activity involving `ipv6.icanhazip.com`, followed by an HTTP GET request.

The recorded DNS transaction IDs must be considered when correlating queries and responses. Packets 2 and 6 have different transaction IDs (`0x0002` and `0x0004`), so they are not established as a matching transaction by the evidence recorded here.

Some DNS responses contain no Answer Section despite reporting NOERROR. These observations are recorded without assuming that an address was returned.

The HTTP requests demonstrate observed communication with the listed hosts and destination addresses. Their presence alone does not establish malicious activity.

## 5\. Evidence Limitations

* The timeline is limited to the supplied PCAP.
* Only selected DNS and HTTP packets are included.
* Relative timestamps indicate packet timing within the capture, not absolute date and time.
* Some DNS responses contain no Answer Section.
* A matching DNS transaction must be established using transaction IDs and other packet details.
* The capture alone does not establish malicious activity or system compromise.

## 6\. Conclusion

The timeline records selected DNS and HTTP events in chronological order. The observed activity includes DNS responses and HTTP GET requests involving IPv4 and IPv6 destinations.

No confirmed malicious activity is established by the timeline evidence examined.

