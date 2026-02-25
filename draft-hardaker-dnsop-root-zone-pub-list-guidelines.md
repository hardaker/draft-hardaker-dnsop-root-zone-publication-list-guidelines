---
title: "Guidelines for IANA DNS Root Zone Publication List Providers"
abbrev: "DNS Root Zone Publication List Guidelines"
category: info

docname: draft-hardaker-dnsop-root-zone-pub-list-guidelines-latest
submissiontype: IETF
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Domain Name System Operations"
keyword:
 - DNS
 - DNSSEC
 - zone transfer
 - axfr
 - ixfr
venue:
  group: "Domain Name System Operations"
  type: "Working Group"
  mail: "dnsop@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/dnsop/"
  github: "https://github.com/hardaker/draft-hardaker-dnsop-root-zone-publication-list-guidelines"
  latest: "https://github.io/hardker/draft-hardaker-dnsop-root-zone-publication-list-guidelines/draft-hardaker-dnsop-root-zone-publication-list-guidelines.html"

author:
  -
    fullname: Wes Hardaker
    organization: Google, Inc.
    email: ietf@hardakers.net
  -
    fullname: Warren Kumari
    organization: Google, Inc.
    email: warren@kumari.net

normative:
  RFC3986:
  RFC4395:
  RFC5234:
  RFC5936:  # DNS Zone Transfer
  RFC8499:
  RFC9103:
  draft-wkumari-dnsop-localroot-bcp:
    target: draft-hardaker-dnsop-dns-xfr-scheme
    title: Running a Root Server Local to a Resolver

informative:
  RFC7766:  # DNS Transport over TCP
  draft-hardaker-dnsop-iana-root-zone-publication-points:
    title: A format for publishing a list of sources of IANA root zone data
    target: https://github.com/hardaker/draft-hardaker-dnsop-iana-root-zone-publication-points

--- abstract

This document describes guidelines for entities that wish to publish a
list of URLs from where the contents of the IANA DNS root zone may be
obtained.  These guidelines are specifically provided as guidance to
IANA, but these suggestions may be applicable to any entity wishing to
build a list of IANA DNS root zone sources for their own purposes.

--- middle

# Introduction

This document describes guidelines for entities that wish to publish a
list of URLs from where the contents of the IANA DNS root zone may be
obtained.  These guidelines are specifically provided as guidance to
IANA, but these suggestions may be applicable to any entity wishing to
build a list of IANA DNS root zone sources for their own purposes.

When implementing a LocalRoot or similar service, as described in
{{draft-wkumari-dnsop-localroot-bcp}}, the contents of the DNS root
zone need to be obtained.  Because the contents of the IANA DNS root
zone are crytographically verifiable, it may be obtained from any
source assuming integrity verification has been performed.

Entities, such as IANA, will need to publish a list of acceptable
sources that LocalRoot enabled resolvers can use to routinely
fetch and serve or cache the contents of the IANA DNS root zone.
The guidelines in this document are intended to provide advice to IANA
or any other entity wishing to build such a list of sources.

A separate document
{{draft-hardaker-dnsop-iana-root-zone-publication-points}} describes
the format of the IANA published list, along with IANA considerations
that request the list's publication.

# Conventions and Definitions {#definitions}

{::boilerplate bcp14-tagged}

# Guidelines for building a IANA DNS root zone publication list

The following describes the community established guidelines when
developing a list of IANA DNS root zone publication points:

## Guidelines related to the list of publication points

- the list of publication points must be machine readable.

- the list of publication points must not be limited to a particular size.

- the list of publication points should include publication points
  hosted from multiple organizations.

- the list of publication points should include a service endpoint
  from IANA itself.

- the list of publication points must be verifiable as complete
  through the use of a cryptographic checksum.

- the list of publication points should be cryptographically
  verifiable as to its origin.

- the list of publication points should include multiple protocols
  that can be used for fetching the IANA root zone data.  Specifically
  the list should include both https and AXFR based sources.

- each item in the list of publication points must be individually
  complete and usable in isolation.

- each item in the list of publication points must be a unique URL.

- the publication list should contain a variety of protocols for
  LocalRoot implementations to make use of based on implementation and
  operator preference.  For example, the list should contain URLs of
  "http", "https", "axfr", "xot" and "xoh" schemes if possible.

- each item in the list of publication points should be routinely
  verified as to its functioning status or else removed from the list.

## Guidelines related to entries in the list of publication points

- each publication point should make use of widely geographically
  distributed service points.

- each publication point must be globally available without imposed
  source-based or other filtering.

- https based publication points should offer service equivalent to
  existing Content Delivery Networks (CDNs) today.

- AXFR, IXFR and XoT publication points should be as robust as the
  existing DNS root servers that offer similar services today.

- each publication point should have a service level agreement,
  ideally at zero cost, with IANA.

# Security Considerations {#security}

TBD

# IANA Considerations

IANA may wish to carefully consider the suggestions in this document
when building a list of IANA DNS root zone publication points.

--- back

# Acknowledgments
{:numbered="false"}

TBD
