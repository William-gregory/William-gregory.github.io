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

# GPSat: Scalable Gaussian process interpolation <br>
<span style="line-height: 0;">[GitHub Repository](https://github.com/CPOMUCL/GPSat) | [Link to Paper](https://doi.org/10.1038/s41467-024-51900-x)</span>
<span style="font-size: 10px;">Collaborators: Ronald MacEachern, So Takao, Isobel Lawrence, Carmen Nab, Marc Deisenroth, Michel Tsamados</span>

<img src="http://William-gregory.github.io/images/GPSat.png" alt="GPSat" width="600" align="right"/>
<span style="font-size: 16px;">Satellite altimeters have been revolutionary in our understanding of sea ice, as they allow us to measure sea ice thickness directly from space. This has therefore given us a crucial insight into energy budgets in the Arctic, and the volumetric response of sea ice to global warming. Despite this, altimeters generally have narrow spatial footprints, on the order of 10s to 100s of metres. This means that on a given day, we may only sample a small fraction of a given spatial domain. For the CryoSat-2 radar altimeter, if data are binned to a 25 km grid, then it takes 30 days to uniformly sample the sea ice cover in the Arctic. At the footprint level it will take on the order of 1 year. These gaps in the data record make it difficult to understand how sea ice thickness changes on timescales ranging from days to weeks. Over the past few years I've been working with colleagues at University College London and the European Space Agency to develop a python programming library called 'GPSat' which attempts to fill these gaps in polar altimetry data. The idea behind GPSat is to use Gaussian Process (GP) models to learn how these observations co-vary in space and time, and to predict their values at unobserved locations. GP models are nice as they follow Bayesian principles; guiding our predictions based on our prior beliefs. The downside of GP models is that they are typically very expensive when dealing with large data sets. In this study in Nature Communications, we showed that our GPSat library can interpolate sea ice observations at relatively high spatial resoluton (5 km), and crucially, in affordable time. This is because we adopt a local approach, whereby we distribute GP models (we call them *local experts*) across the spatial domain (see image above), and then share information across these models when predicting at unobserved locations. We can also significantly speed up computations by leveraging GPU hardware.</span><br>
<span style="font-size: 16px;">In this work, we found that GPSat is over 500x faster than a naive implementation of GP models. We therefore suggested that GPSat could overcome the computational bottlenecks faced in many altimetry-based interpolation routines, and hence advance critical understanding of ocean and sea ice variability over short spatio-temporal scales.</span>

# State-dependent sea ice bias correction with machine learning <br>
<span style="line-height: 0;">[GitHub Repository](https://github.com/William-gregory/DA-ML)</span>
<span style="font-size: 10px;">Collaborators: Mitch Bushuk, Yongfei Zhang, Alistair Adcroft, Laure Zanna</span>

### Part I: Learning model error from data assimilation corrections <br>
[Link to Paper](https://doi.org/10.1029/2023MS003757)

<img src="http://William-gregory.github.io/images/JAMES_increments.png" alt="JAMES1" width="300" align="right"/>
<span style="font-size: 16px;">Climate models contain structural errors as a result of poorly parameterised or missing physics, as well as errors in the discretisation of continuous equations and errors in surface forcing. These structural errors lead to systematic biases in numerical simulations. For example, a climate model which systematically produces too much sea ice relative to a set of observations. Data Assimilation (DA) is a Bayesian framework which can reduce model biases by applying a correction, or *increment*, to the model state based on the current set of observations. These increments actually contain information about the systematic biases of a model. For example, if a model has a systematic positive bias, then the corrections generated from DA will be systematically negative (the DA is always trying to pull the model down from its positively biased state). We can therefore think of these increments as comprising some nonlinear combination of predictable model error growth associated with model bias, and an unpredictable component associated with short-term dynamics. In collaborative work with Princeton University, the Geophysical Fluid Dynamics Laboratory, and New York University, we investigated whether we could learn the predictable component of these increments using machine learning. To do this we trained convolutional neural networks to predict the increments based on the current state of the model (i.e. based on the current sea ice, ocean, and atmosphere conditions). This therefore gives rise to a *state-dependent* representation of the systematic component of model error. In our study published in the Journal of Advances in Modeling Earth Systems, we found that we can predict these increments very well in both the Arctic and Antarctic, and across all seasons. The figure on the right for example is a snapshot of the increments produced from DA (i.e. using observations), compared to the increments predicted by machine learning (i.e using only model state variables). The spatial pattern correlation (rho) is given between these two snapshots.</span><br>
<span style="font-size: 16px;">Based on this work we suggested that this machine learning model could be used to bias correct numerical simulations during forward integration of the model (when we do not have observations).</span>

### Part II: Applying the corrections in numerical simulations <br>
[Link to Paper](https://doi.org/10.1029/2023GL106776)

<img src="http://William-gregory.github.io/images/GRL_snapshot_Arctic.png" alt="GRL1" width="100%"/>
<img src="http://William-gregory.github.io/images/GRL_snapshot.png" alt="GRL2" width="100%"/>


