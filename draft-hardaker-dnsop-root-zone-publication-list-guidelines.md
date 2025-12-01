---
title: "The DNS XFR URI Schemes"
abbrev: "DNS XFR URI Schemes"
category: info

docname: draft-hardaker-dnsop-root-zone-publication-list-guidelines-latest
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

--- abstract

This document describes guidelines for entities that wish to publish a
list of URLs from where the contents of the IANA DNS root zone may be
obtained.  These guidelines are specifically suggested to IANA, but
may be applicable to any entity wishing to build a list of IANA DNS root zone
sources.

--- middle

# Introduction

This document describes guidelines for entities that wish to publish a
list of URLs from where the contents of the IANA DNS root zone may be
obtained.

When implementing a LocalRoot or similar service, as described in
{{draft-wkumari-dnsop-localroot-bcp}}, the contents of the DNS root
zone need to be obtained.  Because the contents of the IANA DNS root
zone are crytographically verifiable, it may be obtained from any
source.

Entities, such as IANA, will need to publish a list of acceptable
sources when they expect LocalRoot enabled DNS resolvers to routine
fetch and serve or cache the contents of the IANA DNS root zone.
The guidelines in this document are intended to provide advice to IANA
or any other entity wishing to build such a list of sources.

# Conventions and Definitions {#definitions}

{::boilerplate bcp14-tagged}

# Guidelines for building a IANA DNS root zone publication list



# Security Considerations {#security}



# IANA Considerations

IANA may wish to carefully consider the suggestions in this document
when building a list of IANA DNS root zone publication points.

--- back

# Acknowledgments
{:numbered="false"}

TBD
