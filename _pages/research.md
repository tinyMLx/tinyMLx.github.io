---
title: "View Our Research"
layout: splash
permalink: /research/
date: 
header:
  overlay_color: "#00A"
  overlay_filter: "0.5"
  overlay_image: /assets/images/banner.jpg
excerpt: "Explore our Academic Publications."
---

## Journal Articles
{% include research_table paper_list = site.data.research.journal %}

## Conference Proceedings
{% include research_table paper_list = site.data.research.conference %}

## Other Publications
{% include research_table paper_list = site.data.research.other %}