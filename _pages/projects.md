---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
header:
  overlay_image: "venice.jpg"
---
<!--
{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

 -->

<!-- To do:
1) d4pdf noise change project
2) Cody CCA static teleconnection
3) mike climate reservoir operations

 -->

# GPSat: Scalable Gaussian process interpolation

[GitHub Repository](https://github.com/CPOMUCL/GPSat) | [Link to Full Paper](https://doi.org/10.1038/s41467-024-51900-x)

In this study we presented GPSat; an open-source Python programming library for performing efficient interpolation of non-stationary satellite altimetry data, using scalable Gaussian process techniques. We used GPSat to generate complete maps of daily 50 km-gridded Arctic sea ice radar freeboard, and found that, relative to a previous interpolation scheme, GPSat offers a 504× computational speedup, with less than 4 mm difference on the derived freeboards on average. We then demonstrated the scalability of GPSat through freeboard interpolation at 5 km resolution, and Sea-Level Anomalies (SLA) at the resolution of the altimeter footprint. Interpolated 5 km radar freeboards showed strong agreement with airborne data (linear correlation of 0.66). Footprintlevel SLA interpolation also showed improvements in predictive skill over linear regression. In this work, we suggested that GPSat could overcome the computational bottlenecks faced in many altimetry-based interpolation routines, and hence advance critical understanding of ocean and sea ice variability over short spatio-temporal scales.


<img src="http://William-gregory.github.io/images/GPSat.png" alt="Brier" width="450"/>
