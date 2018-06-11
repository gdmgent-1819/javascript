---
layout   : course
permalink: introductie/ects/
published: true
#
title     : ECTS
title_long: ECTS-fiche
description: ECTS-fiche
---
{%- assign syllabus = site.data.shared.syllabi | where: 'id', site.syllabus-id | first %}
{% include abbreviations/education.md %}
{% include abbreviations/computer.md %}
{% include hyperlinks/education.md %}

{% include course/content/info-ects.md %}

Studieomvang
------------

{% include course/content/info-workload.md %}

Competenties
------------

### Begincompetenties

{% include course/content/info-competences-start.md %}

### Eindcompetenties

{% include course/content/info-competences-end.md %}

Doelstellingen
--------------

{% include course/content/info-objectives.md %}

Inhoud
------

{% include course/content/info-content.md %}


Studiemateriaal
---------------

{% include course/content/info-course-materials.md %}