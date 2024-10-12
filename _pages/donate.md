---
title: Support the NRPF
layout: page
permalink: "/donate/"
description: Donate to the National Recording Preservation Foundation
bodyClass: page-about
image: images/illustrations/gramophone-left-cropped-12040507v.jpg
---

Consider donating to the National Recording Preservation Foundation! Support at any level allows us to increase our work to preserve at-risk audio collections, share and interpret historic recordings, and promote these histories with new audiences.

You can give directly today using the donation form below. Note that the form may require you to complete a captcha. The form and payment processing are powered by our non-profit partner, GiveLively:

{% include give-lively-widget %}


## Note about payment processing

Payments via GiveLively are processed via **Stripe** and subject to their non-profit fee schedule. Want to pay via **PayPal**? Visit our [GiveLively dedicated page](https://secure.givelively.org/donate/national-recording-preservation-foundation), choose an amount, and select the One Time giving option.

# Other ways to give

For larger donations, or to avoid processing fees, please consider sending
a check or bank transfer.
To facilitate proper acknowledgement for our records and tax purposes,
please ensure that you share contact information to NRPF.

Checks can be sent by mail to:

{{ site.data.contact.address }}

{% if site.data.contact.bank_account %}
Bank transfers may use the following information:

|| Bank Transfer Information (UPIC) |
| :-- | ----------- |
| **Organization:** | {{ site.data.contact.org }} |
| **Contact:** | {{ site.data.contact.press_contact }}{% if site.data.contact.press_contact_title %}, {{ site.data.contact.press_contact_title }}{% endif %} (email: {{ site.data.contact.email }} / phone: {{ site.data.contact.phone }}) |
| **Bank:** | PNC Bank |
| **Routing number:** | {{ site.data.contact.bank_routing }} |
| **Account number:** | {{ site.data.contact.bank_account }} |

{% endif %}

## Transparency

We have achieved the Silver Transparency seal from Guidestar at Candid.org. Click below to review our reports.

{% include candid-seal.html %}
