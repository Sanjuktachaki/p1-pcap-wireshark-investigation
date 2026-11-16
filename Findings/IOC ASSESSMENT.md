# IOC Extraction and Assessment

## 1\. Objective

Identify observable indicators from the PCAP investigation and assess what the available packet evidence supports.

## 2\. Candidate Indicator Inventory

|Indicator Type|Indicator|Evidence|
|-|-|-|
|Domain|ncdn.nb6dsl.neufbox.neuf.fr|HTTP/DNS packets|
|Domain|ipv4.icanhazip.com|HTTP/DNS packets|
|Domain|ipv6.icanhazip.com|HTTP/DNS packets|
|IPv4|93.17.156.250|HTTP packet 10|
|IPv4|216.69.252.100|HTTP packet 38|
|IPv6|2606:f200:0:7:bad:f00d:d00d:1|HTTP packet 56|

## 3\. Assessment

The listed values were observed in the capture and are recorded as candidate indicators.

Their presence alone does not establish malicious activity or compromise.

## 4\. Evidence Limitations

* The assessment is limited to the supplied PCAP.
* No malicious reputation is established by packet presence alone.
* The capture does not establish whether any system was compromised.
* The available evidence may not represent all network activity.

## 5\. Conclusion

Candidate indicators were extracted from observed HTTP and DNS activity. No confirmed malicious indicator is established by the packet evidence examined so far.

