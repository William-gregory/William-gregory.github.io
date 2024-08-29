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

Collaborators: Ronald MacEachern, So Takao, Isobel Lawrence, Carmen Nab, Marc Deisenroth, Michel Tsamados

Satellite altimeters have been revolutionary in our understanding of sea ice, as they allow us to measure the thickness of the ice. Sea ice thickness plays a significant role in the sensitivity of sea ice to a given atmosphere or ocean perturbation (it takes more energy to melt thicker ice). Therefore, altimeters have given us a crucial window into sea ice volume budgets in the Arctic. Despite this, altimeters generally have narrow spatial footprints, on the order of 10s to 100s of metres. This means that on a given day, we may only sample a small fraction of a given spatial domain. For the CryoSat-2 radar altimeter, if data are binned to a 25 km grid, then it takes 30 days to uniformly sample the sea ice cover in the Arctic. At the footprint level it will take on the order of 1 year. These gaps in the data record make it difficult to understand how sea ice thickness changes on timescales ranging from days to weeks. Over the past few years I've been working with colleagues at University College London and the European Space Agency to develop a python programming library called 'GPSat' which attempts to fill these gaps in polar altimetry data. The idea behind GPSat is to use Gaussian Process (GP) models to learn how these observations co-vary in space and time, and to predict their values at unobserved locations. GP models are nice as they follow Bayesian principles; guiding our predictions based on our prior beliefs. The downside of GP models is that they are typically very expensive when dealing with large data sets. In this study in Nature Communications, we showed that our GPSat library can interpolate sea ice observations at relatively high spatial resoluton (5 km), and crucially, in affordable time. This is because we adopt a local approach, whereby we distribute GP models (we call them *local experts*) across the spatial domain (see image below), and then share information across these models when predicting at unobserved locations. We can also significantly speed up computations by leveraging GPU hardware (thanks to Tensorflow).

In this work, we found that GPSat is 500x faster than a naive implementation of GP models. We therefore suggested that GPSat could overcome the computational bottlenecks faced in many altimetry-based interpolation routines, and hence advance critical understanding of ocean and sea ice variability over short spatio-temporal scales.


<img src="http://William-gregory.github.io/images/GPSat.png" alt="Brier" width="450"/>
