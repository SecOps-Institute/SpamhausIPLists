# ![alt text](https://www.spamhaus.org/images/sh_logo2.jpg)
# The Spamhaus Don't Route Or Peer Lists
## Daily Checked and Updated

The Spamhaus DROP (Don't Route Or Peer) lists are advisory "drop all traffic" lists, consisting of netblocks that are "hijacked" or leased by professional spam or cyber-crime operations (used for dissemination of malware, trojan downloaders, botnet controllers). The DROP lists are a tiny subset of the SBL, designed for use by firewalls and routing equipment to filter out the malicious traffic from these netblocks. 

## Spamhaus Don't Route Or Peer List (DROP)

The DROP list will not include any IP address space under the control of any legitimate network - even if being used by "the spammers from hell". DROP will only include netblocks allocated directly by an established Regional Internet Registry (RIR) or National Internet Registry (NIR) such as ARIN, RIPE, AFRINIC, APNIC, LACNIC or KRNIC or direct RIR allocations.

## Spamhaus Extended DROP List (EDROP) --> TO DO
EDROP is an extension of the DROP list that includes suballocated netblocks controlled by spammers or cyber criminals. EDROP is meant to be used in addition to the direct allocations on the DROP list.

## Spamhaus IPv6 DROP List (DROPv6) --> TO DO
The DROPv6 list includes IPv6 ranges allocated to spammers or cyber criminals. DROPv6 will only include IPv6 netblocks allocated directly by an established Regional Internet Registry (RIR) or National Internet Registry (NIR) such as ARIN, RIPE, AFRINIC, APNIC, LACNIC or KRNIC or direct RIR allocations.

## Spamhaus ASN DROP List (ASN-DROP) --> TO DO
ASN-DROP contains a list of Autonomous System Numbers controlled by spammers or cyber criminals, as well as "hijacked" ASNs. ASN-DROP can be used to filter BGP routes which are being used for malicious purposes. 

## Implementation
When implemented at a network or ISP's 'core routers', the Spamhaus DROP lists will help protect the network's users from spamming, scanning, harvesting, DNS-hijacking and DDoS attacks originating on rogue netblocks.

Spamhaus strongly encourages the use of the DROP lists by tier-1s and backbones.

Spamhaus DROP lists are available in text format. Additionally, these lists (as well as the Spamhaus Botnet C&C list) are available by [Spamhaus BGP Feed](https://www.spamhaus.org/bgpf/) announced via an Autonomous System Number (ASN). Users can choose to peer with that ASN to null those prefixes as being ranges for which they do not wish to route traffic.

See the [DROP FAQ](https://www.spamhaus.org/faq/section/DROP%20FAQ) for information on use and implementation.

My Profile: https://www.linkedin.com/in/aarvee11
My Blog: https://amisafe.secops.in
