# Active Scanning Techniques

This repository is a collection of different techniques in order to find specific hosts (with IPv4 and IPv6 addresses) to scan. The goal is to document the available techniques and improve the scanning for defenders.

## Why this collection?

- Finding vulnerable devices can be challenging for CSIRTs (waiting for the next scan in Shodan, Censys).
- Finding the scope of the scan (regional versus global, wrong IRR allocation).
- Discovering newly devices exposed without scanning the whole IPv4 space.
- Discovering named-based services (many services are based on name such as HTTP virtual-host, TLS SNI).
- Discovering newly exposed devices or services using IPv6 addresses.

# Overview

![](https://raw.githubusercontent.com/adulau/active-scanning-techniques/main/img/overview.png)

# Slides

- [Improving Internet Wide Scanning with Dynamic Scanning](https://github.com/adulau/active-scanning-techniques/blob/main/slides/active-scanning.pdf)

# Techniques

## (TAS.1) Certificate Transparency

### (TAS.1.1) Extract subjectAltName

- Resolving AAAA

	- Adding most common hostname  (short dictionary list)
	- DNS brute-forcing

		- SDBF
		- fierce
		- dnsenum

## (TAS.2) Newly registered domains

## (TAS.3) Passive DNS feed

### (TAS.3.1) Extract CNAME, RRNAME

### (TAS.3.2) Extract AAAA

## (TAS 4) BGP Monitoring

## (TAS 5) Discovering active IPv6 subnet from an IPv6 address

### (TAS 5.1) Finding CIDR from RIR whois

### (TAS 5.2) Active monitoring of public services logs (HTTP servers, public NTP servers)

## (TAS 6) Blackhole network monitoring

### (TAS 6.1) Extracting IPv6 addresses from GRE packets

### (TAS 6.2) All protocols extraction "tshark -n -r $FILENAME  -E separator="/n" -E occurrence=a -T fields -e ipv6.src ipv6.dst | sort -u | gzip -f
"

## (TAS 7) Bitorrent GET_PEERS N6 request

## (TAS 8) Guessing IPv6 addresses by using most common IPv6 manual allocations from an IPv6 subnet

### (TAS 8.1) Enumerating easy to remember hex block (CAFE, DEAD, BEEF, ABBA, FFFF, ....)

### (TAS 8.2) Enumerating TCP/UDP service port as last part

## (TAS 9) DomainClassifier extraction (brute-force extraction of potential hostnames)

### (TAS 9.1) GitHub commit streams

### (TAS 9.2) Active crawling from CT logs

### (TAS 9.3) Other sources such as social networks, pasties website, ....

## (TAS 10) Extract potential hostname from IPv4 reverse PTR

### (TAS 10.1) Enumerating IPv4/PTR

