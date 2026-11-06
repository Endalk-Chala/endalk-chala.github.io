---
layout: single
title: "Algorithms, Appeals, and Avenues: Mapping Meta's Oversight Board Across Continents"
date: 2025-05-14
permalink: /posts/2025/05/oversight-board-case-analysis/
categories:
  - blog
tags:
  - research
  - platform-governance
  - oversight-board
author_profile: true
excerpt: "Early research notes on the Meta Oversight Board's case selection, geographic representation, and accountability."
---

Over the past several months, I have conducted a comprehensive analysis of the Meta Oversight Board’s 128 published decisions to understand not only which cases the Board elects to review, but also the geographic and topical distribution of its work. My interest in this subject was piqued earlier this year when Meta quietly removed fact-checking labels from Facebook and Instagram content, raising critical questions about how appeals to “truth” might endure within the company’s increasingly narrow enforcement framework. Simultaneously, the Oversight Board—heralded as a novel experiment in corporate self-regulation—continues to face scrutiny for its opacity and slow deliberations. Journalists such as Casey Newton have critiqued its glacial pace, while scholars including Douek (2024) and Wong & Floridi (2022) have offered nuanced assessments of its institutional strengths and weaknesses.

To ground these debates in empirical evidence, I scraped each decision’s webpage to enrich the dataset with metadata—topics, outcomes, and, where available, jurisdictional information—and compiled the results into a structured CSV ([download the raw enriched data](https://raw.githubusercontent.com/Endalk-Chala/Oversight-Board-Case-Analysis/refs/heads/main/data/decisions_enriched.csv)), with all processing scripts and the methodological README available in the [GitHub repository](https://github.com/Endalk-Chala/Oversight-Board-Case-Analysis). Early in this process, it became clear that while topics and outcomes were consistently recorded, jurisdictional data remained uneven, necessitating further normalization and manual augmentation before robust geographic analysis can proceed.

With these foundations in place, I am poised to explore whether the removal of fact-checking labels has influenced the Board’s case selection—has misinformation-related content become more prominent, or have other priorities, such as hate speech or sex and gender equality, been deprioritized? From a global-majority perspective, it is equally urgent to assess whether decisions disproportionately address contexts in the Global North, despite the Global South’s larger user base. For instance, despite documented impacts of Facebook’s “Dangerous Individuals and Organizations” list on Oromo activists in Ethiopia (Hamda 2021), African contexts remain sparsely represented in the Board’s docket.

This quantitative groundwork also invites comparative analysis with other emerging oversight models. TikTok’s recently announced review body, though lacking the Oversight Board’s public transparency, suggests an alternative approach to external accountability. Juxtaposing these frameworks may illuminate whether true independence can coexist with operational agility, or whether formal legitimacy inevitably impedes responsiveness.

Ultimately, by mapping case topics and jurisdictions over time, I aim to determine whether the Oversight Board fulfills its promise of broad, equitable governance—or whether enduring gaps reveal the inherent limits of corporate self-regulation in shaping the global flow of information. As the data coalesces into analyzable form, I look forward to sharing the emerging patterns and asking whether the Oversight Board can, at last, keep pace with the diverse communities it was created to serve.
