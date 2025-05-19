---
title: "NRPF Grants"
date: 2023-05-01
weight: 4
teaser: "The NRPF has awarded over a quarter of a million dollars to support the digitization and stewardship of at-risk audio collections."
permalink: "/programs/grants/"
layout: page
bodyClass: page-grants
jquery: true
countUp: true
---

In pursuing its mandate to preserve recorded sound heritage, the Foundation
awards grants to digitally preserve audio collections
that are stored on at-risk or obsolete physical media.
Since 2016, the Foundation has distributed over a quarter of a million dollars
to promote and preserve recorded sound history.

## Impact

How have our grants supported audio preservation? Take a look at the numbers:

{% include grants-impact.html %}

## Grants Awarded (since 2016)

{% assign grants = site.grants | where: "type", "grant" | sort: "year" | reverse %}

{% include grants-table-fromcollex.html %}

## Information for Applicants and Grantees

{% if site.data.nrpf_data.cfp == "active" %}
NRPF currently welcomes proposals for {{ site.data.nrpf_data.cfp-title }}. **[Please refer to details at the call for proposals]({{ site.baseurl }}{{ site.data.nrpf_data.cfp-relative-link }}). Applications are due {{ site.data.nrpf_data.cfp-deadline | date: "%B %e, %Y" }}.**
{% else %}
The Foundation does not currently have any open calls for proposals.
Please watch our press releases for annnouncements of any pending NRPF grant opportunities.
{% endif %}

Grant recipients should [refer to our grant policies page for more information on policies and reporting]({% link _pages/grant-policies.md %}).
