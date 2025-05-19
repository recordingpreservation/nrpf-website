---
title: "Edison Memorial Lecture"
date: 2023-05-01
weight: 5
teaser: "The NRPF's distinguished lecture series at the Library of Congress."
---

The NRPF annually selects an individual or group that has 
made distinguished contributions to the field of recording preservation and access
to present a lecture at the Library of Congress. 

The lecture series will be inaugurated in 2023 and the first lecture will be delivered in 2024.
Lectures are presented at the Library of Congress and 
recorded for perpetual access in the Library's collections.
Lecturers are also recognized with a cash prize.

The AES has the Heyser lecture, which focuses on the technical aspects and innovations
that support recorded sound. This lecture is intended to be a broader, publicly accessible,
and celebratory series that draws attention to both the importance of sound recording
history but also creates general interest and awareness in this history.

## Past Lectures

{% assign lectures = site.data.memorial-lecture %}
{% for lecture in lectures %}
### [{{ lecture.title }}](/events/{{ lecture.lecture_id }}/) (){: name="{{ lecture.last_name | slugify }}-{{ lecture.year | string }}"}

{{ lecture.name }}, {{ lecture.year }}

{{ lecture.abstract }}
{% endfor %}