---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

My research examines digital platforms, journalism, information integrity, migration and diaspora communication, and multilingual media systems. This page highlights selected recent work first, followed by a fuller scholarly record organized by publication type.

## Selected & Recent Publications

- **[From Detection to Counterspeech: Auditing AI Moderation and Fact-Checking Practices in Ethiopia’s Multilingual Online Sphere](/publication/2026-09-08-from-detection-to-counterspeech)**. *Media and Communication* (2026). [DOI](https://doi.org/10.17645/mac.12653)

- **[Crowdsourcing Rebellion: Digital Fundraising for Ethiopian Rebel Groups](/publication/2026-09-08-crowdsourcing-rebellion)**. *Civil Wars* (2026). [DOI](https://doi.org/10.1080/13698249.2026.2719413)

- **[Platform Oversight in Practice: How Language Shapes Procedure, Not Outcome in Meta’s Oversight Board](/publication/2026-09-08-platform-oversight-in-practice)**. *Journal of Online Trust and Safety* (2026).

- **[Faith, displacement, and intergenerational relationships: a communication accommodation theory approach to the Ethiopian Orthodox diaspora](/publication/2026-07-08-faith-displacement-intergenerational-relationships)**. *Language and Intercultural Communication* (2026). [DOI](https://doi.org/10.1080/14708477.2026.2690268)

- **[From Multidimensional Safety to Risk Ecologies: A Four-Coordinate Analysis of Journalist Exposure in Ethiopia, 1992–2024](/publication/2026-03-02-from-multidimensional-safety-to-risk-ecologies)**. *Journalism Practice* (2026). [DOI](https://doi.org/10.1080/17512786.2026.2637127)

- **[Internet shutdowns in Ethiopia: Discourses of digital sovereignty and information suppression amid political instability](/publication/2025-10-09-internet-shutdowns-in-ethiopia)**. *New Media & Society* (2025). [DOI](https://doi.org/10.1177/14614448251378981)

## Forthcoming

{% assign forthcoming = site.publications | where: "status", "forthcoming" %}
{% for post in forthcoming %}
- **[{{ post.title }}]({{ post.url | relative_url }})**. *{{ post.venue }}*. Forthcoming.
{% endfor %}

## Full Scholarly Record

### Peer-Reviewed Articles

{% assign articles = site.publications | where: "category", "manuscripts" | sort: "date" | reverse %}
{% for post in articles %}
{% unless post.status == "forthcoming" %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.venue %}. *{{ post.venue }}*{% endif %}{% if post.date %} ({{ post.date | date: "%Y" }}){% endif %}.{% if post.paperurl %} [Article / DOI]({{ post.paperurl }}){% endif %}
{% endunless %}
{% endfor %}

### Book Chapters

{% assign chapters = site.publications | where: "category", "book-chapters" | sort: "date" | reverse %}
{% for post in chapters %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.venue %}. In *{{ post.venue }}*{% endif %}{% if post.status %}. {{ post.status | capitalize }}{% endif %}.
{% endfor %}

### Reports & Applied Research

{% assign reports = site.publications | where: "category", "reports-applied-research" | sort: "date" | reverse %}
{% for post in reports %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.venue %}. {{ post.venue }}{% endif %}{% if post.date %} ({{ post.date | date: "%Y" }}){% endif %}.{% if post.paperurl %} [Full report]({{ post.paperurl }}){% endif %}
{% endfor %}

### Research Reviews & Editorial Contributions

{% assign editorial = site.publications | where: "category", "editorial-contributions" | sort: "date" | reverse %}
{% for post in editorial %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.venue %}. {{ post.venue }}{% endif %}{% if post.date %} ({{ post.date | date: "%Y" }}){% endif %}.
{% endfor %}

### Dissertation

{% assign dissertations = site.publications | where: "category", "dissertation" %}
{% for post in dissertations %}
- **[{{ post.title }}]({{ post.url | relative_url }})**. {{ post.venue }} ({{ post.date | date: "%Y" }}).{% if post.paperurl %} [University repository]({{ post.paperurl }}){% endif %}
{% endfor %}

### Earlier Research

{% assign earlier = site.publications | where: "category", "earlier-research" | sort: "date" | reverse %}
{% for post in earlier %}
- **[{{ post.title }}]({{ post.url | relative_url }})**{% if post.venue %}. {{ post.venue }}{% endif %}{% if post.date %} ({{ post.date | date: "%Y" }}){% endif %}.
{% endfor %}

For journalism and public-facing writing, see **[Selected Journalism & Public Writing](/journalism/)**. For a complete professional record, see my **[CV](/files/Endalkachew_H_Chala_CV.pdf)**.
