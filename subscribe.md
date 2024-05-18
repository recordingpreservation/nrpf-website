---
title: Subscribe to NRPF News
layout: page
description: Subscribe to Our Newsletter
bodyClass: page-about
---

We share information and updates about once per quarter in our email newsletter. If you are interested in learning more about the National Recording Preservation, please subscribe below:

{% include subscribe-form-substack %}

## Follow Us

**You can also follow us on social media! Find us on:**

<ul>
{% for social in site.data.social %}
 <li><a href="{{ social.link }}" title="Follow us on {{ social.name }}">{{ social.name }}</a></li>
{% endfor %}
</ul>
