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

<span style="font-size: 16px;">In a follow-up Geophysical Research Letters study, we used the convolutional neural network which was trained to predict sea ice concentration DA increments, to do online bias correction in global ice-ocean simulations. A snapshot of the model error in summer is shown in the figures below for both the Arctic and Antarctic, where the observed ice edge is shown by the black contour. The colours then represent sea ice concentration errors relative to observations. We can see that the free-running model generally has too much sea ice in summer in both hemispheres - highlighted by the positive errors equator-ward of the observed ice edge contour. The simulation which assimilates observations (DA simulation) then reduces the ice-edge errors significantly. Impressively, the simulation which applies the machine learning correction (ML simulation) also significantly reduces the model errors, despite **never seeing any observations** - the corrections being applied during the model simulation are only a function of the model state variables themselves.</span><br>
<span style="font-size: 16px;">The results we showed in this study were for 'forced' simulations, which is where the atmosphere is prescribed from reanalysis data. Therefore the ocean and sea ice are not impacting the atmosphere in any way. The next step in this work is therefore to assess how well the machine learning correction scheme does at improving real sea ice forecasts in a fully-coupled climate model.</span>

<img src="http://William-gregory.github.io/images/GRL_snapshot_Arctic.png" alt="GRL1" width="100%"/>
<img src="http://William-gregory.github.io/images/GRL_snapshot.png" alt="GRL2" width="100%"/>

# Climate networks <br>
<span style="line-height: 0;">[GitHub Repository](https://github.com/William-gregory/ComplexNetworks)</span>
<span style="font-size: 10px;">Collaborators: Michel Tsamados, Julienne Stroeve, Peter Sollich</span>

### Part I: Atmosphere-ice teleconnections <br>
[Link to Paper](https://doi.org/10.5194/tc-16-1653-2022)

<span style="font-size: 16px;">The representation of the climate system as a complex network is a useful framework with which to visualise and understand intrinsic climate variability, as well as coupled climate interactions, or *teleconnections*. During my PhD at University College London, I developed a workflow based on unsupervised cluster analysis for representing geospatial data sets as complex networks. The first step in this approach is to perform a clustering of grid points based on their temporal correlation structure. This can be seen in the figure on the right, in which grid points have been clustered together into spatially-contigous geographic regions. For sea ice, these represent regions which have behaved in a 'homogenous' way over the length of the time-series record - by homogeneous, we mean a high anomaly correlation coefficient of local sea ice concentration.
<img src="http://William-gregory.github.io/images/SIC_network.png" alt="TC1" width="300" align="right"/>